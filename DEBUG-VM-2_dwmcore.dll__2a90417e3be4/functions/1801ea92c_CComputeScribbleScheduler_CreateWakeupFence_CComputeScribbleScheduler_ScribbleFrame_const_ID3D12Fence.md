# CComputeScribbleScheduler::CreateWakeupFence(CComputeScribbleScheduler::ScribbleFrame const &,ID3D12Fence * *)

- ea: `0x1801ea92c`
- end: `0x1801eab92`
- name: `?CreateWakeupFence@CComputeScribbleScheduler@@AEAAJAEBUScribbleFrame@1@PEAPEAUID3D12Fence@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(CComputeScribbleScheduler *__hidden this, const struct CComputeScribbleScheduler::ScribbleFrame *, struct ID3D12Fence **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18021b22c`

## callees

- `0x18000a254`
- `0x18000a7f4`
- `0x180042854`
- `0x1801ea92c`
- `0x1802549ec`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801eab55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801eab55`

## string_xrefs

- `0x1801ea99d`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x1801ea9da`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x1801eaa34`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x1801eaa7a`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x1801eaac4`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`

## pseudocode

```c
__int64 __fastcall CComputeScribbleScheduler::CreateWakeupFence(
        CComputeScribbleScheduler *this,
        const struct CComputeScribbleScheduler::ScribbleFrame *a2,
        struct ID3D12Fence **a3)
{
  double v3; // xmm0_8
  __int64 v5; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  struct ID3D12Fence *v21; // rax
  __int64 v22; // rcx
  int v23; // [rsp+20h] [rbp-30h]
  __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  struct ID3D12Fence *v25; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v27; // [rsp+80h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+38h] BYREF
  __int64 v29; // [rsp+98h] [rbp+48h] BYREF

  v3 = *((double *)a2 + 2) * 10000000.0;
  v5 = *((_QWORD *)this + 3);
  v24 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v5 + 72LL))(
         v5,
         *((_QWORD *)this + 4),
         (unsigned int)(int)v3,
         &v24);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
    v11 = 440;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)v10,
      v23);
LABEL_17:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v24);
    return v9;
  }
  if ( !v24 )
  {
    v9 = -2147024882;
    v11 = 443;
    v10 = 2147942414LL;
    goto LABEL_5;
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 3);
  v27 = 0;
  v13 = (**v12)(v12, &GUID_64338358_366a_471b_bd56_dd8ef48e439b, &v27);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)v13,
      v23);
LABEL_16:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v27);
    goto LABEL_17;
  }
  hObject = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v27 + 24LL))(v27, v24, 0, 0x10000000);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)v14,
      0);
LABEL_15:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    goto LABEL_16;
  }
  v15 = *((_QWORD *)this + 2);
  v29 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v15 + 56LL))(
          v15,
          &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
          &v29);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)v16,
      0);
LABEL_14:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v29);
    goto LABEL_15;
  }
  v25 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, HANDLE, GUID *, struct ID3D12Fence **))(*(_QWORD *)v29 + 256LL))(
          v29,
          hObject,
          &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76,
          &v25);
  v9 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)v17,
      0);
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v25);
    goto LABEL_14;
  }
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x80000) != 0 )
    McTemplateU0xf_EventWriteTransfer(v19, v18, *(_QWORD *)a2);
  v21 = v25;
  v22 = v29;
  v25 = 0;
  *a3 = v21;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return 0;
}

```

## disassembly

```asm
0x1801ea92c  push    rbp
0x1801ea92e  push    rbx
0x1801ea92f  push    rsi
0x1801ea930  push    rdi
0x1801ea931  push    r14
0x1801ea933  mov     rbp, rsp
0x1801ea936  sub     rsp, 50h
0x1801ea93a  movsd   xmm0, qword ptr [rdx+10h]
0x1801ea93f  lea     r9, [rbp+var_10]
0x1801ea943  mulsd   xmm0, cs:__real@416312d000000000
0x1801ea94b  mov     rsi, rcx
0x1801ea94e  mov     rcx, [rcx+18h]
0x1801ea952  mov     r14, r8
0x1801ea955  mov     [rbp+var_10], 0
0x1801ea95d  mov     rdi, rdx
0x1801ea960  mov     rdx, [rsi+20h]
0x1801ea964  mov     rax, [rcx]
0x1801ea967  cvttsd2si r8, xmm0
0x1801ea96c  mov     rax, [rax+48h]
0x1801ea970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea975  mov     ebx, eax
0x1801ea977  test    eax, eax
0x1801ea979  jns     short loc_1801EA985
0x1801ea97b  mov     r9d, eax
0x1801ea97e  mov     edx, 1B8h
0x1801ea983  jmp     short loc_1801EA999
0x1801ea985  cmp     [rbp+var_10], 0
0x1801ea98a  jnz     short loc_1801EA9AE
0x1801ea98c  mov     ebx, 8007000Eh
0x1801ea991  mov     edx, 1BBh; void *
0x1801ea996  mov     r9d, ebx; char *
0x1801ea999  mov     rcx, [rbp+28h]; this
0x1801ea99d  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801ea9a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea9a9  jmp     loc_1801EAAFC
0x1801ea9ae  mov     rcx, [rsi+18h]
0x1801ea9b2  lea     r8, [rbp+arg_0]
0x1801ea9b6  mov     [rbp+arg_0], 0
0x1801ea9be  lea     rdx, _GUID_64338358_366a_471b_bd56_dd8ef48e439b
0x1801ea9c5  mov     rax, [rcx]
0x1801ea9c8  mov     rax, [rax]
0x1801ea9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea9d0  mov     ebx, eax
0x1801ea9d2  test    eax, eax
0x1801ea9d4  jns     short loc_1801EA9F3
0x1801ea9d6  mov     rcx, [rbp+28h]; this
0x1801ea9da  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801ea9e1  mov     r9d, eax; char *
0x1801ea9e4  mov     edx, 1BEh; void *
0x1801ea9e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea9ee  jmp     loc_1801EAAF3
0x1801ea9f3  mov     rcx, [rbp+arg_0]
0x1801ea9f7  lea     rdx, [rbp+hObject]
0x1801ea9fb  mov     [rsp+50h+var_28], rdx
0x1801eaa00  mov     r9d, 10000000h
0x1801eaa06  mov     rdx, [rbp+var_10]
0x1801eaa0a  xor     r8d, r8d
0x1801eaa0d  mov     [rbp+hObject], 0
0x1801eaa15  mov     rax, [rcx]
0x1801eaa18  mov     qword ptr [rsp+50h+var_30], 0; int
0x1801eaa21  mov     rax, [rax+18h]
0x1801eaa25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eaa2a  mov     ebx, eax
0x1801eaa2c  test    eax, eax
0x1801eaa2e  jns     short loc_1801EAA4D
0x1801eaa30  mov     rcx, [rbp+28h]; this
0x1801eaa34  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801eaa3b  mov     r9d, eax; char *
0x1801eaa3e  mov     edx, 1C6h; void *
0x1801eaa43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eaa48  jmp     loc_1801EAAEA
0x1801eaa4d  mov     rcx, [rsi+10h]
0x1801eaa51  lea     r8, [rbp+arg_18]
0x1801eaa55  mov     [rbp+arg_18], 0
0x1801eaa5d  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x1801eaa64  mov     rax, [rcx]
0x1801eaa67  mov     rax, [rax+38h]
0x1801eaa6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eaa70  mov     ebx, eax
0x1801eaa72  test    eax, eax
0x1801eaa74  jns     short loc_1801EAA90
0x1801eaa76  mov     rcx, [rbp+28h]; this
0x1801eaa7a  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801eaa81  mov     r9d, eax; char *
0x1801eaa84  mov     edx, 1C9h; void *
0x1801eaa89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eaa8e  jmp     short loc_1801EAAE1
0x1801eaa90  mov     rcx, [rbp+arg_18]
0x1801eaa94  lea     r9, [rbp+var_8]
0x1801eaa98  mov     rdx, [rbp+hObject]
0x1801eaa9c  lea     r8, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x1801eaaa3  mov     [rbp+var_8], 0
0x1801eaaab  mov     rax, [rcx]
0x1801eaaae  mov     rax, [rax+100h]
0x1801eaab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eaaba  mov     ebx, eax
0x1801eaabc  test    eax, eax
0x1801eaabe  jns     short loc_1801EAB09
0x1801eaac0  mov     rcx, [rbp+28h]; this
0x1801eaac4  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x1801eaacb  mov     r9d, eax; char *
0x1801eaace  mov     edx, 1CDh; void *
0x1801eaad3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eaad8  lea     rcx, [rbp+var_8]
0x1801eaadc  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801eaae1  lea     rcx, [rbp+arg_18]
0x1801eaae5  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801eaaea  lea     rcx, [rbp+hObject]
0x1801eaaee  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801eaaf3  lea     rcx, [rbp+arg_0]
0x1801eaaf7  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801eaafc  lea     rcx, [rbp+var_10]
0x1801eab00  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801eab05  mov     eax, ebx
0x1801eab07  jmp     short loc_1801EAB87
0x1801eab09  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+2, 8
0x1801eab10  jz      short loc_1801EAB23
0x1801eab12  movsd   xmm3, qword ptr [rdi+10h]
0x1801eab17  mov     r8, [rdi]
0x1801eab1a  cvtpd2ps xmm3, xmm3
0x1801eab1e  call    McTemplateU0xf_EventWriteTransfer
0x1801eab23  mov     rax, [rbp+var_8]
0x1801eab27  mov     rcx, [rbp+arg_18]
0x1801eab2b  mov     [rbp+var_8], 0
0x1801eab33  mov     [r14], rax
0x1801eab36  test    rcx, rcx
0x1801eab39  jz      short loc_1801EAB47
0x1801eab3b  mov     rax, [rcx]
0x1801eab3e  mov     rax, [rax+10h]
0x1801eab42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eab47  mov     rcx, [rbp+hObject]; hObject
0x1801eab4b  lea     rax, [rcx-1]
0x1801eab4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801eab53  ja      short loc_1801EAB5B
0x1801eab55  call    cs:__imp_CloseHandle
0x1801eab5b  mov     rcx, [rbp+arg_0]
0x1801eab5f  test    rcx, rcx
0x1801eab62  jz      short loc_1801EAB70
0x1801eab64  mov     rax, [rcx]
0x1801eab67  mov     rax, [rax+10h]
0x1801eab6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eab70  mov     rcx, [rbp+var_10]
0x1801eab74  test    rcx, rcx
0x1801eab77  jz      short loc_1801EAB85
0x1801eab79  mov     rax, [rcx]
0x1801eab7c  mov     rax, [rax+10h]
0x1801eab80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eab85  xor     eax, eax
0x1801eab87  add     rsp, 50h
0x1801eab8b  pop     r14
0x1801eab8d  pop     rdi
0x1801eab8e  pop     rsi
0x1801eab8f  pop     rbx
0x1801eab90  pop     rbp
0x1801eab91  retn
```
