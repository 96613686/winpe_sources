# ConvertStringSDToSDDomainA

- ea: `0x18005e810`
- end: `0x18005e930`
- name: `ConvertStringSDToSDDomainA`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180019344`
- `0x18005e810`
- `0x18005e940`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18005e85a`
- `ntdll!RtlValidSid` at `0x18005e876`
- `ntdll!RtlValidSid` at `0x18005e85a`
- `ntdll!RtlValidSid` at `0x18005e876`
- `ntdll!RtlNtStatusToDosError` at `0x18005e8b3`
- `ntdll!RtlNtStatusToDosError` at `0x18005e8b3`
- `ntdll!RtlInitAnsiString` at `0x18005e892`
- `ntdll!RtlInitAnsiString` at `0x18005e892`
- `KERNEL32!LocalFree` at `0x18005e8ef`
- `KERNEL32!LocalFree` at `0x18005e8ef`
- `KERNEL32!SetLastError` at `0x18005e901`
- `KERNEL32!SetLastError` at `0x18005e916`
- `KERNEL32!SetLastError` at `0x18005e901`
- `KERNEL32!SetLastError` at `0x18005e916`

## pseudocode

```c
__int64 __fastcall ConvertStringSDToSDDomainA(
        void *a1,
        void *a2,
        const char *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  NTSTATUS v10; // eax
  ULONG v11; // ecx
  unsigned int v12; // ebx
  HLOCAL hMem[2]; // [rsp+30h] [rbp-48h] BYREF
  struct _STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  *(_OWORD *)hMem = 0;
  DestinationString = 0;
  if ( !a3 || !a5 || !a1 || !RtlValidSid(a1) || a2 && !RtlValidSid(a2) )
  {
    v11 = 87;
    goto LABEL_13;
  }
  RtlInitAnsiString(&DestinationString, a3);
  v10 = SddlpAnsiStringToUnicodeString(hMem, &DestinationString);
  if ( v10 < 0 )
  {
    v11 = RtlNtStatusToDosError(v10);
LABEL_13:
    SetLastError(v11);
    return 0;
  }
  v12 = ConvertStringSDToSDDomainW(a1, a2, hMem[1], a4, a5, a6, hMem[0]);
  LocalFree(hMem[1]);
  if ( v12 )
    SetLastError(0);
  return v12;
}

```

## disassembly

```asm
0x18005e810  push    rbx
0x18005e812  push    rbp
0x18005e813  push    rsi
0x18005e814  push    rdi
0x18005e815  push    r14
0x18005e817  sub     rsp, 50h
0x18005e81b  xorps   xmm0, xmm0
0x18005e81e  xorps   xmm1, xmm1
0x18005e821  mov     r14d, r9d
0x18005e824  mov     rbp, r8
0x18005e827  mov     rbx, rdx
0x18005e82a  mov     rdi, rcx
0x18005e82d  movups  xmmword ptr [rsp+78h+hMem], xmm0
0x18005e832  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x18005e837  test    r8, r8
0x18005e83a  jz      loc_18005E911
0x18005e840  mov     rsi, [rsp+78h+arg_20]
0x18005e848  test    rsi, rsi
0x18005e84b  jz      loc_18005E911
0x18005e851  test    rcx, rcx
0x18005e854  jz      loc_18005E911
0x18005e85a  call    cs:__imp_RtlValidSid
0x18005e861  nop     dword ptr [rax+rax+00h]
0x18005e866  test    al, al
0x18005e868  jz      loc_18005E911
0x18005e86e  test    rbx, rbx
0x18005e871  jz      short loc_18005E88A
0x18005e873  mov     rcx, rbx; Sid
0x18005e876  call    cs:__imp_RtlValidSid
0x18005e87d  nop     dword ptr [rax+rax+00h]
0x18005e882  test    al, al
0x18005e884  jz      loc_18005E911
0x18005e88a  mov     rdx, rbp; SourceString
0x18005e88d  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18005e892  call    cs:__imp_RtlInitAnsiString
0x18005e899  nop     dword ptr [rax+rax+00h]
0x18005e89e  lea     rdx, [rsp+78h+DestinationString]
0x18005e8a3  lea     rcx, [rsp+78h+hMem]
0x18005e8a8  call    SddlpAnsiStringToUnicodeString
0x18005e8ad  test    eax, eax
0x18005e8af  jns     short loc_18005E8C3
0x18005e8b1  mov     ecx, eax; Status
0x18005e8b3  call    cs:__imp_RtlNtStatusToDosError
0x18005e8ba  nop     dword ptr [rax+rax+00h]
0x18005e8bf  mov     ecx, eax
0x18005e8c1  jmp     short loc_18005E916
0x18005e8c3  mov     rax, [rsp+78h+arg_28]
0x18005e8cb  mov     r9d, r14d
0x18005e8ce  mov     r8, [rsp+78h+hMem+8]
0x18005e8d3  mov     rdx, rbx
0x18005e8d6  mov     [rsp+78h+var_50], rax
0x18005e8db  mov     rcx, rdi
0x18005e8de  mov     [rsp+78h+var_58], rsi
0x18005e8e3  call    ConvertStringSDToSDDomainW
0x18005e8e8  mov     rcx, [rsp+78h+hMem+8]; hMem
0x18005e8ed  mov     ebx, eax
0x18005e8ef  call    cs:__imp_LocalFree
0x18005e8f6  nop     dword ptr [rax+rax+00h]
0x18005e8fb  test    ebx, ebx
0x18005e8fd  jz      short loc_18005E90D
0x18005e8ff  xor     ecx, ecx; dwErrCode
0x18005e901  call    cs:__imp_SetLastError
0x18005e908  nop     dword ptr [rax+rax+00h]
0x18005e90d  mov     eax, ebx
0x18005e90f  jmp     short loc_18005E924
0x18005e911  mov     ecx, 57h ; 'W'; dwErrCode
0x18005e916  call    cs:__imp_SetLastError
0x18005e91d  nop     dword ptr [rax+rax+00h]
0x18005e922  xor     eax, eax
0x18005e924  add     rsp, 50h
0x18005e928  pop     r14
0x18005e92a  pop     rdi
0x18005e92b  pop     rsi
0x18005e92c  pop     rbp
0x18005e92d  pop     rbx
0x18005e92e  retn
```
