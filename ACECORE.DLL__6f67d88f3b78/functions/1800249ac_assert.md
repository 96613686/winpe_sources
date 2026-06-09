# _assert

- ea: `0x1800249ac`
- end: `0x180024f25`
- name: `_assert`
- size: `1401`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000cac0`
- `0x18000d3f0`
- `0x1800eae00`

## callees

- `0x180001818`
- `0x1800244c4`
- `0x1800248fc`
- `0x1800249ac`
- `0x180046434`
- `0x18004a9bc`
- `0x1801cdd94`
- `0x1801ce394`
- `0x1801d4f70`
- `0x1801d6c50`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024e07`
- `KERNEL32!GetProcAddress` at `0x180024e07`
- `KERNEL32!FreeLibrary` at `0x180024ee4`
- `KERNEL32!FreeLibrary` at `0x180024ee4`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180024d29`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180024d29`
- `Mso30Win32Client!Mso30Win32Client_12962` at `0x180024c55`
- `Mso30Win32Client!Mso30Win32Client_12962` at `0x180024c55`
- `Mso20Win32Client!Mso20Win32Client_59137` at `0x180024d3a`
- `Mso20Win32Client!Mso20Win32Client_59137` at `0x180024d3a`

## string_xrefs

- `0x180024d19`: `SOFTWARE\Microsoft\Office\16.0\Access Connectivity Engine\Engines\`
- `0x180024a3e`: `MS Access`

## pseudocode

```c
void __fastcall __noreturn assert(signed int a1, _WORD *a2, _DWORD *a3)
{
  unsigned int v3; // r14d
  __int64 v4; // r13
  int v5; // esi
  unsigned int v8; // edi
  __int16 v9; // ax
  __int16 *v10; // rcx
  __int64 v11; // r8
  const wchar_t *v12; // r10
  signed __int64 v13; // r9
  __int16 v14; // cx
  wchar_t v15; // dx
  __int64 v16; // r8
  const wchar_t *v17; // r10
  signed __int64 v18; // r9
  __int16 v19; // cx
  wchar_t v20; // dx
  __int64 v21; // r8
  unsigned int v22; // r12d
  __int64 v23; // r15
  unsigned int v24; // r14d
  __int64 *v25; // rsi
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 *v28; // rbx
  __int64 v29; // r9
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rdx
  DWORD v33; // r9d
  int v34; // eax
  DWORD v35; // eax
  __int64 v36; // r8
  __int64 v37; // r9
  HMODULE v38; // r15
  bool v39; // zf
  __int64 i; // rdx
  __int64 v41; // rax
  FARPROC ProcAddress; // rax
  int v43; // edi
  int v44; // eax
  DWORD v45; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD *v47; // [rsp+40h] [rbp-C0h]
  _QWORD v48[7]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Destination[104]; // [rsp+80h] [rbp-80h] BYREF
  BYTE v50[528]; // [rsp+150h] [rbp+50h] BYREF

  v3 = 0;
  v4 = a1;
  v5 = -1;
  v47 = a3;
  v45 = a1;
  v8 = 0;
  if ( !a2 )
    goto LABEL_16;
  v9 = *a2;
  v10 = a2 + 1;
  if ( *a2 == 59 )
    goto LABEL_16;
  do
  {
    if ( !v9 )
      break;
    v9 = *v10;
    ++v8;
    ++v10;
  }
  while ( v9 != 59 );
  if ( !v8 )
  {
LABEL_16:
    *a3 = 0xFFFF;
    return;
  }
  v11 = 9;
  if ( v8 == 9 )
  {
    v12 = L"MS Access";
    v13 = (char *)a2 - (char *)L"MS Access";
    do
    {
      v14 = *(const wchar_t *)((char *)v12 + v13) + 32;
      if ( (unsigned __int16)(*(const wchar_t *)((char *)v12 + v13) - 65) > 0x19u )
        v14 = *(const wchar_t *)((char *)v12 + v13);
      v15 = *v12 + 32;
      if ( (unsigned __int16)(*v12 - 65) > 0x19u )
        v15 = *v12;
      ++v12;
      --v11;
    }
    while ( v11 && v14 && v14 == v15 );
    if ( v14 == v15 )
      goto LABEL_16;
  }
  else
  {
    v16 = 4;
    if ( v8 == 4 )
    {
      v17 = L"ODBC";
      v18 = (char *)a2 - (char *)L"ODBC";
      do
      {
        v19 = *(const wchar_t *)((char *)v17 + v18) + 32;
        if ( (unsigned __int16)(*(const wchar_t *)((char *)v17 + v18) - 65) > 0x19u )
          v19 = *(const wchar_t *)((char *)v17 + v18);
        v20 = *v17 + 32;
        if ( (unsigned __int16)(*v17 - 65) > 0x19u )
          v20 = *v17;
        ++v17;
        --v16;
      }
      while ( v16 && v19 && v19 == v20 );
      if ( v19 == v20 )
      {
        *a3 = 65534;
        return;
      }
    }
  }
  if ( (!(unsigned int)sub_1800248FC(a2) || (unsigned int)sub_1801CDD94()) && (int)sub_1800244C4(v4) >= 0 )
  {
    v22 = *((_DWORD *)qword_18025EA80 + 898 * v4 + 262);
    v23 = *((_QWORD *)qword_18025EA80 + 449 * v4 + 132);
    if ( v22 )
    {
      do
      {
        if ( !(unsigned int)sub_180001818(a2, v23, v8) && !*(_WORD *)(v23 + 2LL * v8) )
          break;
        ++v3;
        v23 += 68;
      }
      while ( v3 < v22 );
      LODWORD(v4) = v45;
    }
    if ( v3 == v22 )
    {
      v24 = 0;
      v48[0] = L"Lotus WK1";
      v25 = v48;
      v48[1] = L"Lotus WK3";
      v48[2] = L"Lotus WK4";
      v48[3] = L"Paradox 3.x";
      v48[4] = L"Paradox 4.x";
      v48[5] = L"Paradox 5.x";
      v48[6] = L"Paradox 7.x";
      do
      {
        v26 = *v25;
        if ( *v25 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *(_WORD *)(v26 + 2 * v27) );
        }
        else
        {
          v27 = 0;
        }
        if ( (unsigned int)Mso30Win32Client_12962(v26, v27, a2, v8, 1) )
          break;
        ++v24;
        ++v25;
      }
      while ( v24 < 7 );
      return;
    }
    v28 = (__int64 *)sub_180046434((unsigned int)v4, v3, v21, 0);
    if ( !v28 )
    {
      v5 = dword_18025D9A8;
      if ( dword_18025D9A8 == -1 )
      {
        v32 = -1;
      }
      else
      {
        v30 = 5LL * dword_18025D9A8;
        v31 = qword_18025D9B0[5 * dword_18025D9A8 + 4];
        v32 = dword_18025D9A8;
        *(_OWORD *)&qword_18025D9B0[v30] = 0;
        dword_18025D9A8 = v31;
        *(_OWORD *)&qword_18025D9B0[v30 + 2] = 0;
        qword_18025D9B0[v30 + 4] = 0;
        LODWORD(qword_18025D9B0[v30 + 4]) = -1;
      }
      if ( v5 == -1 )
        return;
      v28 = &qword_18025D9B0[5 * v32];
    }
    if ( v28[1] != v29 )
    {
LABEL_86:
      *v47 = *((_DWORD *)v28 + 7);
      return;
    }
    v46 = v29;
    v45 = 520;
    if ( *(_WORD *)(v23 + 34) == (_WORD)v29
      || (wcsncpy_s(
            Destination,
            0x64u,
            L"SOFTWARE\\Microsoft\\Office\\16.0\\Access Connectivity Engine\\Engines\\",
            0xFFFFFFFFFFFFFFFFuLL),
          Mso20Win32Client_59137(v23 + 34, Destination, 100),
          v34 = sub_18004A9BC(HKEY_LOCAL_MACHINE, Destination, L"win32", v33, v50, &v45),
          LODWORD(v29) = 0,
          v34)
      || !*(_WORD *)(v23 + 34) )
    {
      v35 = v29;
    }
    else
    {
      v35 = v45 >> 1;
    }
    if ( v35 - 1 > 0x102 )
    {
      v39 = dword_18025EA74 == (_DWORD)v29;
LABEL_62:
      if ( !v39 )
      {
        LODWORD(qword_18025D9B0[5 * v5 + 4]) = dword_18025D9A8;
        dword_18025D9A8 = v5;
      }
      return;
    }
    v38 = (HMODULE)sub_1801CE394(v50);
    if ( !v38 )
    {
      v39 = dword_18025EA74 == 0;
      goto LABEL_62;
    }
    for ( i = 0; (unsigned int)i < v22; i = (unsigned int)(i + 1) )
    {
      v41 = sub_180046434((unsigned int)v4, i, v36, v37);
      if ( v41 && *(HMODULE *)(v41 + 8) == v38 && *(_DWORD *)(v41 + 28) == (_DWORD)i )
        break;
    }
    if ( (_DWORD)i != v22 )
    {
LABEL_81:
      *v28 = v46;
      v28[1] = (__int64)v38;
      *((_DWORD *)v28 + 6) = 0;
      *((_DWORD *)v28 + 7) = i;
      if ( v5 != -1 && qword_18025EA80 && v3 <= 0x27 && (unsigned int)v4 <= 0x3F )
        *((_QWORD *)qword_18025EA80 + 449 * (int)v4 + (int)v3 + 134) = v28;
      goto LABEL_86;
    }
    ProcAddress = GetProcAddress(v38, (LPCSTR)1);
    if ( !ProcAddress )
    {
      v43 = -1003;
      goto LABEL_79;
    }
    if ( ((int (__fastcall *)(__int64 (__fastcall **)(), __int64 *))ProcAddress)(&off_1802250C0, &v46) < 0 )
    {
LABEL_87:
      FreeLibrary(v38);
      if ( dword_18025EA74 )
      {
        LODWORD(qword_18025D9B0[5 * v5 + 4]) = dword_18025D9A8;
        dword_18025D9A8 = v5;
      }
      return;
    }
    if ( (*(_BYTE *)v46 & 0x20) != 0 )
    {
      v44 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v46 + 80))((int)v4 + 144, v28 + 2);
    }
    else
    {
      if ( (*(_BYTE *)v46 & 8) == 0 )
      {
        v43 = -1070;
LABEL_79:
        if ( v43 >= 0 )
        {
          LODWORD(i) = v3;
          goto LABEL_81;
        }
        goto LABEL_87;
      }
      v44 = (*(__int64 (__fastcall **)(_QWORD))(v46 + 80))((int)v4 + 144);
    }
    v43 = v44;
    goto LABEL_79;
  }
}

```

## disassembly

```asm
0x1800249ac  mov     [rsp-8+arg_18], rbx
0x1800249b1  push    rbp
0x1800249b2  push    rsi
0x1800249b3  push    rdi
0x1800249b4  push    r12
0x1800249b6  push    r13
0x1800249b8  push    r14
0x1800249ba  push    r15
0x1800249bc  lea     rbp, [rsp-270h]
0x1800249c4  sub     rsp, 370h
0x1800249cb  mov     rax, cs:__security_cookie
0x1800249d2  xor     rax, rsp
0x1800249d5  mov     [rbp+2A0h+var_40], rax
0x1800249dc  xor     r14d, r14d
0x1800249df  movsxd  r13, ecx
0x1800249e2  or      esi, 0FFFFFFFFh
0x1800249e5  mov     [rsp+3A0h+var_360], r8
0x1800249ea  mov     [rsp+3A0h+var_370], r13d
0x1800249ef  mov     r11, r8
0x1800249f2  mov     rbx, rdx
0x1800249f5  mov     edi, r14d
0x1800249f8  test    rdx, rdx
0x1800249fb  jz      loc_180024A9D
0x180024a01  movzx   eax, word ptr [rdx]
0x180024a04  lea     rcx, [rdx+2]
0x180024a08  cmp     ax, 3Bh ; ';'
0x180024a0c  jz      loc_180024A9D
0x180024a12  test    ax, ax
0x180024a15  jz      short loc_180024A26
0x180024a17  movzx   eax, word ptr [rcx]
0x180024a1a  inc     edi
0x180024a1c  add     rcx, 2
0x180024a20  cmp     ax, 3Bh ; ';'
0x180024a24  jnz     short loc_180024A12
0x180024a26  test    edi, edi
0x180024a28  jz      short loc_180024A9D
0x180024a2a  mov     r8d, 9
0x180024a30  mov     r15w, 20h ; ' '
0x180024a35  cmp     edi, r8d
0x180024a38  jnz     loc_180024AD0
0x180024a3e  lea     r10, aMsAccess
0x180024a45  mov     r9, rbx
0x180024a48  sub     r9, r10
0x180024a4b  movzx   eax, word ptr [r9+r10]
0x180024a50  movzx   ecx, word ptr [r10+r9]
0x180024a55  sub     ax, 41h ; 'A'
0x180024a59  movzx   edx, word ptr [r10]
0x180024a5d  add     cx, r15w
0x180024a61  cmp     ax, 19h
0x180024a65  movzx   eax, word ptr [r10]
0x180024a69  cmova   cx, [r10+r9]
0x180024a6f  add     dx, r15w
0x180024a73  sub     ax, 41h ; 'A'
0x180024a77  cmp     ax, 19h
0x180024a7b  cmova   dx, [r10]
0x180024a80  lea     r10, [r10+2]
0x180024a84  sub     r8, 1
0x180024a88  jz      short loc_180024A94
0x180024a8a  test    cx, cx
0x180024a8d  jz      short loc_180024A94
0x180024a8f  cmp     cx, dx
0x180024a92  jz      short loc_180024A4B
0x180024a94  cmp     cx, dx
0x180024a97  jnz     loc_180024B42
0x180024a9d  mov     dword ptr [r11], 0FFFFh
0x180024aa4  xor     eax, eax
0x180024aa6  mov     rcx, [rbp+2A0h+var_40]
0x180024aad  xor     rcx, rsp; StackCookie
0x180024ab0  call    __security_check_cookie
0x180024ab5  mov     rbx, [rsp+3A0h+arg_18]
0x180024abd  add     rsp, 370h
0x180024ac4  pop     r15
0x180024ac6  pop     r14
0x180024ac8  pop     r13
0x180024aca  pop     r12
0x180024acc  pop     rdi
0x180024acd  pop     rsi
0x180024ace  pop     rbp
0x180024acf  retn
0x180024ad0  mov     r8d, 4
0x180024ad6  cmp     edi, r8d
0x180024ad9  jnz     short loc_180024B42
0x180024adb  lea     r10, aOdbc
0x180024ae2  mov     r9, rbx
0x180024ae5  sub     r9, r10
0x180024ae8  movzx   eax, word ptr [r9+r10]
0x180024aed  movzx   ecx, word ptr [r10+r9]
0x180024af2  sub     ax, 41h ; 'A'
0x180024af6  movzx   edx, word ptr [r10]
0x180024afa  add     cx, r15w
0x180024afe  cmp     ax, 19h
0x180024b02  movzx   eax, word ptr [r10]
0x180024b06  cmova   cx, [r10+r9]
0x180024b0c  add     dx, r15w
0x180024b10  sub     ax, 41h ; 'A'
0x180024b14  cmp     ax, 19h
0x180024b18  cmova   dx, [r10]
0x180024b1d  lea     r10, [r10+2]
0x180024b21  sub     r8, 1
0x180024b25  jz      short loc_180024B31
0x180024b27  test    cx, cx
0x180024b2a  jz      short loc_180024B31
0x180024b2c  cmp     cx, dx
0x180024b2f  jz      short loc_180024AE8
0x180024b31  cmp     cx, dx
0x180024b34  jnz     short loc_180024B42
0x180024b36  mov     dword ptr [r11], 0FFFEh
0x180024b3d  jmp     loc_180024AA4
0x180024b42  mov     rcx, rbx
0x180024b45  call    sub_1800248FC
0x180024b4a  test    eax, eax
0x180024b4c  jz      short loc_180024B61
0x180024b4e  call    sub_1801CDD94
0x180024b53  test    eax, eax
0x180024b55  jnz     short loc_180024B61
0x180024b57  mov     eax, 0FFFFE9B9h
0x180024b5c  jmp     loc_180024AA6
0x180024b61  mov     ecx, r13d
0x180024b64  call    sub_1800244C4
0x180024b69  xor     r9d, r9d
0x180024b6c  test    eax, eax
0x180024b6e  js      loc_180024C6F
0x180024b74  mov     rax, cs:qword_18025EA80
0x180024b7b  imul    rcx, r13, 0E08h
0x180024b82  mov     r12d, [rcx+rax+418h]
0x180024b8a  mov     r15, [rcx+rax+420h]
0x180024b92  test    r12d, r12d
0x180024b95  jz      short loc_180024BC7
0x180024b97  mov     r13d, edi
0x180024b9a  mov     r8, r13
0x180024b9d  mov     rdx, r15
0x180024ba0  mov     rcx, rbx
0x180024ba3  call    sub_180001818
0x180024ba8  xor     r9d, r9d
0x180024bab  test    eax, eax
0x180024bad  jnz     short loc_180024BB6
0x180024baf  cmp     [r15+r13*2], r9w
0x180024bb4  jz      short loc_180024BC2
0x180024bb6  inc     r14d
0x180024bb9  add     r15, 44h ; 'D'
0x180024bbd  cmp     r14d, r12d
0x180024bc0  jb      short loc_180024B9A
0x180024bc2  mov     r13d, [rsp+3A0h+var_370]
0x180024bc7  cmp     r14d, r12d
0x180024bca  jnz     loc_180024C83
0x180024bd0  lea     rax, aLotusWk1
0x180024bd7  mov     r14d, r9d
0x180024bda  mov     [rsp+3A0h+var_358], rax
0x180024bdf  lea     rsi, [rsp+3A0h+var_358]
0x180024be4  lea     rax, aLotusWk3
0x180024beb  mov     [rsp+3A0h+var_350], rax
0x180024bf0  lea     rax, aLotusWk4
0x180024bf7  mov     [rsp+3A0h+var_348], rax
0x180024bfc  lea     rax, aParadox3X
0x180024c03  mov     [rsp+3A0h+var_340], rax
0x180024c08  lea     rax, aParadox4X
0x180024c0f  mov     [rsp+3A0h+var_338], rax
0x180024c14  lea     rax, aParadox5X
0x180024c1b  mov     [rsp+3A0h+var_330], rax
0x180024c20  lea     rax, aParadox7X
0x180024c27  mov     [rsp+3A0h+var_328], rax
0x180024c2c  mov     rcx, [rsi]
0x180024c2f  test    rcx, rcx
0x180024c32  jz      short loc_180024C44
0x180024c34  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180024c38  inc     rdx
0x180024c3b  cmp     [rcx+rdx*2], r9w
0x180024c40  jnz     short loc_180024C38
0x180024c42  jmp     short loc_180024C47
0x180024c44  mov     rdx, r9
0x180024c47  mov     r9d, edi
0x180024c4a  mov     dword ptr [rsp+3A0h+var_380], 1
0x180024c52  mov     r8, rbx
0x180024c55  call    cs:Mso30Win32Client_12962
0x180024c5b  xor     r9d, r9d
0x180024c5e  test    eax, eax
0x180024c60  jnz     short loc_180024C79
0x180024c62  inc     r14d
0x180024c65  add     rsi, 8
0x180024c69  cmp     r14d, 7
0x180024c6d  jb      short loc_180024C2C
0x180024c6f  mov     eax, 0FFFFFBE0h
0x180024c74  jmp     loc_180024AA6
0x180024c79  mov     eax, 0FFFFF0A0h
0x180024c7e  jmp     loc_180024AA6
0x180024c83  mov     edx, r14d
0x180024c86  mov     ecx, r13d
0x180024c89  call    sub_180046434
0x180024c8e  or      r10, 0FFFFFFFFFFFFFFFFh
0x180024c92  lea     r8, qword_18025D9B0
0x180024c99  mov     rbx, rax
0x180024c9c  test    rax, rax
0x180024c9f  jnz     short loc_180024CF5
0x180024ca1  movsxd  rsi, cs:dword_18025D9A8
0x180024ca8  cmp     esi, r10d
0x180024cab  jz      short loc_180024CDB
0x180024cad  lea     rcx, [rsi+rsi*4]
0x180024cb1  xorps   xmm0, xmm0
0x180024cb4  mov     eax, [r8+rcx*8+20h]
0x180024cb9  mov     rdx, rsi
0x180024cbc  movups  xmmword ptr [r8+rcx*8], xmm0
0x180024cc1  mov     cs:dword_18025D9A8, eax
0x180024cc7  xor     eax, eax
0x180024cc9  movups  xmmword ptr [r8+rcx*8+10h], xmm0
0x180024ccf  mov     [r8+rcx*8+20h], rax
0x180024cd4  mov     [r8+rcx*8+20h], r10d
0x180024cd9  jmp     short loc_180024CDE
0x180024cdb  mov     rdx, r10
0x180024cde  cmp     esi, r10d
0x180024ce1  jnz     short loc_180024CED
0x180024ce3  mov     eax, 0FFFFFBABh
0x180024ce8  jmp     loc_180024AA6
0x180024ced  lea     rax, [rdx+rdx*4]
0x180024cf1  lea     rbx, [r8+rax*8]
0x180024cf5  cmp     [rbx+8], r9
0x180024cf9  jnz     loc_180024ED2
0x180024cff  mov     eax, 208h
0x180024d04  mov     [rsp+3A0h+var_368], r9
0x180024d09  mov     [rsp+3A0h+var_370], eax
0x180024d0d  cmp     [r15+22h], r9w
0x180024d12  jz      short loc_180024D80
0x180024d14  mov     edi, 64h ; 'd'
0x180024d19  lea     r8, aSoftwareMicros_0
0x180024d20  mov     edx, edi; SizeInWords
0x180024d22  lea     rcx, [rbp+2A0h+Destination]; Destination
0x180024d26  mov     r9, r10; MaxCount
0x180024d29  call    cs:wcsncpy_s
0x180024d2f  mov     r8d, edi
0x180024d32  lea     rdx, [rbp+2A0h+Destination]
0x180024d36  lea     rcx, [r15+22h]
0x180024d3a  call    cs:Mso20Win32Client_59137
0x180024d40  lea     rax, [rsp+3A0h+var_370]
0x180024d45  mov     rcx, 0FFFFFFFF80000002h
0x180024d4c  mov     [rsp+3A0h+var_378], rax
0x180024d51  lea     r8, aWin32
0x180024d58  lea     rax, [rbp+2A0h+var_250]
0x180024d5c  lea     rdx, [rbp+2A0h+Destination]
0x180024d60  mov     [rsp+3A0h+var_380], rax
0x180024d65  call    sub_18004A9BC
0x180024d6a  xor     r9d, r9d
0x180024d6d  test    eax, eax
0x180024d6f  jnz     short loc_180024D80
0x180024d71  mov     eax, [rsp+3A0h+var_370]
0x180024d75  cmp     [r15+22h], r9w
0x180024d7a  jz      short loc_180024D80
0x180024d7c  shr     eax, 1
0x180024d7e  jmp     short loc_180024D83
0x180024d80  mov     eax, r9d
0x180024d83  dec     eax
0x180024d85  cmp     eax, 102h
0x180024d8a  ja      loc_180024F18
0x180024d90  lea     rcx, [rbp+2A0h+var_250]
0x180024d94  call    sub_1801CE394
0x180024d99  mov     r15, rax
0x180024d9c  test    rax, rax
0x180024d9f  jnz     short loc_180024DD0
0x180024da1  cmp     cs:dword_18025EA74, eax
0x180024da7  jz      loc_180024C6F
0x180024dad  movsxd  rax, esi
0x180024db0  lea     rdx, qword_18025D9B0
0x180024db7  lea     rcx, [rax+rax*4]
0x180024dbb  mov     eax, cs:dword_18025D9A8
0x180024dc1  mov     [rdx+rcx*8+20h], eax
0x180024dc5  mov     cs:dword_18025D9A8, esi
0x180024dcb  jmp     loc_180024C6F
0x180024dd0  xor     edx, edx
0x180024dd2  test    r12d, r12d
0x180024dd5  jz      short loc_180024DF6
0x180024dd7  mov     ecx, r13d
0x180024dda  call    sub_180046434
0x180024ddf  test    rax, rax
0x180024de2  jz      short loc_180024DEF
0x180024de4  cmp     [rax+8], r15
0x180024de8  jnz     short loc_180024DEF
0x180024dea  cmp     [rax+1Ch], edx
0x180024ded  jz      short loc_180024DF6
0x180024def  inc     edx
0x180024df1  cmp     edx, r12d
0x180024df4  jb      short loc_180024DD7
0x180024df6  cmp     edx, r12d
0x180024df9  jnz     loc_180024E87
0x180024dff  mov     edx, 1; lpProcName
0x180024e04  mov     rcx, r15; hModule
0x180024e07  call    cs:GetProcAddress
0x180024e0d  test    rax, rax
0x180024e10  jnz     short loc_180024E19
0x180024e12  mov     edi, 0FFFFFC15h
0x180024e17  jmp     short loc_180024E80
0x180024e19  lea     rdx, [rsp+3A0h+var_368]
0x180024e1e  lea     rcx, off_1802250C0
0x180024e25  call    cs:__guard_dispatch_icall_fptr
0x180024e2b  mov     edi, eax
0x180024e2d  test    eax, eax
0x180024e2f  js      loc_180024EE1
0x180024e35  mov     rax, [rsp+3A0h+var_368]
0x180024e3a  test    byte ptr [rax], 20h
0x180024e3d  jz      short loc_180024E59
0x180024e3f  mov     rax, [rax+50h]
0x180024e43  lea     ecx, [r13+90h]
0x180024e4a  movsxd  rcx, ecx
  ... truncated ...
```
