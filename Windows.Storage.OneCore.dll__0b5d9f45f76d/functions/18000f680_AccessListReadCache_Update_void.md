# AccessListReadCache::Update(void)

- ea: `0x18000f680`
- end: `0x18000fa43`
- name: `?Update@AccessListReadCache@@UEAAXXZ`
- size: `963`
- prototype: `void __fastcall(AccessListReadCache *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ca78`

## callees

- `0x1800030bc`
- `0x18000bd3c`
- `0x18000ca4c`
- `0x18000ce6c`
- `0x18000cf04`
- `0x18000d228`
- `0x18000d498`
- `0x18000d7d0`
- `0x18000d974`
- `0x18000d9c0`
- `0x18000f680`
- `0x18000fa4c`
- `0x18000fcd0`
- `0x1800102cc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f8f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f8f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f8d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f8d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall AccessListReadCache::Update(HKEY *this)
{
  WindowsStorage::Utilities::registry_key_iterator *v2; // rax
  _QWORD *v3; // rax
  WindowsStorage::Utilities::registry_key_iterator *v4; // rax
  const struct WindowsStorage::Utilities::registry_key_iterator *v5; // r9
  const WCHAR **v6; // rax
  const WCHAR *v7; // r14
  const WCHAR *StringRawBuffer; // rax
  int v9; // eax
  __int64 v10; // rdi
  bool v11; // zf
  const unsigned __int16 **v12; // rax
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // rdx
  __int64 *v15; // rbx
  const unsigned __int16 **v16; // rax
  const unsigned __int16 *v17; // r8
  int v18; // eax
  const char *bIgnoreCase; // [rsp+20h] [rbp-248h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-248h]
  __int128 v21; // [rsp+30h] [rbp-238h] BYREF
  __int64 v22; // [rsp+40h] [rbp-228h] BYREF
  __int128 v23; // [rsp+48h] [rbp-220h]
  __int128 v24; // [rsp+58h] [rbp-210h]
  __int64 v25; // [rsp+68h] [rbp-200h]
  int v26; // [rsp+70h] [rbp-1F8h]
  int v27; // [rsp+74h] [rbp-1F4h]
  _BYTE v28[24]; // [rsp+78h] [rbp-1F0h] BYREF
  int v29; // [rsp+90h] [rbp-1D8h] BYREF
  __int128 v30; // [rsp+98h] [rbp-1D0h]
  __int128 v31; // [rsp+A8h] [rbp-1C0h]
  __int64 v32; // [rsp+B8h] [rbp-1B0h]
  int v33; // [rsp+C0h] [rbp-1A8h]
  __int64 v34; // [rsp+C8h] [rbp-1A0h]
  __int128 v35; // [rsp+D0h] [rbp-198h]
  __int64 v36; // [rsp+E0h] [rbp-188h] BYREF
  _BYTE v37[24]; // [rsp+E8h] [rbp-180h] BYREF
  _BYTE v38[80]; // [rsp+100h] [rbp-168h] BYREF
  _BYTE v39[80]; // [rsp+150h] [rbp-118h] BYREF
  _BYTE v40[80]; // [rsp+1A0h] [rbp-C8h] BYREF
  _BYTE v41[120]; // [rsp+1F0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]
  __int64 *length; // [rsp+278h] [rbp+10h] BYREF
  int *v45; // [rsp+280h] [rbp+18h] BYREF
  __int64 *v46; // [rsp+288h] [rbp+20h] BYREF

  std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(v37, this + 3);
  try
  {
    WindowsStorage::Utilities::registry_key_iterator::registry_key_iterator(
      (WindowsStorage::Utilities::registry_key_iterator *)v38,
      this[1]);
    v22 = 131097;
    v27 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = -1;
    memset(v28, 0, sizeof(v28));
    length = &v22;
    v2 = WindowsStorage::Utilities::registry_key_iterator::registry_key_iterator(
           (WindowsStorage::Utilities::registry_key_iterator *)v39,
           (const struct WindowsStorage::Utilities::registry_key_iterator *)v38);
    v29 = *(_DWORD *)v2;
    v30 = 0;
    v30 = *(_OWORD *)((char *)v2 + 8);
    *((_QWORD *)v2 + 1) = 0;
    *((_QWORD *)v2 + 2) = 0;
    v31 = 0;
    v31 = *(_OWORD *)((char *)v2 + 24);
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 4) = 0;
    v32 = *((_QWORD *)v2 + 5);
    v33 = *((_DWORD *)v2 + 12);
    v34 = *((_QWORD *)v2 + 7);
    v35 = 0;
    v35 = *((_OWORD *)v2 + 4);
    *((_QWORD *)v2 + 8) = 0;
    *((_QWORD *)v2 + 9) = 0;
    WindowsStorage::Utilities::registry_key_iterator::~registry_key_iterator(v2);
    v45 = &v29;
    v21 = 0;
    v3 = operator new(0x38u);
    *v3 = v3;
    v3[1] = v3;
    v3[2] = v3;
    *((_WORD *)v3 + 12) = 257;
    *(_QWORD *)&v21 = v3;
    WindowsStorage::Utilities::registry_key_iterator::registry_key_iterator(
      (WindowsStorage::Utilities::registry_key_iterator *)v40,
      (const struct WindowsStorage::Utilities::registry_key_iterator *)&v22);
    v4 = WindowsStorage::Utilities::registry_key_iterator::registry_key_iterator(
           (WindowsStorage::Utilities::registry_key_iterator *)v41,
           (const struct WindowsStorage::Utilities::registry_key_iterator *)&v29);
    std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::insert<WindowsStorage::Utilities::registry_key_iterator>(
      (__int64 *)&v21,
      v4,
      v5);
    WindowsStorage::Utilities::registry_key_iterator::~registry_key_iterator((WindowsStorage::Utilities::registry_key_iterator *)&v29);
    WindowsStorage::Utilities::registry_key_iterator::~registry_key_iterator((WindowsStorage::Utilities::registry_key_iterator *)&v22);
    v10 = *(_QWORD *)this[4];
    v15 = *(__int64 **)v21;
    v46 = *(__int64 **)v21;
LABEL_2:
    v45 = (int *)v10;
    while ( 1 )
    {
      if ( (HKEY)v10 == this[4] )
        goto LABEL_21;
      if ( v15 == (__int64 *)v21 )
        break;
      v6 = (const WCHAR **)v15[5];
      if ( v6 )
        v7 = *v6;
      else
        v7 = 0;
      LODWORD(length) = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v10 + 32), (UINT32 *)&length);
      v9 = CompareStringOrdinal(StringRawBuffer, (int)length, v7, -1, 1);
      if ( v9 == 1 )
      {
        v10 = *AccessListReadCache::_EraseCacheEntry((__int64)this, &v36, (__int64 *)&v45);
        goto LABEL_2;
      }
      v11 = v9 == 3;
      v12 = (const unsigned __int16 **)v15[5];
      if ( v11 )
      {
        if ( v12 )
          v13 = *v12;
        else
          v13 = 0;
        AccessListReadCache::_InsertCacheEntry((__int64)this, (__int64 *)&v45, v13);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsStorage::Utilities::registry_key_entry>>,std::_Iterator_base0>::operator++(&v46);
      }
      else
      {
        if ( v12 )
          v14 = *v12;
        else
          v14 = 0;
        AccessListReadCache::CacheItem::UpdateIfNeeded((AccessListReadCache::CacheItem *)(v10 + 40), v14);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>>,std::_Iterator_base0>::operator++((__int64 *)&v45);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsStorage::Utilities::registry_key_entry>>,std::_Iterator_base0>::operator++(&v46);
        v10 = (__int64)v45;
      }
      v15 = v46;
    }
    if ( (HKEY)v10 == this[4] )
    {
LABEL_21:
      while ( v15 != (__int64 *)v21 )
      {
        v16 = (const unsigned __int16 **)v15[5];
        if ( v16 )
          v17 = *v16;
        else
          v17 = 0;
        AccessListReadCache::_InsertCacheEntry((__int64)this, (__int64 *)&v45, v17);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsStorage::Utilities::registry_key_entry>>,std::_Iterator_base0>::operator++(&v46);
        v15 = v46;
      }
      goto LABEL_27;
    }
    if ( v15 != (__int64 *)v21 )
      goto LABEL_29;
LABEL_27:
    while ( (HKEY)v10 != this[4] )
    {
      v10 = *AccessListReadCache::_EraseCacheEntry((__int64)this, &length, (__int64 *)&v45);
      v45 = (int *)v10;
    }
LABEL_29:
    std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::~_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>((_QWORD **)&v21);
    WindowsStorage::Utilities::registry_key_iterator::~registry_key_iterator((WindowsStorage::Utilities::registry_key_iterator *)v38);
    std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(v37);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
      "AccessListReadCache::Update",
      bIgnoreCase);
    v18 = AccessListReadCache::Clear((AccessListReadCache *)this);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCasea);
  }
}

```

## disassembly

```asm
0x18000f680  mov     [rsp+arg_0], rcx
0x18000f685  push    rbx
0x18000f686  push    rsi
0x18000f687  push    rdi
0x18000f688  push    r14
0x18000f68a  sub     rsp, 248h
0x18000f691  mov     rsi, rcx
0x18000f694  lea     rdx, [rcx+18h]
0x18000f698  lea     rcx, [rsp+268h+var_180]
0x18000f6a0  call    ??0?$unique_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(std::shared_mutex &)
0x18000f6a5  nop
0x18000f6a6  mov     rdx, [rsi+8]; HKEY
0x18000f6aa  lea     rcx, [rsp+268h+var_168]; this
0x18000f6b2  call    ??0registry_key_iterator@Utilities@WindowsStorage@@QEAA@PEAUHKEY__@@@Z; WindowsStorage::Utilities::registry_key_iterator::registry_key_iterator(HKEY__ *)
0x18000f6b7  nop
0x18000f6b8  mov     [rsp+268h+var_228], 20019h
0x18000f6c1  mov     [rsp+268h+var_1F4], 0
0x18000f6c9  xorps   xmm0, xmm0
0x18000f6cc  xorps   xmm1, xmm1
0x18000f6cf  movdqu  [rsp+268h+var_220], xmm1
0x18000f6d5  movdqu  [rsp+268h+var_210], xmm1
0x18000f6db  mov     [rsp+268h+var_200], 0
0x18000f6e4  mov     [rsp+268h+var_1F8], 0FFFFFFFFh
0x18000f6ec  xor     eax, eax
0x18000f6ee  movups  xmmword ptr [rsp+268h+var_1F0], xmm0
0x18000f6f3  mov     qword ptr [rsp+268h+var_1F0], rax
0x18000f6f8  movdqu  xmmword ptr [rsp+268h+var_1F0+8], xmm1
0x18000f701  lea     rax, [rsp+268h+var_228]
0x18000f706  mov     [rsp+268h+length], rax
0x18000f70e  lea     rdx, [rsp+268h+var_168]; struct WindowsStorage::Utilities::registry_key_iterator *
0x18000f716  lea     rcx, [rsp+268h+var_118]; this
0x18000f71e  call    ??0registry_key_iterator@Utilities@WindowsStorage@@QEAA@AEBV012@@Z; WindowsStorage::Utilities::registry_key_iterator::registry_key_iterator(WindowsStorage::Utilities::registry_key_iterator const &)
0x18000f723  mov     rdx, rax
0x18000f726  mov     ecx, [rax]
0x18000f728  mov     [rsp+268h+var_1D8], ecx
0x18000f72f  movdqu  [rsp+268h+var_1D0], xmm0
0x18000f738  mov     rcx, [rax+8]
0x18000f73c  mov     qword ptr [rsp+268h+var_1D0], rcx
0x18000f744  mov     rcx, [rax+10h]
0x18000f748  mov     qword ptr [rsp+268h+var_1D0+8], rcx
0x18000f750  mov     qword ptr [rax+8], 0
0x18000f758  mov     qword ptr [rax+10h], 0
0x18000f760  movdqu  [rsp+268h+var_1C0], xmm0
0x18000f769  mov     rax, [rax+18h]
0x18000f76d  mov     qword ptr [rsp+268h+var_1C0], rax
0x18000f775  mov     rax, [rdx+20h]
0x18000f779  mov     qword ptr [rsp+268h+var_1C0+8], rax
0x18000f781  mov     qword ptr [rdx+18h], 0
0x18000f789  mov     qword ptr [rdx+20h], 0
0x18000f791  mov     rax, [rdx+28h]
0x18000f795  mov     [rsp+268h+var_1B0], rax
0x18000f79d  mov     eax, [rdx+30h]
0x18000f7a0  mov     [rsp+268h+var_1A8], eax
0x18000f7a7  mov     rax, [rdx+38h]
0x18000f7ab  mov     [rsp+268h+var_1A0], rax
0x18000f7b3  movdqu  [rsp+268h+var_198], xmm0
0x18000f7bc  mov     rax, [rdx+40h]
0x18000f7c0  mov     qword ptr [rsp+268h+var_198], rax
0x18000f7c8  mov     rax, [rdx+48h]
0x18000f7cc  mov     qword ptr [rsp+268h+var_198+8], rax
0x18000f7d4  mov     qword ptr [rdx+40h], 0
0x18000f7dc  mov     qword ptr [rdx+48h], 0
0x18000f7e4  mov     rcx, rdx; this
0x18000f7e7  call    ??1registry_key_iterator@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::registry_key_iterator::~registry_key_iterator(void)
0x18000f7ec  lea     rax, [rsp+268h+var_1D8]
0x18000f7f4  mov     [rsp+268h+arg_10], rax
0x18000f7fc  xorps   xmm0, xmm0
0x18000f7ff  movdqu  [rsp+268h+var_238], xmm0
0x18000f805  mov     ecx, 38h ; '8'; Size
0x18000f80a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f80f  mov     [rax], rax
0x18000f812  mov     [rax+8], rax
0x18000f816  mov     [rax+10h], rax
0x18000f81a  mov     word ptr [rax+18h], 101h
0x18000f820  mov     qword ptr [rsp+268h+var_238], rax
0x18000f825  lea     rdx, [rsp+268h+var_228]; struct WindowsStorage::Utilities::registry_key_iterator *
0x18000f82a  lea     rcx, [rsp+268h+var_C8]; this
0x18000f832  call    ??0registry_key_iterator@Utilities@WindowsStorage@@QEAA@AEBV012@@Z; WindowsStorage::Utilities::registry_key_iterator::registry_key_iterator(WindowsStorage::Utilities::registry_key_iterator const &)
0x18000f837  mov     r9, rax
0x18000f83a  lea     rdx, [rsp+268h+var_1D8]; struct WindowsStorage::Utilities::registry_key_iterator *
0x18000f842  lea     rcx, [rsp+268h+var_78]; this
0x18000f84a  call    ??0registry_key_iterator@Utilities@WindowsStorage@@QEAA@AEBV012@@Z; WindowsStorage::Utilities::registry_key_iterator::registry_key_iterator(WindowsStorage::Utilities::registry_key_iterator const &)
0x18000f84f  mov     r8, r9
0x18000f852  mov     rdx, rax
0x18000f855  lea     rcx, [rsp+268h+var_238]
0x18000f85a  call    ??$insert@Vregistry_key_iterator@Utilities@WindowsStorage@@@?$_Tree@V?$_Tset_traits@Vregistry_key_entry@Utilities@WindowsStorage@@U?$less@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@V?$allocator@Vregistry_key_entry@Utilities@WindowsStorage@@@5@$0A@@std@@@std@@QEAAXVregistry_key_iterator@Utilities@WindowsStorage@@0@Z; std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::insert<WindowsStorage::Utilities::registry_key_iterator>(WindowsStorage::Utilities::registry_key_iterator,WindowsStorage::Utilities::registry_key_iterator)
0x18000f85f  nop
0x18000f860  lea     rcx, [rsp+268h+var_1D8]; this
0x18000f868  call    ??1registry_key_iterator@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::registry_key_iterator::~registry_key_iterator(void)
0x18000f86d  nop
0x18000f86e  lea     rcx, [rsp+268h+var_228]; this
0x18000f873  call    ??1registry_key_iterator@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::registry_key_iterator::~registry_key_iterator(void)
0x18000f878  nop
0x18000f879  mov     rdi, [rsi+20h]
0x18000f87d  mov     rdi, [rdi]
0x18000f880  mov     rbx, qword ptr [rsp+268h+var_238]
0x18000f885  mov     rbx, [rbx]
0x18000f888  mov     [rsp+268h+arg_18], rbx
0x18000f890  mov     [rsp+268h+arg_10], rdi
0x18000f898  cmp     rdi, [rsi+20h]
0x18000f89c  jz      loc_18000F99E
0x18000f8a2  cmp     rbx, qword ptr [rsp+268h+var_238]
0x18000f8a7  jz      loc_18000F998
0x18000f8ad  mov     rax, [rbx+28h]
0x18000f8b1  test    rax, rax
0x18000f8b4  jz      short loc_18000F8BB
0x18000f8b6  mov     r14, [rax]
0x18000f8b9  jmp     short loc_18000F8BE
0x18000f8bb  xor     r14d, r14d
0x18000f8be  mov     dword ptr [rsp+268h+length], 0
0x18000f8c9  lea     rdx, [rsp+268h+length]; length
0x18000f8d1  mov     rcx, [rdi+20h]; string
0x18000f8d5  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f8db  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x18000f8e3  or      r9d, 0FFFFFFFFh; cchCount2
0x18000f8e7  mov     r8, r14; lpString2
0x18000f8ea  mov     edx, dword ptr [rsp+268h+length]; cchCount1
0x18000f8f1  mov     rcx, rax; lpString1
0x18000f8f4  call    cs:__imp_CompareStringOrdinal
0x18000f8fa  cmp     eax, 1
0x18000f8fd  jnz     short loc_18000F91F
0x18000f8ff  lea     r8, [rsp+268h+arg_10]
0x18000f907  lea     rdx, [rsp+268h+var_188]
0x18000f90f  mov     rcx, rsi
0x18000f912  call    ?_EraseCacheEntry@AccessListReadCache@@AEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@std@@@std@@@std@@AEBV23@@Z; AccessListReadCache::_EraseCacheEntry(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>>> const &)
0x18000f917  mov     rdi, [rax]
0x18000f91a  jmp     loc_18000F890
0x18000f91f  cmp     eax, 3
0x18000f922  mov     rax, [rbx+28h]
0x18000f926  jnz     short loc_18000F954
0x18000f928  test    rax, rax
0x18000f92b  jz      short loc_18000F932
0x18000f92d  mov     r8, [rax]
0x18000f930  jmp     short loc_18000F935
0x18000f932  xor     r8d, r8d
0x18000f935  lea     rdx, [rsp+268h+arg_10]
0x18000f93d  mov     rcx, rsi
0x18000f940  call    ?_InsertCacheEntry@AccessListReadCache@@AEAAXAEBV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@std@@@std@@@std@@PEBG@Z; AccessListReadCache::_InsertCacheEntry(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>>> const &,ushort const *)
0x18000f945  lea     rcx, [rsp+268h+arg_18]
0x18000f94d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsStorage::Utilities::registry_key_entry>>,std::_Iterator_base0>::operator++(void)
0x18000f952  jmp     short loc_18000F98B
0x18000f954  test    rax, rax
0x18000f957  jz      short loc_18000F95E
0x18000f959  mov     rdx, [rax]
0x18000f95c  jmp     short loc_18000F960
0x18000f95e  xor     edx, edx; unsigned __int16 *
0x18000f960  lea     rcx, [rdi+28h]; this
0x18000f964  call    ?UpdateIfNeeded@CacheItem@AccessListReadCache@@QEAAJPEBG@Z; AccessListReadCache::CacheItem::UpdateIfNeeded(ushort const *)
0x18000f969  lea     rcx, [rsp+268h+arg_10]
0x18000f971  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>>,std::_Iterator_base0>::operator++(void)
0x18000f976  lea     rcx, [rsp+268h+arg_18]
0x18000f97e  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsStorage::Utilities::registry_key_entry>>,std::_Iterator_base0>::operator++(void)
0x18000f983  mov     rdi, [rsp+268h+arg_10]
0x18000f98b  mov     rbx, [rsp+268h+arg_18]
0x18000f993  jmp     loc_18000F898
0x18000f998  cmp     rdi, [rsi+20h]
0x18000f99c  jnz     short loc_18000F9DD
0x18000f99e  cmp     rbx, qword ptr [rsp+268h+var_238]
0x18000f9a3  jz      short loc_18000F9E4
0x18000f9a5  mov     rax, [rbx+28h]
0x18000f9a9  test    rax, rax
0x18000f9ac  jz      short loc_18000F9B3
0x18000f9ae  mov     r8, [rax]
0x18000f9b1  jmp     short loc_18000F9B6
0x18000f9b3  xor     r8d, r8d
0x18000f9b6  lea     rdx, [rsp+268h+arg_10]
0x18000f9be  mov     rcx, rsi
0x18000f9c1  call    ?_InsertCacheEntry@AccessListReadCache@@AEAAXAEBV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@std@@@std@@@std@@PEBG@Z; AccessListReadCache::_InsertCacheEntry(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>>> const &,ushort const *)
0x18000f9c6  lea     rcx, [rsp+268h+arg_18]
0x18000f9ce  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsStorage::Utilities::registry_key_entry>>,std::_Iterator_base0>::operator++(void)
0x18000f9d3  mov     rbx, [rsp+268h+arg_18]
0x18000f9db  jmp     short loc_18000F99E
0x18000f9dd  cmp     rbx, qword ptr [rsp+268h+var_238]
0x18000f9e2  jnz     short loc_18000FA0F
0x18000f9e4  cmp     rdi, [rsi+20h]
0x18000f9e8  jz      short loc_18000FA0F
0x18000f9ea  lea     r8, [rsp+268h+arg_10]
0x18000f9f2  lea     rdx, [rsp+268h+length]
0x18000f9fa  mov     rcx, rsi
0x18000f9fd  call    ?_EraseCacheEntry@AccessListReadCache@@AEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@std@@@std@@@std@@AEBV23@@Z; AccessListReadCache::_EraseCacheEntry(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>>> const &)
0x18000fa02  mov     rdi, [rax]
0x18000fa05  mov     [rsp+268h+arg_10], rdi
0x18000fa0d  jmp     short loc_18000F9E4
0x18000fa0f  lea     rcx, [rsp+268h+var_238]
0x18000fa14  call    ??1?$_Tree@V?$_Tset_traits@Vregistry_key_entry@Utilities@WindowsStorage@@U?$less@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@V?$allocator@Vregistry_key_entry@Utilities@WindowsStorage@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::~_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>(void)
0x18000fa19  nop
0x18000fa1a  lea     rcx, [rsp+268h+var_168]; this
0x18000fa22  call    ??1registry_key_iterator@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::registry_key_iterator::~registry_key_iterator(void)
0x18000fa27  nop
0x18000fa28  lea     rcx, [rsp+268h+var_180]
0x18000fa30  call    ??1?$unique_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(void)
0x18000fa35  nop
0x18000fa36  add     rsp, 248h
0x18000fa3d  pop     r14
0x18000fa3f  pop     rdi
0x18000fa40  pop     rsi
0x18000fa41  pop     rbx
0x18000fa42  retn
```
