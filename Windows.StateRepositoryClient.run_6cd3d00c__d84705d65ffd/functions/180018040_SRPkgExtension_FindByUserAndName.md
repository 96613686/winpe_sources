# SRPkgExtension_FindByUserAndName

- ea: `0x180018040`
- end: `0x180018178`
- name: `SRPkgExtension_FindByUserAndName`
- size: `312`
- prototype: `__int64 __fastcall(PSID pSid1, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800029b0`
- `0x180003630`
- `0x1800075e4`
- `0x1800094a4`
- `0x180016b3c`
- `0x180016d78`
- `0x180017168`
- `0x180018040`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800180bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800180bb`

## string_xrefs

- `0x1800180d6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Manager.hpp`
- `0x1800180ef`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_pkgextension.cpp`
- `0x18001812e`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_pkgextension.cpp`
- `0x180018152`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_pkgextension.cpp`

## pseudocode

```c
__int64 __fastcall SRPkgExtension_FindByUserAndName(
        PSID pSid1,
        unsigned __int16 *a2,
        SRPkgExtensionIteratorContext **a3)
{
  SRPkgExtensionIteratorContext *v6; // rax
  SRPkgExtensionIteratorContext *v7; // rbx
  SRPkgExtensionIteratorContext *v8; // rax
  SRPkgExtensionIteratorContext *v9; // rbx
  unsigned int v10; // edi
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // edx
  int v16[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v17; // [rsp+28h] [rbp-40h] BYREF
  char v18; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a3 = 0;
  v6 = (SRPkgExtensionIteratorContext *)operator new(0x200u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6
    && (memset_0(v6, 0, 0x200u), v8 = SRPkgExtensionIteratorContext::SRPkgExtensionIteratorContext(v7), (v9 = v8) != 0) )
  {
    if ( !*(_QWORD *)v8 )
    {
      *(_QWORD *)v16 = v8;
      v17 = 0;
      v18 = 1;
      v10 = SRCacheManager_Open(0, &v17);
      wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(v16);
      if ( (v10 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Manager.hpp",
          (const char *)v10,
          v16[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_pkgextension.cpp",
          (const char *)v10,
          v16[0]);
        v11 = v10;
        v12 = 215;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_pkgextension.cpp",
          (const char *)v11,
          v16[0]);
        SRPkgExtensionIteratorContext::`scalar deleting destructor'(v9, v14);
        return v10;
      }
    }
    v13 = SRPkgExtensionIteratorContext::FindByUserAndName(v9, pSid1, a2);
    v10 = v13;
    if ( v13 < 0 )
    {
      v11 = (unsigned int)v13;
      v12 = 216;
      goto LABEL_8;
    }
    *a3 = v9;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_pkgextension.cpp",
      (const char *)0x8007000ELL,
      v16[0]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180018040  push    rbx
0x180018042  push    rbp
0x180018043  push    rsi
0x180018044  push    rdi
0x180018045  push    r14
0x180018047  sub     rsp, 40h
0x18001804b  mov     rbp, rdx
0x18001804e  mov     qword ptr [r8], 0
0x180018055  mov     r14, rcx
0x180018058  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001805f  mov     edi, 200h
0x180018064  mov     rsi, r8
0x180018067  mov     ecx, edi; unsigned __int64
0x180018069  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001806e  mov     rbx, rax
0x180018071  test    rax, rax
0x180018074  jz      loc_18001814D
0x18001807a  mov     r8d, edi; Size
0x18001807d  xor     edx, edx; Val
0x18001807f  mov     rcx, rax; void *
0x180018082  call    memset_0
0x180018087  mov     rcx, rbx; this
0x18001808a  call    ??0SRPkgExtensionIteratorContext@@QEAA@XZ; SRPkgExtensionIteratorContext::SRPkgExtensionIteratorContext(void)
0x18001808f  mov     rbx, rax
0x180018092  test    rax, rax
0x180018095  jz      loc_18001814D
0x18001809b  cmp     qword ptr [rax], 0
0x18001809f  jnz     short loc_18001810D
0x1800180a1  lea     rdx, [rsp+68h+var_40]
0x1800180a6  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800180ab  xor     ecx, ecx
0x1800180ad  mov     [rsp+68h+var_40], 0
0x1800180b6  mov     [rsp+68h+var_38], 1
0x1800180bb  call    cs:__imp_SRCacheManager_Open
0x1800180c1  lea     rcx, [rsp+68h+var_48]
0x1800180c6  mov     edi, eax
0x1800180c8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1800180cd  test    edi, edi
0x1800180cf  jns     short loc_18001810D
0x1800180d1  mov     rcx, [rsp+68h]; this
0x1800180d6  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\StateRepositor"...
0x1800180dd  mov     r9d, edi; char *
0x1800180e0  mov     edx, 0A5h; void *
0x1800180e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800180ea  mov     rcx, [rsp+68h]; this
0x1800180ef  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x1800180f6  mov     r9d, edi; char *
0x1800180f9  mov     edx, 2Eh ; '.'; void *
0x1800180fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018103  mov     r9d, edi
0x180018106  mov     edx, 0D7h
0x18001810b  jmp     short loc_180018129
0x18001810d  mov     r8, rbp; unsigned __int16 *
0x180018110  mov     rdx, r14; pSid1
0x180018113  mov     rcx, rbx; this
0x180018116  call    ?FindByUserAndName@SRPkgExtensionIteratorContext@@QEAAJPEAXPEBG@Z; SRPkgExtensionIteratorContext::FindByUserAndName(void *,ushort const *)
0x18001811b  mov     edi, eax
0x18001811d  test    eax, eax
0x18001811f  jns     short loc_180018146
0x180018121  mov     r9d, eax; char *
0x180018124  mov     edx, 0D8h; void *
0x180018129  mov     rcx, [rsp+68h]; this
0x18001812e  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x180018135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001813a  mov     rcx, rbx; this
0x18001813d  call    ??_GSRPkgExtensionIteratorContext@@QEAAPEAXI@Z; SRPkgExtensionIteratorContext::`scalar deleting destructor'(uint)
0x180018142  mov     eax, edi
0x180018144  jmp     short loc_18001816D
0x180018146  mov     [rsi], rbx
0x180018149  xor     eax, eax
0x18001814b  jmp     short loc_18001816D
0x18001814d  mov     rcx, [rsp+68h]; this
0x180018152  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x180018159  mov     ebx, 8007000Eh
0x18001815e  mov     edx, 0D6h; void *
0x180018163  mov     r9d, ebx; char *
0x180018166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001816b  mov     eax, ebx
0x18001816d  add     rsp, 40h
0x180018171  pop     r14
0x180018173  pop     rdi
0x180018174  pop     rsi
0x180018175  pop     rbp
0x180018176  pop     rbx
0x180018177  retn
```
