# OleClassInfoVerbIterator::Next(IOleVerb * *)

- ea: `0x1800c1cf0`
- end: `0x1800c1fae`
- name: `?Next@OleClassInfoVerbIterator@@UEAAJPEAPEAUIOleVerb@@@Z`
- size: `702`
- prototype: `HRESULT __fastcall(OleClassInfoVerbIterator *this, IOleVerb **ppVerb)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800185ec`
- `0x18001b0e4`
- `0x1800500c0`
- `0x180098a48`
- `0x180098bc0`
- `0x1800c0164`
- `0x1800c1cf0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1da9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1de4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1eab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1ee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1da9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1de4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1eab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1ee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1f85`

## string_xrefs

- `0x1800c1d37`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800c1d7f`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800c1dcc`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800c1e68`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800c1ed1`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`

## pseudocode

```c
__int64 __fastcall OleClassInfoVerbIterator::Next(OleClassInfoVerbIterator *this, IOleVerb **ppVerb)
{
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *m_ptr; // rcx
  HRESULT v5; // ebx
  unsigned int v6; // edx
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *v7; // rcx
  HRESULT v8; // eax
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *v9; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  HRESULT v11; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT v13; // r15d
  bool v14; // r8
  bool v15; // r9
  IInspectable *v16; // rbx
  HRESULT hrState; // edi
  IInspectable *v18; // rcx
  HRESULT v19; // eax
  HRESULT String; // eax
  unsigned int v21; // edx
  HSTRING__ *hstr; // [rsp+30h] [rbp-48h] BYREF
  HSTRING__ *v24; // [rsp+38h] [rbp-40h] BYREF
  IResourceContext *p_verbPropValue; // [rsp+40h] [rbp-38h] BYREF
  IInspectable *pI; // [rsp+48h] [rbp-30h] BYREF
  RoVariant v27; // [rsp+50h] [rbp-28h] BYREF
  RoVariant verbPropValue; // [rsp+60h] [rbp-18h] BYREF
  void *retaddr; // [rsp+B8h] [rbp+40h]
  unsigned __int8 hasCurrent; // [rsp+C0h] [rbp+48h] BYREF
  Microsoft::WRL::Wrappers::HString verbId; // [rsp+C8h] [rbp+50h] BYREF
  Microsoft::WRL::Wrappers::HString verbValue; // [rsp+D0h] [rbp+58h] BYREF
  wil::com_ptr_t<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,wil::err_returncode_policy> verbPair; // [rsp+D8h] [rbp+60h] BYREF

  *ppVerb = 0;
  m_ptr = this->m_verbIterator.m_ptr;
  hasCurrent = 0;
  v5 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))m_ptr->lpVtbl[2].AddRef)(
         m_ptr,
         &hasCurrent);
  if ( v5 >= 0 )
  {
    if ( !hasCurrent )
    {
      v5 = -2147024637;
      v6 = 1004;
      goto LABEL_3;
    }
    v7 = this->m_verbIterator.m_ptr;
    verbPair.m_ptr = 0;
    v8 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, wil::com_ptr_t<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,wil::err_returncode_policy> *))v7->lpVtbl[2].QueryInterface)(
           v7,
           &verbPair);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x3EFu,
        "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
        v8);
LABEL_22:
      wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&verbPair);
      return (unsigned int)v5;
    }
    v9 = verbPair.m_ptr;
    verbId.hstr_ = 0;
    QueryInterface = verbPair.m_ptr->lpVtbl[2].QueryInterface;
    WindowsDeleteString(0);
    verbId.hstr_ = 0;
    v11 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *, Microsoft::WRL::Wrappers::HString *))QueryInterface)(
            v9,
            &verbId);
    v5 = v11;
    if ( v11 >= 0 )
    {
      verbPropValue._pI = 0;
      verbPropValue._hrState = 0;
      lpVtbl = verbPair.m_ptr->lpVtbl;
      p_verbPropValue = (IResourceContext *)&verbPropValue;
      pI = 0;
      v13 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *, IInspectable **))lpVtbl[2].AddRef)(
              verbPair.m_ptr,
              &pI);
      RoVariant::RoVariant(&v27, pI, v14, v15);
      v16 = v27._pI;
      hrState = v27._hrState;
      v27._pI = 0;
      v27._hrState = 0;
      RoVariant::~RoVariant(&v27);
      v18 = verbPropValue._pI;
      verbPropValue._pI = v16;
      v19 = verbPropValue._hrState;
      v27._pI = v18;
      verbPropValue._hrState = hrState;
      v27._hrState = v19;
      RoVariant::~RoVariant(&v27);
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0x3F5u,
          "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
          v13);
        RoVariant::~RoVariant(&verbPropValue);
        WindowsDeleteString(verbId.hstr_);
        v5 = v13;
        goto LABEL_21;
      }
      v27 = verbPropValue;
      verbValue.hstr_ = 0;
      WindowsDeleteString(0);
      verbValue.hstr_ = 0;
      String = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v27, &verbValue.hstr_);
      v5 = String;
      if ( String >= 0 )
      {
        String = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))this->m_verbIterator.m_ptr->lpVtbl[2].Release)(
                   this->m_verbIterator.m_ptr,
                   &hasCurrent);
        v5 = String;
        if ( String >= 0 )
        {
          hstr = verbValue.hstr_;
          v24 = verbId.hstr_;
          p_verbPropValue = this->m_resourceContext.m_ptr;
          v27._pI = (IInspectable *)this->m_resourceManager.m_ptr;
          String = Microsoft::WRL::Details::MakeAndInitialize<OleClassInfoVerb,IOleVerb,IMrtResourceManager *,IResourceContext *,HSTRING__ *,HSTRING__ *>(
                     ppVerb,
                     (IMrtResourceManager **)&v27,
                     &p_verbPropValue,
                     &v24,
                     &hstr);
          v5 = String;
          if ( String >= 0 )
          {
            WindowsDeleteString(verbValue.hstr_);
            verbValue.hstr_ = 0;
            RoVariant::~RoVariant(&verbPropValue);
            WindowsDeleteString(verbId.hstr_);
            v5 = 0;
            goto LABEL_21;
          }
          v21 = 1020;
        }
        else
        {
          v21 = 1018;
        }
      }
      else
      {
        v21 = 1016;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        v21,
        "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
        String);
      WindowsDeleteString(verbValue.hstr_);
      verbValue.hstr_ = 0;
      RoVariant::~RoVariant(&verbPropValue);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x3F2u,
        "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
        v11);
    }
    WindowsDeleteString(verbId.hstr_);
LABEL_21:
    verbId.hstr_ = 0;
    goto LABEL_22;
  }
  v6 = 1003;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    v6,
    "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
    v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c1cf0  push    rbp
0x1800c1cf2  push    rbx
0x1800c1cf3  push    rsi
0x1800c1cf4  push    rdi
0x1800c1cf5  push    r12
0x1800c1cf7  push    r13
0x1800c1cf9  push    r14
0x1800c1cfb  push    r15
0x1800c1cfd  mov     rbp, rsp
0x1800c1d00  sub     rsp, 78h
0x1800c1d04  xor     r13d, r13d
0x1800c1d07  mov     r14, this
0x1800c1d0a  mov     [ppVerb], r13
0x1800c1d0d  mov     r12, ppVerb
0x1800c1d10  mov     this, [this+20h]
0x1800c1d14  lea     ppVerb, [rbp+hasCurrent]
0x1800c1d18  mov     [rbp+hasCurrent], r13b
0x1800c1d1c  mov     rax, [this]
0x1800c1d1f  mov     rax, [rax+38h]
0x1800c1d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d28  mov     ebx, eax
0x1800c1d2a  test    eax, eax
0x1800c1d2c  jns     short loc_1800C1D4B
0x1800c1d2e  mov     edx, 3EBh; lineNumber
0x1800c1d33  mov     this, [rbp+40h]; callerReturnAddress
0x1800c1d37  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800c1d3e  mov     r9d, ebx; hr
0x1800c1d41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1d46  jmp     loc_1800C1F9B
0x1800c1d4b  cmp     [rbp+hasCurrent], r13b
0x1800c1d4f  jnz     short loc_1800C1D5D
0x1800c1d51  mov     ebx, 80070103h
0x1800c1d56  mov     edx, 3ECh
0x1800c1d5b  jmp     short loc_1800C1D33
0x1800c1d5d  mov     this, [r14+20h]
0x1800c1d61  lea     ppVerb, [rbp+verbPair]
0x1800c1d65  mov     [rbp+verbPair.m_ptr], r13
0x1800c1d69  mov     rax, [this]
0x1800c1d6c  mov     rax, [rax+30h]
0x1800c1d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d75  mov     ebx, eax
0x1800c1d77  test    eax, eax
0x1800c1d79  jns     short loc_1800C1D98
0x1800c1d7b  mov     this, [rbp+40h]; callerReturnAddress
0x1800c1d7f  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800c1d86  mov     r9d, eax; hr
0x1800c1d89  mov     edx, 3EFh; lineNumber
0x1800c1d8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1d93  jmp     loc_1800C1F92
0x1800c1d98  mov     rdi, [rbp+verbPair.m_ptr]
0x1800c1d9c  xor     ecx, ecx; string
0x1800c1d9e  mov     [rbp+verbId.hstr_], r13
0x1800c1da2  mov     rax, [rdi]
0x1800c1da5  mov     rbx, [rax+30h]
0x1800c1da9  call    cs:__imp_WindowsDeleteString
0x1800c1daf  lea     ppVerb, [rbp+verbId]
0x1800c1db3  mov     [rbp+verbId.hstr_], r13
0x1800c1db7  mov     this, rdi
0x1800c1dba  mov     rax, rbx
0x1800c1dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1dc2  mov     ebx, eax
0x1800c1dc4  test    eax, eax
0x1800c1dc6  jns     short loc_1800C1DEF
0x1800c1dc8  mov     this, [rbp+40h]; callerReturnAddress
0x1800c1dcc  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800c1dd3  mov     r9d, eax; hr
0x1800c1dd6  mov     edx, 3F2h; lineNumber
0x1800c1ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1de0  mov     this, [rbp+verbId.hstr_]; string
0x1800c1de4  call    cs:__imp_WindowsDeleteString
0x1800c1dea  jmp     loc_1800C1F8E
0x1800c1def  mov     this, [rbp+verbPair.m_ptr]
0x1800c1df3  lea     ppVerb, [rbp+verbPropValue]
0x1800c1df7  mov     [rbp+verbPropValue._pI], r13
0x1800c1dfb  mov     [rbp+verbPropValue._hrState], r13d
0x1800c1dff  mov     rax, [this]
0x1800c1e02  mov     [rbp+var_38], ppVerb
0x1800c1e06  lea     ppVerb, [rbp+pI]
0x1800c1e0a  mov     [rbp+pI], r13
0x1800c1e0e  mov     rax, [rax+38h]
0x1800c1e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1e17  mov     ppVerb, [rbp+pI]; pI
0x1800c1e1b  lea     this, [rbp+var_28]; this
0x1800c1e1f  mov     rsi, [rbp+var_38]
0x1800c1e23  mov     r15d, eax
0x1800c1e26  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x1800c1e2b  mov     rbx, [rbp+var_28._pI]
0x1800c1e2f  lea     this, [rbp+var_28]; this
0x1800c1e33  mov     edi, [rbp+var_28._hrState]
0x1800c1e36  mov     [rbp+var_28._pI], r13
0x1800c1e3a  mov     [rbp+var_28._hrState], r13d
0x1800c1e3e  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800c1e43  mov     this, [rsi]
0x1800c1e46  mov     [rsi], rbx
0x1800c1e49  mov     eax, [rsi+8]
0x1800c1e4c  mov     [rbp+var_28._pI], this
0x1800c1e50  lea     this, [rbp+var_28]; this
0x1800c1e54  mov     [rsi+8], edi
0x1800c1e57  mov     [rbp+var_28._hrState], eax
0x1800c1e5a  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800c1e5f  test    r15d, r15d
0x1800c1e62  jns     short loc_1800C1E97
0x1800c1e64  mov     this, [rbp+40h]; callerReturnAddress
0x1800c1e68  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800c1e6f  mov     r9d, r15d; hr
0x1800c1e72  mov     edx, 3F5h; lineNumber
0x1800c1e77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1e7c  lea     this, [rbp+verbPropValue]; this
0x1800c1e80  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800c1e85  mov     this, [rbp+verbId.hstr_]; string
0x1800c1e89  call    cs:__imp_WindowsDeleteString
0x1800c1e8f  mov     ebx, r15d
0x1800c1e92  jmp     loc_1800C1F8E
0x1800c1e97  mov     rax, [rbp+verbPropValue._pI]
0x1800c1e9b  xor     ecx, ecx; string
0x1800c1e9d  mov     [rbp+var_28._pI], rax
0x1800c1ea1  mov     eax, [rbp+verbPropValue._hrState]
0x1800c1ea4  mov     [rbp+var_28._hrState], eax
0x1800c1ea7  mov     [rbp+verbValue.hstr_], r13
0x1800c1eab  call    cs:__imp_WindowsDeleteString
0x1800c1eb1  lea     ppVerb, [rbp+verbValue]; value
0x1800c1eb5  mov     [rbp+verbValue.hstr_], r13
0x1800c1eb9  lea     this, [rbp+var_28]; this
0x1800c1ebd  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x1800c1ec2  mov     ebx, eax
0x1800c1ec4  test    eax, eax
0x1800c1ec6  jns     short loc_1800C1EFC
0x1800c1ec8  mov     edx, 3F8h; lineNumber
0x1800c1ecd  mov     this, [rbp+40h]; callerReturnAddress
0x1800c1ed1  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800c1ed8  mov     r9d, eax; hr
0x1800c1edb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1ee0  mov     this, [rbp+verbValue.hstr_]; string
0x1800c1ee4  call    cs:__imp_WindowsDeleteString
0x1800c1eea  lea     this, [rbp+verbPropValue]; this
0x1800c1eee  mov     [rbp+verbValue.hstr_], r13
0x1800c1ef2  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800c1ef7  jmp     loc_1800C1DE0
0x1800c1efc  mov     this, [r14+20h]
0x1800c1f00  lea     ppVerb, [rbp+hasCurrent]
0x1800c1f04  mov     rax, [this]
0x1800c1f07  mov     rax, [rax+40h]
0x1800c1f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1f10  mov     ebx, eax
0x1800c1f12  test    eax, eax
0x1800c1f14  jns     short loc_1800C1F1D
0x1800c1f16  mov     edx, 3FAh
0x1800c1f1b  jmp     short loc_1800C1ECD
0x1800c1f1d  mov     rax, [rbp+verbValue.hstr_]
0x1800c1f21  lea     r9, [rbp+var_40]; <args_2>
0x1800c1f25  mov     [rbp+var_48], rax
0x1800c1f29  lea     r8, [rbp+var_38]; <args_1>
0x1800c1f2d  mov     rax, [rbp+verbId.hstr_]
0x1800c1f31  lea     ppVerb, [rbp+var_28]; <args_0>
0x1800c1f35  mov     [rbp+var_40], rax
0x1800c1f39  mov     this, r12; result
0x1800c1f3c  mov     rax, [r14+18h]
0x1800c1f40  mov     [rbp+var_38], rax
0x1800c1f44  mov     rax, [r14+10h]
0x1800c1f48  mov     [rbp+var_28._pI], rax
0x1800c1f4c  lea     rax, [rbp+var_48]
0x1800c1f50  mov     [rsp+78h+var_58], rax; <args_3>
0x1800c1f55  call    ??$MakeAndInitialize@VOleClassInfoVerb@@UIOleVerb@@PEAUIMrtResourceManager@@PEAUIResourceContext@@PEAUHSTRING__@@PEAU5@@Details@WRL@Microsoft@@YAJPEAPEAUIOleVerb@@$$QEAPEAUIMrtResourceManager@@$$QEAPEAUIResourceContext@@$$QEAPEAUHSTRING__@@3@Z; Microsoft::WRL::Details::MakeAndInitialize<OleClassInfoVerb,IOleVerb,IMrtResourceManager *,IResourceContext *,HSTRING__ *,HSTRING__ *>(IOleVerb * *,IMrtResourceManager * &&,IResourceContext * &&,HSTRING__ * &&,HSTRING__ * &&)
0x1800c1f5a  mov     ebx, eax
0x1800c1f5c  test    eax, eax
0x1800c1f5e  jns     short loc_1800C1F6A
0x1800c1f60  mov     edx, 3FCh
0x1800c1f65  jmp     loc_1800C1ECD
0x1800c1f6a  mov     this, [rbp+verbValue.hstr_]; string
0x1800c1f6e  call    cs:__imp_WindowsDeleteString
0x1800c1f74  lea     this, [rbp+verbPropValue]; this
0x1800c1f78  mov     [rbp+verbValue.hstr_], r13
0x1800c1f7c  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800c1f81  mov     this, [rbp+verbId.hstr_]; string
0x1800c1f85  call    cs:__imp_WindowsDeleteString
0x1800c1f8b  mov     ebx, r13d
0x1800c1f8e  mov     [rbp+verbId.hstr_], r13
0x1800c1f92  lea     this, [rbp+verbPair]; this
0x1800c1f96  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x1800c1f9b  mov     eax, ebx
0x1800c1f9d  add     rsp, 78h
0x1800c1fa1  pop     r15
0x1800c1fa3  pop     r14
0x1800c1fa5  pop     r13
0x1800c1fa7  pop     r12
0x1800c1fa9  pop     rdi
0x1800c1faa  pop     rsi
0x1800c1fab  pop     rbx
0x1800c1fac  pop     rbp
0x1800c1fad  retn
```
