# GetAccountRegistryPath(ushort const *,unsigned __int64,ushort *)

- ea: `0x180005910`
- end: `0x180005c0d`
- name: `?GetAccountRegistryPath@@YAJPEBG_KPEAG@Z`
- size: `765`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005720`
- `0x180008ce0`
- `0x18000da00`
- `0x18000eac4`

## callees

- `0x180005910`
- `0x1800065f0`
- `0x180006630`
- `0x180007570`
- `0x180007640`
- `0x180007680`
- `0x180008ff0`
- `0x18000b6f4`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180005ac9`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180005ac9`

## pseudocode

```c
__int64 __fastcall GetAccountRegistryPath(const unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v5; // rsi
  signed int v6; // ebx
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  __int64 v9; // rax
  const wchar_t *v10; // r8
  unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rax
  signed int PersistedRegistryLocationW; // eax
  size_t v15; // rdx
  wchar_t v16; // r10
  unsigned int v17; // edx
  bool v18; // cc
  const wchar_t *v19; // r9
  __int64 v20; // r8
  wchar_t *v21; // rdx
  size_t v22; // rcx
  wchar_t *v23; // rax
  __int64 v24; // [rsp+68h] [rbp+10h] BYREF
  size_t pcchLength; // [rsp+78h] [rbp+20h] BYREF

  v24 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids);
  if ( !psz )
  {
    pcchLength = 0;
    LODWORD(v24) = 0;
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"WwanSvc", RegistryPaths[0], &psz, 520, &v24);
    v16 = aMobilebroadban[0];
    v6 = PersistedRegistryLocationW;
    if ( aMobilebroadban[0] )
    {
      if ( StringCchLengthW(L"MobileBroadbandAccounts", v15, &pcchLength) < 0 )
      {
        LOWORD(v6) = 87;
        v5 = 2147483646;
        goto LABEL_50;
      }
      v17 = ((unsigned int)v24 >> 1) + pcchLength + 1;
    }
    else
    {
      v17 = (unsigned int)v24 >> 1;
    }
    v5 = 2147483646;
    v18 = v6 <= 0;
    if ( v6 )
      goto LABEL_17;
    if ( v17 > 0x104 )
    {
      LOWORD(v6) = 234;
    }
    else
    {
      if ( !v16 )
        goto LABEL_41;
      pcchLength = 0;
      if ( StringLengthWorkerW(&psz, 0x104u, &pcchLength) >= 0 )
      {
        v19 = L"\\";
        v20 = 2147483646;
        v21 = &psz + pcchLength;
        v22 = 260 - pcchLength;
        if ( pcchLength != 260 )
        {
          do
          {
            if ( !v20 )
              break;
            if ( !*v19 )
              break;
            *v21++ = *v19++;
            --v20;
            --v22;
          }
          while ( v22 );
        }
        v23 = v21 - 1;
        if ( v22 )
          v23 = v21;
        *v23 = 0;
        if ( v22 )
        {
          if ( StringCchCatW(&psz, 0x104u, L"MobileBroadbandAccounts") >= 0 )
          {
LABEL_41:
            v18 = 1;
LABEL_17:
            if ( v18 )
              goto LABEL_18;
            goto LABEL_50;
          }
        }
      }
      LOWORD(v6) = 31;
    }
LABEL_50:
    v6 = (unsigned __int16)v6 | 0x80070000;
LABEL_18:
    if ( v6 < 0 )
      goto LABEL_19;
    goto LABEL_4;
  }
  v5 = 2147483646;
LABEL_4:
  v6 = StringCchCopyW(a3, 0x104u, &psz);
  if ( v6 >= 0 )
  {
    v7 = 260;
    v8 = a3;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v7;
    }
    while ( v7 );
    v6 = -2147024809;
    if ( v7 )
      v6 = 0;
    v9 = 260 - v7;
    if ( v7 )
    {
      v10 = L"\\Accounts\\";
      v11 = &a3[v9];
      if ( v9 != 260 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v10 )
            break;
          *v11++ = *v10++;
          --v5;
          --v7;
        }
        while ( v7 );
      }
      v12 = v11 - 1;
      v6 = -2147024774;
      if ( v7 )
      {
        v12 = v11;
        v6 = 0;
      }
      *v12 = 0;
      if ( v7 && a1 )
        v6 = StringCchCatW(a3, 0x104u, a1);
    }
  }
LABEL_19:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005910  mov     [rsp+arg_8], rdx
0x180005915  sub     rsp, 58h
0x180005919  mov     [rsp+58h+var_18], r12
0x18000591e  mov     [rsp+58h+var_20], r14
0x180005923  mov     r14, rcx
0x180005926  mov     [rsp+58h+var_28], r15
0x18000592b  mov     r15, r8
0x18000592e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005935  lea     r12, WPP_GLOBAL_Control
0x18000593c  cmp     rcx, r12
0x18000593f  jnz     loc_180005BB8
0x180005945  mov     [rsp+58h+arg_0], rbx
0x18000594a  mov     [rsp+58h+arg_10], rbp
0x18000594f  xor     ebp, ebp
0x180005951  cmp     cs:psz, bp
0x180005958  mov     [rsp+58h+var_8], rsi
0x18000595d  mov     [rsp+58h+var_10], rdi
0x180005962  lea     rdi, psz
0x180005969  jz      loc_180005A9F
0x18000596f  mov     esi, 7FFFFFFEh
0x180005974  mov     r8, rdi; unsigned __int16 *
0x180005977  mov     edx, 104h; unsigned __int64
0x18000597c  mov     rcx, r15; unsigned __int16 *
0x18000597f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005984  mov     ebx, eax
0x180005986  test    eax, eax
0x180005988  js      loc_180005A1A
0x18000598e  mov     ecx, 104h
0x180005993  mov     rax, r15
0x180005996  cmp     word ptr [rax], 0
0x18000599a  jz      short loc_1800059A6
0x18000599c  add     rax, 2
0x1800059a0  sub     rcx, 1
0x1800059a4  jnz     short loc_180005996
0x1800059a6  test    rcx, rcx
0x1800059a9  mov     ebx, 80070057h
0x1800059ae  mov     eax, 104h
0x1800059b3  cmovnz  ebx, ebp
0x1800059b6  sub     rax, rcx
0x1800059b9  test    rcx, rcx
0x1800059bc  cmovz   rax, rbp
0x1800059c0  jz      short loc_180005A1A
0x1800059c2  mov     ecx, 104h
0x1800059c7  lea     r8, aAccounts; "\\Accounts\\"
0x1800059ce  lea     rdx, [r15+rax*2]
0x1800059d2  sub     rcx, rax
0x1800059d5  jnz     loc_180005A70
0x1800059db  test    rcx, rcx
0x1800059de  lea     rax, [rdx-2]
0x1800059e2  mov     ebx, 8007007Ah
0x1800059e7  cmovnz  rax, rdx
0x1800059eb  cmovnz  ebx, ebp
0x1800059ee  mov     [rax], bp
0x1800059f1  jz      short loc_180005A1A
0x1800059f3  test    r14, r14
0x1800059f6  jz      short loc_180005A1A
0x1800059f8  mov     r8, r14; unsigned __int16 *
0x1800059fb  mov     edx, 104h; unsigned __int64
0x180005a00  mov     rcx, r15; unsigned __int16 *
0x180005a03  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005a08  mov     ebx, eax
0x180005a0a  jmp     short loc_180005A1A
0x180005a0c  jg      loc_180005BFF
0x180005a12  test    ebx, ebx
0x180005a14  jns     loc_180005974
0x180005a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a21  mov     r15, [rsp+58h+var_28]
0x180005a26  cmp     rcx, r12
0x180005a29  mov     r12, [rsp+58h+var_18]
0x180005a2e  mov     r14, [rsp+58h+var_20]
0x180005a33  mov     rdi, [rsp+58h+var_10]
0x180005a38  mov     rsi, [rsp+58h+var_8]
0x180005a3d  mov     rbp, [rsp+58h+arg_10]
0x180005a42  jnz     short loc_180005A50
0x180005a44  mov     eax, ebx
0x180005a46  mov     rbx, [rsp+58h+arg_0]
0x180005a4b  add     rsp, 58h
0x180005a4f  retn
0x180005a50  test    byte ptr [rcx+1Ch], 10h
0x180005a54  jz      short loc_180005A44
0x180005a56  mov     rcx, [rcx+10h]
0x180005a5a  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x180005a61  mov     edx, 11h
0x180005a66  mov     r9d, ebx
0x180005a69  call    WPP_SF_d
0x180005a6e  jmp     short loc_180005A44
0x180005a70  test    rsi, rsi
0x180005a73  jz      loc_1800059DB
0x180005a79  movzx   eax, word ptr [r8]
0x180005a7d  test    ax, ax
0x180005a80  jz      loc_1800059DB
0x180005a86  mov     [rdx], ax
0x180005a89  add     r8, 2
0x180005a8d  add     rdx, 2
0x180005a91  dec     rsi
0x180005a94  sub     rcx, 1
0x180005a98  jnz     short loc_180005A70
0x180005a9a  jmp     loc_1800059DB
0x180005a9f  mov     rdx, cs:RegistryPaths
0x180005aa6  lea     rax, [rsp+58h+arg_8]
0x180005aab  mov     rcx, cs:off_180013008; "WwanSvc"
0x180005ab2  mov     r9d, 208h
0x180005ab8  mov     r8, rdi
0x180005abb  mov     [rsp+58h+var_38], rax
0x180005ac0  mov     [rsp+58h+pcchLength], rbp
0x180005ac5  mov     dword ptr [rsp+58h+arg_8], ebp
0x180005ac9  call    cs:__imp_GetPersistedRegistryLocationW
0x180005acf  movzx   r10d, word ptr cs:aMobilebroadban; "MobileBroadbandAccounts"
0x180005ad7  mov     ebx, eax
0x180005ad9  test    r10w, r10w
0x180005add  jz      loc_180005BE8
0x180005ae3  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x180005ae8  lea     rcx, aMobilebroadban; "MobileBroadbandAccounts"
0x180005aef  call    StringCchLengthW
0x180005af4  test    eax, eax
0x180005af6  js      loc_180005BDC
0x180005afc  mov     ecx, dword ptr [rsp+58h+arg_8]
0x180005b00  mov     edx, dword ptr [rsp+58h+pcchLength]
0x180005b04  shr     ecx, 1
0x180005b06  inc     edx
0x180005b08  add     edx, ecx
0x180005b0a  mov     esi, 7FFFFFFEh
0x180005b0f  test    ebx, ebx
0x180005b11  jnz     loc_180005A0C
0x180005b17  cmp     edx, 104h
0x180005b1d  ja      loc_180005BF3
0x180005b23  test    r10w, r10w
0x180005b27  jz      short loc_180005B9B
0x180005b29  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x180005b2e  mov     [rsp+58h+pcchLength], rbp
0x180005b33  mov     edx, 104h; cchMax
0x180005b38  mov     rcx, rdi; psz
0x180005b3b  call    StringLengthWorkerW
0x180005b40  test    eax, eax
0x180005b42  js      loc_180005BFA
0x180005b48  mov     rax, [rsp+58h+pcchLength]
0x180005b4d  lea     r9, asc_180013DE4; "\\"
0x180005b54  mov     ecx, 104h
0x180005b59  mov     r8d, esi
0x180005b5c  lea     rdx, [rdi+rax*2]
0x180005b60  sub     rcx, rax
0x180005b63  jz      short loc_180005B73
0x180005b65  test    r8, r8
0x180005b68  jz      short loc_180005B73
0x180005b6a  movzx   eax, word ptr [r9]
0x180005b6e  test    ax, ax
0x180005b71  jnz     short loc_180005BA2
0x180005b73  test    rcx, rcx
0x180005b76  lea     rax, [rdx-2]
0x180005b7a  cmovnz  rax, rdx
0x180005b7e  mov     [rax], bp
0x180005b81  jz      short loc_180005BFA
0x180005b83  lea     r8, aMobilebroadban; "MobileBroadbandAccounts"
0x180005b8a  mov     edx, 104h; cchDest
0x180005b8f  mov     rcx, rdi; pszDest
0x180005b92  call    StringCchCatW
0x180005b97  test    eax, eax
0x180005b99  js      short loc_180005BFA
0x180005b9b  test    ebx, ebx
0x180005b9d  jmp     loc_180005A0C
0x180005ba2  mov     [rdx], ax
0x180005ba5  add     r9, 2
0x180005ba9  add     rdx, 2
0x180005bad  dec     r8
0x180005bb0  sub     rcx, 1
0x180005bb4  jnz     short loc_180005B65
0x180005bb6  jmp     short loc_180005B73
0x180005bb8  test    byte ptr [rcx+1Ch], 10h
0x180005bbc  jz      loc_180005945
0x180005bc2  mov     rcx, [rcx+10h]
0x180005bc6  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x180005bcd  mov     edx, 10h
0x180005bd2  call    WPP_SF_
0x180005bd7  jmp     loc_180005945
0x180005bdc  mov     ebx, 57h ; 'W'
0x180005be1  mov     esi, 7FFFFFFEh
0x180005be6  jmp     short loc_180005BFF
0x180005be8  mov     edx, dword ptr [rsp+58h+arg_8]
0x180005bec  shr     edx, 1
0x180005bee  jmp     loc_180005B0A
0x180005bf3  mov     ebx, 0EAh
0x180005bf8  jmp     short loc_180005BFF
0x180005bfa  mov     ebx, 1Fh
0x180005bff  movzx   ebx, bx
0x180005c02  or      ebx, 80070000h
0x180005c08  jmp     loc_180005A12
```
