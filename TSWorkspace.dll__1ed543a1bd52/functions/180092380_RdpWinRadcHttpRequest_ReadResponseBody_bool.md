# RdpWinRadcHttpRequest::ReadResponseBody(bool)

- ea: `0x180092380`
- end: `0x180092896`
- name: `?ReadResponseBody@RdpWinRadcHttpRequest@@AEAAJ_N@Z`
- size: `1302`
- prototype: `__int64 __fastcall(HINTERNET *this, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180090f7c`

## callees

- `0x18000224c`
- `0x18000ec94`
- `0x18000ece0`
- `0x180017fcc`
- `0x18001a008`
- `0x18008f2a4`
- `0x180092380`
- `0x18009342c`
- `0x180093cc4`
- `0x180093d28`
- `0x1800a3010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180092866`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180092874`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180092866`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180092874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800927fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800927fd`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800924be`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800924be`
- `WINHTTP!WinHttpReadData` at `0x180092554`
- `WINHTTP!WinHttpReadData` at `0x180092554`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall RdpWinRadcHttpRequest::ReadResponseBody(HINTERNET *this, char a2)
{
  CHAR *v4; // r15
  unsigned int v5; // eax
  signed int LastError; // ebx
  unsigned __int16 *v7; // r12
  unsigned int ActivityIdPrefix; // eax
  DWORD v9; // r14d
  DWORD v10; // r15d
  HINTERNET v11; // rbx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  DWORD v15; // r8d
  DWORD v16; // r14d
  HINTERNET v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // r8
  HINTERNET v20; // rbx
  unsigned int v21; // eax
  __int64 v22; // r8
  HINTERNET v23; // rbx
  unsigned int v24; // eax
  int v25; // eax
  HINTERNET v26; // rbx
  unsigned int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v32; // [rsp+28h] [rbp-50h]
  unsigned int v33; // [rsp+40h] [rbp-38h]
  unsigned int v34; // [rsp+44h] [rbp-34h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-30h]
  DWORD dwNumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+98h] [rbp+20h] BYREF

  lpBuffer = operator new[](0x80000u);
  v4 = (CHAR *)lpBuffer;
  if ( lpBuffer )
  {
    if ( a2 )
    {
      v33 = 0x40000;
      v7 = (unsigned __int16 *)operator new[](0x80000u);
      if ( v7 )
        goto LABEL_15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
          ActivityIdPrefix,
          -2147024882);
      }
      LastError = -2147024882;
    }
    else
    {
      v7 = 0;
      v33 = 0;
      while ( 1 )
      {
LABEL_15:
        dwNumberOfBytesAvailable = 0;
        dwNumberOfBytesRead = 0;
        if ( RdpWinRadcHttpRequest::ShouldEndEarly((RdpWinRadcHttpRequest *)this) )
        {
LABEL_72:
          LastError = 1;
          goto LABEL_73;
        }
        if ( !WinHttpQueryDataAvailable(this[5], &dwNumberOfBytesAvailable) )
          break;
        if ( RdpWinRadcHttpRequest::ShouldEndEarly((RdpWinRadcHttpRequest *)this) )
          goto LABEL_72;
        v9 = dwNumberOfBytesAvailable;
        if ( !dwNumberOfBytesAvailable )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v26 = this[2];
            v27 = RdpX_GetActivityIdPrefix();
            v28 = 136;
LABEL_60:
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v28,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v27,
              v26);
          }
LABEL_61:
          LastError = 0;
          goto LABEL_73;
        }
        v10 = dwNumberOfBytesAvailable;
        if ( dwNumberOfBytesAvailable > 0x80000 )
          v10 = 0x80000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v11 = this[2];
          v12 = RdpX_GetActivityIdPrefix();
          WPP_SF_DILL(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v12, v11, v9, v10);
        }
        v15 = v10;
        v4 = (CHAR *)lpBuffer;
        if ( !WinHttpReadData(this[5], lpBuffer, v15, &dwNumberOfBytesRead) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v29 = RdpX_GetActivityIdPrefix();
            v30 = 138;
LABEL_66:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v30,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v29,
              LastError);
            goto LABEL_67;
          }
          goto LABEL_67;
        }
        if ( RdpWinRadcHttpRequest::ShouldEndEarly((RdpWinRadcHttpRequest *)this) )
          goto LABEL_72;
        v16 = dwNumberOfBytesRead;
        if ( !dwNumberOfBytesRead )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v26 = this[2];
            v27 = RdpX_GetActivityIdPrefix();
            v28 = 139;
            goto LABEL_60;
          }
          goto LABEL_61;
        }
        if ( a2 )
        {
          v34 = v33;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v17 = this[2];
            v18 = RdpX_GetActivityIdPrefix();
            WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, v19, v18, v17, v16);
            v16 = dwNumberOfBytesRead;
          }
          LastError = ConvertAuthCookieBytesToUTF16LE(v4, v16, v7, &v34);
          if ( LastError < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v25 = RdpX_GetActivityIdPrefix();
              LODWORD(v32) = LastError;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                141,
                (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
                v25,
                (__int64)"ConvertAuthCookieBytesToUTF16LE failed",
                v32);
            }
            goto LABEL_73;
          }
          (*(void (__fastcall **)(HINTERNET, HINTERNET, unsigned __int16 *, _QWORD))(*(_QWORD *)this[25] + 56LL))(
            this[25],
            this[2],
            v7,
            v34);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v20 = this[2];
            v21 = RdpX_GetActivityIdPrefix();
            WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, v22, v21, v20, v16);
            v16 = dwNumberOfBytesRead;
          }
          (*(void (__fastcall **)(HINTERNET, HINTERNET, CHAR *, _QWORD))(*(_QWORD *)this[25] + 48LL))(
            this[25],
            this[2],
            v4,
            v16);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v23 = this[2];
          v24 = RdpX_GetActivityIdPrefix();
          WPP_SF_Dq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            144,
            &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
            v24,
            v23);
        }
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpX_GetActivityIdPrefix();
        v30 = 135;
        goto LABEL_66;
      }
LABEL_67:
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
LABEL_73:
    operator delete[](v4);
    if ( v7 )
      operator delete[](v7);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpX_GetActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
        v5,
        -2147024882);
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180092380  mov     [rsp+arg_0], rbx
0x180092385  mov     [rsp+arg_8], rsi
0x18009238a  push    rdi
0x18009238b  push    r12
0x18009238d  push    r13
0x18009238f  push    r14
0x180092391  push    r15
0x180092393  sub     rsp, 50h
0x180092397  mov     rsi, rcx
0x18009239a  mov     ebx, 80000h
0x18009239f  mov     ecx, ebx; unsigned __int64
0x1800923a1  mov     r13b, dl
0x1800923a4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800923a9  mov     [rsp+78h+lpBuffer], rax
0x1800923ae  mov     r15, rax
0x1800923b1  test    rax, rax
0x1800923b4  jnz     short loc_18009240B
0x1800923b6  mov     rax, cs:WPP_GLOBAL_Control
0x1800923bd  lea     rdi, WPP_GLOBAL_Control
0x1800923c4  cmp     rax, rdi
0x1800923c7  jz      short loc_180092401
0x1800923c9  test    byte ptr [rax+1Ch], 8
0x1800923cd  jz      short loc_180092401
0x1800923cf  cmp     byte ptr [rax+19h], 2
0x1800923d3  jb      short loc_180092401
0x1800923d5  call    RdpX_GetActivityIdPrefix
0x1800923da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800923e1  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x1800923e8  mov     edx, 85h
0x1800923ed  mov     dword ptr [rsp+78h+var_58], 8007000Eh
0x1800923f5  mov     r9d, eax
0x1800923f8  mov     rcx, [rcx+10h]
0x1800923fc  call    WPP_SF_Dd
0x180092401  mov     ebx, 8007000Eh
0x180092406  jmp     loc_18009287A
0x18009240b  test    r13b, r13b
0x18009240e  jz      short loc_18009247D
0x180092410  mov     rcx, rbx; unsigned __int64
0x180092413  mov     [rsp+78h+var_38], 40000h
0x18009241b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180092420  mov     r12, rax
0x180092423  test    rax, rax
0x180092426  jnz     short loc_180092485
0x180092428  mov     rcx, cs:WPP_GLOBAL_Control
0x18009242f  lea     rdi, WPP_GLOBAL_Control
0x180092436  cmp     rcx, rdi
0x180092439  jz      short loc_180092473
0x18009243b  test    byte ptr [rcx+1Ch], 8
0x18009243f  jz      short loc_180092473
0x180092441  cmp     byte ptr [rcx+19h], 2
0x180092445  jb      short loc_180092473
0x180092447  call    RdpX_GetActivityIdPrefix
0x18009244c  mov     rcx, cs:WPP_GLOBAL_Control
0x180092453  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18009245a  mov     edx, 86h
0x18009245f  mov     dword ptr [rsp+78h+var_58], 8007000Eh
0x180092467  mov     r9d, eax
0x18009246a  mov     rcx, [rcx+10h]
0x18009246e  call    WPP_SF_Dd
0x180092473  mov     ebx, 8007000Eh
0x180092478  jmp     loc_180092863
0x18009247d  xor     r12d, r12d
0x180092480  mov     [rsp+78h+var_38], r12d
0x180092485  lea     rdi, WPP_GLOBAL_Control
0x18009248c  mov     rcx, rsi; this
0x18009248f  mov     [rsp+78h+dwNumberOfBytesAvailable], 0
0x18009249a  mov     [rsp+78h+dwNumberOfBytesRead], 0
0x1800924a5  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x1800924aa  test    al, al
0x1800924ac  jnz     loc_18009285E
0x1800924b2  mov     rcx, [rsi+28h]; hRequest
0x1800924b6  lea     rdx, [rsp+78h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800924be  call    cs:__imp_WinHttpQueryDataAvailable
0x1800924c4  test    eax, eax
0x1800924c6  jz      loc_1800927FD
0x1800924cc  mov     rcx, rsi; this
0x1800924cf  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x1800924d4  test    al, al
0x1800924d6  jnz     loc_18009285E
0x1800924dc  mov     r14d, [rsp+78h+dwNumberOfBytesAvailable]
0x1800924e4  test    r14d, r14d
0x1800924e7  jz      loc_1800927B1
0x1800924ed  cmp     r14d, ebx
0x1800924f0  mov     r15d, r14d
0x1800924f3  cmova   r15d, ebx
0x1800924f7  mov     rax, cs:WPP_GLOBAL_Control
0x1800924fe  cmp     rax, rdi
0x180092501  jz      short loc_18009253D
0x180092503  test    dword ptr [rax+1Ch], 10000h
0x18009250a  jz      short loc_18009253D
0x18009250c  cmp     byte ptr [rax+19h], 5
0x180092510  jb      short loc_18009253D
0x180092512  mov     rbx, [rsi+10h]
0x180092516  call    RdpX_GetActivityIdPrefix
0x18009251b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092522  mov     r9d, eax
0x180092525  mov     [rsp+78h+var_48], r15d
0x18009252a  mov     dword ptr [rsp+78h+var_50], r14d
0x18009252f  mov     [rsp+78h+var_58], rbx
0x180092534  mov     rcx, [rcx+10h]
0x180092538  call    WPP_SF_DILL
0x18009253d  mov     rcx, [rsi+28h]; hRequest
0x180092541  lea     r9, [rsp+78h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180092549  mov     r8d, r15d; dwNumberOfBytesToRead
0x18009254c  mov     r15, [rsp+78h+lpBuffer]
0x180092551  mov     rdx, r15; lpBuffer
0x180092554  call    cs:__imp_WinHttpReadData
0x18009255a  test    eax, eax
0x18009255c  jz      loc_180092779
0x180092562  mov     rcx, rsi; this
0x180092565  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x18009256a  test    al, al
0x18009256c  jnz     loc_18009285E
0x180092572  mov     r14d, [rsp+78h+dwNumberOfBytesRead]
0x18009257a  test    r14d, r14d
0x18009257d  jz      loc_180092742
0x180092583  test    r13b, r13b
0x180092586  jz      loc_180092617
0x18009258c  mov     eax, [rsp+78h+var_38]
0x180092590  mov     [rsp+78h+var_34], eax
0x180092594  mov     rax, cs:WPP_GLOBAL_Control
0x18009259b  cmp     rax, rdi
0x18009259e  jz      short loc_1800925E2
0x1800925a0  test    dword ptr [rax+1Ch], 10000h
0x1800925a7  jz      short loc_1800925E2
0x1800925a9  cmp     byte ptr [rax+19h], 4
0x1800925ad  jb      short loc_1800925E2
0x1800925af  mov     rbx, [rsi+10h]
0x1800925b3  call    RdpX_GetActivityIdPrefix
0x1800925b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800925bf  mov     edx, 8Ch
0x1800925c4  mov     dword ptr [rsp+78h+var_50], r14d
0x1800925c9  mov     r9d, eax
0x1800925cc  mov     [rsp+78h+var_58], rbx
0x1800925d1  mov     rcx, [rcx+10h]
0x1800925d5  call    WPP_SF_DID
0x1800925da  mov     r14d, [rsp+78h+dwNumberOfBytesRead]
0x1800925e2  lea     r9, [rsp+78h+var_34]; unsigned int *
0x1800925e7  mov     r8, r12; unsigned __int16 *
0x1800925ea  mov     edx, r14d; cbMultiByte
0x1800925ed  mov     rcx, r15; lpMultiByteStr
0x1800925f0  call    ?ConvertAuthCookieBytesToUTF16LE@@YAJPEAEKPEAGPEAI@Z; ConvertAuthCookieBytesToUTF16LE(uchar *,ulong,ushort *,uint *)
0x1800925f5  mov     ebx, eax
0x1800925f7  test    eax, eax
0x1800925f9  js      loc_1800926E5
0x1800925ff  mov     rcx, [rsi+0C8h]
0x180092606  mov     r8, r12
0x180092609  mov     r9d, [rsp+78h+var_34]
0x18009260e  mov     rax, [rcx]
0x180092611  mov     rax, [rax+38h]
0x180092615  jmp     short loc_180092679
0x180092617  mov     rax, cs:WPP_GLOBAL_Control
0x18009261e  cmp     rax, rdi
0x180092621  jz      short loc_180092665
0x180092623  test    dword ptr [rax+1Ch], 10000h
0x18009262a  jz      short loc_180092665
0x18009262c  cmp     byte ptr [rax+19h], 5
0x180092630  jb      short loc_180092665
0x180092632  mov     rbx, [rsi+10h]
0x180092636  call    RdpX_GetActivityIdPrefix
0x18009263b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092642  mov     edx, 8Eh
0x180092647  mov     dword ptr [rsp+78h+var_50], r14d
0x18009264c  mov     r9d, eax
0x18009264f  mov     [rsp+78h+var_58], rbx
0x180092654  mov     rcx, [rcx+10h]
0x180092658  call    WPP_SF_DID
0x18009265d  mov     r14d, [rsp+78h+dwNumberOfBytesRead]
0x180092665  mov     rcx, [rsi+0C8h]
0x18009266c  mov     r9d, r14d
0x18009266f  mov     r8, r15
0x180092672  mov     rax, [rcx]
0x180092675  mov     rax, [rax+30h]
0x180092679  mov     rdx, [rsi+10h]
0x18009267d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092682  mov     rax, cs:WPP_GLOBAL_Control
0x180092689  mov     ebx, 80000h
0x18009268e  cmp     rax, rdi
0x180092691  jz      loc_18009248C
0x180092697  test    dword ptr [rax+1Ch], 10000h
0x18009269e  jz      loc_18009248C
0x1800926a4  cmp     byte ptr [rax+19h], 4
0x1800926a8  jb      loc_18009248C
0x1800926ae  mov     rbx, [rsi+10h]
0x1800926b2  call    RdpX_GetActivityIdPrefix
0x1800926b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800926be  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x1800926c5  mov     edx, 90h
0x1800926ca  mov     [rsp+78h+var_58], rbx
0x1800926cf  mov     r9d, eax
0x1800926d2  mov     rcx, [rcx+10h]
0x1800926d6  call    WPP_SF_Dq
0x1800926db  mov     ebx, 80000h
0x1800926e0  jmp     loc_18009248C
0x1800926e5  mov     rax, cs:WPP_GLOBAL_Control
0x1800926ec  cmp     rax, rdi
0x1800926ef  jz      loc_180092863
0x1800926f5  test    byte ptr [rax+1Ch], 8
0x1800926f9  jz      loc_180092863
0x1800926ff  cmp     byte ptr [rax+19h], 2
0x180092703  jb      loc_180092863
0x180092709  call    RdpX_GetActivityIdPrefix
0x18009270e  lea     rcx, aConvertauthcoo; "ConvertAuthCookieBytesToUTF16LE failed"
0x180092715  mov     dword ptr [rsp+78h+var_50], ebx
0x180092719  mov     [rsp+78h+var_58], rcx
0x18009271e  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180092725  mov     rcx, cs:WPP_GLOBAL_Control
0x18009272c  mov     edx, 8Dh
0x180092731  mov     r9d, eax
0x180092734  mov     rcx, [rcx+10h]
0x180092738  call    WPP_SF_DsD
0x18009273d  jmp     loc_180092863
0x180092742  mov     rax, cs:WPP_GLOBAL_Control
0x180092749  cmp     rax, rdi
0x18009274c  jz      loc_1800927F9
0x180092752  test    dword ptr [rax+1Ch], 10000h
0x180092759  jz      loc_1800927F9
0x18009275f  cmp     byte ptr [rax+19h], 4
0x180092763  jb      loc_1800927F9
0x180092769  mov     rbx, [rsi+10h]
0x18009276d  call    RdpX_GetActivityIdPrefix
0x180092772  mov     edx, 8Bh
0x180092777  jmp     short loc_1800927DA
0x180092779  call    cs:__imp_GetLastError
0x18009277f  mov     ebx, eax
0x180092781  mov     rax, cs:WPP_GLOBAL_Control
0x180092788  cmp     rax, rdi
0x18009278b  jz      loc_180092845
0x180092791  test    byte ptr [rax+1Ch], 8
0x180092795  jz      loc_180092845
0x18009279b  cmp     byte ptr [rax+19h], 2
0x18009279f  jb      loc_180092845
0x1800927a5  call    RdpX_GetActivityIdPrefix
0x1800927aa  mov     edx, 8Ah
0x1800927af  jmp     short loc_180092827
0x1800927b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800927b8  cmp     rax, rdi
0x1800927bb  jz      short loc_1800927F9
0x1800927bd  test    dword ptr [rax+1Ch], 10000h
0x1800927c4  jz      short loc_1800927F9
0x1800927c6  cmp     byte ptr [rax+19h], 4
0x1800927ca  jb      short loc_1800927F9
0x1800927cc  mov     rbx, [rsi+10h]
0x1800927d0  call    RdpX_GetActivityIdPrefix
0x1800927d5  mov     edx, 88h
0x1800927da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800927e1  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x1800927e8  mov     r9d, eax
0x1800927eb  mov     [rsp+78h+var_58], rbx
0x1800927f0  mov     rcx, [rcx+10h]
0x1800927f4  call    WPP_SF_Dq
0x1800927f9  xor     ebx, ebx
0x1800927fb  jmp     short loc_180092863
0x1800927fd  call    cs:__imp_GetLastError
0x180092803  mov     ebx, eax
0x180092805  mov     rax, cs:WPP_GLOBAL_Control
0x18009280c  cmp     rax, rdi
0x18009280f  jz      short loc_180092845
0x180092811  test    byte ptr [rax+1Ch], 8
0x180092815  jz      short loc_180092845
0x180092817  cmp     byte ptr [rax+19h], 2
0x18009281b  jb      short loc_180092845
0x18009281d  call    RdpX_GetActivityIdPrefix
0x180092822  mov     edx, 87h
0x180092827  mov     rcx, cs:WPP_GLOBAL_Control
0x18009282e  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180092835  mov     r9d, eax
0x180092838  mov     dword ptr [rsp+78h+var_58], ebx
0x18009283c  mov     rcx, [rcx+10h]
0x180092840  call    WPP_SF_Dd
0x180092845  test    ebx, ebx
0x180092847  jle     short loc_180092852
0x180092849  movzx   ebx, bx
0x18009284c  or      ebx, 80070000h
0x180092852  test    ebx, ebx
0x180092854  mov     eax, 80004005h
0x180092859  cmovns  ebx, eax
0x18009285c  jmp     short loc_180092863
0x18009285e  mov     ebx, 1
0x180092863  mov     rcx, r15
0x180092866  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18009286c  test    r12, r12
0x18009286f  jz      short loc_18009287A
0x180092871  mov     rcx, r12
0x180092874  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18009287a  lea     r11, [rsp+78h+var_28]
0x18009287f  mov     eax, ebx
0x180092881  mov     rbx, [r11+30h]
0x180092885  mov     rsi, [r11+38h]
0x180092889  mov     rsp, r11
0x18009288c  pop     r15
0x18009288e  pop     r14
0x180092890  pop     r13
0x180092892  pop     r12
0x180092894  pop     rdi
0x180092895  retn
```
