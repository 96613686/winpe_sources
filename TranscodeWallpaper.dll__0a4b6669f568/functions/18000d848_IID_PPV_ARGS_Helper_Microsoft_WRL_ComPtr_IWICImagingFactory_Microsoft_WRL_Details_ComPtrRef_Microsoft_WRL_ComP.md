# IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWICImagingFactory>>)

- ea: `0x18000d848`
- end: `0x18000d875`
- name: `??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `45`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d87c`

## callees

- `0x18000d848`
- `0x18000f010`

## pseudocode

```c
__int64 *__fastcall IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return a1;
}

```

## disassembly

```asm
0x18000d848  push    rbx
0x18000d84a  sub     rsp, 20h
0x18000d84e  mov     rbx, rcx
0x18000d851  mov     rcx, [rcx]
0x18000d854  test    rcx, rcx
0x18000d857  jz      short loc_18000D86C
0x18000d859  mov     qword ptr [rbx], 0
0x18000d860  mov     rax, [rcx]
0x18000d863  mov     rax, [rax+10h]
0x18000d867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d86c  mov     rax, rbx
0x18000d86f  add     rsp, 20h
0x18000d873  pop     rbx
0x18000d874  retn
```
