# Spectre::Engine::D3D11::RenderOutputD3D11Gdi::CreateRenderTarget(Microsoft::WRL::ComPtr<ID3D11Texture2D>)

- ea: `0x1800b9d20`
- end: `0x1800b9ed2`
- name: `?CreateRenderTarget@RenderOutputD3D11Gdi@D3D11@Engine@Spectre@@MEAAXV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@@Z`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000fe40`
- `0x180012680`
- `0x1800b8f04`
- `0x1800b9bf0`
- `0x1800b9d20`
- `0x1800ba38c`
- `0x1800ba45c`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b9dc3`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b9ea0`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b9dc3`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b9ea0`
- `d2d1!__imp_D2D1CreateFactory` at `0x1800b9df6`
- `d2d1!__imp_D2D1CreateFactory` at `0x1800b9df6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Spectre::Engine::D3D11::RenderOutputD3D11Gdi::CreateRenderTarget(void **this, _QWORD *a2)
{
  struct IDXGIObject **v4; // r15
  int v5; // eax
  ULONG_PTR v6; // rdi
  void *v7; // rsi
  __int64 (__fastcall *v8)(void *, struct IDXGIObject *, int *, void **); // rdi
  int v9; // eax
  ULONG_PTR v10; // rbx
  _QWORD v12[2]; // [rsp+30h] [rbp-D0h] BYREF
  EXCEPTION_RECORD pExceptionRecord; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v15; // [rsp+E4h] [rbp-1Ch]
  __int64 v16; // [rsp+ECh] [rbp-14h]
  __int64 v17; // [rsp+F4h] [rbp-Ch]
  void *retaddr; // [rsp+138h] [rbp+38h]

  v12[1] = a2;
  v12[0] = *a2;
  Microsoft::WRL::ComPtr<ID3D11ShaderResourceView>::InternalAddRef(v12);
  Spectre::Engine::D3D11::RenderOutputD3D11::CreateRenderTarget(this, v12);
  v4 = (struct IDXGIObject **)(this + 213);
  v5 = Microsoft::WRL::ComPtr<ID3D11Texture2D>::As<IDXGISurface1>(a2, this + 213);
  v6 = v5;
  if ( v5 < 0 )
  {
    memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
    pExceptionRecord.ExceptionCode = -532265403;
    pExceptionRecord.ExceptionAddress = retaddr;
    pExceptionRecord.NumberParameters = 1;
    pExceptionRecord.ExceptionInformation[0] = v6;
    RaiseFailFastException(&pExceptionRecord, 0, 0);
  }
  D3D11_SetDebugName(*v4, "BackBufferSurface");
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 215);
  D2D1CreateFactory(D2D1_FACTORY_TYPE_SINGLE_THREADED, &GUID_06152247_6f50_465a_9245_118bfd3b6007, 0, this + 215);
  v12[0] = (unsigned int)Spectre::Engine::D3D11::RenderOutputD3D11::GetDxgiFormat((Spectre::Engine::D3D11::RenderOutputD3D11 *)this)
         | 0x100000000LL;
  v14 = 0;
  v15 = v12[0];
  v16 = 0;
  v17 = 2;
  v7 = this[215];
  v8 = *(__int64 (__fastcall **)(void *, struct IDXGIObject *, int *, void **))(*(_QWORD *)v7 + 120LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 214);
  v9 = v8(v7, *v4, &v14, this + 214);
  v10 = v9;
  if ( v9 < 0 )
  {
    memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
    pExceptionRecord.ExceptionCode = -532265403;
    pExceptionRecord.ExceptionAddress = retaddr;
    pExceptionRecord.NumberParameters = 1;
    pExceptionRecord.ExceptionInformation[0] = v10;
    RaiseFailFastException(&pExceptionRecord, 0, 0);
  }
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
}

```

## disassembly

```asm
0x1800b9d20  mov     [rsp-8+arg_10], rbx
0x1800b9d25  push    rbp
0x1800b9d26  push    rsi
0x1800b9d27  push    rdi
0x1800b9d28  push    r14
0x1800b9d2a  push    r15
0x1800b9d2c  lea     rbp, [rsp-10h]
0x1800b9d31  sub     rsp, 110h
0x1800b9d38  mov     rax, cs:__security_cookie
0x1800b9d3f  xor     rax, rsp
0x1800b9d42  mov     [rbp+30h+var_30], rax
0x1800b9d46  mov     r14, rdx
0x1800b9d49  mov     rbx, rcx
0x1800b9d4c  mov     [rsp+130h+var_F8], rdx
0x1800b9d51  mov     rax, [rdx]
0x1800b9d54  mov     [rsp+130h+var_100], rax
0x1800b9d59  lea     rcx, [rsp+130h+var_100]
0x1800b9d5e  call    ?InternalAddRef@?$ComPtr@UID3D11ShaderResourceView@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ID3D11ShaderResourceView>::InternalAddRef(void)
0x1800b9d63  lea     rdx, [rsp+130h+var_100]
0x1800b9d68  mov     rcx, rbx
0x1800b9d6b  call    ?CreateRenderTarget@RenderOutputD3D11@D3D11@Engine@Spectre@@MEAAXV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@@Z; Spectre::Engine::D3D11::RenderOutputD3D11::CreateRenderTarget(Microsoft::WRL::ComPtr<ID3D11Texture2D>)
0x1800b9d70  lea     r15, [rbx+6A8h]
0x1800b9d77  mov     rdx, r15
0x1800b9d7a  mov     rcx, r14
0x1800b9d7d  call    ??$As@UIDXGISurface1@@@?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGISurface1@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Texture2D>::As<IDXGISurface1>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGISurface1>>)
0x1800b9d82  movsxd  rdi, eax
0x1800b9d85  test    eax, eax
0x1800b9d87  jns     short loc_1800B9DC9
0x1800b9d89  xor     edx, edx; Val
0x1800b9d8b  mov     r8d, 98h; Size
0x1800b9d91  lea     rcx, [rsp+130h+pExceptionRecord]; void *
0x1800b9d96  call    memset_0
0x1800b9d9b  mov     [rsp+130h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800b9da3  mov     rcx, [rbp+38h]
0x1800b9da7  mov     [rsp+130h+pExceptionRecord.ExceptionAddress], rcx
0x1800b9dac  mov     [rsp+130h+pExceptionRecord.NumberParameters], 1
0x1800b9db4  mov     [rsp+130h+pExceptionRecord.ExceptionInformation], rdi
0x1800b9db9  xor     r8d, r8d; dwFlags
0x1800b9dbc  xor     edx, edx; pContextRecord
0x1800b9dbe  lea     rcx, [rsp+130h+pExceptionRecord]; pExceptionRecord
0x1800b9dc3  call    cs:__imp_RaiseFailFastException
0x1800b9dc9  lea     rdx, aBackbuffersurf; "BackBufferSurface"
0x1800b9dd0  mov     rcx, [r15]; struct IDXGIObject *
0x1800b9dd3  call    ?D3D11_SetDebugName@@YAXPEAUIDXGIObject@@PEBD@Z; D3D11_SetDebugName(IDXGIObject *,char const *)
0x1800b9dd8  lea     rsi, [rbx+6B8h]
0x1800b9ddf  mov     rcx, rsi
0x1800b9de2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b9de7  mov     r9, rsi; ppIFactory
0x1800b9dea  xor     r8d, r8d; pFactoryOptions
0x1800b9ded  lea     rdx, _GUID_06152247_6f50_465a_9245_118bfd3b6007; riid
0x1800b9df4  xor     ecx, ecx; factoryType
0x1800b9df6  call    cs:__imp_D2D1CreateFactory
0x1800b9dfc  mov     rcx, rbx; this
0x1800b9dff  call    ?GetDxgiFormat@RenderOutputD3D11@D3D11@Engine@Spectre@@QEBA?AW4DXGI_FORMAT@@XZ; Spectre::Engine::D3D11::RenderOutputD3D11::GetDxgiFormat(void)
0x1800b9e04  mov     dword ptr [rsp+130h+var_100], eax
0x1800b9e08  mov     dword ptr [rsp+130h+var_100+4], 1
0x1800b9e10  mov     [rbp+30h+var_50], 0
0x1800b9e17  mov     rax, [rsp+130h+var_100]
0x1800b9e1c  mov     [rbp+30h+var_4C], rax
0x1800b9e20  mov     [rbp+30h+var_44], 0
0x1800b9e28  mov     [rbp+30h+var_3C], 2
0x1800b9e30  mov     rsi, [rsi]
0x1800b9e33  mov     rax, [rsi]
0x1800b9e36  mov     rdi, [rax+78h]
0x1800b9e3a  lea     rcx, [rbx+6B0h]
0x1800b9e41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b9e46  lea     r9, [rbx+6B0h]
0x1800b9e4d  lea     r8, [rbp+30h+var_50]
0x1800b9e51  mov     rdx, [r15]
0x1800b9e54  mov     rcx, rsi
0x1800b9e57  mov     rax, rdi
0x1800b9e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e5f  movsxd  rbx, eax
0x1800b9e62  test    eax, eax
0x1800b9e64  jns     short loc_1800B9EA7
0x1800b9e66  xor     edx, edx; Val
0x1800b9e68  mov     r8d, 98h; Size
0x1800b9e6e  lea     rcx, [rsp+130h+pExceptionRecord]; void *
0x1800b9e73  call    memset_0
0x1800b9e78  mov     [rsp+130h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800b9e80  mov     rdx, [rbp+38h]
0x1800b9e84  mov     [rsp+130h+pExceptionRecord.ExceptionAddress], rdx
0x1800b9e89  mov     [rsp+130h+pExceptionRecord.NumberParameters], 1
0x1800b9e91  mov     [rsp+130h+pExceptionRecord.ExceptionInformation], rbx
0x1800b9e96  xor     r8d, r8d; dwFlags
0x1800b9e99  xor     edx, edx; pContextRecord
0x1800b9e9b  lea     rcx, [rsp+130h+pExceptionRecord]; pExceptionRecord
0x1800b9ea0  call    cs:__imp_RaiseFailFastException
0x1800b9ea6  nop
0x1800b9ea7  mov     rcx, r14
0x1800b9eaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b9eaf  mov     rcx, [rbp+30h+var_30]
0x1800b9eb3  xor     rcx, rsp; StackCookie
0x1800b9eb6  call    __security_check_cookie
0x1800b9ebb  mov     rbx, [rsp+130h+arg_10]
0x1800b9ec3  add     rsp, 110h
0x1800b9eca  pop     r15
0x1800b9ecc  pop     r14
0x1800b9ece  pop     rdi
0x1800b9ecf  pop     rsi
0x1800b9ed0  pop     rbp
0x1800b9ed1  retn
```
