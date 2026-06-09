# Execution::ActivationManagerShim::IsNonSystemVolumeApp(ushort const *,bool &)

- ea: `0x18006f2f4`
- end: `0x18006f477`
- name: `?IsNonSystemVolumeApp@ActivationManagerShim@Execution@@CAJPEBGAEA_N@Z`
- size: `387`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180029270`

## callees

- `0x18000b5c0`
- `0x18002c900`
- `0x18002d5e0`
- `0x180037d38`
- `0x18006f2f4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18006f334`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18006f334`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006f386`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006f42e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006f457`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006f386`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006f42e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18006f457`

## string_xrefs

- `0x18006f34d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall Execution::ActivationManagerShim::IsNonSystemVolumeApp(const unsigned __int16 *a1, bool *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // [rsp+20h] [rbp-59h]
  int v11; // [rsp+20h] [rbp-59h]
  __int64 *v12; // [rsp+30h] [rbp-49h] BYREF
  __int64 v13; // [rsp+38h] [rbp-41h] BYREF
  char v14; // [rsp+40h] [rbp-39h]
  __int128 v15; // [rsp+50h] [rbp-29h] BYREF
  __int64 v16; // [rsp+60h] [rbp-19h]
  __int128 v17; // [rsp+68h] [rbp-11h]
  __int64 v18; // [rsp+78h] [rbp-1h]
  __int64 v19; // [rsp+80h] [rbp+7h]
  __int64 v20; // [rsp+88h] [rbp+Fh]
  __int128 v21; // [rsp+90h] [rbp+17h]
  int v22; // [rsp+A0h] [rbp+27h]
  __int64 v23; // [rsp+A8h] [rbp+2Fh]
  __int64 v24; // [rsp+B0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  int v26; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+F0h] [rbp+77h] BYREF

  v14 = 1;
  *a2 = 0;
  v27 = 0;
  v12 = &v27;
  v13 = 0;
  v4 = SRCacheManager_Open(0, &v13);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v12);
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)v4,
      v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6ED,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)v4,
      v11);
LABEL_3:
    v5 = v27;
    v27 = 0;
    if ( v5 )
      SRCacheManager_Close();
    return v4;
  }
  v16 = 0;
  v15 = 0;
  v21 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v17 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  LOBYTE(v26) = 0;
  v7 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(&v27, a1, 64, &v15);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F2,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v7,
      (int)&v26);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v15);
    goto LABEL_3;
  }
  if ( (_BYTE)v26 )
  {
    *a2 = v18 != 1;
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v15);
    v9 = v27;
    v27 = 0;
    if ( v9 )
      SRCacheManager_Close();
    return 0;
  }
  else
  {
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v15);
    v8 = v27;
    v27 = 0;
    if ( v8 )
      SRCacheManager_Close();
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x18006f2f4  mov     [rsp-8+arg_0], rbx
0x18006f2f9  mov     [rsp-8+arg_18], rsi
0x18006f2fe  push    rbp
0x18006f2ff  push    rdi
0x18006f300  push    r14
0x18006f302  lea     rbp, [rsp-47h]
0x18006f307  sub     rsp, 0C0h
0x18006f30e  xor     r14d, r14d
0x18006f311  mov     [rbp+57h+var_90], 1
0x18006f315  mov     [rdx], r14b
0x18006f318  lea     rax, [rbp+57h+arg_10]
0x18006f31c  mov     rdi, rdx
0x18006f31f  mov     [rbp+57h+arg_10], r14
0x18006f323  mov     rsi, rcx
0x18006f326  mov     [rbp+57h+var_A0], rax
0x18006f32a  lea     rdx, [rbp+57h+var_98]
0x18006f32e  mov     [rbp+57h+var_98], r14
0x18006f332  xor     ecx, ecx
0x18006f334  call    cs:__imp_SRCacheManager_Open
0x18006f33a  lea     rcx, [rbp+57h+var_A0]
0x18006f33e  mov     ebx, eax
0x18006f340  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18006f345  test    ebx, ebx
0x18006f347  jns     short loc_18006F393
0x18006f349  mov     rcx, [rbp+5Fh]; this
0x18006f34d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006f354  mov     r9d, ebx; char *
0x18006f357  mov     edx, 0A5h; void *
0x18006f35c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f361  mov     rcx, [rbp+5Fh]; this
0x18006f365  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006f36c  mov     r9d, ebx; char *
0x18006f36f  mov     edx, 6EDh; void *
0x18006f374  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f379  mov     rcx, [rbp+57h+arg_10]
0x18006f37d  mov     [rbp+57h+arg_10], r14
0x18006f381  test    rcx, rcx
0x18006f384  jz      short loc_18006F38C
0x18006f386  call    cs:__imp_SRCacheManager_Close
0x18006f38c  mov     eax, ebx
0x18006f38e  jmp     loc_18006F45F
0x18006f393  xorps   xmm0, xmm0
0x18006f396  mov     [rbp+57h+var_70], r14
0x18006f39a  xorps   xmm1, xmm1
0x18006f39d  movdqa  [rbp+57h+var_80], xmm0
0x18006f3a2  lea     rax, [rbp+57h+arg_8]
0x18006f3a6  movdqa  [rbp+57h+var_40], xmm0
0x18006f3ab  lea     r9, [rbp+57h+var_80]
0x18006f3af  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18006f3b4  mov     r8d, 40h ; '@'
0x18006f3ba  mov     [rbp+57h+var_58], r14
0x18006f3be  mov     rdx, rsi
0x18006f3c1  mov     [rbp+57h+var_50], r14
0x18006f3c5  lea     rcx, [rbp+57h+arg_10]
0x18006f3c9  mov     [rbp+57h+var_48], r14
0x18006f3cd  movups  [rbp+57h+var_68], xmm1
0x18006f3d1  mov     [rbp+57h+var_30], r14d
0x18006f3d5  mov     [rbp+57h+var_28], r14
0x18006f3d9  mov     [rbp+57h+var_20], r14
0x18006f3dd  mov     byte ptr [rbp+57h+arg_8], r14b
0x18006f3e1  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18006f3e6  mov     ebx, eax
0x18006f3e8  test    eax, eax
0x18006f3ea  jns     short loc_18006F412
0x18006f3ec  mov     rcx, [rbp+5Fh]; this
0x18006f3f0  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006f3f7  mov     r9d, eax; char *
0x18006f3fa  mov     edx, 6F2h; void *
0x18006f3ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f404  lea     rcx, [rbp+57h+var_80]; this
0x18006f408  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006f40d  jmp     loc_18006F379
0x18006f412  lea     rcx, [rbp+57h+var_80]; this
0x18006f416  cmp     byte ptr [rbp+57h+arg_8], r14b
0x18006f41a  jnz     short loc_18006F43B
0x18006f41c  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006f421  mov     rcx, [rbp+57h+arg_10]
0x18006f425  mov     [rbp+57h+arg_10], r14
0x18006f429  test    rcx, rcx
0x18006f42c  jz      short loc_18006F434
0x18006f42e  call    cs:__imp_SRCacheManager_Close
0x18006f434  mov     eax, 80070002h
0x18006f439  jmp     short loc_18006F45F
0x18006f43b  cmp     [rbp+57h+var_58], 1
0x18006f440  setnz   al
0x18006f443  mov     [rdi], al
0x18006f445  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18006f44a  mov     rcx, [rbp+57h+arg_10]
0x18006f44e  mov     [rbp+57h+arg_10], r14
0x18006f452  test    rcx, rcx
0x18006f455  jz      short loc_18006F45D
0x18006f457  call    cs:__imp_SRCacheManager_Close
0x18006f45d  xor     eax, eax
0x18006f45f  lea     r11, [rsp+0D0h+var_10]
0x18006f467  mov     rbx, [r11+20h]
0x18006f46b  mov     rsi, [r11+38h]
0x18006f46f  mov     rsp, r11
0x18006f472  pop     r14
0x18006f474  pop     rdi
0x18006f475  pop     rbp
0x18006f476  retn
```
