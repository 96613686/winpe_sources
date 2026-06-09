# CEditView::OnBeginPrinting(CDC *,CPrintInfo *)

- ea: `0x180068fe0`
- end: `0x180069177`
- name: `?OnBeginPrinting@CEditView@@MEAAXPEAVCDC@@PEAUCPrintInfo@@@Z`
- size: `407`
- prototype: `void __fastcall(CEditView *__hidden this, struct CDC *, struct CPrintInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18003c0d0`
- `0x180054570`
- `0x180068fe0`
- `0x1800d1f92`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800690b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800690b2`
- `KERNEL32!MulDiv` at `0x1800690f4`
- `KERNEL32!MulDiv` at `0x180069126`
- `KERNEL32!MulDiv` at `0x1800690f4`
- `KERNEL32!MulDiv` at `0x180069126`
- `USER32!ReleaseDC` at `0x180069135`
- `USER32!ReleaseDC` at `0x180069135`
- `USER32!GetDC` at `0x1800690c3`
- `USER32!GetDC` at `0x1800690c3`
- `GDI32!GetDeviceCaps` at `0x1800690d4`
- `GDI32!GetDeviceCaps` at `0x1800690e5`
- `GDI32!GetDeviceCaps` at `0x180069106`
- `GDI32!GetDeviceCaps` at `0x180069117`
- `GDI32!GetDeviceCaps` at `0x1800690d4`
- `GDI32!GetDeviceCaps` at `0x1800690e5`
- `GDI32!GetDeviceCaps` at `0x180069106`
- `GDI32!GetDeviceCaps` at `0x180069117`
- `GDI32!GetStockObject` at `0x180069076`
- `GDI32!GetStockObject` at `0x180069076`
- `GDI32!CreateFontIndirectW` at `0x180069140`
- `GDI32!CreateFontIndirectW` at `0x180069140`
- `GDI32!GetObjectW` at `0x18006906d`
- `GDI32!GetObjectW` at `0x180069089`
- `GDI32!GetObjectW` at `0x18006906d`
- `GDI32!GetObjectW` at `0x180069089`

## pseudocode

```c
void __fastcall CEditView::OnBeginPrinting(CEditView *this, HDC *a2, struct CPrintInfo *a3)
{
  struct CFont *Font; // rbx
  HGDIOBJ StockObject; // rax
  HDC DC; // rdi
  int DeviceCaps; // ebx
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  HFONT v12; // rax
  LOGFONTW pv; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v14[28]; // [rsp+90h] [rbp-88h] BYREF
  WCHAR String2[34]; // [rsp+ACh] [rbp-6Ch] BYREF

  CUIntArray::SetAtGrow((CEditView *)((char *)this + 176), *((_QWORD *)this + 24), 0);
  if ( !*((_QWORD *)this + 27) )
  {
    Font = CWnd::GetFont(this);
    memset_0(&pv, 0, sizeof(pv));
    memset_0(v14, 0, 0x5Cu);
    if ( Font )
    {
      GetObjectW(*((HANDLE *)Font + 1), 92, &pv);
      StockObject = GetStockObject(13);
      GetObjectW(StockObject, 92, v14);
      if ( CompareStringW(0x409u, 1u, pv.lfFaceName, -1, String2, -1) != 2 )
      {
        DC = GetDC(0);
        DeviceCaps = GetDeviceCaps(DC, 90);
        v9 = GetDeviceCaps(a2[2], 90);
        pv.lfHeight = MulDiv(pv.lfHeight, v9, DeviceCaps);
        v10 = GetDeviceCaps(DC, 88);
        v11 = GetDeviceCaps(a2[2], 88);
        pv.lfWidth = MulDiv(pv.lfWidth, v11, v10);
        ReleaseDC(0, DC);
        v12 = CreateFontIndirectW(&pv);
        *((_QWORD *)this + 28) = v12;
        *((_QWORD *)this + 27) = v12;
      }
    }
  }
}

```

## disassembly

```asm
0x180068fe0  mov     [rsp+arg_10], rbx
0x180068fe5  push    rbp
0x180068fe6  push    rsi
0x180068fe7  push    rdi
0x180068fe8  sub     rsp, 100h
0x180068fef  mov     rax, cs:__security_cookie
0x180068ff6  xor     rax, rsp
0x180068ff9  mov     [rsp+118h+var_28], rax
0x180069001  mov     rsi, rcx
0x180069004  mov     rbp, rdx
0x180069007  add     rcx, 0B0h; this
0x18006900e  xor     r8d, r8d; unsigned int
0x180069011  mov     rdx, [rcx+10h]; __int64
0x180069015  call    ?SetAtGrow@CUIntArray@@QEAAX_JI@Z; CUIntArray::SetAtGrow(__int64,uint)
0x18006901a  cmp     qword ptr [rsi+0D8h], 0
0x180069022  jnz     loc_180069154
0x180069028  mov     rcx, rsi; this
0x18006902b  call    ?GetFont@CWnd@@QEBAPEAVCFont@@XZ; CWnd::GetFont(void)
0x180069030  mov     edi, 5Ch ; '\'
0x180069035  lea     rcx, [rsp+118h+pv]; void *
0x18006903a  mov     r8d, edi; Size
0x18006903d  xor     edx, edx; Val
0x18006903f  mov     rbx, rax
0x180069042  call    memset_0
0x180069047  mov     r8d, edi; Size
0x18006904a  lea     rcx, [rsp+118h+var_88]; void *
0x180069052  xor     edx, edx; Val
0x180069054  call    memset_0
0x180069059  test    rbx, rbx
0x18006905c  jz      loc_180069154
0x180069062  mov     rcx, [rbx+8]; h
0x180069066  lea     r8, [rsp+118h+pv]; pv
0x18006906b  mov     edx, edi; c
0x18006906d  call    cs:__imp_GetObjectW
0x180069073  lea     ecx, [rdi-4Fh]; i
0x180069076  call    cs:__imp_GetStockObject
0x18006907c  lea     r8, [rsp+118h+var_88]; pv
0x180069084  mov     edx, edi; c
0x180069086  mov     rcx, rax; h
0x180069089  call    cs:__imp_GetObjectW
0x18006908f  or      r9d, 0FFFFFFFFh; cchCount1
0x180069093  lea     rax, [rsp+118h+String2]
0x18006909b  mov     [rsp+118h+cchCount2], r9d; cchCount2
0x1800690a0  lea     r8, [rsp+118h+String1]; lpString1
0x1800690a5  lea     edx, [rdi-5Bh]; dwCmpFlags
0x1800690a8  mov     [rsp+118h+lpString2], rax; lpString2
0x1800690ad  mov     ecx, 409h; Locale
0x1800690b2  call    cs:__imp_CompareStringW
0x1800690b8  cmp     eax, 2
0x1800690bb  jz      loc_180069154
0x1800690c1  xor     ecx, ecx; hWnd
0x1800690c3  call    cs:__imp_GetDC
0x1800690c9  mov     rcx, rax; hdc
0x1800690cc  mov     edx, 5Ah ; 'Z'; index
0x1800690d1  mov     rdi, rax
0x1800690d4  call    cs:__imp_GetDeviceCaps
0x1800690da  mov     rcx, [rbp+10h]; hdc
0x1800690de  mov     edx, 5Ah ; 'Z'; index
0x1800690e3  mov     ebx, eax
0x1800690e5  call    cs:__imp_GetDeviceCaps
0x1800690eb  mov     ecx, [rsp+118h+pv]; nNumber
0x1800690ef  mov     r8d, ebx; nDenominator
0x1800690f2  mov     edx, eax; nNumerator
0x1800690f4  call    cs:__imp_MulDiv
0x1800690fa  mov     edx, 58h ; 'X'; index
0x1800690ff  mov     rcx, rdi; hdc
0x180069102  mov     [rsp+118h+pv], eax
0x180069106  call    cs:__imp_GetDeviceCaps
0x18006910c  mov     rcx, [rbp+10h]; hdc
0x180069110  mov     edx, 58h ; 'X'; index
0x180069115  mov     ebx, eax
0x180069117  call    cs:__imp_GetDeviceCaps
0x18006911d  mov     ecx, [rsp+118h+nNumber]; nNumber
0x180069121  mov     r8d, ebx; nDenominator
0x180069124  mov     edx, eax; nNumerator
0x180069126  call    cs:__imp_MulDiv
0x18006912c  mov     rdx, rdi; hDC
0x18006912f  xor     ecx, ecx; hWnd
0x180069131  mov     [rsp+118h+nNumber], eax
0x180069135  call    cs:__imp_ReleaseDC
0x18006913b  lea     rcx, [rsp+118h+pv]; lplf
0x180069140  call    cs:__imp_CreateFontIndirectW
0x180069146  mov     [rsi+0E0h], rax
0x18006914d  mov     [rsi+0D8h], rax
0x180069154  mov     rcx, [rsp+118h+var_28]
0x18006915c  xor     rcx, rsp; StackCookie
0x18006915f  call    __security_check_cookie
0x180069164  mov     rbx, [rsp+118h+arg_10]
0x18006916c  add     rsp, 100h
0x180069173  pop     rdi
0x180069174  pop     rsi
0x180069175  pop     rbp
0x180069176  retn
```
