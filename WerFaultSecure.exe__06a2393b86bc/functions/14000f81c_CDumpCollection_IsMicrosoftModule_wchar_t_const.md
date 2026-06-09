# CDumpCollection::_IsMicrosoftModule(wchar_t const *)

- ea: `0x14000f81c`
- end: `0x14000fb33`
- name: `?_IsMicrosoftModule@CDumpCollection@@AEAAHPEB_W@Z`
- size: `791`
- prototype: `__int64 __fastcall(CDumpCollection *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000f4b0`

## callees

- `0x1400023d0`
- `0x1400023f4`
- `0x140003268`
- `0x140004664`
- `0x1400073fc`
- `0x140007cd4`
- `0x14000e598`
- `0x14000f81c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f907`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000f98b`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000f9fc`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000f98b`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000f9fc`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x14000f8fd`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x14000f8fd`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x14000f873`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x14000f873`

## string_xrefs

- `0x14000f9cc`: `\StringFileInfo\%04x%04x\CompanyName`

## pseudocode

```c
__int64 __fastcall CDumpCollection::_IsMicrosoftModule(CDumpCollection *this, const wchar_t *a2)
{
  unsigned int v3; // edi
  DWORD FileVersionInfoSize; // eax
  DWORD v5; // r14d
  signed int LastError; // eax
  void *v7; // rax
  void *v8; // rbx
  signed int v9; // eax
  unsigned __int64 v10; // rdx
  _QWORD *v11; // rcx
  unsigned int i; // r14d
  BOOL v13; // eax
  __int64 v14; // r9
  int v15; // ecx
  int v16; // r8d
  int v17; // ecx
  LPVOID lpData; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwHandle; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID v22; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpBuffer; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+4Ch] [rbp-B4h]
  WCHAR SubBlock[256]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  v3 = 1;
  v22 = 0;
  dwHandle = 0;
  puLen = 0;
  FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, a2, &dwHandle);
  v5 = FileVersionInfoSize;
  if ( !FileVersionInfoSize )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids,
        (unsigned int)LastError);
    return 0;
  }
  v7 = operator new[](FileVersionInfoSize, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
    return 0;
  }
  if ( GetFileVersionInfoExW(3u, a2, 0, v5, v7) )
  {
    lpBuffer = (LPVOID)0x4B0040900000000LL;
    v24 = 82052105;
    v25 = 1033;
    if ( !VerQueryValueW(v8, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
      LODWORD(lpBuffer) = 0;
    v11 = WPP_GLOBAL_Control;
    for ( i = 0; i < 4; ++i )
    {
      v10 = *((unsigned __int16 *)&lpBuffer + 2 * (int)i);
      if ( (_WORD)v10 || *((_WORD *)&lpBuffer + 2 * (int)i + 1) )
      {
        LODWORD(lpData) = *((unsigned __int16 *)&lpBuffer + 2 * (int)i + 1);
        if ( (int)StringCchPrintfW(
                    SubBlock,
                    0x100u,
                    L"\\StringFileInfo\\%04x%04x\\CompanyName",
                    *((unsigned __int16 *)&lpBuffer + 2 * (int)i),
                    lpData) < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
            v11 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          v13 = VerQueryValueW(v8, SubBlock, &v22, &puLen);
          v11 = WPP_GLOBAL_Control;
          if ( v13 )
            break;
        }
      }
    }
    if ( i == 4 )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
        WPP_SF_(v11[2], 42, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
    }
    else if ( (puLen & 0xFFFFFFFE) >= 0x12uLL )
    {
      if ( L"Microsoft" == v22 )
        goto LABEL_17;
      v14 = 0;
      while ( 1 )
      {
        v15 = *((unsigned __int16 *)v22 + v14);
        v16 = aMicrosoft[v14];
        v10 = (unsigned int)(v15 - 32);
        if ( (unsigned int)(v15 - 97) >= 0x1A )
          v10 = *((unsigned __int16 *)v22 + v14);
        v17 = v16 - 32;
        if ( (unsigned int)(v16 - 97) >= 0x1A )
          v17 = aMicrosoft[v14];
        if ( v17 != (_DWORD)v10 )
          break;
        if ( ++v14 == 9 )
          goto LABEL_17;
      }
    }
  }
  else
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids,
        (unsigned int)v9);
  }
  v3 = 0;
LABEL_17:
  operator delete(v8, (const struct std::nothrow_t *)v10);
  return v3;
}

```

## disassembly

```asm
0x14000f81c  push    rbp
0x14000f81e  push    rbx
0x14000f81f  push    rsi
0x14000f820  push    rdi
0x14000f821  push    r14
0x14000f823  push    r15
0x14000f825  lea     rbp, [rsp-168h]
0x14000f82d  sub     rsp, 268h
0x14000f834  mov     rax, cs:__security_cookie
0x14000f83b  xor     rax, rsp
0x14000f83e  mov     [rbp+190h+var_40], rax
0x14000f845  xor     r15d, r15d
0x14000f848  mov     rsi, rdx
0x14000f84b  test    rdx, rdx
0x14000f84e  jnz     short loc_14000F855
0x14000f850  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000f855  mov     edi, 1
0x14000f85a  mov     [rsp+290h+var_258], r15
0x14000f85f  mov     ecx, edi; dwFlags
0x14000f861  mov     [rsp+290h+dwHandle], r15d
0x14000f866  lea     r8, [rsp+290h+dwHandle]; lpdwHandle
0x14000f86b  mov     [rsp+290h+puLen], r15d
0x14000f870  mov     rdx, rsi; lpwstrFilename
0x14000f873  call    cs:__imp_GetFileVersionInfoSizeExW
0x14000f879  mov     r14d, eax
0x14000f87c  test    eax, eax
0x14000f87e  jnz     short loc_14000F8D0
0x14000f880  call    cs:__imp_GetLastError
0x14000f886  test    eax, eax
0x14000f888  jle     short loc_14000F892
0x14000f88a  movzx   eax, ax
0x14000f88d  or      eax, 80070000h
0x14000f892  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f899  lea     rsi, WPP_GLOBAL_Control
0x14000f8a0  cmp     rcx, rsi
0x14000f8a3  jz      loc_14000FB0F
0x14000f8a9  test    [rcx+1Ch], dil
0x14000f8ad  jz      loc_14000FB0F
0x14000f8b3  mov     rcx, [rcx+10h]
0x14000f8b7  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000f8be  mov     edx, 26h ; '&'
0x14000f8c3  mov     r9d, eax
0x14000f8c6  call    WPP_SF_d
0x14000f8cb  jmp     loc_14000FB0F
0x14000f8d0  mov     rcx, r14; unsigned __int64
0x14000f8d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000f8da  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000f8df  mov     rbx, rax
0x14000f8e2  test    rax, rax
0x14000f8e5  jz      loc_14000FAE1
0x14000f8eb  xor     r8d, r8d; dwHandle
0x14000f8ee  mov     [rsp+290h+lpData], rax; lpData
0x14000f8f3  mov     r9d, r14d; dwLen
0x14000f8f6  mov     rdx, rsi; lpwstrFilename
0x14000f8f9  lea     ecx, [r8+3]; dwFlags
0x14000f8fd  call    cs:__imp_GetFileVersionInfoExW
0x14000f903  test    eax, eax
0x14000f905  jnz     short loc_14000F95A
0x14000f907  call    cs:__imp_GetLastError
0x14000f90d  test    eax, eax
0x14000f90f  jle     short loc_14000F919
0x14000f911  movzx   eax, ax
0x14000f914  or      eax, 80070000h
0x14000f919  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f920  lea     rsi, WPP_GLOBAL_Control
0x14000f927  cmp     rcx, rsi
0x14000f92a  jz      short loc_14000F94A
0x14000f92c  test    [rcx+1Ch], dil
0x14000f930  jz      short loc_14000F94A
0x14000f932  mov     rcx, [rcx+10h]
0x14000f936  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000f93d  mov     edx, 28h ; '('
0x14000f942  mov     r9d, eax
0x14000f945  call    WPP_SF_d
0x14000f94a  mov     edi, r15d
0x14000f94d  mov     rcx, rbx; void *
0x14000f950  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000f955  jmp     loc_14000FB12
0x14000f95a  lea     r9, [rsp+290h+puLen]; puLen
0x14000f95f  mov     dword ptr [rsp+290h+lpBuffer], r15d
0x14000f964  lea     r8, [rsp+290h+lpBuffer]; lplpBuffer
0x14000f969  mov     dword ptr [rsp+290h+lpBuffer+4], 4B00409h
0x14000f971  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x14000f978  mov     [rsp+290h+var_248], 4E40409h
0x14000f980  mov     rcx, rbx; pBlock
0x14000f983  mov     [rsp+290h+var_244], 409h
0x14000f98b  call    cs:__imp_VerQueryValueW
0x14000f991  test    eax, eax
0x14000f993  jnz     short loc_14000F99A
0x14000f995  mov     dword ptr [rsp+290h+lpBuffer], r15d
0x14000f99a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9a1  lea     rsi, WPP_GLOBAL_Control
0x14000f9a8  mov     r14d, r15d
0x14000f9ab  movsxd  rax, r14d
0x14000f9ae  movzx   edx, word ptr [rsp+rax*4+290h+lpBuffer]
0x14000f9b3  test    dx, dx
0x14000f9b6  jnz     short loc_14000F9C0
0x14000f9b8  cmp     word ptr [rsp+rax*4+290h+lpBuffer+2], r15w
0x14000f9be  jz      short loc_14000FA3D
0x14000f9c0  lea     rcx, [rsp+290h+lpBuffer+2]
0x14000f9c5  mov     r9d, edx
0x14000f9c8  movzx   eax, word ptr [rcx+rax*4]
0x14000f9cc  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\CompanyName"
0x14000f9d3  lea     rcx, [rsp+290h+SubBlock]; wchar_t *
0x14000f9d8  mov     dword ptr [rsp+290h+lpData], eax
0x14000f9dc  mov     edx, 100h; unsigned __int64
0x14000f9e1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000f9e6  test    eax, eax
0x14000f9e8  js      short loc_14000FA0F
0x14000f9ea  lea     r9, [rsp+290h+puLen]; puLen
0x14000f9ef  mov     rcx, rbx; pBlock
0x14000f9f2  lea     r8, [rsp+290h+var_258]; lplpBuffer
0x14000f9f7  lea     rdx, [rsp+290h+SubBlock]; lpSubBlock
0x14000f9fc  call    cs:__imp_VerQueryValueW
0x14000fa02  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa09  test    eax, eax
0x14000fa0b  jnz     short loc_14000FA4A
0x14000fa0d  jmp     short loc_14000FA3D
0x14000fa0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa16  cmp     rcx, rsi
0x14000fa19  jz      short loc_14000FA3D
0x14000fa1b  test    byte ptr [rcx+1Ch], 2
0x14000fa1f  jz      short loc_14000FA3D
0x14000fa21  mov     rcx, [rcx+10h]
0x14000fa25  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000fa2c  mov     edx, 29h ; ')'
0x14000fa31  call    WPP_SF_
0x14000fa36  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa3d  add     r14d, edi
0x14000fa40  cmp     r14d, 4
0x14000fa44  jb      loc_14000F9AB
0x14000fa4a  cmp     r14d, 4
0x14000fa4e  jnz     short loc_14000FA7C
0x14000fa50  cmp     rcx, rsi
0x14000fa53  jz      loc_14000F94A
0x14000fa59  test    [rcx+1Ch], r14b
0x14000fa5d  jz      loc_14000F94A
0x14000fa63  mov     rcx, [rcx+10h]
0x14000fa67  lea     edx, [r14+26h]
0x14000fa6b  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000fa72  call    WPP_SF_
0x14000fa77  jmp     loc_14000F94A
0x14000fa7c  mov     eax, [rsp+290h+puLen]
0x14000fa80  and     rax, 0FFFFFFFFFFFFFFFEh
0x14000fa84  cmp     rax, 12h
0x14000fa88  jb      loc_14000F94A
0x14000fa8e  mov     r10, cs:off_140013240; "Microsoft"
0x14000fa95  mov     r11, [rsp+290h+var_258]
0x14000fa9a  cmp     r10, r11
0x14000fa9d  jz      loc_14000F94D
0x14000faa3  mov     r9, r15
0x14000faa6  movzx   ecx, word ptr [r11+r9*2]
0x14000faab  movzx   r8d, word ptr [r10+r9*2]
0x14000fab0  lea     eax, [rcx-61h]
0x14000fab3  cmp     eax, 1Ah
0x14000fab6  lea     edx, [rcx-20h]
0x14000fab9  lea     eax, [r8-61h]
0x14000fabd  cmovnb  edx, ecx
0x14000fac0  cmp     eax, 1Ah
0x14000fac3  lea     ecx, [r8-20h]
0x14000fac7  cmovnb  ecx, r8d
0x14000facb  cmp     ecx, edx
0x14000facd  jnz     loc_14000F94A
0x14000fad3  add     r9, rdi
0x14000fad6  cmp     r9, 9
0x14000fada  jnz     short loc_14000FAA6
0x14000fadc  jmp     loc_14000F94D
0x14000fae1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fae8  lea     rsi, WPP_GLOBAL_Control
0x14000faef  cmp     rcx, rsi
0x14000faf2  jz      short loc_14000FB0F
0x14000faf4  test    [rcx+1Ch], dil
0x14000faf8  jz      short loc_14000FB0F
0x14000fafa  mov     rcx, [rcx+10h]
0x14000fafe  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000fb05  mov     edx, 27h ; '''
0x14000fb0a  call    WPP_SF_
0x14000fb0f  mov     edi, r15d
0x14000fb12  mov     eax, edi
0x14000fb14  mov     rcx, [rbp+190h+var_40]
0x14000fb1b  xor     rcx, rsp; StackCookie
0x14000fb1e  call    __security_check_cookie
0x14000fb23  add     rsp, 268h
0x14000fb2a  pop     r15
0x14000fb2c  pop     r14
0x14000fb2e  pop     rdi
0x14000fb2f  pop     rsi
0x14000fb30  pop     rbx
0x14000fb31  pop     rbp
0x14000fb32  retn
```
