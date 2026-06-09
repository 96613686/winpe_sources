# _FDoWmCommand(int,HWND__ *,uint)

- ea: `0x1800b7c40`
- end: `0x1800b82df`
- name: `?_FDoWmCommand@@YAHHPEAUHWND__@@I@Z`
- size: `1695`
- prototype: `__int64 __fastcall(int, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b3f14`

## callees

- `0x180021a90`
- `0x18005acac`
- `0x1800b33e4`
- `0x1800b35dc`
- `0x1800b5b54`
- `0x1800b6654`
- `0x1800b66d8`
- `0x1800b7c40`
- `0x1800b88a0`
- `0x1800b9374`
- `0x1800b961c`
- `0x1800b9968`
- `0x1800b9e48`
- `0x1800ba038`
- `0x1800ba754`
- `0x1800bacd0`
- `0x1800baf90`
- `0x1800bc9b8`
- `0x1800bdff4`
- `0x1800db75c`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x1800b7f6e`
- `MSVCR100!free` at `0x1800b7f6e`
- `USER32!IsWindowVisible` at `0x1800b7ccf`
- `USER32!IsWindowVisible` at `0x1800b7ccf`
- `USER32!SetFocus` at `0x1800b812d`
- `USER32!SetFocus` at `0x1800b812d`
- `USER32!GetFocus` at `0x1800b7dd9`
- `USER32!GetFocus` at `0x1800b7dd9`
- `USER32!SendMessageA` at `0x1800b7d16`
- `USER32!SendMessageA` at `0x1800b7db6`
- `USER32!SendMessageA` at `0x1800b7eb0`
- `USER32!SendMessageA` at `0x1800b7ee1`
- `USER32!SendMessageA` at `0x1800b7f15`
- `USER32!SendMessageA` at `0x1800b7fb5`
- `USER32!SendMessageA` at `0x1800b7fe1`
- `USER32!SendMessageA` at `0x1800b80c6`
- `USER32!SendMessageA` at `0x1800b80ed`
- `USER32!SendMessageA` at `0x1800b81b7`
- `USER32!SendMessageA` at `0x1800b81dd`
- `USER32!SendMessageA` at `0x1800b81fa`
- `USER32!SendMessageA` at `0x1800b8261`
- `USER32!SendMessageA` at `0x1800b7d16`
- `USER32!SendMessageA` at `0x1800b7db6`
- `USER32!SendMessageA` at `0x1800b7eb0`
- `USER32!SendMessageA` at `0x1800b7ee1`
- `USER32!SendMessageA` at `0x1800b7f15`
- `USER32!SendMessageA` at `0x1800b7fb5`
- `USER32!SendMessageA` at `0x1800b7fe1`
- `USER32!SendMessageA` at `0x1800b80c6`
- `USER32!SendMessageA` at `0x1800b80ed`
- `USER32!SendMessageA` at `0x1800b81b7`
- `USER32!SendMessageA` at `0x1800b81dd`
- `USER32!SendMessageA` at `0x1800b81fa`
- `USER32!SendMessageA` at `0x1800b8261`
- `OLEAUT32!__imp_VariantClear` at `0x1800b7f5f`
- `OLEAUT32!__imp_VariantClear` at `0x1800b7f5f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800b7d44`
- `OLEAUT32!__imp_VariantCopy` at `0x1800b7d44`

## pseudocode

```c
__int64 __fastcall _FDoWmCommand(int a1, HWND a2, int a3)
{
  int v5; // ecx
  int v6; // ecx
  int v7; // eax
  LRESULT v8; // rax
  __int64 v9; // rdi
  const char *v10; // rcx
  int v11; // edi
  HWND Focus; // rax
  HWND v13; // rcx
  __int64 result; // rax
  LRESULT v15; // rax
  __int64 v16; // rdi
  LRESULT v17; // rax
  __int64 v18; // rsi
  unsigned int v19; // ebp
  void *v20; // rcx
  int v21; // edi
  HWND v22; // rdx
  int v23; // eax
  int v24; // edi
  int v25; // edi
  int v26; // ebx
  unsigned int v27; // eax
  struct IUnknown *v28; // rdx
  BOOL v29; // edx
  struct CTL *v30; // rax
  unsigned __int8 v31; // cl
  struct CTL *v32; // rdx
  __int64 v33[7]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v34; // [rsp+80h] [rbp+8h] BYREF
  struct IPerPropertyBrowsing *v35; // [rsp+98h] [rbp+20h] BYREF

  v5 = a1 - 4096;
  if ( !v5 )
  {
    if ( a3 != 1 )
    {
      if ( a3 != 3 )
      {
        switch ( a3 )
        {
          case 4:
            Pbar_fNoAccel = 0;
            return 1;
          case 7:
            _SizeComboList();
            return 1;
          case 8:
            SetFocus(hWndTo);
            break;
        }
        goto LABEL_78;
      }
      goto LABEL_87;
    }
    if ( Pbrs_it == 3 || Pbrs_it == 2 || Pbrs_it == 5 )
      return 0;
    v26 = SendMessageA(a2, 0x147u, 0, 0);
    if ( v26 == -1 )
    {
      v26 = cDropDownPeek;
      SendMessageA(a2, 0x14Eu, cDropDownPeek, 0);
    }
    if ( Pbrs_it == 4 )
    {
      v27 = SendMessageA(a2, 0x150u, v26, 0);
      if ( qword_1803F33F8 )
        v28 = *(struct IUnknown **)(qword_1803F33F8 + 8LL * v27);
      else
        v28 = 0;
      if ( v28 )
      {
        v29 = ProjitemSel::Select((ProjitemSel *)Pbrs_projitemsel, v28) == 0;
        _PbrsUpdate(0, v29);
      }
      return 1;
    }
    if ( (dword_1803FB04C & 0x200) != 0 )
      return 0;
    v30 = (struct CTL *)SendMessageA(a2, 0x150u, v26, 0);
    hctlPbrsMenu = 0;
    v31 = *(_BYTE *)(**((_QWORD **)v30 + 6) + 95LL);
    if ( v31 != 10 && v31 != 17 )
    {
      if ( v31 == 18 )
      {
        hctlPbrsMenu = v30;
      }
      else if ( v31 <= 0x1Cu || v31 > 0x1Fu )
      {
        v32 = v30;
LABEL_108:
        EdFSetAim(Pbrs_hctlForm, v32, 0);
        _Update(1, Pbrs_hctlForm, Pbrs_it);
        return 1;
      }
    }
    v32 = 0;
    goto LABEL_108;
  }
  v6 = v5 - 2;
  if ( v6 )
  {
    if ( v6 != 2 )
    {
LABEL_78:
      if ( a2 == hWndChild )
      {
        v25 = a3 - 1;
        if ( !v25 )
        {
          dword_1803FB04C |= 4u;
          _SelToEdit();
          return 1;
        }
        if ( v25 == 1 )
        {
          if ( !Pbrs_lpdispatch )
            return 1;
          goto LABEL_70;
        }
      }
      return 0;
    }
    if ( a3 != 256 )
    {
      if ( a3 == 512 )
      {
        if ( Pbar_fNoAccel )
        {
          Pbar_fNoAccel = 0;
          Focus = GetFocus();
          v13 = hWndChild;
          if ( dword_1803FB048 == 1 )
            v13 = qword_1803FB020;
          if ( Focus != v13 )
            PbrsCommit();
        }
      }
      else if ( a3 == 768
             && Pbrs_lpdispatch
             && (dword_1803FB04C & 2) == 0
             && dword_1803FB048 != 7
             && IsWindowVisible(qword_1803F3330) )
      {
        v7 = dword_1803FB04C | 4;
        dword_1803FB04C = v7;
        if ( (v7 & 8) != 0 )
        {
          if ( (v7 & 1) != 0 )
            goto LABEL_21;
          v8 = SendMessageA(hWndTo, 0x199u, pbrs_index, 0);
          v9 = -1;
          if ( v8 != -1 )
            v9 = (__int64)lprgpi + 80 * v8;
          if ( *(_WORD *)(v9 + 40) == 8 )
          {
            pvargDest.vt = 8;
            v10 = Rby_szNull;
            if ( *(_QWORD *)(v9 + 8) )
              v10 = *(const char **)(v9 + 8);
            pvargDest.llVal = (LONGLONG)AllocBstrWfromA(v10);
          }
          else
          {
            VariantCopy(&pvargDest, (const VARIANTARG *)(v9 + 40));
          }
          v7 = dword_1803FB04C | 1;
          dword_1803FB04C = v7;
          if ( (v7 & 1) != 0 )
          {
LABEL_21:
            v11 = Pbrs_fMultiSelect;
            Pbrs_fMultiSelect = 0;
            dword_1803FB04C = v7 | 1;
            if ( (unsigned int)_FlushPartTwo() )
              SendMessageA(qword_1803F3330, 0xB9u, 0, 0);
            Pbrs_fMultiSelect = v11;
          }
        }
        return 1;
      }
      goto LABEL_78;
    }
LABEL_87:
    Pbar_fNoAccel = 1;
    return 1;
  }
  if ( a3 == 1 )
  {
    _PickProp();
    return 1;
  }
  if ( a3 == 2 )
  {
    switch ( dword_1803FB048 )
    {
      case 3:
      case 5:
      case 4:
      case 2:
        v21 = SendMessageA(hWndChild, 0x188u, 0, 0);
        if ( v21 < 0 )
        {
          if ( Pbrs_iprop == -1 )
          {
            if ( (dword_1803FB04C & 0x800) != 0 && dword_1803FB048 == 5 )
            {
              GetPerPropertyBrowsing(Pbrs_lpdispatch, Pbrs_it, &v35);
              if ( v35 )
              {
                if ( (unsigned int)_FillOCXList(v35) )
                  dword_1803FB04C &= ~0x800u;
                ((void (__fastcall *)(struct IPerPropertyBrowsing *))v35->lpVtbl->Release)(v35);
              }
            }
          }
          else
          {
            v33[0] = (__int64)hWndChild;
            v33[1] = (__int64)qword_1803F3330;
            v22 = (HWND)*((_QWORD *)Pbrs_hctl + 11);
            v34 = 0;
            CommonGizWndProc(Pbrs_hctl, v22, 0x1040u, Pbrs_iprop, (__int64)v33, &v34);
          }
          v21 = _SetListBoxIndexFromText();
        }
        v23 = SendMessageA(hWndChild, 0x18Bu, 0, 0);
        if ( v23 <= 0 )
          return 1;
        v24 = v21 + 1;
        if ( v24 >= v23 )
          v24 = 0;
        SendMessageA(hWndChild, 0x186u, v24, 0);
        dword_1803FB04C |= 4u;
        _SelToEdit();
LABEL_70:
        PbrsCommit();
        return 1;
      case 1:
        _ShowSel();
        if ( dword_1803FB040 != 48 )
LABEL_55:
          PbrsStartEdit(0x1069u, 0, 0);
        break;
      case 6:
        _ShowSel();
        break;
      case 7:
        v15 = SendMessageA(hWndTo, 0x199u, pbrs_index, 0);
        v16 = -1;
        if ( v15 != -1 )
          v16 = (__int64)lprgpi + 80 * v15;
        _AddRemoveOutlineEntries((struct tagPropItem *)v16, pbrs_index);
        return 1;
      default:
        v17 = SendMessageA(hWndTo, 0x199u, pbrs_index, 0);
        if ( v17 == -1 )
          v18 = -1;
        else
          v18 = (__int64)lprgpi + 80 * v17;
        if ( !SendMessageA(qword_1803F3330, 0xEu, 0, 0) )
        {
          v19 = pbrs_index;
          _GetPropValue(
            Pbrs_lpdispatch,
            (struct tagPROPERTY_FLAGS *)(v18 + 28),
            *(_DWORD *)(v18 + 64),
            *(_DWORD *)(v18 + 16),
            0,
            0,
            (char **)&v35);
          VariantClear(&pvarg);
          v20 = *(void **)(v18 + 8);
          if ( v20 )
            free(v20);
          *(_QWORD *)(v18 + 8) = v35;
          pbrs_index = -1;
          _UpdateEdit(Pbrs_lpdispatch, Pbrs_it, v19);
          dword_1803FB04C |= 4u;
          SendMessageA(qword_1803F3330, 0xB9u, 1u, 0);
        }
        goto LABEL_55;
    }
    return 1;
  }
  result = 1;
  if ( a3 == 4 )
  {
    Pbar_fNoAccel = 1;
  }
  else if ( a3 == 5 )
  {
    Pbar_fNoAccel = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800b7c40  mov     [rsp+arg_8], rbx
0x1800b7c45  push    rbp
0x1800b7c46  push    rsi
0x1800b7c47  push    rdi
0x1800b7c48  mov     eax, 60h
0x1800b7c4d  call    _alloca_probe
0x1800b7c52  sub     rsp, rax
0x1800b7c55  xor     ebx, ebx
0x1800b7c57  mov     edi, r8d
0x1800b7c5a  mov     rsi, rdx
0x1800b7c5d  sub     ecx, 1000h
0x1800b7c63  jz      loc_1800B810D
0x1800b7c69  sub     ecx, 2
0x1800b7c6c  jz      loc_1800B7E08
0x1800b7c72  cmp     ecx, 2
0x1800b7c75  jnz     loc_1800B8133
0x1800b7c7b  cmp     r8d, 100h
0x1800b7c82  jz      loc_1800B817C
0x1800b7c88  cmp     r8d, 200h
0x1800b7c8f  jz      loc_1800B7DC7
0x1800b7c95  cmp     r8d, 300h
0x1800b7c9c  jnz     loc_1800B8133
0x1800b7ca2  cmp     cs:?Pbrs_lpdispatch@@3PEAUIDispatch@@EA, rbx; IDispatch * Pbrs_lpdispatch
0x1800b7ca9  jz      loc_1800B8133
0x1800b7caf  test    byte ptr cs:dword_1803FB04C, cl
0x1800b7cb5  jnz     loc_1800B8133
0x1800b7cbb  cmp     cs:dword_1803FB048, 7
0x1800b7cc2  jz      loc_1800B8133
0x1800b7cc8  mov     rcx, cs:qword_1803F3330; hWnd
0x1800b7ccf  call    cs:__imp_IsWindowVisible
0x1800b7cd5  test    eax, eax
0x1800b7cd7  jz      loc_1800B8133
0x1800b7cdd  mov     eax, cs:dword_1803FB04C
0x1800b7ce3  lea     esi, [rbx+8]
0x1800b7ce6  or      eax, 4
0x1800b7ce9  mov     cs:dword_1803FB04C, eax
0x1800b7cef  test    sil, al
0x1800b7cf2  jz      loc_1800B816A
0x1800b7cf8  test    al, 1
0x1800b7cfa  jnz     loc_1800B7D86
0x1800b7d00  movsxd  r8, cs:?pbrs_index@@3HA; wParam
0x1800b7d07  mov     rcx, cs:hWndTo; hWnd
0x1800b7d0e  xor     r9d, r9d; lParam
0x1800b7d11  mov     edx, 199h; Msg
0x1800b7d16  call    cs:__imp_SendMessageA
0x1800b7d1c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b7d20  cmp     rax, rdi
0x1800b7d23  jz      short loc_1800B7D34
0x1800b7d25  lea     rdi, [rax+rax*4]
0x1800b7d29  shl     rdi, 4
0x1800b7d2d  add     rdi, cs:?lprgpi@@3PEAUtagPropItem@@EA; tagPropItem * lprgpi
0x1800b7d34  lea     rdx, [rdi+28h]; pvargSrc
0x1800b7d38  cmp     [rdx], si
0x1800b7d3b  jz      short loc_1800B7D4C
0x1800b7d3d  lea     rcx, pvargDest; pvargDest
0x1800b7d44  call    cs:__imp_VariantCopy
0x1800b7d4a  jmp     short loc_1800B7D6F
0x1800b7d4c  mov     word ptr cs:pvargDest, si
0x1800b7d53  cmp     [rdi+8], rbx
0x1800b7d57  lea     rcx, ?Rby_szNull@@3PADA; char near * Rby_szNull
0x1800b7d5e  cmovnz  rcx, [rdi+8]; char *
0x1800b7d63  call    ?AllocBstrWfromA@@YAPEA_WPEBD@Z; AllocBstrWfromA(char const *)
0x1800b7d68  mov     qword ptr cs:pvargDest+8, rax
0x1800b7d6f  mov     eax, cs:dword_1803FB04C
0x1800b7d75  or      eax, 1
0x1800b7d78  mov     cs:dword_1803FB04C, eax
0x1800b7d7e  test    al, 1
0x1800b7d80  jz      loc_1800B816A
0x1800b7d86  mov     edi, cs:?Pbrs_fMultiSelect@@3HA; int Pbrs_fMultiSelect
0x1800b7d8c  or      eax, 1
0x1800b7d8f  mov     cs:?Pbrs_fMultiSelect@@3HA, ebx; int Pbrs_fMultiSelect
0x1800b7d95  mov     cs:dword_1803FB04C, eax
0x1800b7d9b  call    ?_FlushPartTwo@@YAHXZ; _FlushPartTwo(void)
0x1800b7da0  test    eax, eax
0x1800b7da2  jz      short loc_1800B7DBC
0x1800b7da4  mov     rcx, cs:qword_1803F3330; hWnd
0x1800b7dab  xor     r9d, r9d; lParam
0x1800b7dae  xor     r8d, r8d; wParam
0x1800b7db1  mov     edx, 0B9h; Msg
0x1800b7db6  call    cs:__imp_SendMessageA
0x1800b7dbc  mov     cs:?Pbrs_fMultiSelect@@3HA, edi; int Pbrs_fMultiSelect
0x1800b7dc2  jmp     loc_1800B816A
0x1800b7dc7  cmp     cs:?Pbar_fNoAccel@@3HA, ebx; int Pbar_fNoAccel
0x1800b7dcd  jz      loc_1800B8133
0x1800b7dd3  mov     cs:?Pbar_fNoAccel@@3HA, ebx; int Pbar_fNoAccel
0x1800b7dd9  call    cs:__imp_GetFocus
0x1800b7ddf  cmp     cs:dword_1803FB048, 1
0x1800b7de6  mov     rcx, cs:hWndChild
0x1800b7ded  cmovz   rcx, cs:qword_1803FB020
0x1800b7df5  cmp     rax, rcx
0x1800b7df8  jz      loc_1800B8133
0x1800b7dfe  call    ?PbrsCommit@@YAXXZ; PbrsCommit(void)
0x1800b7e03  jmp     loc_1800B8133
0x1800b7e08  dec     edi
0x1800b7e0a  jz      loc_1800B8106
0x1800b7e10  dec     edi
0x1800b7e12  jz      short loc_1800B7E40
0x1800b7e14  mov     eax, 1
0x1800b7e19  sub     edi, 2
0x1800b7e1c  jz      short loc_1800B7E31
0x1800b7e1e  dec     edi
0x1800b7e20  jnz     loc_1800B82CF
0x1800b7e26  mov     cs:?Pbar_fNoAccel@@3HA, ebx; int Pbar_fNoAccel
0x1800b7e2c  jmp     loc_1800B82CF
0x1800b7e31  mov     cs:?Pbar_fNoAccel@@3HA, 1; int Pbar_fNoAccel
0x1800b7e3b  jmp     loc_1800B82CF
0x1800b7e40  mov     eax, cs:dword_1803FB048
0x1800b7e46  cmp     eax, 3
0x1800b7e49  jz      loc_1800B7FCF
0x1800b7e4f  cmp     eax, 5
0x1800b7e52  jz      loc_1800B7FCF
0x1800b7e58  cmp     eax, 4
0x1800b7e5b  jz      loc_1800B7FCF
0x1800b7e61  cmp     eax, 2
0x1800b7e64  jz      loc_1800B7FCF
0x1800b7e6a  cmp     eax, 1
0x1800b7e6d  jnz     short loc_1800B7E86
0x1800b7e6f  call    ?_ShowSel@@YAJXZ; _ShowSel(void)
0x1800b7e74  cmp     cs:dword_1803FB040, 30h ; '0'
0x1800b7e7b  jz      loc_1800B816A
0x1800b7e81  jmp     loc_1800B7FBB
0x1800b7e86  cmp     eax, 6
0x1800b7e89  jnz     short loc_1800B7E95
0x1800b7e8b  call    ?_ShowSel@@YAJXZ; _ShowSel(void)
0x1800b7e90  jmp     loc_1800B816A
0x1800b7e95  movsxd  r8, cs:?pbrs_index@@3HA; wParam
0x1800b7e9c  mov     rcx, cs:hWndTo; hWnd
0x1800b7ea3  xor     r9d, r9d; lParam
0x1800b7ea6  mov     edx, 199h; Msg
0x1800b7eab  cmp     eax, 7
0x1800b7eae  jnz     short loc_1800B7EE1
0x1800b7eb0  call    cs:__imp_SendMessageA
0x1800b7eb6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b7eba  cmp     rax, rdi
0x1800b7ebd  jz      short loc_1800B7ECE
0x1800b7ebf  lea     rdi, [rax+rax*4]
0x1800b7ec3  shl     rdi, 4
0x1800b7ec7  add     rdi, cs:?lprgpi@@3PEAUtagPropItem@@EA; tagPropItem * lprgpi
0x1800b7ece  mov     edx, cs:?pbrs_index@@3HA; int
0x1800b7ed4  mov     rcx, rdi; struct tagPropItem *
0x1800b7ed7  call    ?_AddRemoveOutlineEntries@@YAXPEAUtagPropItem@@H@Z; _AddRemoveOutlineEntries(tagPropItem *,int)
0x1800b7edc  jmp     loc_1800B816A
0x1800b7ee1  call    cs:__imp_SendMessageA
0x1800b7ee7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b7eeb  cmp     rax, rdi
0x1800b7eee  jnz     short loc_1800B7EF5
0x1800b7ef0  mov     rsi, rdi
0x1800b7ef3  jmp     short loc_1800B7F04
0x1800b7ef5  lea     rsi, [rax+rax*4]
0x1800b7ef9  shl     rsi, 4
0x1800b7efd  add     rsi, cs:?lprgpi@@3PEAUtagPropItem@@EA; tagPropItem * lprgpi
0x1800b7f04  mov     rcx, cs:qword_1803F3330; hWnd
0x1800b7f0b  xor     r9d, r9d; lParam
0x1800b7f0e  xor     r8d, r8d; wParam
0x1800b7f11  lea     edx, [r9+0Eh]; Msg
0x1800b7f15  call    cs:__imp_SendMessageA
0x1800b7f1b  test    rax, rax
0x1800b7f1e  jnz     loc_1800B7FBB
0x1800b7f24  mov     r9d, [rsi+10h]; int
0x1800b7f28  mov     r8d, [rsi+40h]; int
0x1800b7f2c  mov     rcx, cs:?Pbrs_lpdispatch@@3PEAUIDispatch@@EA; struct IDispatch *
0x1800b7f33  mov     ebp, cs:?pbrs_index@@3HA; int pbrs_index
0x1800b7f39  lea     rax, [rsp+78h+arg_18]
0x1800b7f41  lea     rdx, [rsi+1Ch]; struct tagPROPERTY_FLAGS *
0x1800b7f45  mov     [rsp+78h+var_48], rax; char **
0x1800b7f4a  mov     [rsp+78h+var_50], rbx; struct ITypeInfo *
0x1800b7f4f  mov     [rsp+78h+var_58], ebx; unsigned int
0x1800b7f53  call    ?_GetPropValue@@YAJPEAUIDispatch@@PEAUtagPROPERTY_FLAGS@@HJKPEAUITypeInfo@@PEAPEAD@Z; _GetPropValue(IDispatch *,tagPROPERTY_FLAGS *,int,long,ulong,ITypeInfo *,char * *)
0x1800b7f58  lea     rcx, pvarg; pvarg
0x1800b7f5f  call    cs:__imp_VariantClear
0x1800b7f65  mov     rcx, [rsi+8]; Block
0x1800b7f69  test    rcx, rcx
0x1800b7f6c  jz      short loc_1800B7F74
0x1800b7f6e  call    cs:__imp_free
0x1800b7f74  mov     rax, [rsp+78h+arg_18]
0x1800b7f7c  mov     r8d, ebp
0x1800b7f7f  mov     [rsi+8], rax
0x1800b7f83  mov     edx, cs:?Pbrs_it@@3W4IT@@A; IT Pbrs_it
0x1800b7f89  mov     rcx, cs:?Pbrs_lpdispatch@@3PEAUIDispatch@@EA; IDispatch * Pbrs_lpdispatch
0x1800b7f90  mov     cs:?pbrs_index@@3HA, edi; int pbrs_index
0x1800b7f96  call    ?_UpdateEdit@@YAXPEAUIDispatch@@W4IT@@H@Z; _UpdateEdit(IDispatch *,IT,int)
0x1800b7f9b  mov     rcx, cs:qword_1803F3330; hWnd
0x1800b7fa2  or      cs:dword_1803FB04C, 4
0x1800b7fa9  xor     r9d, r9d; lParam
0x1800b7fac  mov     edx, 0B9h; Msg
0x1800b7fb1  lea     r8d, [r9+1]; wParam
0x1800b7fb5  call    cs:__imp_SendMessageA
0x1800b7fbb  xor     r8d, r8d; __int64
0x1800b7fbe  xor     edx, edx; unsigned __int64
0x1800b7fc0  mov     ecx, 1069h; unsigned int
0x1800b7fc5  call    ?PbrsStartEdit@@YAXI_K_J@Z; PbrsStartEdit(uint,unsigned __int64,__int64)
0x1800b7fca  jmp     loc_1800B816A
0x1800b7fcf  mov     rcx, cs:hWndChild; hWnd
0x1800b7fd6  xor     r9d, r9d; lParam
0x1800b7fd9  xor     r8d, r8d; wParam
0x1800b7fdc  mov     edx, 188h; Msg
0x1800b7fe1  call    cs:__imp_SendMessageA
0x1800b7fe7  mov     rdi, rax
0x1800b7fea  test    eax, eax
0x1800b7fec  jns     loc_1800B80B4
0x1800b7ff2  movsxd  rcx, cs:?Pbrs_iprop@@3HA; int Pbrs_iprop
0x1800b7ff9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b7ffd  cmp     ecx, edi
0x1800b7fff  jz      short loc_1800B8052
0x1800b8001  mov     rax, cs:hWndChild
0x1800b8008  mov     r9, rcx; unsigned __int64
0x1800b800b  mov     rcx, cs:?Pbrs_hctl@@3PEAUCTL@@EA; struct CTL *
0x1800b8012  mov     [rsp+78h+var_38], rax
0x1800b8017  mov     rax, cs:qword_1803F3330
0x1800b801e  mov     r8d, 1040h; unsigned int
0x1800b8024  mov     [rsp+78h+var_30], rax
0x1800b8029  mov     rdx, [rcx+58h]; HWND
0x1800b802d  lea     rax, [rsp+78h+arg_0]
0x1800b8035  mov     [rsp+78h+var_50], rax; unsigned int *
0x1800b803a  lea     rax, [rsp+78h+var_38]
0x1800b803f  mov     [rsp+78h+arg_0], ebx
0x1800b8046  mov     qword ptr [rsp+78h+var_58], rax; __int64
0x1800b804b  call    ?CommonGizWndProc@@YA_JPEAUCTL@@PEAUHWND__@@I_K_JPEAK@Z; CommonGizWndProc(CTL *,HWND__ *,uint,unsigned __int64,__int64,ulong *)
0x1800b8050  jmp     short loc_1800B80AD
0x1800b8052  test    cs:dword_1803FB04C, 800h
0x1800b805c  jz      short loc_1800B80AD
0x1800b805e  cmp     cs:dword_1803FB048, 5
0x1800b8065  jnz     short loc_1800B80AD
0x1800b8067  mov     edx, cs:?Pbrs_it@@3W4IT@@A; IT Pbrs_it
0x1800b806d  mov     rcx, cs:?Pbrs_lpdispatch@@3PEAUIDispatch@@EA; IDispatch * Pbrs_lpdispatch
0x1800b8074  lea     r8, [rsp+78h+arg_18]
0x1800b807c  call    ?GetPerPropertyBrowsing@@YAXPEAUIDispatch@@W4IT@@PEAPEAUIPerPropertyBrowsing@@@Z; GetPerPropertyBrowsing(IDispatch *,IT,IPerPropertyBrowsing * *)
0x1800b8081  mov     rcx, [rsp+78h+arg_18]; struct IPerPropertyBrowsing *
0x1800b8089  test    rcx, rcx
0x1800b808c  jz      short loc_1800B80AD
0x1800b808e  call    ?_FillOCXList@@YAHPEAUIPerPropertyBrowsing@@@Z; _FillOCXList(IPerPropertyBrowsing *)
0x1800b8093  test    eax, eax
0x1800b8095  jz      short loc_1800B809F
0x1800b8097  btr     cs:dword_1803FB04C, 0Bh
0x1800b809f  mov     rcx, [rsp+78h+arg_18]
0x1800b80a7  mov     rax, [rcx]
0x1800b80aa  call    qword ptr [rax+10h]
0x1800b80ad  call    ?_SetListBoxIndexFromText@@YAHXZ; _SetListBoxIndexFromText(void)
0x1800b80b2  mov     edi, eax
0x1800b80b4  mov     rcx, cs:hWndChild; hWnd
0x1800b80bb  xor     r9d, r9d; lParam
0x1800b80be  xor     r8d, r8d; wParam
0x1800b80c1  mov     edx, 18Bh; Msg
0x1800b80c6  call    cs:__imp_SendMessageA
0x1800b80cc  test    eax, eax
0x1800b80ce  jle     loc_1800B816A
0x1800b80d4  mov     rcx, cs:hWndChild; hWnd
0x1800b80db  inc     edi
0x1800b80dd  mov     edx, 186h; Msg
0x1800b80e2  cmp     edi, eax
0x1800b80e4  cmovge  edi, ebx
0x1800b80e7  xor     r9d, r9d; lParam
0x1800b80ea  movsxd  r8, edi; wParam
0x1800b80ed  call    cs:__imp_SendMessageA
0x1800b80f3  or      cs:dword_1803FB04C, 4
0x1800b80fa  call    ?_SelToEdit@@YAXXZ; _SelToEdit(void)
0x1800b80ff  call    ?PbrsCommit@@YAXXZ; PbrsCommit(void)
0x1800b8104  jmp     short loc_1800B816A
0x1800b8106  call    ?_PickProp@@YAXXZ; _PickProp(void)
0x1800b810b  jmp     short loc_1800B816A
0x1800b810d  mov     eax, r8d
0x1800b8110  dec     eax
0x1800b8112  jz      short loc_1800B8188
0x1800b8114  sub     eax, 2
0x1800b8117  jz      short loc_1800B817C
0x1800b8119  dec     eax
0x1800b811b  jz      short loc_1800B8174
0x1800b811d  sub     eax, 3
0x1800b8120  jz      short loc_1800B8165
0x1800b8122  dec     eax
0x1800b8124  jnz     short loc_1800B8133
0x1800b8126  mov     rcx, cs:hWndTo; hWnd
0x1800b812d  call    cs:__imp_SetFocus
0x1800b8133  cmp     rsi, cs:hWndChild
0x1800b813a  jnz     loc_1800B82CD
0x1800b8140  dec     edi
0x1800b8142  jz      short loc_1800B8157
0x1800b8144  dec     edi
0x1800b8146  jnz     loc_1800B82CD
0x1800b814c  cmp     cs:?Pbrs_lpdispatch@@3PEAUIDispatch@@EA, rbx; IDispatch * Pbrs_lpdispatch
0x1800b8153  jz      short loc_1800B816A
0x1800b8155  jmp     short loc_1800B80FF
0x1800b8157  or      cs:dword_1803FB04C, 4
0x1800b815e  call    ?_SelToEdit@@YAXXZ; _SelToEdit(void)
0x1800b8163  jmp     short loc_1800B816A
0x1800b8165  call    ?_SizeComboList@@YAXXZ; _SizeComboList(void)
0x1800b816a  mov     eax, 1
0x1800b816f  jmp     loc_1800B82CF
0x1800b8174  mov     cs:?Pbar_fNoAccel@@3HA, ebx; int Pbar_fNoAccel
0x1800b817a  jmp     short loc_1800B816A
0x1800b817c  mov     cs:?Pbar_fNoAccel@@3HA, 1; int Pbar_fNoAccel
0x1800b8186  jmp     short loc_1800B816A
0x1800b8188  mov     eax, cs:?Pbrs_it@@3W4IT@@A; IT Pbrs_it
0x1800b818e  cmp     eax, 3
0x1800b8191  jz      loc_1800B82CD
0x1800b8197  cmp     eax, 2
0x1800b819a  jz      loc_1800B82CD
0x1800b81a0  cmp     eax, 5
0x1800b81a3  jz      loc_1800B82CD
0x1800b81a9  xor     r9d, r9d; lParam
  ... truncated ...
```
