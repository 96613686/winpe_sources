# Messaging_IsUnderMediaTempFolder(ushort const *,int *)

- ea: `0x180052320`
- end: `0x180052482`
- name: `?Messaging_IsUnderMediaTempFolder@@YAJPEBGPEAH@Z`
- size: `354`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180008870`
- `0x18000a754`
- `0x18004ee90`
- `0x180052258`
- `0x180052320`
- `0x18005262c`
- `0x1800526cc`
- `0x18005cdcc`
- `0x1800c6940`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180052442`
- `msvcrt!_wcsnicmp` at `0x180052442`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800523ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800523fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800523ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800523fd`

## pseudocode

```c
__int64 __fastcall Messaging_IsUnderMediaTempFolder(const unsigned __int16 *a1, int *a2)
{
  int MediaTempFolder; // eax
  unsigned int v5; // ebx
  int DriveNumber; // ebx
  const unsigned __int16 *v7; // rdi
  const wchar_t *v8; // r11
  size_t MaxCount; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v11[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v12; // [rsp+48h] [rbp-B8h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v14[264]; // [rsp+270h] [rbp+170h] BYREF

  *a2 = 0;
  *(_OWORD *)v11 = 0;
  v12 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
  MediaTempFolder = MessagingGetMediaTempFolder(v11);
  v5 = MediaTempFolder;
  if ( MediaTempFolder >= 0 )
  {
    MediaTempFolder = _ExpandPath(v11[0], pszPath);
    v5 = MediaTempFolder;
    if ( MediaTempFolder >= 0 )
    {
      MediaTempFolder = _ExpandPath(a1, v14);
      v5 = MediaTempFolder;
      if ( MediaTempFolder >= 0 )
      {
        DriveNumber = _GetDriveNumber(v14);
        if ( DriveNumber != (unsigned int)_GetDriveNumber(pszPath) || (v7 = PathSkipRootW(pszPath), !PathSkipRootW(v14)) )
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
  Log_HREvent_28(MediaTempFolder);
LABEL_11:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
  return v5;
}

```

## disassembly

```asm
0x180052320  mov     [rsp-8+arg_10], rbx
0x180052325  push    rbp
0x180052326  push    rsi
0x180052327  push    rdi
0x180052328  lea     rbp, [rsp-390h]
0x180052330  sub     rsp, 490h
0x180052337  mov     rax, cs:__security_cookie
0x18005233e  xor     rax, rsp
0x180052341  mov     [rbp+3A0h+var_20], rax
0x180052348  xorps   xmm0, xmm0
0x18005234b  mov     dword ptr [rdx], 0
0x180052351  mov     rdi, rcx
0x180052354  mov     rsi, rdx
0x180052357  lea     rcx, [rsp+4A0h+var_468]
0x18005235c  movups  xmmword ptr [rsp+4A0h+var_468], xmm0
0x180052361  movups  [rsp+4A0h+var_458], xmm0
0x180052366  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18005236b  lea     rcx, [rsp+4A0h+var_468]
0x180052370  call    ?MessagingGetMediaTempFolder@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; MessagingGetMediaTempFolder(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180052375  mov     ebx, eax
0x180052377  test    eax, eax
0x180052379  jns     short loc_180052383
0x18005237b  mov     r9d, 75h ; 'u'
0x180052381  jmp     short loc_18005239E
0x180052383  mov     rcx, [rsp+4A0h+var_468]; unsigned __int16 *
0x180052388  lea     rdx, [rsp+4A0h+pszPath]; unsigned __int16 *
0x18005238d  call    ?_ExpandPath@@YAJPEBGPEAG@Z; _ExpandPath(ushort const *,ushort *)
0x180052392  mov     ebx, eax
0x180052394  test    eax, eax
0x180052396  jns     short loc_1800523AF
0x180052398  mov     r9d, 78h ; 'x'
0x18005239e  mov     edx, 1
0x1800523a3  mov     ecx, eax; int
0x1800523a5  call    Log_HREvent_28
0x1800523aa  jmp     loc_180052454
0x1800523af  lea     rdx, [rbp+3A0h+var_230]; unsigned __int16 *
0x1800523b6  mov     rcx, rdi; unsigned __int16 *
0x1800523b9  call    ?_ExpandPath@@YAJPEBGPEAG@Z; _ExpandPath(ushort const *,ushort *)
0x1800523be  mov     ebx, eax
0x1800523c0  test    eax, eax
0x1800523c2  jns     short loc_1800523CC
0x1800523c4  mov     r9d, 7Bh ; '{'
0x1800523ca  jmp     short loc_18005239E
0x1800523cc  lea     rcx, [rbp+3A0h+var_230]; unsigned __int16 *
0x1800523d3  call    ?_GetDriveNumber@@YAHPEBG@Z; _GetDriveNumber(ushort const *)
0x1800523d8  lea     rcx, [rsp+4A0h+pszPath]; unsigned __int16 *
0x1800523dd  mov     ebx, eax
0x1800523df  call    ?_GetDriveNumber@@YAHPEBG@Z; _GetDriveNumber(ushort const *)
0x1800523e4  cmp     ebx, eax
0x1800523e6  jnz     short loc_180052452
0x1800523e8  lea     rcx, [rsp+4A0h+pszPath]; pszPath
0x1800523ed  call    cs:__imp_PathSkipRootW
0x1800523f3  lea     rcx, [rbp+3A0h+var_230]; pszPath
0x1800523fa  mov     rdi, rax
0x1800523fd  call    cs:__imp_PathSkipRootW
0x180052403  mov     r11, rax
0x180052406  test    rax, rax
0x180052409  jz      short loc_180052452
0x18005240b  lea     r8, [rsp+4A0h+MaxCount]; unsigned __int64 *
0x180052410  mov     [rsp+4A0h+MaxCount], 0
0x180052419  mov     edx, 104h; unsigned __int64
0x18005241e  mov     rcx, rdi; unsigned __int16 *
0x180052421  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180052426  mov     ebx, eax
0x180052428  test    eax, eax
0x18005242a  jns     short loc_180052437
0x18005242c  mov     r9d, 92h
0x180052432  jmp     loc_18005239E
0x180052437  mov     r8, [rsp+4A0h+MaxCount]; MaxCount
0x18005243c  mov     rdx, rdi; String2
0x18005243f  mov     rcx, r11; String1
0x180052442  call    cs:__imp__wcsnicmp
0x180052448  test    eax, eax
0x18005244a  jnz     short loc_180052452
0x18005244c  mov     dword ptr [rsi], 1
0x180052452  xor     ebx, ebx
0x180052454  lea     rcx, [rsp+4A0h+var_468]
0x180052459  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005245e  mov     eax, ebx
0x180052460  mov     rcx, [rbp+3A0h+var_20]
0x180052467  xor     rcx, rsp; StackCookie
0x18005246a  call    __security_check_cookie
0x18005246f  mov     rbx, [rsp+4A0h+arg_10]
0x180052477  add     rsp, 490h
0x18005247e  pop     rdi
0x18005247f  pop     rsi
0x180052480  pop     rbp
0x180052481  retn
```
