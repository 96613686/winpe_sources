# WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnMouseMove(uint,unsigned __int64,__int64,int &)

- ea: `0x1800249a0`
- end: `0x180024abd`
- name: `?OnMouseMove@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_JI_K_JAEAH@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180027544`

## callees

- `0x180022558`
- `0x1800249a0`
- `0x1800288a0`

## import_xrefs

- `USER32!SetCursor` at `0x180024aa0`
- `USER32!SetCursor` at `0x180024aa0`
- `USER32!UpdateWindow` at `0x180024a26`
- `USER32!UpdateWindow` at `0x180024a26`
- `USER32!GetCapture` at `0x1800249c4`
- `USER32!GetCapture` at `0x1800249c4`

## pseudocode

```c
__int64 __fastcall WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnMouseMove(
        __int64 a1,
        __int64 a2,
        char a3,
        int a4,
        _DWORD *a5)
{
  __int16 v5; // si
  int v7; // edi
  HWND Capture; // rax
  __int64 v9; // r8
  __int64 v10; // r14
  unsigned int v11; // edi
  __int64 v12; // rsi
  int v13; // ecx
  int *v14; // rax

  v5 = a4;
  v7 = SHIWORD(a4);
  if ( (a3 & 1) == 0 )
    goto LABEL_23;
  Capture = GetCapture();
  v10 = a1 - 64;
  if ( !a1 )
    v10 = 8;
  if ( Capture == *(HWND *)v10 )
  {
    v11 = v7 - *(_DWORD *)(a1 + 56) - *(_DWORD *)(a1 + 20);
    if ( v11 == -1 )
      v11 = -2;
    if ( *(_DWORD *)(a1 + 32) != v11 )
    {
      v12 = a1;
      if ( !a1 )
        v12 = 72;
      if ( *(_BYTE *)(a1 + 52) )
      {
        LOBYTE(v9) = 1;
        if ( (unsigned __int8)WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::SetSplitterPos(v12, v11, v9) )
          UpdateWindow(*(HWND *)v10);
      }
      else
      {
        WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar((_DWORD *)a1);
        WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::SetSplitterPos(v12, v11, 0);
        WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar((_DWORD *)a1);
      }
    }
  }
  else
  {
LABEL_23:
    if ( *(_DWORD *)(a1 + 72) == -1 )
    {
      v13 = *(_DWORD *)(a1 + 32);
      if ( v13 != -1 && (v5 == -1 || v5 >= *(_DWORD *)(a1 + 16) && v5 <= *(_DWORD *)(a1 + 24)) )
      {
        v14 = (int *)(a1 + 20);
        if ( (v7 == -1 || v7 >= *v14 && v7 <= *(_DWORD *)(a1 + 28))
          && v7 >= v13 + *v14
          && v7 < *v14 + v13 + *(_DWORD *)(a1 + 40) + *(_DWORD *)(a1 + 48) )
        {
          SetCursor(WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::m_hCursor);
        }
      }
    }
    *a5 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800249a0  push    rbx
0x1800249a2  push    rsi
0x1800249a3  push    rdi
0x1800249a4  push    r14
0x1800249a6  sub     rsp, 28h
0x1800249aa  mov     rax, r9
0x1800249ad  mov     rsi, r9
0x1800249b0  shr     rax, 10h
0x1800249b4  mov     rbx, rcx
0x1800249b7  movsx   edi, ax
0x1800249ba  test    r8b, 1
0x1800249be  jz      loc_180024A50
0x1800249c4  call    cs:__imp_GetCapture
0x1800249ca  test    rbx, rbx
0x1800249cd  lea     r14, [rbx-40h]
0x1800249d1  mov     ecx, 8
0x1800249d6  cmovz   r14, rcx
0x1800249da  cmp     rax, [r14]
0x1800249dd  jnz     short loc_180024A50
0x1800249df  sub     edi, [rbx+38h]
0x1800249e2  or      eax, 0FFFFFFFFh
0x1800249e5  sub     edi, [rbx+14h]
0x1800249e8  mov     ecx, 0FFFFFFFEh
0x1800249ed  cmp     edi, eax
0x1800249ef  cmovz   edi, ecx
0x1800249f2  cmp     [rbx+20h], edi
0x1800249f5  jz      loc_180024AB1
0x1800249fb  test    rbx, rbx
0x1800249fe  lea     eax, [rcx+4Ah]
0x180024a01  mov     rsi, rbx
0x180024a04  cmovz   rsi, rax
0x180024a08  cmp     byte ptr [rbx+34h], 0
0x180024a0c  jz      short loc_180024A31
0x180024a0e  mov     r8b, 1
0x180024a11  mov     edx, edi
0x180024a13  mov     rcx, rsi
0x180024a16  call    ?SetSplitterPos@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_NH_N@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::SetSplitterPos(int,bool)
0x180024a1b  test    al, al
0x180024a1d  jz      loc_180024AB1
0x180024a23  mov     rcx, [r14]; hWnd
0x180024a26  call    cs:__imp_UpdateWindow
0x180024a2c  jmp     loc_180024AB1
0x180024a31  mov     rcx, rbx
0x180024a34  call    ?DrawGhostBar@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar(void)
0x180024a39  xor     r8d, r8d
0x180024a3c  mov     edx, edi
0x180024a3e  mov     rcx, rsi
0x180024a41  call    ?SetSplitterPos@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_NH_N@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::SetSplitterPos(int,bool)
0x180024a46  mov     rcx, rbx
0x180024a49  call    ?DrawGhostBar@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar(void)
0x180024a4e  jmp     short loc_180024AB1
0x180024a50  or      eax, 0FFFFFFFFh
0x180024a53  cmp     [rbx+48h], eax
0x180024a56  jnz     short loc_180024AA6
0x180024a58  mov     ecx, [rbx+20h]
0x180024a5b  cmp     ecx, eax
0x180024a5d  jz      short loc_180024AA6
0x180024a5f  cmp     si, ax
0x180024a62  jz      short loc_180024A71
0x180024a64  movsx   edx, si
0x180024a67  cmp     edx, [rbx+10h]
0x180024a6a  jl      short loc_180024AA6
0x180024a6c  cmp     edx, [rbx+18h]
0x180024a6f  jg      short loc_180024AA6
0x180024a71  cmp     edi, eax
0x180024a73  lea     rax, [rbx+14h]
0x180024a77  jz      short loc_180024A82
0x180024a79  cmp     edi, [rax]
0x180024a7b  jl      short loc_180024AA6
0x180024a7d  cmp     edi, [rbx+1Ch]
0x180024a80  jg      short loc_180024AA6
0x180024a82  mov     edx, [rax]
0x180024a84  lea     eax, [rcx+rdx]
0x180024a87  cmp     edi, eax
0x180024a89  jl      short loc_180024AA6
0x180024a8b  mov     eax, [rbx+30h]
0x180024a8e  add     eax, [rbx+28h]
0x180024a91  add     eax, ecx
0x180024a93  add     eax, edx
0x180024a95  cmp     edi, eax
0x180024a97  jge     short loc_180024AA6
0x180024a99  mov     rcx, cs:?m_hCursor@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@2PEAUHICON__@@EA; hCursor
0x180024aa0  call    cs:__imp_SetCursor
0x180024aa6  mov     rax, [rsp+48h+arg_20]
0x180024aab  mov     dword ptr [rax], 0
0x180024ab1  xor     eax, eax
0x180024ab3  add     rsp, 28h
0x180024ab7  pop     r14
0x180024ab9  pop     rdi
0x180024aba  pop     rsi
0x180024abb  pop     rbx
0x180024abc  retn
```
