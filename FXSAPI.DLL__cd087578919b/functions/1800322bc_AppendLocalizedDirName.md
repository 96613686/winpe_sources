# AppendLocalizedDirName

- ea: `0x1800322bc`
- end: `0x180032682`
- name: `AppendLocalizedDirName`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18003291c`

## callees

- `0x180008438`
- `0x18000abe4`
- `0x18000ac14`
- `0x1800321cc`
- `0x1800322bc`
- `0x18003d4ca`
- `0x18003d510`
- `0x18003e010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800324c8`
- `KERNEL32!LoadLibraryW` at `0x1800324c8`
- `KERNEL32!FreeLibrary` at `0x1800323cf`
- `KERNEL32!FreeLibrary` at `0x1800323cf`
- `KERNEL32!GetProcAddress` at `0x18003252f`
- `KERNEL32!GetProcAddress` at `0x18003252f`
- `KERNEL32!GetLastError` at `0x180032407`
- `KERNEL32!GetLastError` at `0x1800324dc`
- `KERNEL32!GetLastError` at `0x180032540`
- `KERNEL32!GetLastError` at `0x1800325c8`
- `KERNEL32!GetLastError` at `0x180032407`
- `KERNEL32!GetLastError` at `0x1800324dc`
- `KERNEL32!GetLastError` at `0x180032540`
- `KERNEL32!GetLastError` at `0x1800325c8`

## string_xrefs

- `0x1800324c1`: `Kernel32.dll`
- `0x180032525`: `GetFileMUIPath`

## pseudocode

```c
__int64 __fastcall AppendLocalizedDirName(_WORD *a1, unsigned __int16 *a2)
{
  HMODULE v4; // rsi
  int v5; // ebx
  unsigned __int16 *v6; // r8
  int v7; // eax
  unsigned int v8; // edi
  DWORD v9; // ebx
  DWORD LastError; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  _WORD *v14; // r8
  __int64 v15; // rax
  _WORD *v16; // rcx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  DWORD v19; // eax
  __int64 result; // rax
  __int64 v21; // [rsp+48h] [rbp-460h]
  _BYTE v22[528]; // [rsp+50h] [rbp-458h] BYREF
  unsigned __int16 v23[264]; // [rsp+260h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids);
  }
  memset_0(v22, 0, 0x208u);
  memset_0(v23, 0, 0x208u);
  HIWORD(v21) = 0;
  if ( !(unsigned int)LonghornOrMore() )
  {
    v4 = 0;
LABEL_7:
    v5 = 0;
    goto LABEL_8;
  }
  if ( !a1 )
  {
    v8 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids);
    }
    v9 = 87;
    goto LABEL_55;
  }
  v13 = 260;
  v14 = v22;
  v5 = 1;
  v15 = 2147483646;
  do
  {
    if ( !v15 )
      break;
    if ( !*a1 )
      break;
    *v14++ = *a1++;
    --v15;
    --v13;
  }
  while ( v13 );
  v16 = v14 - 1;
  v8 = v13 == 0 ? 0x8007007A : 0;
  if ( v13 )
    v16 = v14;
  *v16 = 0;
  if ( !v13 )
  {
    v9 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v8);
    }
    goto LABEL_55;
  }
  LibraryW = LoadLibraryW(L"Kernel32.dll");
  v4 = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_55;
    }
    v12 = 38;
LABEL_38:
    WPP_SF_d(v11[2], v12, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, LastError);
    goto LABEL_55;
  }
  ProcAddress = GetProcAddress(LibraryW, "GetFileMUIPath");
  if ( !ProcAddress )
  {
    v19 = GetLastError();
    v9 = v19;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v19);
    }
    goto LABEL_16;
  }
  if ( !((unsigned int (__fastcall *)(__int64, _BYTE *, _QWORD))ProcAddress)(16, v22, 0) )
  {
    v9 = GetLastError();
    if ( v9 != 18 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, v8);
      }
      goto LABEL_16;
    }
    goto LABEL_7;
  }
LABEL_8:
  v6 = (unsigned __int16 *)v22;
  if ( v5 )
    v6 = v23;
  v7 = StringCchCopyW(a2, 0x104u, v6);
  v8 = v7;
  if ( v7 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, (unsigned int)v7);
  }
  v9 = 0;
  if ( v4 )
  {
LABEL_16:
    if ( FreeLibrary(v4)
      || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_55;
    }
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    v12 = 42;
    goto LABEL_38;
  }
LABEL_55:
  result = (unsigned __int16)v8;
  if ( (v8 & 0x80000000) == 0 )
    return v9;
  return result;
}

```

## disassembly

```asm
0x1800322bc  mov     [rsp+arg_0], rbx
0x1800322c1  mov     [rsp+arg_10], rbp
0x1800322c6  push    rsi
0x1800322c7  push    rdi
0x1800322c8  push    r12
0x1800322ca  push    r13
0x1800322cc  push    r14
0x1800322ce  sub     rsp, 480h
0x1800322d5  mov     rax, cs:__security_cookie
0x1800322dc  xor     rax, rsp
0x1800322df  mov     [rsp+4A8h+var_38], rax
0x1800322e7  mov     rbp, rdx
0x1800322ea  mov     rdi, rcx
0x1800322ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800322f4  lea     r12, WPP_GLOBAL_Control
0x1800322fb  lea     r13, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids
0x180032302  cmp     rcx, r12
0x180032305  jz      short loc_180032324
0x180032307  test    byte ptr [rcx+1Ch], 2
0x18003230b  jz      short loc_180032324
0x18003230d  cmp     byte ptr [rcx+19h], 5
0x180032311  jb      short loc_180032324
0x180032313  mov     rcx, [rcx+10h]
0x180032317  mov     edx, 23h ; '#'
0x18003231c  mov     r8, r13
0x18003231f  call    WPP_SF_
0x180032324  mov     ebx, 208h
0x180032329  lea     rcx, [rsp+4A8h+var_458]; void *
0x18003232e  mov     r8d, ebx; Size
0x180032331  xor     edx, edx; Val
0x180032333  call    memset_0
0x180032338  mov     r8d, ebx; Size
0x18003233b  lea     rcx, [rsp+4A8h+var_248]; void *
0x180032343  xor     edx, edx; Val
0x180032345  call    memset_0
0x18003234a  mov     ebx, 104h
0x18003234f  xor     r14d, r14d
0x180032352  mov     [rsp+4A8h+var_468], ebx
0x180032356  mov     [rsp+4A8h+var_460], r14
0x18003235b  call    LonghornOrMore
0x180032360  test    eax, eax
0x180032362  jnz     loc_180032424
0x180032368  mov     esi, r14d
0x18003236b  mov     ebx, r14d
0x18003236e  lea     rax, [rsp+4A8h+var_248]
0x180032376  test    ebx, ebx
0x180032378  lea     r8, [rsp+4A8h+var_458]
0x18003237d  mov     edx, 104h; unsigned __int64
0x180032382  cmovnz  r8, rax; unsigned __int16 *
0x180032386  mov     rcx, rbp; unsigned __int16 *
0x180032389  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003238e  mov     edi, eax
0x180032390  test    eax, eax
0x180032392  jns     short loc_1800323C0
0x180032394  mov     rcx, cs:WPP_GLOBAL_Control
0x18003239b  cmp     rcx, r12
0x18003239e  jz      short loc_1800323C0
0x1800323a0  test    byte ptr [rcx+1Ch], 2
0x1800323a4  jz      short loc_1800323C0
0x1800323a6  cmp     byte ptr [rcx+19h], 2
0x1800323aa  jb      short loc_1800323C0
0x1800323ac  mov     rcx, [rcx+10h]
0x1800323b0  mov     edx, 29h ; ')'
0x1800323b5  mov     r9d, eax
0x1800323b8  mov     r8, r13
0x1800323bb  call    WPP_SF_d
0x1800323c0  mov     ebx, r14d
0x1800323c3  test    rsi, rsi
0x1800323c6  jz      loc_18003264D
0x1800323cc  mov     rcx, rsi; hLibModule
0x1800323cf  call    cs:__imp_FreeLibrary
0x1800323d6  nop     dword ptr [rax+rax+00h]
0x1800323db  test    eax, eax
0x1800323dd  jnz     loc_18003264D
0x1800323e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800323ea  cmp     rax, r12
0x1800323ed  jz      loc_18003264D
0x1800323f3  test    byte ptr [rax+1Ch], 2
0x1800323f7  jz      loc_18003264D
0x1800323fd  cmp     byte ptr [rax+19h], 3
0x180032401  jb      loc_18003264D
0x180032407  call    cs:__imp_GetLastError
0x18003240e  nop     dword ptr [rax+rax+00h]
0x180032413  mov     rcx, cs:WPP_GLOBAL_Control
0x18003241a  mov     edx, 2Ah ; '*'
0x18003241f  jmp     loc_180032511
0x180032424  test    rdi, rdi
0x180032427  jz      loc_18003261C
0x18003242d  mov     rdx, rbx
0x180032430  lea     r8, [rsp+4A8h+var_458]
0x180032435  mov     ebx, 1
0x18003243a  mov     eax, 7FFFFFFEh
0x18003243f  test    rax, rax
0x180032442  jz      short loc_180032460
0x180032444  movzx   ecx, word ptr [rdi]
0x180032447  test    cx, cx
0x18003244a  jz      short loc_180032460
0x18003244c  mov     [r8], cx
0x180032450  add     rdi, 2
0x180032454  add     r8, 2
0x180032458  sub     rax, rbx
0x18003245b  sub     rdx, rbx
0x18003245e  jnz     short loc_18003243F
0x180032460  mov     rax, rdx
0x180032463  lea     rcx, [r8-2]
0x180032467  neg     rax
0x18003246a  sbb     edi, edi
0x18003246c  not     edi
0x18003246e  and     edi, 8007007Ah
0x180032474  test    rdx, rdx
0x180032477  cmovnz  rcx, r8
0x18003247b  mov     [rcx], r14w
0x18003247f  jnz     short loc_1800324C1
0x180032481  mov     ebx, r14d
0x180032484  mov     rcx, cs:WPP_GLOBAL_Control
0x18003248b  cmp     rcx, r12
0x18003248e  jz      loc_18003264D
0x180032494  test    byte ptr [rcx+1Ch], 2
0x180032498  jz      loc_18003264D
0x18003249e  cmp     byte ptr [rcx+19h], 2
0x1800324a2  jb      loc_18003264D
0x1800324a8  mov     rcx, [rcx+10h]
0x1800324ac  mov     edx, 25h ; '%'
0x1800324b1  mov     r9d, edi
0x1800324b4  mov     r8, r13
0x1800324b7  call    WPP_SF_d
0x1800324bc  jmp     loc_18003264D
0x1800324c1  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x1800324c8  call    cs:__imp_LoadLibraryW
0x1800324cf  nop     dword ptr [rax+rax+00h]
0x1800324d4  mov     rsi, rax
0x1800324d7  test    rax, rax
0x1800324da  jnz     short loc_180032525
0x1800324dc  call    cs:__imp_GetLastError
0x1800324e3  nop     dword ptr [rax+rax+00h]
0x1800324e8  mov     ebx, eax
0x1800324ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324f1  cmp     rcx, r12
0x1800324f4  jz      loc_18003264D
0x1800324fa  test    byte ptr [rcx+1Ch], 2
0x1800324fe  jz      loc_18003264D
0x180032504  cmp     byte ptr [rcx+19h], 3
0x180032508  jb      loc_18003264D
0x18003250e  lea     edx, [rsi+26h]
0x180032511  mov     rcx, [rcx+10h]
0x180032515  mov     r8, r13
0x180032518  mov     r9d, eax
0x18003251b  call    WPP_SF_d
0x180032520  jmp     loc_18003264D
0x180032525  lea     rdx, aGetfilemuipath; "GetFileMUIPath"
0x18003252c  mov     rcx, rax; hModule
0x18003252f  call    cs:__imp_GetProcAddress
0x180032536  nop     dword ptr [rax+rax+00h]
0x18003253b  test    rax, rax
0x18003253e  jnz     short loc_18003258B
0x180032540  call    cs:__imp_GetLastError
0x180032547  nop     dword ptr [rax+rax+00h]
0x18003254c  mov     ebx, eax
0x18003254e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032555  cmp     rcx, r12
0x180032558  jz      loc_1800323CC
0x18003255e  test    byte ptr [rcx+1Ch], 2
0x180032562  jz      loc_1800323CC
0x180032568  cmp     byte ptr [rcx+19h], 3
0x18003256c  jb      loc_1800323CC
0x180032572  mov     rcx, [rcx+10h]
0x180032576  mov     edx, 27h ; '''
0x18003257b  mov     r9d, eax
0x18003257e  mov     r8, r13
0x180032581  call    WPP_SF_d
0x180032586  jmp     loc_1800323CC
0x18003258b  lea     rcx, [rsp+4A8h+var_460]
0x180032590  xor     r9d, r9d
0x180032593  mov     [rsp+4A8h+var_478], rcx
0x180032598  lea     rdx, [rsp+4A8h+var_458]
0x18003259d  lea     rcx, [rsp+4A8h+var_468]
0x1800325a2  xor     r8d, r8d
0x1800325a5  mov     [rsp+4A8h+var_480], rcx
0x1800325aa  lea     rcx, [rsp+4A8h+var_248]
0x1800325b2  mov     [rsp+4A8h+var_488], rcx
0x1800325b7  lea     ecx, [r9+10h]
0x1800325bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325c0  test    eax, eax
0x1800325c2  jnz     loc_18003236E
0x1800325c8  call    cs:__imp_GetLastError
0x1800325cf  nop     dword ptr [rax+rax+00h]
0x1800325d4  mov     ebx, eax
0x1800325d6  cmp     eax, 12h
0x1800325d9  jz      loc_18003236B
0x1800325df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325e6  cmp     rcx, r12
0x1800325e9  jz      loc_1800323CC
0x1800325ef  test    byte ptr [rcx+1Ch], 2
0x1800325f3  jz      loc_1800323CC
0x1800325f9  cmp     byte ptr [rcx+19h], 2
0x1800325fd  jb      loc_1800323CC
0x180032603  mov     rcx, [rcx+10h]
0x180032607  mov     edx, 28h ; '('
0x18003260c  mov     r9d, edi
0x18003260f  mov     r8, r13
0x180032612  call    WPP_SF_d
0x180032617  jmp     loc_1800323CC
0x18003261c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032623  mov     edi, r14d
0x180032626  cmp     rcx, r12
0x180032629  jz      short loc_180032648
0x18003262b  test    byte ptr [rcx+1Ch], 2
0x18003262f  jz      short loc_180032648
0x180032631  cmp     byte ptr [rcx+19h], 2
0x180032635  jb      short loc_180032648
0x180032637  mov     rcx, [rcx+10h]
0x18003263b  mov     edx, 24h ; '$'
0x180032640  mov     r8, r13
0x180032643  call    WPP_SF_
0x180032648  mov     ebx, 57h ; 'W'
0x18003264d  test    edi, edi
0x18003264f  movzx   eax, di
0x180032652  cmovns  eax, ebx
0x180032655  mov     rcx, [rsp+4A8h+var_38]
0x18003265d  xor     rcx, rsp; StackCookie
0x180032660  call    __security_check_cookie
0x180032665  lea     r11, [rsp+4A8h+var_28]
0x18003266d  mov     rbx, [r11+30h]
0x180032671  mov     rbp, [r11+40h]
0x180032675  mov     rsp, r11
0x180032678  pop     r14
0x18003267a  pop     r13
0x18003267c  pop     r12
0x18003267e  pop     rdi
0x18003267f  pop     rsi
0x180032680  retn
```
