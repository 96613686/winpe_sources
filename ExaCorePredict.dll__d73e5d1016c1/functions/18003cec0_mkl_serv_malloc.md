# mkl_serv_malloc

- ea: `0x18003cec0`
- end: `0x18003d720`
- name: `mkl_serv_malloc`
- size: `2144`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca80`
- `0x18000d570`
- `0x18003c0c0`

## callees

- `0x18003cec0`
- `0x18003d720`
- `0x180054070`
- `0x180054080`
- `0x180055ce0`
- `0x180055e50`
- `0x180056180`
- `0x180060de0`
- `0x180061160`
- `0x180077140`
- `0x1800775d0`
- `0x1800777c0`
- `0x180077840`
- `0x180077850`
- `0x1832ce3b0`
- `0x1832dbf90`
- `0x1832dbfe0`
- `0x1832dc0b0`
- `0x1832dc0c0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003d550`
- `KERNEL32!GetProcAddress` at `0x18003d567`
- `KERNEL32!GetProcAddress` at `0x18003d57e`
- `KERNEL32!GetProcAddress` at `0x18003d550`
- `KERNEL32!GetProcAddress` at `0x18003d567`
- `KERNEL32!GetProcAddress` at `0x18003d57e`
- `KERNEL32!TlsAlloc` at `0x18003d1fc`
- `KERNEL32!TlsAlloc` at `0x18003d1fc`
- `KERNEL32!TlsGetValue` at `0x18003d0c5`
- `KERNEL32!TlsGetValue` at `0x18003d0c5`
- `KERNEL32!LoadLibraryA` at `0x18003d43f`
- `KERNEL32!LoadLibraryA` at `0x18003d538`
- `KERNEL32!LoadLibraryA` at `0x18003d43f`
- `KERNEL32!LoadLibraryA` at `0x18003d538`

## pseudocode

```c
unsigned __int64 __fastcall mkl_serv_malloc(unsigned __int64 a1, int a2)
{
  __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  int v7; // r14d
  char v8; // r13
  unsigned __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // r9
  int v12; // r13d
  unsigned __int64 v13; // rdi
  int v14; // edx
  unsigned int Value; // eax
  __int64 *v16; // rax
  __int64 v17; // rsi
  __int64 v18; // rsi
  __int64 v19; // rsi
  unsigned __int64 v20; // rdx
  int v21; // esi
  int device_count; // r14d
  int v23; // esi
  __int64 v24; // rcx
  char *v25; // r13
  __int64 v26; // rax
  __int64 v27; // rdi
  char v28; // al
  HMODULE LibraryA; // rdi
  __int64 v30; // r14
  __int64 v31; // rax
  __int64 v32; // rdi
  char v33; // al
  FARPROC ProcAddress; // rax
  int v35; // eax
  int v36; // eax
  char v38[16]; // [rsp+20h] [rbp-548h] BYREF
  _OWORD v39[2]; // [rsp+30h] [rbp-538h]
  CHAR v40[256]; // [rsp+50h] [rbp-518h] BYREF
  __int128 v41; // [rsp+150h] [rbp-418h]
  CHAR LibFileName[256]; // [rsp+160h] [rbp-408h] BYREF
  int v43; // [rsp+260h] [rbp-308h]
  char v44[696]; // [rsp+268h] [rbp-300h] BYREF
  char String[8]; // [rsp+520h] [rbp-48h] BYREF

  if ( !a1 )
    return 0;
  if ( dword_1836E1210 == -1 )
  {
    mkl_serv_lock(&unk_1836E8CFC);
    if ( dword_1836E1210 != -1 )
    {
LABEL_65:
      mkl_serv_unlock(&unk_1836E8CFC);
      goto LABEL_4;
    }
    mkl_serv_lock(&unk_1836E8D00);
    if ( dword_1836E1214 == -1 )
    {
      dword_1836E1218 = (int)mkl_serv_getenv("MKL_DISABLE_FAST_MM", &v38[8], 32) > 0;
      if ( (int)mkl_serv_getenv("MKL_FAST_MEMORY_LIMIT", &v38[8], 32) > 0 )
      {
        v36 = atol_0(&v38[8]);
        if ( v36 < 0 )
          qword_1836E1200 = -1;
        else
          qword_1836E1200 = (__int64)v36 << 20;
      }
      dword_1836E1214 = 1;
    }
    mkl_serv_unlock(&unk_1836E8D00);
    v24 = 0x708000000LL;
    while ( (v24 & _intel_mkl_feature_indicator_x) != v24 )
    {
      if ( _intel_mkl_feature_indicator_x )
        goto LABEL_90;
      _intel_mkl_features_init_x();
    }
    v25 = off_1836E1208;
    v26 = 256;
    v43 = _mm_cvtsi128_si32((__m128i)0LL);
    do
    {
      *(_OWORD *)&LibFileName[v26 - 16] = 0;
      *(_OWORD *)&v40[v26 + 240] = 0;
      *(_OWORD *)&v40[v26 + 224] = 0;
      *(_OWORD *)&v40[v26 + 208] = 0;
      v26 -= 64;
    }
    while ( v26 );
    v27 = 0;
    if ( mkl_serv_strnlen_s(v25, 260) )
    {
      while ( 1 )
      {
        v28 = v25[v27];
        if ( v28 == 47 || v28 == 92 )
          break;
        if ( ++v27 >= (unsigned __int64)mkl_serv_strnlen_s(v25, 260) )
          goto LABEL_75;
      }
      LibraryA = 0;
    }
    else
    {
LABEL_75:
      mkl_serv_strncpy_s(LibFileName, 260, byte_1836E8A40, 260);
      mkl_serv_strncat_s(LibFileName, 260, v25, 260);
      LibraryA = LoadLibraryA(LibFileName);
      if ( LibraryA )
      {
LABEL_85:
        if ( LibraryA )
        {
          qword_1836E8C68 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                      LibraryA,
                                                                                      "hbw_posix_memalign_psize");
          qword_1836E8C70 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(LibraryA, "hbw_malloc");
          ProcAddress = GetProcAddress(LibraryA, "hbw_free");
          qword_1836E8C78 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
          if ( qword_1836E8C68 )
          {
            if ( qword_1836E8C70 && ProcAddress )
            {
              v35 = 1;
              goto LABEL_91;
            }
          }
        }
LABEL_90:
        v35 = 0;
LABEL_91:
        dword_1836E8CF0 = v35;
        if ( i_malloc == malloc_0 && i_free == free_0 && i_realloc == realloc_0 && calloc_0 == i_calloc )
        {
          qword_1836E8C80 = (__int64 (__fastcall *)(_QWORD))sub_18003BEE0;
          qword_1836E8C88 = (__int64)sub_18003BAF0;
          qword_1836E8C90 = (__int64 (__fastcall *)(_QWORD))sub_18003C000;
          qword_1836E8C98 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))sub_18003BEE0;
          qword_1836E8CA0 = (__int64 (__fastcall *)(_QWORD))sub_18003C000;
        }
        else
        {
          qword_1836E8C80 = (__int64 (__fastcall *)(_QWORD))i_malloc;
          qword_1836E8C88 = (__int64)i_realloc;
          qword_1836E8C90 = (__int64 (__fastcall *)(_QWORD))i_free;
          qword_1836E8C98 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))i_malloc;
          qword_1836E8CA0 = (__int64 (__fastcall *)(_QWORD))i_free;
        }
        dword_1836E1210 = 1;
        goto LABEL_65;
      }
    }
    v30 = mkl_serv_strnlen_s(byte_1836E8A40, 260);
    if ( v30 != mkl_serv_strnlen_s(byte_1836E8B60, 260) || strncmp_0(byte_1836E8A40, byte_1836E8B60, 0x104u) )
    {
      v31 = 16;
      LODWORD(v41) = _mm_cvtsi128_si32((__m128i)0LL);
      do
      {
        v39[v31 + 1] = 0;
        v39[v31] = 0;
        *(_OWORD *)&v38[v31 * 16] = 0;
        *(_OWORD *)&v38[v31 * 16 - 16] = 0;
        v31 -= 4;
      }
      while ( v31 * 16 );
      v32 = 0;
      if ( mkl_serv_strnlen_s(v25, 260) )
      {
        while ( 1 )
        {
          v33 = v25[v32];
          if ( v33 == 47 || v33 == 92 )
            break;
          if ( ++v32 >= (unsigned __int64)mkl_serv_strnlen_s(v25, 260) )
            goto LABEL_84;
        }
        LibraryA = 0;
      }
      else
      {
LABEL_84:
        mkl_serv_strncpy_s(v40, 260, byte_1836E8B60, 260);
        mkl_serv_strncat_s(v40, 260, v25, 260);
        LibraryA = LoadLibraryA(v40);
      }
    }
    goto LABEL_85;
  }
LABEL_4:
  if ( a2 < 64 )
  {
    v5 = 64;
  }
  else
  {
    v5 = (unsigned int)a2;
    if ( (a2 & (a2 - 1)) != 0 )
      v5 = 64;
  }
  v6 = a1 + v5 + 24;
  if ( a1 > v6 )
    return 0;
  if ( (char *)qword_1836E8C80 == (char *)sub_18003BEE0 )
  {
    *(_QWORD *)v38 = 0;
    v7 = 0;
    v8 = 0;
    v9 = a1 + v5 + 56;
    if ( dword_1836E8CF0
      && (qword_1836E1200 == -1 || qword_1836E1200 && (mkl_serv_lock(&unk_1836E8CF4), v9 < qword_1836E1200)) )
    {
      v7 = 1;
      v8 = 1;
      if ( (unsigned int)qword_1836E8C68(v38, 0x200000, a1 + v5 + 56, 2) )
      {
        *(_QWORD *)v38 = qword_1836E8C70(a1 + v5 + 56);
        if ( !*(_QWORD *)v38 )
        {
          *(_QWORD *)v38 = malloc_0(a1 + v5 + 56);
          v8 = 0;
          v7 = 0;
        }
      }
    }
    else
    {
      *(_QWORD *)v38 = malloc_0(a1 + v5 + 56);
    }
    if ( dword_1836E8CF0 && qword_1836E1200 != -1 && qword_1836E1200 )
    {
      if ( v8 )
        qword_1836E1200 = qword_1836E1200 - v6 - 32;
      mkl_serv_unlock(&unk_1836E8CF4);
    }
    v10 = *(_QWORD *)v38;
    if ( !*(_QWORD *)v38 )
      return 0;
    v11 = *(_QWORD *)v38 + 32LL;
    **(_QWORD **)v38 = *(_QWORD *)v38;
    *(_QWORD *)(v10 + 16) = v9;
    *(_QWORD *)(v10 + 24) = 4096;
    *(_DWORD *)(v10 + 8) = v7;
  }
  else
  {
    v11 = qword_1836E8C80(a1 + v5 + 24);
  }
  if ( v11 )
  {
    v12 = v5;
    v13 = ~(unsigned __int64)(unsigned int)(v5 - 1) & (v5 + v11 + 24);
    *(_QWORD *)(v13 - 24) = v11;
    *(_QWORD *)(v13 - 16) = v6;
    if ( dword_1836E1220 == 3 )
    {
      *(_QWORD *)String = 0;
      mkl_serv_getenv("MKL_MIC_REGISTER_MEMORY", String, 7);
      mkl_serv_lock(&unk_1836E8D08);
      if ( dword_1836E1220 == 3 )
        dword_1836E1220 = atoi_0(String) != 0;
      mkl_serv_unlock(&unk_1836E8D08);
    }
    if ( dword_1836E1220 != 1 || (unsigned int)mkl_aa_fw_enter(v44, "mkl_malloc", 1) )
    {
      v14 = 0;
    }
    else
    {
      device_count = mkl_ueaa_get_device_count();
      v23 = 1;
      if ( device_count > 0 )
      {
        do
          mkl_ueaa_register(v13, a1, (unsigned int)v23++);
        while ( v23 <= device_count );
      }
      mkl_aa_fw_leave(v44);
      v14 = 1;
    }
    *(_DWORD *)(v13 - 8) = v14;
    *(_DWORD *)(v13 - 4) = v12;
    if ( (dword_1836E8CBC & 1) == 0 )
    {
      mkl_serv_lock(&unk_1836E8CB8);
      if ( (dword_1836E8CBC & 1) == 0 )
      {
        dwTlsIndex = TlsAlloc();
        if ( dwTlsIndex != -1 )
        {
          qword_1836E8CB0 = (__int64)sub_180040370;
          dword_1836E8CBC |= 1u;
        }
        mkl_serv_core_register_cleanup(sub_180061240, &dwTlsIndex);
      }
      mkl_serv_unlock(&unk_1836E8CB8);
    }
    if ( (dword_1836E8CBC & 1) != 0 )
      Value = (unsigned int)TlsGetValue(dwTlsIndex);
    else
      Value = 0;
    v16 = (__int64 *)sub_18003D720(Value, 1, 0);
    if ( v16 )
    {
      v17 = *v16;
      if ( *v16 )
      {
        *(_QWORD *)(v17 + 208) += *(_QWORD *)(v13 - 16);
        ++*(_DWORD *)(v17 + 204);
      }
      v18 = *((int *)v16 - 2);
      if ( v18 <= 0 || v18 > 1024 )
        _InterlockedExchangeAdd(dword_1836D11C0, 0xFFFFFFFE);
      else
        dword_1836D11C0[16 * v18] = 0;
    }
    v19 = *(_QWORD *)(v13 - 16);
    if ( dword_1836E121C == 1 )
    {
      mkl_serv_lock(&unk_1836E8D04);
      if ( dword_1836E121C == 1 )
      {
        v20 = v19 + qword_1836E8CC0;
        v21 = dword_1836E8CC8 + 1;
        qword_1836E8CC0 = v20;
        ++dword_1836E8CC8;
        if ( v20 > qword_1836E8CD0 )
        {
          qword_1836E8CD0 = v20;
          dword_1836E8CD8 = v21;
        }
      }
      mkl_serv_unlock(&unk_1836E8D04);
    }
    return v13;
  }
  return 0;
}

```

## disassembly

```asm
0x18003cec0  push    rsi
0x18003cec1  push    rdi
0x18003cec2  push    r12
0x18003cec4  push    r13
0x18003cec6  push    r14
0x18003cec8  push    r15
0x18003ceca  sub     rsp, 538h
0x18003ced1  mov     r12, rcx
0x18003ced4  mov     rax, cs:__security_cookie
0x18003cedb  mov     esi, edx
0x18003cedd  xor     rax, rsp
0x18003cee0  mov     [rsp+568h+var_40], rax
0x18003cee8  cmp     r12, 1
0x18003ceec  jnb     short loc_18003CF12
0x18003ceee  mov     rcx, [rsp+568h+var_40]
0x18003cef6  xor     rcx, rsp; StackCookie
0x18003cef9  call    __security_check_cookie
0x18003cefe  xor     eax, eax
0x18003cf00  add     rsp, 538h
0x18003cf07  pop     r15
0x18003cf09  pop     r14
0x18003cf0b  pop     r13
0x18003cf0d  pop     r12
0x18003cf0f  pop     rdi
0x18003cf10  pop     rsi
0x18003cf11  retn
0x18003cf12  mov     eax, cs:dword_1836E1210
0x18003cf18  cmp     eax, 0FFFFFFFFh
0x18003cf1b  jz      loc_18003D31D
0x18003cf21  cmp     esi, 40h ; '@'
0x18003cf24  jl      short loc_18003CF38
0x18003cf26  mov     edi, esi
0x18003cf28  lea     eax, [rsi-1]
0x18003cf2b  mov     ecx, 40h ; '@'
0x18003cf30  test    eax, esi
0x18003cf32  cmovnz  rdi, rcx
0x18003cf36  jmp     short loc_18003CF3D
0x18003cf38  mov     edi, 40h ; '@'
0x18003cf3d  lea     rsi, [r12+rdi+18h]
0x18003cf42  cmp     r12, rsi
0x18003cf45  ja      short loc_18003CEEE
0x18003cf47  lea     rax, sub_18003BEE0
0x18003cf4e  mov     r8, cs:qword_1836E8C80
0x18003cf55  cmp     r8, rax
0x18003cf58  jnz     loc_18003D04E
0x18003cf5e  mov     qword ptr [rsp+568h+var_548], 0
0x18003cf67  xor     r14d, r14d
0x18003cf6a  xor     r13b, r13b
0x18003cf6d  lea     r15, [rsi+20h]
0x18003cf71  cmp     cs:dword_1836E8CF0, 0
0x18003cf78  jz      short loc_18003CFE0
0x18003cf7a  mov     rax, cs:qword_1836E1200
0x18003cf81  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003cf85  jz      short loc_18003CFA1
0x18003cf87  test    rax, rax
0x18003cf8a  jz      short loc_18003CFE0
0x18003cf8c  lea     rcx, unk_1836E8CF4
0x18003cf93  call    mkl_serv_lock
0x18003cf98  cmp     r15, cs:qword_1836E1200
0x18003cf9f  jnb     short loc_18003CFE0
0x18003cfa1  mov     edx, 200000h
0x18003cfa6  lea     rcx, [rsp+568h+var_548]
0x18003cfab  mov     r8, r15
0x18003cfae  mov     r9d, 2
0x18003cfb4  mov     r14d, 1
0x18003cfba  mov     r13b, 1
0x18003cfbd  call    cs:qword_1836E8C68
0x18003cfc3  test    eax, eax
0x18003cfc5  jz      short loc_18003CFED
0x18003cfc7  mov     rcx, r15
0x18003cfca  call    cs:qword_1836E8C70
0x18003cfd0  mov     qword ptr [rsp+568h+var_548], rax
0x18003cfd5  test    rax, rax
0x18003cfd8  jz      loc_18003D168
0x18003cfde  jmp     short loc_18003CFED
0x18003cfe0  mov     rcx, r15; Size
0x18003cfe3  call    malloc_0
0x18003cfe8  mov     qword ptr [rsp+568h+var_548], rax
0x18003cfed  cmp     cs:dword_1836E8CF0, 0
0x18003cff4  jz      short loc_18003D027
0x18003cff6  mov     rax, cs:qword_1836E1200
0x18003cffd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d001  jz      short loc_18003D027
0x18003d003  test    rax, rax
0x18003d006  jz      short loc_18003D027
0x18003d008  test    r13b, r13b
0x18003d00b  jz      short loc_18003D01B
0x18003d00d  sub     rax, rsi
0x18003d010  add     rax, 0FFFFFFFFFFFFFFE0h
0x18003d014  mov     cs:qword_1836E1200, rax
0x18003d01b  lea     rcx, unk_1836E8CF4
0x18003d022  call    mkl_serv_unlock
0x18003d027  mov     rax, qword ptr [rsp+568h+var_548]
0x18003d02c  test    rax, rax
0x18003d02f  jz      loc_18003D141
0x18003d035  lea     r9, [rax+20h]
0x18003d039  mov     [rax], rax
0x18003d03c  mov     [r9-10h], r15
0x18003d040  mov     qword ptr [r9-8], 1000h
0x18003d048  mov     [r9-18h], r14d
0x18003d04c  jmp     short loc_18003D057
0x18003d04e  mov     rcx, rsi
0x18003d051  call    r8 ; qword_1836E8C80
0x18003d054  mov     r9, rax
0x18003d057  test    r9, r9
0x18003d05a  jz      loc_18003D141
0x18003d060  mov     r13d, edi
0x18003d063  lea     rdi, [rdi+r9+18h]
0x18003d068  lea     r8d, [r13-1]
0x18003d06c  not     r8
0x18003d06f  and     rdi, r8
0x18003d072  mov     [rdi-18h], r9
0x18003d076  mov     [rdi-10h], rsi
0x18003d07a  mov     esi, cs:dword_1836E1220
0x18003d080  cmp     esi, 3
0x18003d083  jz      loc_18003D2A6
0x18003d089  mov     esi, cs:dword_1836E1220
0x18003d08f  cmp     esi, 1
0x18003d092  jz      loc_18003D246
0x18003d098  xor     edx, edx
0x18003d09a  mov     [rdi-8], edx
0x18003d09d  mov     [rdi-4], r13d
0x18003d0a1  mov     edx, cs:dword_1836E8CBC
0x18003d0a7  test    dl, 1
0x18003d0aa  jz      loc_18003D1DA
0x18003d0b0  mov     edx, cs:dword_1836E8CBC
0x18003d0b6  test    dl, 1
0x18003d0b9  jnz     short loc_18003D0BF
0x18003d0bb  xor     eax, eax
0x18003d0bd  jmp     short loc_18003D0CB
0x18003d0bf  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003d0c5  call    cs:__imp_TlsGetValue
0x18003d0cb  mov     ecx, eax
0x18003d0cd  mov     edx, 1
0x18003d0d2  xor     r8d, r8d
0x18003d0d5  call    sub_18003D720
0x18003d0da  test    rax, rax
0x18003d0dd  jz      short loc_18003D132
0x18003d0df  mov     rsi, [rax]
0x18003d0e2  test    rsi, rsi
0x18003d0e5  jz      short loc_18003D0F8
0x18003d0e7  mov     rdx, [rdi-10h]
0x18003d0eb  add     [rsi+0D0h], rdx
0x18003d0f2  inc     dword ptr [rsi+0CCh]
0x18003d0f8  movsxd  rsi, dword ptr [rax-8]
0x18003d0fc  test    rsi, rsi
0x18003d0ff  jle     short loc_18003D122
0x18003d101  cmp     rsi, 400h
0x18003d108  jg      short loc_18003D122
0x18003d10a  shl     rsi, 6
0x18003d10e  lea     rdx, cs:180000000h
0x18003d115  mov     rva dword_1836D11C0[rdx+rsi], 0
0x18003d120  jmp     short loc_18003D132
0x18003d122  lea     rdx, dword_1836D11C0
0x18003d129  mov     eax, 0FFFFFFFEh
0x18003d12e  lock xadd [rdx], eax
0x18003d132  mov     rsi, [rdi-10h]
0x18003d136  cmp     cs:dword_1836E121C, 1
0x18003d13d  jz      short loc_18003D180
0x18003d13f  jmp     short loc_18003D143
0x18003d141  xor     edi, edi
0x18003d143  mov     rcx, [rsp+568h+var_40]
0x18003d14b  xor     rcx, rsp; StackCookie
0x18003d14e  call    __security_check_cookie
0x18003d153  mov     rax, rdi
0x18003d156  add     rsp, 538h
0x18003d15d  pop     r15
0x18003d15f  pop     r14
0x18003d161  pop     r13
0x18003d163  pop     r12
0x18003d165  pop     rdi
0x18003d166  pop     rsi
0x18003d167  retn
0x18003d168  mov     rcx, r15; Size
0x18003d16b  call    malloc_0
0x18003d170  mov     qword ptr [rsp+568h+var_548], rax
0x18003d175  xor     r13b, r13b
0x18003d178  xor     r14d, r14d
0x18003d17b  jmp     loc_18003CFED
0x18003d180  lea     rcx, unk_1836E8D04
0x18003d187  call    mkl_serv_lock
0x18003d18c  cmp     cs:dword_1836E121C, 1
0x18003d193  jz      short loc_18003D1A3
0x18003d195  lea     rcx, unk_1836E8D04
0x18003d19c  call    mkl_serv_unlock
0x18003d1a1  jmp     short loc_18003D143
0x18003d1a3  mov     rdx, cs:qword_1836E8CC0
0x18003d1aa  add     rdx, rsi
0x18003d1ad  mov     esi, cs:dword_1836E8CC8
0x18003d1b3  inc     esi
0x18003d1b5  mov     cs:qword_1836E8CC0, rdx
0x18003d1bc  mov     cs:dword_1836E8CC8, esi
0x18003d1c2  cmp     rdx, cs:qword_1836E8CD0
0x18003d1c9  jbe     short loc_18003D195
0x18003d1cb  mov     cs:qword_1836E8CD0, rdx
0x18003d1d2  mov     cs:dword_1836E8CD8, esi
0x18003d1d8  jmp     short loc_18003D195
0x18003d1da  lea     rcx, unk_1836E8CB8
0x18003d1e1  call    mkl_serv_lock
0x18003d1e6  mov     edx, cs:dword_1836E8CBC
0x18003d1ec  test    dl, 1
0x18003d1ef  jnz     short loc_18003D235
0x18003d1f1  mov     edx, cs:dword_1836E8CBC
0x18003d1f7  test    dl, 1
0x18003d1fa  jnz     short loc_18003D222
0x18003d1fc  call    cs:__imp_TlsAlloc
0x18003d202  mov     cs:dwTlsIndex, eax
0x18003d208  cmp     eax, 0FFFFFFFFh
0x18003d20b  jz      short loc_18003D222
0x18003d20d  lea     rdx, sub_180040370
0x18003d214  mov     cs:qword_1836E8CB0, rdx
0x18003d21b  or      cs:dword_1836E8CBC, 1
0x18003d222  lea     rcx, sub_180061240
0x18003d229  lea     rdx, dwTlsIndex
0x18003d230  call    mkl_serv_core_register_cleanup
0x18003d235  lea     rcx, unk_1836E8CB8
0x18003d23c  call    mkl_serv_unlock
0x18003d241  jmp     loc_18003D0B0
0x18003d246  lea     rdx, aMklMalloc; "mkl_malloc"
0x18003d24d  lea     rcx, [rsp+568h+var_300]
0x18003d255  mov     r8d, 1
0x18003d25b  call    mkl_aa_fw_enter
0x18003d260  test    eax, eax
0x18003d262  jnz     loc_18003D098
0x18003d268  call    mkl_ueaa_get_device_count
0x18003d26d  mov     r14d, eax
0x18003d270  mov     esi, 1
0x18003d275  test    r14d, r14d
0x18003d278  jle     short loc_18003D28F
0x18003d27a  mov     rcx, rdi
0x18003d27d  mov     rdx, r12
0x18003d280  mov     r8d, esi
0x18003d283  call    mkl_ueaa_register
0x18003d288  inc     esi
0x18003d28a  cmp     esi, r14d
0x18003d28d  jle     short loc_18003D27A
0x18003d28f  lea     rcx, [rsp+568h+var_300]
0x18003d297  call    mkl_aa_fw_leave
0x18003d29c  mov     edx, 1
0x18003d2a1  jmp     loc_18003D09A
0x18003d2a6  mov     qword ptr [rsp+568h+String], 0
0x18003d2b2  lea     rcx, aMklMicRegister; "MKL_MIC_REGISTER_MEMORY"
0x18003d2b9  lea     rdx, [rsp+568h+String]
0x18003d2c1  mov     r8d, 7
0x18003d2c7  call    mkl_serv_getenv
0x18003d2cc  lea     rcx, unk_1836E8D08
0x18003d2d3  call    mkl_serv_lock
0x18003d2d8  mov     esi, cs:dword_1836E1220
0x18003d2de  cmp     esi, 3
0x18003d2e1  jz      short loc_18003D2F4
0x18003d2e3  lea     rcx, unk_1836E8D08
0x18003d2ea  call    mkl_serv_unlock
0x18003d2ef  jmp     loc_18003D089
0x18003d2f4  lea     rcx, [rsp+568h+String]; String
0x18003d2fc  call    atoi_0
0x18003d301  test    eax, eax
0x18003d303  jz      short loc_18003D311
0x18003d305  mov     cs:dword_1836E1220, 1
0x18003d30f  jmp     short loc_18003D2E3
0x18003d311  mov     cs:dword_1836E1220, 0
0x18003d31b  jmp     short loc_18003D2E3
0x18003d31d  lea     rcx, unk_1836E8CFC
0x18003d324  call    mkl_serv_lock
0x18003d329  mov     eax, cs:dword_1836E1210
0x18003d32f  cmp     eax, 0FFFFFFFFh
0x18003d332  jz      short loc_18003D345
0x18003d334  lea     rcx, unk_1836E8CFC
0x18003d33b  call    mkl_serv_unlock
0x18003d340  jmp     loc_18003CF21
0x18003d345  lea     rcx, unk_1836E8D00
0x18003d34c  call    mkl_serv_lock
0x18003d351  cmp     cs:dword_1836E1214, 0FFFFFFFFh
0x18003d358  jz      loc_18003D68E
0x18003d35e  lea     rcx, unk_1836E8D00
0x18003d365  call    mkl_serv_unlock
0x18003d36a  mov     rcx, 708000000h
0x18003d374  mov     rax, cs:__intel_mkl_feature_indicator_x
0x18003d37b  and     rax, rcx
0x18003d37e  cmp     rax, rcx
0x18003d381  jnz     loc_18003D676
0x18003d387  mov     r13, cs:off_1836E1208; "memkind.dll"
0x18003d38e  mov     eax, 100h
0x18003d393  pxor    xmm0, xmm0
0x18003d397  movd    [rsp+568h+var_308], xmm0
0x18003d3a0  movaps  [rsp+rax+568h+var_418], xmm0
0x18003d3a8  movaps  [rsp+rax+568h+var_428], xmm0
0x18003d3b0  movaps  [rsp+rax+568h+var_438], xmm0
0x18003d3b8  movaps  [rsp+rax+568h+var_448], xmm0
0x18003d3c0  sub     rax, 40h ; '@'
0x18003d3c4  jnz     short loc_18003D3A0
0x18003d3c6  mov     rcx, r13
0x18003d3c9  mov     edx, 104h
0x18003d3ce  xor     edi, edi
0x18003d3d0  call    mkl_serv_strnlen_s
0x18003d3d5  test    rax, rax
0x18003d3d8  jbe     short loc_18003D403
0x18003d3da  mov     al, [rdi+r13]
0x18003d3de  cmp     al, 2Fh ; '/'
0x18003d3e0  jz      loc_18003D66F
0x18003d3e6  cmp     al, 5Ch ; '\'
  ... truncated ...
```
