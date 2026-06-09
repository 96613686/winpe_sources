# CDockContext::InitLoop(void)

- ea: `0x18004b300`
- end: `0x18004b3f5`
- name: `?InitLoop@CDockContext@@QEAAXXZ`
- size: `245`
- prototype: `void __fastcall(CDockContext *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18004b510`
- `0x18004b900`

## callees

- `0x1800166a0`
- `0x18004b270`
- `0x18004b300`

## import_xrefs

- `USER32!PeekMessageW` at `0x18004b338`
- `USER32!PeekMessageW` at `0x18004b338`
- `USER32!DispatchMessageW` at `0x18004b362`
- `USER32!DispatchMessageW` at `0x18004b362`
- `USER32!SetRectEmpty` at `0x18004b38f`
- `USER32!SetRectEmpty` at `0x18004b38f`
- `USER32!GetMessageW` at `0x18004b34f`
- `USER32!GetMessageW` at `0x18004b34f`
- `USER32!LockWindowUpdate` at `0x18004b3bb`
- `USER32!LockWindowUpdate` at `0x18004b3bb`
- `USER32!GetDCEx` at `0x18004b3d5`
- `USER32!GetDCEx` at `0x18004b3d5`

## pseudocode

```c
void __fastcall CDockContext::InitLoop(CDockContext *this)
{
  __int64 v2; // rcx
  struct CWnd *DesktopWindow; // rbx
  BOOL v4; // eax
  DWORD v5; // r8d
  HDC DCEx; // rax
  struct tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  while ( PeekMessageW(&Msg, 0, 0xFu, 0xFu, 0) )
  {
    if ( !GetMessageW(&Msg, 0, 0xFu, 0xFu) )
      return;
    DispatchMessageW(&Msg);
  }
  v2 = *((_QWORD *)this + 14);
  *((_DWORD *)this + 32) = *(_DWORD *)(v2 + 176);
  *((_DWORD *)this + 34) = *(_DWORD *)(v2 + 172) & 0xF000;
  SetRectEmpty((LPRECT)this + 1);
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *(_QWORD *)((char *)this + 140) = 0;
  DesktopWindow = CWnd::GetDesktopWindow();
  v4 = LockWindowUpdate(*((HWND *)DesktopWindow + 8));
  v5 = 1027;
  if ( !v4 )
    v5 = 3;
  DCEx = GetDCEx(*((HWND *)DesktopWindow + 8), 0, v5);
  *((_QWORD *)this + 19) = CDC::FromHandle(DCEx);
}

```

## disassembly

```asm
0x18004b300  mov     rax, rsp
0x18004b303  mov     [rax+8], rbx
0x18004b307  push    rdi
0x18004b308  sub     rsp, 60h
0x18004b30c  xorps   xmm0, xmm0
0x18004b30f  mov     rdi, rcx
0x18004b312  movups  xmmword ptr [rax-38h], xmm0
0x18004b316  mov     ebx, 0Fh
0x18004b31b  movups  xmmword ptr [rax-28h], xmm0
0x18004b31f  movups  xmmword ptr [rax-18h], xmm0
0x18004b323  mov     r9d, ebx; wMsgFilterMax
0x18004b326  mov     [rsp+68h+wRemoveMsg], 0; wRemoveMsg
0x18004b32e  mov     r8d, ebx; wMsgFilterMin
0x18004b331  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18004b336  xor     edx, edx; hWnd
0x18004b338  call    cs:__imp_PeekMessageW
0x18004b33e  test    eax, eax
0x18004b340  jz      short loc_18004B36A
0x18004b342  mov     r9d, ebx; wMsgFilterMax
0x18004b345  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18004b34a  mov     r8d, ebx; wMsgFilterMin
0x18004b34d  xor     edx, edx; hWnd
0x18004b34f  call    cs:__imp_GetMessageW
0x18004b355  test    eax, eax
0x18004b357  jz      loc_18004B3EA
0x18004b35d  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18004b362  call    cs:__imp_DispatchMessageW
0x18004b368  jmp     short loc_18004B323
0x18004b36a  mov     rcx, [rdi+70h]
0x18004b36e  mov     eax, [rcx+0B0h]
0x18004b374  mov     [rdi+80h], eax
0x18004b37a  mov     eax, [rcx+0ACh]
0x18004b380  lea     rcx, [rdi+10h]; lprc
0x18004b384  and     eax, 0F000h
0x18004b389  mov     [rdi+88h], eax
0x18004b38f  call    cs:__imp_SetRectEmpty
0x18004b395  mov     qword ptr [rdi+20h], 0
0x18004b39d  mov     dword ptr [rdi+28h], 0
0x18004b3a4  mov     qword ptr [rdi+8Ch], 0
0x18004b3af  call    ?GetDesktopWindow@CWnd@@SAPEAV1@XZ; CWnd::GetDesktopWindow(void)
0x18004b3b4  mov     rbx, rax
0x18004b3b7  mov     rcx, [rax+40h]; hWndLock
0x18004b3bb  call    cs:__imp_LockWindowUpdate
0x18004b3c1  mov     rcx, [rbx+40h]; hWnd
0x18004b3c5  xor     edx, edx; hrgnClip
0x18004b3c7  mov     r8d, 403h
0x18004b3cd  test    eax, eax
0x18004b3cf  jnz     short loc_18004B3D5
0x18004b3d1  lea     r8d, [rdx+3]; flags
0x18004b3d5  call    cs:__imp_GetDCEx
0x18004b3db  mov     rcx, rax; HDC
0x18004b3de  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x18004b3e3  mov     [rdi+98h], rax
0x18004b3ea  mov     rbx, [rsp+68h+arg_0]
0x18004b3ef  add     rsp, 60h
0x18004b3f3  pop     rdi
0x18004b3f4  retn
```
