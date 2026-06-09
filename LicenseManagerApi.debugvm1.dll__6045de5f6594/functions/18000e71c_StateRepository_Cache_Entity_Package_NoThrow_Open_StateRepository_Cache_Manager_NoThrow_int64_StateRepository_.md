# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18000e71c`
- end: `0x18000e919`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `509`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000eaec`

## callees

- `0x180001960`
- `0x1800022ea`
- `0x1800052a8`
- `0x180006ddc`
- `0x18000e678`
- `0x18000e71c`
- `0x18000e920`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000e806`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000e806`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000e79d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000e8f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000e79d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000e8f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e869`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e8dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e869`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e8dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000e8a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000e8a4`

## string_xrefs

- `0x18000e815`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000e8b3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e77f`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000e84a`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  int v7; // ebx
  int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12; // r9d
  int v13; // r9d
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // r9d
  __int64 v18; // rcx
  __int64 v19; // rcx
  bool v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+238h] [rbp+138h]
  __int64 v25; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v26; // [rsp+248h] [rbp+148h]
  unsigned __int16 v27[20]; // [rsp+250h] [rbp+150h] BYREF

  v21 = 0;
  v20 = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v21,
         a1,
         L"Package\\Data",
         &v20);
  if ( v7 < 0 )
  {
    v9 = 1192;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (wil::details *)(unsigned int)v7,
      v8);
LABEL_4:
    v10 = v21;
    v21 = 0;
    if ( v10 )
      SRCacheContext_Close();
    return (unsigned int)v7;
  }
  if ( !v20 )
  {
    v7 = -2140733422;
    v9 = 1193;
    goto LABEL_3;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 256;
  v26 = (unsigned __int16 *)v23;
  if ( (unsigned int)_o__ui64tow_s(a2, v27, 17) )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (wil::details *)0x8000FFFFLL,
      v12);
LABEL_12:
    v14 = 1196;
    goto LABEL_13;
  }
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, v27);
  if ( v7 < 0 )
    goto LABEL_12;
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
         a3,
         (struct StateRepository::Cache::Context_NoThrow *)&v21,
         v26,
         a4);
  if ( v7 < 0 )
  {
    v14 = 1197;
    goto LABEL_13;
  }
  v16 = SRCacheContext_AddToCache(v21, L"Package\\Data");
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (wil::details *)(unsigned int)v16,
      v17);
    v14 = 1199;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (wil::details *)(unsigned int)v7,
      v13);
    v15 = v22;
    v22 = 0;
    if ( v15 )
      SRCache_Free();
    goto LABEL_4;
  }
  v18 = v22;
  v22 = 0;
  if ( v18 )
    SRCache_Free();
  v19 = v21;
  v21 = 0;
  if ( v19 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18000e71c  push    rbp
0x18000e71e  push    rbx
0x18000e71f  push    rsi
0x18000e720  push    rdi
0x18000e721  push    r14
0x18000e723  push    r15
0x18000e725  lea     rbp, [rsp-188h]
0x18000e72d  sub     rsp, 288h
0x18000e734  mov     rax, cs:__security_cookie
0x18000e73b  xor     rax, rsp
0x18000e73e  mov     [rbp+1B0h+var_38], rax
0x18000e745  mov     r14, rdx
0x18000e748  mov     rsi, r9
0x18000e74b  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18000e74e  lea     r9, [rsp+2B0h+var_290]; bool *
0x18000e753  mov     rdi, r8
0x18000e756  lea     rcx, [rsp+2B0h+var_288]; this
0x18000e75b  xor     r15d, r15d
0x18000e75e  lea     r8, aPackageData; "Package\\Data"
0x18000e765  mov     [rsp+2B0h+var_288], r15
0x18000e76a  mov     [rsp+2B0h+var_290], r15b
0x18000e76f  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18000e774  mov     ebx, eax
0x18000e776  test    eax, eax
0x18000e778  jns     short loc_18000E7AA
0x18000e77a  mov     ecx, 4A8h; this
0x18000e77f  lea     rdx, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e786  mov     r8d, ebx; wil::details *
0x18000e789  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000e78e  mov     rcx, [rsp+2B0h+var_288]
0x18000e793  mov     [rsp+2B0h+var_288], r15
0x18000e798  test    rcx, rcx
0x18000e79b  jz      short loc_18000E7A3
0x18000e79d  call    cs:__imp_SRCacheContext_Close
0x18000e7a3  mov     eax, ebx
0x18000e7a5  jmp     loc_18000E8FA
0x18000e7aa  cmp     [rsp+2B0h+var_290], r15b
0x18000e7af  jnz     short loc_18000E7BD
0x18000e7b1  mov     ebx, 80670012h
0x18000e7b6  mov     ecx, 4A9h
0x18000e7bb  jmp     short loc_18000E77F
0x18000e7bd  xor     edx, edx; Val
0x18000e7bf  mov     [rsp+2B0h+var_280], r15
0x18000e7c4  mov     r8d, 200h; Size
0x18000e7ca  lea     rcx, [rsp+2B0h+var_278]; void *
0x18000e7cf  call    memset_0
0x18000e7d4  mov     r9d, 10h
0x18000e7da  mov     [rbp+1B0h+var_78], r15
0x18000e7e1  lea     rax, [rsp+2B0h+var_278]
0x18000e7e6  mov     [rbp+1B0h+var_70], 100h
0x18000e7f1  lea     rdx, [rbp+1B0h+var_60]
0x18000e7f8  mov     [rbp+1B0h+var_68], rax
0x18000e7ff  mov     rcx, r14
0x18000e802  lea     r8d, [r9+1]
0x18000e806  call    cs:__imp__o__ui64tow_s
0x18000e80c  test    eax, eax
0x18000e80e  jz      short loc_18000E82B
0x18000e810  mov     ebx, 8000FFFFh
0x18000e815  lea     rdx, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e81c  mov     r8d, ebx; wil::details *
0x18000e81f  mov     ecx, 166h; this
0x18000e824  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000e829  jmp     short loc_18000E842
0x18000e82b  lea     rdx, [rbp+1B0h+var_60]; unsigned __int16 *
0x18000e832  lea     rcx, [rsp+2B0h+var_280]; this
0x18000e837  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000e83c  mov     ebx, eax
0x18000e83e  test    eax, eax
0x18000e840  jns     short loc_18000E874
0x18000e842  mov     ecx, 4ACh; this
0x18000e847  mov     r8d, ebx; wil::details *
0x18000e84a  lea     rdx, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e851  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000e856  mov     rcx, [rsp+2B0h+var_280]
0x18000e85b  mov     [rsp+2B0h+var_280], r15
0x18000e860  test    rcx, rcx
0x18000e863  jz      loc_18000E78E
0x18000e869  call    cs:__imp_SRCache_Free
0x18000e86f  jmp     loc_18000E78E
0x18000e874  mov     r8, [rbp+1B0h+var_68]; unsigned __int16 *
0x18000e87b  lea     rdx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x18000e880  mov     r9, rsi; bool *
0x18000e883  mov     rcx, rdi; this
0x18000e886  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)
0x18000e88b  mov     ebx, eax
0x18000e88d  test    eax, eax
0x18000e88f  jns     short loc_18000E898
0x18000e891  mov     ecx, 4ADh
0x18000e896  jmp     short loc_18000E847
0x18000e898  mov     rcx, [rsp+2B0h+var_288]
0x18000e89d  lea     rdx, aPackageData; "Package\\Data"
0x18000e8a4  call    cs:__imp_SRCacheContext_AddToCache
0x18000e8aa  mov     ebx, eax
0x18000e8ac  test    eax, eax
0x18000e8ae  jns     short loc_18000E8CE
0x18000e8b0  mov     r8d, eax; wil::details *
0x18000e8b3  lea     rdx, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e8ba  mov     ecx, 1A6h; this
0x18000e8bf  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000e8c4  mov     ecx, 4AFh
0x18000e8c9  jmp     loc_18000E847
0x18000e8ce  mov     rcx, [rsp+2B0h+var_280]
0x18000e8d3  mov     [rsp+2B0h+var_280], r15
0x18000e8d8  test    rcx, rcx
0x18000e8db  jz      short loc_18000E8E3
0x18000e8dd  call    cs:__imp_SRCache_Free
0x18000e8e3  mov     rcx, [rsp+2B0h+var_288]
0x18000e8e8  mov     [rsp+2B0h+var_288], r15
0x18000e8ed  test    rcx, rcx
0x18000e8f0  jz      short loc_18000E8F8
0x18000e8f2  call    cs:__imp_SRCacheContext_Close
0x18000e8f8  xor     eax, eax
0x18000e8fa  mov     rcx, [rbp+1B0h+var_38]
0x18000e901  xor     rcx, rsp; StackCookie
0x18000e904  call    __security_check_cookie
0x18000e909  add     rsp, 288h
0x18000e910  pop     r15
0x18000e912  pop     r14
0x18000e914  pop     rdi
0x18000e915  pop     rsi
0x18000e916  pop     rbx
0x18000e917  pop     rbp
0x18000e918  retn
```
