# CEtwLogHelper::CreateDecodedEtlFile(ushort const *)

- ea: `0x180013820`
- end: `0x180013955`
- name: `?CreateDecodedEtlFile@CEtwLogHelper@@SAJPEBG@Z`
- size: `309`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180013e4c`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180006518`
- `0x180013820`
- `0x180019f58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138d7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800138cd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800138cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEtwLogHelper::CreateDecodedEtlFile(const unsigned __int16 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  signed int v4; // ebx
  signed int LastError; // eax
  const WCHAR *v6; // rcx
  int v8; // [rsp+40h] [rbp-C0h] BYREF
  signed int v9[3]; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR lpNewFileName; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v11; // [rsp+60h] [rbp-A0h] BYREF
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v6 = &String2;
    v9[0] = v4;
    if ( lpNewFileName )
      v6 = lpNewFileName;
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v6,
      (__int64)byte_1800400AD,
      a3,
      a4,
      &v11,
      (__int64)v9);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013820  mov     [rsp-8+arg_8], rbx
0x180013825  push    rbp
0x180013826  lea     rbp, [rsp-790h]
0x18001382e  sub     rsp, 890h
0x180013835  mov     rax, cs:__security_cookie
0x18001383c  xor     rax, rsp
0x18001383f  mov     [rbp+790h+var_10], rax
0x180013846  mov     [rsp+890h+lpNewFileName], rcx
0x18001384b  mov     [rsp+890h+var_850], 0
0x180013853  test    rcx, rcx
0x180013856  jnz     short loc_180013862
0x180013858  mov     ebx, 80070057h
0x18001385d  jmp     loc_1800138EC
0x180013862  mov     r9, rcx
0x180013865  lea     r8, aSMerged; "%s.merged"
0x18001386c  lea     rcx, [rsp+890h+ExistingFileName]; unsigned __int16 *
0x180013871  mov     edx, 401h; unsigned __int64
0x180013876  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001387b  mov     ebx, eax
0x18001387d  test    eax, eax
0x18001387f  js      short loc_1800138EC
0x180013881  lea     rax, [rsp+890h+var_850]
0x180013886  mov     [rsp+890h+var_860], 0
0x18001388f  mov     [rsp+890h+var_868], rax
0x180013894  lea     r8, [rsp+890h+ExistingFileName]
0x180013899  mov     r9d, 0FFFFFh
0x18001389f  mov     [rsp+890h+var_870], 0
0x1800138a8  lea     rdx, [rsp+890h+lpNewFileName]
0x1800138ad  mov     ecx, 1
0x1800138b2  call    MergeEtlExWithErrorContext
0x1800138b7  mov     ebx, eax
0x1800138b9  test    eax, eax
0x1800138bb  js      short loc_1800138EC
0x1800138bd  mov     rdx, [rsp+890h+lpNewFileName]; lpNewFileName
0x1800138c2  lea     rcx, [rsp+890h+ExistingFileName]; lpExistingFileName
0x1800138c7  mov     r8d, 1; dwFlags
0x1800138cd  call    cs:__imp_MoveFileExW
0x1800138d3  test    eax, eax
0x1800138d5  jnz     short loc_1800138EC
0x1800138d7  call    cs:__imp_GetLastError
0x1800138dd  mov     ebx, eax
0x1800138df  test    eax, eax
0x1800138e1  jle     short loc_1800138EC
0x1800138e3  movzx   ebx, ax
0x1800138e6  or      ebx, 80070000h
0x1800138ec  mov     eax, cs:dword_180048E90
0x1800138f2  cmp     eax, 5
0x1800138f5  jbe     short loc_180013933
0x1800138f7  mov     rax, [rsp+890h+lpNewFileName]
0x1800138fc  lea     rcx, String2
0x180013903  test    rax, rax
0x180013906  mov     [rsp+890h+var_84C], ebx
0x18001390a  lea     rdx, byte_1800400AD
0x180013911  cmovnz  rcx, rax
0x180013915  lea     rax, [rsp+890h+var_84C]
0x18001391a  mov     [rsp+890h+var_868], rax
0x18001391f  lea     rax, [rsp+890h+var_830]
0x180013924  mov     [rsp+890h+var_870], rax
0x180013929  mov     [rsp+890h+var_830], rcx
0x18001392e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013933  mov     eax, ebx
0x180013935  mov     rcx, [rbp+790h+var_10]
0x18001393c  xor     rcx, rsp; StackCookie
0x18001393f  call    __security_check_cookie
0x180013944  mov     rbx, [rsp+890h+arg_8]
0x18001394c  add     rsp, 890h
0x180013953  pop     rbp
0x180013954  retn
```
