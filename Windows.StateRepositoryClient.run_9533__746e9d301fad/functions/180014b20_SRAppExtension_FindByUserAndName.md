# SRAppExtension_FindByUserAndName

- ea: `0x180014b20`
- end: `0x180014c58`
- name: `SRAppExtension_FindByUserAndName`
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
- `0x180011f54`
- `0x180012420`
- `0x180012adc`
- `0x180014b20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180014b9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180014b9b`

## string_xrefs

- `0x180014bb6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Manager.hpp`
- `0x180014bcf`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_appextension.cpp`
- `0x180014c0e`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_appextension.cpp`
- `0x180014c32`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_appextension.cpp`

## pseudocode

```c
__int64 __fastcall SRAppExtension_FindByUserAndName(
        PSID pSid1,
        unsigned __int16 *a2,
        SRAppExtensionIteratorContext **a3)
{
  SRAppExtensionIteratorContext *v6; // rax
  SRAppExtensionIteratorContext *v7; // rbx
  SRAppExtensionIteratorContext *v8; // rax
  SRAppExtensionIteratorContext *v9; // rbx
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
  v6 = (SRAppExtensionIteratorContext *)operator new(0x270u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6
    && (memset_0(v6, 0, 0x270u), v8 = SRAppExtensionIteratorContext::SRAppExtensionIteratorContext(v7), (v9 = v8) != 0) )
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
          (void *)0x2F,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_appextension.cpp",
          (const char *)v10,
          v16[0]);
        v11 = v10;
        v12 = 225;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_appextension.cpp",
          (const char *)v11,
          v16[0]);
        SRAppExtensionIteratorContext::`scalar deleting destructor'(v9, v14);
        return v10;
      }
    }
    v13 = SRAppExtensionIteratorContext::FindByUserAndName(v9, pSid1, a2);
    v10 = v13;
    if ( v13 < 0 )
    {
      v11 = (unsigned int)v13;
      v12 = 226;
      goto LABEL_8;
    }
    *a3 = v9;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_appextension.cpp",
      (const char *)0x8007000ELL,
      v16[0]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180014b20  push    rbx
0x180014b22  push    rbp
0x180014b23  push    rsi
0x180014b24  push    rdi
0x180014b25  push    r14
0x180014b27  sub     rsp, 40h
0x180014b2b  mov     rbp, rdx
0x180014b2e  mov     qword ptr [r8], 0
0x180014b35  mov     r14, rcx
0x180014b38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014b3f  mov     edi, 270h
0x180014b44  mov     rsi, r8
0x180014b47  mov     ecx, edi; unsigned __int64
0x180014b49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014b4e  mov     rbx, rax
0x180014b51  test    rax, rax
0x180014b54  jz      loc_180014C2D
0x180014b5a  mov     r8d, edi; Size
0x180014b5d  xor     edx, edx; Val
0x180014b5f  mov     rcx, rax; void *
0x180014b62  call    memset_0
0x180014b67  mov     rcx, rbx; this
0x180014b6a  call    ??0SRAppExtensionIteratorContext@@QEAA@XZ; SRAppExtensionIteratorContext::SRAppExtensionIteratorContext(void)
0x180014b6f  mov     rbx, rax
0x180014b72  test    rax, rax
0x180014b75  jz      loc_180014C2D
0x180014b7b  cmp     qword ptr [rax], 0
0x180014b7f  jnz     short loc_180014BED
0x180014b81  lea     rdx, [rsp+68h+var_40]
0x180014b86  mov     qword ptr [rsp+68h+var_48], rax; int
0x180014b8b  xor     ecx, ecx
0x180014b8d  mov     [rsp+68h+var_40], 0
0x180014b96  mov     [rsp+68h+var_38], 1
0x180014b9b  call    cs:__imp_SRCacheManager_Open
0x180014ba1  lea     rcx, [rsp+68h+var_48]
0x180014ba6  mov     edi, eax
0x180014ba8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180014bad  test    edi, edi
0x180014baf  jns     short loc_180014BED
0x180014bb1  mov     rcx, [rsp+68h]; this
0x180014bb6  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\StateRepositor"...
0x180014bbd  mov     r9d, edi; char *
0x180014bc0  mov     edx, 0A5h; void *
0x180014bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014bca  mov     rcx, [rsp+68h]; this
0x180014bcf  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180014bd6  mov     r9d, edi; char *
0x180014bd9  mov     edx, 2Fh ; '/'; void *
0x180014bde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014be3  mov     r9d, edi
0x180014be6  mov     edx, 0E1h
0x180014beb  jmp     short loc_180014C09
0x180014bed  mov     r8, rbp; unsigned __int16 *
0x180014bf0  mov     rdx, r14; pSid1
0x180014bf3  mov     rcx, rbx; this
0x180014bf6  call    ?FindByUserAndName@SRAppExtensionIteratorContext@@QEAAJPEAXPEBG@Z; SRAppExtensionIteratorContext::FindByUserAndName(void *,ushort const *)
0x180014bfb  mov     edi, eax
0x180014bfd  test    eax, eax
0x180014bff  jns     short loc_180014C26
0x180014c01  mov     r9d, eax; char *
0x180014c04  mov     edx, 0E2h; void *
0x180014c09  mov     rcx, [rsp+68h]; this
0x180014c0e  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180014c15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c1a  mov     rcx, rbx; this
0x180014c1d  call    ??_GSRAppExtensionIteratorContext@@QEAAPEAXI@Z; SRAppExtensionIteratorContext::`scalar deleting destructor'(uint)
0x180014c22  mov     eax, edi
0x180014c24  jmp     short loc_180014C4D
0x180014c26  mov     [rsi], rbx
0x180014c29  xor     eax, eax
0x180014c2b  jmp     short loc_180014C4D
0x180014c2d  mov     rcx, [rsp+68h]; this
0x180014c32  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180014c39  mov     ebx, 8007000Eh
0x180014c3e  mov     edx, 0E0h; void *
0x180014c43  mov     r9d, ebx; char *
0x180014c46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c4b  mov     eax, ebx
0x180014c4d  add     rsp, 40h
0x180014c51  pop     r14
0x180014c53  pop     rdi
0x180014c54  pop     rsi
0x180014c55  pop     rbp
0x180014c56  pop     rbx
0x180014c57  retn
```
