# Windows::Graphics::Capture::Server::DCompManager::MakeCaptureRenderTarget(IDCompositionCaptureRenderTargetInternal * *)

- ea: `0x18001ff68`
- end: `0x18001fff7`
- name: `?MakeCaptureRenderTarget@DCompManager@Server@Capture@Graphics@Windows@@QEAAJPEAPEAUIDCompositionCaptureRenderTargetInternal@@@Z`
- size: `143`
- prototype: `int(Windows::Graphics::Capture::Server::DCompManager *__hidden this, struct IDCompositionCaptureRenderTargetInternal **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ca68`

## callees

- `0x18000907c`
- `0x18000ddc4`
- `0x18001881c`
- `0x18001ff68`
- `0x180022010`

## string_xrefs

- `0x18001ffb5`: `onecoreuap\windows\dwm\capture\svc\dll\dcompmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::DCompManager::MakeCaptureRenderTarget(
        Windows::Graphics::Capture::Server::DCompManager *this,
        struct IDCompositionCaptureRenderTargetInternal **a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, struct IDCompositionCaptureRenderTargetInternal **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  struct IDCompositionCaptureRenderTargetInternal *v7; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct IDCompositionCaptureRenderTargetInternal *v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = 0;
  v3 = *((_QWORD *)this + 1);
  v4 = *(__int64 (__fastcall **)(__int64, struct IDCompositionCaptureRenderTargetInternal **))(*(_QWORD *)v3 + 80LL);
  wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(&v11);
  v5 = v4(v3, &v11);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v11;
    v11 = 0;
    *a2 = v7;
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\dcompmanager.cpp",
      (const char *)(unsigned int)v5,
      v9);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v11);
  return v6;
}

```

## disassembly

```asm
0x18001ff68  mov     r11, rsp
0x18001ff6b  mov     [r11+10h], rbx
0x18001ff6f  mov     [r11+18h], rsi
0x18001ff73  push    rdi; int
0x18001ff74  sub     rsp, 20h
0x18001ff78  mov     rsi, rdx
0x18001ff7b  mov     qword ptr [r11+8], 0
0x18001ff83  mov     rdi, [rcx+8]
0x18001ff87  mov     rax, [rdi]
0x18001ff8a  mov     rbx, [rax+50h]
0x18001ff8e  lea     rcx, [r11+8]
0x18001ff92  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x18001ff97  lea     rdx, [rsp+28h+arg_0]
0x18001ff9c  mov     rcx, rdi
0x18001ff9f  mov     rax, rbx
0x18001ffa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffa7  mov     ebx, eax
0x18001ffa9  test    eax, eax
0x18001ffab  jns     short loc_18001FFC8
0x18001ffad  mov     rcx, [rsp+28h]; this
0x18001ffb2  mov     r9d, eax; char *
0x18001ffb5  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ffbc  mov     edx, 4Ch ; 'L'; void *
0x18001ffc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffc6  jmp     short loc_18001FFDB
0x18001ffc8  mov     rax, [rsp+28h+arg_0]
0x18001ffcd  mov     [rsp+28h+arg_0], 0
0x18001ffd6  mov     [rsi], rax
0x18001ffd9  xor     ebx, ebx
0x18001ffdb  lea     rcx, [rsp+28h+arg_0]
0x18001ffe0  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001ffe5  mov     eax, ebx
0x18001ffe7  mov     rbx, [rsp+28h+arg_8]
0x18001ffec  mov     rsi, [rsp+28h+arg_10]
0x18001fff1  add     rsp, 20h
0x18001fff5  pop     rdi
0x18001fff6  retn
```
