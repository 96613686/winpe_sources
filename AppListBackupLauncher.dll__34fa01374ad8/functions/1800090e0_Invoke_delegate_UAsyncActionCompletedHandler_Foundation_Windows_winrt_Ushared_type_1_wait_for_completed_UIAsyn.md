# ?Invoke@?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@UEAAHPEAXH@Z

- ea: `0x1800090e0`
- end: `0x1800090ff`
- name: `?Invoke@?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@UEAAHPEAXH@Z`
- size: `31`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002f21`
- `0x1800090e0`

## pseudocode

```c
__int64 __fastcall _Invoke___delegate_UAsyncActionCompletedHandler_Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_UIAsyncAction_Foundation_Windows_winrt___impl_4_YA_A_PAEBUIAsyncAction_234_I_Z__impl_winrt__UEAAHPEAXH_Z(
        __int64 a1,
        __int64 a2,
        int a3)
{
  *(_DWORD *)(a1 + 24) = a3;
  WINRT_IMPL_SetEvent(*(HANDLE *)(a1 + 16));
  return 0;
}

```

## disassembly

```asm
0x1800090e0  sub     rsp, 28h
0x1800090e4  mov     [rcx+18h], r8d
0x1800090e8  mov     rcx, [rcx+10h]; hEvent
0x1800090ec  call    WINRT_IMPL_SetEvent
0x1800090f1  xor     eax, eax
0x1800090f3  jmp     short loc_1800090F9
0x1800090f5  mov     eax, [rsp+28h+arg_10]
0x1800090f9  add     rsp, 28h
0x1800090fd  retn
```
