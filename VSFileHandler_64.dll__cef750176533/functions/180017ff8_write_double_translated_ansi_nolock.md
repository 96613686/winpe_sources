# write_double_translated_ansi_nolock

- ea: `0x180017ff8`
- end: `0x1800184e4`
- name: `write_double_translated_ansi_nolock`
- size: `1260`
- prototype: `_QWORD *__fastcall(_QWORD *, int, const char *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x180018960`

## callees

- `0x180007700`
- `0x18000c5a4`
- `0x180010810`
- `0x1800138a4`
- `0x180014700`
- `0x180014d4c`
- `0x180017ff8`
- `0x1800245e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018472`
- `KERNEL32!GetLastError` at `0x1800184d2`
- `KERNEL32!GetLastError` at `0x180018472`
- `KERNEL32!GetLastError` at `0x1800184d2`
- `KERNEL32!WriteFile` at `0x18001831e`
- `KERNEL32!WriteFile` at `0x180018370`
- `KERNEL32!WriteFile` at `0x18001831e`
- `KERNEL32!WriteFile` at `0x180018370`
- `KERNEL32!GetConsoleOutputCP` at `0x180018067`
- `KERNEL32!GetConsoleOutputCP` at `0x180018067`

## pseudocode

```c
_QWORD *__fastcall write_double_translated_ansi_nolock(_QWORD *a1, int a2, const char *a3, int a4)
{
  __int64 v4; // rsi
  unsigned __int64 v6; // r13
  __int64 v7; // r12
  __int64 v8; // r14
  int v9; // ebx
  const char *v10; // rdi
  int v11; // edx
  int v12; // ecx
  __int64 v13; // rax
  const char *v14; // rsi
  __int64 v15; // rax
  const char **v16; // r15
  int v17; // edx
  __int64 v18; // r9
  __int64 i; // rsi
  __int64 v20; // r8
  int v21; // r15d
  int v22; // r13d
  __int64 v23; // rdx
  __int64 v24; // r9
  _BYTE *v25; // rcx
  __int64 j; // rdx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rsi
  const char **v31; // rbx
  __int64 v32; // rdx
  char v33; // cl
  char v34; // al
  const char *v35; // rdx
  bool v36; // zf
  DWORD v37; // eax
  DWORD v38; // esi
  int v39; // edx
  const char *v40; // rdi
  char v41; // al
  __int64 v42; // rcx
  int v43; // ebx
  int v44; // r9d
  __int64 v45; // r8
  __int64 v46; // r13
  __int64 v47; // r10
  char v48; // al
  __int64 v49; // rcx
  char v50; // al
  __int64 v51; // rcx
  _QWORD *result; // rax
  struct _Mbstatet *lpOverlapped; // [rsp+20h] [rbp-B9h]
  int v54; // [rsp+40h] [rbp-99h]
  __int16 v55; // [rsp+44h] [rbp-95h] BYREF
  wchar_t DstCh[2]; // [rsp+48h] [rbp-91h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-8Dh] BYREF
  _QWORD v58[3]; // [rsp+50h] [rbp-89h] BYREF
  char v59; // [rsp+68h] [rbp-71h]
  __int64 v60; // [rsp+70h] [rbp-69h]
  UINT ConsoleOutputCP; // [rsp+80h] [rbp-59h]
  int v62; // [rsp+84h] [rbp-55h]
  unsigned __int64 v63; // [rsp+88h] [rbp-51h]
  HANDLE hFile; // [rsp+90h] [rbp-49h]
  unsigned __int64 v65; // [rsp+98h] [rbp-41h] BYREF
  wchar_t v66[4]; // [rsp+A0h] [rbp-39h] BYREF
  unsigned __int64 v67; // [rsp+A8h] [rbp-31h] BYREF
  wchar_t v68[4]; // [rsp+B0h] [rbp-29h] BYREF
  const char *v69; // [rsp+B8h] [rbp-21h]
  __int64 v70; // [rsp+C0h] [rbp-19h]
  __int64 v71; // [rsp+C8h] [rbp-11h]
  _QWORD *v72; // [rsp+D0h] [rbp-9h]
  _BYTE v73[8]; // [rsp+D8h] [rbp-1h] BYREF
  _BYTE v74[8]; // [rsp+E0h] [rbp+7h] BYREF
  CHAR Buffer[8]; // [rsp+E8h] [rbp+Fh] BYREF

  v4 = a2;
  v72 = a1;
  v71 = a2;
  v6 = (unsigned __int64)&a3[a4];
  v69 = a3;
  v63 = v6;
  v7 = (__int64)a2 >> 6;
  v8 = 9LL * (a2 & 0x3F);
  hFile = *(HANDLE *)(_pioinfo[v7] + 72LL * (a2 & 0x3F) + 40);
  ConsoleOutputCP = GetConsoleOutputCP();
  _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)v58, 0);
  v60 = 0;
  v9 = 0;
  v10 = a3;
  v11 = *(_DWORD *)(v58[1] + 12LL);
  v12 = 0;
  v54 = 0;
  v62 = v11;
  if ( (unsigned __int64)a3 >= v6 )
    goto LABEL_53;
  v13 = v4;
  v14 = a3;
  v15 = v13 >> 6;
  v70 = v15;
  while ( 1 )
  {
    LODWORD(v16) = 1;
    LOBYTE(v55) = *v10;
    *(_DWORD *)DstCh = 0;
    if ( v11 != 65001 )
    {
      v32 = _pioinfo[v7];
      v33 = *(_BYTE *)(v32 + 8 * v8 + 61);
      if ( (v33 & 4) != 0 )
      {
        v74[0] = *(_BYTE *)(v32 + 8 * v8 + 62);
        v34 = *v10;
        *(_BYTE *)(v32 + 8 * v8 + 61) = v33 & 0xFB;
        v35 = v74;
        v74[1] = v34;
      }
      else
      {
        if ( (_pctype_func()[*(unsigned __int8 *)v10] & 0x8000u) == 0 )
        {
          if ( mbtowc(DstCh, v10, 1u) == -1 )
            goto LABEL_51;
          goto LABEL_28;
        }
        if ( (unsigned __int64)++v14 >= v6 )
        {
          v50 = *v10;
          v51 = _pioinfo[v7];
          HIDWORD(v60) = v9 + 1;
          *(_BYTE *)(v51 + 8 * v8 + 62) = v50;
          *(_BYTE *)(_pioinfo[v7] + 8 * v8 + 61) |= 4u;
          v36 = v59 == 0;
          goto LABEL_48;
        }
        v35 = v10;
      }
      if ( mbtowc(DstCh, v35, 2u) == -1 )
        goto LABEL_26;
      goto LABEL_28;
    }
    v17 = 0;
    v18 = _pioinfo[v15];
    for ( i = 0; i < 5; ++i )
    {
      if ( !*(_BYTE *)(v18 + 8 * v8 + i + 62) )
        break;
      ++v17;
    }
    if ( i > 0 )
    {
      v20 = v63 - (_QWORD)v10;
      v21 = *((char *)lookuptrailbytes + *(unsigned __int8 *)(_pioinfo[v7] + 8 * v8 + 62)) + 1;
      v22 = v21 - v17;
      if ( v21 - v17 <= (__int64)(v63 - (_QWORD)v10) )
      {
        v23 = 0;
        v24 = v18 - (_QWORD)v73;
        do
        {
          v25 = &v73[v23++];
          *v25 = v25[8 * v8 + 62 + v24];
        }
        while ( v23 < i );
        if ( v22 > 0 )
          memmove(&v73[i], v10, v22);
        for ( j = 0; j < i; ++j )
        {
          v27 = j + _pioinfo[v7];
          *(_BYTE *)(v27 + 8 * v8 + 62) = 0;
        }
        v65 = 0;
        *(_QWORD *)v66 = v73;
        v16 = (const char **)((unsigned int)(v21 == 4) + 1);
        if ( __crt_mbstring::__mbsrtowcs_utf8((__crt_mbstring *)DstCh, v66, v16, (unsigned __int64)&v65, lpOverlapped) != -1 )
        {
          v28 = v22 - 1;
          v6 = v63;
          v14 = &v10[v28];
          goto LABEL_28;
        }
LABEL_26:
        v36 = v59 == 0;
LABEL_48:
        v12 = v54;
        goto LABEL_54;
      }
      v39 = 0;
      if ( v20 > 0 )
      {
        v40 = &v10[-i];
        do
        {
          v41 = v40[i];
          ++v39;
          v42 = i + _pioinfo[v7];
          ++i;
          *(_BYTE *)(v42 + 8 * v8 + 62) = v41;
        }
        while ( v39 < v20 );
        v9 = HIDWORD(v60);
      }
      v43 = v20 + v9;
LABEL_46:
      HIDWORD(v60) = v43;
LABEL_47:
      v36 = v59 == 0;
      goto LABEL_48;
    }
    v29 = v6 - (_QWORD)v10;
    v30 = *((char *)lookuptrailbytes + *(unsigned __int8 *)v10);
    if ( (int)v30 + 1 > (__int64)(v6 - (_QWORD)v10) )
    {
      v44 = 0;
      if ( v29 > 0 )
      {
        v45 = 0;
        v46 = v71 & 0x3F;
        v47 = v71 >> 6;
        do
        {
          v48 = v10[v45];
          ++v44;
          v49 = v45 + _pioinfo[v47];
          ++v45;
          *(_BYTE *)(v49 + 72 * v46 + 62) = v48;
        }
        while ( v44 < v29 );
      }
      v43 = v29 + v9;
      goto LABEL_46;
    }
    v67 = 0;
    *(_QWORD *)v68 = v10;
    v31 = (const char **)((unsigned int)((_DWORD)v30 == 3) + 1);
    if ( __crt_mbstring::__mbsrtowcs_utf8((__crt_mbstring *)DstCh, v68, v31, (unsigned __int64)&v67, lpOverlapped) == -1 )
      goto LABEL_26;
    v14 = &v10[v30];
    LODWORD(v16) = (_DWORD)v31;
LABEL_28:
    v10 = v14 + 1;
    v37 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, DstCh, (int)v16, Buffer, 5, 0, 0);
    v38 = v37;
    if ( !v37 )
      goto LABEL_58;
    if ( !WriteFile(hFile, Buffer, v37, &NumberOfBytesWritten, 0) )
      break;
    v9 = v54 + (_DWORD)v10 - (_DWORD)v69;
    HIDWORD(v60) = v9;
    if ( NumberOfBytesWritten < v38 )
      goto LABEL_47;
    if ( (_BYTE)v55 == 10 )
    {
      v55 = 13;
      if ( !WriteFile(hFile, &v55, 1u, &NumberOfBytesWritten, 0) )
      {
        LODWORD(v60) = GetLastError();
LABEL_51:
        v12 = v54;
        v36 = v59 == 0;
        goto LABEL_54;
      }
      if ( !NumberOfBytesWritten )
        goto LABEL_47;
      ++v9;
      ++v54;
      HIDWORD(v60) = v9;
    }
    v14 = v10;
    if ( (unsigned __int64)v10 >= v6 )
    {
      v12 = v54;
LABEL_53:
      v36 = v59 == 0;
      goto LABEL_54;
    }
    v15 = v70;
    v11 = v62;
  }
  LODWORD(v60) = GetLastError();
LABEL_58:
  v12 = v54;
  v36 = v59 == 0;
LABEL_54:
  if ( !v36 )
    *(_DWORD *)(v58[0] + 936LL) &= ~2u;
  result = v72;
  *v72 = v60;
  *((_DWORD *)result + 2) = v12;
  return result;
}

```

## disassembly

```asm
0x180017ff8  mov     [rsp-8+arg_0], rbx
0x180017ffd  push    rbp
0x180017ffe  push    rsi
0x180017fff  push    rdi
0x180018000  push    r12
0x180018002  push    r13
0x180018004  push    r14
0x180018006  push    r15
0x180018008  lea     rbp, [rsp-27h]
0x18001800d  sub     rsp, 100h
0x180018014  mov     rax, cs:__security_cookie
0x18001801b  xor     rax, rsp
0x18001801e  mov     [rbp+57h+var_40], rax
0x180018022  movsxd  rsi, edx
0x180018025  mov     r15, r8
0x180018028  mov     rax, rsi
0x18001802b  mov     [rbp+57h+var_60], rcx
0x18001802f  mov     [rbp+57h+var_68], rax
0x180018033  lea     rcx, cs:180000000h
0x18001803a  and     eax, 3Fh
0x18001803d  mov     r13d, r9d
0x180018040  add     r13, r8
0x180018043  mov     [rbp+57h+var_78], r8
0x180018047  mov     r12, rsi
0x18001804a  mov     [rbp+57h+var_A8], r13
0x18001804e  sar     r12, 6
0x180018052  lea     r14, [rax+rax*8]
0x180018056  mov     rax, rva __pioinfo[rcx+r12*8]
0x18001805e  mov     rax, [rax+r14*8+28h]
0x180018063  mov     [rbp+57h+hFile], rax
0x180018067  call    cs:__imp_GetConsoleOutputCP
0x18001806d  xor     edx, edx; struct __crt_locale_pointers *
0x18001806f  lea     rcx, [rsp+130h+var_E0]; this
0x180018074  mov     [rbp+57h+var_B0], eax
0x180018077  call    ??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z; _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)
0x18001807c  mov     rcx, [rsp+130h+var_D8]
0x180018081  xor     r11d, r11d
0x180018084  mov     dword ptr [rbp+57h+var_C0], r11d
0x180018088  mov     ebx, r11d
0x18001808b  mov     dword ptr [rbp+57h+var_C0+4], ebx
0x18001808e  mov     rdi, r15
0x180018091  mov     edx, [rcx+0Ch]
0x180018094  mov     ecx, r11d
0x180018097  mov     [rsp+130h+var_F0], ecx
0x18001809b  mov     [rbp+57h+var_AC], edx
0x18001809e  cmp     r15, r13
0x1800180a1  jnb     loc_180018489
0x1800180a7  mov     rax, rsi
0x1800180aa  mov     rsi, r15
0x1800180ad  sar     rax, 6
0x1800180b1  mov     [rbp+57h+var_70], rax
0x1800180b5  mov     cl, [rdi]
0x1800180b7  mov     r15d, 1
0x1800180bd  mov     byte ptr [rsp+130h+var_EC], cl
0x1800180c1  mov     dword ptr [rsp+130h+DstCh], r11d
0x1800180c6  cmp     edx, 0FDE9h
0x1800180cc  jnz     loc_180018242
0x1800180d2  lea     r15, cs:180000000h
0x1800180d9  mov     edx, r11d
0x1800180dc  mov     r9, rva __pioinfo[r15+rax*8]
0x1800180e4  mov     rsi, r11
0x1800180e7  lea     rax, [r9+r14*8]
0x1800180eb  cmp     [rax+rsi+3Eh], r11b
0x1800180f0  jz      short loc_1800180FD
0x1800180f2  inc     edx
0x1800180f4  inc     rsi
0x1800180f7  cmp     rsi, 5
0x1800180fb  jl      short loc_1800180EB
0x1800180fd  test    rsi, rsi
0x180018100  jle     loc_1800181E6
0x180018106  mov     rax, rva __pioinfo[r15+r12*8]
0x18001810e  mov     r8, [rbp+57h+var_A8]
0x180018112  sub     r8, rdi
0x180018115  movzx   ecx, byte ptr [rax+r14*8+3Eh]
0x18001811b  movsx   r15d, byte ptr [rcx+r15+3D950h]
0x180018124  inc     r15d
0x180018127  mov     r13d, r15d
0x18001812a  sub     r13d, edx
0x18001812d  movsxd  r10, r13d
0x180018130  cmp     r10, r8
0x180018133  jg      loc_1800183B1
0x180018139  lea     rax, [rbp+57h+var_58]
0x18001813d  mov     rdx, r11
0x180018140  sub     r9, rax
0x180018143  lea     r8, [r9+r14*8]
0x180018147  lea     rcx, [rbp+57h+var_58]
0x18001814b  add     rcx, rdx
0x18001814e  inc     rdx
0x180018151  mov     al, [rcx+r8+3Eh]
0x180018156  mov     [rcx], al
0x180018158  cmp     rdx, rsi
0x18001815b  jl      short loc_180018147
0x18001815d  test    r13d, r13d
0x180018160  jle     short loc_180018177
0x180018162  lea     rcx, [rbp+57h+var_58]
0x180018166  mov     r8, r10; Size
0x180018169  add     rcx, rsi; void *
0x18001816c  mov     rdx, rdi; Src
0x18001816f  call    memmove
0x180018174  xor     r11d, r11d
0x180018177  mov     rdx, r11
0x18001817a  lea     r8, cs:180000000h
0x180018181  mov     rcx, rva __pioinfo[r8+r12*8]
0x180018189  add     rcx, rdx
0x18001818c  inc     rdx
0x18001818f  mov     [rcx+r14*8+3Eh], r11b
0x180018194  cmp     rdx, rsi
0x180018197  jl      short loc_180018181
0x180018199  lea     rax, [rbp+57h+var_58]
0x18001819d  mov     [rbp+57h+var_98], r11
0x1800181a1  mov     qword ptr [rbp+57h+var_90], rax
0x1800181a5  lea     r9, [rbp+57h+var_98]; unsigned __int64
0x1800181a9  mov     eax, r11d
0x1800181ac  lea     rdx, [rbp+57h+var_90]; wchar_t *
0x1800181b0  cmp     r15d, 4
0x1800181b4  lea     rcx, [rsp+130h+DstCh]; this
0x1800181b9  setz    al
0x1800181bc  inc     eax
0x1800181be  mov     r8d, eax; char **
0x1800181c1  mov     r15d, eax
0x1800181c4  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *)
0x1800181c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800181cd  jz      loc_1800182AA
0x1800181d3  lea     eax, [r13-1]
0x1800181d7  mov     r13, [rbp+57h+var_A8]
0x1800181db  movsxd  rsi, eax
0x1800181de  add     rsi, rdi
0x1800181e1  jmp     loc_1800182CC
0x1800181e6  movzx   eax, byte ptr [rdi]
0x1800181e9  mov     rdx, r13
0x1800181ec  sub     rdx, rdi
0x1800181ef  movsx   rsi, byte ptr [rax+r15+3D950h]
0x1800181f8  lea     ecx, [rsi+1]
0x1800181fb  movsxd  rax, ecx
0x1800181fe  cmp     rax, rdx
0x180018201  jg      loc_1800183EB
0x180018207  cmp     ecx, 4
0x18001820a  mov     [rbp+57h+var_88], r11
0x18001820e  mov     eax, r11d
0x180018211  mov     qword ptr [rbp+57h+var_80], rdi
0x180018215  setz    al
0x180018218  lea     r9, [rbp+57h+var_88]; unsigned __int64
0x18001821c  inc     eax
0x18001821e  lea     rdx, [rbp+57h+var_80]; wchar_t *
0x180018222  mov     r8d, eax; char **
0x180018225  lea     rcx, [rsp+130h+DstCh]; this
0x18001822a  mov     ebx, eax
0x18001822c  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *)
0x180018231  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018235  jz      short loc_1800182AA
0x180018237  add     rsi, rdi
0x18001823a  mov     r15d, ebx
0x18001823d  jmp     loc_1800182CC
0x180018242  lea     rax, cs:180000000h
0x180018249  mov     rdx, rva __pioinfo[rax+r12*8]
0x180018251  mov     cl, [rdx+r14*8+3Dh]
0x180018256  test    cl, 4
0x180018259  jz      short loc_180018276
0x18001825b  mov     al, [rdx+r14*8+3Eh]
0x180018260  and     cl, 0FBh
0x180018263  mov     [rbp+57h+var_50], al
0x180018266  mov     al, [rdi]
0x180018268  mov     [rdx+r14*8+3Dh], cl
0x18001826d  lea     rdx, [rbp+57h+var_50]
0x180018271  mov     [rbp+57h+var_4F], al
0x180018274  jmp     short loc_180018295
0x180018276  call    __pctype_func
0x18001827b  movzx   ecx, byte ptr [rdi]
0x18001827e  xor     edx, edx
0x180018280  cmp     [rax+rcx*2], dx
0x180018284  jge     short loc_1800182B3
0x180018286  inc     rsi
0x180018289  cmp     rsi, r13
0x18001828c  jnb     loc_180018444
0x180018292  mov     rdx, rdi; SrcCh
0x180018295  mov     r8d, 2; SrcSizeInBytes
0x18001829b  lea     rcx, [rsp+130h+DstCh]; DstCh
0x1800182a0  call    mbtowc
0x1800182a5  cmp     eax, 0FFFFFFFFh
0x1800182a8  jnz     short loc_1800182CC
0x1800182aa  cmp     [rbp+57h+var_C8], 0
0x1800182ae  jmp     loc_18001843E
0x1800182b3  mov     r8, r15; SrcSizeInBytes
0x1800182b6  lea     rcx, [rsp+130h+DstCh]; DstCh
0x1800182bb  mov     rdx, rdi; SrcCh
0x1800182be  call    mbtowc
0x1800182c3  cmp     eax, 0FFFFFFFFh
0x1800182c6  jz      loc_18001847B
0x1800182cc  mov     ecx, [rbp+57h+var_B0]
0x1800182cf  lea     rax, [rbp+57h+Buffer]
0x1800182d3  xor     ebx, ebx
0x1800182d5  lea     r8, [rsp+130h+DstCh]
0x1800182da  mov     [rsp+130h+var_F8], rbx
0x1800182df  lea     rdi, [rsi+1]
0x1800182e3  mov     [rsp+130h+var_100], rbx
0x1800182e8  mov     r9d, r15d
0x1800182eb  mov     [rsp+130h+var_108], 5
0x1800182f3  xor     edx, edx
0x1800182f5  mov     [rsp+130h+lpOverlapped], rax
0x1800182fa  call    __acrt_WideCharToMultiByte
0x1800182ff  mov     esi, eax
0x180018301  test    eax, eax
0x180018303  jz      loc_1800184DB
0x180018309  mov     rcx, [rbp+57h+hFile]; hFile
0x18001830d  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180018312  mov     r8d, eax; nNumberOfBytesToWrite
0x180018315  mov     [rsp+130h+lpOverlapped], rbx; lpOverlapped
0x18001831a  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18001831e  call    cs:__imp_WriteFile
0x180018324  xor     r11d, r11d
0x180018327  test    eax, eax
0x180018329  jz      loc_1800184D2
0x18001832f  mov     r15d, [rsp+130h+var_F0]
0x180018334  mov     ebx, edi
0x180018336  sub     ebx, dword ptr [rbp+57h+var_78]
0x180018339  add     ebx, r15d
0x18001833c  mov     dword ptr [rbp+57h+var_C0+4], ebx
0x18001833f  cmp     [rsp+130h+NumberOfBytesWritten], esi
0x180018343  jb      loc_18001843A
0x180018349  cmp     byte ptr [rsp+130h+var_EC], 0Ah
0x18001834e  jnz     short loc_180018399
0x180018350  mov     rcx, [rbp+57h+hFile]; hFile
0x180018354  lea     eax, [r11+0Dh]
0x180018358  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001835d  mov     [rsp+130h+var_EC], ax
0x180018362  lea     r8d, [r11+1]; nNumberOfBytesToWrite
0x180018366  mov     [rsp+130h+lpOverlapped], r11; lpOverlapped
0x18001836b  lea     rdx, [rsp+130h+var_EC]; lpBuffer
0x180018370  call    cs:__imp_WriteFile
0x180018376  xor     r11d, r11d
0x180018379  test    eax, eax
0x18001837b  jz      loc_180018472
0x180018381  cmp     [rsp+130h+NumberOfBytesWritten], 1
0x180018386  jb      loc_18001843A
0x18001838c  inc     r15d
0x18001838f  inc     ebx
0x180018391  mov     [rsp+130h+var_F0], r15d
0x180018396  mov     dword ptr [rbp+57h+var_C0+4], ebx
0x180018399  mov     rsi, rdi
0x18001839c  cmp     rdi, r13
0x18001839f  jnb     loc_180018485
0x1800183a5  mov     rax, [rbp+57h+var_70]
0x1800183a9  mov     edx, [rbp+57h+var_AC]
0x1800183ac  jmp     loc_1800180B5
0x1800183b1  mov     edx, r11d
0x1800183b4  test    r8, r8
0x1800183b7  jle     short loc_1800183E6
0x1800183b9  sub     rdi, rsi
0x1800183bc  lea     rbx, cs:180000000h
0x1800183c3  mov     al, [rdi+rsi]
0x1800183c6  inc     edx
0x1800183c8  mov     rcx, rva __pioinfo[rbx+r12*8]
0x1800183d0  add     rcx, rsi
0x1800183d3  inc     rsi
0x1800183d6  mov     [rcx+r14*8+3Eh], al
0x1800183db  movsxd  rax, edx
0x1800183de  cmp     rax, r8
0x1800183e1  jl      short loc_1800183C3
0x1800183e3  mov     ebx, dword ptr [rbp+57h+var_C0+4]
0x1800183e6  add     ebx, r8d
0x1800183e9  jmp     short loc_180018437
0x1800183eb  mov     r9d, r11d
0x1800183ee  test    rdx, rdx
0x1800183f1  jle     short loc_180018435
0x1800183f3  mov     r13, [rbp+57h+var_68]
0x1800183f7  mov     r8, r11
0x1800183fa  mov     r10, r13
0x1800183fd  and     r13d, 3Fh
0x180018401  sar     r10, 6
0x180018405  lea     r11, ds:0[r13*8]
0x18001840d  add     r11, r13
0x180018410  mov     al, [r8+rdi]
0x180018414  inc     r9d
0x180018417  mov     rcx, rva __pioinfo[r15+r10*8]
0x18001841f  add     rcx, r8
0x180018422  inc     r8
0x180018425  mov     [rcx+r11*8+3Eh], al
0x18001842a  movsxd  rax, r9d
0x18001842d  cmp     rax, rdx
0x180018430  jl      short loc_180018410
0x180018432  xor     r11d, r11d
0x180018435  add     ebx, edx
0x180018437  mov     dword ptr [rbp+57h+var_C0+4], ebx
0x18001843a  cmp     [rbp+57h+var_C8], r11b
0x18001843e  mov     ecx, [rsp+130h+var_F0]
0x180018442  jmp     short loc_18001848D
0x180018444  mov     al, [rdi]
0x180018446  lea     r8, cs:180000000h
0x18001844d  mov     rcx, rva __pioinfo[r8+r12*8]
0x180018455  inc     ebx
0x180018457  mov     dword ptr [rbp+57h+var_C0+4], ebx
0x18001845a  mov     [rcx+r14*8+3Eh], al
0x18001845f  mov     rax, rva __pioinfo[r8+r12*8]
0x180018467  or      byte ptr [rax+r14*8+3Dh], 4
0x18001846d  cmp     [rbp+57h+var_C8], dl
0x180018470  jmp     short loc_18001843E
0x180018472  call    cs:__imp_GetLastError
0x180018478  mov     dword ptr [rbp+57h+var_C0], eax
0x18001847b  mov     ecx, [rsp+130h+var_F0]
0x18001847f  cmp     [rbp+57h+var_C8], 0
  ... truncated ...
```
