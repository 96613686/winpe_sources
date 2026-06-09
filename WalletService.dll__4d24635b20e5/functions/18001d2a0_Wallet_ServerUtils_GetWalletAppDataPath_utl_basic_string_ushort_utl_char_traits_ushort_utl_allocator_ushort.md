# Wallet::ServerUtils::GetWalletAppDataPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18001d2a0`
- end: `0x18001d432`
- name: `?GetWalletAppDataPath@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018bd0`
- `0x18001d438`

## callees

- `0x18000acac`
- `0x18001400c`
- `0x18001c638`
- `0x18001d2a0`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d30c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d30c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d323`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d400`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001d2fc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001d2fc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001d32b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001d32b`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d372`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d391`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d372`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d391`

## pseudocode

```c
__int64 __fastcall Wallet::ServerUtils::GetWalletAppDataPath(__int64 a1)
{
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  BOOL v4; // ebx
  signed int LastError; // eax
  int v6; // eax
  __int64 v7; // r8
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v11[264]; // [rsp+40h] [rbp-C0h] BYREF

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
          v6 = StringCchPrintfW(v11, 0x104u, L"%s\\%s\\", ppszPath, L"Wallet");
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
0x18001d2a0  push    rbp
0x18001d2a2  push    rbx
0x18001d2a3  push    rsi
0x18001d2a4  push    rdi
0x18001d2a5  lea     rbp, [rsp-168h]
0x18001d2ad  sub     rsp, 268h
0x18001d2b4  mov     rax, cs:__security_cookie
0x18001d2bb  xor     rax, rsp
0x18001d2be  mov     [rbp+180h+var_30], rax
0x18001d2c5  xor     esi, esi
0x18001d2c7  mov     rdi, rcx
0x18001d2ca  cmp     cs:?g_fUnitTestContext@@3HA, esi; int g_fUnitTestContext
0x18001d2d0  mov     [rsp+280h+ppszPath], rsi
0x18001d2d5  mov     [rsp+280h+TokenHandle], rsi
0x18001d2da  jz      short loc_18001D2FC
0x18001d2dc  xor     r8d, r8d
0x18001d2df  lea     rdx, sourceString
0x18001d2e6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001d2eb  neg     al
0x18001d2ed  sbb     ebx, ebx
0x18001d2ef  not     ebx
0x18001d2f1  and     ebx, 8007000Eh
0x18001d2f7  jmp     loc_18001D3F6
0x18001d2fc  call    cs:__imp_CoImpersonateClient
0x18001d302  mov     ebx, eax
0x18001d304  test    eax, eax
0x18001d306  js      loc_18001D3F6
0x18001d30c  call    cs:__imp_GetCurrentThread
0x18001d312  mov     edx, 0Ch; DesiredAccess
0x18001d317  lea     r9, [rsp+280h+TokenHandle]; TokenHandle
0x18001d31c  mov     rcx, rax; ThreadHandle
0x18001d31f  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001d323  call    cs:__imp_OpenThreadToken
0x18001d329  mov     ebx, eax
0x18001d32b  call    cs:__imp_CoRevertToSelf
0x18001d331  test    ebx, ebx
0x18001d333  jnz     short loc_18001D35F
0x18001d335  call    cs:__imp_GetLastError
0x18001d33b  mov     ebx, eax
0x18001d33d  test    eax, eax
0x18001d33f  jz      short loc_18001D355
0x18001d341  jle     loc_18001D3F6
0x18001d347  movzx   ebx, ax
0x18001d34a  or      ebx, 80070000h
0x18001d350  jmp     loc_18001D3F6
0x18001d355  mov     ebx, 80390004h
0x18001d35a  jmp     loc_18001D3F6
0x18001d35f  mov     r8, [rsp+280h+TokenHandle]; hToken
0x18001d364  lea     r9, [rsp+280h+ppszPath]; ppszPath
0x18001d369  xor     edx, edx; dwFlags
0x18001d36b  lea     rcx, FOLDERID_Documents; rfid
0x18001d372  call    cs:__imp_SHGetKnownFolderPath
0x18001d378  mov     ebx, eax
0x18001d37a  test    eax, eax
0x18001d37c  jns     short loc_18001D39D
0x18001d37e  mov     r8, [rsp+280h+TokenHandle]; hToken
0x18001d383  lea     r9, [rsp+280h+ppszPath]; ppszPath
0x18001d388  xor     edx, edx; dwFlags
0x18001d38a  lea     rcx, FOLDERID_PublicDocuments; rfid
0x18001d391  call    cs:__imp_SHGetKnownFolderPath
0x18001d397  mov     ebx, eax
0x18001d399  test    eax, eax
0x18001d39b  js      short loc_18001D3F6
0x18001d39d  mov     r9, [rsp+280h+ppszPath]
0x18001d3a2  lea     rax, aWallet_0; "Wallet"
0x18001d3a9  lea     r8, aSS; "%s\\%s\\"
0x18001d3b0  mov     [rsp+280h+var_260], rax
0x18001d3b5  mov     edx, 104h; unsigned __int64
0x18001d3ba  lea     rcx, [rsp+280h+var_240]; unsigned __int16 *
0x18001d3bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d3c4  test    eax, eax
0x18001d3c6  jns     short loc_18001D3CC
0x18001d3c8  mov     ebx, eax
0x18001d3ca  jmp     short loc_18001D3F6
0x18001d3cc  lea     rax, [rsp+280h+var_240]
0x18001d3d1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d3d5  inc     r8
0x18001d3d8  cmp     [rax+r8*2], si
0x18001d3dd  jnz     short loc_18001D3D5
0x18001d3df  lea     rdx, [rsp+280h+var_240]
0x18001d3e4  mov     rcx, rdi
0x18001d3e7  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001d3ec  test    al, al
0x18001d3ee  mov     ecx, 8007000Eh
0x18001d3f3  cmovz   ebx, ecx
0x18001d3f6  mov     rcx, [rsp+280h+TokenHandle]; hObject
0x18001d3fb  test    rcx, rcx
0x18001d3fe  jz      short loc_18001D40B
0x18001d400  call    cs:__imp_CloseHandle
0x18001d406  mov     [rsp+280h+TokenHandle], rsi
0x18001d40b  lea     rcx, [rsp+280h+ppszPath]
0x18001d410  call    ??1?$unique_any@U?$handle_traits@PEAEP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>(void)
0x18001d415  mov     eax, ebx
0x18001d417  mov     rcx, [rbp+180h+var_30]
0x18001d41e  xor     rcx, rsp; StackCookie
0x18001d421  call    __security_check_cookie
0x18001d426  add     rsp, 268h
0x18001d42d  pop     rdi
0x18001d42e  pop     rsi
0x18001d42f  pop     rbx
0x18001d430  pop     rbp
0x18001d431  retn
```
