# PluginEngine::PopulatePluginList(PluginEnumerator *)

- ea: `0x180025fc0`
- end: `0x18002620c`
- name: `?PopulatePluginList@PluginEngine@@MEAAJPEAVPluginEnumerator@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(PluginEngine *__hidden this, struct PluginEnumerator *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800034b8`
- `0x180004394`
- `0x180004a90`
- `0x1800087ec`
- `0x18000f534`
- `0x18001f920`
- `0x1800245c0`
- `0x180024d94`
- `0x180025fc0`
- `0x180027da0`
- `0x18002c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002608f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002616c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800261c7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800261eb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002608f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002616c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800261c7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800261eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800260ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800260ff`

## string_xrefs

- `0x18002600d`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026077`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026144`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PluginEngine::PopulatePluginList(PluginEngine *this, struct PluginEnumerator *a2)
{
  struct PluginEnumerator *v2; // rdi
  struct PluginEnumerator *v4; // rax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 result; // rax
  int v8; // eax
  const char *v9; // r9
  unsigned int v10; // r15d
  __int64 v11; // rax
  __int64 v12; // r12
  __int64 (__fastcall *v13)(_QWORD, _QWORD); // rax
  void *v14; // rbx
  int v15; // eax
  unsigned int v16; // ebx
  LPVOID v17; // rbx
  int v18; // [rsp+20h] [rbp-48h]
  struct PluginEnumerator *v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID pv; // [rsp+78h] [rbp+10h] BYREF
  char v22; // [rsp+80h] [rbp+18h] BYREF
  __int64 (__fastcall *v23)(_QWORD, _QWORD); // [rsp+88h] [rbp+20h]

  v2 = a2;
  if ( !a2 )
  {
    v4 = (struct PluginEnumerator *)operator new(8u, (const struct std::nothrow_t *)std::nothrow);
    v2 = v4;
    pv = v4;
    if ( !v4 )
    {
      v5 = -2147024882;
      v6 = 170;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)v5,
        v18);
      return v5;
    }
    *(_QWORD *)v4 = &PluginEnumerator::`vftable';
  }
  v5 = (*(__int64 (__fastcall **)(PluginEngine *))(*(_QWORD *)this + 96LL))(this);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 173;
    goto LABEL_5;
  }
  v19 = v2;
  v8 = (**(__int64 (__fastcall ***)(struct PluginEnumerator *, _QWORD, char *))v2)(
         v2,
         *((unsigned int *)this + 14),
         (char *)this + 8);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v8,
      (int)v2);
    *(_QWORD *)v2 = &PluginEnumerator::`vftable';
    operator delete(v2);
    return v5;
  }
  std::vector<std::wstring>::clear((char *)this + 32);
  v10 = 0;
  try
  {
    while ( v10 < (unsigned __int64)((__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 3) )
    {
      pv = 0;
      v11 = std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at((char *)this + 8);
      v12 = *(_QWORD *)v11;
      v13 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v11 + 24LL);
      v23 = v13;
      v14 = pv;
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v22);
        CoTaskMemFree(v14);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v22);
        v13 = v23;
      }
      pv = 0;
      v15 = v13(v12, &pv);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
          (const char *)(unsigned int)v15,
          (int)v2);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
        if ( v2 )
        {
          *(_QWORD *)v2 = &PluginEnumerator::`vftable';
          operator delete(v2);
        }
        return v16;
      }
      v17 = pv;
      if ( pv )
      {
        if ( *((_QWORD *)this + 5) == *((_QWORD *)this + 6) )
          std::vector<std::wstring>::_Reserve((char *)this + 32);
        std::wstring::wstring(*((_QWORD *)this + 5), v17);
        *((_QWORD *)this + 5) += 32LL;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
      ++v10;
    }
    if ( v2 )
    {
      *(_QWORD *)v2 = &PluginEnumerator::`vftable';
      operator delete(v2);
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(pv) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0xBF,
                    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                    v9);
    if ( v19 )
    {
      *(_QWORD *)v19 = &PluginEnumerator::`vftable';
      operator delete(v19);
    }
    return (unsigned int)pv;
  }
  return result;
}

```

## disassembly

```asm
0x180025fc0  push    rbx
0x180025fc2  push    rsi
0x180025fc3  push    rdi
0x180025fc4  push    r12
0x180025fc6  push    r13
0x180025fc8  push    r14
0x180025fca  push    r15
0x180025fcc  sub     rsp, 30h
0x180025fd0  mov     rdi, rdx
0x180025fd3  mov     r14, rcx
0x180025fd6  test    rdx, rdx
0x180025fd9  jnz     short loc_180026028
0x180025fdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025fe2  lea     ecx, [rdi+8]; unsigned __int64
0x180025fe5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025fea  mov     rdi, rax
0x180025fed  mov     [rsp+68h+pv], rax
0x180025ff2  test    rax, rax
0x180025ff5  jz      short loc_180026003
0x180025ff7  lea     rsi, ??_7PluginEnumerator@@6B@; const PluginEnumerator::`vftable'
0x180025ffe  mov     [rax], rsi
0x180026001  jmp     short loc_18002602F
0x180026003  mov     ebx, 8007000Eh
0x180026008  mov     edx, 0AAh; void *
0x18002600d  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026014  mov     r9d, ebx; char *
0x180026017  mov     rcx, [rsp+68h]; this
0x18002601c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026021  mov     eax, ebx
0x180026023  jmp     loc_1800261FB
0x180026028  lea     rsi, ??_7PluginEnumerator@@6B@; const PluginEnumerator::`vftable'
0x18002602f  mov     rax, [r14]
0x180026032  mov     rcx, r14
0x180026035  mov     rax, [rax+60h]
0x180026039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002603e  mov     ebx, eax
0x180026040  test    eax, eax
0x180026042  jns     short loc_18002604B
0x180026044  mov     edx, 0ADh
0x180026049  jmp     short loc_18002600D
0x18002604b  mov     qword ptr [rsp+68h+var_48], rdi; int
0x180026050  lea     r13, [r14+8]
0x180026054  mov     rax, [rdi]
0x180026057  mov     r8, r13
0x18002605a  mov     edx, [r14+38h]
0x18002605e  mov     rcx, rdi
0x180026061  mov     rax, [rax]
0x180026064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026069  mov     ebx, eax
0x18002606b  test    eax, eax
0x18002606d  jns     short loc_18002609D
0x18002606f  mov     rcx, [rsp+68h]; this
0x180026074  mov     r9d, eax; char *
0x180026077  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002607e  mov     edx, 0AFh; void *
0x180026083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026088  nop
0x180026089  mov     [rdi], rsi
0x18002608c  mov     rcx, rdi
0x18002608f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026096  nop     dword ptr [rax+rax+00h]
0x18002609b  jmp     short loc_180026021
0x18002609d  lea     rcx, [r14+20h]
0x1800260a1  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x1800260a6  xor     r15d, r15d
0x1800260a9  mov     edx, r15d
0x1800260ac  mov     rax, [r13+8]
0x1800260b0  sub     rax, [r13+0]
0x1800260b4  sar     rax, 3
0x1800260b8  cmp     rdx, rax
0x1800260bb  jnb     loc_1800261BC
0x1800260c1  mov     [rsp+68h+pv], 0
0x1800260ca  mov     rcx, r13
0x1800260cd  call    ?at@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@_K@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(unsigned __int64)
0x1800260d2  mov     r12, [rax]
0x1800260d5  mov     rax, [r12]
0x1800260d9  mov     rax, [rax+18h]
0x1800260dd  mov     [rsp+68h+arg_18], rax
0x1800260e5  mov     rbx, [rsp+68h+pv]
0x1800260ea  test    rbx, rbx
0x1800260ed  jz      short loc_180026120
0x1800260ef  lea     rcx, [rsp+68h+arg_10]; this
0x1800260f7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800260fc  mov     rcx, rbx; pv
0x1800260ff  call    cs:__imp_CoTaskMemFree
0x180026106  nop     dword ptr [rax+rax+00h]
0x18002610b  lea     rcx, [rsp+68h+arg_10]; this
0x180026113  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180026118  mov     rax, [rsp+68h+arg_18]
0x180026120  mov     [rsp+68h+pv], 0
0x180026129  lea     rdx, [rsp+68h+pv]
0x18002612e  mov     rcx, r12
0x180026131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026136  mov     ebx, eax
0x180026138  test    eax, eax
0x18002613a  jns     short loc_18002617C
0x18002613c  mov     rcx, [rsp+68h]; this
0x180026141  mov     r9d, eax; char *
0x180026144  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002614b  mov     edx, 0B7h; void *
0x180026150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026155  nop
0x180026156  lea     rcx, [rsp+68h+pv]
0x18002615b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026160  nop
0x180026161  test    rdi, rdi
0x180026164  jz      short loc_180026178
0x180026166  mov     [rdi], rsi
0x180026169  mov     rcx, rdi
0x18002616c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026173  nop     dword ptr [rax+rax+00h]
0x180026178  mov     eax, ebx
0x18002617a  jmp     short loc_1800261FB
0x18002617c  mov     rbx, [rsp+68h+pv]
0x180026181  test    rbx, rbx
0x180026184  jz      short loc_1800261AA
0x180026186  mov     rax, [r14+30h]
0x18002618a  cmp     [r14+28h], rax
0x18002618e  jnz     short loc_180026199
0x180026190  lea     rcx, [r14+20h]
0x180026194  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180026199  mov     rdx, rbx
0x18002619c  mov     rcx, [r14+28h]
0x1800261a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800261a5  add     qword ptr [r14+28h], 20h ; ' '
0x1800261aa  lea     rcx, [rsp+68h+pv]
0x1800261af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800261b4  inc     r15d
0x1800261b7  jmp     loc_1800260A9
0x1800261bc  test    rdi, rdi
0x1800261bf  jz      short loc_1800261D3
0x1800261c1  mov     [rdi], rsi
0x1800261c4  mov     rcx, rdi
0x1800261c7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800261ce  nop     dword ptr [rax+rax+00h]
0x1800261d3  xor     eax, eax
0x1800261d5  jmp     short loc_1800261FB
0x1800261d7  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800261dc  test    rcx, rcx
0x1800261df  jz      short loc_1800261F7
0x1800261e1  lea     rsi, ??_7PluginEnumerator@@6B@; const PluginEnumerator::`vftable'
0x1800261e8  mov     [rcx], rsi
0x1800261eb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800261f2  nop     dword ptr [rax+rax+00h]
0x1800261f7  mov     eax, dword ptr [rsp+68h+pv]
0x1800261fb  add     rsp, 30h
0x1800261ff  pop     r15
0x180026201  pop     r14
0x180026203  pop     r13
0x180026205  pop     r12
0x180026207  pop     rdi
0x180026208  pop     rsi
0x180026209  pop     rbx
0x18002620a  retn
```
