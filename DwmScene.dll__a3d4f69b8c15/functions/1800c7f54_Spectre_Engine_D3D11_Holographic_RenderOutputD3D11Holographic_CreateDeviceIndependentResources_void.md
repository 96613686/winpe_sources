# Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic::CreateDeviceIndependentResources(void)

- ea: `0x1800c7f54`
- end: `0x1800c8007`
- name: `?CreateDeviceIndependentResources@RenderOutputD3D11Holographic@Holographic@D3D11@Engine@Spectre@@AEAAXXZ`
- size: `179`
- prototype: `void __fastcall(Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c8010`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000fe40`
- `0x1800c7f54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c7fe8`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c7fe8`
- `d2d1!__imp_D2D1CreateFactory` at `0x1800c7f9d`
- `d2d1!__imp_D2D1CreateFactory` at `0x1800c7f9d`

## pseudocode

```c
void __fastcall Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic::CreateDeviceIndependentResources(
        Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic *this)
{
  void **v1; // rbx
  HRESULT v2; // eax
  ULONG_PTR v3; // rbx
  D2D1_FACTORY_OPTIONS pFactoryOptions; // [rsp+20h] [rbp-C8h] BYREF
  EXCEPTION_RECORD pExceptionRecord; // [rsp+30h] [rbp-B8h] BYREF
  void *retaddr; // [rsp+E8h] [rbp+0h]

  v1 = (void **)((char *)this + 512);
  if ( !*((_QWORD *)this + 64) )
  {
    pFactoryOptions.debugLevel = D2D1_DEBUG_LEVEL_NONE;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 512);
    v2 = D2D1CreateFactory(
           D2D1_FACTORY_TYPE_SINGLE_THREADED,
           &GUID_94f81a73_9212_4376_9c58_b16a3a0d3992,
           &pFactoryOptions,
           v1);
    v3 = v2;
    if ( v2 < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v3;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x1800c7f54  push    rbx
0x1800c7f56  sub     rsp, 0E0h
0x1800c7f5d  mov     rax, cs:__security_cookie
0x1800c7f64  xor     rax, rsp
0x1800c7f67  mov     [rsp+0E8h+var_18], rax
0x1800c7f6f  lea     rbx, [rcx+200h]
0x1800c7f76  cmp     qword ptr [rbx], 0
0x1800c7f7a  jnz     short loc_1800C7FEE
0x1800c7f7c  mov     rcx, rbx
0x1800c7f7f  mov     [rsp+0E8h+pFactoryOptions.debugLevel], 0
0x1800c7f87  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c7f8c  mov     r9, rbx; ppIFactory
0x1800c7f8f  lea     r8, [rsp+0E8h+pFactoryOptions]; pFactoryOptions
0x1800c7f94  lea     rdx, _GUID_94f81a73_9212_4376_9c58_b16a3a0d3992; riid
0x1800c7f9b  xor     ecx, ecx; factoryType
0x1800c7f9d  call    cs:__imp_D2D1CreateFactory
0x1800c7fa3  movsxd  rbx, eax
0x1800c7fa6  test    eax, eax
0x1800c7fa8  jns     short loc_1800C7FEE
0x1800c7faa  xor     edx, edx; Val
0x1800c7fac  lea     rcx, [rsp+0E8h+pExceptionRecord]; void *
0x1800c7fb1  mov     r8d, 98h; Size
0x1800c7fb7  call    memset_0
0x1800c7fbc  mov     rcx, [rsp+0E8h]
0x1800c7fc4  xor     r8d, r8d; dwFlags
0x1800c7fc7  mov     [rsp+0E8h+pExceptionRecord.ExceptionAddress], rcx
0x1800c7fcc  xor     edx, edx; pContextRecord
0x1800c7fce  lea     rcx, [rsp+0E8h+pExceptionRecord]; pExceptionRecord
0x1800c7fd3  mov     [rsp+0E8h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800c7fdb  mov     [rsp+0E8h+pExceptionRecord.NumberParameters], 1
0x1800c7fe3  mov     [rsp+0E8h+pExceptionRecord.ExceptionInformation], rbx
0x1800c7fe8  call    cs:__imp_RaiseFailFastException
0x1800c7fee  mov     rcx, [rsp+0E8h+var_18]
0x1800c7ff6  xor     rcx, rsp; StackCookie
0x1800c7ff9  call    __security_check_cookie
0x1800c7ffe  add     rsp, 0E0h
0x1800c8005  pop     rbx
0x1800c8006  retn
```
