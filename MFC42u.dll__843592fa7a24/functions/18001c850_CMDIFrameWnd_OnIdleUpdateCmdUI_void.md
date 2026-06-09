# CMDIFrameWnd::OnIdleUpdateCmdUI(void)

- ea: `0x18001c850`
- end: `0x18001c926`
- name: `?OnIdleUpdateCmdUI@CMDIFrameWnd@@IEAAXXZ`
- size: `214`
- prototype: `void __fastcall(CMDIFrameWnd *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18001c850`
- `0x1800d7010`

## import_xrefs

- `USER32!SendMessageW` at `0x18001c91b`
- `USER32!SendMessageW` at `0x18001c91b`
- `USER32!UpdateWindow` at `0x18001c901`
- `USER32!UpdateWindow` at `0x18001c901`
- `USER32!DrawMenuBar` at `0x18001c89d`
- `USER32!DrawMenuBar` at `0x18001c89d`

## pseudocode

```c
void __fastcall CMDIFrameWnd::OnIdleUpdateCmdUI(HWND *this)
{
  int v2; // edx

  if ( ((_DWORD)this[41] & 1) != 0 )
  {
    DrawMenuBar(this[8]);
    *((_DWORD *)this + 82) &= ~1u;
    if ( ((_DWORD)this[41] & 1) != 0 )
      (*((void (__fastcall **)(HWND *, HWND))*this + 59))(this, this[37]);
  }
  if ( ((_BYTE)this[41] & 2) != 0 )
    (*((void (__fastcall **)(HWND *, __int64))*this + 58))(this, 1);
  v2 = *((_DWORD *)this + 82);
  if ( (v2 & 8) != 0 )
  {
    (*((void (__fastcall **)(HWND *, _QWORD))*this + 52))(this, v2 & 4);
    UpdateWindow(this[8]);
  }
  if ( *((_DWORD *)this + 64) != *((_DWORD *)this + 65) )
    SendMessageW(this[8], 0x362u, *((unsigned int *)this + 64), 0);
  *((_DWORD *)this + 82) = 0;
}

```

## disassembly

```asm
0x18001c850  push    rbx
0x18001c852  sub     rsp, 20h
0x18001c856  mov     eax, [rcx+148h]
0x18001c85c  mov     rbx, rcx
0x18001c85f  test    al, 1
0x18001c861  jnz     short loc_18001C899
0x18001c863  test    byte ptr [rbx+148h], 2
0x18001c86a  jnz     short loc_18001C8CF
0x18001c86c  mov     edx, [rbx+148h]
0x18001c872  test    dl, 8
0x18001c875  jnz     short loc_18001C8E8
0x18001c877  mov     eax, [rbx+100h]
0x18001c87d  cmp     eax, [rbx+104h]
0x18001c883  jnz     loc_18001C90C
0x18001c889  mov     dword ptr [rbx+148h], 0
0x18001c893  add     rsp, 20h
0x18001c897  pop     rbx
0x18001c898  retn
0x18001c899  mov     rcx, [rcx+40h]; hWnd
0x18001c89d  call    cs:__imp_DrawMenuBar
0x18001c8a3  and     dword ptr [rbx+148h], 0FFFFFFFEh
0x18001c8aa  mov     eax, [rbx+148h]
0x18001c8b0  test    al, 1
0x18001c8b2  jz      short loc_18001C863
0x18001c8b4  mov     rax, [rbx]
0x18001c8b7  mov     rcx, rbx
0x18001c8ba  mov     rdx, [rbx+128h]
0x18001c8c1  mov     rax, [rax+1D8h]
0x18001c8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8cd  jmp     short loc_18001C863
0x18001c8cf  mov     rax, [rbx]
0x18001c8d2  mov     edx, 1
0x18001c8d7  mov     rcx, rbx
0x18001c8da  mov     rax, [rax+1D0h]
0x18001c8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8e6  jmp     short loc_18001C86C
0x18001c8e8  mov     rax, [rbx]
0x18001c8eb  and     edx, 4
0x18001c8ee  mov     rcx, rbx
0x18001c8f1  mov     rax, [rax+1A0h]
0x18001c8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8fd  mov     rcx, [rbx+40h]; hWnd
0x18001c901  call    cs:__imp_UpdateWindow
0x18001c907  jmp     loc_18001C877
0x18001c90c  mov     rcx, [rbx+40h]; hWnd
0x18001c910  mov     r8, rax; wParam
0x18001c913  xor     r9d, r9d; lParam
0x18001c916  mov     edx, 362h; Msg
0x18001c91b  call    cs:__imp_SendMessageW
0x18001c921  jmp     loc_18001C889
```
