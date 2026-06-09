# LsaOpenLocalSystemPolicy(ulong,_SECURITY_QUALITY_OF_SERVICE *,void * *)

- ea: `0x18000c800`
- end: `0x18000c898`
- name: `?LsaOpenLocalSystemPolicy@@YAKKPEAU_SECURITY_QUALITY_OF_SERVICE@@PEAPEAX@Z`
- size: `152`
- prototype: `ULONG __fastcall(__int64, struct _SECURITY_QUALITY_OF_SERVICE *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c8a0`

## callees

- `0x18000c800`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000c882`
- `ntdll!RtlNtStatusToDosError` at `0x18000c882`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c869`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c869`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000c84c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000c84c`

## pseudocode

```c
ULONG __fastcall LsaOpenLocalSystemPolicy(__int64 a1, struct _SECURITY_QUALITY_OF_SERVICE *a2, void **a3)
{
  int v3; // ebx
  int v5; // eax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp+18h] BYREF

  v3 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  PolicyHandle = 0;
  ObjectAttributes.SecurityQualityOfService = a2;
  while ( 1 )
  {
    v5 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
    if ( (unsigned int)(v5 + 1073610729) > 1 )
      break;
    if ( ++v3 >= 10 )
      break;
    Sleep(0xAu);
  }
  if ( v5 < 0 )
    return RtlNtStatusToDosError(v5);
  *a3 = PolicyHandle;
  return 0;
}

```

## disassembly

```asm
0x18000c800  mov     [rsp-8+arg_0], rbx
0x18000c805  mov     [rsp-8+arg_10], rdi
0x18000c80a  push    rbp
0x18000c80b  mov     rbp, rsp
0x18000c80e  sub     rsp, 50h
0x18000c812  xor     ebx, ebx
0x18000c814  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000c81c  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18000c820  mov     rdi, r8
0x18000c823  mov     [rbp+ObjectAttributes.ObjectName], rbx
0x18000c827  mov     [rbp+ObjectAttributes.SecurityDescriptor], rbx
0x18000c82b  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18000c833  mov     [rbp+PolicyHandle], 0
0x18000c83b  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rdx
0x18000c83f  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x18000c843  mov     edx, 1; AccessMask
0x18000c848  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x18000c84c  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18000c852  lea     ecx, [rax+3FFDFFE9h]
0x18000c858  cmp     ecx, 1
0x18000c85b  ja      short loc_18000C871
0x18000c85d  inc     ebx
0x18000c85f  cmp     ebx, 0Ah
0x18000c862  jge     short loc_18000C871
0x18000c864  mov     ecx, 0Ah; dwMilliseconds
0x18000c869  call    cs:__imp_Sleep
0x18000c86f  jmp     short loc_18000C83F
0x18000c871  test    eax, eax
0x18000c873  js      short loc_18000C880
0x18000c875  mov     rax, [rbp+PolicyHandle]
0x18000c879  mov     [rdi], rax
0x18000c87c  xor     eax, eax
0x18000c87e  jmp     short loc_18000C888
0x18000c880  mov     ecx, eax; Status
0x18000c882  call    cs:__imp_RtlNtStatusToDosError
0x18000c888  mov     rbx, [rsp+50h+arg_0]
0x18000c88d  mov     rdi, [rsp+50h+arg_10]
0x18000c892  add     rsp, 50h
0x18000c896  pop     rbp
0x18000c897  retn
```
