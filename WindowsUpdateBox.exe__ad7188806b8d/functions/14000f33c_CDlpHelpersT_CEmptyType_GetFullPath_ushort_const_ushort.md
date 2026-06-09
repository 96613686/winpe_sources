# CDlpHelpersT<CEmptyType>::GetFullPath(ushort const *,ushort * *)

- ea: `0x14000f33c`
- end: `0x14000f49e`
- name: `?GetFullPath@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z`
- size: `354`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000c9d8`

## callees

- `0x140002116`
- `0x140002a98`
- `0x1400076c8`
- `0x140009f00`
- `0x14000f33c`
- `0x1400135b8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000f463`
- `KERNEL32!HeapFree` at `0x14000f463`
- `KERNEL32!GetProcessHeap` at `0x14000f44e`
- `KERNEL32!GetProcessHeap` at `0x14000f44e`
- `KERNEL32!GetLastError` at `0x14000f3ba`
- `KERNEL32!GetLastError` at `0x14000f3ba`
- `KERNEL32!GetFullPathNameW` at `0x14000f3aa`
- `KERNEL32!GetFullPathNameW` at `0x14000f3aa`

## pseudocode

```c
__int64 __fastcall CDlpHelpersT<CEmptyType>::GetFullPath(LPCWSTR lpFileName, _QWORD *a2)
{
  __int64 v2; // rbx
  __int64 v5; // rcx
  unsigned int v6; // edi
  signed int LastError; // eax
  int StringCch; // eax
  int Internal; // eax
  __int64 v10; // rax
  HANDLE ProcessHeap; // rax
  int v13; // [rsp+20h] [rbp-848h] BYREF
  __int64 v14; // [rsp+28h] [rbp-840h]
  WCHAR Buffer[1040]; // [rsp+30h] [rbp-838h] BYREF

  v2 = 0;
  v14 = 0;
  if ( !lpFileName || !a2 )
  {
    v5 = 2147942487LL;
    v6 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_18;
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !GetFullPathNameW(lpFileName, 0x410u, Buffer, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
LABEL_10:
    v5 = v6;
    goto LABEL_3;
  }
  v13 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v13, 0x7FFFFFFF);
  v6 = StringCch;
  if ( StringCch >= 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer);
    v6 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v2 = v14;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_10;
  v10 = v2;
  v2 = 0;
  *a2 = v10;
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v2 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v6;
}

```

## disassembly

```asm
0x14000f33c  mov     [rsp+arg_10], rbx
0x14000f341  mov     [rsp+arg_18], rsi
0x14000f346  push    rdi
0x14000f347  sub     rsp, 860h
0x14000f34e  mov     rax, cs:__security_cookie
0x14000f355  xor     rax, rsp
0x14000f358  mov     [rsp+868h+var_18], rax
0x14000f360  xor     ebx, ebx
0x14000f362  mov     rsi, rdx
0x14000f365  mov     [rsp+868h+var_840], rbx
0x14000f36a  mov     rdi, rcx
0x14000f36d  test    rcx, rcx
0x14000f370  jnz     short loc_14000F383
0x14000f372  mov     ecx, 80070057h
0x14000f377  mov     edi, ecx
0x14000f379  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000f37e  jmp     loc_14000F442
0x14000f383  test    rsi, rsi
0x14000f386  jz      short loc_14000F372
0x14000f388  xor     edx, edx; Val
0x14000f38a  lea     rcx, [rsp+868h+Buffer]; void *
0x14000f38f  mov     r8d, 820h; Size
0x14000f395  call    memset_0
0x14000f39a  xor     r9d, r9d; lpFilePart
0x14000f39d  lea     r8, [rsp+868h+Buffer]; lpBuffer
0x14000f3a2  mov     edx, 410h; nBufferLength
0x14000f3a7  mov     rcx, rdi; lpFileName
0x14000f3aa  call    cs:__imp_GetFullPathNameW
0x14000f3b1  nop     dword ptr [rax+rax+00h]
0x14000f3b6  test    eax, eax
0x14000f3b8  jnz     short loc_14000F3E2
0x14000f3ba  call    cs:__imp_GetLastError
0x14000f3c1  nop     dword ptr [rax+rax+00h]
0x14000f3c6  mov     edi, eax
0x14000f3c8  test    eax, eax
0x14000f3ca  jnz     short loc_14000F3D3
0x14000f3cc  mov     edi, 80004005h
0x14000f3d1  jmp     short loc_14000F3DE
0x14000f3d3  jle     short loc_14000F3DE
0x14000f3d5  movzx   edi, ax
0x14000f3d8  or      edi, 80070000h
0x14000f3de  mov     ecx, edi
0x14000f3e0  jmp     short loc_14000F379
0x14000f3e2  mov     r8d, 7FFFFFFFh
0x14000f3e8  mov     [rsp+868h+var_848], ebx
0x14000f3ec  lea     rdx, [rsp+868h+var_848]
0x14000f3f1  lea     rcx, [rsp+868h+Buffer]
0x14000f3f6  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x14000f3fb  mov     edi, eax
0x14000f3fd  test    eax, eax
0x14000f3ff  jns     short loc_14000F40A
0x14000f401  mov     ecx, eax
0x14000f403  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000f408  jmp     short loc_14000F42F
0x14000f40a  mov     edx, [rsp+868h+var_848]
0x14000f40e  lea     r8, [rsp+868h+var_840]
0x14000f413  lea     rcx, [rsp+868h+Buffer]; Src
0x14000f418  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x14000f41d  mov     edi, eax
0x14000f41f  test    eax, eax
0x14000f421  jns     short loc_14000F42A
0x14000f423  mov     ecx, eax
0x14000f425  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000f42a  mov     rbx, [rsp+868h+var_840]
0x14000f42f  mov     ecx, edi
0x14000f431  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000f436  test    edi, edi
0x14000f438  js      short loc_14000F3DE
0x14000f43a  mov     rax, rbx
0x14000f43d  xor     ebx, ebx
0x14000f43f  mov     [rsi], rax
0x14000f442  mov     ecx, edi
0x14000f444  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000f449  test    rbx, rbx
0x14000f44c  jz      short loc_14000F476
0x14000f44e  call    cs:__imp_GetProcessHeap
0x14000f455  nop     dword ptr [rax+rax+00h]
0x14000f45a  lea     r8, [rbx-4]; lpMem
0x14000f45e  xor     edx, edx; dwFlags
0x14000f460  mov     rcx, rax; hHeap
0x14000f463  call    cs:__imp_HeapFree
0x14000f46a  nop     dword ptr [rax+rax+00h]
0x14000f46f  xor     ecx, ecx
0x14000f471  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000f476  mov     eax, edi
0x14000f478  mov     rcx, [rsp+868h+var_18]
0x14000f480  xor     rcx, rsp; StackCookie
0x14000f483  call    __security_check_cookie
0x14000f488  lea     r11, [rsp+868h+var_8]
0x14000f490  mov     rbx, [r11+20h]
0x14000f494  mov     rsi, [r11+28h]
0x14000f498  mov     rsp, r11
0x14000f49b  pop     rdi
0x14000f49c  retn
```
