# CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18002724c`
- end: `0x1800275b1`
- name: `?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `869`
- prototype: `__int64 __fastcall(wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002bae0`

## callees

- `0x180002b38`
- `0x180022e70`
- `0x180027008`
- `0x18002724c`
- `0x1800293a4`
- `0x180032310`

## import_xrefs

- `msvcrt!wcschr` at `0x18002739a`
- `msvcrt!wcschr` at `0x18002739a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027542`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800274cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800274fe`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800274cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800274fe`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800274ed`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800274ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMiscHelpersT<CEmptyType>::CreateFolderPath(wchar_t *a1, __int64 a2)
{
  wchar_t *v3; // rax
  __int64 v4; // r8
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 v7; // rax
  wchar_t *p_Str; // r8
  __int64 v9; // rdx
  wchar_t *v10; // rcx
  unsigned __int64 v11; // rdi
  wchar_t *v12; // rdi
  int v13; // r14d
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  __int64 v16; // rax
  unsigned __int16 *v17; // r8
  wchar_t *v18; // rcx
  __int64 v19; // rdx
  unsigned __int16 *v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  wchar_t *v24; // r9
  __int64 v25; // r8
  unsigned __int16 *v26; // rcx
  unsigned __int64 v27; // rdx
  int v28; // eax
  DWORD FileAttributesW; // eax
  int v30; // ecx
  signed int LastError; // eax
  wchar_t Str; // [rsp+20h] [rbp-E0h] BYREF
  char v34; // [rsp+22h] [rbp-DEh] BYREF
  WCHAR FileName[264]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v36[264]; // [rsp+440h] [rbp+340h] BYREF

  if ( a1 )
  {
    v3 = a1;
    v4 = 260;
    do
    {
      if ( !*v3 )
        break;
      ++v3;
      --v4;
    }
    while ( v4 );
    v5 = v4 == 0 ? 0x80070057 : 0;
    v6 = (260 - v4) & -(__int64)(v4 != 0);
    if ( v4 )
    {
      v7 = 2147483646;
      p_Str = &Str;
      v9 = 261;
      do
      {
        if ( !v7 )
          break;
        if ( !*a1 )
          break;
        *p_Str++ = *a1++;
        --v7;
        --v9;
      }
      while ( v9 );
      v10 = p_Str - 1;
      v5 = v9 == 0 ? 0x8007007A : 0;
      if ( v9 )
        v10 = p_Str;
      *v10 = 0;
      if ( v9 )
      {
        if ( v6 )
        {
          --v6;
          v5 = 0;
        }
        else
        {
          v5 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
        if ( (v5 & 0x80000000) == 0 )
        {
          v11 = 2 * v6;
          if ( *(wchar_t *)((char *)&Str + v11) == 92 )
          {
            if ( v11 >= 0x20A )
LABEL_63:
              _report_rangecheckfailure();
            *(wchar_t *)((char *)&Str + v11) = 0;
          }
          v12 = (wchar_t *)&v34;
          FileName[0] = 0;
          if ( Str != 92 )
            v12 = &Str;
          v13 = 0;
          while ( 1 )
          {
            v14 = wcschr(v12, 0x5Cu);
            v15 = v14;
            if ( v14 )
            {
              v21 = v14 - v12;
              if ( v21 > 0x7FFFFFFE )
                goto LABEL_59;
              v22 = v14 - v12;
              v23 = v36;
              v24 = v12;
              v25 = 261;
              do
              {
                if ( !v22 )
                  break;
                if ( !*v24 )
                  break;
                *v23++ = *v24++;
                --v22;
                --v25;
              }
              while ( v25 );
              v26 = v23 - 1;
              if ( v25 )
                v26 = v23;
              *v26 = 0;
              v5 = v25 == 0 ? 0x8007007A : 0;
              if ( !v25 )
                goto LABEL_60;
              if ( v15 < v12 )
              {
                v30 = -2147024362;
                v5 = -2147024362;
                goto LABEL_61;
              }
              v27 = v21;
              if ( v27 >= 261 )
                goto LABEL_63;
              v36[v27] = 0;
            }
            else
            {
              v16 = 2147483646;
              v17 = v36;
              v18 = v12;
              v19 = 261;
              do
              {
                if ( !v16 )
                  break;
                if ( !*v18 )
                  break;
                *v17++ = *v18++;
                --v16;
                --v19;
              }
              while ( v19 );
              v20 = v17 - 1;
              v5 = v19 == 0 ? 0x8007007A : 0;
              if ( v19 )
                v20 = v17;
              *v20 = 0;
              if ( !v19 )
                goto LABEL_60;
              v13 = 1;
            }
            v28 = StringCchCatW(FileName, 0x105u, v36);
            v5 = v28;
            if ( v28 < 0 )
              goto LABEL_53;
            FileAttributesW = GetFileAttributesW(FileName);
            if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0)
              && (!CreateDirectoryW(FileName, (LPSECURITY_ATTRIBUTES)(a2 & -(__int64)(v13 != 0)))
               || GetFileAttributesW(FileName) == -1) )
            {
              break;
            }
            if ( v15 )
            {
              v28 = StringCchCatW(FileName, 0x105u, L"\\");
              v5 = v28;
              if ( v28 < 0 )
              {
LABEL_53:
                v30 = v28;
                goto LABEL_61;
              }
              v12 = v15 + 1;
            }
            if ( v13 )
              goto LABEL_62;
          }
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v5 = -2147467259;
          }
        }
      }
    }
  }
  else
  {
LABEL_59:
    v5 = -2147024809;
  }
LABEL_60:
  v30 = v5;
LABEL_61:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v30);
LABEL_62:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18002724c  mov     [rsp-8+arg_0], rbx
0x180027251  mov     [rsp-8+arg_10], rsi
0x180027256  push    rbp
0x180027257  push    rdi
0x180027258  push    r12
0x18002725a  push    r14
0x18002725c  push    r15
0x18002725e  lea     rbp, [rsp-560h]
0x180027266  sub     rsp, 660h
0x18002726d  mov     rax, cs:__security_cookie
0x180027274  xor     rax, rsp
0x180027277  mov     [rbp+580h+var_30], rax
0x18002727e  xor     r12d, r12d
0x180027281  mov     r15, rdx
0x180027284  test    rcx, rcx
0x180027287  jz      loc_18002756B
0x18002728d  mov     r9d, 104h
0x180027293  mov     rax, rcx
0x180027296  mov     r8d, r9d
0x180027299  cmp     [rax], r12w
0x18002729d  jz      short loc_1800272A9
0x18002729f  add     rax, 2
0x1800272a3  sub     r8, 1
0x1800272a7  jnz     short loc_180027299
0x1800272a9  mov     rax, r8
0x1800272ac  neg     rax
0x1800272af  mov     rax, r8
0x1800272b2  sbb     ebx, ebx
0x1800272b4  sub     r9, r8
0x1800272b7  not     ebx
0x1800272b9  and     ebx, 80070057h
0x1800272bf  neg     rax
0x1800272c2  sbb     rdi, rdi
0x1800272c5  and     rdi, r9
0x1800272c8  test    r8, r8
0x1800272cb  jz      loc_180027570
0x1800272d1  mov     eax, 7FFFFFFEh
0x1800272d6  lea     r8, [rsp+680h+Str]
0x1800272db  mov     edx, 105h
0x1800272e0  test    rax, rax
0x1800272e3  jz      short loc_180027304
0x1800272e5  movzx   r9d, word ptr [rcx]
0x1800272e9  test    r9w, r9w
0x1800272ed  jz      short loc_180027304
0x1800272ef  mov     [r8], r9w
0x1800272f3  add     rcx, 2
0x1800272f7  add     r8, 2
0x1800272fb  dec     rax
0x1800272fe  sub     rdx, 1
0x180027302  jnz     short loc_1800272E0
0x180027304  mov     rax, rdx
0x180027307  lea     rcx, [r8-2]
0x18002730b  neg     rax
0x18002730e  sbb     ebx, ebx
0x180027310  not     ebx
0x180027312  and     ebx, 8007007Ah
0x180027318  test    rdx, rdx
0x18002731b  cmovnz  rcx, r8
0x18002731f  mov     [rcx], r12w
0x180027323  jz      loc_180027570
0x180027329  lea     rax, [rdi-1]
0x18002732d  mov     ecx, 80070216h
0x180027332  cmp     rax, rdi
0x180027335  ja      short loc_18002733F
0x180027337  mov     rdi, rax
0x18002733a  mov     ebx, r12d
0x18002733d  jmp     short loc_180027346
0x18002733f  mov     ebx, ecx
0x180027341  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027346  mov     ecx, ebx
0x180027348  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002734d  test    ebx, ebx
0x18002734f  js      loc_180027570
0x180027355  add     rdi, rdi
0x180027358  mov     ecx, 5Ch ; '\'
0x18002735d  cmp     [rsp+rdi+680h+Str], cx
0x180027362  jnz     short loc_180027377
0x180027364  cmp     rdi, 20Ah
0x18002736b  jnb     loc_1800275AB
0x180027371  mov     [rsp+rdi+680h+Str], r12w
0x180027377  cmp     [rsp+680h+Str], cx
0x18002737c  lea     rdi, [rsp+680h+var_65E]
0x180027381  lea     rax, [rsp+680h+Str]
0x180027386  mov     [rbp+580h+FileName], r12w
0x18002738e  cmovnz  rdi, rax
0x180027392  mov     r14d, r12d
0x180027395  mov     edx, ecx; Ch
0x180027397  mov     rcx, rdi; Str
0x18002739a  call    cs:__imp_wcschr
0x1800273a0  mov     rsi, rax
0x1800273a3  test    rax, rax
0x1800273a6  jnz     short loc_180027410
0x1800273a8  mov     eax, 7FFFFFFEh
0x1800273ad  lea     r8, [rbp+580h+var_240]
0x1800273b4  mov     rcx, rdi
0x1800273b7  mov     edx, 105h
0x1800273bc  test    rax, rax
0x1800273bf  jz      short loc_1800273E0
0x1800273c1  movzx   r9d, word ptr [rcx]
0x1800273c5  test    r9w, r9w
0x1800273c9  jz      short loc_1800273E0
0x1800273cb  mov     [r8], r9w
0x1800273cf  add     rcx, 2
0x1800273d3  add     r8, 2
0x1800273d7  dec     rax
0x1800273da  sub     rdx, 1
0x1800273de  jnz     short loc_1800273BC
0x1800273e0  mov     rax, rdx
0x1800273e3  lea     rcx, [r8-2]
0x1800273e7  neg     rax
0x1800273ea  sbb     ebx, ebx
0x1800273ec  not     ebx
0x1800273ee  and     ebx, 8007007Ah
0x1800273f4  test    rdx, rdx
0x1800273f7  cmovnz  rcx, r8
0x1800273fb  mov     [rcx], r12w
0x1800273ff  jz      loc_180027570
0x180027405  mov     r14d, 1
0x18002740b  jmp     loc_1800274A7
0x180027410  mov     rdx, rsi
0x180027413  sub     rdx, rdi
0x180027416  sar     rdx, 1
0x180027419  cmp     rdx, 7FFFFFFEh
0x180027420  ja      loc_18002756B
0x180027426  mov     rcx, rdx
0x180027429  lea     rax, [rbp+580h+var_240]
0x180027430  mov     r9, rdi
0x180027433  mov     r8d, 105h
0x180027439  test    rcx, rcx
0x18002743c  jz      short loc_18002745D
0x18002743e  movzx   r10d, word ptr [r9]
0x180027442  test    r10w, r10w
0x180027446  jz      short loc_18002745D
0x180027448  mov     [rax], r10w
0x18002744c  add     r9, 2
0x180027450  add     rax, 2
0x180027454  dec     rcx
0x180027457  sub     r8, 1
0x18002745b  jnz     short loc_180027439
0x18002745d  test    r8, r8
0x180027460  lea     rcx, [rax-2]
0x180027464  cmovnz  rcx, rax
0x180027468  mov     rax, r8
0x18002746b  neg     rax
0x18002746e  sbb     ebx, ebx
0x180027470  not     ebx
0x180027472  mov     [rcx], r12w
0x180027476  and     ebx, 8007007Ah
0x18002747c  test    r8, r8
0x18002747f  jz      loc_180027570
0x180027485  cmp     rsi, rdi
0x180027488  jb      loc_180027562
0x18002748e  add     rdx, rdx
0x180027491  cmp     rdx, 20Ah
0x180027498  jnb     loc_1800275AB
0x18002749e  mov     [rbp+rdx+580h+var_240], r12w
0x1800274a7  lea     r8, [rbp+580h+var_240]; unsigned __int16 *
0x1800274ae  mov     edx, 105h; unsigned __int64
0x1800274b3  lea     rcx, [rbp+580h+FileName]; unsigned __int16 *
0x1800274ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800274bf  mov     ebx, eax
0x1800274c1  test    eax, eax
0x1800274c3  js      short loc_18002753E
0x1800274c5  lea     rcx, [rbp+580h+FileName]; lpFileName
0x1800274cc  call    cs:__imp_GetFileAttributesW
0x1800274d2  cmp     eax, 0FFFFFFFFh
0x1800274d5  jz      short loc_1800274DB
0x1800274d7  test    al, 10h
0x1800274d9  jnz     short loc_180027509
0x1800274db  mov     eax, r14d
0x1800274de  lea     rcx, [rbp+580h+FileName]; lpPathName
0x1800274e5  neg     eax
0x1800274e7  sbb     rdx, rdx
0x1800274ea  and     rdx, r15; lpSecurityAttributes
0x1800274ed  call    cs:__imp_CreateDirectoryW
0x1800274f3  test    eax, eax
0x1800274f5  jz      short loc_180027542
0x1800274f7  lea     rcx, [rbp+580h+FileName]; lpFileName
0x1800274fe  call    cs:__imp_GetFileAttributesW
0x180027504  cmp     eax, 0FFFFFFFFh
0x180027507  jz      short loc_180027542
0x180027509  test    rsi, rsi
0x18002750c  jz      short loc_180027530
0x18002750e  lea     r8, pszSrc; "\\"
0x180027515  mov     edx, 105h; unsigned __int64
0x18002751a  lea     rcx, [rbp+580h+FileName]; unsigned __int16 *
0x180027521  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027526  mov     ebx, eax
0x180027528  test    eax, eax
0x18002752a  js      short loc_18002753E
0x18002752c  lea     rdi, [rsi+2]
0x180027530  test    r14d, r14d
0x180027533  jnz     short loc_180027577
0x180027535  lea     ecx, [r14+5Ch]
0x180027539  jmp     loc_180027395
0x18002753e  mov     ecx, eax
0x180027540  jmp     short loc_180027572
0x180027542  call    cs:__imp_GetLastError
0x180027548  mov     ebx, eax
0x18002754a  test    eax, eax
0x18002754c  jnz     short loc_180027555
0x18002754e  mov     ebx, 80004005h
0x180027553  jmp     short loc_180027570
0x180027555  jle     short loc_180027570
0x180027557  movzx   ebx, ax
0x18002755a  or      ebx, 80070000h
0x180027560  jmp     short loc_180027570
0x180027562  mov     ecx, 80070216h
0x180027567  mov     ebx, ecx
0x180027569  jmp     short loc_180027572
0x18002756b  mov     ebx, 80070057h
0x180027570  mov     ecx, ebx
0x180027572  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027577  mov     ecx, ebx
0x180027579  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002757e  mov     eax, ebx
0x180027580  mov     rcx, [rbp+580h+var_30]
0x180027587  xor     rcx, rsp; StackCookie
0x18002758a  call    __security_check_cookie
0x18002758f  lea     r11, [rsp+680h+var_20]
0x180027597  mov     rbx, [r11+30h]
0x18002759b  mov     rsi, [r11+40h]
0x18002759f  mov     rsp, r11
0x1800275a2  pop     r15
0x1800275a4  pop     r14
0x1800275a6  pop     r12
0x1800275a8  pop     rdi
0x1800275a9  pop     rbp
0x1800275aa  retn
0x1800275ab  call    __report_rangecheckfailure
```
