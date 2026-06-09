# Windows::Networking::UX::Internal::ProfileManager::CacheProfileList(wil::write_lock_required,_GUID const *,WCM_WLAN_PROFILE_INFO_LIST *)

- ea: `0x180073cd8`
- end: `0x180073f50`
- name: `?CacheProfileList@ProfileManager@Internal@UX@Networking@Windows@@AEAAXUwrite_lock_required@wil@@PEBU_GUID@@PEAUWCM_WLAN_PROFILE_INFO_LIST@@@Z`
- size: `632`
- prototype: `void __high(struct wil::write_lock_required, const struct _GUID *, struct WCM_WLAN_PROFILE_INFO_LIST *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800743bc`
- `0x180074790`

## callees

- `0x180003ed0`
- `0x1800043ec`
- `0x18000b86c`
- `0x18000fb40`
- `0x18001bfc0`
- `0x18001d4d4`
- `0x1800321b0`
- `0x180057648`
- `0x1800738dc`
- `0x180073988`
- `0x180073a3c`
- `0x180073cd8`
- `0x180074190`
- `0x180074a5c`
- `0x180074c54`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180073d7b`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180073d7b`
- `wlanapi!WlanPrivateQuery11adPairedConfig` at `0x180073d2e`
- `wlanapi!WlanPrivateQuery11adPairedConfig` at `0x180073d2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PVOID *__fastcall Windows::Networking::UX::Internal::ProfileManager::CacheProfileList(
        _QWORD *a1,
        __int64 a2,
        const struct _GUID *a3,
        unsigned int *a4)
{
  bool v7; // r12
  __int64 v8; // rax
  _QWORD *v9; // r14
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int i; // ebx
  Windows::Networking::UX::Internal::Profile *v15; // rax
  __int64 v16; // rax
  PVOID *result; // rax
  unsigned __int64 v18; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-90h] BYREF
  __int64 v20; // [rsp+40h] [rbp-88h] BYREF
  __int64 *v21; // [rsp+48h] [rbp-80h] BYREF
  __int64 *v22; // [rsp+50h] [rbp-78h]
  PVOID pMemory; // [rsp+58h] [rbp-70h] BYREF
  void **v24; // [rsp+60h] [rbp-68h] BYREF
  struct _GUID v25; // [rsp+70h] [rbp-58h] BYREF
  __int128 v26; // [rsp+80h] [rbp-48h] BYREF
  __int64 v27; // [rsp+90h] [rbp-38h]

  v24 = (void **)a1;
  pMemory = 0;
  v19 = 0;
  v7 = 0;
  if ( !(unsigned int)WlanPrivateQuery11adPairedConfig(*a1, &v19, &pMemory) && pMemory )
  {
    if ( v19 >= 0x3C && *((_DWORD *)pMemory + 12) && *((_DWORD *)pMemory + 13) )
    {
      v8 = *(_QWORD *)((char *)pMemory + 20) - *(_QWORD *)&a3->Data1;
      if ( !v8 )
        v8 = *(_QWORD *)((char *)pMemory + 28) - *(_QWORD *)a3->Data4;
      v7 = v8 == 0;
    }
    WlanFreeMemory(pMemory);
  }
  v9 = a1 + 6;
  std::_Tree<std::_Tmap_traits<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>,Windows::Networking::UX::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>>,0>>::find(
    a1 + 6,
    &v18,
    a3);
  v11 = v18;
  if ( v18 != *v9 )
  {
    Windows::Networking::UX::Internal::ProfileManager::FreeCachedProfileList(v10, v18 + 48);
    v12 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>>>::_Extract(
            v9,
            v11);
    std::_Tree_node<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>,void *>>>(
      v13,
      v12);
  }
  std::vector<Windows::Networking::UX::Internal::Profile *>::vector<Windows::Networking::UX::Internal::Profile *>(&v20);
  try
  {
    v18 = *a4;
    if ( v18 > ((__int64)v22 - v20) >> 3 )
      std::vector<Windows::Networking::UX::Internal::Profile *>::_Reallocate<0>(&v20, &v18);
    for ( i = 0; i < *a4; ++i )
    {
      v15 = (Windows::Networking::UX::Internal::Profile *)operator new(0x260u);
      v16 = Windows::Networking::UX::Internal::Profile::Profile(
              v15,
              *v24,
              a3,
              (struct WCM_WLAN_PROFILE_INFO *)&a4[154 * i + 2],
              v7);
      v18 = v16;
      if ( v21 == v22 )
        std::vector<_L2_NOTIFICATION_DATA *>::_Emplace_reallocate<_L2_NOTIFICATION_DATA *>(&v20, v21, &v18);
      else
        *v21++ = v16;
    }
    v25 = *a3;
    v26 = 0;
    v27 = 0;
    std::vector<Windows::Networking::UX::Internal::Profile *>::_Construct_n<Windows::Networking::UX::Internal::Profile * * const &,Windows::Networking::UX::Internal::Profile * * const &>(
      &v26,
      ((__int64)v21 - v20) >> 3,
      &v20,
      &v21);
    std::_Tree<std::_Tmap_traits<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>,Windows::Networking::UX::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>>,0>>::_Emplace<std::pair<_GUID,std::vector<Windows::Networking::UX::Internal::Profile *>>>(
      v9,
      &v24,
      &v25);
    std::vector<Windows::Networking::UX::Internal::Profile *>::_Tidy(&v26);
    result = (PVOID *)std::vector<Windows::Networking::UX::Internal::Profile *>::_Tidy(&v20);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v18) = 8;
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      return (PVOID *)WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        17,
                        WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids,
                        (unsigned __int16)v18 | 0x80070000);
  }
  return result;
}

```

## disassembly

```asm
0x180073cd8  mov     [rsp+arg_8], rbx
0x180073cdd  push    rsi
0x180073cde  push    r12
0x180073ce0  push    r13
0x180073ce2  push    r14
0x180073ce4  push    r15
0x180073ce6  sub     rsp, 0A0h
0x180073ced  mov     rax, cs:__security_cookie
0x180073cf4  xor     rax, rsp
0x180073cf7  mov     [rsp+0C8h+var_30], rax
0x180073cff  mov     r13, r9
0x180073d02  mov     r15, r8
0x180073d05  mov     rbx, rcx
0x180073d08  mov     [rsp+0C8h+var_68], rcx
0x180073d0d  mov     [rsp+0C8h+pMemory], 0
0x180073d16  mov     [rsp+0C8h+var_90], 0
0x180073d1e  xor     r12b, r12b
0x180073d21  lea     r8, [rsp+0C8h+pMemory]
0x180073d26  lea     rdx, [rsp+0C8h+var_90]
0x180073d2b  mov     rcx, [rcx]
0x180073d2e  call    cs:__imp_WlanPrivateQuery11adPairedConfig
0x180073d34  test    eax, eax
0x180073d36  jnz     short loc_180073D83
0x180073d38  mov     rcx, [rsp+0C8h+pMemory]; pMemory
0x180073d3d  test    rcx, rcx
0x180073d40  jz      short loc_180073D83
0x180073d42  cmp     [rsp+0C8h+var_90], 3Ch ; '<'
0x180073d47  jb      short loc_180073D76
0x180073d49  cmp     [rcx+30h], eax
0x180073d4c  jz      short loc_180073D76
0x180073d4e  cmp     [rcx+34h], eax
0x180073d51  jz      short loc_180073D76
0x180073d53  mov     rax, [rcx+14h]
0x180073d57  sub     rax, [r15]
0x180073d5a  jnz     short loc_180073D64
0x180073d5c  mov     rax, [rcx+1Ch]
0x180073d60  sub     rax, [r15+8]
0x180073d64  movzx   r12d, r12b
0x180073d68  mov     esi, 1
0x180073d6d  test    rax, rax
0x180073d70  cmovz   r12d, esi
0x180073d74  jmp     short loc_180073D7B
0x180073d76  mov     esi, 1
0x180073d7b  call    cs:__imp_WlanFreeMemory
0x180073d81  jmp     short loc_180073D88
0x180073d83  mov     esi, 1
0x180073d88  lea     r14, [rbx+30h]
0x180073d8c  mov     r8, r15
0x180073d8f  lea     rdx, [rsp+0C8h+var_98]
0x180073d94  mov     rcx, r14
0x180073d97  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@UGUIDComparer@Internal@UX@Networking@Windows@@V?$allocator@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>,Windows::Networking::UX::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>>,0>>::find(_GUID const &)
0x180073d9c  mov     rbx, [rsp+0C8h+var_98]
0x180073da1  cmp     rbx, [r14]
0x180073da4  jz      short loc_180073DC3
0x180073da6  lea     rdx, [rbx+30h]
0x180073daa  call    ?FreeCachedProfileList@ProfileManager@Internal@UX@Networking@Windows@@AEAAXAEAV?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@Z; Windows::Networking::UX::Internal::ProfileManager::FreeCachedProfileList(std::vector<Windows::Networking::UX::Internal::Profile *> &)
0x180073daf  mov     rdx, rbx
0x180073db2  mov     rcx, r14
0x180073db5  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>>>,std::_Iterator_base0>)
0x180073dba  mov     rdx, rax
0x180073dbd  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>,void *>> &,std::_Tree_node<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>,void *> *)
0x180073dc2  nop
0x180073dc3  lea     rcx, [rsp+0C8h+var_88]
0x180073dc8  call    ??0?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Networking::UX::Internal::Profile *>::vector<Windows::Networking::UX::Internal::Profile *>(void)
0x180073dcd  nop
0x180073dce  mov     ecx, [r13+0]
0x180073dd2  mov     [rsp+0C8h+var_98], rcx
0x180073dd7  mov     rax, [rsp+0C8h+var_78]
0x180073ddc  sub     rax, [rsp+0C8h+var_88]
0x180073de1  sar     rax, 3
0x180073de5  cmp     rcx, rax
0x180073de8  jbe     short loc_180073DF9
0x180073dea  lea     rdx, [rsp+0C8h+var_98]
0x180073def  lea     rcx, [rsp+0C8h+var_88]
0x180073df4  call    ??$_Reallocate@$0A@@?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Windows::Networking::UX::Internal::Profile *>::_Reallocate<0>(unsigned __int64 &)
0x180073df9  xor     ebx, ebx
0x180073dfb  cmp     ebx, [r13+0]
0x180073dff  jnb     short loc_180073E62
0x180073e01  mov     ecx, 260h; Size
0x180073e06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073e0b  mov     ecx, ebx
0x180073e0d  imul    r9, rcx, 268h
0x180073e14  add     r9, 8
0x180073e18  add     r9, r13; struct WCM_WLAN_PROFILE_INFO *
0x180073e1b  mov     [rsp+0C8h+var_A8], r12b; bool
0x180073e20  mov     r8, r15; struct _GUID *
0x180073e23  mov     rcx, [rsp+0C8h+var_68]
0x180073e28  mov     rdx, [rcx]; void *
0x180073e2b  mov     rcx, rax; this
0x180073e2e  call    ??0Profile@Internal@UX@Networking@Windows@@QEAA@PEAXPEBU_GUID@@PEAUWCM_WLAN_PROFILE_INFO@@_N@Z; Windows::Networking::UX::Internal::Profile::Profile(void *,_GUID const *,WCM_WLAN_PROFILE_INFO *,bool)
0x180073e33  mov     [rsp+0C8h+var_98], rax
0x180073e38  mov     rdx, [rsp+0C8h+var_80]
0x180073e3d  cmp     rdx, [rsp+0C8h+var_78]
0x180073e42  jz      short loc_180073E4F
0x180073e44  mov     [rdx], rax
0x180073e47  add     [rsp+0C8h+var_80], 8
0x180073e4d  jmp     short loc_180073E5E
0x180073e4f  lea     r8, [rsp+0C8h+var_98]
0x180073e54  lea     rcx, [rsp+0C8h+var_88]
0x180073e59  call    ??$_Emplace_reallocate@PEAU_L2_NOTIFICATION_DATA@@@?$vector@PEAU_L2_NOTIFICATION_DATA@@V?$allocator@PEAU_L2_NOTIFICATION_DATA@@@std@@@std@@AEAAPEAPEAU_L2_NOTIFICATION_DATA@@QEAPEAU2@$$QEAPEAU2@@Z; std::vector<_L2_NOTIFICATION_DATA *>::_Emplace_reallocate<_L2_NOTIFICATION_DATA *>(_L2_NOTIFICATION_DATA * * const,_L2_NOTIFICATION_DATA * &&)
0x180073e5e  add     ebx, esi
0x180073e60  jmp     short loc_180073DFB
0x180073e62  movups  xmm0, xmmword ptr [r15]
0x180073e66  movdqu  [rsp+0C8h+var_58], xmm0
0x180073e6c  xorps   xmm1, xmm1
0x180073e6f  movdqu  [rsp+0C8h+var_48], xmm1
0x180073e78  mov     [rsp+0C8h+var_38], 0
0x180073e84  mov     rdx, [rsp+0C8h+var_80]
0x180073e89  sub     rdx, [rsp+0C8h+var_88]
0x180073e8e  sar     rdx, 3
0x180073e92  lea     r9, [rsp+0C8h+var_80]
0x180073e97  lea     r8, [rsp+0C8h+var_88]
0x180073e9c  lea     rcx, [rsp+0C8h+var_48]
0x180073ea4  call    ??$_Construct_n@AEBQEAPEAVProfile@Internal@UX@Networking@Windows@@AEBQEAPEAV12345@@?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@AEAAX_KAEBQEAPEAVProfile@Internal@UX@Networking@Windows@@1@Z; std::vector<Windows::Networking::UX::Internal::Profile *>::_Construct_n<Windows::Networking::UX::Internal::Profile * * const &,Windows::Networking::UX::Internal::Profile * * const &>(unsigned __int64,Windows::Networking::UX::Internal::Profile * * const &,Windows::Networking::UX::Internal::Profile * * const &)
0x180073ea9  nop
0x180073eaa  lea     r8, [rsp+0C8h+var_58]
0x180073eaf  lea     rdx, [rsp+0C8h+var_68]
0x180073eb4  mov     rcx, r14
0x180073eb7  call    ??$_Emplace@U?$pair@U_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@UGUIDComparer@Internal@UX@Networking@Windows@@V?$allocator@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_GUID@@V?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>,Windows::Networking::UX::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,std::vector<Windows::Networking::UX::Internal::Profile *>>>,0>>::_Emplace<std::pair<_GUID,std::vector<Windows::Networking::UX::Internal::Profile *>>>(std::pair<_GUID,std::vector<Windows::Networking::UX::Internal::Profile *>> &&)
0x180073ebc  nop
0x180073ebd  lea     rcx, [rsp+0C8h+var_48]
0x180073ec5  call    ?_Tidy@?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::Networking::UX::Internal::Profile *>::_Tidy(void)
0x180073eca  nop
0x180073ecb  lea     rcx, [rsp+0C8h+var_88]
0x180073ed0  call    ?_Tidy@?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::Networking::UX::Internal::Profile *>::_Tidy(void)
0x180073ed5  nop
0x180073ed6  jmp     short loc_180073F27
0x180073ed8  mov     r9d, dword ptr [rsp+0C8h+var_98]
0x180073edd  movzx   edx, r9w
0x180073ee1  mov     eax, edx
0x180073ee3  mov     r8d, 80070000h
0x180073ee9  or      eax, r8d
0x180073eec  jge     short loc_180073F27
0x180073eee  lea     rax, WPP_GLOBAL_Control
0x180073ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x180073efc  cmp     rcx, rax
0x180073eff  jz      short loc_180073F27
0x180073f01  test    byte ptr [rcx+1Ch], 2
0x180073f05  jz      short loc_180073F27
0x180073f07  test    r9d, r9d
0x180073f0a  jle     short loc_180073F12
0x180073f0c  mov     r9d, edx
0x180073f0f  or      r9d, r8d
0x180073f12  mov     edx, 11h
0x180073f17  lea     r8, WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids
0x180073f1e  mov     rcx, [rcx+10h]
0x180073f22  call    WPP_SF_d
0x180073f27  mov     rcx, [rsp+0C8h+var_30]
0x180073f2f  xor     rcx, rsp; StackCookie
0x180073f32  call    __security_check_cookie
0x180073f37  mov     rbx, [rsp+0C8h+arg_8]
0x180073f3f  add     rsp, 0A0h
0x180073f46  pop     r15
0x180073f48  pop     r14
0x180073f4a  pop     r13
0x180073f4c  pop     r12
0x180073f4e  pop     rsi
0x180073f4f  retn
```
