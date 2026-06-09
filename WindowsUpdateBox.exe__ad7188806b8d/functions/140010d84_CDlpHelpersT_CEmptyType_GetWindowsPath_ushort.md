# CDlpHelpersT<CEmptyType>::GetWindowsPath(ushort * *)

- ea: `0x140010d84`
- end: `0x140010eda`
- name: `?GetWindowsPath@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z`
- size: `342`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140007dd4`
- `0x14000c9d8`
- `0x1400136d4`
- `0x140016a58`

## callees

- `0x140002116`
- `0x140002a98`
- `0x1400076c8`
- `0x140009f00`
- `0x140010d84`
- `0x1400135b8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x140010de4`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x140010de4`
- `KERNEL32!HeapFree` at `0x140010e9f`
- `KERNEL32!HeapFree` at `0x140010e9f`
- `KERNEL32!GetProcessHeap` at `0x140010e8a`
- `KERNEL32!GetProcessHeap` at `0x140010e8a`
- `KERNEL32!GetLastError` at `0x140010df4`
- `KERNEL32!GetLastError` at `0x140010df4`

## pseudocode

```c
__int64 __fastcall CDlpHelpersT<CEmptyType>::GetWindowsPath(_QWORD *a1)
{
  __int64 v1; // rbx
  unsigned int v3; // edi
  signed int LastError; // eax
  int StringCch; // eax
  int v6; // eax
  __int64 v7; // rax
  HANDLE ProcessHeap; // rax
  unsigned int v10; // [rsp+20h] [rbp-238h] BYREF
  __int64 v11; // [rsp+28h] [rbp-230h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  v1 = 0;
  v11 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
    goto LABEL_16;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    goto LABEL_3;
  }
  v10 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v10, 0x7FFFFFFF);
  v3 = StringCch;
  if ( StringCch >= 0 )
  {
    v6 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer, v10, &v11);
    v3 = v6;
    if ( v6 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    v1 = v11;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( (v3 & 0x80000000) != 0 )
    goto LABEL_3;
  v7 = v1;
  v1 = 0;
  *a1 = v7;
LABEL_16:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v1 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v3;
}

```

## disassembly

```asm
0x140010d84  mov     [rsp+arg_8], rbx
0x140010d89  mov     [rsp+arg_10], rsi
0x140010d8e  push    rdi
0x140010d8f  sub     rsp, 250h
0x140010d96  mov     rax, cs:__security_cookie
0x140010d9d  xor     rax, rsp
0x140010da0  mov     [rsp+258h+var_18], rax
0x140010da8  xor     ebx, ebx
0x140010daa  mov     rsi, rcx
0x140010dad  mov     [rsp+258h+var_230], rbx
0x140010db2  test    rcx, rcx
0x140010db5  jnz     short loc_140010DC8
0x140010db7  mov     edi, 80070057h
0x140010dbc  mov     ecx, edi
0x140010dbe  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140010dc3  jmp     loc_140010E7E
0x140010dc8  xor     edx, edx; Val
0x140010dca  lea     rcx, [rsp+258h+Buffer]; void *
0x140010dcf  mov     r8d, 208h; Size
0x140010dd5  call    memset_0
0x140010dda  mov     edx, 104h; uSize
0x140010ddf  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x140010de4  call    cs:__imp_GetSystemWindowsDirectoryW
0x140010deb  nop     dword ptr [rax+rax+00h]
0x140010df0  test    eax, eax
0x140010df2  jnz     short loc_140010E1A
0x140010df4  call    cs:__imp_GetLastError
0x140010dfb  nop     dword ptr [rax+rax+00h]
0x140010e00  mov     edi, eax
0x140010e02  test    eax, eax
0x140010e04  jnz     short loc_140010E0D
0x140010e06  mov     edi, 80004005h
0x140010e0b  jmp     short loc_140010DBC
0x140010e0d  jle     short loc_140010DBC
0x140010e0f  movzx   edi, ax
0x140010e12  or      edi, 80070000h
0x140010e18  jmp     short loc_140010DBC
0x140010e1a  mov     r8d, 7FFFFFFFh
0x140010e20  mov     [rsp+258h+var_238], ebx
0x140010e24  lea     rdx, [rsp+258h+var_238]
0x140010e29  lea     rcx, [rsp+258h+Buffer]
0x140010e2e  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x140010e33  mov     edi, eax
0x140010e35  test    eax, eax
0x140010e37  jns     short loc_140010E42
0x140010e39  mov     ecx, eax
0x140010e3b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140010e40  jmp     short loc_140010E67
0x140010e42  mov     edx, [rsp+258h+var_238]
0x140010e46  lea     r8, [rsp+258h+var_230]
0x140010e4b  lea     rcx, [rsp+258h+Buffer]; Src
0x140010e50  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x140010e55  mov     edi, eax
0x140010e57  test    eax, eax
0x140010e59  jns     short loc_140010E62
0x140010e5b  mov     ecx, eax
0x140010e5d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140010e62  mov     rbx, [rsp+258h+var_230]
0x140010e67  mov     ecx, edi
0x140010e69  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140010e6e  test    edi, edi
0x140010e70  js      loc_140010DBC
0x140010e76  mov     rax, rbx
0x140010e79  xor     ebx, ebx
0x140010e7b  mov     [rsi], rax
0x140010e7e  mov     ecx, edi
0x140010e80  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140010e85  test    rbx, rbx
0x140010e88  jz      short loc_140010EB2
0x140010e8a  call    cs:__imp_GetProcessHeap
0x140010e91  nop     dword ptr [rax+rax+00h]
0x140010e96  lea     r8, [rbx-4]; lpMem
0x140010e9a  xor     edx, edx; dwFlags
0x140010e9c  mov     rcx, rax; hHeap
0x140010e9f  call    cs:__imp_HeapFree
0x140010ea6  nop     dword ptr [rax+rax+00h]
0x140010eab  xor     ecx, ecx
0x140010ead  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140010eb2  mov     eax, edi
0x140010eb4  mov     rcx, [rsp+258h+var_18]
0x140010ebc  xor     rcx, rsp; StackCookie
0x140010ebf  call    __security_check_cookie
0x140010ec4  lea     r11, [rsp+258h+var_8]
0x140010ecc  mov     rbx, [r11+18h]
0x140010ed0  mov     rsi, [r11+20h]
0x140010ed4  mov     rsp, r11
0x140010ed7  pop     rdi
0x140010ed8  retn
```
