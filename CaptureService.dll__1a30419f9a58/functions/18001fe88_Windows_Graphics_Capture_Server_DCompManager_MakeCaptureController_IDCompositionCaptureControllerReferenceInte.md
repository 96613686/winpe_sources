# Windows::Graphics::Capture::Server::DCompManager::MakeCaptureController(IDCompositionCaptureControllerReferenceInternal * *,void * *)

- ea: `0x18001fe88`
- end: `0x18001ff5f`
- name: `?MakeCaptureController@DCompManager@Server@Capture@Graphics@Windows@@QEAAJPEAPEAUIDCompositionCaptureControllerReferenceInternal@@PEAPEAX@Z`
- size: `215`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::DCompManager *__hidden this, struct IDCompositionCaptureControllerReferenceInternal **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ca68`

## callees

- `0x18000907c`
- `0x18000ddc4`
- `0x18000dec8`
- `0x18001fe88`
- `0x180022010`

## import_xrefs

- `dcomp!__imp_DCompositionCreateSharedResourceHandle` at `0x18001feb7`
- `dcomp!__imp_DCompositionCreateSharedResourceHandle` at `0x18001feb7`

## string_xrefs

- `0x18001fefc`: `onecoreuap\windows\dwm\capture\svc\dll\dcompmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Graphics::Capture::Server::DCompManager::MakeCaptureController(
        Windows::Graphics::Capture::Server::DCompManager *this,
        struct IDCompositionCaptureControllerReferenceInternal **a2,
        void **a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  struct IDCompositionCaptureControllerReferenceInternal *v9; // rax
  void *v10; // rax
  int v12; // [rsp+20h] [rbp-48h]
  __int64 v13[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  void *v15; // [rsp+88h] [rbp+20h] BYREF

  v13[0] = 0;
  v15 = 0;
  v6 = DCompositionCreateSharedResourceHandle(&GUID_44794289_3c85_445f_86ec_33d578f442b6, &v15);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, void *, GUID *, __int64 *))(**((_QWORD **)this + 2) + 232LL))(
           *((_QWORD *)this + 2),
           v15,
           &GUID_89c99ebb_edec_405b_a4f3_f908639fe524,
           v13);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v9 = (struct IDCompositionCaptureControllerReferenceInternal *)v13[0];
      v13[0] = 0;
      *a2 = v9;
      v10 = v15;
      v15 = 0;
      *a3 = v10;
      v7 = 0;
      goto LABEL_7;
    }
    v8 = 60;
  }
  else
  {
    v8 = 56;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\dcompmanager.cpp",
    (const char *)(unsigned int)v6,
    v12);
LABEL_7:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(v13);
  return v7;
}

```

## disassembly

```asm
0x18001fe88  mov     rax, rsp
0x18001fe8b  push    rbx
0x18001fe8c  push    rbp
0x18001fe8d  push    rsi
0x18001fe8e  push    rdi
0x18001fe8f  sub     rsp, 48h
0x18001fe93  mov     rdi, r8
0x18001fe96  mov     rsi, rdx
0x18001fe99  mov     rbp, rcx
0x18001fe9c  mov     qword ptr [rax-38h], 0
0x18001fea4  mov     qword ptr [rax+20h], 0
0x18001feac  lea     rdx, [rax+20h]
0x18001feb0  lea     rcx, _GUID_44794289_3c85_445f_86ec_33d578f442b6
0x18001feb7  call    cs:__imp_DCompositionCreateSharedResourceHandle
0x18001febd  mov     ebx, eax
0x18001febf  test    eax, eax
0x18001fec1  jns     short loc_18001FECA
0x18001fec3  mov     edx, 38h ; '8'
0x18001fec8  jmp     short loc_18001FEFC
0x18001feca  mov     rcx, [rbp+10h]
0x18001fece  mov     rax, [rcx]
0x18001fed1  lea     r9, [rsp+68h+var_38]
0x18001fed6  lea     r8, _GUID_89c99ebb_edec_405b_a4f3_f908639fe524
0x18001fedd  mov     rdx, [rsp+68h+arg_18]
0x18001fee5  mov     rax, [rax+0E8h]
0x18001feec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fef1  mov     ebx, eax
0x18001fef3  test    eax, eax
0x18001fef5  jns     short loc_18001FF12
0x18001fef7  mov     edx, 3Ch ; '<'; void *
0x18001fefc  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ff03  mov     r9d, eax; char *
0x18001ff06  mov     rcx, [rsp+68h]; this
0x18001ff0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff10  jmp     short loc_18001FF3C
0x18001ff12  mov     rax, [rsp+68h+var_38]
0x18001ff17  mov     [rsp+68h+var_38], 0
0x18001ff20  mov     [rsi], rax
0x18001ff23  mov     rax, [rsp+68h+arg_18]
0x18001ff2b  mov     [rsp+68h+arg_18], 0
0x18001ff37  mov     [rdi], rax
0x18001ff3a  xor     ebx, ebx
0x18001ff3c  lea     rcx, [rsp+68h+arg_18]
0x18001ff44  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001ff49  nop
0x18001ff4a  lea     rcx, [rsp+68h+var_38]
0x18001ff4f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001ff54  mov     eax, ebx
0x18001ff56  add     rsp, 48h
0x18001ff5a  pop     rdi
0x18001ff5b  pop     rsi
0x18001ff5c  pop     rbp
0x18001ff5d  pop     rbx
0x18001ff5e  retn
```
