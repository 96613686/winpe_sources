# ??$capture@UITaskService@@A6AHAEBUguid@winrt@@PEAXI0PEAPEAX@_EAEBU23@AEAPEAXAEAI@winrt@@YA?AU?$com_ptr@UITaskService@@@0@A6AHAEBUguid@0@PEAXI0PEAPEAX@_E0AEAPEAXAEAI@Z

- ea: `0x180008a2c`
- end: `0x180008a9a`
- name: `??$capture@UITaskService@@A6AHAEBUguid@winrt@@PEAXI0PEAPEAX@_EAEBU23@AEAPEAXAEAI@winrt@@YA?AU?$com_ptr@UITaskService@@@0@A6AHAEBUguid@0@PEAXI0PEAPEAX@_E0AEAPEAXAEAI@Z`
- size: `110`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, const IID *, IUnknown **, DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b30`

## callees

- `0x180003429`
- `0x18000f38c`

## pseudocode

```c
_QWORD *__fastcall ___capture_UITaskService__A6AHAEBUguid_winrt__PEAXI0PEAPEAX__EAEBU23_AEAPEAXAEAI_winrt__YA_AU__com_ptr_UITaskService___0_A6AHAEBUguid_0_PEAXI0PEAPEAX__E0AEAPEAXAEAI_Z(
        _QWORD *a1,
        __int64 a2,
        const IID *a3,
        IUnknown **a4,
        DWORD *a5)
{
  IUnknown *v5; // rdx
  unsigned int v7; // eax
  int v9; // [rsp+38h] [rbp-20h] BYREF
  __int128 v10; // [rsp+40h] [rbp-18h]
  LPVOID v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = a2;
  v11 = a1;
  v5 = *a4;
  v11 = 0;
  v9 = 0;
  v10 = 0;
  v7 = CoCreateInstance_0(a3, v5, *a5, &winrt::impl::guid_v<ITaskService>, &v11);
  winrt::check_hresult(&v12, v7, &v9);
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x180008a2c  mov     rax, rsp
0x180008a2f  mov     [rax+10h], rdx
0x180008a33  mov     [rax+8], rcx
0x180008a37  push    rbx
0x180008a38  sub     rsp, 50h
0x180008a3c  mov     rdx, [r9]; pUnkOuter
0x180008a3f  mov     rbx, rcx
0x180008a42  xor     ecx, ecx
0x180008a44  lea     r9, ??$guid_v@UITaskService@@@impl@winrt@@3Uguid@2@B; riid
0x180008a4b  mov     r10, r8
0x180008a4e  mov     [rax+8], rcx
0x180008a52  mov     r8, [rsp+58h+arg_20]
0x180008a5a  xorps   xmm0, xmm0
0x180008a5d  mov     [rax-20h], ecx
0x180008a60  lea     rcx, [rax+8]
0x180008a64  mov     [rax-38h], rcx
0x180008a68  mov     rcx, r10; rclsid
0x180008a6b  movdqu  xmmword ptr [rax-18h], xmm0
0x180008a70  mov     r8d, [r8]; dwClsContext
0x180008a73  call    CoCreateInstance_0
0x180008a78  lea     r8, [rsp+58h+var_20]
0x180008a7d  mov     edx, eax
0x180008a7f  lea     rcx, [rsp+58h+arg_8]
0x180008a84  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180008a89  mov     rax, [rsp+58h+arg_0]
0x180008a8e  mov     [rbx], rax
0x180008a91  mov     rax, rbx
0x180008a94  add     rsp, 50h
0x180008a98  pop     rbx
0x180008a99  retn
```
