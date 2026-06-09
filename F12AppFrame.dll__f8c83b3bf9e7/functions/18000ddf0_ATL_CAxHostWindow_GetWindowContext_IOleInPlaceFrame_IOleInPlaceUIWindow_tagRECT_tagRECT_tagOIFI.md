# ATL::CAxHostWindow::GetWindowContext(IOleInPlaceFrame * *,IOleInPlaceUIWindow * *,tagRECT *,tagRECT *,tagOIFI *)

- ea: `0x18000ddf0`
- end: `0x18000dfa5`
- name: `?GetWindowContext@CAxHostWindow@ATL@@UEAAJPEAPEAUIOleInPlaceFrame@@PEAPEAUIOleInPlaceUIWindow@@PEAUtagRECT@@2PEAUtagOIFI@@@Z`
- size: `437`
- prototype: `int(ATL::CAxHostWindow *__hidden this, struct IOleInPlaceFrame **, struct IOleInPlaceUIWindow **, struct tagRECT *, struct tagRECT *, struct tagOIFI *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000c854`
- `0x18000c91c`
- `0x18000ddf0`
- `0x180035010`

## import_xrefs

- `USER32!GetClientRect` at `0x18000df03`
- `USER32!GetClientRect` at `0x18000df15`
- `USER32!GetClientRect` at `0x18000df03`
- `USER32!GetClientRect` at `0x18000df15`
- `USER32!GetParent` at `0x18000df6a`
- `USER32!GetParent` at `0x18000df6a`
- `USER32!CreateAcceleratorTableW` at `0x18000df3c`
- `USER32!CreateAcceleratorTableW` at `0x18000df3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAxHostWindow::GetWindowContext(
        ATL::CAxHostWindow *this,
        struct IOleInPlaceFrame **a2,
        struct IOleInPlaceUIWindow **a3,
        struct tagRECT *a4,
        struct tagRECT *lpRect,
        struct tagOIFI *a6)
{
  _QWORD *v10; // r15
  _QWORD *v11; // r14
  struct tagOIFI *v12; // rbx
  __int64 paccel; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !a3 || !a4 || !lpRect )
    return 2147500035LL;
  v10 = (_QWORD *)((char *)this + 120);
  if ( !*((_QWORD *)this + 15) )
  {
    paccel = 0;
    ATL::CComObject<ATL::CAxFrameWindow>::CreateInstance(&paccel);
    (**(void (__fastcall ***)(__int64, GUID *, _QWORD *))(paccel + 72))(
      paccel + 72,
      &GUID_00000116_0000_0000_c000_000000000046,
      v10);
  }
  v11 = (_QWORD *)((char *)this + 128);
  if ( !*((_QWORD *)this + 16) )
  {
    paccel = 0;
    ATL::CComObject<ATL::CAxUIWindow>::CreateInstance(&paccel);
    (**(void (__fastcall ***)(__int64, GUID *, char *))(paccel + 72))(
      paccel + 72,
      &GUID_00000115_0000_0000_c000_000000000046,
      (char *)this + 128);
  }
  *a2 = (struct IOleInPlaceFrame *)*v10;
  if ( *v10 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  *a3 = (struct IOleInPlaceUIWindow *)*v11;
  if ( *v11 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  GetClientRect(*((HWND *)this - 10), a4);
  GetClientRect(*((HWND *)this - 10), lpRect);
  if ( !*((_QWORD *)this + 30) )
  {
    LODWORD(paccel) = 0;
    WORD2(paccel) = 0;
    *((_QWORD *)this + 30) = CreateAcceleratorTableW((LPACCEL)&paccel, 1);
  }
  v12 = a6;
  a6->cb = 32;
  v12->fMDIApp = (*((_DWORD *)this + 48) >> 2) & 1;
  v12->hwndFrame = GetParent(*((HWND *)this - 10));
  v12->haccel = (HACCEL)*((_QWORD *)this + 30);
  v12->cAccelEntries = *((_QWORD *)this + 30) != 0;
  return 0;
}

```

## disassembly

```asm
0x18000ddf0  push    rbx
0x18000ddf2  push    rsi
0x18000ddf3  push    rdi
0x18000ddf4  push    r12
0x18000ddf6  push    r14
0x18000ddf8  push    r15
0x18000ddfa  sub     rsp, 28h
0x18000ddfe  mov     r12, r9
0x18000de01  mov     rbx, r8
0x18000de04  mov     rsi, rdx
0x18000de07  mov     rdi, rcx
0x18000de0a  test    rdx, rdx
0x18000de0d  jz      short loc_18000DE16
0x18000de0f  mov     qword ptr [rdx], 0
0x18000de16  test    rbx, rbx
0x18000de19  jz      short loc_18000DE22
0x18000de1b  mov     qword ptr [r8], 0
0x18000de22  test    rsi, rsi
0x18000de25  jz      loc_18000DF92
0x18000de2b  test    rbx, rbx
0x18000de2e  jz      loc_18000DF92
0x18000de34  test    r12, r12
0x18000de37  jz      loc_18000DF92
0x18000de3d  cmp     [rsp+58h+lpRect], 0
0x18000de46  jz      loc_18000DF92
0x18000de4c  lea     r15, [rcx+78h]
0x18000de50  cmp     qword ptr [r15], 0
0x18000de54  jnz     short loc_18000DE87
0x18000de56  mov     [rsp+58h+paccel], 0
0x18000de5f  lea     rcx, [rsp+58h+paccel]
0x18000de64  call    ?CreateInstance@?$CComObject@VCAxFrameWindow@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CAxFrameWindow>::CreateInstance(ATL::CComObject<ATL::CAxFrameWindow> * *)
0x18000de69  mov     rcx, [rsp+58h+paccel]
0x18000de6e  add     rcx, 48h ; 'H'
0x18000de72  mov     rax, [rcx]
0x18000de75  mov     r8, r15
0x18000de78  lea     rdx, _GUID_00000116_0000_0000_c000_000000000046
0x18000de7f  mov     rax, [rax]
0x18000de82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de87  lea     r14, [rdi+80h]
0x18000de8e  cmp     qword ptr [r14], 0
0x18000de92  jnz     short loc_18000DEC6
0x18000de94  mov     [rsp+58h+paccel], 0
0x18000de9d  lea     rcx, [rsp+58h+paccel]
0x18000dea2  call    ?CreateInstance@?$CComObject@VCAxUIWindow@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CAxUIWindow>::CreateInstance(ATL::CComObject<ATL::CAxUIWindow> * *)
0x18000dea7  mov     rcx, [rsp+58h+paccel]
0x18000deac  add     rcx, 48h ; 'H'
0x18000deb0  mov     rax, [rcx]
0x18000deb3  mov     r8, r14
0x18000deb6  lea     rdx, _GUID_00000115_0000_0000_c000_000000000046
0x18000debd  mov     rax, [rax]
0x18000dec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dec5  nop
0x18000dec6  mov     rax, [r15]
0x18000dec9  mov     [rsi], rax
0x18000decc  mov     rcx, [r15]
0x18000decf  test    rcx, rcx
0x18000ded2  jz      short loc_18000DEE1
0x18000ded4  mov     rax, [rcx]
0x18000ded7  mov     rax, [rax+8]
0x18000dedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dee0  nop
0x18000dee1  mov     rax, [r14]
0x18000dee4  mov     [rbx], rax
0x18000dee7  mov     rcx, [r14]
0x18000deea  test    rcx, rcx
0x18000deed  jz      short loc_18000DEFC
0x18000deef  mov     rax, [rcx]
0x18000def2  mov     rax, [rax+8]
0x18000def6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000defb  nop
0x18000defc  mov     rdx, r12; lpRect
0x18000deff  mov     rcx, [rdi-50h]; hWnd
0x18000df03  call    cs:__imp_GetClientRect
0x18000df09  mov     rdx, [rsp+58h+lpRect]; lpRect
0x18000df11  mov     rcx, [rdi-50h]; hWnd
0x18000df15  call    cs:__imp_GetClientRect
0x18000df1b  cmp     qword ptr [rdi+0F0h], 0
0x18000df23  jnz     short loc_18000DF49
0x18000df25  mov     dword ptr [rsp+58h+paccel], 0
0x18000df2d  xor     eax, eax
0x18000df2f  mov     word ptr [rsp+58h+paccel+4], ax
0x18000df34  lea     edx, [rax+1]; cAccel
0x18000df37  lea     rcx, [rsp+58h+paccel]; paccel
0x18000df3c  call    cs:__imp_CreateAcceleratorTableW
0x18000df42  mov     [rdi+0F0h], rax
0x18000df49  mov     rbx, [rsp+58h+arg_28]
0x18000df51  mov     dword ptr [rbx], 20h ; ' '
0x18000df57  mov     eax, [rdi+0C0h]
0x18000df5d  shr     eax, 2
0x18000df60  and     eax, 1
0x18000df63  mov     [rbx+4], eax
0x18000df66  mov     rcx, [rdi-50h]; hWnd
0x18000df6a  call    cs:__imp_GetParent
0x18000df70  mov     [rbx+8], rax
0x18000df74  mov     rax, [rdi+0F0h]
0x18000df7b  mov     [rbx+10h], rax
0x18000df7f  xor     eax, eax
0x18000df81  cmp     [rdi+0F0h], rax
0x18000df88  setnz   al
0x18000df8b  mov     [rbx+18h], eax
0x18000df8e  xor     eax, eax
0x18000df90  jmp     short loc_18000DF97
0x18000df92  mov     eax, 80004003h
0x18000df97  add     rsp, 28h
0x18000df9b  pop     r15
0x18000df9d  pop     r14
0x18000df9f  pop     r12
0x18000dfa1  pop     rdi
0x18000dfa2  pop     rsi
0x18000dfa3  pop     rbx
0x18000dfa4  retn
```
