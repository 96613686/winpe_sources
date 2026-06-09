# CWnd::RunModalLoop(ulong)

- ea: `0x18001d5c0`
- end: `0x18001d7c1`
- name: `?RunModalLoop@CWnd@@QEAAHK@Z`
- size: `513`
- prototype: `__int64 __fastcall(CWnd *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180056390`
- `0x180058c60`

## callees

- `0x180007110`
- `0x180012eb0`
- `0x180013330`
- `0x180014270`
- `0x18001d5c0`
- `0x180024410`
- `0x18002d600`
- `0x1800d7010`

## import_xrefs

- `USER32!SendMessageW` at `0x18001d64e`
- `USER32!SendMessageW` at `0x18001d669`
- `USER32!SendMessageW` at `0x18001d64e`
- `USER32!SendMessageW` at `0x18001d669`
- `USER32!GetParent` at `0x18001d5f1`
- `USER32!GetParent` at `0x18001d5f1`
- `USER32!PeekMessageW` at `0x18001d61f`
- `USER32!PeekMessageW` at `0x18001d70c`
- `USER32!PeekMessageW` at `0x18001d61f`
- `USER32!PeekMessageW` at `0x18001d70c`
- `USER32!UpdateWindow` at `0x18001d779`
- `USER32!UpdateWindow` at `0x18001d7ab`
- `USER32!UpdateWindow` at `0x18001d779`
- `USER32!UpdateWindow` at `0x18001d7ab`

## pseudocode

```c
__int64 __fastcall CWnd::RunModalLoop(HWND *this, char a2)
{
  int v2; // edi
  int v5; // r12d
  BOOL v6; // esi
  HWND Parent; // rax
  HWND v8; // r13
  struct tagMSG *v9; // rbp
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // ecx

  v2 = 0;
  v5 = 1;
  v6 = (a2 & 4) != 0 && (CWnd::GetStyle((CWnd *)this) & 0x10000000) == 0;
  Parent = GetParent(this[8]);
  *((_DWORD *)this + 20) |= 0x18u;
  v8 = Parent;
  v9 = (struct tagMSG *)((char *)AfxGetThread() + 104);
LABEL_4:
  if ( !v5 )
    goto LABEL_15;
  do
  {
    if ( PeekMessageW(v9, 0, 0, 0, 0) )
      goto LABEL_15;
    if ( v6 )
    {
      CWnd::ShowWindow((CWnd *)this, 1);
      UpdateWindow(this[8]);
      v6 = 0;
    }
    if ( (a2 & 1) == 0 && v8 && !v2 )
      SendMessageW(v8, 0x121u, 0, (LPARAM)this[8]);
    if ( (a2 & 2) != 0 )
      break;
  }
  while ( SendMessageW(this[8], 0x36Au, 0, v2++) );
  v5 = 0;
  while ( 1 )
  {
LABEL_15:
    v11 = *((_QWORD *)AfxGetModuleThreadState() + 1);
    if ( !v11 )
      v11 = *((_QWORD *)AfxGetModuleState() + 1);
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v11 + 200LL))(v11) )
    {
      AfxPostQuitMessage(0);
      return 0xFFFFFFFFLL;
    }
    if ( v6 && (v9->message == 280 || v9->message == 260) )
    {
      CWnd::ShowWindow((CWnd *)this, 1);
      UpdateWindow(this[8]);
      v6 = 0;
    }
    if ( !(*((unsigned int (__fastcall **)(HWND *))*this + 30))(this) )
      break;
    v12 = *((_QWORD *)AfxGetModuleThreadState() + 1);
    if ( !v12 )
      v12 = *((_QWORD *)AfxGetModuleState() + 1);
    v13 = (*(__int64 (__fastcall **)(__int64, struct tagMSG *))(*(_QWORD *)v12 + 216LL))(v12, v9);
    if ( v13 )
      v5 = 1;
    v14 = 0;
    if ( !v13 )
      v14 = v2;
    v2 = v14;
    if ( !PeekMessageW(v9, 0, 0, 0, 0) )
      goto LABEL_4;
  }
  *((_DWORD *)this + 20) &= 0xFFFFFFE7;
  return *((unsigned int *)this + 24);
}

```

## disassembly

```asm
0x18001d5c0  push    rbx
0x18001d5c2  push    rbp
0x18001d5c3  push    rsi
0x18001d5c4  push    rdi
0x18001d5c5  push    r12
0x18001d5c7  push    r13
0x18001d5c9  push    r14
0x18001d5cb  push    r15
0x18001d5cd  sub     rsp, 38h
0x18001d5d1  xor     edi, edi
0x18001d5d3  mov     r14d, 1
0x18001d5d9  mov     r15d, edx
0x18001d5dc  mov     rbx, rcx
0x18001d5df  mov     r12d, r14d
0x18001d5e2  test    dl, 4
0x18001d5e5  jnz     loc_18001D753
0x18001d5eb  xor     esi, esi
0x18001d5ed  mov     rcx, [rbx+40h]; hWnd
0x18001d5f1  call    cs:__imp_GetParent
0x18001d5f7  or      dword ptr [rbx+50h], 18h
0x18001d5fb  mov     r13, rax
0x18001d5fe  call    ?AfxGetThread@@YAPEAVCWinThread@@XZ; AfxGetThread(void)
0x18001d603  lea     rbp, [rax+68h]
0x18001d607  test    r12d, r12d
0x18001d60a  jz      short loc_18001D67F
0x18001d60c  xor     r9d, r9d; wMsgFilterMax
0x18001d60f  mov     [rsp+78h+wRemoveMsg], 0; wRemoveMsg
0x18001d617  xor     r8d, r8d; wMsgFilterMin
0x18001d61a  xor     edx, edx; hWnd
0x18001d61c  mov     rcx, rbp; lpMsg
0x18001d61f  call    cs:__imp_PeekMessageW
0x18001d625  test    eax, eax
0x18001d627  jnz     short loc_18001D67F
0x18001d629  test    esi, esi
0x18001d62b  jnz     loc_18001D76A
0x18001d631  test    r14b, r15b
0x18001d634  jnz     short loc_18001D654
0x18001d636  test    r13, r13
0x18001d639  jz      short loc_18001D654
0x18001d63b  test    edi, edi
0x18001d63d  jnz     short loc_18001D654
0x18001d63f  mov     r9, [rbx+40h]; lParam
0x18001d643  xor     r8d, r8d; wParam
0x18001d646  mov     edx, 121h; Msg
0x18001d64b  mov     rcx, r13; hWnd
0x18001d64e  call    cs:__imp_SendMessageW
0x18001d654  test    r15b, 2
0x18001d658  jnz     short loc_18001D67C
0x18001d65a  mov     rcx, [rbx+40h]; hWnd
0x18001d65e  xor     r8d, r8d; wParam
0x18001d661  movsxd  r9, edi; lParam
0x18001d664  mov     edx, 36Ah; Msg
0x18001d669  call    cs:__imp_SendMessageW
0x18001d66f  inc     edi
0x18001d671  mov     r14d, 1
0x18001d677  test    rax, rax
0x18001d67a  jnz     short loc_18001D60C
0x18001d67c  xor     r12d, r12d
0x18001d67f  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x18001d684  mov     rcx, [rax+8]
0x18001d688  test    rcx, rcx
0x18001d68b  jz      loc_18001D71F
0x18001d691  mov     rax, [rcx]
0x18001d694  mov     rax, [rax+0C8h]
0x18001d69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6a0  test    eax, eax
0x18001d6a2  jz      loc_18001D738
0x18001d6a8  test    esi, esi
0x18001d6aa  jnz     loc_18001D786
0x18001d6b0  mov     rax, [rbx]
0x18001d6b3  mov     rcx, rbx
0x18001d6b6  mov     rax, [rax+0F0h]
0x18001d6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6c2  test    eax, eax
0x18001d6c4  jz      loc_18001D7B8
0x18001d6ca  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x18001d6cf  mov     rcx, [rax+8]
0x18001d6d3  test    rcx, rcx
0x18001d6d6  jz      short loc_18001D72D
0x18001d6d8  mov     rax, [rcx]
0x18001d6db  mov     rdx, rbp
0x18001d6de  mov     rax, [rax+0D8h]
0x18001d6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6ea  test    eax, eax
0x18001d6ec  mov     [rsp+78h+wRemoveMsg], 0; wRemoveMsg
0x18001d6f4  cmovnz  r12d, r14d
0x18001d6f8  xor     ecx, ecx
0x18001d6fa  test    eax, eax
0x18001d6fc  cmovz   ecx, edi
0x18001d6ff  xor     r9d, r9d; wMsgFilterMax
0x18001d702  mov     edi, ecx
0x18001d704  xor     r8d, r8d; wMsgFilterMin
0x18001d707  mov     rcx, rbp; lpMsg
0x18001d70a  xor     edx, edx; hWnd
0x18001d70c  call    cs:__imp_PeekMessageW
0x18001d712  test    eax, eax
0x18001d714  jnz     loc_18001D67F
0x18001d71a  jmp     loc_18001D607
0x18001d71f  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18001d724  mov     rcx, [rax+8]
0x18001d728  jmp     loc_18001D691
0x18001d72d  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18001d732  mov     rcx, [rax+8]
0x18001d736  jmp     short loc_18001D6D8
0x18001d738  xor     ecx, ecx; int
0x18001d73a  call    ?AfxPostQuitMessage@@YAXH@Z; AfxPostQuitMessage(int)
0x18001d73f  or      eax, 0FFFFFFFFh
0x18001d742  add     rsp, 38h
0x18001d746  pop     r15
0x18001d748  pop     r14
0x18001d74a  pop     r13
0x18001d74c  pop     r12
0x18001d74e  pop     rdi
0x18001d74f  pop     rsi
0x18001d750  pop     rbp
0x18001d751  pop     rbx
0x18001d752  retn
0x18001d753  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x18001d758  bt      eax, 1Ch
0x18001d75c  jb      loc_18001D5EB
0x18001d762  mov     esi, r14d
0x18001d765  jmp     loc_18001D5ED
0x18001d76a  mov     edx, r14d; int
0x18001d76d  mov     rcx, rbx; this
0x18001d770  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x18001d775  mov     rcx, [rbx+40h]; hWnd
0x18001d779  call    cs:__imp_UpdateWindow
0x18001d77f  xor     esi, esi
0x18001d781  jmp     loc_18001D631
0x18001d786  cmp     dword ptr [rbp+8], 118h
0x18001d78d  jz      short loc_18001D79C
0x18001d78f  cmp     dword ptr [rbp+8], 104h
0x18001d796  jnz     loc_18001D6B0
0x18001d79c  mov     edx, r14d; int
0x18001d79f  mov     rcx, rbx; this
0x18001d7a2  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x18001d7a7  mov     rcx, [rbx+40h]; hWnd
0x18001d7ab  call    cs:__imp_UpdateWindow
0x18001d7b1  xor     esi, esi
0x18001d7b3  jmp     loc_18001D6B0
0x18001d7b8  and     dword ptr [rbx+50h], 0FFFFFFE7h
0x18001d7bc  mov     eax, [rbx+60h]
0x18001d7bf  jmp     short loc_18001D742
```
