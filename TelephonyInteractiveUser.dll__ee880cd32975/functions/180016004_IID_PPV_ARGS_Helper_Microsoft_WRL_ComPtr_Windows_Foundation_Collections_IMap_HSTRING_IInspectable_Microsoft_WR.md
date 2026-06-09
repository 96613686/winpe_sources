# IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)

- ea: `0x180016004`
- end: `0x180016031`
- name: `??$IID_PPV_ARGS_Helper@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `45`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016040`
- `0x180016298`
- `0x180016798`
- `0x180017108`

## callees

- `0x180016004`
- `0x180019010`

## pseudocode

```c
__int64 *__fastcall IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(
        __int64 *a1)
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
0x180016004  push    rbx
0x180016006  sub     rsp, 20h
0x18001600a  mov     rbx, rcx
0x18001600d  mov     rcx, [rcx]
0x180016010  test    rcx, rcx
0x180016013  jz      short loc_180016028
0x180016015  mov     qword ptr [rbx], 0
0x18001601c  mov     rax, [rcx]
0x18001601f  mov     rax, [rax+10h]
0x180016023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016028  mov     rax, rbx
0x18001602b  add     rsp, 20h
0x18001602f  pop     rbx
0x180016030  retn
```
