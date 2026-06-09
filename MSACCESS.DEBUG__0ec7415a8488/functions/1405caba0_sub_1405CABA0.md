# sub_1405CABA0

- ea: `0x1405caba0`
- end: `0x1405cb021`
- name: `sub_1405CABA0`
- size: `1153`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `3`
- callee_count: `23`
- tags: `installer_update`

## callers

- `0x14036f870`
- `0x14037e3ec`
- `0x140a65c8e`

## callees

- `0x1400036c0`
- `0x140005600`
- `0x14005bf60`
- `0x14006aed0`
- `0x14008834c`
- `0x140091810`
- `0x1400e2ae0`
- `0x1400e3158`
- `0x1403b1c6c`
- `0x1404ceca0`
- `0x1404d321c`
- `0x1404d6680`
- `0x14056a4d0`
- `0x1405caba0`
- `0x1405e1444`
- `0x1405e4794`
- `0x1406d4bac`
- `0x1406de160`
- `0x1407dc2d4`
- `0x1407e10d0`
- `0x1407e6ed8`
- `0x1407f6ddc`
- `0x1407f8f7c`

## import_xrefs

- `USER32!MapWindowPoints` at `0x1405caf09`
- `USER32!MapWindowPoints` at `0x1405caf09`
- `USER32!GetWindowRect` at `0x1405caea9`
- `USER32!GetWindowRect` at `0x1405caea9`
- `USER32!SetFocus` at `0x1405cafd9`
- `USER32!SetFocus` at `0x1405cafd9`
- `USER32!SetWindowLongPtrW` at `0x1405cae9b`
- `USER32!SetWindowLongPtrW` at `0x1405cae9b`
- `USER32!GetWindowLongPtrW` at `0x1405cae86`
- `USER32!GetWindowLongPtrW` at `0x1405cafc0`
- `USER32!GetWindowLongPtrW` at `0x1405cae86`
- `USER32!GetWindowLongPtrW` at `0x1405cafc0`
- `USER32!GetParent` at `0x1405caef3`
- `USER32!GetParent` at `0x1405caef3`
- `USER32!ShowWindow` at `0x1405cae37`
- `USER32!ShowWindow` at `0x1405cae37`
- `USER32!UpdateWindow` at `0x1405caf94`
- `USER32!UpdateWindow` at `0x1405caf94`
- `USER32!MoveWindow` at `0x1405caf32`
- `USER32!MoveWindow` at `0x1405caf32`
- `USER32!IsIconic` at `0x1405cafa6`
- `USER32!IsIconic` at `0x1405cafa6`

## pseudocode

```c
__int64 __fastcall sub_1405CABA0(HWND hWnd)
{
  unsigned int v2; // r14d
  __int16 v3; // bx
  __int16 v4; // si
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 *v22; // rax
  __int64 v23; // rsi
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rsi
  unsigned int v28; // eax
  __int64 i; // r15
  LONG_PTR WindowLongPtrW; // rax
  int v31; // edx
  BOOL v32; // ecx
  HWND Parent; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rsi
  HWND v39; // rax
  _BYTE v41[40]; // [rsp+48h] [rbp-2C0h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-298h] BYREF

  v2 = 0;
  Rect = 0;
  v3 = sub_1400036C0(hWnd);
  v4 = sub_1400036C0(hWnd);
  if ( (v3 & 0xFF00) == 0xB00 )
    *(_DWORD *)(sub_14008834C(hWnd) + 24) = v4 & 0xFF00 | 0xB;
  else
    sub_1407F8F7C(hWnd);
  v6 = sub_1407F6DDC(hWnd, v5);
  if ( (unsigned int)sub_1404D321C(v6, 166) )
  {
    v7 = sub_14006AED0(hWnd);
    if ( v7 )
    {
      sub_1403B1C6C(v41, v7);
      ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
      v12 = *ThreadLocalStoragePointer;
      if ( !*(_BYTE *)(*ThreadLocalStoragePointer + 8) )
        sub_1400E3158(v9, v8, v10);
      if ( (unsigned int)sub_1404CECA0(*(_QWORD *)(*(_QWORD *)(v12 + 64) + 1784LL)) )
      {
        if ( !*(_BYTE *)(v12 + 8) )
          sub_1400E3158(v14, v13, v15);
        sub_14056A4D0(*(_QWORD *)(*(_QWORD *)(v12 + 64) + 1784LL), 0);
      }
      sub_140005600(v41);
      v2 = 0;
    }
  }
  if ( !(unsigned int)sub_140091810(hWnd) )
    sub_1407DC2D4(hWnd, (LONG_PTR)&sub_1405E3230);
  if ( (unsigned int)MidEastSupport_0(v17, v16) && sub_14006AED0(hWnd) )
  {
    v18 = sub_14006AED0(hWnd);
    sub_1403B1C6C(v41, v18);
    v22 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
    v23 = *v22;
    if ( !*(_BYTE *)(*v22 + 8) )
      sub_1400E3158(v20, v19, v21);
    if ( *(_BYTE *)(*(_QWORD *)(v23 + 24) + 8LL) != 1 && !*(_BYTE *)(v23 + 8) )
      sub_1400E3158(v20, v19, v21);
    sub_1407E10D0(hWnd);
    if ( !*(_BYTE *)(v23 + 8) )
      sub_1400E3158(v25, v24, v26);
    v2 = 0;
    *(_BYTE *)(qword_140E1B4C8 + 4712) = (*(_BYTE *)(*(_QWORD *)(v23 + 64) + 1776LL) != 0) + 1;
    sub_140005600(v41);
  }
  sub_1407E10D0(hWnd);
  v27 = *(_QWORD *)sub_1405E4794(hWnd);
  if ( v27 )
  {
    if ( *(_DWORD *)(v27 + 292) )
    {
      v28 = *(_DWORD *)(v27 + 288);
      do
      {
        for ( i = 0; (unsigned int)i < v28; v28 = *(_DWORD *)(v27 + 288) )
        {
          ShowWindow(*(HWND *)(v27 + 8 * (v2 + 4 * i) + 128), 1);
          i = (unsigned int)(i + 1);
        }
        ++v2;
      }
      while ( v2 < *(_DWORD *)(v27 + 292) );
    }
    sub_1406DE160(*(_QWORD *)(v27 + 352), 1, *(_DWORD *)(v27 + 116) != 0, *(_DWORD *)(v27 + 116) != 0, 1, 0);
    WindowLongPtrW = GetWindowLongPtrW(hWnd, -16);
    SetWindowLongPtrW(hWnd, -16, WindowLongPtrW | 0x2000000);
  }
  else
  {
    sub_1405E1444(hWnd);
  }
  GetWindowRect(hWnd, &Rect);
  v31 = Rect.right - Rect.left;
  if ( Rect.right - Rect.left < 160 )
    Rect.right = Rect.left + 160;
  v32 = v31 < 160;
  if ( Rect.bottom - Rect.top < 120 )
  {
    Rect.bottom = Rect.top + 120;
    v32 = 1;
  }
  if ( v32 )
  {
    Parent = GetParent(hWnd);
    MapWindowPoints(0, Parent, (LPPOINT)&Rect, 2u);
    MoveWindow(hWnd, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 1);
  }
  if ( !(unsigned int)sub_140091810(hWnd) )
  {
    v34 = sub_14006AED0(hWnd);
    if ( v34 )
    {
      sub_1403B1C6C(v41, v34);
      v38 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
      if ( !*(_BYTE *)(v38 + 8) )
        sub_1400E3158(v36, v35, v37);
      if ( (*(_BYTE *)(*(_QWORD *)(v38 + 64) + 1376LL) & 1) == 0 )
      {
        UpdateWindow(hWnd);
        if ( !hWnd
          || !IsIconic(hWndMain)
          || (v39 = (HWND)sub_1407E6ED8(hWnd), (GetWindowLongPtrW(v39, -16) & 0x80000000LL) != 0) )
        {
          if ( dword_140E34778 )
            SetFocus(hWnd);
        }
      }
      sub_140005600(v41);
    }
  }
  sub_1406D4BAC(5);
  sub_1404D6680(hWnd);
  return 0;
}

```

## disassembly

```asm
0x1405caba0  mov     [rsp+arg_10], r8d
0x1405caba5  push    rbx
0x1405caba6  push    rsi
0x1405caba7  push    rdi
0x1405caba8  push    r12
0x1405cabaa  push    r13
0x1405cabac  push    r14
0x1405cabae  push    r15
0x1405cabb0  sub     rsp, 2D0h
0x1405cabb7  mov     rax, cs:__security_cookie
0x1405cabbe  xor     rax, rsp
0x1405cabc1  mov     [rsp+308h+var_48], rax
0x1405cabc9  mov     r12, r9
0x1405cabcc  mov     rdi, rcx
0x1405cabcf  mov     [rsp+308h+var_2D0], rcx
0x1405cabd4  xor     r14d, r14d
0x1405cabd7  mov     [rsp+308h+var_2C8], r14
0x1405cabdc  xorps   xmm0, xmm0
0x1405cabdf  movups  xmmword ptr [rsp+308h+Rect.left], xmm0
0x1405cabe4  call    sub_1400036C0
0x1405cabe9  mov     ebx, eax
0x1405cabeb  mov     rcx, rdi; hWnd
0x1405cabee  call    sub_1400036C0
0x1405cabf3  mov     esi, eax
0x1405cabf5  mov     [rsp+308h+var_2D8], eax
0x1405cabf9  mov     r15d, 0FF00h
0x1405cabff  and     ebx, r15d
0x1405cac02  mov     rcx, rdi; hWnd
0x1405cac05  cmp     ebx, 0B00h
0x1405cac0b  jz      short loc_1405CAC1C
0x1405cac0d  and     esi, r15d
0x1405cac10  or      esi, 0Bh
0x1405cac13  mov     edx, esi
0x1405cac15  call    sub_1407F8F7C
0x1405cac1a  jmp     short loc_1405CAC2A
0x1405cac1c  call    sub_14008834C
0x1405cac21  and     esi, r15d
0x1405cac24  or      esi, 0Bh
0x1405cac27  mov     [rax+18h], esi
0x1405cac2a  mov     rcx, rdi
0x1405cac2d  call    sub_1407F6DDC
0x1405cac32  mov     edx, 0A6h
0x1405cac37  mov     rcx, rax
0x1405cac3a  call    sub_1404D321C
0x1405cac3f  test    eax, eax
0x1405cac41  jz      loc_1405CACC7
0x1405cac47  mov     rcx, rdi
0x1405cac4a  call    sub_14006AED0
0x1405cac4f  test    rax, rax
0x1405cac52  jz      short loc_1405CACC7
0x1405cac54  mov     rdx, rax
0x1405cac57  lea     rcx, [rsp+308h+var_2C0]
0x1405cac5c  call    sub_1403B1C6C
0x1405cac61  nop
0x1405cac62  mov     rax, gs:58h
0x1405cac6b  mov     rbx, [rax]
0x1405cac6e  mov     r15d, 8
0x1405cac74  cmp     [rbx+r15], r14b
0x1405cac78  jnz     short loc_1405CAC7F
0x1405cac7a  call    sub_1400E3158
0x1405cac7f  mov     r13d, 40h ; '@'
0x1405cac85  mov     rcx, [rbx+r13]
0x1405cac89  mov     rcx, [rcx+6F8h]
0x1405cac90  call    sub_1404CECA0
0x1405cac95  test    eax, eax
0x1405cac97  jz      short loc_1405CACB8
0x1405cac99  cmp     byte ptr [rbx+r15], 0
0x1405cac9e  jnz     short loc_1405CACA5
0x1405caca0  call    sub_1400E3158
0x1405caca5  mov     rax, [rbx+r13]
0x1405caca9  xor     edx, edx
0x1405cacab  mov     rcx, [rax+6F8h]
0x1405cacb2  call    sub_14056A4D0
0x1405cacb7  nop
0x1405cacb8  lea     rcx, [rsp+308h+var_2C0]
0x1405cacbd  call    sub_140005600
0x1405cacc2  xor     r14d, r14d
0x1405cacc5  jmp     short loc_1405CACD3
0x1405cacc7  mov     r15d, 8
0x1405caccd  mov     r13d, 40h ; '@'
0x1405cacd3  mov     rcx, rdi
0x1405cacd6  call    sub_140091810
0x1405cacdb  test    eax, eax
0x1405cacdd  jnz     short loc_1405CACF3
0x1405cacdf  lea     rdx, sub_1405E3230; dwNewLong
0x1405cace6  mov     rcx, rdi; hWnd
0x1405cace9  call    sub_1407DC2D4
0x1405cacee  mov     [rsp+308h+var_2C8], rax
0x1405cacf3  call    MidEastSupport_0
0x1405cacf8  mov     rcx, rdi; hWnd
0x1405cacfb  test    eax, eax
0x1405cacfd  jz      loc_1405CADE4
0x1405cad03  call    sub_14006AED0
0x1405cad08  test    rax, rax
0x1405cad0b  jz      loc_1405CADC1
0x1405cad11  mov     rcx, rdi
0x1405cad14  call    sub_14006AED0
0x1405cad19  mov     rdx, rax
0x1405cad1c  lea     rcx, [rsp+308h+var_2C0]
0x1405cad21  call    sub_1403B1C6C
0x1405cad26  nop
0x1405cad27  mov     rax, gs:58h
0x1405cad30  mov     rsi, [rax]
0x1405cad33  cmp     [rsi+r15], r14b
0x1405cad37  jnz     short loc_1405CAD3E
0x1405cad39  call    sub_1400E3158
0x1405cad3e  mov     eax, 18h
0x1405cad43  mov     rax, [rsi+rax]
0x1405cad47  mov     ebx, 1
0x1405cad4c  cmp     [rax+8], bl
0x1405cad4f  jnz     short loc_1405CAD68
0x1405cad51  mov     r14d, r13d
0x1405cad54  xor     edx, edx
0x1405cad56  mov     rax, cs:qword_140E1B4C8
0x1405cad5d  cmp     [rax+1248h], dl
0x1405cad63  setz    dl
0x1405cad66  jmp     short loc_1405CAD81
0x1405cad68  cmp     [rsi+r15], r14b
0x1405cad6c  jnz     short loc_1405CAD73
0x1405cad6e  call    sub_1400E3158
0x1405cad73  mov     r14d, r13d
0x1405cad76  mov     rax, [rsi+r14]
0x1405cad7a  movzx   edx, byte ptr [rax+6F0h]
0x1405cad81  mov     rcx, rdi; hWnd
0x1405cad84  call    sub_1407E10D0
0x1405cad89  cmp     byte ptr [r15+rsi], 0
0x1405cad8e  jnz     short loc_1405CAD95
0x1405cad90  call    sub_1400E3158
0x1405cad95  mov     rax, [rsi+r14]
0x1405cad99  xor     r14d, r14d
0x1405cad9c  cmp     [rax+6F0h], r14b
0x1405cada3  setnz   cl
0x1405cada6  add     cl, bl
0x1405cada8  mov     rax, cs:qword_140E1B4C8
0x1405cadaf  mov     [rax+1268h], cl
0x1405cadb5  lea     rcx, [rsp+308h+var_2C0]
0x1405cadba  call    sub_140005600
0x1405cadbf  jmp     short loc_1405CADC6
0x1405cadc1  mov     ebx, 1
0x1405cadc6  mov     edx, r14d
0x1405cadc9  mov     rax, cs:qword_140E1B4C8
0x1405cadd0  cmp     [rax+1248h], r14b
0x1405cadd7  setz    dl
0x1405cadda  mov     rcx, rdi; hWnd
0x1405caddd  call    sub_1407E10D0
0x1405cade2  jmp     short loc_1405CADF0
0x1405cade4  xor     edx, edx
0x1405cade6  call    sub_1407E10D0
0x1405cadeb  mov     ebx, 1
0x1405cadf0  mov     rcx, rdi
0x1405cadf3  call    sub_1405E4794
0x1405cadf8  mov     rsi, [rax]
0x1405cadfb  test    rsi, rsi
0x1405cadfe  jnz     short loc_1405CAE10
0x1405cae00  mov     rdx, r12
0x1405cae03  mov     rcx, rdi; hWnd
0x1405cae06  call    sub_1405E1444
0x1405cae0b  jmp     loc_1405CAEA1
0x1405cae10  cmp     dword ptr [rsi+124h], 0
0x1405cae17  jbe     short loc_1405CAE57
0x1405cae19  mov     eax, [rsi+120h]
0x1405cae1f  xor     r15d, r15d
0x1405cae22  test    eax, eax
0x1405cae24  jz      short loc_1405CAE4B
0x1405cae26  mov     r12d, r14d
0x1405cae29  lea     rcx, [r12+r15*4]
0x1405cae2d  mov     edx, ebx; nCmdShow
0x1405cae2f  mov     rcx, [rsi+rcx*8+80h]; hWnd
0x1405cae37  call    cs:ShowWindow
0x1405cae3d  add     r15d, ebx
0x1405cae40  mov     eax, [rsi+120h]
0x1405cae46  cmp     r15d, eax
0x1405cae49  jb      short loc_1405CAE29
0x1405cae4b  add     r14d, ebx
0x1405cae4e  cmp     r14d, [rsi+124h]
0x1405cae55  jb      short loc_1405CAE1F
0x1405cae57  xor     r14d, r14d
0x1405cae5a  mov     r8d, r14d
0x1405cae5d  cmp     [rsi+74h], r14d
0x1405cae61  setnz   r8b
0x1405cae65  mov     [rsp+308h+bRepaint], r14d
0x1405cae6a  mov     [rsp+308h+nHeight], ebx
0x1405cae6e  mov     r9d, r8d
0x1405cae71  mov     edx, ebx
0x1405cae73  mov     rcx, [rsi+160h]
0x1405cae7a  call    sub_1406DE160
0x1405cae7f  lea     edx, [r14-10h]; nIndex
0x1405cae83  mov     rcx, rdi; hWnd
0x1405cae86  call    cs:GetWindowLongPtrW
0x1405cae8c  bts     rax, 19h
0x1405cae91  mov     r8, rax; dwNewLong
0x1405cae94  lea     edx, [r14-10h]; nIndex
0x1405cae98  mov     rcx, rdi; hWnd
0x1405cae9b  call    cs:SetWindowLongPtrW
0x1405caea1  lea     rdx, [rsp+308h+Rect]; lpRect
0x1405caea6  mov     rcx, rdi; hWnd
0x1405caea9  call    cs:GetWindowRect
0x1405caeaf  mov     edx, [rsp+308h+Rect.right]
0x1405caeb3  mov     eax, [rsp+308h+Rect.left]
0x1405caeb7  sub     edx, eax
0x1405caeb9  mov     r8d, 0A0h
0x1405caebf  cmp     edx, r8d
0x1405caec2  jge     short loc_1405CAECB
0x1405caec4  add     eax, r8d
0x1405caec7  mov     [rsp+308h+Rect.right], eax
0x1405caecb  mov     ecx, r14d
0x1405caece  cmp     edx, r8d
0x1405caed1  setl    cl
0x1405caed4  mov     eax, [rsp+308h+Rect.bottom]
0x1405caed8  mov     edx, [rsp+308h+Rect.top]
0x1405caedc  sub     eax, edx
0x1405caede  cmp     eax, 78h ; 'x'
0x1405caee1  jge     short loc_1405CAEEC
0x1405caee3  lea     eax, [rdx+78h]
0x1405caee6  mov     [rsp+308h+Rect.bottom], eax
0x1405caeea  mov     ecx, ebx
0x1405caeec  test    ecx, ecx
0x1405caeee  jz      short loc_1405CAF38
0x1405caef0  mov     rcx, rdi; hWnd
0x1405caef3  call    cs:GetParent
0x1405caef9  mov     rdx, rax; hWndTo
0x1405caefc  mov     r9d, 2; cPoints
0x1405caf02  lea     r8, [rsp+308h+Rect]; lpPoints
0x1405caf07  xor     ecx, ecx; hWndFrom
0x1405caf09  call    cs:MapWindowPoints
0x1405caf0f  mov     eax, [rsp+308h+Rect.bottom]
0x1405caf13  mov     r8d, [rsp+308h+Rect.top]; Y
0x1405caf18  sub     eax, r8d
0x1405caf1b  mov     r9d, [rsp+308h+Rect.right]
0x1405caf20  mov     edx, [rsp+308h+Rect.left]; X
0x1405caf24  sub     r9d, edx; nWidth
0x1405caf27  mov     [rsp+308h+bRepaint], ebx; bRepaint
0x1405caf2b  mov     [rsp+308h+nHeight], eax; nHeight
0x1405caf2f  mov     rcx, rdi; hWnd
0x1405caf32  call    cs:MoveWindow
0x1405caf38  mov     rcx, rdi
0x1405caf3b  call    sub_140091810
0x1405caf40  test    eax, eax
0x1405caf42  jnz     loc_1405CAFE9
0x1405caf48  mov     rcx, rdi
0x1405caf4b  call    sub_14006AED0
0x1405caf50  test    rax, rax
0x1405caf53  jz      loc_1405CAFE9
0x1405caf59  mov     rdx, rax
0x1405caf5c  lea     rcx, [rsp+308h+var_2C0]
0x1405caf61  call    sub_1403B1C6C
0x1405caf66  mov     rax, gs:58h
0x1405caf6f  mov     rsi, [rax]
0x1405caf72  mov     eax, 8
0x1405caf77  cmp     [rsi+rax], r14b
0x1405caf7b  jnz     short loc_1405CAF82
0x1405caf7d  call    sub_1400E3158
0x1405caf82  mov     eax, r13d
0x1405caf85  mov     rcx, [rax+rsi]
0x1405caf89  test    [rcx+560h], bl
0x1405caf8f  jnz     short loc_1405CAFDF
0x1405caf91  mov     rcx, rdi; hWnd
0x1405caf94  call    cs:UpdateWindow
0x1405caf9a  test    rdi, rdi
0x1405caf9d  jz      short loc_1405CAFCD
0x1405caf9f  mov     rcx, cs:hWndMain; hWnd
0x1405cafa6  call    cs:IsIconic
0x1405cafac  test    eax, eax
0x1405cafae  jz      short loc_1405CAFCD
0x1405cafb0  mov     rcx, rdi; hWnd
0x1405cafb3  call    sub_1407E6ED8
0x1405cafb8  mov     rcx, rax; hWnd
0x1405cafbb  mov     edx, 0FFFFFFF0h; nIndex
0x1405cafc0  call    cs:GetWindowLongPtrW
0x1405cafc6  bt      rax, 1Fh
0x1405cafcb  jnb     short loc_1405CAFDF
0x1405cafcd  cmp     cs:dword_140E34778, r14d
0x1405cafd4  jz      short loc_1405CAFDF
0x1405cafd6  mov     rcx, rdi; hWnd
0x1405cafd9  call    cs:SetFocus
0x1405cafdf  lea     rcx, [rsp+308h+var_2C0]
0x1405cafe4  call    sub_140005600
0x1405cafe9  mov     ecx, 5
0x1405cafee  call    sub_1406D4BAC
0x1405caff3  mov     rcx, rdi; hWnd
0x1405caff6  call    sub_1404D6680
0x1405caffb  nop
0x1405caffc  xor     eax, eax
0x1405caffe  mov     rcx, [rsp+308h+var_48]
0x1405cb006  xor     rcx, rsp; StackCookie
0x1405cb009  call    __security_check_cookie
0x1405cb00e  add     rsp, 2D0h
0x1405cb015  pop     r15
0x1405cb017  pop     r14
0x1405cb019  pop     r13
0x1405cb01b  pop     r12
0x1405cb01d  pop     rdi
0x1405cb01e  pop     rsi
0x1405cb01f  pop     rbx
0x1405cb020  retn
```
