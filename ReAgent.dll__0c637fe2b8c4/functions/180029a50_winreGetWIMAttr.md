# winreGetWIMAttr

- ea: `0x180029a50`
- end: `0x180029c1e`
- name: `winreGetWIMAttr`
- size: `462`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x1800170a4`
- `0x180017248`
- `0x180023590`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c658`
- `0x18000ff68`
- `0x18000ffcc`
- `0x180011074`
- `0x180029a50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029bf5`
- `KERNEL32!GetLastError` at `0x180029bf5`
- `KERNEL32!GetFileAttributesExW` at `0x180029beb`
- `KERNEL32!GetFileAttributesExW` at `0x180029beb`
- `ole32!CoTaskMemFree` at `0x180029c05`
- `ole32!CoTaskMemFree` at `0x180029c05`

## string_xrefs

- `0x180029a92`: `failed to allocate path`
- `0x180029a99`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180029aee`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180029baf`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180029af8`: `failed to copy string`

## pseudocode

```c
__int64 __fastcall winreGetWIMAttr(__int64 a1, void *a2, __int64 a3, const unsigned __int16 *a4)
{
  signed int v8; // eax
  unsigned __int16 *v9; // rdi
  signed int LastError; // ebx
  const wchar_t *v11; // r8
  int v12; // esi
  int v14; // [rsp+28h] [rbp-60h]
  int v15; // [rsp+28h] [rbp-60h]
  LPCWSTR lpFileName[11]; // [rsp+30h] [rbp-58h] BYREF

  lpFileName[0] = 0;
  v8 = winreAllocPath(lpFileName);
  v9 = (unsigned __int16 *)lpFileName[0];
  LastError = v8;
  if ( v8 )
  {
    v14 = 1800;
    v11 = L"failed to allocate path";
LABEL_3:
    UnattendLogW(
      2,
      L"winreGetWIMAttr %s (0x%x) in file %S line %d",
      v11,
      (unsigned int)LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v14);
    goto LABEL_22;
  }
  if ( *(_DWORD *)(a3 + 5588) )
  {
    LastError = StringCchCopyW((unsigned __int16 *)lpFileName[0], 0x12Eu, (const unsigned __int16 *)(a3 + 16));
    if ( LastError < 0 )
    {
      v15 = 1810;
LABEL_7:
      UnattendLogW(
        2,
        L"winreGetWIMAttr %s (0x%x) in file %S line %d",
        L"failed to copy string",
        (unsigned int)LastError,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        v15);
      LastError = (unsigned __int16)LastError;
      goto LABEL_22;
    }
  }
  else if ( a4 && *a4 )
  {
    LastError = StringCchCopyW((unsigned __int16 *)lpFileName[0], 0x12Eu, a4);
    if ( LastError < 0 )
    {
      v15 = 1822;
      goto LABEL_7;
    }
  }
  else if ( !(unsigned int)winreIsImageStaged(a1, a3, lpFileName[0]) )
  {
    if ( !ReAgentError )
      ReAgentError = 14;
    LastError = 1614;
    goto LABEL_22;
  }
  LastError = winreAddTrailingBackslash(v9);
  if ( LastError )
  {
    v14 = 1837;
    v11 = L"failed to add trailing back slash";
    goto LABEL_3;
  }
  v12 = StringCchCatW(v9, 0x12Eu, L"Winre.wim");
  if ( v12 >= 0 )
  {
    if ( !GetFileAttributesExW(v9, GetFileExInfoStandard, a2) )
      LastError = GetLastError();
  }
  else
  {
    UnattendLogW(
      2,
      L"winreGetWIMAttr %s (0x%x) in file %S line %d",
      L"failed to concatenate winre.wim file name",
      (unsigned int)v12,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      1838);
    LastError = (unsigned __int16)v12;
  }
LABEL_22:
  if ( v9 )
    CoTaskMemFree(v9);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180029a50  push    rbx
0x180029a52  push    rbp
0x180029a53  push    rsi
0x180029a54  push    rdi
0x180029a55  push    r12
0x180029a57  push    r13
0x180029a59  push    r14
0x180029a5b  push    r15
0x180029a5d  sub     rsp, 48h
0x180029a61  mov     r14, rcx
0x180029a64  xor     r12d, r12d
0x180029a67  lea     rcx, [rsp+88h+lpFileName]
0x180029a6c  mov     [rsp+88h+lpFileName], r12
0x180029a71  mov     rsi, r9
0x180029a74  mov     rbp, r8
0x180029a77  mov     r15, rdx
0x180029a7a  call    winreAllocPath
0x180029a7f  mov     rdi, [rsp+88h+lpFileName]
0x180029a84  mov     ebx, eax
0x180029a86  test    eax, eax
0x180029a88  jz      short loc_180029ABE
0x180029a8a  mov     [rsp+88h+var_60], 708h
0x180029a92  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180029a99  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180029aa0  mov     r9d, ebx
0x180029aa3  lea     rdx, aWinregetwimatt; "winreGetWIMAttr %s (0x%x) in file %S li"...
0x180029aaa  mov     [rsp+88h+var_68], rax
0x180029aaf  mov     ecx, 2
0x180029ab4  call    UnattendLogW
0x180029ab9  jmp     loc_180029BFD
0x180029abe  mov     r13d, 12Eh
0x180029ac4  cmp     [rbp+15D4h], r12d
0x180029acb  jz      short loc_180029B1D
0x180029acd  lea     r8, [rbp+10h]; unsigned __int16 *
0x180029ad1  mov     edx, r13d; unsigned __int64
0x180029ad4  mov     rcx, rdi; unsigned __int16 *
0x180029ad7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029adc  mov     ebx, eax
0x180029ade  test    eax, eax
0x180029ae0  jns     loc_180029B75
0x180029ae6  mov     [rsp+88h+var_60], 712h
0x180029aee  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180029af5  mov     r9d, ebx
0x180029af8  lea     r8, aFailedToCopySt; "failed to copy string"
0x180029aff  mov     [rsp+88h+var_68], rax
0x180029b04  lea     rdx, aWinregetwimatt; "winreGetWIMAttr %s (0x%x) in file %S li"...
0x180029b0b  mov     ecx, 2
0x180029b10  call    UnattendLogW
0x180029b15  movzx   ebx, bx
0x180029b18  jmp     loc_180029BFD
0x180029b1d  test    rsi, rsi
0x180029b20  jz      short loc_180029B46
0x180029b22  cmp     [rsi], r12w
0x180029b26  jz      short loc_180029B46
0x180029b28  mov     r8, rsi; unsigned __int16 *
0x180029b2b  mov     rdx, r13; unsigned __int64
0x180029b2e  mov     rcx, rdi; unsigned __int16 *
0x180029b31  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029b36  mov     ebx, eax
0x180029b38  test    eax, eax
0x180029b3a  jns     short loc_180029B75
0x180029b3c  mov     [rsp+88h+var_60], 71Eh
0x180029b44  jmp     short loc_180029AEE
0x180029b46  mov     r8, rdi
0x180029b49  mov     rdx, rbp
0x180029b4c  mov     rcx, r14
0x180029b4f  call    winreIsImageStaged
0x180029b54  test    eax, eax
0x180029b56  jnz     short loc_180029B75
0x180029b58  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r12d; _ReAgentErrorCodes ReAgentError
0x180029b5f  jnz     short loc_180029B6B
0x180029b61  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0Eh; _ReAgentErrorCodes ReAgentError
0x180029b6b  mov     ebx, 64Eh
0x180029b70  jmp     loc_180029BFD
0x180029b75  mov     rcx, rdi
0x180029b78  call    winreAddTrailingBackslash
0x180029b7d  mov     ebx, eax
0x180029b7f  test    eax, eax
0x180029b81  jz      short loc_180029B97
0x180029b83  mov     [rsp+88h+var_60], 72Dh
0x180029b8b  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x180029b92  jmp     loc_180029A99
0x180029b97  lea     r8, aWinreWim; "Winre.wim"
0x180029b9e  mov     rdx, r13; unsigned __int64
0x180029ba1  mov     rcx, rdi; unsigned __int16 *
0x180029ba4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029ba9  mov     esi, eax
0x180029bab  test    eax, eax
0x180029bad  jns     short loc_180029BE3
0x180029baf  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180029bb6  mov     [rsp+88h+var_60], 72Eh
0x180029bbe  mov     r9d, esi
0x180029bc1  mov     [rsp+88h+var_68], rax
0x180029bc6  lea     r8, aFailedToConcat_3; "failed to concatenate winre.wim file na"...
0x180029bcd  mov     ecx, 2
0x180029bd2  lea     rdx, aWinregetwimatt; "winreGetWIMAttr %s (0x%x) in file %S li"...
0x180029bd9  call    UnattendLogW
0x180029bde  movzx   ebx, si
0x180029be1  jmp     short loc_180029BFD
0x180029be3  mov     r8, r15; lpFileInformation
0x180029be6  xor     edx, edx; fInfoLevelId
0x180029be8  mov     rcx, rdi; lpFileName
0x180029beb  call    cs:__imp_GetFileAttributesExW
0x180029bf1  test    eax, eax
0x180029bf3  jnz     short loc_180029BFD
0x180029bf5  call    cs:__imp_GetLastError
0x180029bfb  mov     ebx, eax
0x180029bfd  test    rdi, rdi
0x180029c00  jz      short loc_180029C0B
0x180029c02  mov     rcx, rdi; pv
0x180029c05  call    cs:__imp_CoTaskMemFree
0x180029c0b  mov     eax, ebx
0x180029c0d  add     rsp, 48h
0x180029c11  pop     r15
0x180029c13  pop     r14
0x180029c15  pop     r13
0x180029c17  pop     r12
0x180029c19  pop     rdi
0x180029c1a  pop     rsi
0x180029c1b  pop     rbp
0x180029c1c  pop     rbx
0x180029c1d  retn
```
