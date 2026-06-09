# wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_3___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_3___

- ea: `0x140007e9c`
- end: `0x140007eb5`
- name: `wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_3___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_3___`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400098cc`

## callees

- `0x140007e9c`

## import_xrefs

- `DUI70!UnInitThread` at `0x140007eaa`
- `DUI70!UnInitThread` at `0x140007eaa`

## pseudocode

```c
__int64 __fastcall wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_3___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_3___(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 1) )
  {
    *(_BYTE *)(a1 + 1) = 0;
    return UnInitThread();
  }
  return result;
}

```

## disassembly

```asm
0x140007e9c  sub     rsp, 28h
0x140007ea0  cmp     byte ptr [rcx+1], 0
0x140007ea4  jz      short loc_140007EB0
0x140007ea6  mov     byte ptr [rcx+1], 0
0x140007eaa  call    cs:__imp_UnInitThread
0x140007eb0  add     rsp, 28h
0x140007eb4  retn
```
