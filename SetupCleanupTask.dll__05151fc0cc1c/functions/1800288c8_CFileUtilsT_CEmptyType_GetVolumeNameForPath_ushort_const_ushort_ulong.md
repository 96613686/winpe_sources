# CFileUtilsT<CEmptyType>::GetVolumeNameForPath(ushort const *,ushort *,ulong)

- ea: `0x1800288c8`
- end: `0x180028a00`
- name: `?GetVolumeNameForPath@?$CFileUtilsT@VCEmptyType@@@@SAJPEBGPEAGK@Z`
- size: `312`
- prototype: `__int64 __fastcall(const WCHAR *, WCHAR *)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180026824`
- `0x180028a08`
- `0x180028d7c`

## callees

- `0x180027008`
- `0x1800288c8`
- `0x1800293a4`
- `0x1800322ea`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028924`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18002891a`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18002891a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180028977`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180028977`

## pseudocode

```c
__int64 __fastcall CFileUtilsT<CEmptyType>::GetVolumeNameForPath(const WCHAR *a1, WCHAR *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 v5; // rbx
  __int64 v6; // rax
  unsigned int v7; // esi
  WCHAR szVolumeMountPoint[2]; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+24h] [rbp-34h]
  wchar_t String2[8]; // [rsp+28h] [rbp-30h] BYREF

  *(_DWORD *)szVolumeMountPoint = 3801088;
  v10 = 92;
  wcscpy(String2, L"\\\\?\\");
  if ( !GetVolumePathNameW(a1, a2, 0x104u) )
    goto LABEL_2;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 == 3 )
  {
    szVolumeMountPoint[0] = *a2;
    if ( !GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, a2, 0x104u) )
    {
LABEL_2:
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v4 = -2147467259;
      }
      goto LABEL_18;
    }
  }
  do
    ++v5;
  while ( a2[v5] );
  v7 = v5;
  if ( v5 == (unsigned int)v5 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v4 = 0;
  }
  else
  {
    v4 = -2147024362;
    v7 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
  {
LABEL_18:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_19;
  }
  if ( v7 <= 5 || wcsncmp_0(a2, String2, 4u) )
  {
    v4 = -2147418113;
    goto LABEL_18;
  }
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x1800288c8  mov     [rsp+arg_10], rbx
0x1800288cd  push    rbp
0x1800288ce  push    rsi
0x1800288cf  push    rdi
0x1800288d0  sub     rsp, 40h
0x1800288d4  mov     rax, cs:__security_cookie
0x1800288db  xor     rax, rsp
0x1800288de  mov     [rsp+58h+var_20], rax
0x1800288e3  movsd   xmm0, qword ptr cs:asc_18003D740; "\\\\?\\"
0x1800288eb  mov     esi, 104h
0x1800288f0  movzx   eax, word ptr cs:asc_18003D740+8; ""
0x1800288f7  mov     r8d, esi; cchBufferLength
0x1800288fa  mov     rdi, rdx
0x1800288fd  mov     dword ptr [rsp+58h+szVolumeMountPoint], 3A0000h
0x180028905  xor     ebp, ebp
0x180028907  mov     [rsp+58h+var_34], 5Ch ; '\'
0x18002890f  movsd   qword ptr [rsp+58h+String2], xmm0
0x180028915  mov     [rsp+58h+var_28], ax
0x18002891a  call    cs:__imp_GetVolumePathNameW
0x180028920  test    eax, eax
0x180028922  jnz     short loc_18002894E
0x180028924  call    cs:__imp_GetLastError
0x18002892a  mov     ebx, eax
0x18002892c  test    eax, eax
0x18002892e  jnz     short loc_18002893A
0x180028930  mov     ebx, 80004005h
0x180028935  jmp     loc_1800289D6
0x18002893a  jle     loc_1800289D6
0x180028940  movzx   ebx, ax
0x180028943  or      ebx, 80070000h
0x180028949  jmp     loc_1800289D6
0x18002894e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028952  mov     rax, rbx
0x180028955  inc     rax
0x180028958  cmp     [rdi+rax*2], bp
0x18002895c  jnz     short loc_180028955
0x18002895e  cmp     rax, 3
0x180028962  jnz     short loc_180028981
0x180028964  movzx   eax, word ptr [rdi]
0x180028967  lea     rcx, [rsp+58h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18002896c  mov     r8d, esi; cchBufferLength
0x18002896f  mov     [rsp+58h+szVolumeMountPoint], ax
0x180028974  mov     rdx, rdi; lpszVolumeName
0x180028977  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002897d  test    eax, eax
0x18002897f  jz      short loc_180028924
0x180028981  inc     rbx
0x180028984  cmp     [rdi+rbx*2], bp
0x180028988  jnz     short loc_180028981
0x18002898a  mov     esi, ebx
0x18002898c  cmp     rbx, rsi
0x18002898f  jz      short loc_1800289A1
0x180028991  mov     ebx, 80070216h
0x180028996  mov     esi, ebp
0x180028998  mov     ecx, ebx
0x18002899a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002899f  jmp     short loc_1800289AA
0x1800289a1  xor     ecx, ecx
0x1800289a3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800289a8  mov     ebx, ebp
0x1800289aa  mov     ecx, ebx
0x1800289ac  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800289b1  test    ebx, ebx
0x1800289b3  js      short loc_1800289D6
0x1800289b5  cmp     esi, 5
0x1800289b8  jbe     short loc_1800289D1
0x1800289ba  mov     r8d, 4; MaxCount
0x1800289c0  lea     rdx, [rsp+58h+String2]; String2
0x1800289c5  mov     rcx, rdi; String1
0x1800289c8  call    wcsncmp_0
0x1800289cd  test    eax, eax
0x1800289cf  jz      short loc_1800289DD
0x1800289d1  mov     ebx, 8000FFFFh
0x1800289d6  mov     ecx, ebx
0x1800289d8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800289dd  mov     ecx, ebx
0x1800289df  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800289e4  mov     eax, ebx
0x1800289e6  mov     rcx, [rsp+58h+var_20]
0x1800289eb  xor     rcx, rsp; StackCookie
0x1800289ee  call    __security_check_cookie
0x1800289f3  mov     rbx, [rsp+58h+arg_10]
0x1800289f8  add     rsp, 40h
0x1800289fc  pop     rdi
0x1800289fd  pop     rsi
0x1800289fe  pop     rbp
0x1800289ff  retn
```
