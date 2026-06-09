# HrCreateTridentMenu

- ea: `0x1800081b0`
- end: `0x180008365`
- name: `HrCreateTridentMenu`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800081b0`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000830f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000830f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180008325`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180008325`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800082c5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800082c5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800082b1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800082b1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800082ed`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800082ed`
- `USER32!CreatePopupMenu` at `0x180008208`
- `USER32!CreatePopupMenu` at `0x180008208`
- `USER32!AppendMenuW` at `0x180008305`
- `USER32!AppendMenuW` at `0x180008305`

## pseudocode

```c
__int64 __fastcall HrCreateTridentMenu(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        unsigned int a3,
        int a4,
        HMENU *a5)
{
  HMENU *v5; // r12
  HMENU PopupMenu; // r14
  int v12; // ebx
  SAFEARRAY *v13; // rsi
  int v14; // r15d
  UINT_PTR v15; // r8
  LONG plUbound; // [rsp+40h] [rbp-30h] BYREF
  LONG plLbound; // [rsp+44h] [rbp-2Ch] BYREF
  WCHAR *pv; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  SAFEARRAY *psa[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v21; // [rsp+68h] [rbp-8h]
  LONG rgIndices; // [rsp+B0h] [rbp+40h] BYREF

  v5 = a5;
  v21 = 0;
  plLbound = 0;
  plUbound = 0;
  rgIndices = 0;
  pv = 0;
  v19 = 0;
  *(_OWORD *)psa = 0;
  if ( !a5 || !a1 )
    return 2147942487LL;
  PopupMenu = CreatePopupMenu();
  if ( !PopupMenu )
    return 2147942414LL;
  if ( a2 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v12 = (**a1)(a1, &IID_IOleCommandTarget, &v19);
    if ( v12 >= 0 )
    {
      LOWORD(psa[0]) = 0x2000;
      psa[1] = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, __int64, _QWORD, SAFEARRAY **))(*(_QWORD *)v19 + 32LL))(
              v19,
              &CGID_MSHTML,
              2233,
              2,
              0,
              psa);
      if ( v12 >= 0 )
      {
        v13 = psa[1];
        if ( !SafeArrayGetLBound(psa[1], 1u, &plLbound) && !SafeArrayGetUBound(v13, 1u, &plUbound) )
        {
          rgIndices = plLbound;
          if ( plLbound <= plUbound )
          {
            v14 = a3 + a4;
            do
            {
              if ( a3 == v14 )
                break;
              if ( !SafeArrayGetElement(v13, &rgIndices, &pv) )
              {
                v15 = a3++;
                AppendMenuW(PopupMenu, 0, v15, pv);
                SysFreeString(pv);
              }
              ++rgIndices;
            }
            while ( rgIndices <= plUbound );
          }
        }
        SafeArrayDestroy(v13);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    if ( !v12 )
      *v5 = PopupMenu;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800081b0  mov     [rsp-28h+arg_0], rbx
0x1800081b5  mov     [rsp-28h+arg_8], rsi
0x1800081ba  push    rbp
0x1800081bb  push    rdi
0x1800081bc  push    r12
0x1800081be  push    r14
0x1800081c0  push    r15
0x1800081c2  mov     rbp, rsp
0x1800081c5  sub     rsp, 70h
0x1800081c9  mov     r12, [rbp+arg_20]
0x1800081cd  xor     eax, eax
0x1800081cf  mov     [rbp+var_8], rax
0x1800081d3  xorps   xmm0, xmm0
0x1800081d6  mov     [rbp+plLbound], eax
0x1800081d9  mov     r15d, r9d
0x1800081dc  mov     [rbp+plUbound], eax
0x1800081df  mov     edi, r8d
0x1800081e2  mov     [rbp+rgIndices], eax
0x1800081e5  mov     esi, edx
0x1800081e7  mov     [rbp+pv], rax
0x1800081eb  mov     rbx, rcx
0x1800081ee  mov     [rbp+var_20], rax
0x1800081f2  movups  xmmword ptr [rbp+psa], xmm0
0x1800081f6  test    r12, r12
0x1800081f9  jz      loc_180008347
0x1800081ff  test    rcx, rcx
0x180008202  jz      loc_180008347
0x180008208  call    cs:__imp_CreatePopupMenu
0x18000820e  mov     r14, rax
0x180008211  test    rax, rax
0x180008214  jnz     short loc_180008220
0x180008216  mov     eax, 8007000Eh
0x18000821b  jmp     loc_18000834C
0x180008220  test    esi, esi
0x180008222  jz      short loc_18000822E
0x180008224  mov     ebx, 80004005h
0x180008229  jmp     loc_180008343
0x18000822e  mov     rax, [rbx]
0x180008231  lea     r8, [rbp+var_20]
0x180008235  lea     rdx, IID_IOleCommandTarget
0x18000823c  mov     rcx, rbx
0x18000823f  mov     rax, [rax]
0x180008242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008247  mov     ebx, eax
0x180008249  test    eax, eax
0x18000824b  js      loc_18000833B
0x180008251  mov     rcx, [rbp+var_20]
0x180008255  lea     rdx, [rbp+psa]
0x180008259  mov     [rsp+70h+var_48], rdx
0x18000825e  mov     eax, 2000h
0x180008263  mov     word ptr [rbp+psa], ax
0x180008267  lea     rdx, CGID_MSHTML
0x18000826e  mov     [rbp+psa+8], 0
0x180008276  mov     r9d, 2
0x18000827c  mov     rax, [rcx]
0x18000827f  mov     r8d, 8B9h
0x180008285  mov     [rsp+70h+var_50], 0
0x18000828e  mov     rax, [rax+20h]
0x180008292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008297  mov     ebx, eax
0x180008299  test    eax, eax
0x18000829b  js      loc_18000832B
0x1800082a1  mov     rsi, [rbp+psa+8]
0x1800082a5  lea     r8, [rbp+plLbound]; plLbound
0x1800082a9  mov     rcx, rsi; psa
0x1800082ac  mov     edx, 1; nDim
0x1800082b1  call    cs:__imp_SafeArrayGetLBound
0x1800082b7  test    eax, eax
0x1800082b9  jnz     short loc_180008322
0x1800082bb  lea     r8, [rbp+plUbound]; plUbound
0x1800082bf  mov     rcx, rsi; psa
0x1800082c2  lea     edx, [rax+1]; nDim
0x1800082c5  call    cs:__imp_SafeArrayGetUBound
0x1800082cb  test    eax, eax
0x1800082cd  jnz     short loc_180008322
0x1800082cf  mov     eax, [rbp+plLbound]
0x1800082d2  mov     [rbp+rgIndices], eax
0x1800082d5  cmp     eax, [rbp+plUbound]
0x1800082d8  jg      short loc_180008322
0x1800082da  add     r15d, edi
0x1800082dd  cmp     edi, r15d
0x1800082e0  jz      short loc_180008322
0x1800082e2  lea     r8, [rbp+pv]; pv
0x1800082e6  mov     rcx, rsi; psa
0x1800082e9  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800082ed  call    cs:__imp_SafeArrayGetElement
0x1800082f3  test    eax, eax
0x1800082f5  jnz     short loc_180008315
0x1800082f7  mov     r9, [rbp+pv]; lpNewItem
0x1800082fb  xor     edx, edx; uFlags
0x1800082fd  mov     r8d, edi; uIDNewItem
0x180008300  mov     rcx, r14; hMenu
0x180008303  inc     edi
0x180008305  call    cs:__imp_AppendMenuW
0x18000830b  mov     rcx, [rbp+pv]; bstrString
0x18000830f  call    cs:__imp_SysFreeString
0x180008315  mov     eax, [rbp+rgIndices]
0x180008318  inc     eax
0x18000831a  mov     [rbp+rgIndices], eax
0x18000831d  cmp     eax, [rbp+plUbound]
0x180008320  jle     short loc_1800082DD
0x180008322  mov     rcx, rsi; psa
0x180008325  call    cs:__imp_SafeArrayDestroy
0x18000832b  mov     rcx, [rbp+var_20]
0x18000832f  mov     rax, [rcx]
0x180008332  mov     rax, [rax+10h]
0x180008336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000833b  test    ebx, ebx
0x18000833d  jnz     short loc_180008343
0x18000833f  mov     [r12], r14
0x180008343  mov     eax, ebx
0x180008345  jmp     short loc_18000834C
0x180008347  mov     eax, 80070057h
0x18000834c  lea     r11, [rsp+70h+var_s0]
0x180008351  mov     rbx, [r11+30h]
0x180008355  mov     rsi, [r11+38h]
0x180008359  mov     rsp, r11
0x18000835c  pop     r15
0x18000835e  pop     r14
0x180008360  pop     r12
0x180008362  pop     rdi
0x180008363  pop     rbp
0x180008364  retn
```
