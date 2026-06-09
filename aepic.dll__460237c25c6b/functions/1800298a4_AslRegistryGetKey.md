# AslRegistryGetKey

- ea: `0x1800298a4`
- end: `0x180029994`
- name: `AslRegistryGetKey`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e1a8`

## callees

- `0x1800295dc`
- `0x18002979c`
- `0x1800297bc`
- `0x1800298a4`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18002993d`
- `ntdll!ZwOpenKey` at `0x18002993d`

## string_xrefs

- `0x1800298e1`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x1800298f3`: `AslRegistryGetKey`
- `0x180029950`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+28h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  v4 = AslRegistryBuildMachinePath(&Destination, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = "AslRegistryBuildMachinePath failed %x for %ws";
    v7 = 1718;
LABEL_3:
    AslLogCallPrintf(1, "AslRegistryGetKey", v7, v6, v4, a2);
    goto LABEL_8;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v5 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
  else if ( v4 != -1073741772 )
  {
    v6 = "NtOpenKey failed %x for %ws";
    v7 = 1761;
    goto LABEL_3;
  }
LABEL_8:
  if ( Destination.Buffer )
    AslFree(NtCurrentPeb()->ProcessHeap, Destination.Buffer);
  return v5;
}

```

## disassembly

```asm
0x1800298a4  push    rbp
0x1800298a6  push    rbx
0x1800298a7  push    rsi
0x1800298a8  push    rdi
0x1800298a9  mov     rbp, rsp
0x1800298ac  sub     rsp, 78h
0x1800298b0  xorps   xmm0, xmm0
0x1800298b3  xor     eax, eax
0x1800298b5  mov     [rcx], rax
0x1800298b8  mov     rsi, rcx
0x1800298bb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800298bf  lea     rcx, [rbp+Destination]; Destination
0x1800298c3  mov     [rbp+KeyHandle], rax
0x1800298c7  mov     rdi, rdx
0x1800298ca  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800298ce  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800298d2  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x1800298d6  call    AslRegistryBuildMachinePath
0x1800298db  mov     ebx, eax
0x1800298dd  test    eax, eax
0x1800298df  jns     short loc_18002990A
0x1800298e1  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x1800298e8  mov     r8d, 6B6h
0x1800298ee  mov     [rsp+78h+var_50], rdi
0x1800298f3  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x1800298fa  mov     ecx, 1
0x1800298ff  mov     [rsp+78h+var_58], eax
0x180029903  call    AslLogCallPrintf
0x180029908  jmp     short loc_18002996C
0x18002990a  lea     rax, [rbp+Destination]
0x18002990e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180029915  xorps   xmm0, xmm0
0x180029918  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002991c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180029920  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180029928  mov     edx, 1; DesiredAccess
0x18002992d  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180029934  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180029938  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002993d  call    cs:__imp_ZwOpenKey
0x180029943  mov     ebx, eax
0x180029945  test    eax, eax
0x180029947  jns     short loc_18002995F
0x180029949  cmp     eax, 0C0000034h
0x18002994e  jz      short loc_18002996C
0x180029950  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x180029957  mov     r8d, 6E1h
0x18002995d  jmp     short loc_1800298EE
0x18002995f  mov     rax, [rbp+KeyHandle]
0x180029963  xor     ebx, ebx
0x180029965  mov     [rsi], rax
0x180029968  mov     [rbp+KeyHandle], rbx
0x18002996c  cmp     [rbp+Destination.Buffer], 0
0x180029971  jz      short loc_180029989
0x180029973  mov     rcx, gs:60h
0x18002997c  mov     rdx, [rbp+Destination.Buffer]
0x180029980  mov     rcx, [rcx+30h]
0x180029984  call    AslFree
0x180029989  mov     eax, ebx
0x18002998b  add     rsp, 78h
0x18002998f  pop     rdi
0x180029990  pop     rsi
0x180029991  pop     rbx
0x180029992  pop     rbp
0x180029993  retn
```
