# MessagingIsUnderMediaTempFolder(ushort const *,int *)

- ea: `0x18005d08c`
- end: `0x18005d1ee`
- name: `?MessagingIsUnderMediaTempFolder@@YAJPEBGPEAH@Z`
- size: `354`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800251c4`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18004ee90`
- `0x18005cd08`
- `0x18005cdcc`
- `0x18005d08c`
- `0x18005d70c`
- `0x18005d8e4`
- `0x1800c6940`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18005d1ae`
- `msvcrt!_wcsnicmp` at `0x18005d1ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18005d159`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18005d169`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18005d159`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18005d169`

## pseudocode

```c
__int64 __fastcall MessagingIsUnderMediaTempFolder(const unsigned __int16 *a1, int *a2)
{
  int MediaTempFolder; // eax
  unsigned int v5; // ebx
  int DriveNumber; // ebx
  const unsigned __int16 *v7; // rdi
  const wchar_t *v8; // r11
  size_t MaxCount; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v11[2]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v13[264]; // [rsp+270h] [rbp+170h] BYREF

  *a2 = 0;
  memset(v11, 0, sizeof(v11));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
  MediaTempFolder = MessagingGetMediaTempFolder((__int64)v11);
  v5 = MediaTempFolder;
  if ( MediaTempFolder >= 0 )
  {
    MediaTempFolder = ExpandPath(*(_QWORD *)&v11[0], pszPath);
    v5 = MediaTempFolder;
    if ( MediaTempFolder >= 0 )
    {
      MediaTempFolder = ExpandPath(a1, v13);
      v5 = MediaTempFolder;
      if ( MediaTempFolder >= 0 )
      {
        DriveNumber = GetDriveNumber(v13);
        if ( DriveNumber != (unsigned int)GetDriveNumber(pszPath) || (v7 = PathSkipRootW(pszPath), !PathSkipRootW(v13)) )
        {
LABEL_10:
          v5 = 0;
          goto LABEL_11;
        }
        MaxCount = 0;
        MediaTempFolder = StringCchLengthW(v7, 0x104u, &MaxCount);
        v5 = MediaTempFolder;
        if ( MediaTempFolder >= 0 )
        {
          if ( !_wcsnicmp(v8, v7, MaxCount) )
            *a2 = 1;
          goto LABEL_10;
        }
      }
    }
  }
  Log_HREvent_33(MediaTempFolder);
LABEL_11:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
  return v5;
}

```

## disassembly

```asm
0x18005d08c  mov     [rsp-8+arg_10], rbx
0x18005d091  push    rbp
0x18005d092  push    rsi
0x18005d093  push    rdi
0x18005d094  lea     rbp, [rsp-390h]
0x18005d09c  sub     rsp, 490h
0x18005d0a3  mov     rax, cs:__security_cookie
0x18005d0aa  xor     rax, rsp
0x18005d0ad  mov     [rbp+3A0h+var_20], rax
0x18005d0b4  xorps   xmm0, xmm0
0x18005d0b7  mov     dword ptr [rdx], 0
0x18005d0bd  mov     rdi, rcx
0x18005d0c0  mov     rsi, rdx
0x18005d0c3  lea     rcx, [rsp+4A0h+var_468]
0x18005d0c8  movups  [rsp+4A0h+var_468], xmm0
0x18005d0cd  movups  [rsp+4A0h+var_458], xmm0
0x18005d0d2  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18005d0d7  lea     rcx, [rsp+4A0h+var_468]
0x18005d0dc  call    ?MessagingGetMediaTempFolder@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; MessagingGetMediaTempFolder(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18005d0e1  mov     ebx, eax
0x18005d0e3  test    eax, eax
0x18005d0e5  jns     short loc_18005D0EF
0x18005d0e7  mov     r9d, 9Ch
0x18005d0ed  jmp     short loc_18005D10A
0x18005d0ef  mov     rcx, qword ptr [rsp+4A0h+var_468]
0x18005d0f4  lea     rdx, [rsp+4A0h+pszPath]
0x18005d0f9  call    _ExpandPath
0x18005d0fe  mov     ebx, eax
0x18005d100  test    eax, eax
0x18005d102  jns     short loc_18005D11B
0x18005d104  mov     r9d, 9Fh
0x18005d10a  mov     edx, 1
0x18005d10f  mov     ecx, eax; int
0x18005d111  call    Log_HREvent_33
0x18005d116  jmp     loc_18005D1C0
0x18005d11b  lea     rdx, [rbp+3A0h+var_230]
0x18005d122  mov     rcx, rdi
0x18005d125  call    _ExpandPath
0x18005d12a  mov     ebx, eax
0x18005d12c  test    eax, eax
0x18005d12e  jns     short loc_18005D138
0x18005d130  mov     r9d, 0A2h
0x18005d136  jmp     short loc_18005D10A
0x18005d138  lea     rcx, [rbp+3A0h+var_230]
0x18005d13f  call    _GetDriveNumber
0x18005d144  lea     rcx, [rsp+4A0h+pszPath]
0x18005d149  mov     ebx, eax
0x18005d14b  call    _GetDriveNumber
0x18005d150  cmp     ebx, eax
0x18005d152  jnz     short loc_18005D1BE
0x18005d154  lea     rcx, [rsp+4A0h+pszPath]; pszPath
0x18005d159  call    cs:__imp_PathSkipRootW
0x18005d15f  lea     rcx, [rbp+3A0h+var_230]; pszPath
0x18005d166  mov     rdi, rax
0x18005d169  call    cs:__imp_PathSkipRootW
0x18005d16f  mov     r11, rax
0x18005d172  test    rax, rax
0x18005d175  jz      short loc_18005D1BE
0x18005d177  lea     r8, [rsp+4A0h+MaxCount]; unsigned __int64 *
0x18005d17c  mov     [rsp+4A0h+MaxCount], 0
0x18005d185  mov     edx, 104h; unsigned __int64
0x18005d18a  mov     rcx, rdi; unsigned __int16 *
0x18005d18d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005d192  mov     ebx, eax
0x18005d194  test    eax, eax
0x18005d196  jns     short loc_18005D1A3
0x18005d198  mov     r9d, 0B9h
0x18005d19e  jmp     loc_18005D10A
0x18005d1a3  mov     r8, [rsp+4A0h+MaxCount]; MaxCount
0x18005d1a8  mov     rdx, rdi; String2
0x18005d1ab  mov     rcx, r11; String1
0x18005d1ae  call    cs:__imp__wcsnicmp
0x18005d1b4  test    eax, eax
0x18005d1b6  jnz     short loc_18005D1BE
0x18005d1b8  mov     dword ptr [rsi], 1
0x18005d1be  xor     ebx, ebx
0x18005d1c0  lea     rcx, [rsp+4A0h+var_468]
0x18005d1c5  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005d1ca  mov     eax, ebx
0x18005d1cc  mov     rcx, [rbp+3A0h+var_20]
0x18005d1d3  xor     rcx, rsp; StackCookie
0x18005d1d6  call    __security_check_cookie
0x18005d1db  mov     rbx, [rsp+4A0h+arg_10]
0x18005d1e3  add     rsp, 490h
0x18005d1ea  pop     rdi
0x18005d1eb  pop     rsi
0x18005d1ec  pop     rbp
0x18005d1ed  retn
```
