# PluginEngine::GetPluginIndexFromId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong *)

- ea: `0x180025d60`
- end: `0x180025efb`
- name: `?GetPluginIndexFromId@PluginEngine@@MEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAK@Z`
- size: `411`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004394`
- `0x180004a90`
- `0x1800087ec`
- `0x18001fbfc`
- `0x180021c1c`
- `0x180024d94`
- `0x180025d60`
- `0x180027da0`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dd8`

## string_xrefs

- `0x180025e15`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PluginEngine::GetPluginIndexFromId(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // esi
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, LPVOID *); // r15
  void *v11; // rdi
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // edi
  __int64 v16; // rdx
  const char *v17; // r9
  __int64 result; // rax
  _WORD *v19; // rcx
  unsigned __int64 v20; // r9
  unsigned __int64 v21; // r10
  unsigned __int64 v22; // rdx
  _WORD *v23; // r8
  __int64 v24; // rdx
  LPVOID pv; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v26[8]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v27; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v27 = a2;
  v6 = 0;
  try
  {
    while ( 1 )
    {
      v7 = v6;
      if ( v6 >= (unsigned __int64)((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3) )
        break;
      pv = 0;
      v8 = std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(a1 + 8);
      v9 = *(_QWORD *)v8;
      v10 = *(__int64 (__fastcall **)(__int64, LPVOID *))(**(_QWORD **)v8 + 24LL);
      v11 = pv;
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v26);
        CoTaskMemFree(v11);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v26);
      }
      pv = 0;
      v12 = v10(v9, &pv);
      v15 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x93,
          (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
          (const char *)(unsigned int)v12,
          (int)pv);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
        LOBYTE(v16) = 1;
        std::wstring::_Tidy(a2, v16, 0);
        return v15;
      }
      if ( pv )
      {
        v20 = std::char_traits<unsigned short>::length(pv, v13, v14);
        v21 = *(_QWORD *)(a2 + 16);
        v22 = v20;
        if ( v21 < v20 )
          v22 = *(_QWORD *)(a2 + 16);
        if ( *(_QWORD *)(a2 + 24) < 8u )
          v23 = (_WORD *)a2;
        else
          v23 = *(_WORD **)a2;
        if ( v22 )
        {
          while ( v22 )
          {
            if ( *v23 != *v19 )
              goto LABEL_20;
            ++v23;
            ++v19;
            --v22;
          }
        }
        if ( v21 == v20 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
          break;
        }
      }
LABEL_20:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
      ++v6;
    }
    *a3 = v6;
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(a2, v7, 0);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(pv) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x9F,
                    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                    v17);
    LOBYTE(v24) = 1;
    std::wstring::_Tidy(v27, v24, 0);
    return (unsigned int)pv;
  }
  return result;
}

```

## disassembly

```asm
0x180025d60  push    rbx
0x180025d62  push    rsi
0x180025d63  push    rdi
0x180025d64  push    r12
0x180025d66  push    r13
0x180025d68  push    r14
0x180025d6a  push    r15
0x180025d6c  sub     rsp, 40h
0x180025d70  mov     rax, cs:__security_cookie
0x180025d77  xor     rax, rsp
0x180025d7a  mov     [rsp+78h+var_40], rax
0x180025d7f  mov     r12, r8
0x180025d82  mov     rbx, rdx
0x180025d85  mov     r13, rcx
0x180025d88  mov     [rsp+78h+var_48], rdx
0x180025d8d  xor     esi, esi
0x180025d8f  lea     rcx, [r13+8]
0x180025d93  mov     edx, esi
0x180025d95  mov     rax, [rcx+8]
0x180025d99  sub     rax, [rcx]
0x180025d9c  sar     rax, 3
0x180025da0  cmp     rdx, rax
0x180025da3  jnb     loc_180025EA4
0x180025da9  mov     [rsp+78h+pv], 0
0x180025db2  call    ?at@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@_K@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(unsigned __int64)
0x180025db7  mov     r14, [rax]
0x180025dba  mov     rax, [r14]
0x180025dbd  mov     r15, [rax+18h]
0x180025dc1  mov     rdi, [rsp+78h+pv]
0x180025dc6  test    rdi, rdi
0x180025dc9  jz      short loc_180025DEE
0x180025dcb  lea     rcx, [rsp+78h+var_50]; this
0x180025dd0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180025dd5  mov     rcx, rdi; pv
0x180025dd8  call    cs:__imp_CoTaskMemFree
0x180025ddf  nop     dword ptr [rax+rax+00h]
0x180025de4  lea     rcx, [rsp+78h+var_50]; this
0x180025de9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180025dee  mov     [rsp+78h+pv], 0; int
0x180025df7  lea     rdx, [rsp+78h+pv]
0x180025dfc  mov     rcx, r14
0x180025dff  mov     rax, r15
0x180025e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e07  mov     edi, eax
0x180025e09  test    eax, eax
0x180025e0b  jns     short loc_180025E46
0x180025e0d  mov     rcx, [rsp+78h]; this
0x180025e12  mov     r9d, eax; char *
0x180025e15  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180025e1c  mov     edx, 93h; void *
0x180025e21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e26  nop
0x180025e27  lea     rcx, [rsp+78h+pv]
0x180025e2c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025e31  nop
0x180025e32  xor     r8d, r8d
0x180025e35  mov     dl, 1
0x180025e37  mov     rcx, rbx
0x180025e3a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025e3f  mov     eax, edi
0x180025e41  jmp     loc_180025EDD
0x180025e46  mov     rcx, [rsp+78h+pv]
0x180025e4b  test    rcx, rcx
0x180025e4e  jz      short loc_180025EB9
0x180025e50  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180025e55  mov     r9, rax
0x180025e58  mov     r10, [rbx+10h]
0x180025e5c  mov     rdx, rax
0x180025e5f  cmp     r10, rax
0x180025e62  cmovb   rdx, r10
0x180025e66  cmp     qword ptr [rbx+18h], 8
0x180025e6b  jb      short loc_180025E72
0x180025e6d  mov     r8, [rbx]
0x180025e70  jmp     short loc_180025E75
0x180025e72  mov     r8, rbx
0x180025e75  test    rdx, rdx
0x180025e78  jz      short loc_180025E95
0x180025e7a  test    rdx, rdx
0x180025e7d  jz      short loc_180025E95
0x180025e7f  movzx   eax, word ptr [rcx]
0x180025e82  cmp     [r8], ax
0x180025e86  jnz     short loc_180025EB9
0x180025e88  add     r8, 2
0x180025e8c  add     rcx, 2
0x180025e90  dec     rdx
0x180025e93  jmp     short loc_180025E7A
0x180025e95  cmp     r10, r9
0x180025e98  jnz     short loc_180025EB9
0x180025e9a  lea     rcx, [rsp+78h+pv]
0x180025e9f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025ea4  mov     [r12], esi
0x180025ea8  xor     r8d, r8d
0x180025eab  mov     dl, 1
0x180025ead  mov     rcx, rbx
0x180025eb0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025eb5  xor     eax, eax
0x180025eb7  jmp     short loc_180025EDD
0x180025eb9  lea     rcx, [rsp+78h+pv]
0x180025ebe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025ec3  inc     esi
0x180025ec5  jmp     loc_180025D8F
0x180025eca  xor     r8d, r8d
0x180025ecd  mov     dl, 1
0x180025ecf  mov     rcx, [rsp+78h+var_48]
0x180025ed4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025ed9  mov     eax, dword ptr [rsp+78h+pv]
0x180025edd  mov     rcx, [rsp+78h+var_40]
0x180025ee2  xor     rcx, rsp; StackCookie
0x180025ee5  call    __security_check_cookie
0x180025eea  add     rsp, 40h
0x180025eee  pop     r15
0x180025ef0  pop     r14
0x180025ef2  pop     r13
0x180025ef4  pop     r12
0x180025ef6  pop     rdi
0x180025ef7  pop     rsi
0x180025ef8  pop     rbx
0x180025ef9  retn
```
