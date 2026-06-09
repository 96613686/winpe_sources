# AppCompatUtility::CheckCacheMatchingPlugin(int *,ushort const *,ulong)

- ea: `0x18003fa7c`
- end: `0x18003fcbe`
- name: `?CheckCacheMatchingPlugin@AppCompatUtility@@YAHPEAHPEBGK@Z`
- size: `578`
- prototype: `__int64 __fastcall(AppCompatUtility *__hidden this, int *, const unsigned __int16 *, unsigned int)`
- caller_count: `12`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000c974`
- `0x18000ef90`
- `0x1800108d0`
- `0x180014580`
- `0x180018a50`
- `0x18001ae10`
- `0x18001cad0`
- `0x18001e440`
- `0x180020d1c`
- `0x180022148`
- `0x180030684`
- `0x180031e14`

## callees

- `0x180001cf0`
- `0x1800020c0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c050`
- `0x18000c10c`
- `0x18001ff74`
- `0x18003d510`
- `0x18003fa7c`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18003fac4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003fac4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003fc89`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003fc89`

## string_xrefs

- `0x18003fbb7`: `Clearing matching plugin cache.`
- `0x18003fbc4`: `AppCompatUtility::CheckCacheMatchingPlugin`
- `0x18003fc6a`: `AppCompatUtility::CheckCacheMatchingPlugin`
- `0x18003fc5d`: `Found from cache for %ws; matched = %d`

## pseudocode

```c
__int64 __fastcall AppCompatUtility::CheckCacheMatchingPlugin(
        AppCompatUtility *this,
        int *a2,
        const unsigned __int16 *a3)
{
  unsigned int v3; // ebx
  _QWORD *v6; // rcx
  _BYTE *v7; // rdx
  _QWORD *v8; // rdi
  __int64 *v9; // rsi
  __int64 *v10; // rbx
  _QWORD *v11; // rbx
  _QWORD *v12; // rdi
  void *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rbx
  int v16; // eax
  const char *v18; // rax
  int v19; // [rsp+28h] [rbp-90h]
  unsigned int v20; // [rsp+30h] [rbp-88h]
  const std::exception *v21; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v22[12]; // [rsp+48h] [rbp-70h] BYREF
  int v23; // [rsp+54h] [rbp-64h]
  __int64 v24; // [rsp+58h] [rbp-60h]
  __int128 v25; // [rsp+60h] [rbp-58h] BYREF
  __int64 v26; // [rsp+70h] [rbp-48h]
  __int64 v27; // [rsp+78h] [rbp-40h]

  v3 = (unsigned int)a3;
  v20 = 0;
  AcquireSRWLockExclusive(&g_CacheLock);
  v6 = (_QWORD *)*((_QWORD *)g_MatchingPluginQueryResultCacheTagIds + 1);
  v23 = 0;
  v7 = g_MatchingPluginQueryResultCacheTagIds;
  while ( !*((_BYTE *)v6 + 25) )
  {
    if ( *((_DWORD *)v6 + 7) >= v3 )
    {
      v7 = v6;
      v6 = (_QWORD *)*v6;
    }
    else
    {
      v6 = (_QWORD *)v6[2];
    }
  }
  try
  {
    if ( !v7[25] && v3 >= *((_DWORD *)v7 + 7) && g_MatchingPluginQueryResultCacheTagIds != v7 )
    {
      v8 = (_QWORD *)g_MatchingPluginQueryResultCache;
      v9 = *(__int64 **)(g_MatchingPluginQueryResultCache + 8);
      while ( !*((_BYTE *)v9 + 25) )
      {
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,int>,void *>>>(
          &g_MatchingPluginQueryResultCache,
          &g_MatchingPluginQueryResultCache,
          v9[2]);
        v10 = v9;
        v9 = (__int64 *)*v9;
        std::wstring::~wstring(v10 + 4);
        operator delete(v10);
      }
      v8[1] = v8;
      *v8 = v8;
      v8[2] = v8;
      qword_180097940 = 0;
      v11 = g_MatchingPluginQueryResultCacheTagIds;
      v12 = (_QWORD *)*((_QWORD *)g_MatchingPluginQueryResultCacheTagIds + 1);
      while ( !*((_BYTE *)v12 + 25) )
      {
        std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
          &g_MatchingPluginQueryResultCacheTagIds,
          &g_MatchingPluginQueryResultCacheTagIds,
          v12[2]);
        v13 = v12;
        v12 = (_QWORD *)*v12;
        operator delete(v13);
      }
      v11[1] = v11;
      *v11 = v11;
      v11[2] = v11;
      qword_180097950 = 0;
      AslLogCallPrintf(3, "AppCompatUtility::CheckCacheMatchingPlugin", 82, "Clearing matching plugin cache.");
    }
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)a2 + v14) );
    std::wstring::_Construct<1,unsigned short const *>(&v25, a2, v14);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
      &g_MatchingPluginQueryResultCache,
      v22,
      &v25);
    v15 = v24;
    if ( *(_BYTE *)(v24 + 25) || (unsigned __int8)std::operator<<unsigned short>(&v25, v24 + 32) )
      v15 = g_MatchingPluginQueryResultCache;
    std::wstring::~wstring(&v25);
    if ( g_MatchingPluginQueryResultCache != v15 )
    {
      v16 = *(_DWORD *)(v15 + 64);
      *(_DWORD *)this = v16;
      v19 = v16;
      AslLogCallPrintf(
        3,
        "AppCompatUtility::CheckCacheMatchingPlugin",
        89,
        "Found from cache for %ws; matched = %d",
        a2,
        v19);
      v20 = 1;
    }
    ReleaseSRWLockExclusive(&g_CacheLock);
  }
  catch ( const std::exception *v21 )
  {
    v18 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v21 + 8LL))(v21);
    AslLogCallPrintf(1, "AppCompatUtility::CheckCacheMatchingPlugin", 97, "Exception: %s", v18);
    return v20;
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "AppCompatUtility::CheckCacheMatchingPlugin", 101, "Unhandled exception.");
  }
  return v20;
}

```

## disassembly

```asm
0x18003fa7c  mov     rax, rsp
0x18003fa7f  push    rsi
0x18003fa80  push    rdi
0x18003fa81  push    r12
0x18003fa83  push    r14
0x18003fa85  push    r15
0x18003fa87  sub     rsp, 90h
0x18003fa8e  mov     qword ptr [rax-80h], 0FFFFFFFFFFFFFFFEh
0x18003fa96  mov     [rax+18h], rbx
0x18003fa9a  mov     rax, cs:__security_cookie
0x18003faa1  xor     rax, rsp
0x18003faa4  mov     [rsp+0B8h+var_38], rax
0x18003faac  mov     ebx, r8d
0x18003faaf  mov     r14, rdx
0x18003fab2  mov     r15, rcx
0x18003fab5  xor     r12d, r12d
0x18003fab8  mov     [rsp+0B8h+var_88], r12d
0x18003fabd  lea     rcx, ?g_CacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003fac4  call    cs:__imp_AcquireSRWLockExclusive
0x18003faca  mov     rax, cs:?g_MatchingPluginQueryResultCacheTagIds@@3V?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@A; std::set<ulong> g_MatchingPluginQueryResultCacheTagIds
0x18003fad1  mov     rcx, [rax+8]
0x18003fad5  xor     edx, edx
0x18003fad7  mov     [rsp+0B8h+var_64], edx
0x18003fadb  mov     rdx, rax
0x18003fade  jmp     short loc_18003FAF1
0x18003fae0  cmp     [rcx+1Ch], ebx
0x18003fae3  jnb     short loc_18003FAEB
0x18003fae5  mov     rcx, [rcx+10h]
0x18003fae9  jmp     short loc_18003FAF1
0x18003faeb  mov     rdx, rcx
0x18003faee  mov     rcx, [rcx]
0x18003faf1  cmp     [rcx+19h], r12b
0x18003faf5  jz      short loc_18003FAE0
0x18003faf7  cmp     [rdx+19h], r12b
0x18003fafb  jnz     loc_18003FBD4
0x18003fb01  cmp     ebx, [rdx+1Ch]
0x18003fb04  jb      loc_18003FBD4
0x18003fb0a  cmp     rax, rdx
0x18003fb0d  jz      loc_18003FBD4
0x18003fb13  mov     rdi, cs:?g_MatchingPluginQueryResultCache@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@A; std::map<std::wstring,int> g_MatchingPluginQueryResultCache
0x18003fb1a  mov     rsi, [rdi+8]
0x18003fb1e  jmp     short loc_18003FB53
0x18003fb20  mov     r8, [rsi+10h]
0x18003fb24  lea     rdx, ?g_MatchingPluginQueryResultCache@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@A; std::map<std::wstring,int> g_MatchingPluginQueryResultCache
0x18003fb2b  lea     rcx, ?g_MatchingPluginQueryResultCache@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@A; std::map<std::wstring,int> g_MatchingPluginQueryResultCache
0x18003fb32  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,int>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,int>,void *>> &,std::_Tree_node<std::pair<std::wstring const,int>,void *> *)
0x18003fb37  mov     rbx, rsi
0x18003fb3a  mov     rsi, [rsi]
0x18003fb3d  lea     rcx, [rbx+20h]; void *
0x18003fb41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003fb46  mov     edx, 48h ; 'H'
0x18003fb4b  mov     rcx, rbx; Block
0x18003fb4e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003fb53  cmp     [rsi+19h], r12b
0x18003fb57  jz      short loc_18003FB20
0x18003fb59  mov     [rdi+8], rdi
0x18003fb5d  mov     [rdi], rdi
0x18003fb60  mov     [rdi+10h], rdi
0x18003fb64  mov     cs:qword_180097940, r12
0x18003fb6b  mov     rbx, cs:?g_MatchingPluginQueryResultCacheTagIds@@3V?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@A; std::set<ulong> g_MatchingPluginQueryResultCacheTagIds
0x18003fb72  mov     rdi, [rbx+8]
0x18003fb76  jmp     short loc_18003FB9F
0x18003fb78  mov     r8, [rdi+10h]
0x18003fb7c  lea     rdx, ?g_MatchingPluginQueryResultCacheTagIds@@3V?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@A; std::set<ulong> g_MatchingPluginQueryResultCacheTagIds
0x18003fb83  lea     rcx, ?g_MatchingPluginQueryResultCacheTagIds@@3V?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@A; std::set<ulong> g_MatchingPluginQueryResultCacheTagIds
0x18003fb8a  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x18003fb8f  mov     rcx, rdi; Block
0x18003fb92  mov     rdi, [rdi]
0x18003fb95  mov     edx, 20h ; ' '
0x18003fb9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003fb9f  cmp     [rdi+19h], r12b
0x18003fba3  jz      short loc_18003FB78
0x18003fba5  mov     [rbx+8], rbx
0x18003fba9  mov     [rbx], rbx
0x18003fbac  mov     [rbx+10h], rbx
0x18003fbb0  mov     cs:qword_180097950, r12
0x18003fbb7  lea     r9, aClearingMatchi; "Clearing matching plugin cache."
0x18003fbbe  mov     r8d, 52h ; 'R'
0x18003fbc4  lea     rdx, aAppcompatutili_19; "AppCompatUtility::CheckCacheMatchingPlu"...
0x18003fbcb  lea     ecx, [r8-4Fh]
0x18003fbcf  call    AslLogCallPrintf
0x18003fbd4  xorps   xmm0, xmm0
0x18003fbd7  movups  [rsp+0B8h+var_58], xmm0
0x18003fbdc  mov     [rsp+0B8h+var_48], r12
0x18003fbe1  mov     [rsp+0B8h+var_40], r12
0x18003fbe6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003fbea  inc     r8
0x18003fbed  cmp     [r14+r8*2], r12w
0x18003fbf2  jnz     short loc_18003FBEA
0x18003fbf4  mov     rdx, r14
0x18003fbf7  lea     rcx, [rsp+0B8h+var_58]
0x18003fbfc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003fc01  lea     r8, [rsp+0B8h+var_58]
0x18003fc06  lea     rdx, [rsp+0B8h+var_70]
0x18003fc0b  lea     rcx, ?g_MatchingPluginQueryResultCache@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@A; std::map<std::wstring,int> g_MatchingPluginQueryResultCache
0x18003fc12  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18003fc17  mov     rbx, [rsp+0B8h+var_60]
0x18003fc1c  cmp     [rbx+19h], r12b
0x18003fc20  jnz     short loc_18003FC34
0x18003fc22  lea     rdx, [rbx+20h]
0x18003fc26  lea     rcx, [rsp+0B8h+var_58]
0x18003fc2b  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18003fc30  test    al, al
0x18003fc32  jz      short loc_18003FC3B
0x18003fc34  mov     rbx, cs:?g_MatchingPluginQueryResultCache@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@A; std::map<std::wstring,int> g_MatchingPluginQueryResultCache
0x18003fc3b  lea     rcx, [rsp+0B8h+var_58]; void *
0x18003fc40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003fc45  cmp     cs:?g_MatchingPluginQueryResultCache@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@@std@@A, rbx; std::map<std::wstring,int> g_MatchingPluginQueryResultCache
0x18003fc4c  jz      short loc_18003FC82
0x18003fc4e  mov     eax, [rbx+40h]
0x18003fc51  mov     [r15], eax
0x18003fc54  mov     [rsp+0B8h+var_90], eax
0x18003fc58  mov     [rsp+0B8h+var_98], r14
0x18003fc5d  lea     r9, aFoundFromCache; "Found from cache for %ws; matched = %d"
0x18003fc64  mov     r8d, 59h ; 'Y'
0x18003fc6a  lea     rdx, aAppcompatutili_19; "AppCompatUtility::CheckCacheMatchingPlu"...
0x18003fc71  lea     ecx, [r8-56h]
0x18003fc75  call    AslLogCallPrintf
0x18003fc7a  mov     [rsp+0B8h+var_88], 1
0x18003fc82  lea     rcx, ?g_CacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003fc89  call    cs:__imp_ReleaseSRWLockExclusive
0x18003fc8f  nop
0x18003fc90  mov     eax, [rsp+0B8h+var_88]
0x18003fc94  mov     rcx, [rsp+0B8h+var_38]
0x18003fc9c  xor     rcx, rsp; StackCookie
0x18003fc9f  call    __security_check_cookie
0x18003fca4  mov     rbx, [rsp+0B8h+arg_10]
0x18003fcac  add     rsp, 90h
0x18003fcb3  pop     r15
0x18003fcb5  pop     r14
0x18003fcb7  pop     r12
0x18003fcb9  pop     rdi
0x18003fcba  pop     rsi
0x18003fcbb  retn
0x18003fcbc  jmp     short loc_18003FC90
```
