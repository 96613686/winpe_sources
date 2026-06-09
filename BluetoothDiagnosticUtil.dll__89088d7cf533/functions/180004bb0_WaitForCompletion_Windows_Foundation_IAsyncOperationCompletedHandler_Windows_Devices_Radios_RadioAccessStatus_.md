# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vector deleting destructor'(uint)

- ea: `0x180004bb0`
- end: `0x180004c2d`
- name: `??_EFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAAPEAXI@Z`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180004bb0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004c12`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004c12`
- `KERNEL32!CloseHandle` at `0x180004bd8`
- `KERNEL32!CloseHandle` at `0x180004bd8`

## pseudocode

```c
void *__fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus>>'::`2'::FTMEventDelegate::`vector deleting destructor'(
        void *a1,
        char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)a1 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)a1 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CloseHandle(*((HANDLE *)a1 + 7));
  *((_DWORD *)a1 + 11) = -1073741823;
  v4 = *((_QWORD *)a1 + 4);
  if ( v4 )
  {
    *((_QWORD *)a1 + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004bb0  mov     [rsp+arg_0], rbx
0x180004bb5  push    rdi
0x180004bb6  sub     rsp, 20h
0x180004bba  mov     edi, edx
0x180004bbc  mov     rbx, rcx
0x180004bbf  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>'}
0x180004bc6  mov     [rcx], rax
0x180004bc9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180004bd0  mov     [rcx+8], rax
0x180004bd4  mov     rcx, [rcx+38h]; hObject
0x180004bd8  call    cs:__imp_CloseHandle
0x180004bdf  nop     dword ptr [rax+rax+00h]
0x180004be4  mov     dword ptr [rbx+2Ch], 0C0000001h
0x180004beb  mov     rcx, [rbx+20h]
0x180004bef  test    rcx, rcx
0x180004bf2  jz      short loc_180004C09
0x180004bf4  mov     qword ptr [rbx+20h], 0
0x180004bfc  mov     rax, [rcx]
0x180004bff  mov     rax, [rax+10h]
0x180004c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c08  nop
0x180004c09  test    dil, 1
0x180004c0d  jz      short loc_180004C1E
0x180004c0f  mov     rcx, rbx
0x180004c12  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004c19  nop     dword ptr [rax+rax+00h]
0x180004c1e  mov     rax, rbx
0x180004c21  mov     rbx, [rsp+28h+arg_0]
0x180004c26  add     rsp, 20h
0x180004c2a  pop     rdi
0x180004c2b  retn
```
