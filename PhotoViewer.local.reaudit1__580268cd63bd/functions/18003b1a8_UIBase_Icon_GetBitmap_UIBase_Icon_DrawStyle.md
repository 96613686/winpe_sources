# UIBase::Icon::GetBitmap(UIBase::Icon::DrawStyle)

- ea: `0x18003b1a8`
- end: `0x18003b421`
- name: `?GetBitmap@Icon@UIBase@@QEBAPEAUHBITMAP__@@W4DrawStyle@12@@Z`
- size: `633`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006aeb4`
- `0x18006d440`

## callees

- `0x18000cb74`
- `0x18002ac68`
- `0x18003b1a8`
- `0x18003b428`
- `0x18003f800`
- `0x180040264`
- `0x180073d18`
- `0x180073f48`
- `0x180080010`

## import_xrefs

- `GDI32!SelectObject` at `0x18003b29e`
- `GDI32!SelectObject` at `0x18003b3c9`
- `GDI32!SelectObject` at `0x18003b29e`
- `GDI32!SelectObject` at `0x18003b3c9`
- `GDI32!ExtTextOutW` at `0x18003b302`
- `GDI32!ExtTextOutW` at `0x18003b302`
- `GDI32!SetBkColor` at `0x18003b2d0`
- `GDI32!SetBkColor` at `0x18003b30d`
- `GDI32!SetBkColor` at `0x18003b2d0`
- `GDI32!SetBkColor` at `0x18003b30d`
- `GDI32!CreateCompatibleDC` at `0x18003b273`
- `GDI32!CreateCompatibleDC` at `0x18003b273`
- `GDI32!DeleteDC` at `0x18003b3eb`
- `GDI32!DeleteDC` at `0x18003b3eb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b213`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b23b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b26b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b28b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b32d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b3b8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b213`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b23b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b26b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b28b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b32d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b3b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
HGDIOBJ __fastcall UIBase::Icon::GetBitmap(__int64 a1)
{
  int v2; // edx
  __int64 v3; // rcx
  int v4; // edx
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // eax
  int v8; // edx
  int v9; // edx
  HDC CompatibleDC; // rbx
  HGDIOBJ v11; // rdx
  HGDIOBJ v12; // rsi
  COLORREF v13; // edi
  __int64 v14; // rdx
  int Interface; // eax
  int v16; // edx
  int v17; // eax
  int v18; // edx
  HGDIOBJ v19; // rdi
  void *v21; // [rsp+40h] [rbp-F8h] BYREF
  int v22; // [rsp+48h] [rbp-F0h] BYREF
  HGDIOBJ v23; // [rsp+50h] [rbp-E8h] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-D8h] BYREF
  _QWORD v26[3]; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+80h] [rbp-B8h] BYREF
  char v28[8]; // [rsp+88h] [rbp-B0h] BYREF
  int v29; // [rsp+90h] [rbp-A8h]
  HDC v30; // [rsp+98h] [rbp-A0h]
  void *v31; // [rsp+A8h] [rbp-90h]
  int v32; // [rsp+B8h] [rbp-80h]
  int v33; // [rsp+BCh] [rbp-7Ch]
  int v34; // [rsp+C0h] [rbp-78h]
  RECT rect; // [rsp+F0h] [rbp-48h] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
    return 0;
  v25 = 0;
  v22 = 0;
  (*(void (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)a1 + 32LL))(a1, &v25, &v22);
  v3 = v25;
  if ( !v25 )
    Base::Throw((Base *)0x80004005LL, v2);
  v21 = 0;
  if ( !(unsigned int)IsolationAwareImageList_GetIconSize(v3, &v21, (char *)&v21 + 4) )
    Base::Throw((Base *)0x80004005LL, v4);
  v23 = v21;
  h = 0;
  v7 = UIBase::LocalCopiedShellFunctions::Create32BitHBITMAP(v5, &v23, v6, &h);
  if ( v7 < 0 )
    Base::Throw((Base *)(unsigned int)v7, v8);
  CompatibleDC = CreateCompatibleDC(0);
  v26[1] = CompatibleDC;
  if ( !CompatibleDC )
    Base::Throw((Base *)0x80004005LL, v9);
  v11 = h;
  h = 0;
  v12 = SelectObject(CompatibleDC, v11);
  v23 = v12;
  *(_QWORD *)&rect.left = 0;
  *(_QWORD *)&rect.right = v21;
  v13 = SetBkColor(CompatibleDC, 0xFFFFFFFF);
  ExtTextOutW(CompatibleDC, 0, 0, 2u, &rect, 0, 0, 0);
  SetBkColor(CompatibleDC, v13);
  v26[0] = 0;
  Interface = IsolationAwareHIMAGELIST_QueryInterface(v25, v14, v26);
  if ( Interface < 0 )
    Base::Throw((Base *)(unsigned int)Interface, v16);
  v27 = 88;
  memset_0(v28, 0, 0x50u);
  v29 = v22;
  v30 = CompatibleDC;
  v31 = v21;
  v32 = -16777216;
  v33 = -16777216;
  v34 = 327681;
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v26[0] + 64LL))(v26[0], &v27);
  if ( v17 < 0 )
    Base::Throw((Base *)(unsigned int)v17, v18);
  v23 = 0;
  v19 = SelectObject(CompatibleDC, v12);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(v26);
  GdiUtil::AutoGDIObject<HBITMAP__ *,0,GdiUtil::DeleteObjectReleaser>::Release(&v23);
  DeleteDC(CompatibleDC);
  GdiUtil::AutoGDIObject<HBITMAP__ *,0,GdiUtil::DeleteObjectReleaser>::Release(&h);
  return v19;
}

```

## disassembly

```asm
0x18003b1a8  push    rbx
0x18003b1aa  push    rsi
0x18003b1ab  push    rdi
0x18003b1ac  push    r14
0x18003b1ae  sub     rsp, 118h
0x18003b1b5  mov     rax, cs:__security_cookie
0x18003b1bc  xor     rax, rsp
0x18003b1bf  mov     [rsp+138h+var_38], rax
0x18003b1c7  mov     rbx, rcx
0x18003b1ca  mov     rax, [rcx]
0x18003b1cd  mov     rax, [rax+8]
0x18003b1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1d6  xor     r14d, r14d
0x18003b1d9  test    al, al
0x18003b1db  jz      loc_18003B401
0x18003b1e1  mov     [rsp+138h+var_D8], r14
0x18003b1e6  mov     [rsp+138h+var_F0], r14d
0x18003b1eb  mov     rax, [rbx]
0x18003b1ee  lea     r8, [rsp+138h+var_F0]
0x18003b1f3  lea     rdx, [rsp+138h+var_D8]
0x18003b1f8  mov     rcx, rbx
0x18003b1fb  mov     rax, [rax+20h]
0x18003b1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b204  mov     rcx, [rsp+138h+var_D8]
0x18003b209  test    rcx, rcx
0x18003b20c  jnz     short loc_18003B219
0x18003b20e  mov     ecx, 80004005h
0x18003b213  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b219  mov     dword ptr [rsp+138h+var_F8], r14d
0x18003b21e  mov     dword ptr [rsp+138h+var_F8+4], r14d
0x18003b223  lea     r8, [rsp+138h+var_F8+4]
0x18003b228  lea     rdx, [rsp+138h+var_F8]
0x18003b22d  call    IsolationAwareImageList_GetIconSize
0x18003b232  test    eax, eax
0x18003b234  jnz     short loc_18003B241
0x18003b236  mov     ecx, 80004005h
0x18003b23b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b241  mov     eax, dword ptr [rsp+138h+var_F8]
0x18003b245  mov     dword ptr [rsp+138h+var_E8], eax
0x18003b249  mov     eax, dword ptr [rsp+138h+var_F8+4]
0x18003b24d  mov     dword ptr [rsp+138h+var_E8+4], eax
0x18003b251  mov     [rsp+138h+h], r14
0x18003b256  lea     r9, [rsp+138h+h]
0x18003b25b  lea     rdx, [rsp+138h+var_E8]
0x18003b260  call    UIBase__LocalCopiedShellFunctions__Create32BitHBITMAP
0x18003b265  test    eax, eax
0x18003b267  jns     short loc_18003B271
0x18003b269  mov     ecx, eax
0x18003b26b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b271  xor     ecx, ecx; hdc
0x18003b273  call    cs:__imp_CreateCompatibleDC
0x18003b279  mov     rbx, rax
0x18003b27c  mov     [rsp+138h+var_C8], rax
0x18003b281  test    rax, rax
0x18003b284  jnz     short loc_18003B291
0x18003b286  mov     ecx, 80004005h
0x18003b28b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b291  mov     rdx, [rsp+138h+h]; h
0x18003b296  mov     [rsp+138h+h], r14
0x18003b29b  mov     rcx, rbx; hdc
0x18003b29e  call    cs:__imp_SelectObject
0x18003b2a4  mov     rsi, rax
0x18003b2a7  mov     [rsp+138h+var_E8], rax
0x18003b2ac  mov     qword ptr [rsp+138h+rect.left], r14
0x18003b2b4  mov     ecx, dword ptr [rsp+138h+var_F8]
0x18003b2b8  mov     [rsp+138h+rect.right], ecx
0x18003b2bf  mov     ecx, dword ptr [rsp+138h+var_F8+4]
0x18003b2c3  mov     [rsp+138h+rect.bottom], ecx
0x18003b2ca  or      edx, 0FFFFFFFFh; color
0x18003b2cd  mov     rcx, rbx; hdc
0x18003b2d0  call    cs:__imp_SetBkColor
0x18003b2d6  mov     edi, eax
0x18003b2d8  mov     [rsp+138h+lpDx], r14; lpDx
0x18003b2dd  mov     [rsp+138h+c], r14d; c
0x18003b2e2  mov     [rsp+138h+lpString], r14; lpString
0x18003b2e7  lea     rax, [rsp+138h+rect]
0x18003b2ef  mov     [rsp+138h+lprect], rax; lprect
0x18003b2f4  mov     r9d, 2; options
0x18003b2fa  xor     r8d, r8d; y
0x18003b2fd  xor     edx, edx; x
0x18003b2ff  mov     rcx, rbx; hdc
0x18003b302  call    cs:__imp_ExtTextOutW
0x18003b308  mov     edx, edi; color
0x18003b30a  mov     rcx, rbx; hdc
0x18003b30d  call    cs:__imp_SetBkColor
0x18003b313  mov     [rsp+138h+var_D0], r14
0x18003b318  lea     r8, [rsp+138h+var_D0]
0x18003b31d  mov     rcx, [rsp+138h+var_D8]
0x18003b322  call    IsolationAwareHIMAGELIST_QueryInterface
0x18003b327  test    eax, eax
0x18003b329  jns     short loc_18003B333
0x18003b32b  mov     ecx, eax
0x18003b32d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b333  mov     [rsp+138h+var_B8], 58h ; 'X'
0x18003b33f  xor     edx, edx; Val
0x18003b341  lea     r8d, [rdx+50h]; Size
0x18003b345  lea     rcx, [rsp+138h+var_B0]; void *
0x18003b34d  call    memset_0
0x18003b352  mov     eax, [rsp+138h+var_F0]
0x18003b356  mov     [rsp+138h+var_A8], eax
0x18003b35d  mov     [rsp+138h+var_A0], rbx
0x18003b365  mov     eax, dword ptr [rsp+138h+var_F8]
0x18003b369  mov     dword ptr [rsp+138h+var_90], eax
0x18003b370  mov     eax, dword ptr [rsp+138h+var_F8+4]
0x18003b374  mov     dword ptr [rsp+138h+var_90+4], eax
0x18003b37b  mov     eax, 0FF000000h
0x18003b380  mov     [rsp+138h+var_80], eax
0x18003b387  mov     [rsp+138h+var_7C], eax
0x18003b38e  mov     [rsp+138h+var_78], 50001h
0x18003b399  mov     rcx, [rsp+138h+var_D0]
0x18003b39e  mov     rax, [rcx]
0x18003b3a1  lea     rdx, [rsp+138h+var_B8]
0x18003b3a9  mov     rax, [rax+40h]
0x18003b3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3b2  test    eax, eax
0x18003b3b4  jns     short loc_18003B3BE
0x18003b3b6  mov     ecx, eax
0x18003b3b8  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b3be  mov     [rsp+138h+var_E8], r14
0x18003b3c3  mov     rdx, rsi; h
0x18003b3c6  mov     rcx, rbx; hdc
0x18003b3c9  call    cs:__imp_SelectObject
0x18003b3cf  mov     rdi, rax
0x18003b3d2  lea     rcx, [rsp+138h+var_D0]
0x18003b3d7  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003b3dc  nop
0x18003b3dd  lea     rcx, [rsp+138h+var_E8]
0x18003b3e2  call    ?Release@?$AutoGDIObject@PEAUHBITMAP__@@$0A@UDeleteObjectReleaser@GdiUtil@@@GdiUtil@@QEAAXXZ; GdiUtil::AutoGDIObject<HBITMAP__ *,0,GdiUtil::DeleteObjectReleaser>::Release(void)
0x18003b3e7  nop
0x18003b3e8  mov     rcx, rbx; hdc
0x18003b3eb  call    cs:__imp_DeleteDC
0x18003b3f1  nop
0x18003b3f2  lea     rcx, [rsp+138h+h]
0x18003b3f7  call    ?Release@?$AutoGDIObject@PEAUHBITMAP__@@$0A@UDeleteObjectReleaser@GdiUtil@@@GdiUtil@@QEAAXXZ; GdiUtil::AutoGDIObject<HBITMAP__ *,0,GdiUtil::DeleteObjectReleaser>::Release(void)
0x18003b3fc  mov     rax, rdi
0x18003b3ff  jmp     short loc_18003B403
0x18003b401  xor     eax, eax
0x18003b403  mov     rcx, [rsp+138h+var_38]
0x18003b40b  xor     rcx, rsp; StackCookie
0x18003b40e  call    __security_check_cookie
0x18003b413  add     rsp, 118h
0x18003b41a  pop     r14
0x18003b41c  pop     rdi
0x18003b41d  pop     rsi
0x18003b41e  pop     rbx
0x18003b41f  retn
```
