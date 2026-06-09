# Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(void)

- ea: `0x1800f62d8`
- end: `0x1800f6442`
- name: `?GetStorageDatabaseDirectory@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `362`
- prototype: `void **__fastcall(void **Src, __int64, __int64, const char *)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800eeff4`
- `0x1800f6448`
- `0x1800f6584`
- `0x1800f6a20`

## callees

- `0x1800e4e0a`
- `0x1800e793c`
- `0x1800edb4c`
- `0x1800f5c78`
- `0x1800f610c`
- `0x1800f62d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6405`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800f634a`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800f634a`

## string_xrefs

- `0x1800f63a8`: `\Microsoft\Windows\CapabilityAccessManager`

## pseudocode

```c
void **__fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(
        void **Src,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdx
  HRESULT v6; // eax
  void *v7; // r9
  unsigned __int64 v8; // rdx
  char *v9; // rsi
  __int64 v10; // rbx
  void **v11; // r9
  __int64 v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *Srca; // [rsp+58h] [rbp+10h] BYREF

  if ( !Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::GlobalManager::m_initState )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
      a4);
  Srca = 0;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = (void *)7;
  *(_WORD *)Src = 0;
  v5 = *(_QWORD *)&dwFlags;
  if ( *(_QWORD *)&dwFlags )
  {
    v11 = &Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath;
    if ( Src != &Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath )
    {
      if ( (unsigned __int64)qword_18013FA38 > 7 )
        v11 = (void **)Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath;
      if ( *(_QWORD *)&dwFlags > 7u )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
      }
      else
      {
        Src[2] = *(void **)&dwFlags;
        v12 = 2 * v5;
        memmove_0(Src, v11, 2 * v5);
        *(_WORD *)((char *)Src + v12) = 0;
      }
    }
  }
  else
  {
    Srca = 0;
    v6 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, (PWSTR *)&Srca);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v6,
        1);
    v7 = Srca;
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)Srca + v8) );
    if ( v8 > (unsigned __int64)Src[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
    }
    else
    {
      if ( (unsigned __int64)Src[3] <= 7 )
        v9 = (char *)Src;
      else
        v9 = (char *)*Src;
      Src[2] = (void *)v8;
      v10 = 2 * v8;
      memmove_0(v9, v7, 2 * v8);
      *(_WORD *)&v9[v10] = 0;
    }
    std::wstring::operator+=(Src, L"\\Microsoft\\Windows\\CapabilityAccessManager");
  }
  if ( Srca )
    CoTaskMemFree(Srca);
  return Src;
}

```

## disassembly

```asm
0x1800f62d8  mov     r11, rsp
0x1800f62db  mov     [r11+18h], rbx
0x1800f62df  mov     [r11+8], rcx
0x1800f62e3  push    rbp
0x1800f62e4  push    rsi
0x1800f62e5  push    rdi
0x1800f62e6  sub     rsp, 30h
0x1800f62ea  mov     rdi, rcx
0x1800f62ed  xor     ebp, ebp
0x1800f62ef  mov     [rsp+48h+var_28], ebp
0x1800f62f3  mov     eax, cs:?m_initState@GlobalManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::GlobalManager::m_initState
0x1800f62f9  nop
0x1800f62fa  mov     rcx, [rsp+48h]; this
0x1800f62ff  cmp     eax, 1
0x1800f6302  jb      loc_1800F6430
0x1800f6308  mov     [r11+10h], rbp
0x1800f630c  xorps   xmm0, xmm0
0x1800f630f  movups  xmmword ptr [rdi], xmm0
0x1800f6312  mov     [rdi+10h], rbp
0x1800f6316  lea     ebx, [rbp+7]
0x1800f6319  mov     [rdi+18h], rbx
0x1800f631d  mov     [rdi], bp
0x1800f6320  mov     [rsp+48h+var_28], 1; int
0x1800f6328  mov     rdx, cs:dwFlags; dwFlags
0x1800f632f  test    rdx, rdx
0x1800f6332  jnz     loc_1800F63B9
0x1800f6338  mov     [r11+10h], rbp
0x1800f633c  lea     r9, [r11+10h]; ppszPath
0x1800f6340  xor     r8d, r8d; hToken
0x1800f6343  lea     rcx, FOLDERID_ProgramData; rfid
0x1800f634a  call    cs:__imp_SHGetKnownFolderPath
0x1800f6350  mov     rcx, [rsp+48h]; this
0x1800f6355  test    eax, eax
0x1800f6357  js      loc_1800F641B
0x1800f635d  mov     r9, [rsp+48h+Src]
0x1800f6362  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f6366  inc     rdx
0x1800f6369  cmp     [r9+rdx*2], bp
0x1800f636e  jnz     short loc_1800F6366
0x1800f6370  cmp     rdx, [rdi+18h]
0x1800f6374  ja      short loc_1800F63A0
0x1800f6376  cmp     [rdi+18h], rbx
0x1800f637a  jbe     short loc_1800F6381
0x1800f637c  mov     rsi, [rdi]
0x1800f637f  jmp     short loc_1800F6384
0x1800f6381  mov     rsi, rdi
0x1800f6384  mov     [rdi+10h], rdx
0x1800f6388  lea     rbx, [rdx+rdx]
0x1800f638c  mov     r8, rbx; Size
0x1800f638f  mov     rdx, r9; Src
0x1800f6392  mov     rcx, rsi; void *
0x1800f6395  call    memmove_0
0x1800f639a  mov     [rbx+rsi], bp
0x1800f639e  jmp     short loc_1800F63A8
0x1800f63a0  mov     rcx, rdi
0x1800f63a3  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800f63a8  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\CapabilityAccessM"...
0x1800f63af  mov     rcx, rdi; Src
0x1800f63b2  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1800f63b7  jmp     short loc_1800F63FB
0x1800f63b9  lea     r9, ?m_databaseRedirectedPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath
0x1800f63c0  cmp     rdi, r9
0x1800f63c3  jz      short loc_1800F63FB
0x1800f63c5  cmp     cs:qword_18013FA38, rbx
0x1800f63cc  cmova   r9, cs:?m_databaseRedirectedPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseRedirectedPath
0x1800f63d4  mov     rcx, rdi; void *
0x1800f63d7  cmp     rdx, rbx
0x1800f63da  ja      short loc_1800F63F5
0x1800f63dc  mov     [rdi+10h], rdx
0x1800f63e0  lea     rbx, [rdx+rdx]
0x1800f63e4  mov     r8, rbx; Size
0x1800f63e7  mov     rdx, r9; Src
0x1800f63ea  call    memmove_0
0x1800f63ef  mov     [rbx+rdi], bp
0x1800f63f3  jmp     short loc_1800F63FB
0x1800f63f5  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800f63fa  nop
0x1800f63fb  mov     rcx, [rsp+48h+Src]; pv
0x1800f6400  test    rcx, rcx
0x1800f6403  jz      short loc_1800F640B
0x1800f6405  call    cs:__imp_CoTaskMemFree
0x1800f640b  mov     rax, rdi
0x1800f640e  mov     rbx, [rsp+48h+arg_10]
0x1800f6413  add     rsp, 30h
0x1800f6417  pop     rdi
0x1800f6418  pop     rsi
0x1800f6419  pop     rbp
0x1800f641a  retn
0x1800f641b  mov     r9d, eax; char *
0x1800f641e  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6425  mov     edx, 7Ch ; '|'; void *
0x1800f642a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6430  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6437  mov     edx, 75h ; 'u'; void *
0x1800f643c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
