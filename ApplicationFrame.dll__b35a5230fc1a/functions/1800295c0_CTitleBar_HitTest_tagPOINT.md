# CTitleBar::_HitTest(tagPOINT)

- ea: `0x1800295c0`
- end: `0x18002995b`
- name: `?_HitTest@CTitleBar@@AEAA?AW4TitleBarControl@1@UtagPOINT@@@Z`
- size: `923`
- prototype: `enum CTitleBar::TitleBarControl __high(struct tagPOINT)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180028ed8`
- `0x1800292c4`
- `0x18002936c`
- `0x180029fa0`
- `0x18002a2e0`
- `0x18005b2c4`
- `0x18005b30c`

## callees

- `0x1800295c0`
- `0x180043c30`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029611`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029661`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029677`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002968c`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800296a1`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800296bc`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029752`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800297c3`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800297d4`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800297e9`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029801`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029819`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029832`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002990f`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029611`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029661`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029677`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002968c`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800296a1`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800296bc`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029752`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800297c3`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800297d4`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x1800297e9`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029801`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029819`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x180029832`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002990f`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002970f`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002970f`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x1800296e8`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x1800296f9`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x1800296e8`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x1800296f9`

## pseudocode

```c
__int64 __fastcall CTitleBar::_HitTest(__int64 a1, POINT a2)
{
  unsigned __int64 v2; // rdi
  bool v5; // bp
  const RECT *v6; // r12
  unsigned int v7; // edi
  __int64 v9; // r15
  HWND *v10; // r14
  bool v11; // zf
  LONG v12; // eax
  LONG v13; // ecx
  RECT rc; // [rsp+20h] [rbp-48h] BYREF

  *(POINT *)&rc.left = a2;
  v2 = HIDWORD(*(unsigned __int64 *)&a2);
  v5 = (*(_DWORD *)(a1 + 1456) & 0x100) != 0 && *(_DWORD *)(a1 + 552) == 1;
  v6 = (const RECT *)(a1 + 852);
  if ( PtInRect((const RECT *)(a1 + 852), a2) || v5 && !(_DWORD)v2 )
  {
    v7 = 9;
    if ( PtInRect((const RECT *)(a1 + 1300), a2) )
    {
      v9 = 8;
    }
    else if ( PtInRect((const RECT *)(a1 + 1364), a2) )
    {
      v9 = 9;
    }
    else if ( PtInRect((const RECT *)(a1 + 1316), a2) )
    {
      v9 = 23;
    }
    else if ( PtInRect((const RECT *)(a1 + 1332), a2) )
    {
      v9 = 24;
    }
    else
    {
      v9 = 1;
      if ( PtInRect((const RECT *)(a1 + 1348), a2) )
        v9 = 20;
    }
    v10 = (HWND *)(a1 + 504);
    if ( (*(_BYTE *)(a1 + 1452) & 2) != 0 && !IsZoomed(*v10) )
    {
      v13 = *(_DWORD *)(a1 + 632);
      if ( rc.top <= v13 )
      {
        if ( a2.x >= v6->right - v13 - v6->left )
          v9 = 14;
        else
          v9 = (a2.x <= v13) + 12LL;
      }
    }
    if ( IsZoomed(*v10) && !IsRectEmpty((const RECT *)(a1 + 1348)) )
    {
      v11 = *(_BYTE *)(a1 + 559) == 0;
      v12 = *(_DWORD *)(a1 + 856);
      rc = *(RECT *)(a1 + 1348);
      rc.top = v12;
      if ( !v11 || *(_BYTE *)(a1 + 560) )
        rc.left = v6->left;
      else
        rc.right = v6->right;
      if ( PtInRect(&rc, a2) )
        return 11;
    }
    switch ( v9 )
    {
      case 3LL:
        return 4;
      case 1LL:
LABEL_34:
        if ( PtInRect((const RECT *)(a1 + 1252), a2) )
          return 4;
        if ( PtInRect((const RECT *)(a1 + 1268), a2) )
        {
          return 5;
        }
        else if ( PtInRect((const RECT *)(a1 + 1284), a2) )
        {
          return 6;
        }
        else if ( PtInRect((const RECT *)(a1 + 1380), a2) )
        {
          return 12;
        }
        else if ( PtInRect((const RECT *)(a1 + 1412), a2) )
        {
          return 13;
        }
        else
        {
          v7 = 15;
          if ( PtInRect(v6, a2) )
            return 0;
        }
        break;
      case 9LL:
        return 8;
      default:
        switch ( v9 )
        {
          case 2LL:
            goto LABEL_34;
          case 8LL:
            v7 = 7;
            break;
          case 10LL:
          case 11LL:
          case 12LL:
          case 13LL:
          case 14LL:
            v7 = 0;
            if ( !PtInRect(v6, a2) )
              v7 = 15;
            break;
          case 20LL:
            return 11;
          case 23LL:
            return v7;
          case 24LL:
            v7 = 10;
            break;
          default:
            return 15;
        }
        break;
    }
  }
  else
  {
    return 15;
  }
  return v7;
}

```

## disassembly

```asm
0x1800295c0  push    rbx
0x1800295c2  push    rbp
0x1800295c3  push    rsi
0x1800295c4  push    rdi
0x1800295c5  push    r12
0x1800295c7  sub     rsp, 40h
0x1800295cb  mov     rax, cs:__security_cookie
0x1800295d2  xor     rax, rsp
0x1800295d5  mov     [rsp+68h+var_38], rax
0x1800295da  mov     rdi, rdx
0x1800295dd  mov     qword ptr [rsp+68h+rc.left], rdx
0x1800295e2  shr     rdi, 20h
0x1800295e6  mov     rbx, rdx
0x1800295e9  test    dword ptr [rcx+5B0h], 100h
0x1800295f3  mov     rsi, rcx
0x1800295f6  jnz     loc_180029793
0x1800295fc  xor     bpl, bpl
0x1800295ff  lea     r12, [rcx+354h]
0x180029606  mov     [rsp+68h+arg_18], r15
0x18002960e  mov     rcx, r12; lprc
0x180029611  call    cs:__imp_PtInRect
0x180029617  test    eax, eax
0x180029619  jnz     short loc_18002964B
0x18002961b  test    bpl, bpl
0x18002961e  jnz     short loc_180029647
0x180029620  mov     edi, 0Fh; jumptable 000000018002986F default case, cases 3-7,9,15-19,21,22
0x180029625  mov     r15, [rsp+68h+arg_18]; jumptable 000000018002986F case 23
0x18002962d  mov     eax, edi
0x18002962f  mov     rcx, [rsp+68h+var_38]
0x180029634  xor     rcx, rsp; StackCookie
0x180029637  call    __security_check_cookie
0x18002963c  add     rsp, 40h
0x180029640  pop     r12
0x180029642  pop     rdi
0x180029643  pop     rsi
0x180029644  pop     rbp
0x180029645  pop     rbx
0x180029646  retn
0x180029647  test    edi, edi
0x180029649  jnz     short def_18002986F; jumptable 000000018002986F default case, cases 3-7,9,15-19,21,22
0x18002964b  lea     rbp, [rsi+4E4h]
0x180029652  mov     [rsp+68h+arg_10], r14
0x18002965a  lea     rcx, [rbp+30h]; lprc
0x18002965e  mov     rdx, rbx; pt
0x180029661  call    cs:__imp_PtInRect
0x180029667  mov     edi, 9
0x18002966c  test    eax, eax
0x18002966e  jnz     short loc_1800296CF
0x180029670  lea     rcx, [rbp+70h]; lprc
0x180029674  mov     rdx, rbx; pt
0x180029677  call    cs:__imp_PtInRect
0x18002967d  test    eax, eax
0x18002967f  jnz     loc_180029776
0x180029685  lea     rcx, [rbp+40h]; lprc
0x180029689  mov     rdx, rbx; pt
0x18002968c  call    cs:__imp_PtInRect
0x180029692  test    eax, eax
0x180029694  jnz     loc_1800297A8
0x18002969a  lea     rcx, [rbp+50h]; lprc
0x18002969e  mov     rdx, rbx; pt
0x1800296a1  call    cs:__imp_PtInRect
0x1800296a7  test    eax, eax
0x1800296a9  jnz     loc_18002977E
0x1800296af  lea     rcx, [rbp+60h]; lprc
0x1800296b3  mov     rdx, rbx; pt
0x1800296b6  mov     r15d, 1
0x1800296bc  call    cs:__imp_PtInRect
0x1800296c2  test    eax, eax
0x1800296c4  mov     ecx, 14h
0x1800296c9  cmovnz  r15d, ecx
0x1800296cd  jmp     short loc_1800296D5
0x1800296cf  mov     r15d, 8
0x1800296d5  test    byte ptr [rsi+5ACh], 2
0x1800296dc  lea     r14, [rsi+1F8h]
0x1800296e3  jz      short loc_1800296F6
0x1800296e5  mov     rcx, [r14]; hWnd
0x1800296e8  call    cs:__imp_IsZoomed
0x1800296ee  test    eax, eax
0x1800296f0  jz      loc_18002987B
0x1800296f6  mov     rcx, [r14]; hWnd
0x1800296f9  call    cs:__imp_IsZoomed
0x1800296ff  mov     r14, [rsp+68h+arg_10]
0x180029707  test    eax, eax
0x180029709  jz      short loc_180029766
0x18002970b  lea     rcx, [rbp+60h]; lprc
0x18002970f  call    cs:__imp_IsRectEmpty
0x180029715  test    eax, eax
0x180029717  jnz     short loc_180029766
0x180029719  cmp     byte ptr [rsi+22Fh], 0
0x180029720  movups  xmm0, xmmword ptr [rsi+544h]
0x180029727  mov     eax, [rsi+358h]
0x18002972d  movups  xmmword ptr [rsp+68h+rc.left], xmm0
0x180029732  mov     [rsp+68h+rc.top], eax
0x180029736  jnz     short loc_180029789
0x180029738  cmp     byte ptr [rsi+230h], 0
0x18002973f  jnz     short loc_180029789
0x180029741  mov     eax, [r12+8]
0x180029746  mov     [rsp+68h+rc.right], eax
0x18002974a  mov     rdx, rbx; pt
0x18002974d  lea     rcx, [rsp+68h+rc]; lprc
0x180029752  call    cs:__imp_PtInRect
0x180029758  test    eax, eax
0x18002975a  jz      short loc_180029766
0x18002975c  mov     edi, 0Bh; jumptable 000000018002986F case 20
0x180029761  jmp     loc_180029625; jumptable 000000018002986F case 23
0x180029766  cmp     r15, 3
0x18002976a  jnz     short loc_1800297B3
0x18002976c  mov     edi, 4
0x180029771  jmp     loc_180029625; jumptable 000000018002986F case 23
0x180029776  mov     r15, rdi
0x180029779  jmp     loc_1800296D5
0x18002977e  mov     r15d, 18h
0x180029784  jmp     loc_1800296D5
0x180029789  mov     eax, [r12]
0x18002978d  mov     [rsp+68h+rc.left], eax
0x180029791  jmp     short loc_18002974A
0x180029793  cmp     dword ptr [rcx+228h], 1
0x18002979a  jnz     loc_1800295FC
0x1800297a0  mov     bpl, 1
0x1800297a3  jmp     loc_1800295FF
0x1800297a8  mov     r15d, 17h
0x1800297ae  jmp     loc_1800296D5
0x1800297b3  cmp     r15, 1
0x1800297b7  jnz     loc_1800298BD
0x1800297bd  mov     rdx, rbx; jumptable 000000018002986F case 2
0x1800297c0  mov     rcx, rbp; lprc
0x1800297c3  call    cs:__imp_PtInRect
0x1800297c9  test    eax, eax
0x1800297cb  jnz     short loc_18002976C
0x1800297cd  lea     rcx, [rbp+10h]; lprc
0x1800297d1  mov     rdx, rbx; pt
0x1800297d4  call    cs:__imp_PtInRect
0x1800297da  test    eax, eax
0x1800297dc  jnz     loc_1800298E1
0x1800297e2  lea     rcx, [rbp+20h]; lprc
0x1800297e6  mov     rdx, rbx; pt
0x1800297e9  call    cs:__imp_PtInRect
0x1800297ef  test    eax, eax
0x1800297f1  jnz     loc_1800298EB
0x1800297f7  lea     rcx, [rbp+80h]; lprc
0x1800297fe  mov     rdx, rbx; pt
0x180029801  call    cs:__imp_PtInRect
0x180029807  test    eax, eax
0x180029809  jnz     loc_1800298F5
0x18002980f  lea     rcx, [rbp+0A0h]; lprc
0x180029816  mov     rdx, rbx; pt
0x180029819  call    cs:__imp_PtInRect
0x18002981f  test    eax, eax
0x180029821  jnz     loc_1800298FF
0x180029827  mov     rdx, rbx; pt
0x18002982a  mov     rcx, r12; lprc
0x18002982d  mov     edi, 0Fh
0x180029832  call    cs:__imp_PtInRect
0x180029838  test    eax, eax
0x18002983a  jz      loc_180029625; jumptable 000000018002986F case 23
0x180029840  xor     edi, edi
0x180029842  jmp     loc_180029625; jumptable 000000018002986F case 23
0x180029847  add     r15, 0FFFFFFFFFFFFFFFEh; switch 23 cases
0x18002984b  cmp     r15, 16h
0x18002984f  ja      def_18002986F; jumptable 000000018002986F default case, cases 3-7,9,15-19,21,22
0x180029855  lea     rdx, __ImageBase
0x18002985c  movzx   eax, ds:(byte_180029944 - 180000000h)[rdx+r15]
0x180029865  mov     ecx, ds:(jpt_18002986F - 180000000h)[rdx+rax*4]
0x18002986c  add     rcx, rdx
0x18002986f  jmp     rcx; switch jump
0x180029871  mov     edi, 7; jumptable 000000018002986F case 8
0x180029876  jmp     loc_180029625; jumptable 000000018002986F case 23
0x18002987b  mov     ecx, [rsi+278h]
0x180029881  cmp     [rsp+68h+rc.top], ecx
0x180029885  mov     eax, [r12+8]
0x18002988a  setle   dl
0x18002988d  cmp     ebx, ecx
0x18002988f  setle   r8b
0x180029893  sub     eax, ecx
0x180029895  sub     eax, [r12]
0x180029899  cmp     ebx, eax
0x18002989b  setnl   al
0x18002989e  test    dl, dl
0x1800298a0  jz      loc_1800296F6
0x1800298a6  test    al, al
0x1800298a8  jnz     short loc_1800298CC
0x1800298aa  xor     r15d, r15d
0x1800298ad  test    r8b, r8b
0x1800298b0  setnz   r15b
0x1800298b4  add     r15, 0Ch
0x1800298b8  jmp     loc_1800296F6
0x1800298bd  cmp     r15, rdi
0x1800298c0  jnz     short loc_180029847
0x1800298c2  mov     edi, 8
0x1800298c7  jmp     loc_180029625; jumptable 000000018002986F case 23
0x1800298cc  mov     r15d, 0Eh
0x1800298d2  jmp     loc_1800296F6
0x1800298d7  mov     edi, 0Ah; jumptable 000000018002986F case 24
0x1800298dc  jmp     loc_180029625; jumptable 000000018002986F case 23
0x1800298e1  mov     edi, 5
0x1800298e6  jmp     loc_180029625; jumptable 000000018002986F case 23
0x1800298eb  mov     edi, 6
0x1800298f0  jmp     loc_180029625; jumptable 000000018002986F case 23
0x1800298f5  mov     edi, 0Ch
0x1800298fa  jmp     loc_180029625; jumptable 000000018002986F case 23
0x1800298ff  mov     edi, 0Dh
0x180029904  jmp     loc_180029625; jumptable 000000018002986F case 23
0x180029909  mov     rdx, rbx; jumptable 000000018002986F cases 10-14
0x18002990c  mov     rcx, r12; lprc
0x18002990f  call    cs:__imp_PtInRect
0x180029915  xor     edi, edi
0x180029917  mov     edx, 0Fh
0x18002991c  test    eax, eax
0x18002991e  cmovz   edi, edx
0x180029921  jmp     loc_180029625; jumptable 000000018002986F case 23
```
