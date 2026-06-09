# sub_1800EC1DC

- ea: `0x1800ec1dc`
- end: `0x1800ec890`
- name: `sub_1800EC1DC`
- size: `1716`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x1800eb1e0`
- `0x1800ec1dc`

## callees

- `0x1800048f0`
- `0x180004bec`
- `0x1800050ac`
- `0x1800050ec`
- `0x1800057e4`
- `0x180018fb8`
- `0x18001916c`
- `0x18001d71c`
- `0x18001d80c`
- `0x180021c34`
- `0x180028810`
- `0x180028894`
- `0x18002ea54`
- `0x180037dc4`
- `0x18003dd80`
- `0x18005f060`
- `0x18006064c`
- `0x1800641ac`
- `0x18007b0f4`
- `0x18008f24c`
- `0x1800e492c`
- `0x1800eb184`
- `0x1800eb300`
- `0x1800ebf18`
- `0x1800ec1dc`
- `0x180135010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ec586`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ec586`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ec5f3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ec5f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ec2c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ec4fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ec2c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ec4fd`

## string_xrefs

- `0x1800ec7cc`: `Attempting to use an invalid handle.`
- `0x1800ec7fd`: `Attempting to use an invalid handle.`
- `0x1800ec82e`: `Attempting to use an invalid handle.`
- `0x1800ec85f`: `Attempting to use an invalid handle.`

## pseudocode

```c
bool __fastcall sub_1800EC1DC(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // r15
  _BYTE *v8; // rsi
  __int64 v9; // rsi
  __int128 *v10; // rcx
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v20; // rbx
  const WCHAR *v21; // rdx
  unsigned int InfoKeyW; // eax
  WCHAR *v23; // rsi
  DWORD i; // r13d
  unsigned int v25; // r15d
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  const WCHAR *v29; // r9
  unsigned __int64 v30; // r8
  _QWORD *v31; // rax
  unsigned __int64 v32; // r8
  bool v33; // bl
  _QWORD Src[4]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD pExceptionObject[4]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR *v36; // [rsp+C0h] [rbp-40h]
  _locale_t cbMaxSubKeyLen; // [rsp+C8h] [rbp-38h] BYREF
  tagPOINT hKey; // [rsp+D0h] [rbp-30h] BYREF
  tagPOINT phkResult; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v40; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v41; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v42; // [rsp+F8h] [rbp-8h]
  void **v43; // [rsp+100h] [rbp+0h] BYREF
  int v44; // [rsp+108h] [rbp+8h]
  _QWORD v45[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v46[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v47[4]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v48[4]; // [rsp+170h] [rbp+70h] BYREF
  void **v49; // [rsp+190h] [rbp+90h] BYREF
  int v50; // [rsp+198h] [rbp+98h]
  _QWORD v51[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v52[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD v53[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  _QWORD v54[4]; // [rsp+200h] [rbp+100h] BYREF
  void (__fastcall ***v55)(_QWORD, __int64); // [rsp+220h] [rbp+120h]
  int v56; // [rsp+228h] [rbp+128h]
  int v57; // [rsp+22Ch] [rbp+12Ch]
  char v58; // [rsp+230h] [rbp+130h]

  v6 = *(_QWORD *)(a1 + 152);
  v7 = *(_QWORD *)(a1 + 144);
  v8 = (_BYTE *)(a1 + 216);
  if ( !((v6 - v7) >> 5) || *v8 )
  {
    hKey = 0;
    v20 = a2 + 80;
    if ( *(_QWORD *)(a2 + 104) <= 7u )
      v21 = (const WCHAR *)(a2 + 80);
    else
      v21 = *(const WCHAR **)v20;
    InfoKeyW = RegOpenKeyExW(HKEY_CURRENT_USER, v21, 0, 0xF003Fu, (PHKEY)&hKey);
    if ( InfoKeyW )
      goto LABEL_32;
    if ( !*(_QWORD *)&hKey )
    {
      sub_18001D80C(Src, L"Attempting to use an invalid handle.");
      sub_18002EA54(pExceptionObject, Src);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    sub_1800EBF18(hKey);
    if ( *v8 == 1 )
    {
      LODWORD(cbMaxSubKeyLen) = 0;
      if ( !*(_QWORD *)&hKey )
      {
        sub_18001D80C(Src, L"Attempting to use an invalid handle.");
        sub_18002EA54(pExceptionObject, Src);
        throw (Uev::SmartHandleException *)pExceptionObject;
      }
      InfoKeyW = RegQueryInfoKeyW(*(HKEY *)&hKey, 0, 0, 0, 0, (LPDWORD)&cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( InfoKeyW )
      {
LABEL_32:
        sub_1800EB184(a2 + 80, InfoKeyW);
        sub_1800641AC(&hKey);
        return 0;
      }
      LODWORD(cbMaxSubKeyLen) = (_DWORD)cbMaxSubKeyLen + 2;
      v23 = (WCHAR *)sub_1800050EC(saturated_mul((unsigned int)cbMaxSubKeyLen, 2u));
      v36 = v23;
      for ( i = 0; ; ++i )
      {
        phkResult.x = (int)cbMaxSubKeyLen;
        if ( !*(_QWORD *)&hKey )
        {
          sub_18001D80C(Src, L"Attempting to use an invalid handle.");
          sub_18002EA54(pExceptionObject, Src);
          throw (Uev::SmartHandleException *)pExceptionObject;
        }
        v25 = RegEnumKeyExW(*(HKEY *)&hKey, i, v23, (LPDWORD)&phkResult, 0, 0, 0, 0);
        if ( v25 == 259 )
          break;
        v40 = 0;
        if ( v25 )
        {
          v41 = 0;
          v42 = 0;
          v32 = -1;
          do
            ++v32;
          while ( v23[v32] );
          sub_18001916C(&v40, v23, v32);
          sub_1800EB184(&v40, v25);
          sub_180028810(&v40);
        }
        else
        {
          v41 = 0;
          v42 = 0;
          sub_18001916C(&v40, &Data, 0);
          v28 = *(_QWORD *)(v20 + 16);
          if ( v28 == 0x7FFFFFFFFFFFFFFELL )
            sub_180028894();
          if ( *(_QWORD *)(v20 + 24) <= 7u )
            v29 = (const WCHAR *)v20;
          else
            v29 = *(const WCHAR **)v20;
          sub_180037DC4((char *)Src, v26, v27, v29, v28, (void *)L"\\", 1);
          v30 = -1;
          do
            ++v30;
          while ( v23[v30] );
          v31 = sub_180018FB8(Src, v23, v30);
          pExceptionObject[0] = *(_OWORD *)v31;
          pExceptionObject[1] = *((_OWORD *)v31 + 1);
          v31[2] = 0;
          v31[3] = 7;
          *(_WORD *)v31 = 0;
          sub_18007B0F4(&v43, pExceptionObject, &v40);
          sub_180028810(pExceptionObject);
          sub_180028810(Src);
          sub_180028810(&v40);
          if ( !(unsigned __int8)sub_1800E492C(a1, &v43) )
            sub_1800EC1DC(a1, &v43, a3);
          v43 = &Uev::Path::`vftable';
          sub_180028810(v48);
          sub_180028810(v47);
          sub_180028810(v46);
          sub_180028810(v45);
        }
      }
      j_j__o_free_0();
    }
    v33 = *(_QWORD *)(a3 + 32) != 0;
    sub_1800641AC(&hKey);
    return v33;
  }
  if ( v7 != v6 )
  {
    v9 = v6;
    while ( 1 )
    {
      sub_18001D71C((__int64)&v40, v7);
      v10 = &v40;
      if ( v42 > 7 )
        v10 = (__int128 *)v40;
      if ( v41 != 1 || (unsigned int)sub_18003DD80(v10, L"*", 1) )
        break;
      phkResult = 0;
      if ( *(_QWORD *)(a2 + 104) <= 7u )
        v11 = (const WCHAR *)(a2 + 80);
      else
        v11 = *(const WCHAR **)(a2 + 80);
      v12 = RegOpenKeyExW(HKEY_CURRENT_USER, v11, 0, 0xF003Fu, (PHKEY)&phkResult);
      if ( v12 )
      {
        sub_1800EB184(a2 + 80, v12);
        sub_1800641AC(&phkResult);
        sub_180028810(&v40);
        return 0;
      }
      if ( !*(_QWORD *)&phkResult )
      {
        sub_18001D80C(Src, L"Attempting to use an invalid handle.");
        sub_18002EA54(pExceptionObject, Src);
        throw (Uev::SmartHandleException *)pExceptionObject;
      }
      sub_1800EBF18(phkResult);
      sub_1800641AC(&phkResult);
LABEL_24:
      sub_180028810(&v40);
      v7 += 32;
      if ( v7 == v9 )
        return *(_QWORD *)(a3 + 32) != 0;
    }
    sub_18005F060(&v43, a1);
    sub_180021C34((char *)v48, (char *)&v40, v13);
    if ( !(unsigned __int8)sub_18006064C(a1, &v43) )
    {
LABEL_23:
      v43 = &Uev::Path::`vftable';
      sub_180028810(v48);
      sub_180028810(v47);
      sub_180028810(v46);
      sub_180028810(v45);
      goto LABEL_24;
    }
    sub_18005F060(&v49, &v43);
    v14 = sub_180004BEC(16);
    phkResult = (tagPOINT)v14;
    *(_QWORD *)v14 = &boost::any::holder<unsigned int>::`vftable';
    *(_DWORD *)(v14 + 8) = 0;
    v55 = (void (__fastcall ***)(_QWORD, __int64))v14;
    v56 = 2;
    v57 = 1;
    v58 = 0;
    if ( (unsigned __int8)sub_1800EB300(&v43, &v49) != 1 )
    {
      if ( *(_BYTE *)(a1 + 217) != 1 )
      {
LABEL_20:
        if ( v55 )
          (**v55)(v55, 1);
        v49 = &Uev::Path::`vftable';
        sub_180028810(v54);
        sub_180028810(v53);
        sub_180028810(v52);
        sub_180028810(v51);
        goto LABEL_23;
      }
      v50 = v44;
      sub_180021C34((char *)v52, (char *)v46, v15);
      sub_180021C34((char *)v53, (char *)v47, v16);
      sub_180021C34((char *)v54, (char *)v48, v17);
      sub_180021C34((char *)v51, (char *)v45, v18);
      v57 = 3;
    }
    sub_18008F24C(a3, &v49);
    goto LABEL_20;
  }
  return *(_QWORD *)(a3 + 32) != 0;
}

```

## disassembly

```asm
0x1800ec1dc  push    rbp
0x1800ec1de  push    rbx
0x1800ec1df  push    rsi
0x1800ec1e0  push    r12
0x1800ec1e2  push    r13
0x1800ec1e4  push    r14
0x1800ec1e6  push    r15
0x1800ec1e8  lea     rbp, [rsp-150h]
0x1800ec1f0  sub     rsp, 250h
0x1800ec1f7  mov     rax, cs:__security_cookie
0x1800ec1fe  xor     rax, rsp
0x1800ec201  mov     [rbp+180h+var_40], rax
0x1800ec208  mov     r12, r8
0x1800ec20b  mov     r13, rdx
0x1800ec20e  mov     r14, rcx
0x1800ec211  xor     edx, edx
0x1800ec213  mov     rcx, [rcx+98h]
0x1800ec21a  mov     r15, [r14+90h]
0x1800ec221  lea     rsi, [r14+0D8h]
0x1800ec228  mov     rax, rcx
0x1800ec22b  sub     rax, r15
0x1800ec22e  sar     rax, 5
0x1800ec232  test    rax, rax
0x1800ec235  jz      loc_1800EC4CA
0x1800ec23b  cmp     [rsi], dl
0x1800ec23d  jnz     loc_1800EC4CA
0x1800ec243  cmp     r15, rcx
0x1800ec246  jz      loc_1800EC498
0x1800ec24c  lea     rbx, ??_7Path@Uev@@6B@; const Uev::Path::`vftable'
0x1800ec253  mov     rsi, rcx
0x1800ec256  mov     rdx, r15
0x1800ec259  lea     rcx, [rbp+180h+var_1A0]
0x1800ec25d  call    sub_18001D71C
0x1800ec262  nop
0x1800ec263  mov     r8, [rbp+180h+var_190]
0x1800ec267  lea     rcx, [rbp+180h+var_1A0]
0x1800ec26b  cmp     [rbp+180h+var_188], 7
0x1800ec270  cmova   rcx, qword ptr [rbp+180h+var_1A0]
0x1800ec275  cmp     r8, 1
0x1800ec279  jnz     loc_1800EC302
0x1800ec27f  lea     rdx, asc_18014AAE8; "*"
0x1800ec286  call    sub_18003DD80
0x1800ec28b  test    eax, eax
0x1800ec28d  jnz     short loc_1800EC302
0x1800ec28f  mov     qword ptr [rbp+180h+var_1A8.x], 0
0x1800ec297  lea     rbx, [r13+50h]
0x1800ec29b  cmp     qword ptr [rbx+18h], 7
0x1800ec2a0  jbe     short loc_1800EC2A7
0x1800ec2a2  mov     rdx, [rbx]
0x1800ec2a5  jmp     short loc_1800EC2AA
0x1800ec2a7  mov     rdx, rbx; lpSubKey
0x1800ec2aa  lea     rax, [rbp+180h+var_1A8]
0x1800ec2ae  mov     qword ptr [rsp+280h+phkResult.x], rax; phkResult
0x1800ec2b3  mov     r9d, 0F003Fh; samDesired
0x1800ec2b9  xor     r8d, r8d; ulOptions
0x1800ec2bc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800ec2c3  call    cs:RegOpenKeyExW
0x1800ec2c9  test    eax, eax
0x1800ec2cb  jnz     loc_1800EC4A5
0x1800ec2d1  mov     rcx, qword ptr [rbp+180h+var_1A8.x]; hKey
0x1800ec2d5  test    rcx, rcx
0x1800ec2d8  jz      loc_1800EC7FD
0x1800ec2de  mov     r9, r12
0x1800ec2e1  mov     r8, r14
0x1800ec2e4  mov     rdx, r13
0x1800ec2e7  call    sub_1800EBF18
0x1800ec2ec  nop
0x1800ec2ed  lea     rcx, [rbp+180h+var_1A8]
0x1800ec2f1  call    sub_1800641AC
0x1800ec2f6  lea     rbx, ??_7Path@Uev@@6B@; const Uev::Path::`vftable'
0x1800ec2fd  jmp     loc_1800EC480
0x1800ec302  mov     rdx, r14
0x1800ec305  lea     rcx, [rbp+180h+var_180]
0x1800ec309  call    sub_18005F060
0x1800ec30e  nop
0x1800ec30f  lea     rdx, [rbp+180h+var_1A0]
0x1800ec313  lea     rcx, [rbp+180h+var_110]
0x1800ec317  call    sub_180021C34
0x1800ec31c  lea     rdx, [rbp+180h+var_180]
0x1800ec320  mov     rcx, r14
0x1800ec323  call    sub_18006064C
0x1800ec328  test    al, al
0x1800ec32a  jz      loc_1800EC457
0x1800ec330  lea     rdx, [rbp+180h+var_180]
0x1800ec334  lea     rcx, [rbp+180h+var_F0]
0x1800ec33b  call    sub_18005F060
0x1800ec340  nop
0x1800ec341  mov     ecx, 10h
0x1800ec346  call    sub_180004BEC
0x1800ec34b  mov     qword ptr [rbp+180h+var_1A8.x], rax
0x1800ec34f  lea     rcx, ??_7?$holder@I@any@boost@@6B@; const boost::any::holder<uint>::`vftable'
0x1800ec356  mov     [rax], rcx
0x1800ec359  mov     dword ptr [rax+8], 0
0x1800ec360  mov     [rbp+180h+var_60], rax
0x1800ec367  mov     [rbp+180h+var_58], 2
0x1800ec371  mov     [rbp+180h+var_54], 1
0x1800ec37b  mov     [rbp+180h+var_50], 0
0x1800ec382  lea     rdx, [rbp+180h+var_F0]
0x1800ec389  lea     rcx, [rbp+180h+var_180]
0x1800ec38d  call    sub_1800EB300
0x1800ec392  cmp     al, 1
0x1800ec394  jz      short loc_1800EC3F3
0x1800ec396  cmp     byte ptr [r14+0D9h], 1
0x1800ec39e  jnz     short loc_1800EC403
0x1800ec3a0  mov     eax, [rbp+180h+var_178]
0x1800ec3a3  mov     [rbp+180h+var_E8], eax
0x1800ec3a9  lea     rdx, [rbp+180h+var_150]
0x1800ec3ad  lea     rcx, [rbp+180h+var_C0]
0x1800ec3b4  call    sub_180021C34
0x1800ec3b9  lea     rdx, [rbp+180h+var_130]
0x1800ec3bd  lea     rcx, [rbp+180h+var_A0]
0x1800ec3c4  call    sub_180021C34
0x1800ec3c9  lea     rdx, [rbp+180h+var_110]
0x1800ec3cd  lea     rcx, [rbp+180h+var_80]
0x1800ec3d4  call    sub_180021C34
0x1800ec3d9  lea     rdx, [rbp+180h+var_170]
0x1800ec3dd  lea     rcx, [rbp+180h+var_E0]
0x1800ec3e4  call    sub_180021C34
0x1800ec3e9  mov     [rbp+180h+var_54], 3
0x1800ec3f3  lea     rdx, [rbp+180h+var_F0]
0x1800ec3fa  mov     rcx, r12
0x1800ec3fd  call    sub_18008F24C
0x1800ec402  nop
0x1800ec403  mov     rcx, [rbp+180h+var_60]
0x1800ec40a  test    rcx, rcx
0x1800ec40d  jz      short loc_1800EC41F
0x1800ec40f  mov     rax, [rcx]
0x1800ec412  mov     edx, 1
0x1800ec417  mov     rax, [rax]
0x1800ec41a  call    j__guard_dispatch_icall
0x1800ec41f  mov     [rbp+180h+var_F0], rbx
0x1800ec426  lea     rcx, [rbp+180h+var_80]
0x1800ec42d  call    sub_180028810
0x1800ec432  lea     rcx, [rbp+180h+var_A0]
0x1800ec439  call    sub_180028810
0x1800ec43e  lea     rcx, [rbp+180h+var_C0]
0x1800ec445  call    sub_180028810
0x1800ec44a  lea     rcx, [rbp+180h+var_E0]
0x1800ec451  call    sub_180028810
0x1800ec456  nop
0x1800ec457  mov     [rbp+180h+var_180], rbx
0x1800ec45b  lea     rcx, [rbp+180h+var_110]
0x1800ec45f  call    sub_180028810
0x1800ec464  lea     rcx, [rbp+180h+var_130]
0x1800ec468  call    sub_180028810
0x1800ec46d  lea     rcx, [rbp+180h+var_150]
0x1800ec471  call    sub_180028810
0x1800ec476  lea     rcx, [rbp+180h+var_170]
0x1800ec47a  call    sub_180028810
0x1800ec47f  nop
0x1800ec480  lea     rcx, [rbp+180h+var_1A0]
0x1800ec484  call    sub_180028810
0x1800ec489  add     r15, 20h ; ' '
0x1800ec48d  cmp     r15, rsi
0x1800ec490  jnz     loc_1800EC256
0x1800ec496  xor     edx, edx
0x1800ec498  cmp     [r12+20h], rdx
0x1800ec49d  setnz   al
0x1800ec4a0  jmp     loc_1800EC7A4
0x1800ec4a5  mov     edx, eax
0x1800ec4a7  mov     rcx, rbx
0x1800ec4aa  call    sub_1800EB184
0x1800ec4af  nop
0x1800ec4b0  lea     rcx, [rbp+180h+var_1A8]
0x1800ec4b4  call    sub_1800641AC
0x1800ec4b9  nop
0x1800ec4ba  lea     rcx, [rbp+180h+var_1A0]
0x1800ec4be  call    sub_180028810
0x1800ec4c3  xor     al, al
0x1800ec4c5  jmp     loc_1800EC7A4
0x1800ec4ca  xor     r15d, r15d
0x1800ec4cd  mov     qword ptr [rbp+180h+hKey.x], r15
0x1800ec4d1  lea     rbx, [r13+50h]
0x1800ec4d5  cmp     qword ptr [rbx+18h], 7
0x1800ec4da  jbe     short loc_1800EC4E1
0x1800ec4dc  mov     rdx, [rbx]
0x1800ec4df  jmp     short loc_1800EC4E4
0x1800ec4e1  mov     rdx, rbx; lpSubKey
0x1800ec4e4  lea     rax, [rbp+180h+hKey]
0x1800ec4e8  mov     qword ptr [rsp+280h+phkResult.x], rax; phkResult
0x1800ec4ed  mov     r9d, 0F003Fh; samDesired
0x1800ec4f3  xor     r8d, r8d; ulOptions
0x1800ec4f6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800ec4fd  call    cs:RegOpenKeyExW
0x1800ec503  test    eax, eax
0x1800ec505  jz      short loc_1800EC51D
0x1800ec507  mov     edx, eax
0x1800ec509  mov     rcx, rbx
0x1800ec50c  call    sub_1800EB184
0x1800ec511  nop
0x1800ec512  lea     rcx, [rbp+180h+hKey]
0x1800ec516  call    sub_1800641AC
0x1800ec51b  jmp     short loc_1800EC4C3
0x1800ec51d  mov     rcx, qword ptr [rbp+180h+hKey.x]; hKey
0x1800ec521  test    rcx, rcx
0x1800ec524  jz      loc_1800EC82E
0x1800ec52a  mov     r9, r12
0x1800ec52d  mov     r8, r14
0x1800ec530  mov     rdx, r13
0x1800ec533  call    sub_1800EBF18
0x1800ec538  cmp     byte ptr [rsi], 1
0x1800ec53b  jnz     loc_1800EC791
0x1800ec541  mov     dword ptr [rbp+180h+cbMaxSubKeyLen], r15d
0x1800ec545  mov     rcx, qword ptr [rbp+180h+hKey.x]; hKey
0x1800ec549  test    rcx, rcx
0x1800ec54c  jz      loc_1800EC85F
0x1800ec552  mov     [rsp+280h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800ec557  mov     [rsp+280h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800ec55c  mov     [rsp+280h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800ec561  mov     [rsp+280h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800ec566  mov     [rsp+280h+lpcValues], r15; lpcValues
0x1800ec56b  mov     [rsp+280h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800ec570  lea     rax, [rbp+180h+cbMaxSubKeyLen]
0x1800ec574  mov     [rsp+280h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800ec579  mov     qword ptr [rsp+280h+phkResult.x], r15; lpcSubKeys
0x1800ec57e  xor     r9d, r9d; lpReserved
0x1800ec581  xor     r8d, r8d; lpcchClass
0x1800ec584  xor     edx, edx; lpClass
0x1800ec586  call    cs:RegQueryInfoKeyW
0x1800ec58c  test    eax, eax
0x1800ec58e  jnz     loc_1800EC507
0x1800ec594  mov     ecx, dword ptr [rbp+180h+cbMaxSubKeyLen]
0x1800ec597  add     ecx, 2
0x1800ec59a  mov     dword ptr [rbp+180h+cbMaxSubKeyLen], ecx
0x1800ec59d  mov     eax, 2
0x1800ec5a2  mul     rcx
0x1800ec5a5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ec5ac  cmovb   rax, rcx
0x1800ec5b0  mov     rcx, rax
0x1800ec5b3  call    sub_1800050EC
0x1800ec5b8  mov     rsi, rax
0x1800ec5bb  mov     [rbp+180h+var_1C0], rax
0x1800ec5bf  mov     r13d, r15d
0x1800ec5c2  mov     ecx, dword ptr [rbp+180h+cbMaxSubKeyLen]
0x1800ec5c5  mov     [rbp+180h+var_1A8.x], ecx
0x1800ec5c8  mov     rcx, qword ptr [rbp+180h+hKey.x]; hKey
0x1800ec5cc  test    rcx, rcx
0x1800ec5cf  jz      loc_1800EC7CC
0x1800ec5d5  mov     [rsp+280h+lpcValues], r15; lpftLastWriteTime
0x1800ec5da  mov     [rsp+280h+lpcbMaxClassLen], r15; lpcchClass
0x1800ec5df  mov     [rsp+280h+lpcbMaxSubKeyLen], r15; lpClass
0x1800ec5e4  mov     qword ptr [rsp+280h+phkResult.x], r15; lpReserved
0x1800ec5e9  lea     r9, [rbp+180h+var_1A8]; lpcchName
0x1800ec5ed  mov     r8, rsi; lpName
0x1800ec5f0  mov     edx, r13d; dwIndex
0x1800ec5f3  call    cs:RegEnumKeyExW
0x1800ec5f9  mov     r15d, eax
0x1800ec5fc  cmp     eax, 103h
0x1800ec601  jz      loc_1800EC786
0x1800ec607  xor     eax, eax
0x1800ec609  xorps   xmm0, xmm0
0x1800ec60c  movups  [rbp+180h+var_1A0], xmm0
0x1800ec610  test    r15d, r15d
0x1800ec613  jnz     loc_1800EC742
0x1800ec619  xor     r15d, r15d
0x1800ec61c  mov     [rbp+180h+var_190], r15
0x1800ec620  mov     [rbp+180h+var_188], r15
0x1800ec624  xor     r8d, r8d
0x1800ec627  lea     rdx, Data
0x1800ec62e  lea     rcx, [rbp+180h+var_1A0]
0x1800ec632  call    sub_18001916C
0x1800ec637  nop
0x1800ec638  mov     rcx, [rbx+10h]
0x1800ec63c  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800ec646  sub     rax, rcx
0x1800ec649  cmp     rax, 1
0x1800ec64d  jb      loc_1800EC7C6
0x1800ec653  cmp     qword ptr [rbx+18h], 7
0x1800ec658  jbe     short loc_1800EC65F
0x1800ec65a  mov     r9, [rbx]
0x1800ec65d  jmp     short loc_1800EC662
0x1800ec65f  mov     r9, rbx
0x1800ec662  mov     [rsp+280h+lpcbMaxClassLen], 1
0x1800ec66b  lea     rax, SubBlock; "\\"
0x1800ec672  mov     [rsp+280h+lpcbMaxSubKeyLen], rax
0x1800ec677  mov     qword ptr [rsp+280h+phkResult.x], rcx
0x1800ec67c  lea     rcx, [rsp+280h+Src]
0x1800ec681  call    sub_180037DC4
0x1800ec686  nop
0x1800ec687  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ec68b  inc     r8
0x1800ec68e  cmp     [rsi+r8*2], r15w
0x1800ec693  jnz     short loc_1800EC68B
0x1800ec695  mov     rdx, rsi
0x1800ec698  lea     rcx, [rsp+280h+Src]; Src
0x1800ec69d  call    sub_180018FB8
0x1800ec6a2  movups  xmm0, xmmword ptr [rax]
0x1800ec6a5  movups  [rbp+180h+pExceptionObject], xmm0
0x1800ec6a9  movups  xmm1, xmmword ptr [rax+10h]
0x1800ec6ad  movups  [rbp+180h+var_1F0], xmm1
0x1800ec6b1  mov     [rax+10h], r15
0x1800ec6b5  mov     qword ptr [rax+18h], 7
0x1800ec6bd  mov     [rax], r15w
0x1800ec6c1  lea     r8, [rbp+180h+var_1A0]
0x1800ec6c5  lea     rdx, [rbp+180h+pExceptionObject]
0x1800ec6c9  lea     rcx, [rbp+180h+var_180]
0x1800ec6cd  call    sub_18007B0F4
0x1800ec6d2  nop
0x1800ec6d3  lea     rcx, [rbp+180h+pExceptionObject]
0x1800ec6d7  call    sub_180028810
  ... truncated ...
```
