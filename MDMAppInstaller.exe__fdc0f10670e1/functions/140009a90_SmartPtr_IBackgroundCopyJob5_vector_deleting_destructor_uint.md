# SmartPtr<IBackgroundCopyJob5>::`vector deleting destructor'(uint)

- ea: `0x140009a90`
- end: `0x140009ace`
- name: `??_E?$SmartPtr@UIBackgroundCopyJob5@@@@UEAAPEAXI@Z`
- size: `62`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009040`
- `0x140009a90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140009aba`
- `msvcrt!??3@YAXPEAX@Z` at `0x140009aba`

## pseudocode

```c
_QWORD *__fastcall SmartPtr<IBackgroundCopyJob5>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &SmartPtr<IBackgroundCopyJob5>::`vftable';
  ATL::CComPtr<IDeliveryOptimizationJob>::~CComPtr<IDeliveryOptimizationJob>((__int64)(a1 + 1));
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140009a90  mov     [rsp+arg_0], rbx
0x140009a95  push    rdi
0x140009a96  sub     rsp, 20h
0x140009a9a  lea     rax, ??_7?$SmartPtr@UIBackgroundCopyJob5@@@@6B@; const SmartPtr<IBackgroundCopyJob5>::`vftable'
0x140009aa1  mov     rdi, rcx
0x140009aa4  mov     [rcx], rax
0x140009aa7  mov     ebx, edx
0x140009aa9  add     rcx, 8
0x140009aad  call    ??1?$CComPtr@UIDeliveryOptimizationJob@@@ATL@@QEAA@XZ; ATL::CComPtr<IDeliveryOptimizationJob>::~CComPtr<IDeliveryOptimizationJob>(void)
0x140009ab2  test    bl, 1
0x140009ab5  jz      short loc_140009AC0
0x140009ab7  mov     rcx, rdi
0x140009aba  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140009ac0  mov     rbx, [rsp+28h+arg_0]
0x140009ac5  mov     rax, rdi
0x140009ac8  add     rsp, 20h
0x140009acc  pop     rdi
0x140009acd  retn
```
