# Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18001f160`
- end: `0x18001f201`
- name: `?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `161`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012444`
- `0x18001ec98`
- `0x18001ee10`
- `0x18001f208`
- `0x18001f4d0`
- `0x18001f59c`
- `0x18001f668`
- `0x18001f7e0`

## callees

- `0x18000907c`
- `0x18000ddc4`
- `0x18001892c`
- `0x18001f160`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001f186`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001f186`

## string_xrefs

- `0x18001f1cd`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::GetClientProcessHandle(__int64 a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  void *v5; // rdi
  __int64 (__fastcall *v6)(void *, __int64, __int64); // rbx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  v2 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &v10);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = v10;
    v6 = *(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v10 + 24LL);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1,
      0);
    v2 = v6(v5, 4096, a1);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v3 = 0;
      goto LABEL_7;
    }
    v4 = 28;
  }
  else
  {
    v4 = 25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
    (const char *)(unsigned int)v2,
    v8);
LABEL_7:
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v10);
  return v3;
}

```

## disassembly

```asm
0x18001f160  mov     rax, rsp
0x18001f163  mov     [rax+8], rbx
0x18001f167  mov     [rax+18h], rsi
0x18001f16b  push    rdi; int
0x18001f16c  sub     rsp, 20h
0x18001f170  mov     rsi, rcx
0x18001f173  mov     qword ptr [rax+10h], 0
0x18001f17b  lea     rdx, [rax+10h]; ppInterface
0x18001f17f  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18001f186  call    cs:__imp_CoGetCallContext
0x18001f18c  mov     ebx, eax
0x18001f18e  test    eax, eax
0x18001f190  jns     short loc_18001F199
0x18001f192  mov     edx, 19h
0x18001f197  jmp     short loc_18001F1CD
0x18001f199  mov     rdi, [rsp+28h+arg_8]
0x18001f19e  mov     rax, [rdi]
0x18001f1a1  mov     rbx, [rax+18h]
0x18001f1a5  xor     edx, edx
0x18001f1a7  mov     rcx, rsi
0x18001f1aa  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001f1af  mov     r8, rsi
0x18001f1b2  mov     edx, 1000h
0x18001f1b7  mov     rcx, rdi
0x18001f1ba  mov     rax, rbx
0x18001f1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1c2  mov     ebx, eax
0x18001f1c4  test    eax, eax
0x18001f1c6  jns     short loc_18001F1E3
0x18001f1c8  mov     edx, 1Ch; void *
0x18001f1cd  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f1d4  mov     r9d, eax; char *
0x18001f1d7  mov     rcx, [rsp+28h]; this
0x18001f1dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1e1  jmp     short loc_18001F1E5
0x18001f1e3  xor     ebx, ebx
0x18001f1e5  lea     rcx, [rsp+28h+arg_8]
0x18001f1ea  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001f1ef  mov     eax, ebx
0x18001f1f1  mov     rbx, [rsp+28h+arg_0]
0x18001f1f6  mov     rsi, [rsp+28h+arg_10]
0x18001f1fb  add     rsp, 20h
0x18001f1ff  pop     rdi
0x18001f200  retn
```
