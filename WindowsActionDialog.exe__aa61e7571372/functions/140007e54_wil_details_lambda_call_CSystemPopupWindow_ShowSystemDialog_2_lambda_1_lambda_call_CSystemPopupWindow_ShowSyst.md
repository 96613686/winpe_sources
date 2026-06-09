# wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_1___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_1___

- ea: `0x140007e54`
- end: `0x140007e6d`
- name: `wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_1___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_1___`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400098a8`

## callees

- `0x140007e54`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140007e62`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140007e62`

## pseudocode

```c
__int64 __fastcall wil::details::lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_1___::_lambda_call__CSystemPopupWindow::ShowSystemDialog_::_2_::_lambda_1___(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 1) )
  {
    *(_BYTE *)(a1 + 1) = 0;
    return RoUninitialize();
  }
  return result;
}

```

## disassembly

```asm
0x140007e54  sub     rsp, 28h
0x140007e58  cmp     byte ptr [rcx+1], 0
0x140007e5c  jz      short loc_140007E68
0x140007e5e  mov     byte ptr [rcx+1], 0
0x140007e62  call    cs:__imp_RoUninitialize
0x140007e68  add     rsp, 28h
0x140007e6c  retn
```
