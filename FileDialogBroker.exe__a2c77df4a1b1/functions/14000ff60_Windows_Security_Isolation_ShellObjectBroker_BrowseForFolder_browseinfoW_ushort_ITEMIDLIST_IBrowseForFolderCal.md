# Windows::Security::Isolation::ShellObjectBroker::BrowseForFolder(_browseinfoW *,ushort * *,_ITEMIDLIST * *,IBrowseForFolderCallback *)

- ea: `0x14000ff60`
- end: `0x1400100df`
- name: `?BrowseForFolder@ShellObjectBroker@Isolation@Security@Windows@@UEAAJPEAU_browseinfoW@@PEAPEAGPEAPEFAU_ITEMIDLIST@@PEAUIBrowseForFolderCallback@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::ShellObjectBroker *__hidden this, struct _browseinfoW *, unsigned __int16 **, struct _ITEMIDLIST **, struct IBrowseForFolderCallback *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005084`
- `0x14000fdec`
- `0x14000fed4`
- `0x14000ff60`
- `0x140010498`
- `0x140014010`

## import_xrefs

- `SHELL32!SHBrowseForFolderW` at `0x140010074`
- `SHELL32!SHBrowseForFolderW` at `0x140010074`

## string_xrefs

- `0x14000ff93`: `onecoreuap\ds\security\isolation\broker\lib\shellobjectbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::ShellObjectBroker::BrowseForFolder(
        Windows::Security::Isolation::ShellObjectBroker *this,
        struct _browseinfoW *a2,
        unsigned __int16 **a3,
        struct _ITEMIDLIST **a4,
        struct IBrowseForFolderCallback *a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  struct IBrowseForFolderCallback *v11; // rcx
  __int64 v12; // r14
  struct _ITEMIDLIST *v13; // rax
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned __int16 *v17; // rax
  _browseinfoW bi; // [rsp+20h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned __int16 *v20; // [rsp+90h] [rbp+30h] BYREF

  if ( !a3 )
  {
    v8 = 48;
LABEL_3:
    v9 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\shellobjectbroker.cpp",
      (const char *)v9,
      (int)bi.hwndOwner);
    return v9;
  }
  *a3 = 0;
  if ( !a4 )
  {
    v8 = 51;
    goto LABEL_3;
  }
  *a4 = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    v8 = 54;
    goto LABEL_4;
  }
  bi.hwndOwner = a2->hwndOwner;
  bi.pidlRoot = a2->pidlRoot;
  bi.pszDisplayName = a2->pszDisplayName;
  bi.lpszTitle = a2->lpszTitle;
  bi.ulFlags = a2->ulFlags;
  *(&bi.ulFlags + 1) = 0;
  bi.lpfn = a2->lpfn;
  bi.lParam = a2->lParam;
  bi.iImage = a2->iImage;
  *(&bi.iImage + 1) = 0;
  v11 = a5;
  if ( bi.lpfn )
  {
    if ( !a5 )
    {
      v9 = -2147024809;
      v8 = 68;
      goto LABEL_4;
    }
  }
  else if ( !a5 )
  {
    goto LABEL_16;
  }
  bi.lpfn = (BFFCALLBACK)Windows::Security::Isolation::ShellObjectBroker::s_BrowseForFolderCallbackIntercept;
  v12 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = a5;
  (*(void (__fastcall **)(struct IBrowseForFolderCallback *))(*(_QWORD *)v11 + 8LL))(v11);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  bi.lParam = *((_QWORD *)this + 4);
LABEL_16:
  v13 = SHBrowseForFolderW(&bi);
  *a4 = v13;
  if ( !v13 )
  {
    v9 = -2147467259;
    v8 = 71;
    goto LABEL_4;
  }
  if ( bi.pszDisplayName )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v20,
      bi.pszDisplayName);
    v17 = v20;
    if ( !v20 )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, v14, v15, v16);
    v20 = 0;
    *a3 = v17;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
  }
  return 0;
}

```

## disassembly

```asm
0x14000ff60  mov     [rsp-18h+arg_0], rbx
0x14000ff65  mov     [rsp-18h+arg_8], rsi
0x14000ff6a  push    rbp
0x14000ff6b  push    rdi
0x14000ff6c  push    r14
0x14000ff6e  mov     rbp, rsp
0x14000ff71  sub     rsp, 60h
0x14000ff75  mov     rbx, r9
0x14000ff78  mov     rdi, r8
0x14000ff7b  mov     rsi, rcx
0x14000ff7e  test    r8, r8
0x14000ff81  jnz     short loc_14000FFA6
0x14000ff83  lea     edx, [r8+30h]; void *
0x14000ff87  mov     ebx, 80004003h
0x14000ff8c  mov     rcx, [rbp+18h]; this
0x14000ff90  mov     r9d, ebx; char *
0x14000ff93  lea     r8, aOnecoreuapDsSe_4; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000ff9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ff9f  mov     eax, ebx
0x14000ffa1  jmp     loc_1400100CA
0x14000ffa6  mov     qword ptr [r8], 0
0x14000ffad  test    rbx, rbx
0x14000ffb0  jnz     short loc_14000FFB7
0x14000ffb2  lea     edx, [rbx+33h]
0x14000ffb5  jmp     short loc_14000FF87
0x14000ffb7  mov     qword ptr [r9], 0
0x14000ffbe  test    rdx, rdx
0x14000ffc1  jnz     short loc_14000FFCF
0x14000ffc3  mov     ebx, 80070057h
0x14000ffc8  mov     edx, 36h ; '6'
0x14000ffcd  jmp     short loc_14000FF8C
0x14000ffcf  mov     rax, [rdx]
0x14000ffd2  mov     [rbp+bi.hwndOwner], rax
0x14000ffd6  mov     rax, [rdx+8]
0x14000ffda  mov     [rbp+bi.pidlRoot], rax
0x14000ffde  mov     rax, [rdx+10h]
0x14000ffe2  mov     [rbp+bi.pszDisplayName], rax
0x14000ffe6  mov     rax, [rdx+18h]
0x14000ffea  mov     [rbp+bi.lpszTitle], rax
0x14000ffee  mov     eax, [rdx+20h]
0x14000fff1  mov     [rbp+bi.ulFlags], eax
0x14000fff4  xor     eax, eax
0x14000fff6  mov     dword ptr [rbp+bi+24h], eax
0x14000fff9  mov     rcx, [rdx+28h]
0x14000fffd  mov     [rbp+bi.lpfn], rcx
0x140010001  mov     rax, [rdx+30h]
0x140010005  mov     [rbp+bi.lParam], rax
0x140010009  mov     eax, [rdx+38h]
0x14001000c  mov     [rbp+bi.iImage], eax
0x14001000f  xor     eax, eax
0x140010011  mov     dword ptr [rbp+bi+3Ch], eax
0x140010014  test    rcx, rcx
0x140010017  mov     rcx, [rbp+arg_20]
0x14001001b  jz      short loc_14001002F
0x14001001d  test    rcx, rcx
0x140010020  jnz     short loc_140010034
0x140010022  mov     ebx, 80070057h
0x140010027  lea     edx, [rax+44h]
0x14001002a  jmp     loc_14000FF8C
0x14001002f  test    rcx, rcx
0x140010032  jz      short loc_140010070
0x140010034  lea     rax, ?s_BrowseForFolderCallbackIntercept@ShellObjectBroker@Isolation@Security@Windows@@SAHPEAUHWND__@@I_J1@Z; Windows::Security::Isolation::ShellObjectBroker::s_BrowseForFolderCallbackIntercept(HWND__ *,uint,__int64,__int64)
0x14001003b  mov     [rbp+bi.lpfn], rax
0x14001003f  mov     r14, [rsi+20h]
0x140010043  mov     [rsi+20h], rcx
0x140010047  mov     rax, [rcx]
0x14001004a  mov     rax, [rax+8]
0x14001004e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010053  test    r14, r14
0x140010056  jz      short loc_140010068
0x140010058  mov     rax, [r14]
0x14001005b  mov     rcx, r14
0x14001005e  mov     rax, [rax+10h]
0x140010062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010067  nop
0x140010068  mov     rax, [rsi+20h]
0x14001006c  mov     [rbp+bi.lParam], rax
0x140010070  lea     rcx, [rbp+bi]; lpbi
0x140010074  call    cs:__imp_SHBrowseForFolderW
0x14001007a  mov     [rbx], rax
0x14001007d  test    rax, rax
0x140010080  jnz     short loc_14001008F
0x140010082  mov     ebx, 80004005h
0x140010087  lea     edx, [rax+47h]
0x14001008a  jmp     loc_14000FF8C
0x14001008f  mov     rdx, [rbp+bi.pszDisplayName]
0x140010093  test    rdx, rdx
0x140010096  jz      short loc_1400100C8
0x140010098  lea     rcx, [rbp+arg_10]
0x14001009c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1400100a1  mov     rcx, [rbp+18h]; this
0x1400100a5  mov     rax, [rbp+arg_10]
0x1400100a9  test    rax, rax
0x1400100ac  jnz     short loc_1400100B4
0x1400100ae  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1400100b4  mov     [rbp+arg_10], 0
0x1400100bc  mov     [rdi], rax
0x1400100bf  lea     rcx, [rbp+arg_10]
0x1400100c3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400100c8  xor     eax, eax
0x1400100ca  lea     r11, [rsp+60h+var_s0]
0x1400100cf  mov     rbx, [r11+20h]
0x1400100d3  mov     rsi, [r11+28h]
0x1400100d7  mov     rsp, r11
0x1400100da  pop     r14
0x1400100dc  pop     rdi
0x1400100dd  pop     rbp
0x1400100de  retn
```
