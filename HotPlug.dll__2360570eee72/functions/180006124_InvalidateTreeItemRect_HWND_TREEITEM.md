# InvalidateTreeItemRect(HWND__ *,_TREEITEM *)

- ea: `0x180006124`
- end: `0x180006189`
- name: `?InvalidateTreeItemRect@@YAXPEAUHWND__@@PEAU_TREEITEM@@@Z`
- size: `101`
- prototype: `void __fastcall(HWND hWnd, struct _TREEITEM *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030d4`
- `0x180003964`
- `0x180004664`

## callees

- `0x180006124`
- `0x180008760`

## import_xrefs

- `USER32!InvalidateRect` at `0x180006170`
- `USER32!InvalidateRect` at `0x180006170`
- `USER32!SendMessageW` at `0x18000615b`
- `USER32!SendMessageW` at `0x18000615b`

## pseudocode

```c
void __fastcall InvalidateTreeItemRect(HWND hWnd, struct _TREEITEM *a2)
{
  RECT lParam; // [rsp+20h] [rbp-28h] BYREF

  if ( a2 )
  {
    *(_QWORD *)&lParam.left = a2;
    *(_QWORD *)&lParam.right = 0;
    if ( (unsigned int)SendMessageW(hWnd, 0x1104u, 0, (LPARAM)&lParam) )
      InvalidateRect(hWnd, &lParam, 0);
  }
}

```

## disassembly

```asm
0x180006124  test    rdx, rdx
0x180006127  jz      short locret_180006188
0x180006129  push    rbx
0x18000612a  sub     rsp, 40h
0x18000612e  mov     rax, cs:__security_cookie
0x180006135  xor     rax, rsp
0x180006138  mov     [rsp+48h+var_18], rax
0x18000613d  mov     [rsp+48h+lParam], rdx
0x180006142  lea     r9, [rsp+48h+lParam]; lParam
0x180006147  mov     edx, 1104h; Msg
0x18000614c  mov     [rsp+48h+var_20], 0
0x180006155  xor     r8d, r8d; wParam
0x180006158  mov     rbx, rcx
0x18000615b  call    cs:__imp_SendMessageW
0x180006161  test    eax, eax
0x180006163  jz      short loc_180006176
0x180006165  xor     r8d, r8d; bErase
0x180006168  lea     rdx, [rsp+48h+lParam]; lpRect
0x18000616d  mov     rcx, rbx; hWnd
0x180006170  call    cs:__imp_InvalidateRect
0x180006176  mov     rcx, [rsp+48h+var_18]
0x18000617b  xor     rcx, rsp; StackCookie
0x18000617e  call    __security_check_cookie
0x180006183  add     rsp, 40h
0x180006187  pop     rbx
0x180006188  retn
```
