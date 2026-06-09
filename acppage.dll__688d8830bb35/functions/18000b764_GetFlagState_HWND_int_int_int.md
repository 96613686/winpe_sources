# GetFlagState(HWND__ *,int,int *,int *)

- ea: `0x18000b764`
- end: `0x18000b7c0`
- name: `?GetFlagState@@YAXPEAUHWND__@@HPEAH1@Z`
- size: `92`
- prototype: `void __fastcall(HWND hDlg, int nIDDlgItem, int *, int *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000aa90`
- `0x18000d14c`
- `0x18000e73c`

## import_xrefs

- `USER32!GetDlgItem` at `0x18000b7a4`
- `USER32!GetDlgItem` at `0x18000b7a4`
- `USER32!IsWindowEnabled` at `0x18000b7ad`
- `USER32!IsWindowEnabled` at `0x18000b7ad`
- `USER32!SendDlgItemMessageW` at `0x18000b78b`
- `USER32!SendDlgItemMessageW` at `0x18000b78b`

## pseudocode

```c
void __fastcall GetFlagState(HWND hDlg, int nIDDlgItem, int *a3, int *a4)
{
  HWND DlgItem; // rax

  *a3 = SendDlgItemMessageW(hDlg, nIDDlgItem, 0xF0u, 0, 0) == 1;
  DlgItem = GetDlgItem(hDlg, nIDDlgItem);
  *a4 = IsWindowEnabled(DlgItem);
}

```

## disassembly

```asm
0x18000b764  push    rbx
0x18000b766  push    rsi
0x18000b767  push    rdi
0x18000b768  push    r14
0x18000b76a  sub     rsp, 38h
0x18000b76e  mov     r14, r9
0x18000b771  mov     [rsp+58h+lParam], 0; lParam
0x18000b77a  mov     rbx, r8
0x18000b77d  xor     r9d, r9d; wParam
0x18000b780  mov     r8d, 0F0h; Msg
0x18000b786  mov     edi, edx
0x18000b788  mov     rsi, rcx
0x18000b78b  call    cs:__imp_SendDlgItemMessageW
0x18000b791  xor     r10d, r10d
0x18000b794  mov     edx, edi; nIDDlgItem
0x18000b796  cmp     rax, 1
0x18000b79a  mov     rcx, rsi; hDlg
0x18000b79d  setz    r10b
0x18000b7a1  mov     [rbx], r10d
0x18000b7a4  call    cs:__imp_GetDlgItem
0x18000b7aa  mov     rcx, rax; hWnd
0x18000b7ad  call    cs:__imp_IsWindowEnabled
0x18000b7b3  mov     [r14], eax
0x18000b7b6  add     rsp, 38h
0x18000b7ba  pop     r14
0x18000b7bc  pop     rdi
0x18000b7bd  pop     rsi
0x18000b7be  pop     rbx
0x18000b7bf  retn
```
