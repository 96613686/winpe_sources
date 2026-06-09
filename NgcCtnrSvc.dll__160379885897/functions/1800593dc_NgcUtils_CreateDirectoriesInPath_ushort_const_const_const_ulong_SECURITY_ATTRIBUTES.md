# NgcUtils::CreateDirectoriesInPath(ushort const * const * const,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800593dc`
- end: `0x180059503`
- name: `?CreateDirectoriesInPath@NgcUtils@@YAJQEBQEBGKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(NgcUtils *this, const unsigned __int16 *const *const, struct _SECURITY_ATTRIBUTES *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001cac0`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x180018194`
- `0x180020378`
- `0x18002c640`
- `0x1800592e4`
- `0x1800593dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005948a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005948a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180059466`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180059466`

## pseudocode

```c
__int64 __fastcall NgcUtils::CreateDirectoriesInPath(
        NgcUtils *this,
        const unsigned __int16 *const *const a2,
        struct _SECURITY_ATTRIBUTES *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  unsigned int v6; // edi
  const unsigned __int16 *v7; // rdx
  int v8; // ebx
  LPCWSTR *v9; // rcx
  int v10; // eax
  const WCHAR *v11; // rcx
  signed int LastError; // eax
  int v14; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpPathName[3]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v16; // [rsp+50h] [rbp-10h]

  v6 = 1;
  while ( 1 )
  {
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(lpPathName);
    v8 = NgcUtils::ComposePath(this, v6, (__int64)lpPathName);
    if ( v8 < 0 )
      break;
    v9 = lpPathName;
    if ( v16 > 7 )
      v9 = (LPCWSTR *)lpPathName[0];
    v10 = NgcUtils::CheckForDirectory((NgcUtils *)v9, v7);
    v8 = v10;
    if ( v10 < 0 )
    {
      if ( (unsigned int)(v10 + 2147024894) > 1 )
        break;
      v11 = (const WCHAR *)lpPathName;
      if ( v16 > 7 )
        v11 = lpPathName[0];
      if ( !CreateDirectoryW(v11, a3) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          v14 = v8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800BE0B8,
            (unsigned int)byte_1800ADD95,
            0,
            0,
            (__int64)&v14);
        }
        break;
      }
      v8 = 0;
    }
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpPathName);
    if ( ++v6 > 3 )
      return (unsigned int)v8;
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpPathName);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800593dc  mov     [rsp-18h+arg_8], rbx
0x1800593e1  mov     [rsp-18h+arg_18], rsi
0x1800593e6  push    rbp
0x1800593e7  push    rdi
0x1800593e8  push    r14
0x1800593ea  mov     rbp, rsp
0x1800593ed  sub     rsp, 60h
0x1800593f1  mov     rax, cs:__security_cookie
0x1800593f8  xor     rax, rsp
0x1800593fb  mov     [rbp+var_8], rax
0x1800593ff  mov     r14, r8
0x180059402  mov     rsi, rcx
0x180059405  mov     edi, 1
0x18005940a  lea     rcx, [rbp+lpPathName]
0x18005940e  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180059413  nop
0x180059414  lea     r8, [rbp+lpPathName]
0x180059418  mov     edx, edi
0x18005941a  mov     rcx, rsi
0x18005941d  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x180059422  mov     ebx, eax
0x180059424  test    eax, eax
0x180059426  js      loc_1800594D6
0x18005942c  lea     rcx, [rbp+lpPathName]
0x180059430  cmp     [rbp+var_10], 7
0x180059435  cmova   rcx, [rbp+lpPathName]; this
0x18005943a  call    ?CheckForDirectory@NgcUtils@@YAJPEBG@Z; NgcUtils::CheckForDirectory(ushort const *)
0x18005943f  mov     ebx, eax
0x180059441  test    eax, eax
0x180059443  js      short loc_180059447
0x180059445  jmp     short loc_180059478
0x180059447  add     eax, 7FF8FFFEh
0x18005944c  cmp     eax, 1
0x18005944f  ja      loc_1800594D6
0x180059455  lea     rcx, [rbp+lpPathName]
0x180059459  cmp     [rbp+var_10], 7
0x18005945e  cmova   rcx, [rbp+lpPathName]; lpPathName
0x180059463  mov     rdx, r14; lpSecurityAttributes
0x180059466  call    cs:__imp_CreateDirectoryW
0x18005946d  nop     dword ptr [rax+rax+00h]
0x180059472  test    eax, eax
0x180059474  jz      short loc_18005948A
0x180059476  xor     ebx, ebx
0x180059478  lea     rcx, [rbp+lpPathName]
0x18005947c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180059481  inc     edi
0x180059483  cmp     edi, 3
0x180059486  jbe     short loc_18005940A
0x180059488  jmp     short loc_1800594DF
0x18005948a  call    cs:__imp_GetLastError
0x180059491  nop     dword ptr [rax+rax+00h]
0x180059496  mov     ebx, eax
0x180059498  test    eax, eax
0x18005949a  jle     short loc_1800594A5
0x18005949c  movzx   ebx, ax
0x18005949f  or      ebx, 80070000h
0x1800594a5  mov     eax, cs:dword_1800BE0B8
0x1800594ab  cmp     eax, 2
0x1800594ae  jbe     short loc_1800594D6
0x1800594b0  mov     [rbp+var_30], ebx
0x1800594b3  lea     rax, [rbp+var_30]
0x1800594b7  mov     [rsp+60h+var_40], rax
0x1800594bc  xor     r9d, r9d
0x1800594bf  xor     r8d, r8d
0x1800594c2  lea     rdx, byte_1800ADD95
0x1800594c9  lea     rcx, dword_1800BE0B8
0x1800594d0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800594d5  nop
0x1800594d6  lea     rcx, [rbp+lpPathName]
0x1800594da  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800594df  mov     eax, ebx
0x1800594e1  mov     rcx, [rbp+var_8]
0x1800594e5  xor     rcx, rsp; StackCookie
0x1800594e8  call    __security_check_cookie
0x1800594ed  lea     r11, [rsp+60h+var_s0]
0x1800594f2  mov     rbx, [r11+28h]
0x1800594f6  mov     rsi, [r11+38h]
0x1800594fa  mov     rsp, r11
0x1800594fd  pop     r14
0x1800594ff  pop     rdi
0x180059500  pop     rbp
0x180059501  retn
```
