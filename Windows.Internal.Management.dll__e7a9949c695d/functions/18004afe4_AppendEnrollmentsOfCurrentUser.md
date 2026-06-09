# AppendEnrollmentsOfCurrentUser

- ea: `0x18004afe4`
- end: `0x18004b1fd`
- name: `AppendEnrollmentsOfCurrentUser`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059e40`

## callees

- `0x180004d50`
- `0x18000a2a4`
- `0x18000d724`
- `0x180015e4c`
- `0x1800168d0`
- `0x180024b60`
- `0x180024cd0`
- `0x18003b198`
- `0x18004afe4`
- `0x18004b204`
- `0x18005a894`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b11c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b11c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b0cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b0cf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004b0a2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004b0a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AppendEnrollmentsOfCurrentUser(HSTRING a1, _QWORD *a2)
{
  int TargetedSID; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HRESULT v7; // eax
  struct IUnknown *v8; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  __int64 v10; // rax
  int v11; // eax
  struct IUnknown *v13; // [rsp+20h] [rbp-79h] BYREF
  __int64 v14; // [rsp+28h] [rbp-71h] BYREF
  HSTRING string[2]; // [rsp+30h] [rbp-69h] BYREF
  GUID rguid; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  string[1] = a1;
  std::wstring::wstring(v17);
  TargetedSID = GetTargetedSID((__int64)v17);
  v5 = TargetedSID;
  if ( TargetedSID >= 0 )
  {
    v13 = 0;
    while ( !(*(unsigned int (__fastcall **)(_QWORD, struct IUnknown **))(**(_QWORD **)a1 + 24LL))(*(_QWORD *)a1, &v13) )
    {
      rguid = 0;
      if ( ((int (__fastcall *)(struct IUnknown *, GUID *))v13->lpVtbl[1].QueryInterface)(v13, &rguid) >= 0 )
      {
        sz[0] = 0;
        if ( StringFromGUID2(&rguid, sz, 39) != 39 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
          v5 = -2147418113;
          goto LABEL_21;
        }
        string[0] = 0;
        v6 = -1;
        do
          ++v6;
        while ( sz[v6] );
        v7 = WindowsCreateString(sz, v6, string);
        v5 = v7;
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB68,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\enroller.cpp",
            (const char *)(unsigned int)v7,
            (int)v13);
          goto LABEL_18;
        }
        v14 = 0;
        v8 = v13;
        Release = v13->lpVtbl[4].Release;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v14,
          0);
        if ( ((int (__fastcall *)(struct IUnknown *, __int64 *))Release)(v8, &v14) >= 0 )
        {
          v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
          if ( !(unsigned int)_o__wcsicmp(v10, v14) )
          {
            v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(*(_QWORD *)*a2 + 104LL))(*a2, string[0]);
            v5 = v11;
            if ( v11 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xB72,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\enroller.cpp",
                (const char *)(unsigned int)v11,
                (int)v13);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
LABEL_18:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
              goto LABEL_21;
            }
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
      }
      if ( v13 )
        ATL::AtlComPtrAssign(&v13, 0);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
    v5 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB55,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\enroller.cpp",
      (const char *)(unsigned int)TargetedSID,
      (int)v13);
  }
LABEL_21:
  std::wstring::~wstring(v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
  return v5;
}

```

## disassembly

```asm
0x18004afe4  mov     [rsp-8+arg_10], rbx
0x18004afe9  push    rbp
0x18004afea  push    rsi
0x18004afeb  push    rdi
0x18004afec  push    r14
0x18004afee  push    r15
0x18004aff0  lea     rbp, [rsp-37h]
0x18004aff5  sub     rsp, 0D0h
0x18004affc  mov     rax, cs:__security_cookie
0x18004b003  xor     rax, rsp
0x18004b006  mov     [rbp+57h+var_30], rax
0x18004b00a  mov     r14, rdx
0x18004b00d  mov     rsi, rcx
0x18004b010  mov     [rbp+57h+var_B8], rcx
0x18004b014  lea     rcx, [rbp+57h+var_A0]
0x18004b018  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004b01d  nop
0x18004b01e  lea     rcx, [rbp+57h+var_A0]
0x18004b022  call    GetTargetedSID
0x18004b027  mov     ebx, eax
0x18004b029  xor     r15d, r15d
0x18004b02c  test    eax, eax
0x18004b02e  jns     short loc_18004B04D
0x18004b030  mov     rcx, [rbp+5Fh]; this
0x18004b034  mov     r9d, eax; char *
0x18004b037  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004b03e  mov     edx, 0B55h; void *
0x18004b043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b048  jmp     loc_18004B1C6
0x18004b04d  mov     [rbp+57h+var_D0], r15
0x18004b051  mov     rcx, [rsi]
0x18004b054  mov     rax, [rcx]
0x18004b057  lea     rdx, [rbp+57h+var_D0]
0x18004b05b  mov     rax, [rax+18h]
0x18004b05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b064  test    eax, eax
0x18004b066  jnz     loc_18004B1BA
0x18004b06c  xorps   xmm0, xmm0
0x18004b06f  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x18004b073  mov     rcx, [rbp+57h+var_D0]
0x18004b077  mov     rax, [rcx]
0x18004b07a  lea     rdx, [rbp+57h+rguid]
0x18004b07e  mov     rax, [rax+18h]
0x18004b082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b087  test    eax, eax
0x18004b089  js      loc_18004B148
0x18004b08f  mov     [rbp+57h+sz], r15w
0x18004b094  mov     r8d, 27h ; '''; cchMax
0x18004b09a  lea     rdx, [rbp+57h+sz]; lpsz
0x18004b09e  lea     rcx, [rbp+57h+rguid]; rguid
0x18004b0a2  call    cs:__imp_StringFromGUID2
0x18004b0a8  cmp     eax, 27h ; '''
0x18004b0ab  jnz     loc_18004B1AA
0x18004b0b1  mov     [rbp+57h+string], r15
0x18004b0b5  lea     rax, [rbp+57h+sz]
0x18004b0b9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004b0bd  inc     rdx; length
0x18004b0c0  cmp     [rax+rdx*2], r15w
0x18004b0c5  jnz     short loc_18004B0BD
0x18004b0c7  lea     r8, [rbp+57h+string]; string
0x18004b0cb  lea     rcx, [rbp+57h+sz]; sourceString
0x18004b0cf  call    cs:__imp_WindowsCreateString
0x18004b0d5  mov     ebx, eax
0x18004b0d7  test    eax, eax
0x18004b0d9  js      loc_18004B186
0x18004b0df  mov     [rbp+57h+var_C8], r15
0x18004b0e3  mov     rdi, [rbp+57h+var_D0]
0x18004b0e7  mov     rax, [rdi]
0x18004b0ea  mov     rbx, [rax+70h]
0x18004b0ee  xor     edx, edx
0x18004b0f0  lea     rcx, [rbp+57h+var_C8]
0x18004b0f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004b0f9  lea     rdx, [rbp+57h+var_C8]
0x18004b0fd  mov     rcx, rdi
0x18004b100  mov     rax, rbx
0x18004b103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b108  test    eax, eax
0x18004b10a  js      short loc_18004B13F
0x18004b10c  lea     rcx, [rbp+57h+var_A0]
0x18004b110  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004b115  mov     rcx, rax
0x18004b118  mov     rdx, [rbp+57h+var_C8]
0x18004b11c  call    cs:__imp__o__wcsicmp
0x18004b122  test    eax, eax
0x18004b124  jnz     short loc_18004B13F
0x18004b126  mov     rcx, [r14]
0x18004b129  mov     rax, [rcx]
0x18004b12c  mov     rdx, [rbp+57h+string]
0x18004b130  mov     rax, [rax+68h]
0x18004b134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b139  mov     ebx, eax
0x18004b13b  test    eax, eax
0x18004b13d  js      short loc_18004B162
0x18004b13f  lea     rcx, [rbp+57h+var_C8]
0x18004b143  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004b148  cmp     [rbp+57h+var_D0], r15
0x18004b14c  jz      loc_18004B051
0x18004b152  xor     edx, edx; struct IUnknown *
0x18004b154  lea     rcx, [rbp+57h+var_D0]; struct IUnknown **
0x18004b158  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004b15d  jmp     loc_18004B051
0x18004b162  mov     rcx, [rbp+5Fh]; this
0x18004b166  mov     r9d, eax; char *
0x18004b169  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004b170  mov     edx, 0B72h; void *
0x18004b175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b17a  nop
0x18004b17b  lea     rcx, [rbp+57h+var_C8]
0x18004b17f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004b184  jmp     short loc_18004B19F
0x18004b186  mov     rcx, [rbp+5Fh]; this
0x18004b18a  mov     r9d, eax; char *
0x18004b18d  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004b194  mov     edx, 0B68h; void *
0x18004b199  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b19e  nop
0x18004b19f  lea     rcx, [rbp+57h+var_D0]
0x18004b1a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b1a8  jmp     short loc_18004B1C6
0x18004b1aa  lea     rcx, [rbp+57h+var_D0]
0x18004b1ae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b1b3  mov     ebx, 8000FFFFh
0x18004b1b8  jmp     short loc_18004B1C6
0x18004b1ba  lea     rcx, [rbp+57h+var_D0]
0x18004b1be  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b1c3  mov     ebx, r15d
0x18004b1c6  lea     rcx, [rbp+57h+var_A0]
0x18004b1ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b1cf  nop
0x18004b1d0  mov     rcx, rsi
0x18004b1d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b1d8  mov     eax, ebx
0x18004b1da  mov     rcx, [rbp+57h+var_30]
0x18004b1de  xor     rcx, rsp; StackCookie
0x18004b1e1  call    __security_check_cookie
0x18004b1e6  mov     rbx, [rsp+0F0h+arg_10]
0x18004b1ee  add     rsp, 0D0h
0x18004b1f5  pop     r15
0x18004b1f7  pop     r14
0x18004b1f9  pop     rdi
0x18004b1fa  pop     rsi
0x18004b1fb  pop     rbp
0x18004b1fc  retn
```
