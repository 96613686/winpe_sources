# Wallet::ServerUtils::GetWalletAppDataParentPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18001d114`
- end: `0x18001d29a`
- name: `?GetWalletAppDataParentPath@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018bd0`

## callees

- `0x18000acac`
- `0x18001400c`
- `0x18001c638`
- `0x18001d114`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d180`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d180`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d197`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d268`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d268`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001d170`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001d170`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001d19f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001d19f`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d1e6`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d205`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d1e6`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d205`

## pseudocode

```c
__int64 __fastcall Wallet::ServerUtils::GetWalletAppDataParentPath(__int64 a1)
{
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  BOOL v4; // ebx
  signed int LastError; // eax
  int v6; // eax
  __int64 v7; // r8
  void *TokenHandle; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 v11[264]; // [rsp+30h] [rbp-D0h] BYREF

  ppszPath = 0;
  TokenHandle = 0;
  if ( g_fUnitTestContext )
  {
    v2 = (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            a1,
                            &sourceString) == 0
       ? 0x8007000E
       : 0;
  }
  else
  {
    v2 = CoImpersonateClient();
    if ( v2 >= 0 )
    {
      CurrentThread = GetCurrentThread();
      v4 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
      CoRevertToSelf();
      if ( v4 )
      {
        v2 = SHGetKnownFolderPath(&FOLDERID_Documents, 0, TokenHandle, &ppszPath);
        if ( v2 >= 0 || (v2 = SHGetKnownFolderPath(&FOLDERID_PublicDocuments, 0, TokenHandle, &ppszPath), v2 >= 0) )
        {
          v6 = StringCchPrintfW(v11, 0x104u, L"%s", ppszPath, TokenHandle);
          if ( v6 >= 0 )
          {
            v7 = -1;
            do
              ++v7;
            while ( v11[v7] );
            if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                     a1,
                                     v11) )
              v2 = -2147024882;
          }
          else
          {
            v2 = v6;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v2 = -2143748092;
        }
      }
    }
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  tlx::unique_any<tlx::handle_traits<unsigned char *,void (*)(void *),&void CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<unsigned char *,void (*)(void *),&void CoTaskMemFree(void *),0>>(&ppszPath);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001d114  push    rbp
0x18001d116  push    rbx
0x18001d117  push    rsi
0x18001d118  push    rdi
0x18001d119  lea     rbp, [rsp-158h]
0x18001d121  sub     rsp, 258h
0x18001d128  mov     rax, cs:__security_cookie
0x18001d12f  xor     rax, rsp
0x18001d132  mov     [rbp+170h+var_30], rax
0x18001d139  xor     esi, esi
0x18001d13b  mov     rdi, rcx
0x18001d13e  cmp     cs:?g_fUnitTestContext@@3HA, esi; int g_fUnitTestContext
0x18001d144  mov     [rsp+270h+ppszPath], rsi
0x18001d149  mov     [rsp+270h+TokenHandle], rsi
0x18001d14e  jz      short loc_18001D170
0x18001d150  xor     r8d, r8d
0x18001d153  lea     rdx, sourceString
0x18001d15a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001d15f  neg     al
0x18001d161  sbb     ebx, ebx
0x18001d163  not     ebx
0x18001d165  and     ebx, 8007000Eh
0x18001d16b  jmp     loc_18001D25E
0x18001d170  call    cs:__imp_CoImpersonateClient
0x18001d176  mov     ebx, eax
0x18001d178  test    eax, eax
0x18001d17a  js      loc_18001D25E
0x18001d180  call    cs:__imp_GetCurrentThread
0x18001d186  mov     edx, 0Ch; DesiredAccess
0x18001d18b  lea     r9, [rsp+270h+TokenHandle]; TokenHandle
0x18001d190  mov     rcx, rax; ThreadHandle
0x18001d193  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001d197  call    cs:__imp_OpenThreadToken
0x18001d19d  mov     ebx, eax
0x18001d19f  call    cs:__imp_CoRevertToSelf
0x18001d1a5  test    ebx, ebx
0x18001d1a7  jnz     short loc_18001D1D3
0x18001d1a9  call    cs:__imp_GetLastError
0x18001d1af  mov     ebx, eax
0x18001d1b1  test    eax, eax
0x18001d1b3  jz      short loc_18001D1C9
0x18001d1b5  jle     loc_18001D25E
0x18001d1bb  movzx   ebx, ax
0x18001d1be  or      ebx, 80070000h
0x18001d1c4  jmp     loc_18001D25E
0x18001d1c9  mov     ebx, 80390004h
0x18001d1ce  jmp     loc_18001D25E
0x18001d1d3  mov     r8, [rsp+270h+TokenHandle]; hToken
0x18001d1d8  lea     r9, [rsp+270h+ppszPath]; ppszPath
0x18001d1dd  xor     edx, edx; dwFlags
0x18001d1df  lea     rcx, FOLDERID_Documents; rfid
0x18001d1e6  call    cs:__imp_SHGetKnownFolderPath
0x18001d1ec  mov     ebx, eax
0x18001d1ee  test    eax, eax
0x18001d1f0  jns     short loc_18001D211
0x18001d1f2  mov     r8, [rsp+270h+TokenHandle]; hToken
0x18001d1f7  lea     r9, [rsp+270h+ppszPath]; ppszPath
0x18001d1fc  xor     edx, edx; dwFlags
0x18001d1fe  lea     rcx, FOLDERID_PublicDocuments; rfid
0x18001d205  call    cs:__imp_SHGetKnownFolderPath
0x18001d20b  mov     ebx, eax
0x18001d20d  test    eax, eax
0x18001d20f  js      short loc_18001D25E
0x18001d211  mov     r9, [rsp+270h+ppszPath]
0x18001d216  lea     r8, aS_0; "%s"
0x18001d21d  mov     edx, 104h; unsigned __int64
0x18001d222  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18001d227  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d22c  test    eax, eax
0x18001d22e  jns     short loc_18001D234
0x18001d230  mov     ebx, eax
0x18001d232  jmp     short loc_18001D25E
0x18001d234  lea     rax, [rsp+270h+var_240]
0x18001d239  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d23d  inc     r8
0x18001d240  cmp     [rax+r8*2], si
0x18001d245  jnz     short loc_18001D23D
0x18001d247  lea     rdx, [rsp+270h+var_240]
0x18001d24c  mov     rcx, rdi
0x18001d24f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001d254  test    al, al
0x18001d256  mov     ecx, 8007000Eh
0x18001d25b  cmovz   ebx, ecx
0x18001d25e  mov     rcx, [rsp+270h+TokenHandle]; hObject
0x18001d263  test    rcx, rcx
0x18001d266  jz      short loc_18001D273
0x18001d268  call    cs:__imp_CloseHandle
0x18001d26e  mov     [rsp+270h+TokenHandle], rsi
0x18001d273  lea     rcx, [rsp+270h+ppszPath]
0x18001d278  call    ??1?$unique_any@U?$handle_traits@PEAEP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>(void)
0x18001d27d  mov     eax, ebx
0x18001d27f  mov     rcx, [rbp+170h+var_30]
0x18001d286  xor     rcx, rsp; StackCookie
0x18001d289  call    __security_check_cookie
0x18001d28e  add     rsp, 258h
0x18001d295  pop     rdi
0x18001d296  pop     rsi
0x18001d297  pop     rbx
0x18001d298  pop     rbp
0x18001d299  retn
```
