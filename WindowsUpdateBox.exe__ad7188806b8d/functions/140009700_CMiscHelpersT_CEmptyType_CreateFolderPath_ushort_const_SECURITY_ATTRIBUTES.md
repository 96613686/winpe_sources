# CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x140009700`
- end: `0x140009aa0`
- name: `?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `928`
- prototype: `__int64 __fastcall(_WORD *)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d200`
- `0x1400136d4`
- `0x140013894`
- `0x140016a58`
- `0x14001b310`
- `0x14001c624`

## callees

- `0x140001b08`
- `0x1400076c8`
- `0x140009700`
- `0x1400135b8`
- `0x14001f668`
- `0x140080d70`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x1400099b5`
- `KERNEL32!CreateDirectoryW` at `0x1400099b5`
- `KERNEL32!GetLastError` at `0x140009a12`
- `KERNEL32!GetLastError` at `0x140009a12`
- `KERNEL32!GetFileAttributesW` at `0x140009997`
- `KERNEL32!GetFileAttributesW` at `0x1400099cc`
- `KERNEL32!GetFileAttributesW` at `0x140009997`
- `KERNEL32!GetFileAttributesW` at `0x1400099cc`
- `msvcrt!wcschr` at `0x14000984f`
- `msvcrt!wcschr` at `0x14000984f`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::CreateFolderPath(_WORD *a1)
{
  _WORD *v1; // rax
  __int64 v2; // rdx
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdi
  __int64 v6; // r8
  signed __int64 v7; // rcx
  wchar_t *p_Str; // rdx
  wchar_t v9; // ax
  wchar_t *v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  wchar_t *v13; // rdi
  int v14; // r15d
  wchar_t *v15; // rax
  wchar_t *v16; // r14
  unsigned __int16 *v17; // rdx
  __int64 v18; // r8
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int16 *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r8
  unsigned __int16 v25; // r9
  unsigned __int16 *v26; // rax
  unsigned __int64 v27; // rcx
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  wchar_t Str; // [rsp+28h] [rbp-E0h] BYREF
  char v32; // [rsp+2Ah] [rbp-DEh] BYREF
  unsigned __int16 v33[264]; // [rsp+238h] [rbp+130h] BYREF
  WCHAR FileName[264]; // [rsp+448h] [rbp+340h] BYREF

  if ( !a1 )
  {
    v4 = -2147024809;
    v3 = -2147024809;
LABEL_60:
    v11 = (unsigned int)v4;
    goto LABEL_61;
  }
  v1 = a1;
  v2 = 260;
  do
  {
    if ( !*v1 )
      break;
    ++v1;
    --v2;
  }
  while ( v2 );
  v3 = v2 == 0 ? 0x80070057 : 0;
  v4 = v3;
  v5 = (260 - v2) & -(__int64)(v2 != 0);
  if ( !v2 )
    goto LABEL_60;
  v6 = 261;
  v7 = (char *)a1 - (char *)&Str;
  p_Str = &Str;
  do
  {
    if ( v6 == -2147483385 )
      break;
    v9 = *(wchar_t *)((char *)p_Str + v7);
    if ( !v9 )
      break;
    *p_Str++ = v9;
    --v6;
  }
  while ( v6 );
  v10 = p_Str - 1;
  v3 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v10 = p_Str;
  *v10 = 0;
  if ( v6 )
  {
    if ( v5 )
    {
      --v5;
      v3 = 0;
    }
    else
    {
      v3 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
    if ( (v3 & 0x80000000) == 0 )
    {
      v12 = 2 * v5;
      if ( *(wchar_t *)((char *)&Str + v12) == 92 )
      {
        if ( v12 >= 0x20A )
LABEL_63:
          _report_rangecheckfailure();
        *(wchar_t *)((char *)&Str + v12) = 0;
      }
      v13 = (wchar_t *)&v32;
      FileName[0] = 0;
      if ( Str != 92 )
        v13 = &Str;
      v14 = 0;
      while ( 1 )
      {
        v15 = wcschr(v13, 0x5Cu);
        v16 = v15;
        if ( v15 )
        {
          v21 = v15 - v13;
          if ( v21 > 0x7FFFFFFE )
          {
            v3 = -2147024809;
            goto LABEL_13;
          }
          v22 = v33;
          v23 = v15 - v13;
          v24 = 261;
          do
          {
            if ( !v23 )
              break;
            v25 = *(unsigned __int16 *)((char *)v22 + (char *)v13 - (char *)v33);
            if ( !v25 )
              break;
            *v22 = v25;
            --v23;
            ++v22;
            --v24;
          }
          while ( v24 );
          v26 = v22 - 1;
          if ( v24 )
            v26 = v22;
          *v26 = 0;
          v3 = v24 == 0 ? 0x8007007A : 0;
          if ( !v24 )
            goto LABEL_13;
          if ( v16 < v13 )
          {
            v3 = -2147024362;
            goto LABEL_13;
          }
          v27 = v21;
          if ( v27 >= 261 )
            goto LABEL_63;
          v33[v27] = 0;
        }
        else
        {
          v17 = v33;
          v18 = 261;
          do
          {
            if ( v18 == -2147483385 )
              break;
            v19 = *(unsigned __int16 *)((char *)v17 + (char *)v13 - (char *)v33);
            if ( !v19 )
              break;
            *v17++ = v19;
            --v18;
          }
          while ( v18 );
          v20 = v17 - 1;
          v3 = v18 == 0 ? 0x8007007A : 0;
          if ( v18 )
            v20 = v17;
          *v20 = 0;
          if ( !v18 )
            goto LABEL_13;
          v14 = 1;
        }
        v4 = StringCchCatW(FileName, 0x105u, v33);
        v3 = v4;
        if ( v4 < 0 )
          goto LABEL_60;
        FileAttributesW = GetFileAttributesW(FileName);
        if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0)
          && (!CreateDirectoryW(FileName, 0) || GetFileAttributesW(FileName) == -1) )
        {
          break;
        }
        if ( v16 )
        {
          v13 = v16 + 1;
          v4 = StringCchCatW(FileName, 0x105u, L"\\");
          v3 = v4;
          if ( v4 < 0 )
            goto LABEL_60;
        }
        if ( v14 )
          goto LABEL_62;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
    }
  }
LABEL_13:
  v11 = v3;
LABEL_61:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
LABEL_62:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x140009700  mov     rax, rsp
0x140009703  mov     [rax+8], rbx
0x140009707  mov     [rax+10h], rdi
0x14000970b  mov     [rax+18h], r12
0x14000970f  push    rbp
0x140009710  push    r14
0x140009712  push    r15
0x140009714  lea     rbp, [rax-578h]
0x14000971b  sub     rsp, 660h
0x140009722  mov     rax, cs:__security_cookie
0x140009729  xor     rax, rsp
0x14000972c  mov     [rbp+570h+var_20], rax
0x140009733  xor     r12d, r12d
0x140009736  test    rcx, rcx
0x140009739  jz      loc_140009A56
0x14000973f  mov     r8d, 104h
0x140009745  mov     rax, rcx
0x140009748  mov     edx, r8d
0x14000974b  cmp     [rax], r12w
0x14000974f  jz      short loc_14000975B
0x140009751  add     rax, 2
0x140009755  sub     rdx, 1
0x140009759  jnz     short loc_14000974B
0x14000975b  mov     rax, rdx
0x14000975e  neg     rax
0x140009761  mov     rax, rdx
0x140009764  sbb     ebx, ebx
0x140009766  sub     r8, rdx
0x140009769  not     ebx
0x14000976b  and     ebx, 80070057h
0x140009771  neg     rax
0x140009774  mov     eax, ebx
0x140009776  sbb     rdi, rdi
0x140009779  and     rdi, r8
0x14000977c  test    rdx, rdx
0x14000977f  jz      loc_140009A5D
0x140009785  lea     rax, [rsp+670h+Str]
0x14000978a  mov     r8d, 105h
0x140009790  sub     rcx, rax
0x140009793  lea     rdx, [rsp+670h+Str]
0x140009798  lea     rax, [r8+7FFFFEF9h]
0x14000979f  test    rax, rax
0x1400097a2  jz      short loc_1400097BA
0x1400097a4  movzx   eax, word ptr [rcx+rdx]
0x1400097a8  test    ax, ax
0x1400097ab  jz      short loc_1400097BA
0x1400097ad  mov     [rdx], ax
0x1400097b0  add     rdx, 2
0x1400097b4  sub     r8, 1
0x1400097b8  jnz     short loc_140009798
0x1400097ba  mov     rax, r8
0x1400097bd  neg     rax
0x1400097c0  lea     rax, [rdx-2]
0x1400097c4  sbb     ebx, ebx
0x1400097c6  not     ebx
0x1400097c8  and     ebx, 8007007Ah
0x1400097ce  test    r8, r8
0x1400097d1  cmovnz  rax, rdx
0x1400097d5  mov     [rax], r12w
0x1400097d9  jnz     short loc_1400097E2
0x1400097db  mov     ecx, ebx
0x1400097dd  jmp     loc_140009A5F
0x1400097e2  lea     rax, [rdi-1]
0x1400097e6  cmp     rax, rdi
0x1400097e9  ja      short loc_1400097F3
0x1400097eb  mov     rdi, rax
0x1400097ee  mov     ebx, r12d
0x1400097f1  jmp     short loc_1400097FF
0x1400097f3  mov     ebx, 80070216h
0x1400097f8  mov     ecx, ebx
0x1400097fa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400097ff  mov     ecx, ebx
0x140009801  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140009806  test    ebx, ebx
0x140009808  js      short loc_1400097DB
0x14000980a  add     rdi, rdi
0x14000980d  mov     ecx, 5Ch ; '\'
0x140009812  cmp     [rsp+rdi+670h+Str], cx
0x140009817  jnz     short loc_14000982C
0x140009819  cmp     rdi, 20Ah
0x140009820  jnb     loc_140009A9A
0x140009826  mov     [rsp+rdi+670h+Str], r12w
0x14000982c  cmp     [rsp+670h+Str], cx
0x140009831  lea     rax, [rsp+670h+Str]
0x140009836  lea     rdi, [rsp+670h+var_64E]
0x14000983b  mov     [rbp+570h+FileName], r12w
0x140009843  cmovnz  rdi, rax
0x140009847  mov     r15d, r12d
0x14000984a  mov     edx, ecx; Ch
0x14000984c  mov     rcx, rdi; Str
0x14000984f  call    cs:__imp_wcschr
0x140009856  nop     dword ptr [rax+rax+00h]
0x14000985b  mov     r14, rax
0x14000985e  test    rax, rax
0x140009861  jnz     short loc_1400098D0
0x140009863  lea     rax, [rbp+570h+var_440]
0x14000986a  mov     r9, rdi
0x14000986d  sub     r9, rax
0x140009870  lea     rdx, [rbp+570h+var_440]
0x140009877  mov     r8d, 105h
0x14000987d  lea     rcx, [r8+7FFFFEF9h]
0x140009884  test    rcx, rcx
0x140009887  jz      short loc_1400098A0
0x140009889  movzx   eax, word ptr [r9+rdx]
0x14000988e  test    ax, ax
0x140009891  jz      short loc_1400098A0
0x140009893  mov     [rdx], ax
0x140009896  add     rdx, 2
0x14000989a  sub     r8, 1
0x14000989e  jnz     short loc_14000987D
0x1400098a0  mov     rax, r8
0x1400098a3  neg     rax
0x1400098a6  lea     rax, [rdx-2]
0x1400098aa  sbb     ebx, ebx
0x1400098ac  not     ebx
0x1400098ae  and     ebx, 8007007Ah
0x1400098b4  test    r8, r8
0x1400098b7  cmovnz  rax, rdx
0x1400098bb  mov     [rax], r12w
0x1400098bf  jz      loc_1400097DB
0x1400098c5  mov     r15d, 1
0x1400098cb  jmp     loc_14000996E
0x1400098d0  mov     rcx, r14
0x1400098d3  sub     rcx, rdi
0x1400098d6  sar     rcx, 1
0x1400098d9  cmp     rcx, 7FFFFFFEh
0x1400098e0  ja      loc_140009A4C
0x1400098e6  lea     r9, [rbp+570h+var_440]
0x1400098ed  mov     r10, rdi
0x1400098f0  sub     r10, r9
0x1400098f3  lea     rdx, [rbp+570h+var_440]
0x1400098fa  mov     rax, rcx
0x1400098fd  mov     r8d, 105h
0x140009903  test    rax, rax
0x140009906  jz      short loc_140009924
0x140009908  movzx   r9d, word ptr [r10+rdx]
0x14000990d  test    r9w, r9w
0x140009911  jz      short loc_140009924
0x140009913  mov     [rdx], r9w
0x140009917  dec     rax
0x14000991a  add     rdx, 2
0x14000991e  sub     r8, 1
0x140009922  jnz     short loc_140009903
0x140009924  test    r8, r8
0x140009927  lea     rax, [rdx-2]
0x14000992b  cmovnz  rax, rdx
0x14000992f  mov     [rax], r12w
0x140009933  mov     rax, r8
0x140009936  neg     rax
0x140009939  sbb     ebx, ebx
0x14000993b  not     ebx
0x14000993d  and     ebx, 8007007Ah
0x140009943  test    r8, r8
0x140009946  jz      loc_1400097DB
0x14000994c  cmp     r14, rdi
0x14000994f  jb      loc_140009A42
0x140009955  add     rcx, rcx
0x140009958  cmp     rcx, 20Ah
0x14000995f  jnb     loc_140009A9A
0x140009965  mov     [rbp+rcx+570h+var_440], r12w
0x14000996e  lea     r8, [rbp+570h+var_440]; unsigned __int16 *
0x140009975  mov     edx, 105h; unsigned __int64
0x14000997a  lea     rcx, [rbp+570h+FileName]; unsigned __int16 *
0x140009981  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009986  mov     ebx, eax
0x140009988  test    eax, eax
0x14000998a  js      loc_140009A5D
0x140009990  lea     rcx, [rbp+570h+FileName]; lpFileName
0x140009997  call    cs:__imp_GetFileAttributesW
0x14000999e  nop     dword ptr [rax+rax+00h]
0x1400099a3  cmp     eax, 0FFFFFFFFh
0x1400099a6  jz      short loc_1400099AC
0x1400099a8  test    al, 10h
0x1400099aa  jnz     short loc_1400099DD
0x1400099ac  xor     edx, edx; lpSecurityAttributes
0x1400099ae  lea     rcx, [rbp+570h+FileName]; lpPathName
0x1400099b5  call    cs:__imp_CreateDirectoryW
0x1400099bc  nop     dword ptr [rax+rax+00h]
0x1400099c1  test    eax, eax
0x1400099c3  jz      short loc_140009A12
0x1400099c5  lea     rcx, [rbp+570h+FileName]; lpFileName
0x1400099cc  call    cs:__imp_GetFileAttributesW
0x1400099d3  nop     dword ptr [rax+rax+00h]
0x1400099d8  cmp     eax, 0FFFFFFFFh
0x1400099db  jz      short loc_140009A12
0x1400099dd  test    r14, r14
0x1400099e0  jz      short loc_140009A04
0x1400099e2  lea     r8, pszSrc; "\\"
0x1400099e9  mov     edx, 105h; unsigned __int64
0x1400099ee  lea     rcx, [rbp+570h+FileName]; unsigned __int16 *
0x1400099f5  lea     rdi, [r14+2]
0x1400099f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400099fe  mov     ebx, eax
0x140009a00  test    eax, eax
0x140009a02  js      short loc_140009A5D
0x140009a04  test    r15d, r15d
0x140009a07  jnz     short loc_140009A64
0x140009a09  lea     ecx, [r15+5Ch]
0x140009a0d  jmp     loc_14000984A
0x140009a12  call    cs:__imp_GetLastError
0x140009a19  nop     dword ptr [rax+rax+00h]
0x140009a1e  mov     ebx, eax
0x140009a20  test    eax, eax
0x140009a22  jnz     short loc_140009A2E
0x140009a24  mov     ebx, 80004005h
0x140009a29  jmp     loc_1400097DB
0x140009a2e  jle     loc_1400097DB
0x140009a34  movzx   ebx, ax
0x140009a37  or      ebx, 80070000h
0x140009a3d  jmp     loc_1400097DB
0x140009a42  mov     ebx, 80070216h
0x140009a47  jmp     loc_1400097DB
0x140009a4c  mov     ebx, 80070057h
0x140009a51  jmp     loc_1400097DB
0x140009a56  mov     eax, 80070057h
0x140009a5b  mov     ebx, eax
0x140009a5d  mov     ecx, eax
0x140009a5f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140009a64  mov     ecx, ebx
0x140009a66  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140009a6b  mov     eax, ebx
0x140009a6d  mov     rcx, [rbp+570h+var_20]
0x140009a74  xor     rcx, rsp; StackCookie
0x140009a77  call    __security_check_cookie
0x140009a7c  lea     r11, [rsp+670h+var_10]
0x140009a84  mov     rbx, [r11+20h]
0x140009a88  mov     rdi, [r11+28h]
0x140009a8c  mov     r12, [r11+30h]
0x140009a90  mov     rsp, r11
0x140009a93  pop     r15
0x140009a95  pop     r14
0x140009a97  pop     rbp
0x140009a98  retn
0x140009a9a  call    __report_rangecheckfailure
```
