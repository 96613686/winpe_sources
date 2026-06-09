# CEtwLogHelper::CreateDecodedEtlFile(ushort const *)

- ea: `0x180014270`
- end: `0x1800143b2`
- name: `?CreateDecodedEtlFile@CEtwLogHelper@@SAJPEBG@Z`
- size: `322`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800148f0`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180006498`
- `0x180014270`
- `0x18001ae3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001432d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001432d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001431d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001431d`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::CreateDecodedEtlFile(const unsigned __int16 *a1, __int64 a2, int a3, int a4)
{
  signed int v4; // ebx
  signed int LastError; // eax
  LPCWSTR v6; // rcx
  int v8; // [rsp+40h] [rbp-C0h] BYREF
  signed int v9[3]; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR lpNewFileName; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR v11[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ExistingFileName[1032]; // [rsp+70h] [rbp-90h] BYREF

  lpNewFileName = a1;
  v8 = 0;
  if ( a1 )
  {
    v4 = StringCchPrintfW(ExistingFileName, 0x401u, L"%s.merged", a1);
    if ( v4 >= 0 )
    {
      v4 = MergeEtlExWithErrorContext(
             1,
             (unsigned int)&lpNewFileName,
             (unsigned int)ExistingFileName,
             0xFFFFF,
             0,
             (__int64)&v8);
      if ( v4 >= 0 && !MoveFileExW(ExistingFileName, lpNewFileName, 1u) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v6 = &String2;
    v9[0] = v4;
    if ( lpNewFileName )
      v6 = lpNewFileName;
    v11[0] = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v6,
      (unsigned int)byte_1800420AD,
      a3,
      a4,
      (__int64)v11,
      (__int64)v9);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014270  mov     [rsp-8+arg_8], rbx
0x180014275  push    rbp
0x180014276  lea     rbp, [rsp-790h]
0x18001427e  sub     rsp, 890h
0x180014285  mov     rax, cs:__security_cookie
0x18001428c  xor     rax, rsp
0x18001428f  mov     [rbp+790h+var_10], rax
0x180014296  mov     [rsp+890h+lpNewFileName], rcx
0x18001429b  mov     [rsp+890h+var_850], 0
0x1800142a3  test    rcx, rcx
0x1800142a6  jnz     short loc_1800142B2
0x1800142a8  mov     ebx, 80070057h
0x1800142ad  jmp     loc_180014348
0x1800142b2  mov     r9, rcx
0x1800142b5  lea     r8, aSMerged; "%s.merged"
0x1800142bc  lea     rcx, [rsp+890h+ExistingFileName]; unsigned __int16 *
0x1800142c1  mov     edx, 401h; unsigned __int64
0x1800142c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800142cb  mov     ebx, eax
0x1800142cd  test    eax, eax
0x1800142cf  js      short loc_180014348
0x1800142d1  lea     rax, [rsp+890h+var_850]
0x1800142d6  mov     [rsp+890h+var_860], 0
0x1800142df  mov     [rsp+890h+var_868], rax
0x1800142e4  lea     r8, [rsp+890h+ExistingFileName]
0x1800142e9  mov     r9d, 0FFFFFh
0x1800142ef  mov     [rsp+890h+var_870], 0
0x1800142f8  lea     rdx, [rsp+890h+lpNewFileName]
0x1800142fd  mov     ecx, 1
0x180014302  call    MergeEtlExWithErrorContext
0x180014307  mov     ebx, eax
0x180014309  test    eax, eax
0x18001430b  js      short loc_180014348
0x18001430d  mov     rdx, [rsp+890h+lpNewFileName]; lpNewFileName
0x180014312  lea     rcx, [rsp+890h+ExistingFileName]; lpExistingFileName
0x180014317  mov     r8d, 1; dwFlags
0x18001431d  call    cs:__imp_MoveFileExW
0x180014324  nop     dword ptr [rax+rax+00h]
0x180014329  test    eax, eax
0x18001432b  jnz     short loc_180014348
0x18001432d  call    cs:__imp_GetLastError
0x180014334  nop     dword ptr [rax+rax+00h]
0x180014339  mov     ebx, eax
0x18001433b  test    eax, eax
0x18001433d  jle     short loc_180014348
0x18001433f  movzx   ebx, ax
0x180014342  or      ebx, 80070000h
0x180014348  mov     eax, cs:dword_18004AE90
0x18001434e  cmp     eax, 5
0x180014351  jbe     short loc_18001438F
0x180014353  mov     rax, [rsp+890h+lpNewFileName]
0x180014358  lea     rcx, String2
0x18001435f  test    rax, rax
0x180014362  mov     [rsp+890h+var_84C], ebx
0x180014366  lea     rdx, byte_1800420AD
0x18001436d  cmovnz  rcx, rax
0x180014371  lea     rax, [rsp+890h+var_84C]
0x180014376  mov     [rsp+890h+var_868], rax
0x18001437b  lea     rax, [rsp+890h+var_830]
0x180014380  mov     [rsp+890h+var_870], rax
0x180014385  mov     [rsp+890h+var_830], rcx
0x18001438a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001438f  mov     eax, ebx
0x180014391  mov     rcx, [rbp+790h+var_10]
0x180014398  xor     rcx, rsp; StackCookie
0x18001439b  call    __security_check_cookie
0x1800143a0  mov     rbx, [rsp+890h+arg_8]
0x1800143a8  add     rsp, 890h
0x1800143af  pop     rbp
0x1800143b0  retn
```
