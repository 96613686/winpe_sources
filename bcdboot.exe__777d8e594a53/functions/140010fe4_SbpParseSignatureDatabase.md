# SbpParseSignatureDatabase

- ea: `0x140010fe4`
- end: `0x1400111a5`
- name: `SbpParseSignatureDatabase`
- size: `449`
- prototype: `__int64 __fastcall(PCWSTR SourceString, LPGUID VendorGuid, _QWORD *, _DWORD *, _QWORD *, _DWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000fa8c`

## callees

- `0x140010e28`
- `0x140010fe4`
- `0x1400111ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400110e0`
- `KERNEL32!GetLastError` at `0x140011189`
- `KERNEL32!GetLastError` at `0x1400110e0`
- `KERNEL32!GetLastError` at `0x140011189`
- `KERNEL32!LocalFree` at `0x1400110d3`
- `KERNEL32!LocalFree` at `0x14001117e`
- `KERNEL32!LocalFree` at `0x1400110d3`
- `KERNEL32!LocalFree` at `0x14001117e`
- `KERNEL32!LocalAlloc` at `0x14001108f`
- `KERNEL32!LocalAlloc` at `0x14001108f`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x14001106c`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x1400110bb`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x14001106c`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x1400110bb`
- `ntdll!RtlInitUnicodeString` at `0x140011053`
- `ntdll!RtlInitUnicodeString` at `0x140011053`

## string_xrefs

- `0x140011009`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
__int64 __fastcall SbpParseSignatureDatabase(
        PCWSTR SourceString,
        LPGUID VendorGuid,
        _QWORD *a3,
        _DWORD *a4,
        _QWORD *a5,
        _DWORD *a6,
        _QWORD *a7,
        _DWORD *a8)
{
  void *v9; // rdi
  NTSTATUS v13; // ebx
  ULONG v14; // r14d
  HLOCAL v15; // rsi
  ULONG ReturnLength; // [rsp+40h] [rbp-41h] BYREF
  int v18; // [rsp+44h] [rbp-3Dh] BYREF
  int v19; // [rsp+48h] [rbp-39h] BYREF
  int v20; // [rsp+4Ch] [rbp-35h] BYREF
  ULONG Attributes; // [rsp+50h] [rbp-31h] BYREF
  __int64 v22; // [rsp+58h] [rbp-29h] BYREF
  __int64 v23; // [rsp+60h] [rbp-21h] BYREF
  __int64 v24; // [rsp+68h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-11h] BYREF

  v23 = 0;
  v19 = 0;
  v24 = 0;
  v9 = 0;
  v20 = 0;
  v22 = 0;
  v18 = 0;
  Attributes = 0;
  DestinationString = 0;
  ReturnLength = 0;
  if ( (int)SbpEnablePrivilege(L"SeSystemEnvironmentPrivilege") >= 0 )
  {
    v14 = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    v13 = NtQuerySystemEnvironmentValueEx(&DestinationString, VendorGuid, 0, &ReturnLength, 0);
    if ( (int)(v13 + 0x80000000) < 0 || v13 == -1073741789 )
    {
      v15 = LocalAlloc(0x40u, ReturnLength);
      if ( v15 )
      {
        v13 = NtQuerySystemEnvironmentValueEx(&DestinationString, VendorGuid, v15, &ReturnLength, &Attributes);
        if ( v13 < 0 )
        {
          if ( LocalFree(v15) )
            GetLastError();
        }
        else
        {
          v14 = ReturnLength;
          v9 = v15;
        }
      }
      else
      {
        v13 = -1073741670;
      }
    }
    SbpEnablePrivilege(0);
    if ( v13 >= 0 )
    {
      v13 = SbpParseSignatureDatabaseFromBuffer(
              (_DWORD)v9,
              v14,
              (unsigned int)&v22,
              (unsigned int)&v18,
              (__int64)&v23,
              (__int64)&v19,
              (__int64)&v24,
              (__int64)&v20);
      if ( v13 >= 0 )
      {
        *a3 = v22;
        *a4 = v18;
        *a5 = v23;
        *a6 = v19;
        if ( a7 )
          *a7 = v24;
        if ( a8 )
          *a8 = v20;
      }
    }
  }
  else
  {
    v13 = -1073741727;
  }
  if ( v9 && LocalFree(v9) )
    GetLastError();
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140010fe4  push    rbp
0x140010fe6  push    rbx
0x140010fe7  push    rsi
0x140010fe8  push    rdi
0x140010fe9  push    r12
0x140010feb  push    r13
0x140010fed  push    r14
0x140010fef  push    r15
0x140010ff1  lea     rbp, [rsp-7]
0x140010ff6  sub     rsp, 88h
0x140010ffd  xor     esi, esi
0x140010fff  mov     rbx, rcx
0x140011002  xorps   xmm0, xmm0
0x140011005  mov     [rbp+3Fh+var_60], rsi
0x140011009  lea     rcx, Name; "SeSystemEnvironmentPrivilege"
0x140011010  mov     [rbp+3Fh+var_78], esi
0x140011013  mov     [rbp+3Fh+var_58], rsi
0x140011017  mov     edi, esi
0x140011019  mov     [rbp+3Fh+var_74], esi
0x14001101c  mov     r12, r9
0x14001101f  mov     [rbp+3Fh+var_68], rsi
0x140011023  mov     r13, r8
0x140011026  mov     [rbp+3Fh+var_7C], esi
0x140011029  mov     r15, rdx
0x14001102c  mov     [rbp+3Fh+var_70], esi
0x14001102f  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140011033  mov     [rbp+3Fh+ReturnLength], esi
0x140011036  call    SbpEnablePrivilege
0x14001103b  test    eax, eax
0x14001103d  jns     short loc_140011049
0x14001103f  mov     ebx, 0C0000061h
0x140011044  jmp     loc_140011176
0x140011049  mov     rdx, rbx; SourceString
0x14001104c  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140011050  mov     r14d, esi
0x140011053  call    cs:__imp_RtlInitUnicodeString
0x140011059  lea     r9, [rbp+3Fh+ReturnLength]; ReturnLength
0x14001105d  mov     [rsp+0C0h+Attributes], rsi; Attributes
0x140011062  xor     r8d, r8d; Value
0x140011065  lea     rcx, [rbp+3Fh+DestinationString]; VariableName
0x140011069  mov     rdx, r15; VendorGuid
0x14001106c  call    cs:__imp_NtQuerySystemEnvironmentValueEx
0x140011072  mov     ecx, 80000000h
0x140011077  mov     ebx, eax
0x140011079  add     eax, ecx
0x14001107b  test    ecx, eax
0x14001107d  jnz     short loc_140011087
0x14001107f  cmp     ebx, 0C0000023h
0x140011085  jnz     short loc_1400110E6
0x140011087  mov     edx, [rbp+3Fh+ReturnLength]; uBytes
0x14001108a  mov     ecx, 40h ; '@'; uFlags
0x14001108f  call    cs:__imp_LocalAlloc
0x140011095  mov     rsi, rax
0x140011098  test    rax, rax
0x14001109b  jnz     short loc_1400110A4
0x14001109d  mov     ebx, 0C000009Ah
0x1400110a2  jmp     short loc_1400110E6
0x1400110a4  lea     rax, [rbp+3Fh+var_70]
0x1400110a8  mov     r8, rsi; Value
0x1400110ab  lea     r9, [rbp+3Fh+ReturnLength]; ReturnLength
0x1400110af  mov     [rsp+0C0h+Attributes], rax; Attributes
0x1400110b4  mov     rdx, r15; VendorGuid
0x1400110b7  lea     rcx, [rbp+3Fh+DestinationString]; VariableName
0x1400110bb  call    cs:__imp_NtQuerySystemEnvironmentValueEx
0x1400110c1  mov     ebx, eax
0x1400110c3  test    eax, eax
0x1400110c5  js      short loc_1400110D0
0x1400110c7  mov     r14d, [rbp+3Fh+ReturnLength]
0x1400110cb  mov     rdi, rsi
0x1400110ce  jmp     short loc_1400110E6
0x1400110d0  mov     rcx, rsi; hMem
0x1400110d3  call    cs:__imp_LocalFree
0x1400110d9  xor     esi, esi
0x1400110db  test    rax, rax
0x1400110de  jz      short loc_1400110E6
0x1400110e0  call    cs:__imp_GetLastError
0x1400110e6  xor     ecx, ecx; lpName
0x1400110e8  call    SbpEnablePrivilege
0x1400110ed  test    ebx, ebx
0x1400110ef  js      loc_140011176
0x1400110f5  lea     rax, [rbp+3Fh+var_74]
0x1400110f9  mov     edx, r14d
0x1400110fc  mov     [rsp+0C0h+var_88], rax
0x140011101  lea     r9, [rbp+3Fh+var_7C]
0x140011105  lea     rax, [rbp+3Fh+var_58]
0x140011109  mov     rcx, rdi
0x14001110c  mov     [rsp+0C0h+var_90], rax
0x140011111  lea     r8, [rbp+3Fh+var_68]
0x140011115  lea     rax, [rbp+3Fh+var_78]
0x140011119  mov     [rsp+0C0h+var_98], rax
0x14001111e  lea     rax, [rbp+3Fh+var_60]
0x140011122  mov     [rsp+0C0h+Attributes], rax
0x140011127  call    SbpParseSignatureDatabaseFromBuffer
0x14001112c  mov     ebx, eax
0x14001112e  test    eax, eax
0x140011130  js      short loc_140011176
0x140011132  mov     rcx, [rbp+3Fh+var_68]
0x140011136  mov     rdx, [rbp+3Fh+arg_20]
0x14001113a  mov     [r13+0], rcx
0x14001113e  mov     ecx, [rbp+3Fh+var_7C]
0x140011141  mov     [r12], ecx
0x140011145  mov     rcx, [rbp+3Fh+var_60]
0x140011149  mov     [rdx], rcx
0x14001114c  mov     ecx, [rbp+3Fh+var_78]
0x14001114f  mov     rdx, [rbp+3Fh+arg_28]
0x140011153  mov     [rdx], ecx
0x140011155  mov     rcx, [rbp+3Fh+arg_30]
0x140011159  test    rcx, rcx
0x14001115c  jz      short loc_140011165
0x14001115e  mov     rax, [rbp+3Fh+var_58]
0x140011162  mov     [rcx], rax
0x140011165  mov     rcx, [rbp+3Fh+arg_38]
0x14001116c  test    rcx, rcx
0x14001116f  jz      short loc_140011176
0x140011171  mov     eax, [rbp+3Fh+var_74]
0x140011174  mov     [rcx], eax
0x140011176  test    rdi, rdi
0x140011179  jz      short loc_14001118F
0x14001117b  mov     rcx, rdi; hMem
0x14001117e  call    cs:__imp_LocalFree
0x140011184  test    rax, rax
0x140011187  jz      short loc_14001118F
0x140011189  call    cs:__imp_GetLastError
0x14001118f  mov     eax, ebx
0x140011191  add     rsp, 88h
0x140011198  pop     r15
0x14001119a  pop     r14
0x14001119c  pop     r13
0x14001119e  pop     r12
0x1400111a0  pop     rdi
0x1400111a1  pop     rsi
0x1400111a2  pop     rbx
0x1400111a3  pop     rbp
0x1400111a4  retn
```
