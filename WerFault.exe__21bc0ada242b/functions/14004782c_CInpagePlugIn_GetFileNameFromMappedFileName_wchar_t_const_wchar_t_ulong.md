# CInpagePlugIn::GetFileNameFromMappedFileName(wchar_t const *,wchar_t *,ulong)

- ea: `0x14004782c`
- end: `0x1400479f9`
- name: `?GetFileNameFromMappedFileName@CInpagePlugIn@@AEAAJPEB_WPEA_WK@Z`
- size: `461`
- prototype: `__int64 __fastcall(CInpagePlugIn *this, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400476bc`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000b540`
- `0x14003b8f8`
- `0x14004782c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004797a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004797a`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x1400478ff`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x1400478ff`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x14004793a`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x14004793a`

## pseudocode

```c
__int64 __fastcall CInpagePlugIn::GetFileNameFromMappedFileName(CInpagePlugIn *this, const wchar_t *a2, wchar_t *a3)
{
  unsigned __int64 v5; // rdi
  __int64 result; // rax
  WCHAR v7; // ax
  WCHAR *p_Buffer; // r14
  unsigned __int64 v9; // rbx
  _QWORD v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v12; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR DeviceName; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+52h] [rbp-AEh]
  WCHAR Buffer; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[526]; // [rsp+62h] [rbp-9Eh] BYREF
  WCHAR TargetPath[264]; // [rsp+270h] [rbp+170h] BYREF

  Buffer = 0;
  memset_0(v16, 0, 0x206u);
  if ( !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  v5 = -1;
  v11[0] = a2;
  do
    ++v5;
  while ( a2[v5] );
  v11[1] = v5;
  v12 = *(_OWORD *)&off_1400602D0;
  if ( (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                          v11,
                          &v12) )
  {
    result = StringCchPrintfW(a3, 0x104u, L"\\%s", a2 + 24);
    if ( (int)result < 0 )
      return result;
    return 0;
  }
  if ( !GetLogicalDriveStringsW(0x103u, &Buffer) )
    return 0;
  v7 = Buffer;
  p_Buffer = &Buffer;
  v14 = 58;
  TargetPath[0] = 0;
  while ( 1 )
  {
    DeviceName = v7;
    if ( QueryDosDeviceW(&DeviceName, TargetPath, 0x103u) )
    {
      v9 = -1;
      do
        ++v9;
      while ( TargetPath[v9] );
      if ( (!v9 || v9 <= v5 && CompareStringOrdinal(a2, v9, TargetPath, v9, 1) == 2) && v9 < v5 )
        break;
    }
    while ( *p_Buffer++ )
      ;
    v7 = *p_Buffer;
    if ( !*p_Buffer )
      return 0;
  }
  return StringCchPrintfW(a3, 0x104u, L"%s%s", &DeviceName, &a2[v9]);
}

```

## disassembly

```asm
0x14004782c  mov     [rsp-8+arg_0], rbx
0x140047831  mov     [rsp-8+arg_18], rsi
0x140047836  push    rbp
0x140047837  push    rdi
0x140047838  push    r12
0x14004783a  push    r14
0x14004783c  push    r15
0x14004783e  lea     rbp, [rsp-390h]
0x140047846  sub     rsp, 490h
0x14004784d  mov     rax, cs:__security_cookie
0x140047854  xor     rax, rsp
0x140047857  mov     [rbp+3B0h+var_30], rax
0x14004785e  mov     r15, r8
0x140047861  lea     rcx, [rsp+4B0h+var_44E]; void *
0x140047866  mov     rsi, rdx
0x140047869  xor     r12d, r12d
0x14004786c  xor     edx, edx; Val
0x14004786e  mov     [rsp+4B0h+Buffer], r12w
0x140047874  mov     r8d, 206h; Size
0x14004787a  call    memset_0
0x14004787f  test    rsi, rsi
0x140047882  jz      loc_1400479C9
0x140047888  test    r15, r15
0x14004788b  jz      loc_1400479C9
0x140047891  mov     [r15], r12w
0x140047895  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140047899  mov     [rsp+4B0h+var_480], rsi
0x14004789e  inc     rdi
0x1400478a1  cmp     [rsi+rdi*2], r12w
0x1400478a6  jnz     short loc_14004789E
0x1400478a8  movups  xmm0, xmmword ptr cs:off_1400602D0; "\\Device\\LanmanRedirector"
0x1400478af  lea     rdx, [rsp+4B0h+var_470]
0x1400478b4  mov     [rsp+4B0h+var_478], rdi
0x1400478b9  lea     rcx, [rsp+4B0h+var_480]
0x1400478be  movdqu  [rsp+4B0h+var_470], xmm0
0x1400478c4  call    ?starts_with@?$basic_string_view@_WU?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@QEBA_NV12@@Z; utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>)
0x1400478c9  test    al, al
0x1400478cb  jz      short loc_1400478F5
0x1400478cd  lea     r9, [rsi+30h]
0x1400478d1  mov     edx, 104h; unsigned __int64
0x1400478d6  lea     r8, aS_5; "\\%s"
0x1400478dd  mov     rcx, r15; wchar_t *
0x1400478e0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400478e5  test    eax, eax
0x1400478e7  js      loc_1400479CE
0x1400478ed  mov     eax, r12d
0x1400478f0  jmp     loc_1400479CE
0x1400478f5  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x1400478fa  mov     ecx, 103h; nBufferLength
0x1400478ff  call    cs:__imp_GetLogicalDriveStringsW
0x140047905  test    eax, eax
0x140047907  jz      short loc_1400478ED
0x140047909  movzx   eax, [rsp+4B0h+Buffer]
0x14004790e  lea     r14, [rsp+4B0h+Buffer]
0x140047913  mov     [rsp+4B0h+var_45E], 3Ah ; ':'
0x14004791b  mov     [rbp+3B0h+TargetPath], r12w
0x140047923  mov     r8d, 103h; ucchMax
0x140047929  mov     [rsp+4B0h+DeviceName], ax
0x14004792e  lea     rdx, [rbp+3B0h+TargetPath]; lpTargetPath
0x140047935  lea     rcx, [rsp+4B0h+DeviceName]; lpDeviceName
0x14004793a  call    cs:__imp_QueryDosDeviceW
0x140047940  test    eax, eax
0x140047942  jz      short loc_14004798A
0x140047944  lea     rax, [rbp+3B0h+TargetPath]
0x14004794b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14004794f  inc     rbx
0x140047952  cmp     [rax+rbx*2], r12w
0x140047957  jnz     short loc_14004794F
0x140047959  test    rbx, rbx
0x14004795c  jz      short loc_140047985
0x14004795e  cmp     rbx, rdi
0x140047961  ja      short loc_14004798A
0x140047963  mov     r9d, ebx; cchCount2
0x140047966  mov     [rsp+4B0h+bIgnoreCase], 1; bIgnoreCase
0x14004796e  lea     r8, [rbp+3B0h+TargetPath]; lpString2
0x140047975  mov     edx, ebx; cchCount1
0x140047977  mov     rcx, rsi; lpString1
0x14004797a  call    cs:__imp_CompareStringOrdinal
0x140047980  cmp     eax, 2
0x140047983  jnz     short loc_14004798A
0x140047985  cmp     rbx, rdi
0x140047988  jb      short loc_1400479A5
0x14004798a  movzx   eax, word ptr [r14]
0x14004798e  add     r14, 2
0x140047992  test    ax, ax
0x140047995  jnz     short loc_14004798A
0x140047997  movzx   eax, word ptr [r14]
0x14004799b  test    ax, ax
0x14004799e  jnz     short loc_140047923
0x1400479a0  jmp     loc_1400478ED
0x1400479a5  lea     rax, [rsi+rbx*2]
0x1400479a9  mov     edx, 104h; unsigned __int64
0x1400479ae  lea     r9, [rsp+4B0h+DeviceName]
0x1400479b3  mov     qword ptr [rsp+4B0h+bIgnoreCase], rax
0x1400479b8  lea     r8, aSS_4; "%s%s"
0x1400479bf  mov     rcx, r15; wchar_t *
0x1400479c2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400479c7  jmp     short loc_1400479CE
0x1400479c9  mov     eax, 80070057h
0x1400479ce  mov     rcx, [rbp+3B0h+var_30]
0x1400479d5  xor     rcx, rsp; StackCookie
0x1400479d8  call    __security_check_cookie
0x1400479dd  lea     r11, [rsp+4B0h+var_20]
0x1400479e5  mov     rbx, [r11+30h]
0x1400479e9  mov     rsi, [r11+48h]
0x1400479ed  mov     rsp, r11
0x1400479f0  pop     r15
0x1400479f2  pop     r14
0x1400479f4  pop     r12
0x1400479f6  pop     rdi
0x1400479f7  pop     rbp
0x1400479f8  retn
```
