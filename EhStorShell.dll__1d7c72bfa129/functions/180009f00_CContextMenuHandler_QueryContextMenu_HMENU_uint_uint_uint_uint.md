# CContextMenuHandler::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180009f00`
- end: `0x18000a34c`
- name: `?QueryContextMenu@CContextMenuHandler@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `1100`
- prototype: `__int64 __fastcall(CContextMenuHandler *this, HMENU, UINT, unsigned int, unsigned int, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800064cc`
- `0x1800066c0`
- `0x18000684c`
- `0x180009b44`
- `0x180009f00`
- `0x18000b630`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a048`
- `KERNEL32!GetLastError` at `0x18000a102`
- `KERNEL32!GetLastError` at `0x18000a1a2`
- `KERNEL32!GetLastError` at `0x18000a048`
- `KERNEL32!GetLastError` at `0x18000a102`
- `KERNEL32!GetLastError` at `0x18000a1a2`
- `KERNEL32!CompareStringW` at `0x18000a2ac`
- `KERNEL32!CompareStringW` at `0x18000a2ac`
- `USER32!SetMenuDefaultItem` at `0x18000a0bc`
- `USER32!SetMenuDefaultItem` at `0x18000a176`
- `USER32!SetMenuDefaultItem` at `0x18000a0bc`
- `USER32!SetMenuDefaultItem` at `0x18000a176`
- `USER32!LoadStringW` at `0x18000a02c`
- `USER32!LoadStringW` at `0x18000a0e6`
- `USER32!LoadStringW` at `0x18000a186`
- `USER32!LoadStringW` at `0x18000a2ce`
- `USER32!LoadStringW` at `0x18000a02c`
- `USER32!LoadStringW` at `0x18000a0e6`
- `USER32!LoadStringW` at `0x18000a186`
- `USER32!LoadStringW` at `0x18000a2ce`
- `USER32!InsertMenuW` at `0x180009ff4`
- `USER32!InsertMenuW` at `0x18000a0ae`
- `USER32!InsertMenuW` at `0x18000a168`
- `USER32!InsertMenuW` at `0x18000a208`
- `USER32!InsertMenuW` at `0x18000a2fb`
- `USER32!InsertMenuW` at `0x18000a33a`
- `USER32!InsertMenuW` at `0x180009ff4`
- `USER32!InsertMenuW` at `0x18000a0ae`
- `USER32!InsertMenuW` at `0x18000a168`
- `USER32!InsertMenuW` at `0x18000a208`
- `USER32!InsertMenuW` at `0x18000a2fb`
- `USER32!InsertMenuW` at `0x18000a33a`
- `ole32!CoTaskMemFree` at `0x18000a306`
- `ole32!CoTaskMemFree` at `0x18000a306`

## pseudocode

```c
__int64 __fastcall CContextMenuHandler::QueryContextMenu(
        CContextMenuHandler *this,
        HMENU a2,
        UINT a3,
        unsigned int a4,
        unsigned int a5,
        char a6)
{
  UINT_PTR v6; // r13
  PVOID *v10; // r9
  UINT v12; // edi
  UINT v13; // ebx
  int v14; // eax
  __int64 v15; // r9
  DWORD v16; // eax
  __int64 v17; // r9
  DWORD v18; // eax
  __int64 v19; // r9
  DWORD LastError; // eax
  UINT v21; // edi
  unsigned int v22; // r15d
  _QWORD *v23; // rax
  const WCHAR *lpNewItem; // rax
  UINT v25; // edx
  PCNZWCH lpString1; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v27; // [rsp+3Ch] [rbp-C4h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR NewItem[264]; // [rsp+250h] [rbp+150h] BYREF

  v6 = a4;
  v27 = a4;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids,
      WPP_GLOBAL_Control);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 16) )
    return 2147500037LL;
  if ( (int)v6 + *((_DWORD *)this + 10) + 1 > a5 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
      WPP_SF_(v10[2], 25, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, v10);
    return 2147500037LL;
  }
  v12 = a3 + 1;
  InsertMenuW(a2, a3, 0xC00u, v6, 0);
  v13 = v6 + 1;
  v14 = *((_DWORD *)this + 17);
  if ( (a6 & 1) == 0 )
  {
    if ( v14 )
    {
      if ( LoadStringW(g_hInst, 0x66u, Buffer, 260) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, v19);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, LastError);
      }
      InsertMenuW(a2, v12, 0x400u, v13, Buffer);
    }
    else
    {
      if ( LoadStringW(g_hInst, 0x67u, Buffer, 260) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, v17);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v18 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, v18);
      }
      InsertMenuW(a2, v12, 0x400u, v13, Buffer);
      SetMenuDefaultItem(a2, v13, 0);
    }
    v13 = v6 + 2;
    if ( !*((_QWORD *)this + 5) )
      return v13 - (unsigned int)v6;
    v21 = v12 + 1;
    v22 = 0;
    while ( 1 )
    {
      lpString1 = 0;
      v23 = (_QWORD *)ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::operator[](
                        (char *)this + 32,
                        v22);
      if ( (*(int (__fastcall **)(_QWORD, PCNZWCH *))(*(_QWORD *)*v23 + 24LL))(*v23, &lpString1) >= 0 )
        break;
LABEL_49:
      ++v22;
      ++v13;
      if ( (unsigned __int64)v22 >= *((_QWORD *)this + 5) )
      {
        LODWORD(v6) = v27;
        InsertMenuW(a2, v21, 0xC00u, v13++, 0);
        return v13 - (unsigned int)v6;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, lpString1);
    if ( CompareStringW(0, 0, lpString1, -1, L"Set password", -1) == 2 )
    {
      if ( !LoadStringW(g_hInst, 0x68u, NewItem, 260) )
      {
LABEL_48:
        CoTaskMemFree((LPVOID)lpString1);
        goto LABEL_49;
      }
      lpNewItem = NewItem;
    }
    else
    {
      lpNewItem = lpString1;
    }
    v25 = v21++;
    InsertMenuW(a2, v25, 0x400u, v13, lpNewItem);
    goto LABEL_48;
  }
  if ( !v14 )
  {
    if ( LoadStringW(g_hInst, 0x67u, Buffer, 260) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, v15);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v16 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, v16);
    }
    InsertMenuW(a2, v12, 0x400u, v13, Buffer);
    SetMenuDefaultItem(a2, v13, 0);
    v13 = v6 + 2;
  }
  return v13 - (unsigned int)v6;
}

```

## disassembly

```asm
0x180009f00  push    rbp
0x180009f02  push    rbx
0x180009f03  push    rsi
0x180009f04  push    rdi
0x180009f05  push    r12
0x180009f07  push    r13
0x180009f09  push    r14
0x180009f0b  push    r15
0x180009f0d  lea     rbp, [rsp-378h]
0x180009f15  sub     rsp, 478h
0x180009f1c  mov     rax, cs:__security_cookie
0x180009f23  xor     rax, rsp
0x180009f26  mov     [rbp+3B0h+var_50], rax
0x180009f2d  mov     r13d, r9d
0x180009f30  mov     ebx, r8d
0x180009f33  mov     [rsp+4B0h+var_474], r13d
0x180009f38  mov     rsi, rdx
0x180009f3b  mov     r14, rcx
0x180009f3e  mov     r9, cs:WPP_GLOBAL_Control
0x180009f45  lea     r15, WPP_GLOBAL_Control
0x180009f4c  mov     r12d, 20h ; ' '
0x180009f52  cmp     r9, r15
0x180009f55  jz      short loc_180009F79
0x180009f57  test    [r9+1Ch], r12b
0x180009f5b  jz      short loc_180009F79
0x180009f5d  mov     rcx, [r9+10h]
0x180009f61  lea     edx, [r12-8]
0x180009f66  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009f6d  call    WPP_SF_
0x180009f72  mov     r9, cs:WPP_GLOBAL_Control
0x180009f79  cmp     dword ptr [r14+40h], 0
0x180009f7e  jz      short loc_180009FB2
0x180009f80  mov     ecx, [r14+28h]
0x180009f84  inc     ecx
0x180009f86  add     ecx, r13d
0x180009f89  cmp     ecx, [rbp+3B0h+arg_20]
0x180009f8f  jbe     short loc_180009FDA
0x180009f91  cmp     r9, r15
0x180009f94  jz      short loc_180009FB2
0x180009f96  test    byte ptr [r9+1Ch], 2
0x180009f9b  jz      short loc_180009FB2
0x180009f9d  mov     rcx, [r9+10h]
0x180009fa1  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009fa8  mov     edx, 19h
0x180009fad  call    WPP_SF_
0x180009fb2  mov     eax, 80004005h
0x180009fb7  mov     rcx, [rbp+3B0h+var_50]
0x180009fbe  xor     rcx, rsp; StackCookie
0x180009fc1  call    __security_check_cookie
0x180009fc6  add     rsp, 478h
0x180009fcd  pop     r15
0x180009fcf  pop     r14
0x180009fd1  pop     r13
0x180009fd3  pop     r12
0x180009fd5  pop     rdi
0x180009fd6  pop     rsi
0x180009fd7  pop     rbx
0x180009fd8  pop     rbp
0x180009fd9  retn
0x180009fda  mov     r9, r13; uIDNewItem
0x180009fdd  mov     [rsp+4B0h+lpNewItem], 0; lpNewItem
0x180009fe6  mov     r8d, 0C00h; uFlags
0x180009fec  lea     edi, [rbx+1]
0x180009fef  mov     edx, ebx; uPosition
0x180009ff1  mov     rcx, rsi; hMenu
0x180009ff4  call    cs:__imp_InsertMenuW
0x180009ffa  test    byte ptr [rbp+3B0h+arg_28], 1
0x18000a001  lea     ebx, [r13+1]
0x18000a005  mov     eax, [r14+44h]
0x18000a009  jz      loc_18000A0C9
0x18000a00f  test    eax, eax
0x18000a011  jnz     loc_18000A342
0x18000a017  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000a01e  lea     r8, [rsp+4B0h+Buffer]; lpBuffer
0x18000a023  mov     r9d, 104h; cchBufferMax
0x18000a029  lea     edx, [rax+67h]; uID
0x18000a02c  call    cs:__imp_LoadStringW
0x18000a032  test    eax, eax
0x18000a034  jnz     short loc_18000A06F
0x18000a036  mov     rax, cs:WPP_GLOBAL_Control
0x18000a03d  cmp     rax, r15
0x18000a040  jz      short loc_18000A096
0x18000a042  test    [rax+1Ch], r12b
0x18000a046  jz      short loc_18000A096
0x18000a048  call    cs:__imp_GetLastError
0x18000a04e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a055  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x18000a05c  mov     edx, 1Ah
0x18000a061  mov     r9d, eax
0x18000a064  mov     rcx, [rcx+10h]
0x18000a068  call    WPP_SF_d
0x18000a06d  jmp     short loc_18000A096
0x18000a06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a076  cmp     rcx, r15
0x18000a079  jz      short loc_18000A096
0x18000a07b  test    [rcx+1Ch], r12b
0x18000a07f  jz      short loc_18000A096
0x18000a081  mov     rcx, [rcx+10h]
0x18000a085  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x18000a08c  mov     edx, 1Bh
0x18000a091  call    WPP_SF_
0x18000a096  lea     rax, [rsp+4B0h+Buffer]
0x18000a09b  mov     r9d, ebx; uIDNewItem
0x18000a09e  mov     r8d, 400h; uFlags
0x18000a0a4  mov     [rsp+4B0h+lpNewItem], rax; lpNewItem
0x18000a0a9  mov     edx, edi; uPosition
0x18000a0ab  mov     rcx, rsi; hMenu
0x18000a0ae  call    cs:__imp_InsertMenuW
0x18000a0b4  xor     r8d, r8d; fByPos
0x18000a0b7  mov     edx, ebx; uItem
0x18000a0b9  mov     rcx, rsi; hMenu
0x18000a0bc  call    cs:__imp_SetMenuDefaultItem
0x18000a0c2  inc     ebx
0x18000a0c4  jmp     loc_18000A342
0x18000a0c9  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000a0d0  mov     r9d, 104h; cchBufferMax
0x18000a0d6  lea     r8, [rsp+4B0h+Buffer]; lpBuffer
0x18000a0db  test    eax, eax
0x18000a0dd  jnz     loc_18000A181
0x18000a0e3  lea     edx, [rax+67h]; uID
0x18000a0e6  call    cs:__imp_LoadStringW
0x18000a0ec  test    eax, eax
0x18000a0ee  jnz     short loc_18000A129
0x18000a0f0  mov     rax, cs:WPP_GLOBAL_Control
0x18000a0f7  cmp     rax, r15
0x18000a0fa  jz      short loc_18000A150
0x18000a0fc  test    [rax+1Ch], r12b
0x18000a100  jz      short loc_18000A150
0x18000a102  call    cs:__imp_GetLastError
0x18000a108  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a10f  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x18000a116  mov     edx, 1Ch
0x18000a11b  mov     r9d, eax
0x18000a11e  mov     rcx, [rcx+10h]
0x18000a122  call    WPP_SF_d
0x18000a127  jmp     short loc_18000A150
0x18000a129  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a130  cmp     rcx, r15
0x18000a133  jz      short loc_18000A150
0x18000a135  test    [rcx+1Ch], r12b
0x18000a139  jz      short loc_18000A150
0x18000a13b  mov     rcx, [rcx+10h]
0x18000a13f  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x18000a146  mov     edx, 1Dh
0x18000a14b  call    WPP_SF_
0x18000a150  lea     rax, [rsp+4B0h+Buffer]
0x18000a155  mov     r9d, ebx; uIDNewItem
0x18000a158  mov     r8d, 400h; uFlags
0x18000a15e  mov     [rsp+4B0h+lpNewItem], rax; lpNewItem
0x18000a163  mov     edx, edi; uPosition
0x18000a165  mov     rcx, rsi; hMenu
0x18000a168  call    cs:__imp_InsertMenuW
0x18000a16e  xor     r8d, r8d; fByPos
0x18000a171  mov     edx, ebx; uItem
0x18000a173  mov     rcx, rsi; hMenu
0x18000a176  call    cs:__imp_SetMenuDefaultItem
0x18000a17c  jmp     loc_18000A20E
0x18000a181  mov     edx, 66h ; 'f'; uID
0x18000a186  call    cs:__imp_LoadStringW
0x18000a18c  test    eax, eax
0x18000a18e  jnz     short loc_18000A1C9
0x18000a190  mov     rax, cs:WPP_GLOBAL_Control
0x18000a197  cmp     rax, r15
0x18000a19a  jz      short loc_18000A1F0
0x18000a19c  test    [rax+1Ch], r12b
0x18000a1a0  jz      short loc_18000A1F0
0x18000a1a2  call    cs:__imp_GetLastError
0x18000a1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1af  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x18000a1b6  mov     edx, 1Eh
0x18000a1bb  mov     r9d, eax
0x18000a1be  mov     rcx, [rcx+10h]
0x18000a1c2  call    WPP_SF_d
0x18000a1c7  jmp     short loc_18000A1F0
0x18000a1c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1d0  cmp     rcx, r15
0x18000a1d3  jz      short loc_18000A1F0
0x18000a1d5  test    [rcx+1Ch], r12b
0x18000a1d9  jz      short loc_18000A1F0
0x18000a1db  mov     rcx, [rcx+10h]
0x18000a1df  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x18000a1e6  mov     edx, 1Fh
0x18000a1eb  call    WPP_SF_
0x18000a1f0  lea     rax, [rsp+4B0h+Buffer]
0x18000a1f5  mov     r9d, ebx; uIDNewItem
0x18000a1f8  mov     r8d, 400h; uFlags
0x18000a1fe  mov     [rsp+4B0h+lpNewItem], rax; lpNewItem
0x18000a203  mov     edx, edi; uPosition
0x18000a205  mov     rcx, rsi; hMenu
0x18000a208  call    cs:__imp_InsertMenuW
0x18000a20e  mov     rax, [r14+28h]
0x18000a212  inc     ebx
0x18000a214  test    rax, rax
0x18000a217  jz      loc_18000A342
0x18000a21d  inc     edi
0x18000a21f  test    rax, rax
0x18000a222  jz      loc_18000A323
0x18000a228  xor     r15d, r15d
0x18000a22b  lea     r13, WPP_GLOBAL_Control
0x18000a232  mov     edx, r15d
0x18000a235  lea     rcx, [r14+20h]
0x18000a239  mov     [rsp+4B0h+lpString1], 0
0x18000a242  call    ??A?$CAtlArray@PEAUIEnhancedStorageSiloAction@@V?$CElementTraits@PEAUIEnhancedStorageSiloAction@@@ATL@@@ATL@@QEAAAEAPEAUIEnhancedStorageSiloAction@@_K@Z; ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::operator[](unsigned __int64)
0x18000a247  lea     rdx, [rsp+4B0h+lpString1]
0x18000a24c  mov     rcx, [rax]
0x18000a24f  mov     rax, [rcx]
0x18000a252  mov     rax, [rax+18h]
0x18000a256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25b  test    eax, eax
0x18000a25d  js      loc_18000A30C
0x18000a263  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a26a  cmp     rcx, r13
0x18000a26d  jz      short loc_18000A28D
0x18000a26f  test    [rcx+1Ch], r12b
0x18000a273  jz      short loc_18000A28D
0x18000a275  mov     r9, [rsp+4B0h+lpString1]
0x18000a27a  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x18000a281  mov     rcx, [rcx+10h]
0x18000a285  mov     edx, r12d
0x18000a288  call    WPP_SF_S
0x18000a28d  mov     r8, [rsp+4B0h+lpString1]; lpString1
0x18000a292  lea     rax, aSetPassword; "Set password"
0x18000a299  or      ecx, 0FFFFFFFFh
0x18000a29c  xor     edx, edx; dwCmpFlags
0x18000a29e  mov     [rsp+4B0h+cchCount2], ecx; cchCount2
0x18000a2a2  mov     r9d, ecx; cchCount1
0x18000a2a5  xor     ecx, ecx; Locale
0x18000a2a7  mov     [rsp+4B0h+lpNewItem], rax; lpString2
0x18000a2ac  call    cs:__imp_CompareStringW
0x18000a2b2  cmp     eax, 2
0x18000a2b5  jnz     short loc_18000A2E1
0x18000a2b7  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000a2be  lea     r8, [rbp+3B0h+NewItem]; lpBuffer
0x18000a2c5  mov     r9d, 104h; cchBufferMax
0x18000a2cb  lea     edx, [rax+66h]; uID
0x18000a2ce  call    cs:__imp_LoadStringW
0x18000a2d4  test    eax, eax
0x18000a2d6  jz      short loc_18000A301
0x18000a2d8  lea     rax, [rbp+3B0h+NewItem]
0x18000a2df  jmp     short loc_18000A2E6
0x18000a2e1  mov     rax, [rsp+4B0h+lpString1]
0x18000a2e6  mov     edx, edi; uPosition
0x18000a2e8  mov     r9d, ebx; uIDNewItem
0x18000a2eb  inc     edi
0x18000a2ed  mov     [rsp+4B0h+lpNewItem], rax; lpNewItem
0x18000a2f2  mov     r8d, 400h; uFlags
0x18000a2f8  mov     rcx, rsi; hMenu
0x18000a2fb  call    cs:__imp_InsertMenuW
0x18000a301  mov     rcx, [rsp+4B0h+lpString1]; pv
0x18000a306  call    cs:__imp_CoTaskMemFree
0x18000a30c  inc     r15d
0x18000a30f  inc     ebx
0x18000a311  mov     eax, r15d
0x18000a314  cmp     rax, [r14+28h]
0x18000a318  jb      loc_18000A232
0x18000a31e  mov     r13d, [rsp+4B0h+var_474]
0x18000a323  mov     r9d, ebx; uIDNewItem
0x18000a326  mov     r8d, 0C00h; uFlags
0x18000a32c  mov     edx, edi; uPosition
0x18000a32e  mov     [rsp+4B0h+lpNewItem], 0; lpNewItem
0x18000a337  mov     rcx, rsi; hMenu
0x18000a33a  call    cs:__imp_InsertMenuW
0x18000a340  inc     ebx
0x18000a342  sub     ebx, r13d
0x18000a345  mov     eax, ebx
0x18000a347  jmp     loc_180009FB7
```
