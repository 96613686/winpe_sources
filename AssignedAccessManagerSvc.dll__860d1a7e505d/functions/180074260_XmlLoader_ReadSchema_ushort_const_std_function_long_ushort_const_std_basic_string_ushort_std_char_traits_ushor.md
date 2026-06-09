# XmlLoader::ReadSchema(ushort const *,std::function<long (ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)> const &,IXMLDOMDocument3 * *)

- ea: `0x180074260`
- end: `0x1800743b9`
- name: `?ReadSchema@XmlLoader@@AEAAJPEBGAEBV?$function@$$A6AJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@std@@PEAPEAUIXMLDOMDocument3@@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073a70`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000f62c`
- `0x180010c98`
- `0x18002001c`
- `0x180051e2c`
- `0x18005391c`
- `0x180074260`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007429e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007429e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800742e0`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800742e0`

## string_xrefs

- `0x1800742b1`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`
- `0x180074378`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XmlLoader::ReadSchema(__int64 a1, __int64 a2, __int64 a3, LPVOID *a4)
{
  HRESULT Instance; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 v12; // rcx
  int v13; // eax
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  LPVOID v16; // rbx
  __int64 (__fastcall *v17)(LPVOID, _QWORD *, __int16 *); // rdi
  const unsigned __int16 *v18; // rax
  _QWORD *v19; // rdx
  int ppv; // [rsp+20h] [rbp-50h]
  __int16 v21; // [rsp+30h] [rbp-40h] BYREF
  __int64 v22; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
               a4);
  v10 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return v10;
  }
  std::wstring::wstring(v23, v8, v9);
  v22 = a2;
  v12 = *(_QWORD *)(a3 + 56);
  if ( !v12 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)v12 + 16LL))(v12, &v22, v23);
  v10 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)v13;
    v15 = 191;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
      (const char *)v14,
      ppv);
    std::wstring::_Tidy_deallocate(v23);
    return v10;
  }
  v21 = 0;
  v16 = *a4;
  v17 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int16 *))(*(_QWORD *)*a4 + 520LL);
  v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
  v19 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v22, v18);
  if ( v19 )
    v19 = (_QWORD *)*v19;
  v10 = v17(v16, v19, &v21);
  _bstr_t::_Free((_bstr_t *)&v22);
  if ( (v10 & 0x80000000) != 0 )
  {
    v15 = 193;
LABEL_14:
    v14 = v10;
    goto LABEL_15;
  }
  if ( v21 != -1 )
  {
    v10 = -2147467259;
    v15 = 195;
    goto LABEL_14;
  }
  std::wstring::_Tidy_deallocate(v23);
  return 0;
}

```

## disassembly

```asm
0x180074260  push    rbp
0x180074262  push    rbx
0x180074263  push    rsi
0x180074264  push    rdi
0x180074265  push    r14
0x180074267  mov     rbp, rsp
0x18007426a  sub     rsp, 70h
0x18007426e  mov     rax, cs:__security_cookie
0x180074275  xor     rax, rsp
0x180074278  mov     [rbp+var_10], rax
0x18007427c  mov     r14, r9
0x18007427f  mov     rsi, r8
0x180074282  mov     rdi, rdx
0x180074285  mov     qword ptr [rsp+70h+ppv], r9; int
0x18007428a  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x180074291  xor     edx, edx; pUnkOuter
0x180074293  lea     r8d, [rdx+1]; dwClsContext
0x180074297  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18007429e  call    cs:__imp_CoCreateInstance
0x1800742a4  mov     ebx, eax
0x1800742a6  test    eax, eax
0x1800742a8  jns     short loc_1800742C9
0x1800742aa  mov     rcx, [rbp+28h]; this
0x1800742ae  mov     r9d, eax; char *
0x1800742b1  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800742b8  mov     edx, 0BCh; void *
0x1800742bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800742c2  mov     eax, ebx
0x1800742c4  jmp     loc_1800743A2
0x1800742c9  lea     rcx, [rbp+var_30]
0x1800742cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800742d2  nop
0x1800742d3  mov     [rbp+var_38], rdi
0x1800742d7  mov     rcx, [rsi+38h]
0x1800742db  test    rcx, rcx
0x1800742de  jnz     short loc_1800742E7
0x1800742e0  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800742e6  int     3; Trap to Debugger
0x1800742e7  mov     rax, [rcx]
0x1800742ea  lea     r8, [rbp+var_30]
0x1800742ee  lea     rdx, [rbp+var_38]
0x1800742f2  mov     rax, [rax+10h]
0x1800742f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742fb  mov     ebx, eax
0x1800742fd  test    eax, eax
0x1800742ff  jns     short loc_18007430B
0x180074301  mov     r9d, eax
0x180074304  mov     edx, 0BFh
0x180074309  jmp     short loc_180074378
0x18007430b  xor     eax, eax
0x18007430d  mov     [rbp+var_40], ax
0x180074311  mov     rbx, [r14]
0x180074314  mov     rax, [rbx]
0x180074317  mov     rdi, [rax+208h]
0x18007431e  lea     rcx, [rbp+var_30]
0x180074322  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074327  mov     rdx, rax; unsigned __int16 *
0x18007432a  lea     rcx, [rbp+var_38]; this
0x18007432e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180074333  nop
0x180074334  mov     rdx, [rax]
0x180074337  test    rdx, rdx
0x18007433a  jz      short loc_18007433F
0x18007433c  mov     rdx, [rdx]
0x18007433f  lea     r8, [rbp+var_40]
0x180074343  mov     rcx, rbx
0x180074346  mov     rax, rdi
0x180074349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007434e  mov     ebx, eax
0x180074350  lea     rcx, [rbp+var_38]; this
0x180074354  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180074359  test    ebx, ebx
0x18007435b  jns     short loc_180074364
0x18007435d  mov     edx, 0C1h
0x180074362  jmp     short loc_180074375
0x180074364  cmp     [rbp+var_40], 0FFFFh
0x180074369  jz      short loc_180074397
0x18007436b  mov     ebx, 80004005h
0x180074370  mov     edx, 0C3h; void *
0x180074375  mov     r9d, ebx; char *
0x180074378  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007437f  mov     rcx, [rbp+28h]; this
0x180074383  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074388  nop
0x180074389  lea     rcx, [rbp+var_30]
0x18007438d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074392  jmp     loc_1800742C2
0x180074397  lea     rcx, [rbp+var_30]
0x18007439b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800743a0  xor     eax, eax
0x1800743a2  mov     rcx, [rbp+var_10]
0x1800743a6  xor     rcx, rsp; StackCookie
0x1800743a9  call    __security_check_cookie
0x1800743ae  add     rsp, 70h
0x1800743b2  pop     r14
0x1800743b4  pop     rdi
0x1800743b5  pop     rsi
0x1800743b6  pop     rbx
0x1800743b7  pop     rbp
0x1800743b8  retn
```
