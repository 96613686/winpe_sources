# BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>>,tagCOWAIT_FLAGS,void *)

- ea: `0x180001c48`
- end: `0x180001c9e`
- name: `??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@23@U?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@U?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009670`
- `0x1800098a0`

## callees

- `0x180001c48`
- `0x180002b50`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        __int64 *a2,
        __int64 a3)
{
  __int64 v5; // rcx
  __int64 result; // rax

  v5 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  result = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>>(
             a1,
             (HRESULT)a2,
             a3);
  if ( (int)result >= 0 )
    return ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))(*a1)[8])(a1, a2);
  return result;
}

```

## disassembly

```asm
0x180001c48  mov     [rsp+arg_0], rbx
0x180001c4d  push    rdi
0x180001c4e  sub     rsp, 20h
0x180001c52  mov     rbx, rdx
0x180001c55  mov     rdi, rcx
0x180001c58  mov     rcx, [rdx]
0x180001c5b  test    rcx, rcx
0x180001c5e  jz      short loc_180001C74
0x180001c60  mov     qword ptr [rdx], 0
0x180001c67  mov     rax, [rcx]
0x180001c6a  mov     rax, [rax+10h]
0x180001c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c73  nop
0x180001c74  mov     rcx, rdi
0x180001c77  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,tagCOWAIT_FLAGS,void *)
0x180001c7c  test    eax, eax
0x180001c7e  js      short loc_180001C92
0x180001c80  mov     rax, [rdi]
0x180001c83  mov     rdx, rbx
0x180001c86  mov     rcx, rdi
0x180001c89  mov     rax, [rax+40h]
0x180001c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c92  mov     rbx, [rsp+28h+arg_0]
0x180001c97  add     rsp, 20h
0x180001c9b  pop     rdi
0x180001c9c  retn
```
