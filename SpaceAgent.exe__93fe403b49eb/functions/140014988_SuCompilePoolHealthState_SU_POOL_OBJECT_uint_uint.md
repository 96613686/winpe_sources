# SuCompilePoolHealthState(_SU_POOL_OBJECT *,uint *,uint *)

- ea: `0x140014988`
- end: `0x140014e6e`
- name: `?SuCompilePoolHealthState@@YAJPEAU_SU_POOL_OBJECT@@PEAI1@Z`
- size: `1254`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140002e4c`

## callees

- `0x140001caf`
- `0x1400081d4`
- `0x14000c600`
- `0x14000e158`
- `0x140012e28`
- `0x140012e84`
- `0x140014988`
- `0x140016994`
- `0x14001ab68`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140014b6b`
- `KERNEL32!LocalFree` at `0x140014d43`
- `KERNEL32!LocalFree` at `0x140014e2e`
- `KERNEL32!LocalFree` at `0x140014e3c`
- `KERNEL32!LocalFree` at `0x140014b6b`
- `KERNEL32!LocalFree` at `0x140014d43`
- `KERNEL32!LocalFree` at `0x140014e2e`
- `KERNEL32!LocalFree` at `0x140014e3c`
- `KERNEL32!GetLastError` at `0x140014aba`
- `KERNEL32!GetLastError` at `0x140014b02`
- `KERNEL32!GetLastError` at `0x140014b76`
- `KERNEL32!GetLastError` at `0x140014bc8`
- `KERNEL32!GetLastError` at `0x140014c20`
- `KERNEL32!GetLastError` at `0x140014d52`
- `KERNEL32!GetLastError` at `0x140014aba`
- `KERNEL32!GetLastError` at `0x140014b02`
- `KERNEL32!GetLastError` at `0x140014b76`
- `KERNEL32!GetLastError` at `0x140014bc8`
- `KERNEL32!GetLastError` at `0x140014c20`
- `KERNEL32!GetLastError` at `0x140014d52`

## pseudocode

```c
__int64 __fastcall SuCompilePoolHealthState(struct _SU_POOL_OBJECT *a1, unsigned int *a2, unsigned int *a3)
{
  int v3; // r9d
  int v4; // r10d
  int v6; // edx
  struct _SU_POOL_OBJECT *v7; // r13
  int v8; // ecx
  unsigned int *v9; // r12
  signed int v10; // ebx
  struct _SP_IDS *v11; // r15
  int v12; // r9d
  int v13; // r9d
  __int128 v14; // xmm0
  unsigned int v15; // r8d
  signed int LastError; // eax
  _DWORD *v17; // rax
  struct _GUID *v18; // rsi
  signed int v19; // eax
  HLOCAL v20; // rcx
  int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  BOOL v24; // r14d
  struct _GUID *v25; // rax
  signed int v26; // eax
  char *v27; // rsi
  char *v28; // rax
  unsigned int v29; // r12d
  unsigned int v30; // r14d
  unsigned int v31; // r13d
  bool v32; // zf
  __int64 v33; // r9
  HLOCAL v34; // rax
  signed int v35; // eax
  int v36; // eax
  struct _GUID *v37; // rax
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // r9
  int v41; // [rsp+40h] [rbp-C0h]
  int v42; // [rsp+44h] [rbp-BCh]
  int v43; // [rsp+48h] [rbp-B8h]
  BOOL v44; // [rsp+4Ch] [rbp-B4h]
  HLOCAL v45; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+60h] [rbp-A0h]
  struct _SP_IDS *v48; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v49; // [rsp+70h] [rbp-90h]
  int v50; // [rsp+78h] [rbp-88h]
  HLOCAL v51; // [rsp+80h] [rbp-80h] BYREF
  struct _SU_POOL_OBJECT *v52; // [rsp+88h] [rbp-78h]
  int v53; // [rsp+90h] [rbp-70h] BYREF
  __int128 v54; // [rsp+94h] [rbp-6Ch]
  unsigned int v55; // [rsp+A4h] [rbp-5Ch]
  char v56; // [rsp+A8h] [rbp-58h]
  char v57; // [rsp+B0h] [rbp-50h]
  char v58; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v59[264]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = *((_DWORD *)a1 + 662);
  v4 = *((_DWORD *)a1 + 666);
  v6 = *((_DWORD *)a1 + 663);
  v7 = a1;
  v52 = a1;
  v8 = 0;
  v49 = a3;
  *a2 = 3;
  v9 = a3;
  *a3 = 33299;
  v45 = 0;
  v10 = 0;
  v48 = 0;
  v11 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( v3 )
  {
    v12 = v3 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 == 1 )
          *a2 = 3;
      }
      else
      {
        *a2 = 2;
        v42 = 1;
      }
    }
    else
    {
      v8 = 1;
      *a2 = 1;
      v41 = 1;
    }
  }
  else
  {
    *a2 = 0;
    v43 = 1;
  }
  if ( v6 == 1 )
  {
    if ( v4 == 2 )
    {
      *a3 = 33300;
    }
    else if ( v4 == 3 )
    {
      *a3 = 33297;
    }
  }
  else if ( v6 == 2 )
  {
    *a3 = 33298;
  }
  if ( v8 )
    return (unsigned int)v10;
  v14 = *(_OWORD *)((char *)v7 + 40);
  v56 = 0;
  v57 = 0;
  v54 = v14;
  v58 = 0;
  v53 = 64;
  LOWORD(v55) = 257;
  BYTE2(v55) = 1;
  if ( !(unsigned int)SiGetDriveIds((struct SP_DRIVE_ENUM_FILTER *)&v53, (struct _SP_IDS **)&v45) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
  v17 = v45;
  v18 = (struct _GUID *)((char *)v45 + 4);
  while ( v10 >= 0 )
  {
    if ( !*v17 )
    {
      if ( !(unsigned int)SuGetSpaceIds((struct _GUID *)((char *)v7 + 40), &v48) )
      {
        v23 = GetLastError();
        v10 = v23;
        if ( v23 > 0 )
          v10 = (unsigned __int16)v23 | 0x80070000;
      }
      v11 = v48;
      break;
    }
    hMem = 0;
    if ( SuGetDriveFiltered(v7, v18, v15, (struct _SU_DRIVE_OBJECT **)&hMem) )
    {
      v10 = 0;
    }
    else
    {
      v19 = GetLastError();
      v10 = v19;
      if ( v19 > 0 )
        v10 = (unsigned __int16)v19 | 0x80070000;
      if ( v10 < 0 )
        break;
    }
    v20 = hMem;
    if ( hMem )
    {
      v21 = *((_DWORD *)hMem + 715);
      if ( v21 == 1 )
      {
        v41 = 1;
        *v9 = 33303;
      }
      else if ( v21 == 2 )
      {
        v42 = 1;
      }
      else if ( !v21 || *((_DWORD *)hMem + 714) == 5 )
      {
        v43 = 1;
      }
      if ( LocalFree(v20) )
      {
        v22 = GetLastError();
        v10 = v22;
        if ( v22 > 0 )
          v10 = (unsigned __int16)v22 | 0x80070000;
      }
      if ( v41 )
      {
        *a2 = 1;
        goto LABEL_91;
      }
      if ( v10 < 0 )
        break;
    }
    v17 = v45;
    --*(_DWORD *)v45;
    ++v18;
  }
  v24 = 0;
  v25 = (struct _GUID *)((char *)v11 + 4);
  v44 = 0;
  while ( 1 )
  {
    hMem = v25;
    if ( v10 < 0 || !*(_DWORD *)v11 )
      break;
    v51 = 0;
    if ( SuGetSpaceFiltered(v7, v25, v15, (struct _SU_SPACE_OBJECT **)&v51) )
    {
      v10 = 0;
    }
    else
    {
      v26 = GetLastError();
      v10 = v26;
      if ( v26 > 0 )
        v10 = (unsigned __int16)v26 | 0x80070000;
    }
    v27 = (char *)v51;
    v47 = 0;
    LODWORD(v48) = 0;
    v50 = 0;
    if ( v10 < 0 )
      goto LABEL_78;
    v28 = (char *)v51 + 72;
    v29 = 0;
    v30 = *((_DWORD *)v51 + 669);
    v31 = 0;
    if ( v30 != -1 )
    {
      memset_0(&v53, 0, 0x50u);
      StringCchPrintfW(v59, 0x104u, (size_t *)L"\\\\.\\PhysicalDrive%d", v30);
      v32 = (unsigned int)GetDiskProperties(v59, (struct DISK_PROPERTIES *)&v53) == 1;
      v28 = v27 + 72;
      if ( v32 )
      {
        v29 = HIDWORD(v54);
        v31 = v55;
      }
    }
    v24 = v44 || *((_DWORD *)v27 + 692) == 1;
    v44 = v24;
    v33 = v31;
    v7 = v52;
    SuCompileSpaceHealthState(v28, v52, v29, v33);
    switch ( v47 )
    {
      case 1:
        v9 = v49;
        v41 = 1;
        *v49 = 33303;
        break;
      case 2:
        v42 = 1;
        break;
      case 0:
        v9 = v49;
LABEL_78:
        v43 = 1;
        break;
      default:
        v9 = v49;
        break;
    }
    if ( v27 )
    {
      v34 = LocalFree(v27);
      if ( v10 >= 0 )
      {
        if ( v34 )
        {
          v35 = GetLastError();
          v10 = v35;
          if ( v35 > 0 )
            v10 = (unsigned __int16)v35 | 0x80070000;
        }
      }
    }
    v36 = v41;
    if ( v41 )
    {
      *a2 = 1;
      goto LABEL_85;
    }
    v37 = (struct _GUID *)hMem;
    if ( v10 < 0 )
      break;
    --*(_DWORD *)v11;
    v25 = v37 + 1;
  }
  if ( v42 )
  {
    *a2 = 2;
  }
  else if ( v43 )
  {
    *a2 = 0;
  }
  v36 = v41;
LABEL_85:
  if ( v24 )
  {
    v38 = *((_QWORD *)v7 + 334);
    v39 = *((_QWORD *)v7 + 335);
    if ( v39 == v38 )
    {
      *a2 = 1;
      *v9 = 33301;
    }
    else if ( !v36 && v39 >= v38 / 0x64 * *((unsigned __int8 *)v7 + 2724) )
    {
      *a2 = 2;
      *v9 = 33302;
    }
  }
LABEL_91:
  if ( v45 )
    LocalFree(v45);
  if ( v11 )
    LocalFree(v11);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140014988  mov     [rsp-8+arg_18], rbx
0x14001498d  push    rbp
0x14001498e  push    rsi
0x14001498f  push    rdi
0x140014990  push    r12
0x140014992  push    r13
0x140014994  push    r14
0x140014996  push    r15
0x140014998  lea     rbp, [rsp-200h]
0x1400149a0  sub     rsp, 300h
0x1400149a7  mov     rax, cs:__security_cookie
0x1400149ae  xor     rax, rsp
0x1400149b1  mov     [rbp+230h+var_40], rax
0x1400149b8  mov     r9d, [rcx+0A58h]
0x1400149bf  xor     esi, esi
0x1400149c1  mov     r10d, [rcx+0A68h]
0x1400149c8  mov     rdi, rdx
0x1400149cb  mov     edx, [rcx+0A5Ch]
0x1400149d1  mov     r13, rcx
0x1400149d4  mov     [rbp+230h+var_2A8], rcx
0x1400149d8  mov     ecx, esi
0x1400149da  mov     [rsp+330h+var_2C0], r8
0x1400149df  lea     r11d, [rsi+3]
0x1400149e3  mov     [rdi], r11d
0x1400149e6  mov     r12, r8
0x1400149e9  mov     dword ptr [r8], 8213h
0x1400149f0  lea     r8d, [rsi+1]
0x1400149f4  mov     [rsp+330h+var_2E0], rsi
0x1400149f9  mov     ebx, esi
0x1400149fb  mov     [rsp+330h+var_2C8], rsi
0x140014a00  mov     r15d, esi
0x140014a03  mov     [rsp+330h+var_2F0], ecx
0x140014a07  mov     [rsp+330h+var_2EC], esi
0x140014a0b  mov     [rsp+330h+var_2E8], esi
0x140014a0f  test    r9d, r9d
0x140014a12  jz      short loc_140014A41
0x140014a14  sub     r9d, r8d
0x140014a17  jz      short loc_140014A35
0x140014a19  sub     r9d, r8d
0x140014a1c  jz      short loc_140014A28
0x140014a1e  cmp     r9d, r8d
0x140014a21  jnz     short loc_140014A48
0x140014a23  mov     [rdi], r11d
0x140014a26  jmp     short loc_140014A48
0x140014a28  mov     dword ptr [rdi], 2
0x140014a2e  mov     [rsp+330h+var_2EC], r8d
0x140014a33  jmp     short loc_140014A48
0x140014a35  mov     ecx, r8d
0x140014a38  mov     [rdi], r8d
0x140014a3b  mov     [rsp+330h+var_2F0], ecx
0x140014a3f  jmp     short loc_140014A48
0x140014a41  mov     [rdi], esi
0x140014a43  mov     [rsp+330h+var_2E8], r8d
0x140014a48  cmp     edx, r8d
0x140014a4b  jnz     short loc_140014A6C
0x140014a4d  cmp     r10d, 2
0x140014a51  jnz     short loc_140014A5D
0x140014a53  mov     dword ptr [r12], 8214h
0x140014a5b  jmp     short loc_140014A79
0x140014a5d  cmp     r10d, r11d
0x140014a60  jnz     short loc_140014A79
0x140014a62  mov     dword ptr [r12], 8211h
0x140014a6a  jmp     short loc_140014A79
0x140014a6c  cmp     edx, 2
0x140014a6f  jnz     short loc_140014A79
0x140014a71  mov     dword ptr [r12], 8212h
0x140014a79  test    ecx, ecx
0x140014a7b  jnz     loc_140014E42
0x140014a81  movups  xmm0, xmmword ptr [r13+28h]
0x140014a86  lea     rdx, [rsp+330h+var_2E0]; struct _SP_IDS **
0x140014a8b  mov     [rbp+230h+var_288], sil
0x140014a8f  lea     rcx, [rbp+230h+var_2A0]; lpInBuffer
0x140014a93  mov     [rbp+230h+var_280], sil
0x140014a97  movdqu  [rbp+230h+var_29C], xmm0
0x140014a9c  mov     [rbp+230h+var_278], sil
0x140014aa0  mov     [rbp+230h+var_2A0], 40h ; '@'
0x140014aa7  mov     word ptr [rbp+230h+var_28C], 101h
0x140014aad  mov     byte ptr [rbp+230h+var_28C+2], r8b
0x140014ab1  call    ?SiGetDriveIds@@YAHPEAVSP_DRIVE_ENUM_FILTER@@PEAPEAU_SP_IDS@@@Z; SiGetDriveIds(SP_DRIVE_ENUM_FILTER *,_SP_IDS * *)
0x140014ab6  test    eax, eax
0x140014ab8  jnz     short loc_140014ACF
0x140014aba  call    cs:__imp_GetLastError
0x140014ac0  mov     ebx, eax
0x140014ac2  test    eax, eax
0x140014ac4  jle     short loc_140014ACF
0x140014ac6  movzx   ebx, ax
0x140014ac9  or      ebx, 80070000h
0x140014acf  mov     rax, [rsp+330h+var_2E0]
0x140014ad4  lea     rsi, [rax+4]
0x140014ad8  test    ebx, ebx
0x140014ada  js      loc_140014BE2
0x140014ae0  cmp     [rax], r15d
0x140014ae3  jbe     loc_140014BB6
0x140014ae9  lea     r9, [rsp+330h+hMem]; struct _SU_DRIVE_OBJECT **
0x140014aee  mov     [rsp+330h+hMem], r15
0x140014af3  mov     rdx, rsi; struct _GUID *
0x140014af6  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140014af9  call    ?SuGetDriveFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_DRIVE_OBJECT@@@Z; SuGetDriveFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_DRIVE_OBJECT * *)
0x140014afe  test    eax, eax
0x140014b00  jnz     short loc_140014B26
0x140014b02  call    cs:__imp_GetLastError
0x140014b08  mov     ebx, eax
0x140014b0a  test    eax, eax
0x140014b0c  jle     short loc_140014B17
0x140014b0e  movzx   ebx, ax
0x140014b11  or      ebx, 80070000h
0x140014b17  mov     rax, [rsp+330h+var_2E0]
0x140014b1c  test    ebx, ebx
0x140014b1e  js      loc_140014BE2
0x140014b24  jmp     short loc_140014B28
0x140014b26  xor     ebx, ebx
0x140014b28  mov     rcx, [rsp+330h+hMem]; hMem
0x140014b2d  test    rcx, rcx
0x140014b30  jz      short loc_140014B9B
0x140014b32  mov     eax, [rcx+0B2Ch]
0x140014b38  mov     edx, 1
0x140014b3d  cmp     eax, edx
0x140014b3f  jnz     short loc_140014B4F
0x140014b41  mov     [rsp+330h+var_2F0], edx
0x140014b45  mov     dword ptr [r12], 8217h
0x140014b4d  jmp     short loc_140014B6B
0x140014b4f  cmp     eax, 2
0x140014b52  jnz     short loc_140014B5A
0x140014b54  mov     [rsp+330h+var_2EC], edx
0x140014b58  jmp     short loc_140014B6B
0x140014b5a  test    eax, eax
0x140014b5c  jz      short loc_140014B67
0x140014b5e  cmp     dword ptr [rcx+0B28h], 5
0x140014b65  jnz     short loc_140014B6B
0x140014b67  mov     [rsp+330h+var_2E8], edx
0x140014b6b  call    cs:__imp_LocalFree
0x140014b71  test    rax, rax
0x140014b74  jz      short loc_140014B8B
0x140014b76  call    cs:__imp_GetLastError
0x140014b7c  mov     ebx, eax
0x140014b7e  test    eax, eax
0x140014b80  jle     short loc_140014B8B
0x140014b82  movzx   ebx, ax
0x140014b85  or      ebx, 80070000h
0x140014b8b  cmp     [rsp+330h+var_2F0], r15d
0x140014b90  jnz     short loc_140014BAB
0x140014b92  mov     rax, [rsp+330h+var_2E0]
0x140014b97  test    ebx, ebx
0x140014b99  js      short loc_140014BE2
0x140014b9b  mov     rax, [rsp+330h+var_2E0]
0x140014ba0  dec     dword ptr [rax]
0x140014ba2  add     rsi, 10h
0x140014ba6  jmp     loc_140014AD8
0x140014bab  mov     dword ptr [rdi], 1
0x140014bb1  jmp     loc_140014E24
0x140014bb6  lea     rdx, [rsp+330h+var_2C8]; struct _SP_IDS **
0x140014bbb  lea     rcx, [r13+28h]; struct _GUID *
0x140014bbf  call    ?SuGetSpaceIds@@YAHPEAU_GUID@@PEAPEAU_SP_IDS@@@Z; SuGetSpaceIds(_GUID *,_SP_IDS * *)
0x140014bc4  test    eax, eax
0x140014bc6  jnz     short loc_140014BDD
0x140014bc8  call    cs:__imp_GetLastError
0x140014bce  mov     ebx, eax
0x140014bd0  test    eax, eax
0x140014bd2  jle     short loc_140014BDD
0x140014bd4  movzx   ebx, ax
0x140014bd7  or      ebx, 80070000h
0x140014bdd  mov     r15, [rsp+330h+var_2C8]
0x140014be2  xor     r14d, r14d
0x140014be5  lea     rax, [r15+4]
0x140014be9  mov     [rsp+330h+var_2E4], r14d
0x140014bee  mov     [rsp+330h+hMem], rax
0x140014bf3  test    ebx, ebx
0x140014bf5  js      loc_140014D9F
0x140014bfb  cmp     dword ptr [r15], 0
0x140014bff  jbe     loc_140014D9F
0x140014c05  lea     r9, [rbp+230h+var_2B0]; struct _SU_SPACE_OBJECT **
0x140014c09  mov     [rbp+230h+var_2B0], 0
0x140014c11  mov     rdx, rax; struct _GUID *
0x140014c14  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140014c17  call    ?SuGetSpaceFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpaceFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_SPACE_OBJECT * *)
0x140014c1c  test    eax, eax
0x140014c1e  jnz     short loc_140014C37
0x140014c20  call    cs:__imp_GetLastError
0x140014c26  mov     ebx, eax
0x140014c28  test    eax, eax
0x140014c2a  jle     short loc_140014C39
0x140014c2c  movzx   ebx, ax
0x140014c2f  or      ebx, 80070000h
0x140014c35  jmp     short loc_140014C39
0x140014c37  xor     ebx, ebx
0x140014c39  mov     rsi, [rbp+230h+var_2B0]
0x140014c3d  mov     [rsp+330h+var_2D0], 0
0x140014c45  mov     dword ptr [rsp+330h+var_2C8], 0
0x140014c4d  mov     [rsp+330h+var_2B8], 0
0x140014c55  test    ebx, ebx
0x140014c57  js      loc_140014D8D
0x140014c5d  lea     rax, [rsi+48h]
0x140014c61  xor     r12d, r12d
0x140014c64  mov     r14d, [rax+0A2Ch]
0x140014c6b  xor     r13d, r13d
0x140014c6e  cmp     r14d, 0FFFFFFFFh
0x140014c72  jz      short loc_140014CBA
0x140014c74  xor     edx, edx; Val
0x140014c76  lea     r8d, [r12+50h]; Size
0x140014c7b  lea     rcx, [rbp+230h+var_2A0]; void *
0x140014c7f  call    memset_0
0x140014c84  mov     r9d, r14d
0x140014c87  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x140014c8e  mov     edx, 104h; unsigned __int64
0x140014c93  lea     rcx, [rbp+230h+var_250]; unsigned __int16 *
0x140014c97  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014c9c  lea     rdx, [rbp+230h+var_2A0]; struct DISK_PROPERTIES *
0x140014ca0  lea     rcx, [rbp+230h+var_250]; unsigned __int16 *
0x140014ca4  call    ?GetDiskProperties@@YAHPEBGPEAUDISK_PROPERTIES@@@Z; GetDiskProperties(ushort const *,DISK_PROPERTIES *)
0x140014ca9  cmp     eax, 1
0x140014cac  lea     rax, [rsi+48h]
0x140014cb0  jnz     short loc_140014CBA
0x140014cb2  mov     r12d, dword ptr [rbp+230h+var_29C+0Ch]
0x140014cb6  mov     r13d, [rbp+230h+var_28C]
0x140014cba  cmp     [rsp+330h+var_2E4], 0
0x140014cbf  jnz     short loc_140014CCF
0x140014cc1  cmp     dword ptr [rsi+0AD0h], 1
0x140014cc8  jz      short loc_140014CCF
0x140014cca  xor     r14d, r14d
0x140014ccd  jmp     short loc_140014CD5
0x140014ccf  mov     r14d, 1
0x140014cd5  lea     rcx, [rsp+330h+var_2B8]
0x140014cda  mov     [rsp+330h+var_2E4], r14d
0x140014cdf  mov     [rsp+330h+var_2F8], rcx
0x140014ce4  mov     r9d, r13d
0x140014ce7  mov     r13, [rbp+230h+var_2A8]
0x140014ceb  lea     rcx, [rsp+330h+var_2C8]
0x140014cf0  mov     [rsp+330h+var_300], rcx
0x140014cf5  mov     r8d, r12d
0x140014cf8  lea     rcx, [rsp+330h+var_2D0]
0x140014cfd  mov     rdx, r13
0x140014d00  mov     [rsp+330h+var_308], rcx
0x140014d05  mov     rcx, rax
0x140014d08  call    ?SuCompileSpaceHealthState@@YAXPEBU_SP_SPACE_INFO@@PEAU_SU_POOL_OBJECT@@HW4_DISK_OFFLINE_REASON@@HPEAI3PEAK@Z; SuCompileSpaceHealthState(_SP_SPACE_INFO const *,_SU_POOL_OBJECT *,int,_DISK_OFFLINE_REASON,int,uint *,uint *,ulong *)
0x140014d0d  mov     eax, [rsp+330h+var_2D0]
0x140014d11  cmp     eax, 1
0x140014d14  jnz     short loc_140014D29
0x140014d16  mov     r12, [rsp+330h+var_2C0]
0x140014d1b  mov     [rsp+330h+var_2F0], eax
0x140014d1f  mov     dword ptr [r12], 8217h
0x140014d27  jmp     short loc_140014D3B
0x140014d29  cmp     eax, 2
0x140014d2c  jnz     short loc_140014D84
0x140014d2e  mov     [rsp+330h+var_2EC], 1
0x140014d36  mov     r12, [rsp+330h+var_2C0]
0x140014d3b  test    rsi, rsi
0x140014d3e  jz      short loc_140014D67
0x140014d40  mov     rcx, rsi; hMem
0x140014d43  call    cs:__imp_LocalFree
0x140014d49  test    ebx, ebx
0x140014d4b  js      short loc_140014D67
0x140014d4d  test    rax, rax
0x140014d50  jz      short loc_140014D67
0x140014d52  call    cs:__imp_GetLastError
0x140014d58  mov     ebx, eax
0x140014d5a  test    eax, eax
0x140014d5c  jle     short loc_140014D67
0x140014d5e  movzx   ebx, ax
0x140014d61  or      ebx, 80070000h
0x140014d67  mov     eax, [rsp+330h+var_2F0]
0x140014d6b  test    eax, eax
0x140014d6d  jnz     short loc_140014D97
0x140014d6f  mov     rax, [rsp+330h+hMem]
0x140014d74  test    ebx, ebx
0x140014d76  js      short loc_140014D9F
0x140014d78  dec     dword ptr [r15]
0x140014d7b  add     rax, 10h
0x140014d7f  jmp     loc_140014BEE
0x140014d84  test    eax, eax
0x140014d86  jnz     short loc_140014D36
0x140014d88  mov     r12, [rsp+330h+var_2C0]
0x140014d8d  mov     [rsp+330h+var_2E8], 1
0x140014d95  jmp     short loc_140014D3B
0x140014d97  mov     dword ptr [rdi], 1
0x140014d9d  jmp     short loc_140014DBF
0x140014d9f  cmp     [rsp+330h+var_2EC], 0
0x140014da4  jz      short loc_140014DAE
0x140014da6  mov     dword ptr [rdi], 2
0x140014dac  jmp     short loc_140014DBB
0x140014dae  cmp     [rsp+330h+var_2E8], 0
0x140014db3  jz      short loc_140014DBB
0x140014db5  mov     dword ptr [rdi], 0
0x140014dbb  mov     eax, [rsp+330h+var_2F0]
0x140014dbf  test    r14d, r14d
0x140014dc2  jz      short loc_140014E24
0x140014dc4  mov     rcx, [r13+0A70h]
0x140014dcb  mov     r9, [r13+0A78h]
0x140014dd2  cmp     r9, rcx
0x140014dd5  jnz     short loc_140014DE7
0x140014dd7  mov     dword ptr [rdi], 1
0x140014ddd  mov     dword ptr [r12], 8215h
0x140014de5  jmp     short loc_140014E24
0x140014de7  test    eax, eax
0x140014de9  jnz     short loc_140014E24
0x140014deb  movzx   r8d, byte ptr [r13+0AA4h]
0x140014df3  mov     rax, 47AE147AE147AE15h
0x140014dfd  mul     rcx
0x140014e00  sub     rcx, rdx
0x140014e03  shr     rcx, 1
0x140014e06  add     rcx, rdx
  ... truncated ...
```
