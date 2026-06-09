# CommonFileMapping::CommonFileMapping(ushort const *,int,unsigned __int64)

- ea: `0x180020810`
- end: `0x180020a2c`
- name: `??0CommonFileMapping@@QEAA@PEBGH_K@Z`
- size: `540`
- prototype: `CommonFileMapping *__fastcall(CommonFileMapping *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001fae0`

## callees

- `0x18000cde4`
- `0x18000cef4`
- `0x180020398`
- `0x180020694`
- `0x180020810`
- `0x180020f98`
- `0x18002164c`
- `0x180021850`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002098d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800209ea`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002098d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800209ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020904`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020904`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020a04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020a04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020861`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020861`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800208ec`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800208ec`

## pseudocode

```c
CommonFileMapping *__fastcall CommonFileMapping::CommonFileMapping(
        CommonFileMapping *this,
        unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  HMODULE Library; // rax
  struct CommonFileMappingRawBase *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // rcx
  __int64 v16; // rcx
  struct CommonFileMappingRawBase *v18[4]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v19[12]; // [rsp+50h] [rbp-59h] BYREF
  int v20; // [rsp+5Ch] [rbp-4Dh]
  void *v21[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v22; // [rsp+70h] [rbp-39h]
  unsigned __int64 v23; // [rsp+78h] [rbp-31h]
  int v24; // [rsp+80h] [rbp-29h]
  void *v25[3]; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v26; // [rsp+A0h] [rbp-9h]
  int v27; // [rsp+A8h] [rbp-1h]
  struct CommonFileMappingRawBase *v28; // [rsp+B0h] [rbp+7h]
  int v29; // [rsp+B8h] [rbp+Fh]
  int v30; // [rsp+BCh] [rbp+13h]

  v18[2] = this;
  *((_QWORD *)this + 3) = 7;
  *((_QWORD *)this + 2) = 0;
  *(_WORD *)this = 0;
  EnterCriticalSection(&g_SyncLock);
  v18[3] = (struct CommonFileMappingRawBase *)&g_SyncLock;
  std::wstring::assign(this, &dword_180028204);
  *((_DWORD *)this + 8) = 1;
  *((_QWORD *)this + 5) = 0;
  v23 = 7;
  v22 = 0;
  LOWORD(v21[0]) = 0;
  if ( *a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
  }
  std::wstring::assign(v21, a2);
  v24 = a3;
  v8 = *(_QWORD *)std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::find(
                    v7,
                    v19,
                    v21);
  if ( v8 != CommonFileMapping::m_mapSingleton )
  {
    ++*(_DWORD *)(v8 + 80);
LABEL_14:
    v16 = *(_QWORD *)(v8 + 72);
    *((_QWORD *)this + 5) = v16;
    if ( v16 )
    {
      if ( this != (CommonFileMapping *)v21 )
        std::wstring::assign(this);
      *((_DWORD *)this + 8) = v24;
    }
    goto LABEL_18;
  }
  v18[0] = 0;
  if ( a3 )
  {
    if ( GetFileAttributesW(a2) != -1 )
    {
      Library = LoadLibraryExW(a2, 0, 2u);
      if ( Library )
      {
        CommonFileMappingRawPEWrapped::CreateInstance(v18, a2, Library);
        v10 = v18[0];
        if ( v18[0] )
        {
          v26 = 7;
          v25[2] = 0;
          LOWORD(v25[0]) = 0;
          std::wstring::assign(v25);
          v27 = v24;
          v28 = v10;
          v29 = 1;
          v30 = v20;
          v12 = std::_Tree_buy<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>::_Buynode<std::pair<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>>>(
                  v11,
                  v25);
          std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Insert_nohint<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>,void *> *>(
            v13,
            (unsigned int)v18,
            v14,
            v12 + 32,
            v12);
          if ( v26 >= 8 )
            operator delete(v25[0]);
          v8 = *(_QWORD *)std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::find(
                            v15,
                            v18,
                            v21);
          if ( v8 != CommonFileMapping::m_mapSingleton )
            goto LABEL_14;
        }
      }
    }
  }
LABEL_18:
  if ( v23 >= 8 )
    operator delete(v21[0]);
  v23 = 7;
  v22 = 0;
  LOWORD(v21[0]) = 0;
  LeaveCriticalSection(&g_SyncLock);
  return this;
}

```

## disassembly

```asm
0x180020810  push    rbp
0x180020812  push    rbx
0x180020813  push    rsi
0x180020814  push    rdi
0x180020815  push    r13
0x180020817  push    r14
0x180020819  push    r15
0x18002081b  lea     rbp, [rsp-27h]
0x180020820  sub     rsp, 0D0h
0x180020827  mov     rax, cs:__security_cookie
0x18002082e  xor     rax, rsp
0x180020831  mov     [rbp+57h+var_40], rax
0x180020835  mov     esi, r8d
0x180020838  mov     rdi, rdx
0x18002083b  mov     rbx, rcx
0x18002083e  mov     [rbp+57h+var_C0], rcx
0x180020842  mov     r13d, 7
0x180020848  mov     [rcx+18h], r13
0x18002084c  xor     r14d, r14d
0x18002084f  mov     [rcx+10h], r14
0x180020853  mov     [rcx], r14w
0x180020857  lea     r15, ?g_SyncLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection g_SyncLock
0x18002085e  mov     rcx, r15; lpCriticalSection
0x180020861  call    cs:__imp_EnterCriticalSection
0x180020867  mov     [rbp+57h+var_B8], r15
0x18002086b  xor     r8d, r8d
0x18002086e  lea     rdx, dword_180028204; Src
0x180020875  mov     rcx, rbx; void *
0x180020878  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002087d  mov     dword ptr [rbx+20h], 1
0x180020884  mov     [rbx+28h], r14
0x180020888  mov     [rbp+57h+var_88], r13
0x18002088c  mov     [rbp+57h+var_90], r14
0x180020890  mov     word ptr [rbp+57h+var_A0], r14w
0x180020895  or      r15, 0FFFFFFFFFFFFFFFFh
0x180020899  cmp     [rdi], r14w
0x18002089d  jnz     short loc_1800208A4
0x18002089f  mov     r8d, r14d
0x1800208a2  jmp     short loc_1800208B1
0x1800208a4  mov     r8, r15
0x1800208a7  inc     r8
0x1800208aa  cmp     [rdi+r8*2], r14w
0x1800208af  jnz     short loc_1800208A7
0x1800208b1  mov     rdx, rdi; Src
0x1800208b4  lea     rcx, [rbp+57h+var_A0]; void *
0x1800208b8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800208bd  mov     [rbp+57h+var_80], esi
0x1800208c0  lea     r8, [rbp+57h+var_A0]
0x1800208c4  lea     rdx, [rbp+57h+var_B0]
0x1800208c8  call    ?find@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@2@AEBUtagSFILENAMEwithATTRIBUTE@@@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::find(tagSFILENAMEwithATTRIBUTE const &)
0x1800208cd  mov     rax, [rax]
0x1800208d0  cmp     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800208d7  jnz     loc_1800209AE
0x1800208dd  mov     [rbp+57h+var_D0], r14
0x1800208e1  test    esi, esi
0x1800208e3  jz      loc_1800209DF
0x1800208e9  mov     rcx, rdi; lpFileName
0x1800208ec  call    cs:__imp_GetFileAttributesW
0x1800208f2  cmp     eax, 0FFFFFFFFh
0x1800208f5  jz      loc_1800209DF
0x1800208fb  xor     edx, edx; hFile
0x1800208fd  lea     r8d, [rdx+2]; dwFlags
0x180020901  mov     rcx, rdi; lpLibFileName
0x180020904  call    cs:__imp_LoadLibraryExW
0x18002090a  test    rax, rax
0x18002090d  jz      loc_1800209DF
0x180020913  mov     r8, rax; HINSTANCE
0x180020916  mov     rdx, rdi; unsigned __int16 *
0x180020919  lea     rcx, [rbp+57h+var_D0]; struct CommonFileMappingRawBase **
0x18002091d  call    ?CreateInstance@CommonFileMappingRawPEWrapped@@SAJPEAPEAVCommonFileMappingRawBase@@PEBGPEAUHINSTANCE__@@@Z; CommonFileMappingRawPEWrapped::CreateInstance(CommonFileMappingRawBase * *,ushort const *,HINSTANCE__ *)
0x180020922  mov     rdi, [rbp+57h+var_D0]
0x180020926  test    rdi, rdi
0x180020929  jz      loc_1800209DF
0x18002092f  mov     [rbp+57h+var_60], r13
0x180020933  mov     [rbp+57h+var_68], r14
0x180020937  mov     word ptr [rbp+57h+var_78], r14w
0x18002093c  mov     r9, r15
0x18002093f  xor     r8d, r8d
0x180020942  lea     rdx, [rbp+57h+var_A0]
0x180020946  lea     rcx, [rbp+57h+var_78]; void *
0x18002094a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002094f  mov     eax, [rbp+57h+var_80]
0x180020952  mov     [rbp+57h+var_58], eax
0x180020955  mov     [rbp+57h+var_50], rdi
0x180020959  mov     [rbp+57h+var_48], 1
0x180020960  mov     eax, [rbp+57h+var_A4]
0x180020963  mov     [rbp+57h+var_44], eax
0x180020966  lea     rdx, [rbp+57h+var_78]
0x18002096a  call    ??$_Buynode@U?$pair@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@?$_Tree_buy@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@1@$$QEAU?$pair@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@1@@Z; std::_Tree_buy<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>::_Buynode<std::pair<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>>>(std::pair<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> &&)
0x18002096f  lea     r9, [rax+20h]
0x180020973  mov     [rsp+100h+var_E0], rax
0x180020978  lea     rdx, [rbp+57h+var_D0]
0x18002097c  call    ??$_Insert_nohint@AEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Insert_nohint<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *>(bool,std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>> &,std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)
0x180020981  nop
0x180020982  cmp     [rbp+57h+var_60], 8
0x180020987  jb      short loc_180020993
0x180020989  mov     rcx, [rbp+57h+var_78]
0x18002098d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020993  lea     r8, [rbp+57h+var_A0]
0x180020997  lea     rdx, [rbp+57h+var_D0]
0x18002099b  call    ?find@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@2@AEBUtagSFILENAMEwithATTRIBUTE@@@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::find(tagSFILENAMEwithATTRIBUTE const &)
0x1800209a0  mov     rax, [rax]
0x1800209a3  cmp     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800209aa  jnz     short loc_1800209B1
0x1800209ac  jmp     short loc_1800209DF
0x1800209ae  inc     dword ptr [rax+50h]
0x1800209b1  mov     rcx, [rax+48h]
0x1800209b5  mov     [rbx+28h], rcx
0x1800209b9  test    rcx, rcx
0x1800209bc  jz      short loc_1800209DF
0x1800209be  lea     rax, [rbp+57h+var_A0]
0x1800209c2  cmp     rbx, rax
0x1800209c5  jz      short loc_1800209D9
0x1800209c7  mov     r9, r15
0x1800209ca  xor     r8d, r8d
0x1800209cd  lea     rdx, [rbp+57h+var_A0]
0x1800209d1  mov     rcx, rbx; void *
0x1800209d4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800209d9  mov     eax, [rbp+57h+var_80]
0x1800209dc  mov     [rbx+20h], eax
0x1800209df  cmp     [rbp+57h+var_88], 8
0x1800209e4  jb      short loc_1800209F0
0x1800209e6  mov     rcx, [rbp+57h+var_A0]
0x1800209ea  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800209f0  mov     [rbp+57h+var_88], r13
0x1800209f4  mov     [rbp+57h+var_90], r14
0x1800209f8  mov     word ptr [rbp+57h+var_A0], r14w
0x1800209fd  lea     rcx, ?g_SyncLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x180020a04  call    cs:__imp_LeaveCriticalSection
0x180020a0a  nop
0x180020a0b  mov     rax, rbx
0x180020a0e  mov     rcx, [rbp+57h+var_40]
0x180020a12  xor     rcx, rsp; StackCookie
0x180020a15  call    __security_check_cookie
0x180020a1a  add     rsp, 0D0h
0x180020a21  pop     r15
0x180020a23  pop     r14
0x180020a25  pop     r13
0x180020a27  pop     rdi
0x180020a28  pop     rsi
0x180020a29  pop     rbx
0x180020a2a  pop     rbp
0x180020a2b  retn
```
