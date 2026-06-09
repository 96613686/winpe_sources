# ConvertStringSDToSDDomainA

- ea: `0x180052dc0`
- end: `0x180052eb1`
- name: `ConvertStringSDToSDDomainA`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001aa10`
- `0x180052dc0`
- `0x180052ec0`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180052e0a`
- `ntdll!RtlValidSid` at `0x180052e20`
- `ntdll!RtlValidSid` at `0x180052e0a`
- `ntdll!RtlValidSid` at `0x180052e20`
- `ntdll!RtlNtStatusToDosError` at `0x180052e4d`
- `ntdll!RtlNtStatusToDosError` at `0x180052e4d`
- `ntdll!RtlInitAnsiString` at `0x180052e32`
- `ntdll!RtlInitAnsiString` at `0x180052e32`
- `KERNEL32!LocalFree` at `0x180052e83`
- `KERNEL32!LocalFree` at `0x180052e83`
- `KERNEL32!SetLastError` at `0x180052e8f`
- `KERNEL32!SetLastError` at `0x180052e9e`
- `KERNEL32!SetLastError` at `0x180052e8f`
- `KERNEL32!SetLastError` at `0x180052e9e`

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
0x180052dc0  push    rbx
0x180052dc2  push    rbp
0x180052dc3  push    rsi
0x180052dc4  push    rdi
0x180052dc5  push    r14
0x180052dc7  sub     rsp, 50h
0x180052dcb  xorps   xmm0, xmm0
0x180052dce  xorps   xmm1, xmm1
0x180052dd1  mov     r14d, r9d
0x180052dd4  mov     rbp, r8
0x180052dd7  mov     rbx, rdx
0x180052dda  mov     rdi, rcx
0x180052ddd  movups  xmmword ptr [rsp+78h+hMem], xmm0
0x180052de2  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x180052de7  test    r8, r8
0x180052dea  jz      loc_180052E99
0x180052df0  mov     rsi, [rsp+78h+arg_20]
0x180052df8  test    rsi, rsi
0x180052dfb  jz      loc_180052E99
0x180052e01  test    rcx, rcx
0x180052e04  jz      loc_180052E99
0x180052e0a  call    cs:__imp_RtlValidSid
0x180052e10  test    al, al
0x180052e12  jz      loc_180052E99
0x180052e18  test    rbx, rbx
0x180052e1b  jz      short loc_180052E2A
0x180052e1d  mov     rcx, rbx; Sid
0x180052e20  call    cs:__imp_RtlValidSid
0x180052e26  test    al, al
0x180052e28  jz      short loc_180052E99
0x180052e2a  mov     rdx, rbp; SourceString
0x180052e2d  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180052e32  call    cs:__imp_RtlInitAnsiString
0x180052e38  lea     rdx, [rsp+78h+DestinationString]
0x180052e3d  lea     rcx, [rsp+78h+hMem]
0x180052e42  call    SddlpAnsiStringToUnicodeString
0x180052e47  test    eax, eax
0x180052e49  jns     short loc_180052E57
0x180052e4b  mov     ecx, eax; Status
0x180052e4d  call    cs:__imp_RtlNtStatusToDosError
0x180052e53  mov     ecx, eax
0x180052e55  jmp     short loc_180052E9E
0x180052e57  mov     rax, [rsp+78h+arg_28]
0x180052e5f  mov     r9d, r14d
0x180052e62  mov     r8, [rsp+78h+hMem+8]
0x180052e67  mov     rdx, rbx
0x180052e6a  mov     [rsp+78h+var_50], rax
0x180052e6f  mov     rcx, rdi
0x180052e72  mov     [rsp+78h+var_58], rsi
0x180052e77  call    ConvertStringSDToSDDomainW
0x180052e7c  mov     rcx, [rsp+78h+hMem+8]; hMem
0x180052e81  mov     ebx, eax
0x180052e83  call    cs:__imp_LocalFree
0x180052e89  test    ebx, ebx
0x180052e8b  jz      short loc_180052E95
0x180052e8d  xor     ecx, ecx; dwErrCode
0x180052e8f  call    cs:__imp_SetLastError
0x180052e95  mov     eax, ebx
0x180052e97  jmp     short loc_180052EA6
0x180052e99  mov     ecx, 57h ; 'W'; dwErrCode
0x180052e9e  call    cs:__imp_SetLastError
0x180052ea4  xor     eax, eax
0x180052ea6  add     rsp, 50h
0x180052eaa  pop     r14
0x180052eac  pop     rdi
0x180052ead  pop     rsi
0x180052eae  pop     rbp
0x180052eaf  pop     rbx
0x180052eb0  retn
```
