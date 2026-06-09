# HrGetBitmapData(HBITMAP__ *,HPALETTE__ *,ushort,tagBITMAPINFO * *,void * *,void * *)

- ea: `0x1800802d4`
- end: `0x180080766`
- name: `?HrGetBitmapData@@YAJPEAUHBITMAP__@@PEAUHPALETTE__@@GPEAPEAUtagBITMAPINFO@@PEAPEAX3@Z`
- size: `1170`
- prototype: `__int64 __fastcall(HBITMAP, HPALETTE, unsigned __int16 biBitCount, struct tagBITMAPINFO **, void **, void **)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007fc2c`
- `0x18007fec8`
- `0x18007ffc0`
- `0x1800c5adc`

## callees

- `0x1800802d4`
- `0x1800bb784`
- `0x1800c9a78`
- `0x1800c9be8`
- `0x1800e3c04`
- `0x18017ad7c`
- `0x18017ae70`
- `0x18017b044`
- `0x18017b528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008062b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008063d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008062b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008063d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180080362`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180080464`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800805cd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180080362`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180080464`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800805cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800802fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008039d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800802fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008039d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008032e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800805ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800806bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008032e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800805ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800806bd`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18008052b`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18008052b`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180080320`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180080320`
- `ext-ms-win-gdi-dc-l1-2-0!GetPaletteEntries` at `0x180080656`
- `ext-ms-win-gdi-dc-l1-2-0!GetPaletteEntries` at `0x180080656`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x1800803c3`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x1800804df`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x1800803c3`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x1800804df`

## pseudocode

```c
__int64 __fastcall HrGetBitmapData(
        HBITMAP a1,
        HPALETTE a2,
        unsigned __int16 biBitCount,
        struct tagBITMAPINFO **a4,
        void **a5,
        void **a6)
{
  UINT PaletteEntries; // r14d
  HDC CompatibleDC; // r13
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // ebx
  struct tagPALETTEENTRY *v13; // rbx
  struct tagBITMAPINFO *v14; // rax
  struct tagBITMAPINFO *lpbmi; // rdi
  void *v16; // r15
  int biHeight; // ecx
  unsigned int biWidth; // r8d
  int v19; // eax
  unsigned int v20; // r8d
  void *v21; // rax
  void *lpvBits; // rbp
  bool v24; // zf
  struct tagPALETTEENTRY *v25; // rax
  signed int v26; // eax
  signed int v27; // eax

  SetLastError(0);
  PaletteEntries = 0;
  if ( !(unsigned __int8)IsDeleteDCPresent() || !(unsigned __int8)IsDeleteDCPresent() )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147467263);
    return (unsigned int)-2147467263;
  }
  CompatibleDC = CreateCompatibleDC(0);
  if ( !CompatibleDC )
  {
    LastError = GetLastError();
    v11 = LastError < 0;
    if ( LastError > 0 )
      v11 = 1;
    if ( v11 )
    {
      v12 = CheckGdiHandlesNearLimit();
      if ( v12 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
        {
          DoStackCapture(v12);
          if ( (_DWORD)g_doStackCaptures )
            DoStackCapture(v12);
        }
        return (unsigned int)v12;
      }
    }
  }
  if ( a2 )
  {
    v25 = (struct tagPALETTEENTRY *)malloc(0x400u);
    v13 = v25;
    if ( v25 )
      memset_0(v25, 0, 0x400u);
    if ( !(unsigned __int8)IsGetObjectAPresent() )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147467263);
      v12 = -2147467263;
      goto LABEL_35;
    }
    PaletteEntries = GetPaletteEntries(a2, 0, 0x100u, v13);
  }
  else
  {
    v13 = 0;
  }
  v14 = (struct tagBITMAPINFO *)malloc(0x42Cu);
  lpbmi = v14;
  if ( v14 )
  {
    v16 = 0;
    memset_0(&v14->bmiHeader.biWidth, 0, 0x428u);
    lpbmi->bmiHeader.biSize = 40;
    if ( !(unsigned __int8)IsSetDIBitsPresent() )
      goto LABEL_66;
    SetLastError(0);
    if ( !GetDIBits(CompatibleDC, a1, 0, 0, 0, lpbmi, 0) )
    {
      v26 = GetLastError();
      v12 = v26;
      if ( v26 > 0 )
        v12 = (unsigned __int16)v26 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2003292268;
      v24 = (_DWORD)g_doStackCaptures == 0;
      goto LABEL_60;
    }
    if ( !biBitCount )
    {
      biBitCount = lpbmi->bmiHeader.biBitCount;
      if ( biBitCount )
        goto LABEL_15;
      biBitCount = 32;
    }
    lpbmi->bmiHeader.biBitCount = biBitCount;
LABEL_15:
    lpbmi->bmiHeader.biPlanes = 1;
    if ( a2 )
    {
      memcpy_0(lpbmi->bmiColors, v13, 4LL * PaletteEntries);
      if ( PaletteEntries > 2 )
      {
        if ( PaletteEntries > 0x10 )
        {
          if ( PaletteEntries <= 0x100 )
            lpbmi->bmiHeader.biBitCount = 8;
        }
        else
        {
          lpbmi->bmiHeader.biBitCount = 4;
        }
      }
      else
      {
        lpbmi->bmiHeader.biBitCount = 2;
      }
      biBitCount = lpbmi->bmiHeader.biBitCount;
    }
    else
    {
      lpbmi->bmiHeader.biCompression = 0;
    }
    biHeight = lpbmi->bmiHeader.biHeight;
    if ( biHeight > 0 )
    {
      biHeight = -biHeight;
      lpbmi->bmiHeader.biHeight = biHeight;
    }
    if ( biBitCount )
    {
      biWidth = lpbmi->bmiHeader.biWidth;
      if ( biWidth <= 0x7FFFFFF8u / biBitCount )
      {
        v19 = -biHeight;
        if ( biHeight > 0 )
          v19 = biHeight;
        if ( v19
          && (v20 = (((biBitCount * biWidth + 7) >> 3) + 3) & 0xFFFFFFFC) != 0
          && v20 < 0xFFFFFFFFFFFFFF7FuLL / v19 )
        {
          v21 = malloc(v19 * (unsigned __int64)v20 + 128);
          v16 = v21;
          if ( v21 )
          {
            v12 = 0;
            lpvBits = (void *)(((unsigned __int64)v21 + 127) & 0xFFFFFFFFFFFFFF80uLL);
            if ( (unsigned __int8)IsSetDIBitsPresent() )
            {
              if ( GetDIBits(CompatibleDC, a1, 0, -lpbmi->bmiHeader.biHeight, lpvBits, lpbmi, a2 != 0) )
                goto LABEL_34;
              v27 = GetLastError();
              v12 = v27;
              if ( v27 > 0 )
                v12 = (unsigned __int16)v27 | 0x80070000;
              if ( v12 >= 0 )
              {
LABEL_34:
                lpbmi->bmiHeader.biHeight = -lpbmi->bmiHeader.biHeight;
                *a4 = lpbmi;
                *a5 = lpvBits;
                *a6 = v16;
                goto LABEL_35;
              }
              if ( !(_DWORD)g_doStackCaptures )
                goto LABEL_62;
LABEL_61:
              DoStackCapture(v12);
LABEL_62:
              free(lpbmi);
              if ( v16 )
                free(v16);
              goto LABEL_35;
            }
LABEL_66:
            if ( (_DWORD)g_doStackCaptures )
              DoStackCapture(-2147467263);
            v12 = -2147467263;
            goto LABEL_62;
          }
          v12 = -2147024882;
        }
        else
        {
          v16 = 0;
          v12 = -2147024809;
        }
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v12);
        goto LABEL_62;
      }
    }
    v12 = -2147024362;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_62;
    DoStackCapture(-2147024362);
    v24 = (_DWORD)g_doStackCaptures == 0;
LABEL_60:
    if ( v24 )
      goto LABEL_62;
    goto LABEL_61;
  }
  v12 = -2147024882;
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(-2147024882);
LABEL_35:
  if ( !CompatibleDC )
    return (unsigned int)v12;
  if ( (unsigned __int8)IsDeleteDCPresent() )
  {
    DeleteDC(CompatibleDC);
    return (unsigned int)v12;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800802d4  mov     [rsp+arg_8], rbx
0x1800802d9  mov     [rsp+arg_18], r9
0x1800802de  mov     [rsp+hbm], rcx
0x1800802e3  push    rbp
0x1800802e4  push    rsi
0x1800802e5  push    rdi
0x1800802e6  push    r12
0x1800802e8  push    r13
0x1800802ea  push    r14
0x1800802ec  push    r15
0x1800802ee  sub     rsp, 40h
0x1800802f2  xor     ecx, ecx; dwErrCode
0x1800802f4  movzx   ebp, r8w
0x1800802f8  mov     r12, rdx
0x1800802fb  call    cs:__imp_SetLastError
0x180080301  call    IsDeleteDCPresent
0x180080306  xor     r14d, r14d
0x180080309  test    al, al
0x18008030b  jz      loc_1800805AA
0x180080311  call    IsDeleteDCPresent
0x180080316  test    al, al
0x180080318  jz      loc_1800805AA
0x18008031e  xor     ecx, ecx; hdc
0x180080320  call    cs:__imp_CreateCompatibleDC
0x180080326  mov     r13, rax
0x180080329  test    rax, rax
0x18008032c  jnz     short loc_18008034D
0x18008032e  call    cs:__imp_GetLastError
0x180080334  test    eax, eax
0x180080336  jg      loc_18008066E
0x18008033c  jns     short loc_18008034D
0x18008033e  call    ?CheckGdiHandlesNearLimit@@YAJXZ; CheckGdiHandlesNearLimit(void)
0x180080343  mov     ebx, eax
0x180080345  test    eax, eax
0x180080347  js      loc_180080562
0x18008034d  mov     esi, 80004001h
0x180080352  test    r12, r12
0x180080355  jnz     loc_1800805C6
0x18008035b  xor     ebx, ebx
0x18008035d  mov     ecx, 42Ch; Size
0x180080362  call    cs:__imp_malloc
0x180080368  mov     rdi, rax
0x18008036b  test    rax, rax
0x18008036e  jz      loc_18008069C
0x180080374  lea     rcx, [rax+4]; void *
0x180080378  xor     edx, edx; Val
0x18008037a  mov     r8d, 428h; Size
0x180080380  xor     r15d, r15d
0x180080383  call    memset_0
0x180080388  mov     dword ptr [rdi], 28h ; '('
0x18008038e  call    IsSetDIBitsPresent
0x180080393  test    al, al
0x180080395  jz      loc_180080706
0x18008039b  xor     ecx, ecx; dwErrCode
0x18008039d  call    cs:__imp_SetLastError
0x1800803a3  mov     rdx, [rsp+78h+hbm]; hbm
0x1800803ab  xor     r9d, r9d; cLines
0x1800803ae  mov     [rsp+78h+usage], r15d; usage
0x1800803b3  xor     r8d, r8d; start
0x1800803b6  mov     [rsp+78h+lpbmi], rdi; lpbmi
0x1800803bb  mov     rcx, r13; hdc
0x1800803be  mov     [rsp+78h+lpvBits], r15; lpvBits
0x1800803c3  call    cs:__imp_GetDIBits
0x1800803c9  test    eax, eax
0x1800803cb  jz      loc_1800805FF
0x1800803d1  test    bp, bp
0x1800803d4  jz      loc_18008054B
0x1800803da  mov     [rdi+0Eh], bp
0x1800803de  mov     word ptr [rdi+0Ch], 1
0x1800803e4  test    r12, r12
0x1800803e7  jnz     loc_18008070E
0x1800803ed  xor     r14d, r14d
0x1800803f0  mov     [rdi+10h], r14d
0x1800803f4  mov     ecx, [rdi+8]
0x1800803f7  test    ecx, ecx
0x1800803f9  jle     short loc_180080400
0x1800803fb  neg     ecx
0x1800803fd  mov     [rdi+8], ecx
0x180080400  movzx   r9d, bp
0x180080404  test    r9d, r9d
0x180080407  jz      loc_180080586
0x18008040d  mov     r8d, [rdi+4]
0x180080411  xor     edx, edx
0x180080413  mov     eax, 7FFFFFF8h
0x180080418  div     r9d
0x18008041b  cmp     r8d, eax
0x18008041e  ja      loc_180080586
0x180080424  mov     eax, ecx
0x180080426  neg     eax
0x180080428  cmovs   eax, ecx
0x18008042b  movsxd  r10, eax
0x18008042e  test    eax, eax
0x180080430  jz      short loc_180080483
0x180080432  imul    r8d, r9d
0x180080436  add     r8d, 7
0x18008043a  shr     r8d, 3
0x18008043e  add     r8d, 3
0x180080442  and     r8d, 0FFFFFFFCh
0x180080446  jz      short loc_180080483
0x180080448  xor     edx, edx
0x18008044a  mov     ecx, r8d
0x18008044d  mov     rax, 0FFFFFFFFFFFFFF7Fh
0x180080454  div     r10
0x180080457  cmp     rcx, rax
0x18008045a  jnb     short loc_180080483
0x18008045c  imul    rcx, r10
0x180080460  sub     rcx, 0FFFFFFFFFFFFFF80h; Size
0x180080464  call    cs:__imp_malloc
0x18008046a  mov     r15, rax
0x18008046d  test    rax, rax
0x180080470  jz      loc_180080664
0x180080476  lea     rbp, [rax+7Fh]
0x18008047a  mov     ebx, r14d
0x18008047d  and     rbp, 0FFFFFFFFFFFFFF80h
0x180080481  jmp     short loc_1800804A6
0x180080483  mov     r15, r14
0x180080486  mov     ebx, 80070057h
0x18008048b  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180080492  mov     rbp, r14
0x180080495  jz      short loc_18008049E
0x180080497  mov     ecx, ebx; int
0x180080499  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008049e  test    ebx, ebx
0x1800804a0  js      loc_180080628
0x1800804a6  call    IsSetDIBitsPresent
0x1800804ab  test    al, al
0x1800804ad  jz      loc_180080688
0x1800804b3  mov     r9d, [rdi+8]
0x1800804b7  mov     eax, r14d
0x1800804ba  mov     rdx, [rsp+78h+hbm]; hbm
0x1800804c2  test    r12, r12
0x1800804c5  mov     rcx, r13; hdc
0x1800804c8  setnz   al
0x1800804cb  neg     r9d; cLines
0x1800804ce  mov     [rsp+78h+usage], eax; usage
0x1800804d2  xor     r8d, r8d; start
0x1800804d5  mov     [rsp+78h+lpbmi], rdi; lpbmi
0x1800804da  mov     [rsp+78h+lpvBits], rbp; lpvBits
0x1800804df  call    cs:__imp_GetDIBits
0x1800804e5  test    eax, eax
0x1800804e7  jz      loc_1800806BD
0x1800804ed  mov     eax, [rdi+8]
0x1800804f0  neg     eax
0x1800804f2  mov     [rdi+8], eax
0x1800804f5  mov     rax, [rsp+78h+arg_18]
0x1800804fd  mov     [rax], rdi
0x180080500  mov     rax, [rsp+78h+arg_20]
0x180080508  mov     [rax], rbp
0x18008050b  mov     rax, [rsp+78h+arg_28]
0x180080513  mov     [rax], r15
0x180080516  test    r13, r13
0x180080519  jz      short loc_180080531
0x18008051b  call    IsDeleteDCPresent
0x180080520  test    al, al
0x180080522  jz      loc_18008075A
0x180080528  mov     rcx, r13; hdc
0x18008052b  call    cs:__imp_DeleteDC
0x180080531  mov     eax, ebx
0x180080533  mov     rbx, [rsp+78h+arg_8]
0x18008053b  add     rsp, 40h
0x18008053f  pop     r15
0x180080541  pop     r14
0x180080543  pop     r13
0x180080545  pop     r12
0x180080547  pop     rdi
0x180080548  pop     rsi
0x180080549  pop     rbp
0x18008054a  retn
0x18008054b  movzx   ebp, word ptr [rdi+0Eh]
0x18008054f  test    bp, bp
0x180080552  jnz     loc_1800803DE
0x180080558  mov     ebp, 20h ; ' '
0x18008055d  jmp     loc_1800803DA
0x180080562  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180080568  test    eax, eax
0x18008056a  jz      short loc_180080531
0x18008056c  mov     ecx, ebx; int
0x18008056e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180080573  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180080579  test    eax, eax
0x18008057b  jz      short loc_180080531
0x18008057d  mov     ecx, ebx; int
0x18008057f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180080584  jmp     short loc_180080531
0x180080586  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18008058c  mov     ebx, 80070216h
0x180080591  test    eax, eax
0x180080593  jz      loc_180080628
0x180080599  mov     ecx, ebx; int
0x18008059b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800805a0  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800805a6  test    eax, eax
0x1800805a8  jmp     short loc_18008061F
0x1800805aa  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800805b1  mov     esi, 80004001h
0x1800805b6  jz      short loc_1800805BF
0x1800805b8  mov     ecx, esi; int
0x1800805ba  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800805bf  mov     ebx, esi
0x1800805c1  jmp     loc_180080531
0x1800805c6  mov     edi, 400h
0x1800805cb  mov     ecx, edi; Size
0x1800805cd  call    cs:__imp_malloc
0x1800805d3  mov     rbx, rax
0x1800805d6  test    rax, rax
0x1800805d9  jnz     loc_1800806F4
0x1800805df  call    IsGetObjectAPresent
0x1800805e4  test    al, al
0x1800805e6  jnz     short loc_180080648
0x1800805e8  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800805ef  jz      short loc_1800805F8
0x1800805f1  mov     ecx, esi; int
0x1800805f3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800805f8  mov     ebx, esi
0x1800805fa  jmp     loc_180080516
0x1800805ff  call    cs:__imp_GetLastError
0x180080605  xor     r14d, r14d
0x180080608  mov     ebx, eax
0x18008060a  test    eax, eax
0x18008060c  jg      short loc_18008067D
0x18008060e  test    ebx, ebx
0x180080610  mov     eax, 88982F94h
0x180080615  cmovns  ebx, eax
0x180080618  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18008061f  jz      short loc_180080628
0x180080621  mov     ecx, ebx; int
0x180080623  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180080628  mov     rcx, rdi; Block
0x18008062b  call    cs:__imp_free
0x180080631  test    r15, r15
0x180080634  jz      loc_180080516
0x18008063a  mov     rcx, r15; Block
0x18008063d  call    cs:__imp_free
0x180080643  jmp     loc_180080516
0x180080648  mov     r9, rbx; pPalEntries
0x18008064b  xor     edx, edx; iStart
0x18008064d  mov     r8d, 100h; cEntries
0x180080653  mov     rcx, r12; hpal
0x180080656  call    cs:__imp_GetPaletteEntries
0x18008065c  mov     r14d, eax
0x18008065f  jmp     loc_18008035D
0x180080664  mov     ebx, 8007000Eh
0x180080669  jmp     loc_18008048B
0x18008066e  movzx   eax, ax
0x180080671  or      eax, 80070000h
0x180080676  test    eax, eax
0x180080678  jmp     loc_18008033C
0x18008067d  movzx   ebx, ax
0x180080680  or      ebx, 80070000h
0x180080686  jmp     short loc_18008060E
0x180080688  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18008068f  jz      short loc_180080698
0x180080691  mov     ecx, esi; int
0x180080693  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180080698  mov     ebx, esi
0x18008069a  jmp     short loc_180080628
0x18008069c  xor     r14d, r14d
0x18008069f  mov     ebx, 8007000Eh
0x1800806a4  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800806ab  jz      loc_180080516
0x1800806b1  mov     ecx, ebx; int
0x1800806b3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800806b8  jmp     loc_180080516
0x1800806bd  call    cs:__imp_GetLastError
0x1800806c3  mov     ebx, eax
0x1800806c5  test    eax, eax
0x1800806c7  jle     short loc_1800806D2
0x1800806c9  movzx   ebx, ax
0x1800806cc  or      ebx, 80070000h
0x1800806d2  test    ebx, ebx
0x1800806d4  jns     loc_1800804ED
0x1800806da  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800806e1  jnz     loc_180080621
0x1800806e7  test    ebx, ebx
0x1800806e9  js      loc_180080628
0x1800806ef  jmp     loc_1800804ED
0x1800806f4  mov     r8, rdi; Size
0x1800806f7  xor     edx, edx; Val
0x1800806f9  mov     rcx, rbx; void *
0x1800806fc  call    memset_0
0x180080701  jmp     loc_1800805DF
0x180080706  xor     r14d, r14d
0x180080709  jmp     loc_180080688
0x18008070e  mov     r8d, r14d
0x180080711  lea     rcx, [rdi+28h]; void *
0x180080715  shl     r8, 2; Size
0x180080719  mov     rdx, rbx; Src
0x18008071c  call    memcpy_0
0x180080721  mov     eax, 2
0x180080726  cmp     r14d, eax
0x180080729  ja      short loc_180080731
0x18008072b  mov     [rdi+0Eh], ax
0x18008072f  jmp     short loc_18008074E
0x180080731  cmp     r14d, 10h
0x180080735  ja      short loc_18008073F
0x180080737  mov     word ptr [rdi+0Eh], 4
0x18008073d  jmp     short loc_18008074E
0x18008073f  cmp     r14d, 100h
0x180080746  ja      short loc_18008074E
0x180080748  mov     word ptr [rdi+0Eh], 8
  ... truncated ...
```
