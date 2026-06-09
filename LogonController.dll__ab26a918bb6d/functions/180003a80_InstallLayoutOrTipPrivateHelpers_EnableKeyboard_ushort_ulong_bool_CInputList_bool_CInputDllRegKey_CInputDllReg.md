# InstallLayoutOrTipPrivateHelpers::EnableKeyboard(ushort,ulong,bool,CInputList &,bool,CInputDllRegKey &,CInputDllRegKey &)

- ea: `0x180003a80`
- end: `0x1800040d6`
- name: `?EnableKeyboard@InstallLayoutOrTipPrivateHelpers@@SAXGK_NAEAVCInputList@@0AEAVCInputDllRegKey@@2@Z`
- size: `1622`
- prototype: `void __fastcall(unsigned __int16, unsigned int, char, struct CInputList *, bool, struct CInputDllRegKey *, struct CInputDllRegKey *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180002f10`
- `0x180005500`

## callees

- `0x180003a80`
- `0x180004b70`
- `0x18003b860`
- `0x18006c000`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003e53`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003e53`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180003ea7`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180003ea7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall InstallLayoutOrTipPrivateHelpers::EnableKeyboard(
        unsigned __int16 a1,
        unsigned int a2,
        char a3,
        struct CInputList *a4,
        bool a5,
        struct CInputDllRegKey *a6,
        struct CInputDllRegKey *a7)
{
  struct InputContainer *NextEmptyEntry; // r12
  unsigned int v10; // r8d
  char v11; // dl
  unsigned int v12; // r13d
  unsigned int v13; // ecx
  __int64 v14; // rax
  int v15; // ebx
  HKEY v16; // r14
  HKEY v17; // rsi
  LSTATUS v18; // eax
  LSTATUS v19; // edi
  unsigned int v20; // edi
  int v21; // edx
  unsigned int v22; // r8d
  __int64 v23; // rcx
  char *v24; // r9
  __int64 v25; // rcx
  unsigned int v26; // edx
  __int64 v27; // rcx
  char *v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned __int16 *v31; // rcx
  __int64 v32; // r9
  struct InputContainer *v33; // rax
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 *v45; // rax
  __int64 v46; // rcx
  __int128 v47; // xmm0
  unsigned __int16 *v48; // rcx
  __int128 v49; // xmm1
  _OWORD *v50; // rax
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  __int128 v57; // xmm0
  __int128 v58; // xmm1
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY v64; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v66; // [rsp+64h] [rbp-9Ch]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[12]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v69[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v70[176]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v71[352]; // [rsp+150h] [rbp+50h] BYREF

  NextEmptyEntry = 0;
  v66 = a2;
  v10 = 0;
  v11 = 0;
  v12 = a1;
  v13 = *(_DWORD *)a4;
  if ( *(_DWORD *)a4 )
    v14 = *((_QWORD *)a4 + 1);
  else
    v14 = 0;
  v15 = 1;
  while ( v14 && v10 < *((_DWORD *)a4 + 1) )
  {
    if ( *(_BYTE *)(v14 + 16) )
      v11 = 1;
    if ( *(_WORD *)v14 == (_WORD)v12 && *(_DWORD *)(v14 + 4) == a2 )
    {
      NextEmptyEntry = (struct InputContainer *)v14;
      break;
    }
    if ( ++v10 >= v13 )
      v14 = 0;
    else
      v14 = *((_QWORD *)a4 + 1) + 700LL * v10;
  }
  if ( !v11 && NextEmptyEntry )
  {
    while ( 1 )
    {
      v29 = ++v10 >= v13 ? 0LL : *((_QWORD *)a4 + 1) + 700LL * v10;
      if ( !v29 || v10 >= *((_DWORD *)a4 + 1) )
        break;
      if ( *(_BYTE *)(v29 + 16) )
      {
        v30 = 5;
        v31 = v71;
        v32 = 5;
        v33 = NextEmptyEntry;
        do
        {
          v31 += 64;
          v34 = *(_OWORD *)v33;
          v35 = *((_OWORD *)v33 + 1);
          v33 = (struct InputContainer *)((char *)v33 + 128);
          *((_OWORD *)v31 - 8) = v34;
          v36 = *((_OWORD *)v33 - 6);
          *((_OWORD *)v31 - 7) = v35;
          v37 = *((_OWORD *)v33 - 5);
          *((_OWORD *)v31 - 6) = v36;
          v38 = *((_OWORD *)v33 - 4);
          *((_OWORD *)v31 - 5) = v37;
          v39 = *((_OWORD *)v33 - 3);
          *((_OWORD *)v31 - 4) = v38;
          v40 = *((_OWORD *)v33 - 2);
          *((_OWORD *)v31 - 3) = v39;
          v41 = *((_OWORD *)v33 - 1);
          *((_OWORD *)v31 - 2) = v40;
          *((_OWORD *)v31 - 1) = v41;
          --v32;
        }
        while ( v32 );
        v42 = *((_OWORD *)v33 + 1);
        *(_OWORD *)v31 = *(_OWORD *)v33;
        v43 = *((_OWORD *)v33 + 2);
        *((_OWORD *)v31 + 1) = v42;
        v44 = *(_OWORD *)((char *)v33 + 44);
        v45 = (__int128 *)v29;
        *((_OWORD *)v31 + 2) = v43;
        *(_OWORD *)(v31 + 22) = v44;
        v46 = 5;
        do
        {
          NextEmptyEntry = (struct InputContainer *)((char *)NextEmptyEntry + 128);
          v47 = *v45;
          v45 += 8;
          *((_OWORD *)NextEmptyEntry - 8) = v47;
          *((_OWORD *)NextEmptyEntry - 7) = *(v45 - 7);
          *((_OWORD *)NextEmptyEntry - 6) = *(v45 - 6);
          *((_OWORD *)NextEmptyEntry - 5) = *(v45 - 5);
          *((_OWORD *)NextEmptyEntry - 4) = *(v45 - 4);
          *((_OWORD *)NextEmptyEntry - 3) = *(v45 - 3);
          *((_OWORD *)NextEmptyEntry - 2) = *(v45 - 2);
          *((_OWORD *)NextEmptyEntry - 1) = *(v45 - 1);
          --v46;
        }
        while ( v46 );
        v48 = v71;
        *(_OWORD *)NextEmptyEntry = *v45;
        *((_OWORD *)NextEmptyEntry + 1) = v45[1];
        *((_OWORD *)NextEmptyEntry + 2) = v45[2];
        v49 = *(__int128 *)((char *)v45 + 44);
        v50 = (_OWORD *)v29;
        *(_OWORD *)((char *)NextEmptyEntry + 44) = v49;
        do
        {
          v50 += 8;
          v51 = *(_OWORD *)v48;
          v52 = *((_OWORD *)v48 + 1);
          v48 += 64;
          *(v50 - 8) = v51;
          v53 = *((_OWORD *)v48 - 6);
          *(v50 - 7) = v52;
          v54 = *((_OWORD *)v48 - 5);
          *(v50 - 6) = v53;
          v55 = *((_OWORD *)v48 - 4);
          *(v50 - 5) = v54;
          v56 = *((_OWORD *)v48 - 3);
          *(v50 - 4) = v55;
          v57 = *((_OWORD *)v48 - 2);
          *(v50 - 3) = v56;
          v58 = *((_OWORD *)v48 - 1);
          *(v50 - 2) = v57;
          *(v50 - 1) = v58;
          --v30;
        }
        while ( v30 );
        NextEmptyEntry = (struct InputContainer *)v29;
        v59 = *((_OWORD *)v48 + 1);
        *v50 = *(_OWORD *)v48;
        v60 = *((_OWORD *)v48 + 2);
        v50[1] = v59;
        v61 = *(_OWORD *)(v48 + 22);
        v50[2] = v60;
        *(_OWORD *)((char *)v50 + 44) = v61;
        break;
      }
    }
  }
  if ( (((_WORD)v12 - 0x2000) & 0xF3FF) == 0 && (_WORD)v12 != 11264
    || (_WORD)v12 == 11264
    || (StringCchPrintfW(SubKey, 9u, L"%08x", v12),
        !(*(unsigned int (__fastcall **)(struct CInputDllRegKey *, _BYTE *, WCHAR *, __int64))(*(_QWORD *)a7 + 8LL))(
           a7,
           v69,
           SubKey,
           9)) )
  {
    StringCchPrintfW(SubKey, 9u, L"%08x", a2);
    v16 = (HKEY)*((_QWORD *)a6 + 1);
    v17 = 0;
    v64 = 0;
    hKey = 0;
    if ( v16 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &hKey) )
      v16 = hKey;
    v18 = RegOpenKeyExW(v16, SubKey, 0, 0x20019u, &v64);
    v19 = v18;
    if ( !v18
      || v18 == 5
      && (dwDisposition = 0, (v19 = RegCreateKeyExW(v16, SubKey, 0, 0, 4u, 0x20019u, 0, &v64, &dwDisposition)) == 0) )
    {
      v17 = v64;
      v19 = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v19 )
    {
      if ( v17 )
        RegCloseKey(v17);
    }
    else
    {
      if ( v17 )
        RegCloseKey(v17);
      if ( NextEmptyEntry || (NextEmptyEntry = CInputList::GetNextEmptyEntry((const void **)a4)) != 0 )
      {
        v20 = v66;
        *((_BYTE *)NextEmptyEntry + 18) = a3;
        v21 = 1;
        *((_DWORD *)NextEmptyEntry + 3) = 1;
        v22 = 0;
        *(_WORD *)NextEmptyEntry = v12;
        *((_DWORD *)NextEmptyEntry + 1) = v20;
        *((_WORD *)NextEmptyEntry + 8) = 257;
        *((_WORD *)NextEmptyEntry + 10) = 123;
        do
        {
          if ( v21 >= 36 )
            break;
          v23 = *((unsigned __int8 *)qword_1800B0EC0 + (int)v22);
          v24 = (char *)NextEmptyEntry + 2 * v21;
          if ( (_BYTE)v23 == 45 )
          {
            *((_WORD *)v24 + 10) = 45;
          }
          else
          {
            ++v21;
            *((_WORD *)v24 + 10) = word_1800B0E90[(unsigned __int64)*((unsigned __int8 *)&GUID_NULL.Data1 + v23) >> 4];
            *((_WORD *)NextEmptyEntry + v21 + 10) = word_1800B0E90[*((_BYTE *)&_ImageBase + v23 + 709696) & 0xF];
          }
          ++v22;
          ++v21;
        }
        while ( v22 < 0x14 );
        v25 = v21;
        v26 = 0;
        *(_DWORD *)((char *)NextEmptyEntry + 2 * v25 + 20) = 125;
        *((_WORD *)NextEmptyEntry + 49) = 123;
        do
        {
          if ( v15 >= 36 )
            break;
          v27 = *((unsigned __int8 *)qword_1800B0EC0 + (int)v26);
          v28 = (char *)NextEmptyEntry + 2 * v15;
          if ( (_BYTE)v27 == 45 )
          {
            *((_WORD *)v28 + 49) = 45;
          }
          else
          {
            ++v15;
            *((_WORD *)v28 + 49) = word_1800B0E90[(unsigned __int64)*((unsigned __int8 *)&GUID_NULL.Data1 + v27) >> 4];
            *((_WORD *)NextEmptyEntry + v15 + 49) = word_1800B0E90[*((_BYTE *)&_ImageBase + v27 + 709696) & 0xF];
          }
          ++v26;
          ++v15;
        }
        while ( v26 < 0x14 );
        *(_DWORD *)((char *)NextEmptyEntry + 2 * v15 + 98) = 125;
        if ( a5
          && !a3
          && (int)((__int64 (__fastcall *)(_QWORD, _BYTE *, __int64))pfnBcp47BufferFromLcid)(v12, v70, 85) >= 0
          && (int)((__int64 (__fastcall *)(__int64, _BYTE *))pfnAppendUserLanguages)(59, v70) >= 0 )
        {
          LODWORD(phkResult) = v20;
          v71[0] = 0;
          StringCchPrintfW(v71, 0x57u, L"%04X:%08X", v12, phkResult);
          ((void (__fastcall *)(_BYTE *, __int64, unsigned __int16 *))pfnAppendUserLanguageInputMethods)(v70, 59, v71);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180003a80  mov     [rsp-8+arg_10], rbx
0x180003a85  push    rbp
0x180003a86  push    rsi
0x180003a87  push    rdi
0x180003a88  push    r12
0x180003a8a  push    r13
0x180003a8c  push    r14
0x180003a8e  push    r15
0x180003a90  lea     rbp, [rsp-320h]
0x180003a98  sub     rsp, 420h
0x180003a9f  mov     rax, cs:__security_cookie
0x180003aa6  xor     rax, rsp
0x180003aa9  mov     [rbp+350h+var_40], rax
0x180003ab0  mov     r14, [rbp+350h+arg_28]
0x180003ab7  mov     esi, edx
0x180003ab9  mov     rdi, [rbp+350h+arg_30]
0x180003ac0  xor     r12d, r12d
0x180003ac3  mov     [rsp+450h+var_400], r8b
0x180003ac8  mov     r15, r9
0x180003acb  mov     [rsp+450h+var_3EC], edx
0x180003acf  xor     r8d, r8d
0x180003ad2  xor     dl, dl
0x180003ad4  movzx   r13d, cx
0x180003ad8  mov     ecx, [r9]
0x180003adb  test    ecx, ecx
0x180003add  jz      loc_180003EDF
0x180003ae3  mov     rax, [r9+8]
0x180003ae7  mov     ebx, 1
0x180003aec  test    rax, rax
0x180003aef  jnz     loc_180003E68
0x180003af5  test    dl, dl
0x180003af7  jz      loc_180003EED
0x180003afd  mov     ecx, 2000h
0x180003b02  movzx   eax, r13w
0x180003b06  sub     ax, cx
0x180003b09  mov     ecx, 0F3FFh
0x180003b0e  test    cx, ax
0x180003b11  mov     eax, 2C00h
0x180003b16  jnz     loc_180003DC4
0x180003b1c  cmp     r13w, ax
0x180003b20  jz      loc_180003DC4
0x180003b26  mov     r9d, esi
0x180003b29  lea     r8, a08x_1; "%08x"
0x180003b30  mov     edx, 9; unsigned __int64
0x180003b35  lea     rcx, [rsp+450h+SubKey]; unsigned __int16 *
0x180003b3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003b3f  mov     r14, [r14+8]
0x180003b43  xor     esi, esi
0x180003b45  mov     [rsp+450h+var_3F8], rsi
0x180003b4a  mov     [rsp+450h+hKey], rsi
0x180003b4f  cmp     r14, 0FFFFFFFF80000001h
0x180003b56  jz      loc_180003E9D
0x180003b5c  lea     rax, [rsp+450h+var_3F8]
0x180003b61  mov     r9d, 20019h; samDesired
0x180003b67  xor     r8d, r8d; ulOptions
0x180003b6a  mov     [rsp+450h+phkResult], rax; phkResult
0x180003b6f  lea     rdx, [rsp+450h+SubKey]; lpSubKey
0x180003b74  mov     rcx, r14; hKey
0x180003b77  call    cs:__imp_RegOpenKeyExW
0x180003b7d  mov     edi, eax
0x180003b7f  test    eax, eax
0x180003b81  jnz     loc_180003E0F
0x180003b87  mov     rsi, [rsp+450h+var_3F8]
0x180003b8c  xor     edi, edi
0x180003b8e  mov     rcx, [rsp+450h+hKey]; hKey
0x180003b93  test    rcx, rcx
0x180003b96  jz      short loc_180003B9E
0x180003b98  call    cs:__imp_RegCloseKey
0x180003b9e  test    edi, edi
0x180003ba0  jnz     loc_180003D91
0x180003ba6  test    rsi, rsi
0x180003ba9  jnz     loc_1800040A1
0x180003baf  test    r12, r12
0x180003bb2  jz      loc_1800040AF
0x180003bb8  movzx   r10d, [rsp+450h+var_400]
0x180003bbe  lea     r11, __ImageBase
0x180003bc5  mov     edi, [rsp+450h+var_3EC]
0x180003bc9  mov     esi, 7Bh ; '{'
0x180003bce  mov     [r12+12h], r10b
0x180003bd3  mov     edx, ebx
0x180003bd5  mov     [r12+0Ch], ebx
0x180003bda  xor     r8d, r8d
0x180003bdd  mov     [r12], r13w
0x180003be2  mov     r14d, 2Dh ; '-'
0x180003be8  mov     [r12+4], edi
0x180003bed  mov     word ptr [r12+10h], 101h
0x180003bf5  mov     [r12+14h], si
0x180003bfb  nop     dword ptr [rax+rax+00h]
0x180003c00  cmp     edx, 24h ; '$'
0x180003c03  jge     short loc_180003C6A
0x180003c05  movsxd  rax, r8d
0x180003c08  movzx   ecx, byte ptr [rax+r11+0B0EC0h]
0x180003c11  movsxd  rax, edx
0x180003c14  lea     r9, [r12+rax*2]
0x180003c18  cmp     cl, r14b
0x180003c1b  jz      loc_180003D7D
0x180003c21  movzx   eax, byte ptr [rcx+r11+0AD440h]
0x180003c2a  lea     rcx, [rcx+0AD440h]
0x180003c31  shr     rax, 4
0x180003c35  inc     edx
0x180003c37  movzx   eax, ds:rva word_1800B0E90[r11+rax*2]
0x180003c40  mov     [r9+14h], ax
0x180003c45  movzx   eax, byte ptr [rcx+r11]
0x180003c4a  and     eax, 0Fh
0x180003c4d  movsxd  rcx, edx
0x180003c50  movzx   eax, ds:rva word_1800B0E90[r11+rax*2]
0x180003c59  mov     [r12+rcx*2+14h], ax
0x180003c5f  inc     r8d
0x180003c62  inc     edx
0x180003c64  cmp     r8d, 14h
0x180003c68  jb      short loc_180003C00
0x180003c6a  movsxd  rcx, edx
0x180003c6d  xor     edx, edx
0x180003c6f  mov     dword ptr [r12+rcx*2+14h], 7Dh ; '}'
0x180003c78  mov     [r12+62h], si
0x180003c7e  xchg    ax, ax
0x180003c80  cmp     ebx, 24h ; '$'
0x180003c83  jge     short loc_180003CE8
0x180003c85  movsxd  rax, edx
0x180003c88  movzx   ecx, byte ptr [rax+r11+0B0EC0h]
0x180003c91  movsxd  rax, ebx
0x180003c94  lea     r8, [r12+rax*2]
0x180003c98  cmp     cl, r14b
0x180003c9b  jz      loc_180003D87
0x180003ca1  movzx   eax, byte ptr [rcx+r11+0AD440h]
0x180003caa  lea     rcx, [rcx+0AD440h]
0x180003cb1  shr     rax, 4
0x180003cb5  inc     ebx
0x180003cb7  movzx   eax, ds:rva word_1800B0E90[r11+rax*2]
0x180003cc0  mov     [r8+62h], ax
0x180003cc5  movzx   eax, byte ptr [rcx+r11]
0x180003cca  and     eax, 0Fh
0x180003ccd  movsxd  rcx, ebx
0x180003cd0  movzx   eax, ds:rva word_1800B0E90[r11+rax*2]
0x180003cd9  mov     [r12+rcx*2+62h], ax
0x180003cdf  inc     edx
0x180003ce1  inc     ebx
0x180003ce3  cmp     edx, 14h
0x180003ce6  jb      short loc_180003C80
0x180003ce8  cmp     [rbp+350h+arg_20], 0
0x180003cef  movsxd  rcx, ebx
0x180003cf2  mov     dword ptr [r12+rcx*2+62h], 7Dh ; '}'
0x180003cfb  jz      loc_180003D9A
0x180003d01  test    r10b, r10b
0x180003d04  jnz     loc_180003D9A
0x180003d0a  mov     rax, cs:pfnBcp47BufferFromLcid
0x180003d11  lea     rdx, [rbp+350h+var_3B0]
0x180003d15  mov     r8d, 55h ; 'U'
0x180003d1b  mov     ecx, r13d
0x180003d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d23  test    eax, eax
0x180003d25  js      short loc_180003D9A
0x180003d27  mov     rax, cs:pfnAppendUserLanguages
0x180003d2e  lea     rdx, [rbp+350h+var_3B0]
0x180003d32  mov     ecx, 3Bh ; ';'
0x180003d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d3c  test    eax, eax
0x180003d3e  js      short loc_180003D9A
0x180003d40  xor     eax, eax
0x180003d42  mov     dword ptr [rsp+450h+phkResult], edi
0x180003d46  mov     r9d, r13d
0x180003d49  mov     [rbp+350h+var_300], ax
0x180003d4d  lea     r8, a04x08x; "%04X:%08X"
0x180003d54  mov     edx, 57h ; 'W'; unsigned __int64
0x180003d59  lea     rcx, [rbp+350h+var_300]; unsigned __int16 *
0x180003d5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003d62  mov     rax, cs:pfnAppendUserLanguageInputMethods
0x180003d69  lea     r8, [rbp+350h+var_300]
0x180003d6d  mov     edx, 3Bh ; ';'
0x180003d72  lea     rcx, [rbp+350h+var_3B0]
0x180003d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d7b  jmp     short loc_180003D9A
0x180003d7d  mov     [r9+14h], r14w
0x180003d82  jmp     loc_180003C5F
0x180003d87  mov     [r8+62h], r14w
0x180003d8c  jmp     loc_180003CDF
0x180003d91  test    rsi, rsi
0x180003d94  jnz     loc_1800040C8
0x180003d9a  mov     rcx, [rbp+350h+var_40]
0x180003da1  xor     rcx, rsp; StackCookie
0x180003da4  call    __security_check_cookie
0x180003da9  mov     rbx, [rsp+450h+arg_10]
0x180003db1  add     rsp, 420h
0x180003db8  pop     r15
0x180003dba  pop     r14
0x180003dbc  pop     r13
0x180003dbe  pop     r12
0x180003dc0  pop     rdi
0x180003dc1  pop     rsi
0x180003dc2  pop     rbp
0x180003dc3  retn
0x180003dc4  cmp     r13w, ax
0x180003dc8  jz      loc_180003B26
0x180003dce  mov     r9d, r13d
0x180003dd1  lea     r8, a08x_1; "%08x"
0x180003dd8  mov     edx, 9; unsigned __int64
0x180003ddd  lea     rcx, [rsp+450h+SubKey]; unsigned __int16 *
0x180003de2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003de7  mov     rax, [rdi]
0x180003dea  lea     r8, [rsp+450h+SubKey]
0x180003def  mov     r9d, 9
0x180003df5  lea     rdx, [rbp+350h+var_3C8]
0x180003df9  mov     rcx, rdi
0x180003dfc  mov     rax, [rax+8]
0x180003e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e05  test    eax, eax
0x180003e07  jz      loc_180003B26
0x180003e0d  jmp     short loc_180003D9A
0x180003e0f  cmp     eax, 5
0x180003e12  jnz     loc_180003B8E
0x180003e18  lea     rax, [rsp+450h+dwDisposition]
0x180003e1d  mov     [rsp+450h+dwDisposition], esi
0x180003e21  mov     [rsp+450h+lpdwDisposition], rax; lpdwDisposition
0x180003e26  lea     rdx, [rsp+450h+SubKey]; lpSubKey
0x180003e2b  lea     rax, [rsp+450h+var_3F8]
0x180003e30  xor     r9d, r9d; lpClass
0x180003e33  mov     [rsp+450h+var_418], rax; phkResult
0x180003e38  xor     r8d, r8d; Reserved
0x180003e3b  mov     [rsp+450h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180003e40  mov     rcx, r14; hKey
0x180003e43  mov     [rsp+450h+samDesired], 20019h; samDesired
0x180003e4b  mov     dword ptr [rsp+450h+phkResult], 4; dwOptions
0x180003e53  call    cs:__imp_RegCreateKeyExW
0x180003e59  mov     edi, eax
0x180003e5b  test    eax, eax
0x180003e5d  jz      loc_180003B87
0x180003e63  jmp     loc_180003B8E
0x180003e68  cmp     r8d, [r9+4]
0x180003e6c  jnb     loc_180003AF5
0x180003e72  cmp     [rax+10h], r12b
0x180003e76  movzx   edx, dl
0x180003e79  cmovnz  edx, ebx
0x180003e7c  cmp     [rax], r13w
0x180003e80  jz      short loc_180003EBA
0x180003e82  inc     r8d
0x180003e85  cmp     r8d, ecx
0x180003e88  jnb     short loc_180003EE6
0x180003e8a  mov     eax, r8d
0x180003e8d  imul    rax, 2BCh
0x180003e94  add     rax, [r9+8]
0x180003e98  jmp     loc_180003AEC
0x180003e9d  lea     rdx, [rsp+450h+hKey]; phkResult
0x180003ea2  mov     ecx, 20019h; samDesired
0x180003ea7  call    cs:__imp_RegOpenCurrentUser
0x180003ead  test    eax, eax
0x180003eaf  cmovz   r14, [rsp+450h+hKey]
0x180003eb5  jmp     loc_180003B5C
0x180003eba  cmp     [rax+4], esi
0x180003ebd  jnz     short loc_180003E82
0x180003ebf  mov     r12, rax
0x180003ec2  jmp     loc_180003AF5
0x180003ec7  inc     r8d
0x180003eca  cmp     r8d, ecx
0x180003ecd  jnb     short loc_180003EF8
0x180003ecf  mov     eax, r8d
0x180003ed2  imul    rdx, rax, 2BCh
0x180003ed9  add     rdx, [r9+8]
0x180003edd  jmp     short loc_180003EFA
0x180003edf  xor     eax, eax
0x180003ee1  jmp     loc_180003AE7
0x180003ee6  xor     eax, eax
0x180003ee8  jmp     loc_180003AEC
0x180003eed  test    r12, r12
0x180003ef0  jz      loc_180003AFD
0x180003ef6  jmp     short loc_180003EC7
0x180003ef8  xor     edx, edx
0x180003efa  test    rdx, rdx
0x180003efd  jz      loc_180003AFD
0x180003f03  cmp     r8d, [r9+4]
0x180003f07  jnb     loc_180003AFD
0x180003f0d  cmp     byte ptr [rdx+10h], 0
0x180003f11  jz      short loc_180003EC7
0x180003f13  mov     r8d, 5
0x180003f19  lea     rcx, [rbp+350h+var_300]
0x180003f1d  mov     r9d, r8d
0x180003f20  mov     rax, r12
0x180003f23  lea     rcx, [rcx+80h]
0x180003f2a  movups  xmm0, xmmword ptr [rax]
0x180003f2d  movups  xmm1, xmmword ptr [rax+10h]
0x180003f31  lea     rax, [rax+80h]
0x180003f38  movups  xmmword ptr [rcx-80h], xmm0
0x180003f3c  movups  xmm0, xmmword ptr [rax-60h]
0x180003f40  movups  xmmword ptr [rcx-70h], xmm1
0x180003f44  movups  xmm1, xmmword ptr [rax-50h]
0x180003f48  movups  xmmword ptr [rcx-60h], xmm0
0x180003f4c  movups  xmm0, xmmword ptr [rax-40h]
0x180003f50  movups  xmmword ptr [rcx-50h], xmm1
0x180003f54  movups  xmm1, xmmword ptr [rax-30h]
0x180003f58  movups  xmmword ptr [rcx-40h], xmm0
0x180003f5c  movups  xmm0, xmmword ptr [rax-20h]
0x180003f60  movups  xmmword ptr [rcx-30h], xmm1
0x180003f64  movups  xmm1, xmmword ptr [rax-10h]
0x180003f68  movups  xmmword ptr [rcx-20h], xmm0
0x180003f6c  movups  xmmword ptr [rcx-10h], xmm1
0x180003f70  sub     r9, rbx
0x180003f73  jnz     short loc_180003F23
0x180003f75  movups  xmm0, xmmword ptr [rax]
0x180003f78  movups  xmm1, xmmword ptr [rax+10h]
0x180003f7c  movups  xmmword ptr [rcx], xmm0
0x180003f7f  movups  xmm0, xmmword ptr [rax+20h]
  ... truncated ...
```
