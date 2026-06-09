# OSIntegration::Tools::MoCOMHelper::FixACIDEntryPointProperty(ushort const *)

- ea: `0x180006770`
- end: `0x180006990`
- name: `?FixACIDEntryPointProperty@MoCOMHelper@Tools@OSIntegration@@AEAAJPEBG@Z`
- size: `544`
- prototype: `__int64 __fastcall(OSIntegration::Tools::MoCOMHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005f50`
- `0x180006258`
- `0x180014d50`

## callees

- `0x180006770`
- `0x180006998`
- `0x1800135d8`
- `0x18003a300`
- `0x180098bf4`
- `0x1800fc229`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180006897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180006897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800067ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180006867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800067ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180006867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800067c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006856`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000687e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800068d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800068e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800067c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006856`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000687e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800068d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800068e1`

## string_xrefs

- `0x18000682d`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180006946`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180006977`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::FixACIDEntryPointProperty(
        OSIntegration::Tools::MoCOMHelper *this,
        unsigned __int16 *a2)
{
  HSTRING v3; // rbx
  HRESULT v4; // eax
  unsigned int v5; // edi
  HSTRING v6; // rdi
  unsigned __int64 v7; // r15
  _QWORD *v8; // r14
  const WCHAR *v9; // rcx
  unsigned __int64 v10; // rdx
  HRESULT v11; // esi
  HSTRING v13; // rcx
  int v14; // eax
  HSTRING v15[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  HSTRING string; // [rsp+80h] [rbp+50h] BYREF
  HSTRING v19; // [rsp+88h] [rbp+58h] BYREF

  v3 = 0;
  v15[0] = 0;
  v19 = 0;
  string = 0;
  v4 = WindowsCreateString(L"AppObject.EntryPoint", 0x14u, &string);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x469,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v4,
      (int)v15[0]);
    return v5;
  }
  v6 = string;
  v19 = string;
  WindowsDeleteString(0);
  v7 = 0;
  v8 = (_QWORD *)((char *)this + 520);
  while ( 1 )
  {
    if ( v7 >= *((_QWORD *)this + 67) )
      goto LABEL_20;
    v9 = *(const WCHAR **)(*(_QWORD *)(*v8 + 8 * v7) + 32LL);
    if ( !v9 )
    {
      v11 = -2147467261;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x470,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v11,
        (int)v15[0]);
      if ( v6 )
        WindowsDeleteString(v6);
      if ( v3 )
        WindowsDeleteString(v3);
      return (unsigned int)v11;
    }
    string = 0;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    if ( v10 <= 0xFFFFFFFF )
    {
      v11 = WindowsCreateString(v9, v10, &string);
      if ( v11 >= 0 )
      {
        v13 = v3;
        v3 = string;
        v15[0] = string;
        WindowsDeleteString(v13);
      }
    }
    else
    {
      v11 = -2147024362;
    }
    if ( v11 < 0 )
      goto LABEL_10;
    LODWORD(string) = 0;
    WindowsCompareStringOrdinal(v3, v6, (INT32 *)&string);
    if ( !(_DWORD)string )
      break;
    ++v7;
  }
  if ( v7 < *((_QWORD *)this + 67) )
  {
    if ( *((_BYTE *)this + 544) )
      Common::ContainerOperations<OSIntegration::Tools::Internal::Property<Common::StringBuffer>,OSIntegration::Tools::Internal::Property<Common::StringBuffer>>::Delete(*(void **)(*v8 + 8 * v7));
    memmove_0((void *)(8 * v7 + *v8), (const void *)(8 * v7 + *v8 + 8), 8 * (*((_QWORD *)this + 67) - v7) - 8);
    --*((_QWORD *)this + 67);
  }
LABEL_20:
  v14 = OSIntegration::Tools::AddStringPropertyToContainer(L"AppObject.EntryPoint", a2);
  v11 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47F,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v14,
      (int)v15[0]);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v19);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(v15);
    return (unsigned int)v11;
  }
  if ( v6 )
    WindowsDeleteString(v6);
  if ( v3 )
    WindowsDeleteString(v3);
  return 0;
}

```

## disassembly

```asm
0x180006770  mov     [rsp-38h+arg_0], rbx
0x180006775  mov     [rsp-38h+arg_8], rdx
0x18000677a  push    rbp
0x18000677b  push    rsi
0x18000677c  push    rdi
0x18000677d  push    r12
0x18000677f  push    r13
0x180006781  push    r14
0x180006783  push    r15
0x180006785  mov     rbp, rsp
0x180006788  sub     rsp, 30h
0x18000678c  mov     r13, rcx
0x18000678f  xor     esi, esi
0x180006791  mov     ebx, esi
0x180006793  mov     [rbp+var_10], rbx
0x180006797  mov     [rbp+arg_18], rsi
0x18000679b  mov     [rbp+string], rsi
0x18000679f  lea     r8, [rbp+string]; string
0x1800067a3  lea     edx, [rsi+14h]; length
0x1800067a6  lea     rcx, sourceString; "AppObject.EntryPoint"
0x1800067ad  call    cs:__imp_WindowsCreateString
0x1800067b3  mov     edi, eax
0x1800067b5  test    eax, eax
0x1800067b7  js      loc_180006970
0x1800067bd  mov     rdi, [rbp+string]
0x1800067c1  mov     [rbp+arg_18], rdi
0x1800067c5  xor     ecx, ecx; string
0x1800067c7  call    cs:__imp_WindowsDeleteString
0x1800067cd  mov     r15d, esi
0x1800067d0  lea     r14, [r13+208h]
0x1800067d7  mov     rax, r14
0x1800067da  lea     r12, ds:0[r15*8]
0x1800067e2  cmp     r15, [r13+218h]
0x1800067e9  jnb     loc_1800068AE
0x1800067ef  mov     rax, [r14]
0x1800067f2  mov     rcx, [rax+r12]
0x1800067f6  mov     rcx, [rcx+20h]; sourceString
0x1800067fa  test    rcx, rcx
0x1800067fd  jz      short loc_180006821
0x1800067ff  mov     [rbp+string], rsi
0x180006803  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180006807  inc     rdx; length
0x18000680a  cmp     [rcx+rdx*2], si
0x18000680e  jnz     short loc_180006807
0x180006810  mov     eax, 0FFFFFFFFh
0x180006815  cmp     rdx, rax
0x180006818  jbe     short loc_180006863
0x18000681a  mov     esi, 80070216h
0x18000681f  jmp     short loc_180006884
0x180006821  mov     esi, 80004003h
0x180006826  mov     rcx, [rbp+38h]; this
0x18000682a  mov     r9d, esi; char *
0x18000682d  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180006834  mov     edx, 470h; void *
0x180006839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000683e  nop
0x18000683f  test    rdi, rdi
0x180006842  jz      short loc_18000684E
0x180006844  mov     rcx, rdi; string
0x180006847  call    cs:__imp_WindowsDeleteString
0x18000684d  nop
0x18000684e  test    rbx, rbx
0x180006851  jz      short loc_18000685C
0x180006853  mov     rcx, rbx; string
0x180006856  call    cs:__imp_WindowsDeleteString
0x18000685c  mov     eax, esi
0x18000685e  jmp     loc_1800068E9
0x180006863  lea     r8, [rbp+string]; string
0x180006867  call    cs:__imp_WindowsCreateString
0x18000686d  mov     esi, eax
0x18000686f  test    eax, eax
0x180006871  js      short loc_180006884
0x180006873  mov     rcx, rbx; string
0x180006876  mov     rbx, [rbp+string]
0x18000687a  mov     [rbp+var_10], rbx
0x18000687e  call    cs:__imp_WindowsDeleteString
0x180006884  test    esi, esi
0x180006886  js      short loc_180006826
0x180006888  xor     esi, esi
0x18000688a  mov     dword ptr [rbp+string], esi
0x18000688d  lea     r8, [rbp+string]; result
0x180006891  mov     rdx, rdi; string2
0x180006894  mov     rcx, rbx; string1
0x180006897  call    cs:__imp_WindowsCompareStringOrdinal
0x18000689d  cmp     dword ptr [rbp+string], esi
0x1800068a0  jnz     short loc_1800068FE
0x1800068a2  mov     rax, r14
0x1800068a5  cmp     r15, [r13+218h]
0x1800068ac  jb      short loc_180006906
0x1800068ae  mov     r14, rax
0x1800068b1  mov     r8, r14
0x1800068b4  mov     rdx, [rbp+arg_8]
0x1800068b8  lea     rcx, sourceString; "AppObject.EntryPoint"
0x1800068bf  call    ?AddStringPropertyToContainer@Tools@OSIntegration@@YAJPEBG0AEAV?$Array@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@V?$ContainerOperations@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@@6@V?$ArrayOperations@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@VNoKey@Common@@@6@@Common@@@Z; OSIntegration::Tools::AddStringPropertyToContainer(ushort const *,ushort const *,Common::Array<OSIntegration::Tools::Internal::Property<Common::StringBuffer>,Common::ContainerOperations<OSIntegration::Tools::Internal::Property<Common::StringBuffer>,OSIntegration::Tools::Internal::Property<Common::StringBuffer>>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::Tools::Internal::Property<Common::StringBuffer>>,Common::ArrayOperations<OSIntegration::Tools::Internal::Property<Common::StringBuffer>,Common::NoKey>> &)
0x1800068c4  mov     esi, eax
0x1800068c6  test    eax, eax
0x1800068c8  js      short loc_18000693F
0x1800068ca  test    rdi, rdi
0x1800068cd  jz      short loc_1800068D9
0x1800068cf  mov     rcx, rdi; string
0x1800068d2  call    cs:__imp_WindowsDeleteString
0x1800068d8  nop
0x1800068d9  test    rbx, rbx
0x1800068dc  jz      short loc_1800068E7
0x1800068de  mov     rcx, rbx; string
0x1800068e1  call    cs:__imp_WindowsDeleteString
0x1800068e7  xor     eax, eax
0x1800068e9  mov     rbx, [rsp+30h+arg_0]
0x1800068ee  add     rsp, 30h
0x1800068f2  pop     r15
0x1800068f4  pop     r14
0x1800068f6  pop     r13
0x1800068f8  pop     r12
0x1800068fa  pop     rdi
0x1800068fb  pop     rsi
0x1800068fc  pop     rbp
0x1800068fd  retn
0x1800068fe  inc     r15
0x180006901  jmp     loc_1800067D7
0x180006906  cmp     [r14+18h], sil
0x18000690a  jz      short loc_180006918
0x18000690c  mov     rcx, [r14]
0x18000690f  mov     rcx, [rcx+r12]; void *
0x180006913  call    ?Delete@?$ContainerOperations@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@V1234@@Common@@SAXPEAV?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@@Z; Common::ContainerOperations<OSIntegration::Tools::Internal::Property<Common::StringBuffer>,OSIntegration::Tools::Internal::Property<Common::StringBuffer>>::Delete(OSIntegration::Tools::Internal::Property<Common::StringBuffer> *)
0x180006918  mov     rcx, [r14]
0x18000691b  add     rcx, r12; void *
0x18000691e  mov     r8, [r14+10h]
0x180006922  sub     r8, r15
0x180006925  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x18000692d  lea     rdx, [rcx+8]; Src
0x180006931  call    memmove_0
0x180006936  dec     qword ptr [r14+10h]
0x18000693a  jmp     loc_1800068B1
0x18000693f  mov     rcx, [rbp+38h]; this
0x180006943  mov     r9d, esi; char *
0x180006946  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18000694d  mov     edx, 47Fh; void *
0x180006952  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006957  nop
0x180006958  lea     rcx, [rbp+arg_18]
0x18000695c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180006961  nop
0x180006962  lea     rcx, [rbp+var_10]
0x180006966  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18000696b  jmp     loc_18000685C
0x180006970  mov     rcx, [rbp+38h]; this
0x180006974  mov     r9d, edi; char *
0x180006977  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18000697e  mov     edx, 469h; void *
0x180006983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006988  nop
0x180006989  mov     eax, edi
0x18000698b  jmp     loc_1800068E9
```
