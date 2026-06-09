# CreateObjectServerTaskBase::Start(IUnknown *,ushort *)

- ea: `0x140008a10`
- end: `0x140008b1a`
- name: `?Start@CreateObjectServerTaskBase@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `266`
- prototype: `__int64 __fastcall(CreateObjectServerTaskBase *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140004340`
- `0x140004d74`
- `0x1400068c4`
- `0x140007158`
- `0x1400072ec`
- `0x140007fec`
- `0x140008a10`
- `0x14000a010`

## string_xrefs

- `0x140008a62`: `onecoreuap\internal\shell\inc\private\createobjectservertaskbase.h`
- `0x140008abe`: `onecoreuap\internal\shell\inc\private\createobjectservertaskbase.h`

## pseudocode

```c
__int64 __fastcall CreateObjectServerTaskBase::Start(
        CreateObjectServerTaskBase *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  int v11[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF
  CreateObjectServerTaskBase *v14; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         &v13);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v14 = this;
    Microsoft::WRL::ComPtr<ITaskHandler>::InternalAddRef(&v14);
    v8 = _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::_lambda_ea734d1cec1fa7b22a66fb865ad05d37_(v11, this, &v14, &v13);
    v7 = Windows::Internal::ComTaskPool::QueueTask<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(v9, v8);
    _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::~_lambda_ea734d1cec1fa7b22a66fb865ad05d37_((_lambda_ea734d1cec1fa7b22a66fb865ad05d37_ *)v11);
    if ( v7 >= 0 )
    {
      if ( this )
        (*(void (__fastcall **)(CreateObjectServerTaskBase *))(*(_QWORD *)this + 16LL))(this);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\createobjectservertaskbase.h",
        (const char *)(unsigned int)v7,
        v11[0]);
      if ( this )
        (*(void (__fastcall **)(CreateObjectServerTaskBase *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\createobjectservertaskbase.h",
      (const char *)(unsigned int)v6,
      v11[0]);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008a10  mov     r11, rsp
0x140008a13  mov     [r11+8], rbx
0x140008a17  mov     [r11+18h], rsi
0x140008a1b  push    rdi
0x140008a1c  sub     rsp, 40h
0x140008a20  mov     rdi, rdx
0x140008a23  mov     rsi, rcx
0x140008a26  mov     qword ptr [r11+10h], 0
0x140008a2e  mov     rax, [rdx]
0x140008a31  mov     rbx, [rax]
0x140008a34  lea     rcx, [r11+10h]
0x140008a38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008a3d  lea     r8, [rsp+48h+arg_8]
0x140008a42  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x140008a49  mov     rcx, rdi
0x140008a4c  mov     rax, rbx
0x140008a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a54  mov     ebx, eax
0x140008a56  test    eax, eax
0x140008a58  jns     short loc_140008A78
0x140008a5a  mov     rcx, [rsp+48h]; this
0x140008a5f  mov     r9d, eax; char *
0x140008a62  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x140008a69  mov     edx, 1Bh; void *
0x140008a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008a73  jmp     loc_140008AFE
0x140008a78  mov     [rsp+48h+arg_18], rsi
0x140008a7d  lea     rcx, [rsp+48h+arg_18]
0x140008a82  call    ?InternalAddRef@?$ComPtr@UITaskHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ITaskHandler>::InternalAddRef(void)
0x140008a87  lea     r9, [rsp+48h+arg_8]
0x140008a8c  lea     r8, [rsp+48h+arg_18]
0x140008a91  mov     rdx, rsi
0x140008a94  lea     rcx, [rsp+48h+var_28]
0x140008a99  call    ??0_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@QEAA@PEAVCreateObjectServerTaskBase@@AEBV?$ComPtr@UITaskHandler@@@WRL@Microsoft@@AEBV?$ComPtr@UITaskHandlerStatus@@@34@@Z; _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::_lambda_ea734d1cec1fa7b22a66fb865ad05d37_(CreateObjectServerTaskBase *,Microsoft::WRL::ComPtr<ITaskHandler> const &,Microsoft::WRL::ComPtr<ITaskHandlerStatus> const &)
0x140008a9e  mov     rdx, rax
0x140008aa1  call    ??$QueueTask@V_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_ea734d1cec1fa7b22a66fb865ad05d37_>(Windows::Internal::TaskApartment,_lambda_ea734d1cec1fa7b22a66fb865ad05d37_ &&)
0x140008aa6  mov     ebx, eax
0x140008aa8  lea     rcx, [rsp+48h+var_28]; this
0x140008aad  call    ??1_lambda_ea734d1cec1fa7b22a66fb865ad05d37_@@QEAA@XZ; _lambda_ea734d1cec1fa7b22a66fb865ad05d37_::~_lambda_ea734d1cec1fa7b22a66fb865ad05d37_(void)
0x140008ab2  test    ebx, ebx
0x140008ab4  jns     short loc_140008AE7
0x140008ab6  mov     rcx, [rsp+48h]; this
0x140008abb  mov     r9d, ebx; char *
0x140008abe  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x140008ac5  mov     edx, 41h ; 'A'; void *
0x140008aca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008acf  nop
0x140008ad0  test    rsi, rsi
0x140008ad3  jz      short loc_140008AE5
0x140008ad5  mov     rax, [rsi]
0x140008ad8  mov     rcx, rsi
0x140008adb  mov     rax, [rax+10h]
0x140008adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ae4  nop
0x140008ae5  jmp     short loc_140008AFE
0x140008ae7  test    rsi, rsi
0x140008aea  jz      short loc_140008AFC
0x140008aec  mov     rax, [rsi]
0x140008aef  mov     rcx, rsi
0x140008af2  mov     rax, [rax+10h]
0x140008af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008afb  nop
0x140008afc  xor     ebx, ebx
0x140008afe  lea     rcx, [rsp+48h+arg_8]
0x140008b03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008b08  mov     eax, ebx
0x140008b0a  mov     rbx, [rsp+48h+arg_0]
0x140008b0f  mov     rsi, [rsp+48h+arg_10]
0x140008b14  add     rsp, 40h
0x140008b18  pop     rdi
0x140008b19  retn
```
