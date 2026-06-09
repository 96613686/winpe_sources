# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vector deleting destructor'(uint)

- ea: `0x180009c40`
- end: `0x180009cb4`
- name: `??_E?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAPEAXI@Z`
- size: `116`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800022c0`
- `0x180008378`
- `0x180009c40`
- `0x180011010`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  v4 = a1[15];
  if ( v4 )
  {
    a1[15] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = a1[13];
  if ( v5 )
  {
    a1[13] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::~AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x90);
  return a1;
}

```

## disassembly

```asm
0x180009c40  mov     [rsp+arg_0], rbx
0x180009c45  push    rdi
0x180009c46  sub     rsp, 20h
0x180009c4a  mov     edi, edx
0x180009c4c  mov     rbx, rcx
0x180009c4f  mov     rcx, [rcx+78h]
0x180009c53  test    rcx, rcx
0x180009c56  jz      short loc_180009C6D
0x180009c58  mov     qword ptr [rbx+78h], 0
0x180009c60  mov     rax, [rcx]
0x180009c63  mov     rax, [rax+10h]
0x180009c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c6c  nop
0x180009c6d  mov     rcx, [rbx+68h]
0x180009c71  test    rcx, rcx
0x180009c74  jz      short loc_180009C8B
0x180009c76  mov     qword ptr [rbx+68h], 0
0x180009c7e  mov     rax, [rcx]
0x180009c81  mov     rax, [rax+10h]
0x180009c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c8a  nop
0x180009c8b  mov     rcx, rbx
0x180009c8e  call    ??1?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::~AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(void)
0x180009c93  test    dil, 1
0x180009c97  jz      short loc_180009CA6
0x180009c99  mov     edx, 90h; struct std::nothrow_t *
0x180009c9e  mov     rcx, rbx; void *
0x180009ca1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009ca6  mov     rax, rbx
0x180009ca9  mov     rbx, [rsp+28h+arg_0]
0x180009cae  add     rsp, 20h
0x180009cb2  pop     rdi
0x180009cb3  retn
```
