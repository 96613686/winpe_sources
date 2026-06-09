# NotifyDataChanged(HWND__ *,CHANGE_TYPE)

- ea: `0x18000d0d0`
- end: `0x18000d145`
- name: `?NotifyDataChanged@@YAXPEAUHWND__@@W4CHANGE_TYPE@@@Z`
- size: `117`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa90`
- `0x18000c0d0`
- `0x18000cb60`

## callees

- `0x18000d0d0`

## import_xrefs

- `USER32!GetParent` at `0x18000d0e9`
- `USER32!GetParent` at `0x18000d0e9`
- `USER32!SendMessageW` at `0x18000d12f`
- `USER32!SendMessageW` at `0x18000d12f`
- `USER32!GetWindowLongPtrW` at `0x18000d10c`
- `USER32!GetWindowLongPtrW` at `0x18000d10c`

## pseudocode

```c
void __fastcall NotifyDataChanged(HWND a1, int a2)
{
  HWND Parent; // rdi
  LONG_PTR WindowLongPtrW; // rax

  if ( a1 )
  {
    Parent = GetParent(a1);
    if ( Parent )
    {
      if ( a2 || !g_bSafeMode )
      {
        WindowLongPtrW = GetWindowLongPtrW(a1, -21);
        if ( WindowLongPtrW )
          *(_DWORD *)(WindowLongPtrW + 584) = 1;
        SendMessageW(Parent, 0x468u, (WPARAM)a1, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x18000d0d0  test    rcx, rcx
0x18000d0d3  jz      short locret_18000D144
0x18000d0d5  mov     [rsp+arg_0], rbx
0x18000d0da  mov     [rsp+arg_8], rsi
0x18000d0df  push    rdi
0x18000d0e0  sub     rsp, 20h
0x18000d0e4  mov     esi, edx
0x18000d0e6  mov     rbx, rcx
0x18000d0e9  call    cs:__imp_GetParent
0x18000d0ef  mov     rdi, rax
0x18000d0f2  test    rax, rax
0x18000d0f5  jz      short loc_18000D135
0x18000d0f7  test    esi, esi
0x18000d0f9  jnz     short loc_18000D104
0x18000d0fb  cmp     cs:?g_bSafeMode@@3EA, sil; uchar g_bSafeMode
0x18000d102  jnz     short loc_18000D135
0x18000d104  mov     edx, 0FFFFFFEBh; nIndex
0x18000d109  mov     rcx, rbx; hWnd
0x18000d10c  call    cs:__imp_GetWindowLongPtrW
0x18000d112  test    rax, rax
0x18000d115  jz      short loc_18000D121
0x18000d117  mov     dword ptr [rax+248h], 1
0x18000d121  xor     r9d, r9d; lParam
0x18000d124  mov     r8, rbx; wParam
0x18000d127  mov     edx, 468h; Msg
0x18000d12c  mov     rcx, rdi; hWnd
0x18000d12f  call    cs:__imp_SendMessageW
0x18000d135  mov     rbx, [rsp+28h+arg_0]
0x18000d13a  mov     rsi, [rsp+28h+arg_8]
0x18000d13f  add     rsp, 20h
0x18000d143  pop     rdi
0x18000d144  retn
```
