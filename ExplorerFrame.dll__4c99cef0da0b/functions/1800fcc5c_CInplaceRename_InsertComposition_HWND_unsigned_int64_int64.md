# CInplaceRename::_InsertComposition(HWND__ *,unsigned __int64,__int64)

- ea: `0x1800fcc5c`
- end: `0x1800fcf0b`
- name: `?_InsertComposition@CInplaceRename@@AEAAXPEAUHWND__@@_K_J@Z`
- size: `687`
- prototype: `void __fastcall(CInplaceRename *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800846ac`

## callees

- `0x1800fcc5c`
- `0x1800fcf14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fcd10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fcd59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fcdbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fce72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fcd10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fcd59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fcdbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fce72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fcd67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fce80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fcd67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fce80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fcd22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fcdce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fcd22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fcdce`
- `IMM32!ImmReleaseContext` at `0x1800fcecc`
- `IMM32!ImmReleaseContext` at `0x1800fcecc`
- `IMM32!ImmGetContext` at `0x1800fcc8c`
- `IMM32!ImmGetContext` at `0x1800fcc8c`
- `IMM32!ImmGetCompositionStringW` at `0x1800fcd03`
- `IMM32!ImmGetCompositionStringW` at `0x1800fcd3f`
- `IMM32!ImmGetCompositionStringW` at `0x1800fcdab`
- `IMM32!ImmGetCompositionStringW` at `0x1800fcdef`
- `IMM32!ImmGetCompositionStringW` at `0x1800fcd03`
- `IMM32!ImmGetCompositionStringW` at `0x1800fcd3f`
- `IMM32!ImmGetCompositionStringW` at `0x1800fcdab`
- `IMM32!ImmGetCompositionStringW` at `0x1800fcdef`
- `IMM32!ImmSetCompositionStringW` at `0x1800fce52`
- `IMM32!ImmSetCompositionStringW` at `0x1800fce52`
- `USER32!SendMessageW` at `0x1800fcc83`
- `USER32!SendMessageW` at `0x1800fccc0`
- `USER32!SendMessageW` at `0x1800fcce4`
- `USER32!SendMessageW` at `0x1800fcd8b`
- `USER32!SendMessageW` at `0x1800fce03`
- `USER32!SendMessageW` at `0x1800fcee0`
- `USER32!SendMessageW` at `0x1800fcc83`
- `USER32!SendMessageW` at `0x1800fccc0`
- `USER32!SendMessageW` at `0x1800fcce4`
- `USER32!SendMessageW` at `0x1800fcd8b`
- `USER32!SendMessageW` at `0x1800fce03`
- `USER32!SendMessageW` at `0x1800fcee0`
- `USER32!SetPropW` at `0x1800fcec0`
- `USER32!SetPropW` at `0x1800fcec0`
- `USER32!GetPropW` at `0x1800fcca8`
- `USER32!GetPropW` at `0x1800fcca8`
- `USER32!RemovePropW` at `0x1800fcd77`
- `USER32!RemovePropW` at `0x1800fce94`
- `USER32!RemovePropW` at `0x1800fcd77`
- `USER32!RemovePropW` at `0x1800fce94`
- `USER32!GetWindowTextLengthW` at `0x1800fce0f`
- `USER32!GetWindowTextLengthW` at `0x1800fce0f`
- `USER32!RedrawWindow` at `0x1800fcf04`

## string_xrefs

- `0x1800fcc9e`: `IMECompPos`
- `0x1800fcd6d`: `IMECompPos`
- `0x1800fce8a`: `IMECompPos`
- `0x1800fcea0`: `IMECompPos`

## pseudocode

```c
void __fastcall CInplaceRename::_InsertComposition(CInplaceRename *this, HWND a2, __int64 a3, __int16 a4)
{
  HIMC Context; // r15
  unsigned int PropW; // eax
  unsigned int v9; // r12d
  LONG CompositionStringW; // eax
  __int64 v11; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  HANDLE v15; // rax
  LONG v16; // eax
  __int64 v17; // rsi
  HANDLE v18; // rax
  char *v19; // rax
  char *v20; // r14
  int v21; // ebx
  signed int v22; // ebp
  HANDLE v23; // rax

  SendMessageW(a2, 0xBu, 0, 0);
  Context = ImmGetContext(a2);
  if ( Context )
  {
    PropW = (unsigned int)GetPropW(a2, L"IMECompPos");
    if ( PropW )
      v9 = PropW;
    else
      v9 = SendMessageW(a2, 0xB0u, 0, 0);
    SendMessageW(a2, 0xB1u, (__int16)v9, SHIWORD(v9));
    if ( (a4 & 0x800) != 0 )
    {
      CompositionStringW = ImmGetCompositionStringW(Context, 0x800u, 0, 0);
      v11 = CompositionStringW;
      if ( CompositionStringW >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v13 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v11 + 2);
        v14 = v13;
        if ( v13 )
        {
          ImmGetCompositionStringW(Context, 0x800u, v13, v11 + 2);
          *(unsigned __int16 *)((char *)v14 + v11) = 0;
          CInplaceRename::_IMEReplaceSelection(this, a2, v14);
          v15 = GetProcessHeap();
          HeapFree(v15, 0, v14);
        }
      }
      RemovePropW(a2, L"IMECompPos");
      v9 = SendMessageW(a2, 0xB0u, 0, 0);
    }
    if ( (a4 & 8) != 0 )
    {
      v16 = ImmGetCompositionStringW(Context, 8u, 0, 0);
      v17 = v16;
      if ( v16 < 0 )
        goto LABEL_20;
      v18 = GetProcessHeap();
      v19 = (char *)HeapAlloc(v18, 8u, v17 + 2);
      v20 = v19;
      if ( v19 )
      {
        ImmGetCompositionStringW(Context, 8u, v19, v17 + 2);
        v21 = SendMessageW(a2, 0xD5u, 0, 0);
        v22 = 2 * (v21 + HIWORD(v9) - (unsigned __int16)v9 - GetWindowTextLengthW(a2));
        if ( (int)v17 >= v22 && v22 >= 0 && v22 < (int)v17 )
        {
          *(_WORD *)&v20[v22] = 0;
          ImmSetCompositionStringW(Context, 9u, v20, v22, 0, 0);
          LODWORD(v17) = v22;
        }
        *(_WORD *)&v20[(int)v17] = 0;
        CInplaceRename::_IMEReplaceSelection(this, a2, (unsigned __int16 *)v20);
        v23 = GetProcessHeap();
        HeapFree(v23, 0, v20);
      }
      if ( (_DWORD)v17 )
LABEL_20:
        SetPropW(
          a2,
          L"IMECompPos",
          (HANDLE)((unsigned __int16)v9 | ((unsigned __int16)(v9 + ((unsigned __int64)(int)v17 >> 1)) << 16)));
      else
        RemovePropW(a2, L"IMECompPos");
    }
    ImmReleaseContext(a2, Context);
  }
  SendMessageW(a2, 0xBu, 1u, 0);
  RedrawWindow(a2, 0, 0, 3u);
}

```

## disassembly

```asm
0x1800fcc5c  push    rbx
0x1800fcc5e  push    rbp
0x1800fcc5f  push    rsi
0x1800fcc60  push    rdi
0x1800fcc61  push    r12
0x1800fcc63  push    r13
0x1800fcc65  push    r14
0x1800fcc67  push    r15
0x1800fcc69  sub     rsp, 38h
0x1800fcc6d  mov     rdi, rdx
0x1800fcc70  mov     rbp, r9
0x1800fcc73  xor     r9d, r9d; lParam
0x1800fcc76  mov     r13, rcx
0x1800fcc79  xor     r8d, r8d; wParam
0x1800fcc7c  mov     rcx, rdi; hWnd
0x1800fcc7f  lea     edx, [r9+0Bh]; Msg
0x1800fcc83  call    cs:__imp_SendMessageW
0x1800fcc89  mov     rcx, rdi; HWND
0x1800fcc8c  call    cs:__imp_ImmGetContext
0x1800fcc92  mov     r15, rax
0x1800fcc95  test    rax, rax
0x1800fcc98  jz      loc_1800FCED2
0x1800fcc9e  lea     rdx, ?s_szIMECompPos@CInplaceRename@@0QBGB; "IMECompPos"
0x1800fcca5  mov     rcx, rdi; hWnd
0x1800fcca8  call    cs:__imp_GetPropW
0x1800fccae  test    eax, eax
0x1800fccb0  jnz     short loc_1800FCCCB
0x1800fccb2  xor     r9d, r9d; lParam
0x1800fccb5  xor     r8d, r8d; wParam
0x1800fccb8  mov     edx, 0B0h; Msg
0x1800fccbd  mov     rcx, rdi; hWnd
0x1800fccc0  call    cs:__imp_SendMessageW
0x1800fccc6  mov     r12, rax
0x1800fccc9  jmp     short loc_1800FCCCE
0x1800fcccb  mov     r12d, eax
0x1800fccce  mov     eax, r12d
0x1800fccd1  movsx   r8, r12w; wParam
0x1800fccd5  shr     eax, 10h
0x1800fccd8  mov     edx, 0B1h; Msg
0x1800fccdd  movsx   r9, ax; lParam
0x1800fcce1  mov     rcx, rdi; hWnd
0x1800fcce4  call    cs:__imp_SendMessageW
0x1800fccea  mov     eax, 800h
0x1800fccef  test    rax, rbp
0x1800fccf2  jz      loc_1800FCD94
0x1800fccf8  xor     r9d, r9d; dwBufLen
0x1800fccfb  xor     r8d, r8d; lpBuf
0x1800fccfe  mov     edx, eax; DWORD
0x1800fcd00  mov     rcx, r15; HIMC
0x1800fcd03  call    cs:__imp_ImmGetCompositionStringW
0x1800fcd09  movsxd  rsi, eax
0x1800fcd0c  test    eax, eax
0x1800fcd0e  js      short loc_1800FCD6D
0x1800fcd10  call    cs:__imp_GetProcessHeap
0x1800fcd16  lea     r8, [rsi+2]; dwBytes
0x1800fcd1a  mov     edx, 8; dwFlags
0x1800fcd1f  mov     rcx, rax; hHeap
0x1800fcd22  call    cs:__imp_HeapAlloc
0x1800fcd28  mov     rbx, rax
0x1800fcd2b  test    rax, rax
0x1800fcd2e  jz      short loc_1800FCD6D
0x1800fcd30  lea     r9d, [rsi+2]; dwBufLen
0x1800fcd34  mov     r8, rax; lpBuf
0x1800fcd37  mov     edx, 800h; DWORD
0x1800fcd3c  mov     rcx, r15; HIMC
0x1800fcd3f  call    cs:__imp_ImmGetCompositionStringW
0x1800fcd45  xor     ecx, ecx
0x1800fcd47  mov     r8, rbx; unsigned __int16 *
0x1800fcd4a  mov     [rsi+rbx], cx
0x1800fcd4e  mov     rdx, rdi; HWND
0x1800fcd51  mov     rcx, r13; this
0x1800fcd54  call    ?_IMEReplaceSelection@CInplaceRename@@AEAAXPEAUHWND__@@PEAG@Z; CInplaceRename::_IMEReplaceSelection(HWND__ *,ushort *)
0x1800fcd59  call    cs:__imp_GetProcessHeap
0x1800fcd5f  mov     r8, rbx; lpMem
0x1800fcd62  xor     edx, edx; dwFlags
0x1800fcd64  mov     rcx, rax; hHeap
0x1800fcd67  call    cs:__imp_HeapFree
0x1800fcd6d  lea     rdx, ?s_szIMECompPos@CInplaceRename@@0QBGB; "IMECompPos"
0x1800fcd74  mov     rcx, rdi; hWnd
0x1800fcd77  call    cs:__imp_RemovePropW
0x1800fcd7d  xor     r9d, r9d; lParam
0x1800fcd80  xor     r8d, r8d; wParam
0x1800fcd83  mov     edx, 0B0h; Msg
0x1800fcd88  mov     rcx, rdi; hWnd
0x1800fcd8b  call    cs:__imp_SendMessageW
0x1800fcd91  mov     r12d, eax
0x1800fcd94  test    bpl, 8
0x1800fcd98  jz      loc_1800FCEC6
0x1800fcd9e  xor     r9d, r9d; dwBufLen
0x1800fcda1  xor     r8d, r8d; lpBuf
0x1800fcda4  mov     rcx, r15; HIMC
0x1800fcda7  lea     edx, [r9+8]; DWORD
0x1800fcdab  call    cs:__imp_ImmGetCompositionStringW
0x1800fcdb1  movsxd  rsi, eax
0x1800fcdb4  test    eax, eax
0x1800fcdb6  js      loc_1800FCE9C
0x1800fcdbc  call    cs:__imp_GetProcessHeap
0x1800fcdc2  lea     r8, [rsi+2]; dwBytes
0x1800fcdc6  mov     edx, 8; dwFlags
0x1800fcdcb  mov     rcx, rax; hHeap
0x1800fcdce  call    cs:__imp_HeapAlloc
0x1800fcdd4  mov     r14, rax
0x1800fcdd7  test    rax, rax
0x1800fcdda  jz      loc_1800FCE86
0x1800fcde0  lea     r9d, [rsi+2]; dwBufLen
0x1800fcde4  mov     r8, rax; lpBuf
0x1800fcde7  mov     edx, 8; DWORD
0x1800fcdec  mov     rcx, r15; HIMC
0x1800fcdef  call    cs:__imp_ImmGetCompositionStringW
0x1800fcdf5  xor     r9d, r9d; lParam
0x1800fcdf8  xor     r8d, r8d; wParam
0x1800fcdfb  mov     edx, 0D5h; Msg
0x1800fce00  mov     rcx, rdi; hWnd
0x1800fce03  call    cs:__imp_SendMessageW
0x1800fce09  mov     rcx, rdi; hWnd
0x1800fce0c  mov     rbx, rax
0x1800fce0f  call    cs:__imp_GetWindowTextLengthW
0x1800fce15  mov     ebp, r12d
0x1800fce18  movzx   ecx, r12w
0x1800fce1c  shr     ebp, 10h
0x1800fce1f  sub     ebp, ecx
0x1800fce21  add     ebp, ebx
0x1800fce23  sub     ebp, eax
0x1800fce25  add     ebp, ebp
0x1800fce27  cmp     esi, ebp
0x1800fce29  jl      short loc_1800FCE5A
0x1800fce2b  test    ebp, ebp
0x1800fce2d  js      short loc_1800FCE5A
0x1800fce2f  cmp     ebp, esi
0x1800fce31  jge     short loc_1800FCE5A
0x1800fce33  xor     eax, eax
0x1800fce35  movsxd  rcx, ebp
0x1800fce38  mov     [rsp+78h+dwReadLen], eax; dwReadLen
0x1800fce3c  mov     r9d, ebp; dwCompLen
0x1800fce3f  mov     r8, r14; lpComp
0x1800fce42  mov     [rsp+78h+lpRead], rax; lpRead
0x1800fce47  mov     [rcx+r14], ax
0x1800fce4c  lea     edx, [rax+9]; dwIndex
0x1800fce4f  mov     rcx, r15; HIMC
0x1800fce52  call    cs:__imp_ImmSetCompositionStringW
0x1800fce58  mov     esi, ebp
0x1800fce5a  movsxd  rcx, esi
0x1800fce5d  xor     eax, eax
0x1800fce5f  mov     r8, r14; unsigned __int16 *
0x1800fce62  mov     rdx, rdi; HWND
0x1800fce65  mov     [rcx+r14], ax
0x1800fce6a  mov     rcx, r13; this
0x1800fce6d  call    ?_IMEReplaceSelection@CInplaceRename@@AEAAXPEAUHWND__@@PEAG@Z; CInplaceRename::_IMEReplaceSelection(HWND__ *,ushort *)
0x1800fce72  call    cs:__imp_GetProcessHeap
0x1800fce78  mov     r8, r14; lpMem
0x1800fce7b  xor     edx, edx; dwFlags
0x1800fce7d  mov     rcx, rax; hHeap
0x1800fce80  call    cs:__imp_HeapFree
0x1800fce86  test    esi, esi
0x1800fce88  jnz     short loc_1800FCE9C
0x1800fce8a  lea     rdx, ?s_szIMECompPos@CInplaceRename@@0QBGB; "IMECompPos"
0x1800fce91  mov     rcx, rdi; hWnd
0x1800fce94  call    cs:__imp_RemovePropW
0x1800fce9a  jmp     short loc_1800FCEC6
0x1800fce9c  movzx   r8d, r12w
0x1800fcea0  lea     rdx, ?s_szIMECompPos@CInplaceRename@@0QBGB; "IMECompPos"
0x1800fcea7  movsxd  rax, esi
0x1800fceaa  shr     rax, 1
0x1800fcead  add     ax, r8w
0x1800fceb1  movzx   ecx, ax
0x1800fceb4  shl     ecx, 10h
0x1800fceb7  or      ecx, r8d
0x1800fceba  movsxd  r8, ecx; hData
0x1800fcebd  mov     rcx, rdi; hWnd
0x1800fcec0  call    cs:__imp_SetPropW
0x1800fcec6  mov     rdx, r15; HIMC
0x1800fcec9  mov     rcx, rdi; HWND
0x1800fcecc  call    cs:__imp_ImmReleaseContext
0x1800fced2  xor     r9d, r9d; lParam
0x1800fced5  mov     rcx, rdi; hWnd
0x1800fced8  lea     edx, [r9+0Bh]; Msg
0x1800fcedc  lea     r8d, [r9+1]; wParam
0x1800fcee0  call    cs:__imp_SendMessageW
0x1800fcee6  mov     r9d, 3
0x1800fceec  xor     r8d, r8d
0x1800fceef  xor     edx, edx
0x1800fcef1  mov     rcx, rdi
0x1800fcef4  add     rsp, 38h
0x1800fcef8  pop     r15
0x1800fcefa  pop     r14
0x1800fcefc  pop     r13
0x1800fcefe  pop     r12
0x1800fcf00  pop     rdi
0x1800fcf01  pop     rsi
0x1800fcf02  pop     rbp
0x1800fcf03  pop     rbx
0x1800fcf04  jmp     cs:__imp_RedrawWindow
```
