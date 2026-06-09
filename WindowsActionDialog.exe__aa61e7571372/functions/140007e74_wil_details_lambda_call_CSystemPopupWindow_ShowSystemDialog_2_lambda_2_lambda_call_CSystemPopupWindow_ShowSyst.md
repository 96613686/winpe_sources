# wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_2___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_2___

- ea: `0x140007e74`
- end: `0x140007e94`
- name: `wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_2___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_2___`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400098ba`

## callees

- `0x140007e74`

## import_xrefs

- `DUI70!UnInitProcessPriv` at `0x140007e89`
- `DUI70!UnInitProcessPriv` at `0x140007e89`

## pseudocode

```c
__int64 __fastcall wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_2___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_2___(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 1) )
  {
    *(_BYTE *)(a1 + 1) = 0;
    return UnInitProcessPriv(0x140000000uLL);
  }
  return result;
}

```

## disassembly

```asm
0x140007e74  sub     rsp, 28h
0x140007e78  cmp     byte ptr [rcx+1], 0
0x140007e7c  jz      short loc_140007E8F
0x140007e7e  mov     byte ptr [rcx+1], 0
0x140007e82  lea     rcx, cs:140000000h
0x140007e89  call    cs:__imp_UnInitProcessPriv
0x140007e8f  add     rsp, 28h
0x140007e93  retn
```
