# ?Invoke@?$delegate@U?$AsyncOperationCompletedHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAHPEAXH@Z

- ea: `0x180009b50`
- end: `0x180009b68`
- name: `?Invoke@?$delegate@U?$AsyncOperationCompletedHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAHPEAXH@Z`
- size: `24`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c74d`

## pseudocode

```c
__int64 __fastcall _Invoke___delegate_U__AsyncOperationCompletedHandler_UIInspectable_Foundation_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UIInspectable_Foundation_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UIInspectable_Foundation_Windows_winrt___234_I_Z__impl_winrt__UEAAHPEAXH_Z(
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
0x180009b50  sub     rsp, 28h
0x180009b54  mov     [rcx+18h], r8d
0x180009b58  mov     rcx, [rcx+10h]; hEvent
0x180009b5c  call    WINRT_IMPL_SetEvent
0x180009b61  xor     eax, eax
0x180009b63  add     rsp, 28h
0x180009b67  retn
```
