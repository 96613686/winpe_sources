# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x18000a3ec`
- end: `0x18000a5db`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000a644`
- `0x1800137e8`

## callees

- `0x180002be0`
- `0x1800037c8`
- `0x180007fac`
- `0x18000a3ec`
- `0x18000d434`
- `0x18000d564`
- `0x18000dab4`
- `0x180010c08`
- `0x18001121c`
- `0x1800113ec`

## string_xrefs

- `0x18000a4a2`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x18000a568`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x18000a597`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,256>(
        _QWORD *a1,
        __int64 a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rax
  int v6; // eax
  unsigned __int64 v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  bool v11; // cc
  int v12; // eax
  int v13; // edi
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  int v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string[2]; // [rsp+28h] [rbp-D8h] BYREF
  PCNZWCH v19; // [rsp+38h] [rbp-C8h]
  _BYTE v20[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR sourceString[256]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *(_OWORD *)string = 0;
  v19 = 0;
  memset_0(sourceString, 0, sizeof(sourceString));
  *(_QWORD *)v17 = 0;
  v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
         a2,
         sourceString,
         256,
         v17);
  if ( v4 < 0 )
    goto LABEL_16;
  v5 = *(_QWORD *)v17;
  if ( *(_QWORD *)v17 > 0x100u )
  {
    while ( 1 )
    {
      v7 = v5;
      v8 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::make(
             string,
             0,
             (int)v5 - 1);
      v9 = v8;
      if ( v8 < 0 )
        break;
      v10 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v19, v7, v17);
      if ( v10 < 0 )
      {
        v4 = v10;
        goto LABEL_16;
      }
      v5 = *(_QWORD *)v17;
      v11 = *(_QWORD *)v17 <= v7;
      if ( *(_QWORD *)v17 < v7 )
      {
        v12 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::make(
                string,
                v19,
                v17[0] - 1);
        v13 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
            (const char *)(unsigned int)v12,
            v17[0]);
          v4 = v13;
          goto LABEL_16;
        }
        v5 = *(_QWORD *)v17;
        v11 = *(_QWORD *)v17 <= v7;
      }
      if ( v11 )
        goto LABEL_11;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17A,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v8,
      v17[0]);
    wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(string);
    return v9;
  }
  else
  {
    v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::make(
           string,
           sourceString,
           v17[0] - 1);
    v4 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v6,
        v17[0]);
LABEL_16:
      wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(string);
      return (unsigned int)v4;
    }
LABEL_11:
    v14 = (_QWORD *)wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::release(
                      string,
                      v20);
    v15 = v14;
    if ( a1 != v14 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        a1,
        *v14);
      *v15 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(v20);
    wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(string);
    return 0;
  }
}

```

## disassembly

```asm
0x18000a3ec  mov     [rsp-8+arg_10], rbx
0x18000a3f1  mov     [rsp-8+arg_18], rsi
0x18000a3f6  push    rbp
0x18000a3f7  push    rdi
0x18000a3f8  push    r14
0x18000a3fa  lea     rbp, [rsp-160h]
0x18000a402  sub     rsp, 260h
0x18000a409  mov     rax, cs:__security_cookie
0x18000a410  xor     rax, rsp
0x18000a413  mov     [rbp+170h+var_20], rax
0x18000a41a  mov     r14, rdx
0x18000a41d  mov     rsi, rcx
0x18000a420  xorps   xmm0, xmm0
0x18000a423  movdqu  xmmword ptr [rsp+270h+string], xmm0
0x18000a429  mov     [rsp+270h+var_238], 0
0x18000a432  xor     edx, edx; Val
0x18000a434  mov     r8d, 200h; Size
0x18000a43a  lea     rcx, [rsp+270h+sourceString]; void *
0x18000a43f  call    memset_0
0x18000a444  mov     qword ptr [rsp+270h+var_250], 0; int
0x18000a44d  lea     r9, [rsp+270h+var_250]
0x18000a452  mov     edi, 100h
0x18000a457  mov     r8d, edi
0x18000a45a  lea     rdx, [rsp+270h+sourceString]
0x18000a45f  mov     rcx, r14
0x18000a462  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000a467  mov     ebx, eax
0x18000a469  test    eax, eax
0x18000a46b  js      loc_18000A57F
0x18000a471  mov     rax, qword ptr [rsp+270h+var_250]
0x18000a476  cmp     rax, rdi
0x18000a479  ja      short loc_18000A4B6
0x18000a47b  lea     r8, [rax-1]; length
0x18000a47f  lea     rdx, [rsp+270h+sourceString]; sourceString
0x18000a484  lea     rcx, [rsp+270h+string]; string
0x18000a489  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000a48e  mov     ebx, eax
0x18000a490  test    eax, eax
0x18000a492  jns     loc_18000A51D
0x18000a498  mov     rcx, [rbp+178h]; this
0x18000a49f  mov     r9d, eax; char *
0x18000a4a2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a4a9  lea     edx, [rdi+6Fh]; void *
0x18000a4ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4b1  jmp     loc_18000A57F
0x18000a4b6  mov     rbx, rax
0x18000a4b9  lea     r8, [rax-1]; length
0x18000a4bd  xor     edx, edx; sourceString
0x18000a4bf  lea     rcx, [rsp+270h+string]; string
0x18000a4c4  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000a4c9  mov     edi, eax
0x18000a4cb  test    eax, eax
0x18000a4cd  js      loc_18000A58D
0x18000a4d3  lea     r9, [rsp+270h+var_250]
0x18000a4d8  mov     r8, rbx
0x18000a4db  mov     rdx, [rsp+270h+var_238]
0x18000a4e0  mov     rcx, r14
0x18000a4e3  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000a4e8  test    eax, eax
0x18000a4ea  js      loc_18000A57D
0x18000a4f0  mov     rax, qword ptr [rsp+270h+var_250]
0x18000a4f5  cmp     rax, rbx
0x18000a4f8  jnb     short loc_18000A51B
0x18000a4fa  lea     r8, [rax-1]; length
0x18000a4fe  mov     rdx, [rsp+270h+var_238]; sourceString
0x18000a503  lea     rcx, [rsp+270h+string]; string
0x18000a508  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000a50d  mov     edi, eax
0x18000a50f  test    eax, eax
0x18000a511  js      short loc_18000A55E
0x18000a513  mov     rax, qword ptr [rsp+270h+var_250]
0x18000a518  cmp     rax, rbx
0x18000a51b  ja      short loc_18000A4B6
0x18000a51d  lea     rdx, [rsp+270h+var_230]
0x18000a522  lea     rcx, [rsp+270h+string]
0x18000a527  call    ?release@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@XZ; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::release(void)
0x18000a52c  mov     rbx, rax
0x18000a52f  cmp     rsi, rax
0x18000a532  jz      short loc_18000A546
0x18000a534  mov     rdx, [rax]
0x18000a537  mov     rcx, rsi
0x18000a53a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18000a53f  mov     qword ptr [rbx], 0
0x18000a546  lea     rcx, [rsp+270h+var_230]
0x18000a54b  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18000a550  lea     rcx, [rsp+270h+string]
0x18000a555  call    ??1?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18000a55a  xor     eax, eax
0x18000a55c  jmp     short loc_18000A5B4
0x18000a55e  mov     rcx, [rbp+178h]; this
0x18000a565  mov     r9d, edi; char *
0x18000a568  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a56f  mov     edx, 182h; void *
0x18000a574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a579  mov     ebx, edi
0x18000a57b  jmp     short loc_18000A57F
0x18000a57d  mov     ebx, eax
0x18000a57f  lea     rcx, [rsp+270h+string]
0x18000a584  call    ??1?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18000a589  mov     eax, ebx
0x18000a58b  jmp     short loc_18000A5B4
0x18000a58d  mov     rcx, [rbp+178h]; this
0x18000a594  mov     r9d, edi; char *
0x18000a597  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a59e  mov     edx, 17Ah; void *
0x18000a5a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5a8  lea     rcx, [rsp+270h+string]
0x18000a5ad  call    ??1?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18000a5b2  mov     eax, edi
0x18000a5b4  mov     rcx, [rbp+170h+var_20]
0x18000a5bb  xor     rcx, rsp; StackCookie
0x18000a5be  call    __security_check_cookie
0x18000a5c3  lea     r11, [rsp+270h+var_10]
0x18000a5cb  mov     rbx, [r11+30h]
0x18000a5cf  mov     rsi, [r11+38h]
0x18000a5d3  mov     rsp, r11
0x18000a5d6  pop     r14
0x18000a5d8  pop     rdi
0x18000a5d9  pop     rbp
0x18000a5da  retn
```
