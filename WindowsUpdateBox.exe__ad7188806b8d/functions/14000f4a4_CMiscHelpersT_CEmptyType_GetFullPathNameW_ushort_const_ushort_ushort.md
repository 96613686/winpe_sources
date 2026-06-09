# CMiscHelpersT<CEmptyType>::GetFullPathNameW(ushort const *,ushort * *,ushort * *)

- ea: `0x14000f4a4`
- end: `0x14000f676`
- name: `?GetFullPathNameW@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG1@Z`
- size: `466`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPWSTR *, WCHAR **)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140013894`
- `0x140016260`
- `0x14001cfa4`
- `0x140040e70`
- `0x14004f250`
- `0x14004f660`

## callees

- `0x140002a98`
- `0x1400076c8`
- `0x140009f00`
- `0x14000f4a4`
- `0x1400135b8`
- `0x14001d37c`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000f63f`
- `KERNEL32!HeapFree` at `0x14000f63f`
- `KERNEL32!GetProcessHeap` at `0x14000f62a`
- `KERNEL32!GetProcessHeap` at `0x14000f62a`
- `KERNEL32!GetLastError` at `0x14000f5e7`
- `KERNEL32!GetLastError` at `0x14000f5e7`
- `KERNEL32!GetFullPathNameW` at `0x14000f4f5`
- `KERNEL32!GetFullPathNameW` at `0x14000f5d5`
- `KERNEL32!GetFullPathNameW` at `0x14000f4f5`
- `KERNEL32!GetFullPathNameW` at `0x14000f5d5`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::GetFullPathNameW(LPCWSTR lpFileName, LPWSTR *a2, WCHAR **a3)
{
  LPWSTR v5; // rbx
  DWORD FullPathNameW; // eax
  DWORD v8; // esi
  int StringCch; // eax
  unsigned int v10; // edi
  WCHAR *v11; // rcx
  int v12; // eax
  DWORD v13; // ecx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR FilePart; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  v5 = 0;
  lpBuffer = 0;
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, Buffer, &FilePart);
  v8 = FullPathNameW;
  if ( !FullPathNameW )
    goto LABEL_16;
  if ( FullPathNameW <= 0x104 )
  {
    LODWORD(lpBuffer) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &lpBuffer, 0x7FFFFFFF);
    v10 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer),
          v10 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
    if ( (v10 & 0x80000000) == 0 )
    {
      v11 = FilePart;
      if ( FilePart )
      {
        v11 = &(*a2)[FilePart - Buffer];
        FilePart = v11;
      }
      goto LABEL_21;
    }
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_23;
  }
  v12 = STRAPI_CreateCchBufferN(0, FullPathNameW, &lpBuffer);
  v10 = v12;
  if ( v12 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
    v5 = lpBuffer;
    goto LABEL_23;
  }
  v5 = lpBuffer;
  v13 = GetFullPathNameW(lpFileName, v8, lpBuffer, &FilePart);
  if ( !v13 )
  {
LABEL_16:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v10 = -2147467259;
    }
    goto LABEL_12;
  }
  if ( v13 != v8 - 1 )
  {
    v10 = -2147024774;
    goto LABEL_12;
  }
  v11 = FilePart;
  *a2 = v5;
  v5 = 0;
LABEL_21:
  if ( a3 )
    *a3 = v11;
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v10;
}

```

## disassembly

```asm
0x14000f4a4  push    rbp
0x14000f4a6  push    rbx
0x14000f4a7  push    rsi
0x14000f4a8  push    rdi
0x14000f4a9  push    r12
0x14000f4ab  push    r14
0x14000f4ad  push    r15
0x14000f4af  lea     rbp, [rsp-150h]
0x14000f4b7  sub     rsp, 250h
0x14000f4be  mov     rax, cs:__security_cookie
0x14000f4c5  xor     rax, rsp
0x14000f4c8  mov     [rbp+180h+var_40], rax
0x14000f4cf  mov     r15, r8
0x14000f4d2  lea     r9, [rsp+280h+FilePart]; lpFilePart
0x14000f4d7  mov     r14, rdx
0x14000f4da  lea     r8, [rsp+280h+Buffer]; lpBuffer
0x14000f4df  xor     ebx, ebx
0x14000f4e1  mov     edi, 104h
0x14000f4e6  mov     edx, edi; nBufferLength
0x14000f4e8  mov     [rsp+280h+lpBuffer], rbx
0x14000f4ed  mov     r12, rcx
0x14000f4f0  mov     [rsp+280h+FilePart], rbx
0x14000f4f5  call    cs:__imp_GetFullPathNameW
0x14000f4fc  nop     dword ptr [rax+rax+00h]
0x14000f501  mov     esi, eax
0x14000f503  test    eax, eax
0x14000f505  jz      loc_14000F5E7
0x14000f50b  cmp     esi, edi
0x14000f50d  ja      loc_14000F5A0
0x14000f513  mov     r8d, 7FFFFFFFh
0x14000f519  mov     dword ptr [rsp+280h+lpBuffer], ebx
0x14000f51d  lea     rdx, [rsp+280h+lpBuffer]
0x14000f522  lea     rcx, [rsp+280h+Buffer]
0x14000f527  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x14000f52c  mov     edi, eax
0x14000f52e  test    eax, eax
0x14000f530  js      short loc_14000F549
0x14000f532  mov     edx, dword ptr [rsp+280h+lpBuffer]
0x14000f536  lea     rcx, [rsp+280h+Buffer]; Src
0x14000f53b  mov     r8, r14
0x14000f53e  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x14000f543  mov     edi, eax
0x14000f545  test    eax, eax
0x14000f547  jns     short loc_14000F550
0x14000f549  mov     ecx, eax
0x14000f54b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000f550  mov     ecx, edi
0x14000f552  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000f557  test    edi, edi
0x14000f559  js      short loc_14000F597
0x14000f55b  mov     rcx, [rsp+280h+FilePart]
0x14000f560  test    rcx, rcx
0x14000f563  jz      loc_14000F616
0x14000f569  lea     rax, [rsp+280h+Buffer]
0x14000f56e  sub     rcx, rax
0x14000f571  mov     rax, [r14]
0x14000f574  sar     rcx, 1
0x14000f577  lea     rcx, [rax+rcx*2]
0x14000f57b  mov     [rsp+280h+FilePart], rcx
0x14000f580  jmp     loc_14000F616
0x14000f585  mov     edi, 80004005h
0x14000f58a  jmp     short loc_14000F597
0x14000f58c  jle     short loc_14000F597
0x14000f58e  movzx   edi, ax
0x14000f591  or      edi, 80070000h
0x14000f597  mov     ecx, edi
0x14000f599  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000f59e  jmp     short loc_14000F61E
0x14000f5a0  mov     rdx, rsi; unsigned __int64
0x14000f5a3  lea     r8, [rsp+280h+lpBuffer]; unsigned __int16 **
0x14000f5a8  xor     ecx, ecx; unsigned __int16
0x14000f5aa  call    ?STRAPI_CreateCchBufferN@@YAJG_KPEAPEAG@Z; STRAPI_CreateCchBufferN(ushort,unsigned __int64,ushort * *)
0x14000f5af  mov     edi, eax
0x14000f5b1  test    eax, eax
0x14000f5b3  jns     short loc_14000F5C3
0x14000f5b5  mov     ecx, eax
0x14000f5b7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000f5bc  mov     rbx, [rsp+280h+lpBuffer]
0x14000f5c1  jmp     short loc_14000F61E
0x14000f5c3  mov     rbx, [rsp+280h+lpBuffer]
0x14000f5c8  lea     r9, [rsp+280h+FilePart]; lpFilePart
0x14000f5cd  mov     r8, rbx; lpBuffer
0x14000f5d0  mov     edx, esi; nBufferLength
0x14000f5d2  mov     rcx, r12; lpFileName
0x14000f5d5  call    cs:__imp_GetFullPathNameW
0x14000f5dc  nop     dword ptr [rax+rax+00h]
0x14000f5e1  mov     ecx, eax
0x14000f5e3  test    eax, eax
0x14000f5e5  jnz     short loc_14000F5FB
0x14000f5e7  call    cs:__imp_GetLastError
0x14000f5ee  nop     dword ptr [rax+rax+00h]
0x14000f5f3  mov     edi, eax
0x14000f5f5  test    eax, eax
0x14000f5f7  jz      short loc_14000F585
0x14000f5f9  jmp     short loc_14000F58C
0x14000f5fb  lea     eax, [rsi-1]
0x14000f5fe  cmp     ecx, eax
0x14000f600  jz      short loc_14000F609
0x14000f602  mov     edi, 8007007Ah
0x14000f607  jmp     short loc_14000F597
0x14000f609  mov     rcx, [rsp+280h+FilePart]
0x14000f60e  mov     rax, rbx
0x14000f611  mov     [r14], rax
0x14000f614  xor     ebx, ebx
0x14000f616  test    r15, r15
0x14000f619  jz      short loc_14000F61E
0x14000f61b  mov     [r15], rcx
0x14000f61e  mov     ecx, edi
0x14000f620  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000f625  test    rbx, rbx
0x14000f628  jz      short loc_14000F652
0x14000f62a  call    cs:__imp_GetProcessHeap
0x14000f631  nop     dword ptr [rax+rax+00h]
0x14000f636  lea     r8, [rbx-4]; lpMem
0x14000f63a  xor     edx, edx; dwFlags
0x14000f63c  mov     rcx, rax; hHeap
0x14000f63f  call    cs:__imp_HeapFree
0x14000f646  nop     dword ptr [rax+rax+00h]
0x14000f64b  xor     ecx, ecx
0x14000f64d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000f652  mov     eax, edi
0x14000f654  mov     rcx, [rbp+180h+var_40]
0x14000f65b  xor     rcx, rsp; StackCookie
0x14000f65e  call    __security_check_cookie
0x14000f663  add     rsp, 250h
0x14000f66a  pop     r15
0x14000f66c  pop     r14
0x14000f66e  pop     r12
0x14000f670  pop     rdi
0x14000f671  pop     rsi
0x14000f672  pop     rbx
0x14000f673  pop     rbp
0x14000f674  retn
```
