# CContextMenuOnContextMenuArrayNoDuplicateVerbs::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x1800403f0`
- end: `0x18004063e`
- name: `?QueryContextMenu@CContextMenuOnContextMenuArrayNoDuplicateVerbs@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `590`
- prototype: `int(CContextMenuOnContextMenuArrayNoDuplicateVerbs *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18003f600`
- `0x180040178`
- `0x180040234`
- `0x180040260`
- `0x1800403f0`
- `0x18004a9e0`
- `0x18004aa00`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800405d9`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800405d9`
- `ext-ms-win-ntuser-menu-l1-1-0!RemoveMenu` at `0x1800405fc`
- `ext-ms-win-ntuser-menu-l1-1-0!RemoveMenu` at `0x1800405fc`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemCount` at `0x180040453`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemCount` at `0x180040453`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoW` at `0x180040497`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoW` at `0x180040497`

## pseudocode

```c
__int64 __fastcall CContextMenuOnContextMenuArrayNoDuplicateVerbs::QueryContextMenu(
        CContextMenuOnContextMenuArrayNoDuplicateVerbs *this,
        HMENU a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  HMENU v7; // rbx
  unsigned int v9; // r14d
  int v10; // r15d
  int MenuItemCount; // r13d
  signed int i; // esi
  unsigned int v13; // ebx
  __int64 j; // rax
  __int64 v15; // r14
  struct _DSA *v16; // rcx
  unsigned int k; // ebx
  int *v18; // rsi
  int v19; // esi
  __int64 v20; // r15
  _DWORD *v21; // r14
  int m; // r14d
  const WCHAR *v23; // rax
  int ContextMenu; // [rsp+30h] [rbp-D0h]
  const WCHAR *ItemPtr; // [rsp+40h] [rbp-C0h]
  struct tagMENUITEMINFOW mii; // [rsp+50h] [rbp-B0h] BYREF
  UINT pitem; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v30[86]; // [rsp+A4h] [rbp-5Ch] BYREF

  v7 = a2;
  ContextMenu = CContextMenuOnContextMenuArray::QueryContextMenu(this, a2, a3, a4, a5, a6);
  v9 = ContextMenu;
  if ( ContextMenu >= 0 )
  {
    v10 = 0;
    MenuItemCount = GetMenuItemCount(v7);
    for ( i = 0; i < MenuItemCount; ++i )
    {
      memset_0(&mii, 0, sizeof(mii));
      mii.cbSize = 80;
      mii.fMask = 18;
      if ( GetMenuItemInfoW(v7, i, 1024, &mii) && IsValidCommandItem(&mii, a4) && !IsDefViewPlaceholder(v7, i) )
      {
        v13 = mii.wID - a4;
        for ( j = 0; (unsigned int)j < *((_DWORD *)this + 14); j = (unsigned int)(j + 1) )
        {
          v15 = (unsigned int)j;
          if ( v13 <= *((_DWORD *)this + j + 16) )
          {
            if ( (_DWORD)j )
              v13 = v13 - *((_DWORD *)this + (unsigned int)(j - 1) + 16) - 1;
            memset_0(&pitem, 0, 0xA4u);
            if ( ContextMenu_GetCommandStringVerb(*((struct IContextMenu **)this + v15 + 11), v13, v30, 80) >= 0 )
            {
              v16 = (struct _DSA *)*((_QWORD *)this + v15 + 27);
              pitem = mii.wID;
              v10 = 0;
              if ( DSA_InsertItem(v16, 0x7FFFFFFF, &pitem) == -1 )
                v10 = -2147024882;
            }
            break;
          }
        }
        v7 = a2;
      }
      if ( v10 < 0 )
        return (unsigned int)ContextMenu;
    }
    for ( k = 1; k < *((_DWORD *)this + 14); ++k )
    {
      v18 = (int *)*((_QWORD *)this + k + 27);
      if ( v18 )
      {
        v19 = *v18;
        while ( --v19 >= 0 )
        {
          ItemPtr = (const WCHAR *)g_pfn_DSA_GetItemPtr(*((HDSA *)this + k + 27), v19);
          v20 = 0;
LABEL_23:
          if ( (unsigned int)v20 < k )
          {
            v21 = (_DWORD *)*((_QWORD *)this + v20 + 27);
            if ( v21 )
              LODWORD(v21) = *v21;
            for ( m = (_DWORD)v21 - 1; ; --m )
            {
              if ( m < 0 )
              {
                v20 = (unsigned int)(v20 + 1);
                goto LABEL_23;
              }
              v23 = (const WCHAR *)g_pfn_DSA_GetItemPtr(*((HDSA *)this + v20 + 27), m);
              if ( !StrCmpICW(ItemPtr + 2, v23 + 2) )
                break;
            }
            RemoveMenu(a2, *(_DWORD *)ItemPtr, 0);
          }
        }
      }
    }
    return (unsigned int)ContextMenu;
  }
  return v9;
}

```

## disassembly

```asm
0x1800403f0  push    rbp
0x1800403f2  push    rbx
0x1800403f3  push    rsi
0x1800403f4  push    rdi
0x1800403f5  push    r12
0x1800403f7  push    r13
0x1800403f9  push    r14
0x1800403fb  push    r15
0x1800403fd  lea     rbp, [rsp-68h]
0x180040402  sub     rsp, 168h
0x180040409  mov     rax, cs:__security_cookie
0x180040410  xor     rax, rsp
0x180040413  mov     [rbp+0A0h+var_50], rax
0x180040417  mov     eax, [rbp+0A0h+arg_28]
0x18004041d  mov     r12d, r9d
0x180040420  mov     [rsp+1A0h+var_178], eax; unsigned int
0x180040424  mov     rbx, rdx
0x180040427  mov     eax, [rbp+0A0h+arg_20]
0x18004042d  mov     rdi, rcx
0x180040430  mov     [rsp+1A0h+var_180], eax; unsigned int
0x180040434  mov     [rsp+1A0h+hMenu], rdx
0x180040439  call    ?QueryContextMenu@CContextMenuOnContextMenuArray@@UEAAJPEAUHMENU__@@IIII@Z; CContextMenuOnContextMenuArray::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)
0x18004043e  mov     [rsp+1A0h+var_170], eax
0x180040442  mov     r14d, eax
0x180040445  test    eax, eax
0x180040447  js      loc_18004061B
0x18004044d  mov     rcx, rbx; hMenu
0x180040450  xor     r15d, r15d
0x180040453  call    cs:__imp_GetMenuItemCount
0x180040459  mov     r13d, eax
0x18004045c  xor     esi, esi
0x18004045e  cmp     esi, r13d
0x180040461  jge     loc_180040560
0x180040467  xor     edx, edx; Val
0x180040469  lea     rcx, [rsp+1A0h+mii]; void *
0x18004046e  lea     r8d, [rdx+50h]; Size
0x180040472  call    memset_0
0x180040477  lea     r9, [rsp+1A0h+mii]; lpmii
0x18004047c  mov     [rsp+1A0h+mii.cbSize], 50h ; 'P'
0x180040484  mov     r8d, 400h; fByPosition
0x18004048a  mov     [rsp+1A0h+mii.fMask], 12h
0x180040492  mov     edx, esi; item
0x180040494  mov     rcx, rbx; hmenu
0x180040497  call    cs:__imp_GetMenuItemInfoW
0x18004049d  test    eax, eax
0x18004049f  jz      loc_180040550
0x1800404a5  mov     edx, r12d; unsigned int
0x1800404a8  lea     rcx, [rsp+1A0h+mii]; struct tagMENUITEMINFOW *
0x1800404ad  call    ?IsValidCommandItem@@YA_NAEBUtagMENUITEMINFOW@@I@Z; IsValidCommandItem(tagMENUITEMINFOW const &,uint)
0x1800404b2  test    al, al
0x1800404b4  jz      loc_180040550
0x1800404ba  mov     edx, esi; item
0x1800404bc  mov     rcx, rbx; hmenu
0x1800404bf  call    ?IsDefViewPlaceholder@@YA_NPEAUHMENU__@@H@Z; IsDefViewPlaceholder(HMENU__ *,int)
0x1800404c4  test    al, al
0x1800404c6  jnz     loc_180040550
0x1800404cc  mov     ebx, [rsp+1A0h+mii.wID]
0x1800404d0  sub     ebx, r12d
0x1800404d3  xor     eax, eax
0x1800404d5  cmp     eax, [rdi+38h]
0x1800404d8  jnb     short loc_18004054B
0x1800404da  mov     r14d, eax
0x1800404dd  cmp     ebx, [rdi+rax*4+40h]
0x1800404e1  jbe     short loc_1800404E7
0x1800404e3  inc     eax
0x1800404e5  jmp     short loc_1800404D5
0x1800404e7  test    eax, eax
0x1800404e9  jz      short loc_1800404F3
0x1800404eb  dec     eax
0x1800404ed  sub     ebx, [rdi+rax*4+40h]
0x1800404f1  dec     ebx
0x1800404f3  xor     edx, edx; Val
0x1800404f5  lea     rcx, [rbp+0A0h+pitem]; void *
0x1800404f9  mov     r8d, 0A4h; Size
0x1800404ff  call    memset_0
0x180040504  mov     rcx, [rdi+r14*8+58h]; struct IContextMenu *
0x180040509  lea     r8, [rbp+0A0h+var_FC]; unsigned __int16 *
0x18004050d  mov     r9d, 50h ; 'P'; int
0x180040513  mov     edx, ebx; unsigned int
0x180040515  call    ?ContextMenu_GetCommandStringVerb@@YAJPEAUIContextMenu@@IPEAGH@Z; ContextMenu_GetCommandStringVerb(IContextMenu *,uint,ushort *,int)
0x18004051a  test    eax, eax
0x18004051c  js      short loc_18004054B
0x18004051e  mov     eax, [rsp+1A0h+mii.wID]
0x180040522  lea     r8, [rbp+0A0h+pitem]; pitem
0x180040526  mov     rcx, [rdi+r14*8+0D8h]; hdsa
0x18004052e  mov     edx, 7FFFFFFFh; i
0x180040533  mov     [rbp+0A0h+pitem], eax
0x180040536  call    cs:__imp_DSA_InsertItem
0x18004053c  xor     r15d, r15d
0x18004053f  mov     ecx, 8007000Eh
0x180040544  cmp     eax, 0FFFFFFFFh
0x180040547  cmovz   r15d, ecx
0x18004054b  mov     rbx, [rsp+1A0h+hMenu]
0x180040550  inc     esi
0x180040552  test    r15d, r15d
0x180040555  jns     loc_18004045E
0x18004055b  jmp     loc_180040616
0x180040560  mov     ebx, 1
0x180040565  cmp     [rdi+38h], ebx
0x180040568  jbe     loc_180040616
0x18004056e  mov     r12d, ebx
0x180040571  mov     rsi, [rdi+r12*8+0D8h]
0x180040579  test    rsi, rsi
0x18004057c  jz      loc_18004060B
0x180040582  mov     esi, [rsi]
0x180040584  jmp     short loc_180040602
0x180040586  mov     rcx, [rdi+r12*8+0D8h]; hdsa
0x18004058e  mov     edx, esi; i
0x180040590  call    cs:g_pfn_DSA_GetItemPtr
0x180040596  mov     [rsp+1A0h+var_160], rax
0x18004059b  xor     r15d, r15d
0x18004059e  cmp     r15d, ebx
0x1800405a1  jnb     short loc_180040602
0x1800405a3  mov     r14, [rdi+r15*8+0D8h]
0x1800405ab  test    r14, r14
0x1800405ae  jz      short loc_1800405B3
0x1800405b0  mov     r14d, [r14]
0x1800405b3  dec     r14d
0x1800405b6  test    r14d, r14d
0x1800405b9  js      short loc_1800405E8
0x1800405bb  mov     rcx, [rdi+r15*8+0D8h]; hdsa
0x1800405c3  mov     edx, r14d; i
0x1800405c6  call    cs:g_pfn_DSA_GetItemPtr
0x1800405cc  mov     rcx, [rsp+1A0h+var_160]
0x1800405d1  add     rcx, 4; pszStr1
0x1800405d5  lea     rdx, [rax+4]; pszStr2
0x1800405d9  call    cs:__imp_StrCmpICW
0x1800405df  test    eax, eax
0x1800405e1  jz      short loc_1800405ED
0x1800405e3  dec     r14d
0x1800405e6  jmp     short loc_1800405B6
0x1800405e8  inc     r15d
0x1800405eb  jmp     short loc_18004059E
0x1800405ed  mov     rax, [rsp+1A0h+var_160]
0x1800405f2  xor     r8d, r8d; uFlags
0x1800405f5  mov     rcx, [rsp+1A0h+hMenu]; hMenu
0x1800405fa  mov     edx, [rax]; uPosition
0x1800405fc  call    cs:__imp_RemoveMenu
0x180040602  sub     esi, 1
0x180040605  jns     loc_180040586
0x18004060b  inc     ebx
0x18004060d  cmp     ebx, [rdi+38h]
0x180040610  jb      loc_18004056E
0x180040616  mov     r14d, [rsp+1A0h+var_170]
0x18004061b  mov     eax, r14d
0x18004061e  mov     rcx, [rbp+0A0h+var_50]
0x180040622  xor     rcx, rsp; StackCookie
0x180040625  call    __security_check_cookie
0x18004062a  add     rsp, 168h
0x180040631  pop     r15
0x180040633  pop     r14
0x180040635  pop     r13
0x180040637  pop     r12
0x180040639  pop     rdi
0x18004063a  pop     rsi
0x18004063b  pop     rbx
0x18004063c  pop     rbp
0x18004063d  retn
```
