# CFveDriveType::GetFveVolumePath(ushort const *,ushort *,ulong)

- ea: `0x180071a28`
- end: `0x180071c03`
- name: `?GetFveVolumePath@CFveDriveType@@SAJPEBGPEAGK@Z`
- size: `475`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x180032f60`
- `0x180071970`
- `0x180075754`
- `0x1800791dc`
- `0x180079374`

## callees

- `0x18000dd60`
- `0x18000f760`
- `0x18001b7f0`
- `0x180034070`
- `0x180034500`
- `0x180034cbc`
- `0x180034d28`
- `0x180071a28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071baf`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180071b9b`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180071b9b`

## pseudocode

```c
signed int __fastcall CFveDriveType::GetFveVolumePath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int result; // eax
  __int64 v5; // rdx
  unsigned __int64 v6; // rbx
  unsigned __int64 v7[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+40h] [rbp-C0h] BYREF

  v7[0] = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  memset_0(a2, 0, 0x104u);
  result = StringCchLengthW(a1, 0x104u, v7);
  if ( result < 0 )
    return result;
  if ( v7[0] < 2 )
    return -2147024809;
  if ( v7[0] > 3 )
  {
    if ( !GetVolumePathNameW(a1, szVolumePathName, 0x104u) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
  }
  else
  {
    if ( !iswascii(*a1) || a1[1] != 58 || v7[0] == 3 && a1[2] != 92 )
      return -2147024809;
    result = StringCchCopyW(szVolumePathName, 0x104u, a1);
    if ( result < 0 )
      return result;
  }
  result = StringCchLengthW(szVolumePathName, 0x104u, v7);
  if ( result >= 0 )
  {
    v6 = v7[0];
    if ( v7[0] < 2 )
      return -2147024809;
    if ( *((_WORD *)&v7[1] + v7[0] + 3) == 92 )
    {
      v6 = v7[0] - 1;
      if ( 2 * (v7[0] - 1) >= 0x208 )
        _report_rangecheckfailure(2 * (v7[0] - 1), v5);
      szVolumePathName[v6] = 0;
    }
    if ( iswascii(szVolumePathName[0]) && szVolumePathName[1] == 58 && (v6 == 2 || v6 == 3 && szVolumePathName[2] == 92) )
      return StringCchPrintfW(a2, 0x104u, L"%s%s", L"\\\\.\\", szVolumePathName);
    else
      return StringCchCopyW(a2, 0x104u, szVolumePathName);
  }
  return result;
}

```

## disassembly

```asm
0x180071a28  mov     [rsp-8+arg_10], rbx
0x180071a2d  push    rbp
0x180071a2e  push    rsi
0x180071a2f  push    r14
0x180071a31  lea     rbp, [rsp-160h]
0x180071a39  sub     rsp, 260h
0x180071a40  mov     rax, cs:__security_cookie
0x180071a47  xor     rax, rsp
0x180071a4a  mov     [rbp+170h+var_20], rax
0x180071a51  mov     rsi, rdx
0x180071a54  mov     [rsp+270h+var_240], 0
0x180071a5d  mov     rbx, rcx
0x180071a60  xor     edx, edx; Val
0x180071a62  lea     rcx, [rsp+270h+szVolumePathName]; void *
0x180071a67  mov     r8d, 208h; Size
0x180071a6d  call    memset_0
0x180071a72  mov     r14d, 104h
0x180071a78  xor     edx, edx; Val
0x180071a7a  mov     r8d, r14d; Size
0x180071a7d  mov     rcx, rsi; void *
0x180071a80  call    memset_0
0x180071a85  lea     r8, [rsp+270h+var_240]; unsigned __int64 *
0x180071a8a  mov     edx, r14d; unsigned __int64
0x180071a8d  mov     rcx, rbx; unsigned __int16 *
0x180071a90  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180071a95  test    eax, eax
0x180071a97  js      loc_180071BDF
0x180071a9d  cmp     [rsp+270h+var_240], 2
0x180071aa3  jnb     short loc_180071AAF
0x180071aa5  mov     eax, 80070057h
0x180071aaa  jmp     loc_180071BDF
0x180071aaf  cmp     [rsp+270h+var_240], 3
0x180071ab5  ja      loc_180071B90
0x180071abb  movzx   ecx, word ptr [rbx]; C
0x180071abe  call    iswascii
0x180071ac3  test    eax, eax
0x180071ac5  jz      short loc_180071AA5
0x180071ac7  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180071acc  jnz     short loc_180071AA5
0x180071ace  cmp     [rsp+270h+var_240], 3
0x180071ad4  jnz     short loc_180071ADD
0x180071ad6  cmp     word ptr [rbx+4], 5Ch ; '\'
0x180071adb  jnz     short loc_180071AA5
0x180071add  mov     r8, rbx; unsigned __int16 *
0x180071ae0  lea     rcx, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x180071ae5  mov     rdx, r14; unsigned __int64
0x180071ae8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180071aed  test    eax, eax
0x180071aef  js      loc_180071BDF
0x180071af5  lea     r8, [rsp+270h+var_240]; unsigned __int64 *
0x180071afa  mov     rdx, r14; unsigned __int64
0x180071afd  lea     rcx, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x180071b02  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180071b07  test    eax, eax
0x180071b09  js      loc_180071BDF
0x180071b0f  mov     rbx, [rsp+270h+var_240]
0x180071b14  cmp     rbx, 2
0x180071b18  jb      short loc_180071AA5
0x180071b1a  cmp     [rsp+rbx*2+270h+var_232], 5Ch ; '\'
0x180071b20  jnz     short loc_180071B3D
0x180071b22  dec     rbx
0x180071b25  lea     rcx, [rbx+rbx]
0x180071b29  cmp     rcx, 208h
0x180071b30  jnb     loc_180071BC9
0x180071b36  xor     eax, eax
0x180071b38  mov     [rsp+rcx+270h+szVolumePathName], ax
0x180071b3d  movzx   ecx, [rsp+270h+szVolumePathName]; C
0x180071b42  call    iswascii
0x180071b47  test    eax, eax
0x180071b49  jz      loc_180071BCF
0x180071b4f  cmp     [rsp+270h+var_22E], 3Ah ; ':'
0x180071b55  jnz     short loc_180071BCF
0x180071b57  cmp     rbx, 2
0x180071b5b  jz      short loc_180071B6B
0x180071b5d  cmp     rbx, 3
0x180071b61  jnz     short loc_180071BCF
0x180071b63  cmp     [rsp+270h+var_22C], 5Ch ; '\'
0x180071b69  jnz     short loc_180071BCF
0x180071b6b  lea     rax, [rsp+270h+szVolumePathName]
0x180071b70  mov     rdx, r14; unsigned __int64
0x180071b73  lea     r9, asc_18008A968; "\\\\.\\"
0x180071b7a  mov     [rsp+270h+var_250], rax
0x180071b7f  lea     r8, aSS_0; "%s%s"
0x180071b86  mov     rcx, rsi; unsigned __int16 *
0x180071b89  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180071b8e  jmp     short loc_180071BDF
0x180071b90  mov     r8d, r14d; cchBufferLength
0x180071b93  lea     rdx, [rsp+270h+szVolumePathName]; lpszVolumePathName
0x180071b98  mov     rcx, rbx; lpszFileName
0x180071b9b  call    cs:__imp_GetVolumePathNameW
0x180071ba2  nop     dword ptr [rax+rax+00h]
0x180071ba7  test    eax, eax
0x180071ba9  jnz     loc_180071AF5
0x180071baf  call    cs:__imp_GetLastError
0x180071bb6  nop     dword ptr [rax+rax+00h]
0x180071bbb  test    eax, eax
0x180071bbd  jle     short loc_180071BDF
0x180071bbf  movzx   eax, ax
0x180071bc2  or      eax, 80070000h
0x180071bc7  jmp     short loc_180071BDF
0x180071bc9  call    __report_rangecheckfailure
0x180071bcf  lea     r8, [rsp+270h+szVolumePathName]; unsigned __int16 *
0x180071bd4  mov     rdx, r14; unsigned __int64
0x180071bd7  mov     rcx, rsi; unsigned __int16 *
0x180071bda  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180071bdf  mov     rcx, [rbp+170h+var_20]
0x180071be6  xor     rcx, rsp; StackCookie
0x180071be9  call    __security_check_cookie
0x180071bee  mov     rbx, [rsp+270h+arg_10]
0x180071bf6  add     rsp, 260h
0x180071bfd  pop     r14
0x180071bff  pop     rsi
0x180071c00  pop     rbp
0x180071c01  retn
```
