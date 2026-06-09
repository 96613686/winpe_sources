# AppendEnrollmentsOfCurrentUser

- ea: `0x18004b1e0`
- end: `0x18004b40c`
- name: `AppendEnrollmentsOfCurrentUser`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005a820`

## callees

- `0x180004eb0`
- `0x18000a5c4`
- `0x18000dc18`
- `0x18001656c`
- `0x180017024`
- `0x1800231e8`
- `0x18002335c`
- `0x18003a52c`
- `0x18004b1e0`
- `0x18004b414`
- `0x18005b2f8`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b324`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b2d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b2d1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004b29e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004b29e`

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
            (void *)0xB54,
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
                (void *)0xB5E,
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
      (void *)0xB41,
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
0x18004b1e0  mov     [rsp-8+arg_10], rbx
0x18004b1e5  push    rbp
0x18004b1e6  push    rsi
0x18004b1e7  push    rdi
0x18004b1e8  push    r14
0x18004b1ea  push    r15
0x18004b1ec  lea     rbp, [rsp-37h]
0x18004b1f1  sub     rsp, 0D0h
0x18004b1f8  mov     rax, cs:__security_cookie
0x18004b1ff  xor     rax, rsp
0x18004b202  mov     [rbp+57h+var_30], rax
0x18004b206  mov     r14, rdx
0x18004b209  mov     rsi, rcx
0x18004b20c  mov     [rbp+57h+var_B8], rcx
0x18004b210  lea     rcx, [rbp+57h+var_A0]
0x18004b214  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004b219  nop
0x18004b21a  lea     rcx, [rbp+57h+var_A0]
0x18004b21e  call    GetTargetedSID
0x18004b223  mov     ebx, eax
0x18004b225  xor     r15d, r15d
0x18004b228  test    eax, eax
0x18004b22a  jns     short loc_18004B249
0x18004b22c  mov     rcx, [rbp+5Fh]; this
0x18004b230  mov     r9d, eax; char *
0x18004b233  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004b23a  mov     edx, 0B41h; void *
0x18004b23f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b244  jmp     loc_18004B3D4
0x18004b249  mov     [rbp+57h+var_D0], r15
0x18004b24d  mov     rcx, [rsi]
0x18004b250  mov     rax, [rcx]
0x18004b253  lea     rdx, [rbp+57h+var_D0]
0x18004b257  mov     rax, [rax+18h]
0x18004b25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b260  test    eax, eax
0x18004b262  jnz     loc_18004B3C8
0x18004b268  xorps   xmm0, xmm0
0x18004b26b  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x18004b26f  mov     rcx, [rbp+57h+var_D0]
0x18004b273  mov     rax, [rcx]
0x18004b276  lea     rdx, [rbp+57h+rguid]
0x18004b27a  mov     rax, [rax+18h]
0x18004b27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b283  test    eax, eax
0x18004b285  js      loc_18004B356
0x18004b28b  mov     [rbp+57h+sz], r15w
0x18004b290  mov     r8d, 27h ; '''; cchMax
0x18004b296  lea     rdx, [rbp+57h+sz]; lpsz
0x18004b29a  lea     rcx, [rbp+57h+rguid]; rguid
0x18004b29e  call    cs:__imp_StringFromGUID2
0x18004b2a5  nop     dword ptr [rax+rax+00h]
0x18004b2aa  cmp     eax, 27h ; '''
0x18004b2ad  jnz     loc_18004B3B8
0x18004b2b3  mov     [rbp+57h+string], r15
0x18004b2b7  lea     rax, [rbp+57h+sz]
0x18004b2bb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004b2bf  inc     rdx; length
0x18004b2c2  cmp     [rax+rdx*2], r15w
0x18004b2c7  jnz     short loc_18004B2BF
0x18004b2c9  lea     r8, [rbp+57h+string]; string
0x18004b2cd  lea     rcx, [rbp+57h+sz]; sourceString
0x18004b2d1  call    cs:__imp_WindowsCreateString
0x18004b2d8  nop     dword ptr [rax+rax+00h]
0x18004b2dd  mov     ebx, eax
0x18004b2df  test    eax, eax
0x18004b2e1  js      loc_18004B394
0x18004b2e7  mov     [rbp+57h+var_C8], r15
0x18004b2eb  mov     rdi, [rbp+57h+var_D0]
0x18004b2ef  mov     rax, [rdi]
0x18004b2f2  mov     rbx, [rax+70h]
0x18004b2f6  xor     edx, edx
0x18004b2f8  lea     rcx, [rbp+57h+var_C8]
0x18004b2fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004b301  lea     rdx, [rbp+57h+var_C8]
0x18004b305  mov     rcx, rdi
0x18004b308  mov     rax, rbx
0x18004b30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b310  test    eax, eax
0x18004b312  js      short loc_18004B34D
0x18004b314  lea     rcx, [rbp+57h+var_A0]
0x18004b318  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004b31d  mov     rcx, rax
0x18004b320  mov     rdx, [rbp+57h+var_C8]
0x18004b324  call    cs:__imp__o__wcsicmp
0x18004b32b  nop     dword ptr [rax+rax+00h]
0x18004b330  test    eax, eax
0x18004b332  jnz     short loc_18004B34D
0x18004b334  mov     rcx, [r14]
0x18004b337  mov     rax, [rcx]
0x18004b33a  mov     rdx, [rbp+57h+string]
0x18004b33e  mov     rax, [rax+68h]
0x18004b342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b347  mov     ebx, eax
0x18004b349  test    eax, eax
0x18004b34b  js      short loc_18004B370
0x18004b34d  lea     rcx, [rbp+57h+var_C8]
0x18004b351  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004b356  cmp     [rbp+57h+var_D0], r15
0x18004b35a  jz      loc_18004B24D
0x18004b360  xor     edx, edx; struct IUnknown *
0x18004b362  lea     rcx, [rbp+57h+var_D0]; struct IUnknown **
0x18004b366  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004b36b  jmp     loc_18004B24D
0x18004b370  mov     rcx, [rbp+5Fh]; this
0x18004b374  mov     r9d, eax; char *
0x18004b377  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004b37e  mov     edx, 0B5Eh; void *
0x18004b383  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b388  nop
0x18004b389  lea     rcx, [rbp+57h+var_C8]
0x18004b38d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004b392  jmp     short loc_18004B3AD
0x18004b394  mov     rcx, [rbp+5Fh]; this
0x18004b398  mov     r9d, eax; char *
0x18004b39b  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004b3a2  mov     edx, 0B54h; void *
0x18004b3a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b3ac  nop
0x18004b3ad  lea     rcx, [rbp+57h+var_D0]
0x18004b3b1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b3b6  jmp     short loc_18004B3D4
0x18004b3b8  lea     rcx, [rbp+57h+var_D0]
0x18004b3bc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b3c1  mov     ebx, 8000FFFFh
0x18004b3c6  jmp     short loc_18004B3D4
0x18004b3c8  lea     rcx, [rbp+57h+var_D0]
0x18004b3cc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b3d1  mov     ebx, r15d
0x18004b3d4  lea     rcx, [rbp+57h+var_A0]
0x18004b3d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b3dd  nop
0x18004b3de  mov     rcx, rsi
0x18004b3e1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b3e6  mov     eax, ebx
0x18004b3e8  mov     rcx, [rbp+57h+var_30]
0x18004b3ec  xor     rcx, rsp; StackCookie
0x18004b3ef  call    __security_check_cookie
0x18004b3f4  mov     rbx, [rsp+0F0h+arg_10]
0x18004b3fc  add     rsp, 0D0h
0x18004b403  pop     r15
0x18004b405  pop     r14
0x18004b407  pop     rdi
0x18004b408  pop     rsi
0x18004b409  pop     rbp
0x18004b40a  retn
```
