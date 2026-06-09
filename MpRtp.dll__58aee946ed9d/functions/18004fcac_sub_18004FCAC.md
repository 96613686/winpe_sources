# sub_18004FCAC

- ea: `0x18004fcac`
- end: `0x180050377`
- name: `sub_18004FCAC`
- size: `1739`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18005e440`

## callees

- `0x180008780`
- `0x1800115a0`
- `0x1800115ec`
- `0x180017f40`
- `0x18003d734`
- `0x18003d758`
- `0x18003d810`
- `0x180048df4`
- `0x18004f2d0`
- `0x18004f3e8`
- `0x18004fcac`
- `0x180051010`
- `0x180052ea0`
- `0x18005332c`
- `0x1800533dc`
- `0x18005348c`
- `0x18005448c`
- `0x18009e050`
- `0x1800c2958`
- `0x1800c2f64`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800500a5`
- `KERNEL32!Sleep` at `0x1800500a5`
- `KERNEL32!FindStringOrdinal` at `0x18004fd40`
- `KERNEL32!FindStringOrdinal` at `0x18004fd40`
- `KERNEL32!ProcessIdToSessionId` at `0x180050154`
- `KERNEL32!ProcessIdToSessionId` at `0x180050154`
- `KERNEL32!CloseHandle` at `0x18004ff1e`
- `KERNEL32!CloseHandle` at `0x18004ff95`
- `KERNEL32!CloseHandle` at `0x18004ffcd`
- `KERNEL32!CloseHandle` at `0x1800500e0`
- `KERNEL32!CloseHandle` at `0x18005023c`
- `KERNEL32!CloseHandle` at `0x1800502ac`
- `KERNEL32!CloseHandle` at `0x1800502ed`
- `KERNEL32!CloseHandle` at `0x18004ff1e`
- `KERNEL32!CloseHandle` at `0x18004ff95`
- `KERNEL32!CloseHandle` at `0x18004ffcd`
- `KERNEL32!CloseHandle` at `0x1800500e0`
- `KERNEL32!CloseHandle` at `0x18005023c`
- `KERNEL32!CloseHandle` at `0x1800502ac`
- `KERNEL32!CloseHandle` at `0x1800502ed`
- `KERNEL32!GetLastError` at `0x180050170`
- `KERNEL32!GetLastError` at `0x180050170`

## string_xrefs

- `0x18005018f`: `MpDetoursCopyAccelerator.dll`
- `0x180050068`: `covrun64.dll`
- `0x18004fdaf`: `[RtpCopyAccelerator] Copy accelerator process launch failed with HRESULT %#lx.`
- `0x1800501b2`: `Injected copy acceleration detours dll to process %ls (%lu). hr: %#lx`

## pseudocode

```c
__int64 __fastcall sub_18004FCAC(__int64 a1, __int64 a2, const WCHAR *a3, char a4)
{
  int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // eax
  void *v19; // rcx
  char v20; // al
  void *v21; // rbx
  int v22; // eax
  char LastError; // al
  int v24; // edx
  int v25; // r8d
  int v26; // r9d
  unsigned int v27; // esi
  int v28; // eax
  char v29; // [rsp+30h] [rbp-A8h] BYREF
  signed int v30; // [rsp+34h] [rbp-A4h] BYREF
  char v31; // [rsp+38h] [rbp-A0h]
  int v32; // [rsp+3Ch] [rbp-9Ch] BYREF
  char v33; // [rsp+40h] [rbp-98h]
  const WCHAR *v34; // [rsp+48h] [rbp-90h]
  __int64 v35; // [rsp+50h] [rbp-88h]
  __int64 v36; // [rsp+58h] [rbp-80h]
  __int64 v37; // [rsp+60h] [rbp-78h]
  _BYTE *v38; // [rsp+68h] [rbp-70h]
  _BYTE v39[8]; // [rsp+78h] [rbp-60h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-58h] BYREF
  int v41; // [rsp+88h] [rbp-50h] BYREF
  DWORD pSessionId; // [rsp+8Ch] [rbp-4Ch] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-48h] BYREF

  v31 = a4;
  v34 = a3;
  if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 0x10) != 0 )
    sub_18003D734(*((_QWORD *)off_180119DF0 + 2), 116, &stru_1800EEB98);
  if ( FindStringOrdinal(0x200000u, a3, -1, L"explorer.exe", -1, 1) != -1 )
  {
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 4) != 0 )
      sub_18003D810(*((_QWORD *)off_180119DF0 + 2), 117, &stru_1800EEB98, a3);
    return 1;
  }
  v8 = sub_180051010(*(_QWORD *)(a1 + 232));
  v10 = v8;
  if ( v8 < 0 )
  {
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
      sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 118, &stru_1800EEB98, (unsigned int)v8);
    sub_180048DF4(L"[RtpCopyAccelerator] Copy accelerator process launch failed with HRESULT %#lx.", v10);
    return v10;
  }
  v39[0] = 0;
  LOBYTE(v9) = 1;
  v11 = sub_18005348C(a1, a2, v9, v39);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
      sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 119, &stru_1800EEB98, (unsigned int)v11);
    return v12;
  }
  if ( v39[0] )
    return 1;
  v35 = 0;
  v36 = a1;
  v37 = a2;
  v38 = v39;
  v32 = 0;
  v33 = 0;
  v13 = sub_18004F3E8(a1, a2, &v32);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
      sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 120, &stru_1800EEB98, (unsigned int)v13);
LABEL_41:
    sub_18005348C(a1, a2, 0, v39);
    return v14;
  }
  if ( BYTE1(v32) )
  {
LABEL_27:
    sub_18005348C(a1, a2, 0, v39);
    return 1;
  }
  hObject = 0;
  v15 = sub_180008780(&hObject, *(unsigned int *)(a2 + 8), a2, 1024);
  v14 = v15;
  if ( v15 < 0 )
  {
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
      sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 121, &stru_1800EEB98, (unsigned int)v15);
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_41;
  }
  v41 = 0;
  v17 = sub_18009E050(hObject, v16, &v41);
  v14 = v17;
  if ( v17 < 0 )
  {
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
      sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 122, &stru_1800EEB98, (unsigned int)v17);
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_41;
  }
  if ( (v41 & 1) != 0 )
  {
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_27;
  }
  v29 = 0;
  lpMem = 0;
  v18 = sub_1800C2F64(a2, (unsigned int)&v29, (unsigned int)off_180119E88, 7, (__int64)&lpMem);
  v30 = v18;
  v19 = off_180119DF0;
  if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 4) != 0 )
    sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 123, &stru_1800EEB98, v18);
  v20 = v29;
  v21 = lpMem;
  if ( HIBYTE(v32) && v29 && lpMem )
  {
    if ( !(unsigned int)sub_180017F40(lpMem, L"covrun64.dll") )
    {
      if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 4) != 0 )
        sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 124, &stru_1800EEB98, *(unsigned int *)(a2 + 8));
      Sleep(0x1F4u);
    }
    v20 = v29;
  }
  if ( v30 >= 0 && v20 )
  {
    sub_1800533DC(a1, a2);
    if ( v21 )
      sub_1800115EC(v21);
    if ( hObject )
      CloseHandle(hObject);
    sub_18005348C(a1, a2, 0, v39);
    return 1;
  }
  else
  {
    v30 = 5000;
    v22 = sub_18004F2D0(v19, &v30);
    if ( v22 < 0 && off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 2) != 0 )
      sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 125, &stru_1800EEB98, (unsigned int)v22);
    pSessionId = -1;
    if ( !ProcessIdToSessionId(*(_DWORD *)(a2 + 8), &pSessionId)
      && off_180119DF0 != (_UNKNOWN *)&off_180119DF0
      && (*((_BYTE *)off_180119DF0 + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      sub_18005448C(*((_QWORD *)off_180119DF0 + 2), v24, v25, (_DWORD)v34, LastError);
    }
    v30 = sub_1800C2958(a2, v30);
    sub_180048DF4(
      L"Injected copy acceleration detours dll to process %ls (%lu). hr: %#lx",
      v34,
      *(unsigned int *)(a2 + 8),
      (unsigned int)v30);
    LOBYTE(v26) = v31;
    sub_180052EA0(a1, (_DWORD)v34, v30, v26, pSessionId);
    if ( v30 >= 0 )
    {
      v28 = sub_18005332C(a1, a2);
      v30 = v28;
      if ( v28 >= 0 )
      {
        if ( v21 )
          sub_1800115EC(v21);
        if ( hObject )
          CloseHandle(hObject);
        sub_18005348C(a1, a2, 0, v39);
        return 0;
      }
      else
      {
        if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
          sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 128, &stru_1800EEB98, (unsigned int)v28);
        if ( v21 )
          sub_1800115EC(v21);
        if ( hObject )
          CloseHandle(hObject);
        sub_18005348C(a1, a2, 0, v39);
        return (unsigned int)v30;
      }
    }
    else
    {
      sub_1800533DC(a1, a2);
      if ( off_180119DF0 == (_UNKNOWN *)&off_180119DF0 )
      {
        v27 = v30;
      }
      else
      {
        v27 = v30;
        if ( (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
          sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 127, &stru_1800EEB98, (unsigned int)v30);
      }
      if ( v21 )
        sub_1800115EC(v21);
      if ( hObject )
        CloseHandle(hObject);
      sub_18005348C(a1, a2, 0, v39);
      return v27;
    }
  }
}

```

## disassembly

```asm
0x18004fcac  push    rbx
0x18004fcae  push    rsi
0x18004fcaf  push    rdi
0x18004fcb0  push    r12
0x18004fcb2  push    r13
0x18004fcb4  push    r14
0x18004fcb6  push    r15
0x18004fcb8  sub     rsp, 0A0h
0x18004fcbf  mov     rax, cs:__security_cookie
0x18004fcc6  xor     rax, rsp
0x18004fcc9  mov     [rsp+0D8h+var_40], rax
0x18004fcd1  mov     [rsp+0D8h+var_A0], r9b
0x18004fcd6  mov     rbx, r8
0x18004fcd9  mov     [rsp+0D8h+var_90], rbx
0x18004fcde  mov     r14, rdx
0x18004fce1  mov     r13, rcx
0x18004fce4  lea     r12, off_180119DF0
0x18004fceb  mov     rcx, cs:off_180119DF0
0x18004fcf2  cmp     rcx, r12
0x18004fcf5  jz      short loc_18004FD17
0x18004fcf7  test    byte ptr [rcx+1Ch], 10h
0x18004fcfb  jz      short loc_18004FD17
0x18004fcfd  mov     edx, 74h ; 't'
0x18004fd02  lea     r15, stru_1800EEB98
0x18004fd09  mov     r8, r15
0x18004fd0c  mov     rcx, [rcx+10h]
0x18004fd10  call    sub_18003D734
0x18004fd15  jmp     short loc_18004FD1E
0x18004fd17  lea     r15, stru_1800EEB98
0x18004fd1e  mov     esi, 1
0x18004fd23  mov     [rsp+0D8h+bIgnoreCase], esi; bIgnoreCase
0x18004fd27  or      edi, 0FFFFFFFFh
0x18004fd2a  mov     [rsp+0D8h+cchValue], edi; cchValue
0x18004fd2e  lea     r9, StringValue; "explorer.exe"
0x18004fd35  mov     r8d, edi; cchSource
0x18004fd38  mov     rdx, rbx; lpStringSource
0x18004fd3b  mov     ecx, 200000h; dwFindStringOrdinalFlags
0x18004fd40  call    cs:FindStringOrdinal
0x18004fd46  cmp     eax, edi
0x18004fd48  jz      short loc_18004FD75
0x18004fd4a  mov     rcx, cs:off_180119DF0
0x18004fd51  cmp     rcx, r12
0x18004fd54  jz      short loc_18004FD6E
0x18004fd56  test    byte ptr [rcx+1Ch], 4
0x18004fd5a  jz      short loc_18004FD6E
0x18004fd5c  lea     edx, [rsi+74h]
0x18004fd5f  mov     r9, rbx
0x18004fd62  mov     r8, r15
0x18004fd65  mov     rcx, [rcx+10h]
0x18004fd69  call    sub_18003D810
0x18004fd6e  mov     eax, esi
0x18004fd70  jmp     loc_180050354
0x18004fd75  mov     rcx, [r13+0E8h]
0x18004fd7c  call    sub_180051010
0x18004fd81  mov     ebx, eax
0x18004fd83  xor     edi, edi
0x18004fd85  test    eax, eax
0x18004fd87  jns     short loc_18004FDC2
0x18004fd89  mov     rcx, cs:off_180119DF0
0x18004fd90  cmp     rcx, r12
0x18004fd93  jz      short loc_18004FDAD
0x18004fd95  test    [rcx+1Ch], sil
0x18004fd99  jz      short loc_18004FDAD
0x18004fd9b  lea     edx, [rdi+76h]
0x18004fd9e  mov     r9d, eax
0x18004fda1  mov     r8, r15
0x18004fda4  mov     rcx, [rcx+10h]
0x18004fda8  call    sub_18003D758
0x18004fdad  mov     edx, ebx
0x18004fdaf  lea     rcx, aRtpcopyacceler_9; "[RtpCopyAccelerator] Copy accelerator p"...
0x18004fdb6  call    sub_180048DF4
0x18004fdbb  mov     eax, ebx
0x18004fdbd  jmp     loc_180050354
0x18004fdc2  mov     [rsp+0D8h+var_60], dil
0x18004fdc7  lea     r9, [rsp+0D8h+var_60]
0x18004fdcc  mov     r8b, sil
0x18004fdcf  mov     rdx, r14
0x18004fdd2  mov     rcx, r13
0x18004fdd5  call    sub_18005348C
0x18004fdda  mov     ebx, eax
0x18004fddc  test    eax, eax
0x18004fdde  jns     short loc_18004FE0D
0x18004fde0  mov     rcx, cs:off_180119DF0
0x18004fde7  cmp     rcx, r12
0x18004fdea  jz      short loc_18004FE06
0x18004fdec  test    [rcx+1Ch], sil
0x18004fdf0  jz      short loc_18004FE06
0x18004fdf2  mov     edx, 77h ; 'w'
0x18004fdf7  mov     r9d, eax
0x18004fdfa  mov     r8, r15
0x18004fdfd  mov     rcx, [rcx+10h]
0x18004fe01  call    sub_18003D758
0x18004fe06  mov     eax, ebx
0x18004fe08  jmp     loc_180050354
0x18004fe0d  cmp     [rsp+0D8h+var_60], dil
0x18004fe12  jz      short loc_18004FE1B
0x18004fe14  mov     eax, esi
0x18004fe16  jmp     loc_180050354
0x18004fe1b  xorps   xmm0, xmm0
0x18004fe1e  movups  [rsp+0D8h+var_88], xmm0
0x18004fe23  movups  [rsp+0D8h+var_78], xmm0
0x18004fe28  mov     byte ptr [rsp+0D8h+var_88], dil
0x18004fe2d  mov     qword ptr [rsp+0D8h+var_88+8], r13
0x18004fe32  mov     qword ptr [rsp+0D8h+var_78], r14
0x18004fe37  lea     rax, [rsp+0D8h+var_60]
0x18004fe3c  mov     qword ptr [rsp+0D8h+var_78+8], rax
0x18004fe41  mov     [rsp+0D8h+var_9C], edi
0x18004fe45  mov     [rsp+0D8h+var_98], dil
0x18004fe4a  lea     r8, [rsp+0D8h+var_9C]
0x18004fe4f  mov     rdx, r14
0x18004fe52  mov     rcx, r13
0x18004fe55  call    sub_18004F3E8
0x18004fe5a  mov     ebx, eax
0x18004fe5c  test    eax, eax
0x18004fe5e  jns     short loc_18004FEA1
0x18004fe60  mov     rcx, cs:off_180119DF0
0x18004fe67  cmp     rcx, r12
0x18004fe6a  jz      short loc_18004FE87
0x18004fe6c  test    [rcx+1Ch], sil
0x18004fe70  jz      short loc_18004FE87
0x18004fe72  mov     edx, 78h ; 'x'
0x18004fe77  mov     r9d, eax
0x18004fe7a  mov     r8, r15
0x18004fe7d  mov     rcx, [rcx+10h]
0x18004fe81  call    sub_18003D758
0x18004fe86  nop
0x18004fe87  lea     r9, [rsp+0D8h+var_60]
0x18004fe8c  xor     r8d, r8d
0x18004fe8f  mov     rdx, r14
0x18004fe92  mov     rcx, r13
0x18004fe95  call    sub_18005348C
0x18004fe9a  mov     eax, ebx
0x18004fe9c  jmp     loc_180050354
0x18004fea1  cmp     byte ptr [rsp+0D8h+var_9C+1], dil
0x18004fea6  jz      short loc_18004FEC2
0x18004fea8  lea     r9, [rsp+0D8h+var_60]
0x18004fead  xor     r8d, r8d
0x18004feb0  mov     rdx, r14
0x18004feb3  mov     rcx, r13
0x18004feb6  call    sub_18005348C
0x18004febb  mov     eax, esi
0x18004febd  jmp     loc_180050354
0x18004fec2  mov     [rsp+0D8h+hObject], rdi
0x18004feca  mov     r9d, 400h
0x18004fed0  mov     r8, r14
0x18004fed3  mov     edx, [r14+8]
0x18004fed7  lea     rcx, [rsp+0D8h+hObject]
0x18004fedf  call    sub_180008780
0x18004fee4  mov     ebx, eax
0x18004fee6  test    eax, eax
0x18004fee8  jns     short loc_18004FF3F
0x18004feea  mov     rcx, cs:off_180119DF0
0x18004fef1  cmp     rcx, r12
0x18004fef4  jz      short loc_18004FF11
0x18004fef6  test    [rcx+1Ch], sil
0x18004fefa  jz      short loc_18004FF11
0x18004fefc  mov     edx, 79h ; 'y'
0x18004ff01  mov     r9d, eax
0x18004ff04  mov     r8, r15
0x18004ff07  mov     rcx, [rcx+10h]
0x18004ff0b  call    sub_18003D758
0x18004ff10  nop
0x18004ff11  mov     rcx, [rsp+0D8h+hObject]; hObject
0x18004ff19  test    rcx, rcx
0x18004ff1c  jz      short loc_18004FF25
0x18004ff1e  call    cs:CloseHandle
0x18004ff24  nop
0x18004ff25  lea     r9, [rsp+0D8h+var_60]
0x18004ff2a  xor     r8d, r8d
0x18004ff2d  mov     rdx, r14
0x18004ff30  mov     rcx, r13
0x18004ff33  call    sub_18005348C
0x18004ff38  mov     eax, ebx
0x18004ff3a  jmp     loc_180050354
0x18004ff3f  mov     [rsp+0D8h+var_50], edi
0x18004ff46  lea     r8, [rsp+0D8h+var_50]
0x18004ff4e  mov     rcx, [rsp+0D8h+hObject]
0x18004ff56  call    sub_18009E050
0x18004ff5b  mov     ebx, eax
0x18004ff5d  test    eax, eax
0x18004ff5f  jns     short loc_18004FFB6
0x18004ff61  mov     rcx, cs:off_180119DF0
0x18004ff68  cmp     rcx, r12
0x18004ff6b  jz      short loc_18004FF88
0x18004ff6d  test    [rcx+1Ch], sil
0x18004ff71  jz      short loc_18004FF88
0x18004ff73  mov     edx, 7Ah ; 'z'
0x18004ff78  mov     r9d, eax
0x18004ff7b  mov     r8, r15
0x18004ff7e  mov     rcx, [rcx+10h]
0x18004ff82  call    sub_18003D758
0x18004ff87  nop
0x18004ff88  mov     rcx, [rsp+0D8h+hObject]; hObject
0x18004ff90  test    rcx, rcx
0x18004ff93  jz      short loc_18004FF9C
0x18004ff95  call    cs:CloseHandle
0x18004ff9b  nop
0x18004ff9c  lea     r9, [rsp+0D8h+var_60]
0x18004ffa1  xor     r8d, r8d
0x18004ffa4  mov     rdx, r14
0x18004ffa7  mov     rcx, r13
0x18004ffaa  call    sub_18005348C
0x18004ffaf  mov     eax, ebx
0x18004ffb1  jmp     loc_180050354
0x18004ffb6  test    byte ptr [rsp+0D8h+var_50], sil
0x18004ffbe  jz      short loc_18004FFEE
0x18004ffc0  mov     rcx, [rsp+0D8h+hObject]; hObject
0x18004ffc8  test    rcx, rcx
0x18004ffcb  jz      short loc_18004FFD4
0x18004ffcd  call    cs:CloseHandle
0x18004ffd3  nop
0x18004ffd4  lea     r9, [rsp+0D8h+var_60]
0x18004ffd9  xor     r8d, r8d
0x18004ffdc  mov     rdx, r14
0x18004ffdf  mov     rcx, r13
0x18004ffe2  call    sub_18005348C
0x18004ffe7  mov     eax, esi
0x18004ffe9  jmp     loc_180050354
0x18004ffee  mov     [rsp+0D8h+var_A8], dil
0x18004fff3  mov     [rsp+0D8h+lpMem], rdi
0x18004fffb  lea     rax, [rsp+0D8h+lpMem]
0x180050003  mov     qword ptr [rsp+0D8h+cchValue], rax
0x180050008  mov     r9d, 7
0x18005000e  lea     r8, off_180119E88; "MpDetoursCopyAccelerator.dll"
0x180050015  lea     rdx, [rsp+0D8h+var_A8]
0x18005001a  mov     rcx, r14
0x18005001d  call    sub_1800C2F64
0x180050022  mov     [rsp+0D8h+var_A4], eax
0x180050026  mov     rcx, cs:off_180119DF0
0x18005002d  cmp     rcx, r12
0x180050030  jz      short loc_18005004C
0x180050032  test    byte ptr [rcx+1Ch], 4
0x180050036  jz      short loc_18005004C
0x180050038  mov     edx, 7Bh ; '{'
0x18005003d  mov     r9d, eax
0x180050040  mov     r8, r15
0x180050043  mov     rcx, [rcx+10h]
0x180050047  call    sub_18003D758
0x18005004c  mov     al, [rsp+0D8h+var_A8]
0x180050050  mov     rbx, [rsp+0D8h+lpMem]
0x180050058  cmp     byte ptr [rsp+0D8h+var_9C+3], dil
0x18005005d  jz      short loc_1800500AF
0x18005005f  test    al, al
0x180050061  jz      short loc_1800500AF
0x180050063  test    rbx, rbx
0x180050066  jz      short loc_1800500AF
0x180050068  lea     rdx, aCovrun64Dll; "covrun64.dll"
0x18005006f  mov     rcx, rbx
0x180050072  call    sub_180017F40
0x180050077  test    eax, eax
0x180050079  jnz     short loc_1800500AB
0x18005007b  mov     rcx, cs:off_180119DF0
0x180050082  cmp     rcx, r12
0x180050085  jz      short loc_1800500A0
0x180050087  test    byte ptr [rcx+1Ch], 4
0x18005008b  jz      short loc_1800500A0
0x18005008d  lea     edx, [rax+7Ch]
0x180050090  mov     r9d, [r14+8]
0x180050094  mov     r8, r15
0x180050097  mov     rcx, [rcx+10h]
0x18005009b  call    sub_18003D758
0x1800500a0  mov     ecx, 1F4h; dwMilliseconds
0x1800500a5  call    cs:Sleep
0x1800500ab  mov     al, [rsp+0D8h+var_A8]
0x1800500af  cmp     [rsp+0D8h+var_A4], edi
0x1800500b3  jl      short loc_180050101
0x1800500b5  test    al, al
0x1800500b7  jz      short loc_180050101
0x1800500b9  mov     rdx, r14
0x1800500bc  mov     rcx, r13
0x1800500bf  call    sub_1800533DC
0x1800500c4  nop
0x1800500c5  test    rbx, rbx
0x1800500c8  jz      short loc_1800500D3
0x1800500ca  mov     rcx, rbx; lpMem
0x1800500cd  call    sub_1800115EC
0x1800500d2  nop
0x1800500d3  mov     rcx, [rsp+0D8h+hObject]; hObject
0x1800500db  test    rcx, rcx
0x1800500de  jz      short loc_1800500E7
0x1800500e0  call    cs:CloseHandle
0x1800500e6  nop
0x1800500e7  lea     r9, [rsp+0D8h+var_60]
0x1800500ec  xor     r8d, r8d
0x1800500ef  mov     rdx, r14
0x1800500f2  mov     rcx, r13
0x1800500f5  call    sub_18005348C
0x1800500fa  mov     eax, esi
0x1800500fc  jmp     loc_180050354
0x180050101  mov     [rsp+0D8h+var_A4], 1388h
0x180050109  lea     rdx, [rsp+0D8h+var_A4]
0x18005010e  call    sub_18004F2D0
0x180050113  test    eax, eax
0x180050115  jns     short loc_18005013D
0x180050117  mov     rcx, cs:off_180119DF0
0x18005011e  cmp     rcx, r12
0x180050121  jz      short loc_18005013D
0x180050123  test    byte ptr [rcx+1Ch], 2
0x180050127  jz      short loc_18005013D
0x180050129  mov     edx, 7Dh ; '}'
  ... truncated ...
```
