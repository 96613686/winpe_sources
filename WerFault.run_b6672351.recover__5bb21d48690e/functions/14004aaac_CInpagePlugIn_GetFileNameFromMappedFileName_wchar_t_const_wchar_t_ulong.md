# CInpagePlugIn::GetFileNameFromMappedFileName(wchar_t const *,wchar_t *,ulong)

- ea: `0x14004aaac`
- end: `0x14004ac90`
- name: `?GetFileNameFromMappedFileName@CInpagePlugIn@@AEAAJPEB_WPEA_WK@Z`
- size: `484`
- prototype: `int(CInpagePlugIn *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004a91c`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000b580`
- `0x14003e1b4`
- `0x14004aaac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ac06`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ac06`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x14004ab7f`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x14004ab7f`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x14004abc0`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x14004abc0`

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
  v12 = *(_OWORD *)&off_1400642D0;
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
0x14004aaac  mov     [rsp-8+arg_0], rbx
0x14004aab1  mov     [rsp-8+arg_18], rsi
0x14004aab6  push    rbp
0x14004aab7  push    rdi
0x14004aab8  push    r12
0x14004aaba  push    r14
0x14004aabc  push    r15
0x14004aabe  lea     rbp, [rsp-390h]
0x14004aac6  sub     rsp, 490h
0x14004aacd  mov     rax, cs:__security_cookie
0x14004aad4  xor     rax, rsp
0x14004aad7  mov     [rbp+3B0h+var_30], rax
0x14004aade  mov     r15, r8
0x14004aae1  lea     rcx, [rsp+4B0h+var_44E]; void *
0x14004aae6  mov     rsi, rdx
0x14004aae9  xor     r12d, r12d
0x14004aaec  xor     edx, edx; Val
0x14004aaee  mov     [rsp+4B0h+Buffer], r12w
0x14004aaf4  mov     r8d, 206h; Size
0x14004aafa  call    memset_0
0x14004aaff  test    rsi, rsi
0x14004ab02  jz      loc_14004AC5F
0x14004ab08  test    r15, r15
0x14004ab0b  jz      loc_14004AC5F
0x14004ab11  mov     [r15], r12w
0x14004ab15  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14004ab19  mov     [rsp+4B0h+var_480], rsi
0x14004ab1e  inc     rdi
0x14004ab21  cmp     [rsi+rdi*2], r12w
0x14004ab26  jnz     short loc_14004AB1E
0x14004ab28  movups  xmm0, xmmword ptr cs:off_1400642D0; "\\Device\\LanmanRedirector"
0x14004ab2f  lea     rdx, [rsp+4B0h+var_470]
0x14004ab34  mov     [rsp+4B0h+var_478], rdi
0x14004ab39  lea     rcx, [rsp+4B0h+var_480]
0x14004ab3e  movdqu  [rsp+4B0h+var_470], xmm0
0x14004ab44  call    ?starts_with@?$basic_string_view@_WU?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@QEBA_NV12@@Z; utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>)
0x14004ab49  test    al, al
0x14004ab4b  jz      short loc_14004AB75
0x14004ab4d  lea     r9, [rsi+30h]
0x14004ab51  mov     edx, 104h; unsigned __int64
0x14004ab56  lea     r8, aS_5; "\\%s"
0x14004ab5d  mov     rcx, r15; wchar_t *
0x14004ab60  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14004ab65  test    eax, eax
0x14004ab67  js      loc_14004AC64
0x14004ab6d  mov     eax, r12d
0x14004ab70  jmp     loc_14004AC64
0x14004ab75  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x14004ab7a  mov     ecx, 103h; nBufferLength
0x14004ab7f  call    cs:__imp_GetLogicalDriveStringsW
0x14004ab86  nop     dword ptr [rax+rax+00h]
0x14004ab8b  test    eax, eax
0x14004ab8d  jz      short loc_14004AB6D
0x14004ab8f  movzx   eax, [rsp+4B0h+Buffer]
0x14004ab94  lea     r14, [rsp+4B0h+Buffer]
0x14004ab99  mov     [rsp+4B0h+var_45E], 3Ah ; ':'
0x14004aba1  mov     [rbp+3B0h+TargetPath], r12w
0x14004aba9  mov     r8d, 103h; ucchMax
0x14004abaf  mov     [rsp+4B0h+DeviceName], ax
0x14004abb4  lea     rdx, [rbp+3B0h+TargetPath]; lpTargetPath
0x14004abbb  lea     rcx, [rsp+4B0h+DeviceName]; lpDeviceName
0x14004abc0  call    cs:__imp_QueryDosDeviceW
0x14004abc7  nop     dword ptr [rax+rax+00h]
0x14004abcc  test    eax, eax
0x14004abce  jz      short loc_14004AC1C
0x14004abd0  lea     rax, [rbp+3B0h+TargetPath]
0x14004abd7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14004abdb  inc     rbx
0x14004abde  cmp     [rax+rbx*2], r12w
0x14004abe3  jnz     short loc_14004ABDB
0x14004abe5  test    rbx, rbx
0x14004abe8  jz      short loc_14004AC17
0x14004abea  cmp     rbx, rdi
0x14004abed  ja      short loc_14004AC1C
0x14004abef  mov     r9d, ebx; cchCount2
0x14004abf2  mov     [rsp+4B0h+bIgnoreCase], 1; bIgnoreCase
0x14004abfa  lea     r8, [rbp+3B0h+TargetPath]; lpString2
0x14004ac01  mov     edx, ebx; cchCount1
0x14004ac03  mov     rcx, rsi; lpString1
0x14004ac06  call    cs:__imp_CompareStringOrdinal
0x14004ac0d  nop     dword ptr [rax+rax+00h]
0x14004ac12  cmp     eax, 2
0x14004ac15  jnz     short loc_14004AC1C
0x14004ac17  cmp     rbx, rdi
0x14004ac1a  jb      short loc_14004AC3B
0x14004ac1c  movzx   eax, word ptr [r14]
0x14004ac20  add     r14, 2
0x14004ac24  test    ax, ax
0x14004ac27  jnz     short loc_14004AC1C
0x14004ac29  movzx   eax, word ptr [r14]
0x14004ac2d  test    ax, ax
0x14004ac30  jnz     loc_14004ABA9
0x14004ac36  jmp     loc_14004AB6D
0x14004ac3b  lea     rax, [rsi+rbx*2]
0x14004ac3f  mov     edx, 104h; unsigned __int64
0x14004ac44  lea     r9, [rsp+4B0h+DeviceName]
0x14004ac49  mov     qword ptr [rsp+4B0h+bIgnoreCase], rax
0x14004ac4e  lea     r8, aSS_4; "%s%s"
0x14004ac55  mov     rcx, r15; wchar_t *
0x14004ac58  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14004ac5d  jmp     short loc_14004AC64
0x14004ac5f  mov     eax, 80070057h
0x14004ac64  mov     rcx, [rbp+3B0h+var_30]
0x14004ac6b  xor     rcx, rsp; StackCookie
0x14004ac6e  call    __security_check_cookie
0x14004ac73  lea     r11, [rsp+4B0h+var_20]
0x14004ac7b  mov     rbx, [r11+30h]
0x14004ac7f  mov     rsi, [r11+48h]
0x14004ac83  mov     rsp, r11
0x14004ac86  pop     r15
0x14004ac88  pop     r14
0x14004ac8a  pop     r12
0x14004ac8c  pop     rdi
0x14004ac8d  pop     rbp
0x14004ac8e  retn
```
