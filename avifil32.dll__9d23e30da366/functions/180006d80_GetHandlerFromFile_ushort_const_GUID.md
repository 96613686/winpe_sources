# GetHandlerFromFile(ushort const *,_GUID *)

- ea: `0x180006d80`
- end: `0x180006fab`
- name: `?GetHandlerFromFile@@YAHPEBGPEAU_GUID@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(LPWSTR pszFileName, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180007c00`

## callees

- `0x180001460`
- `0x180006d80`
- `0x1800070ec`
- `0x1800088ac`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180006f12`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180006f84`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180006f12`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180006f84`
- `WINMM!mmioRead` at `0x180006e11`
- `WINMM!mmioRead` at `0x180006e11`
- `WINMM!mmioClose` at `0x180006e25`
- `WINMM!mmioClose` at `0x180006eaf`
- `WINMM!mmioClose` at `0x180006e25`
- `WINMM!mmioClose` at `0x180006eaf`
- `WINMM!mmioOpenW` at `0x180006dc8`
- `WINMM!mmioOpenW` at `0x180006ddf`
- `WINMM!mmioOpenW` at `0x180006df5`
- `WINMM!mmioOpenW` at `0x180006dc8`
- `WINMM!mmioOpenW` at `0x180006ddf`
- `WINMM!mmioOpenW` at `0x180006df5`

## string_xrefs

- `0x180006f46`: `AVIFile\Extensions`

## pseudocode

```c
_BOOL8 __fastcall GetHandlerFromFile(LPWSTR pszFileName, struct _GUID *a2)
{
  HMMIO v4; // rbx
  LPWSTR j; // rcx
  WCHAR *v6; // rax
  int v7; // ecx
  int i; // eax
  __int64 v10; // rcx
  WCHAR *v11; // rax
  LONG cbData; // [rsp+38h] [rbp-C8h] BYREF
  char pch[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[8]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Data[99]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v16; // [rsp+116h] [rbp+16h]
  WCHAR SubKey[104]; // [rsp+120h] [rbp+20h] BYREF

  cbData = 0;
  Data[0] = 0;
  v4 = mmioOpenW(pszFileName, 0, 0x20u);
  if ( v4 || (v4 = mmioOpenW(pszFileName, 0, 0x40u)) != 0 || (v4 = mmioOpenW(pszFileName, 0, 0)) != 0 )
  {
    if ( mmioRead(v4, pch, 12) == 12 )
    {
      mmioClose(v4, 0);
      if ( *(_DWORD *)pch == 1179011410 )
      {
        for ( i = 3; i >= 0; --i )
        {
          v10 = (unsigned int)i;
          if ( v14[i] != 32 )
            break;
          v14[v10] = 0;
        }
        StringCchPrintfW(SubKey, 0x64u, L"AVIFile\\RIFFHandlers\\%.4hs", v14);
        cbData = 200;
        RegQueryValueW(HKEY_CLASSES_ROOT, SubKey, Data, &cbData);
        v16 = 0;
        if ( (unsigned int)GUIDFromString(Data, a2) )
          return 1;
      }
    }
    else
    {
      mmioClose(v4, 0);
    }
  }
  for ( j = pszFileName; *j; ++j )
    ;
  if ( (unsigned __int64)(j - pszFileName) >= 4 && *(j - 1) != 46 )
  {
    v6 = j - 2;
    v7 = 1;
    while ( *v6 != 47 && *v6 != 92 )
    {
      if ( *v6 == 46 )
      {
        v11 = v6 + 1;
        if ( !v11 )
          return 0;
        StringCchPrintfW(SubKey, 0x64u, L"%s\\%.3ls", L"AVIFile\\Extensions", v11);
        cbData = 200;
        RegQueryValueW(HKEY_CLASSES_ROOT, SubKey, Data, &cbData);
        v16 = 0;
        return (unsigned int)GUIDFromString(Data, a2) != 0;
      }
      if ( v6 != pszFileName )
      {
        --v6;
        if ( ++v7 <= 3 )
          continue;
      }
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006d80  mov     [rsp-8+arg_10], rbx
0x180006d85  mov     [rsp-8+arg_18], rsi
0x180006d8a  push    rbp
0x180006d8b  push    rdi
0x180006d8c  push    r14
0x180006d8e  lea     rbp, [rsp-100h]
0x180006d96  sub     rsp, 200h
0x180006d9d  mov     rax, cs:__security_cookie
0x180006da4  xor     rax, rsp
0x180006da7  mov     [rbp+110h+var_20], rax
0x180006dae  xor     r14d, r14d
0x180006db1  mov     rsi, rdx
0x180006db4  xor     edx, edx; pmmioinfo
0x180006db6  mov     [rsp+210h+cbData], r14d
0x180006dbb  mov     rdi, rcx
0x180006dbe  mov     [rsp+210h+Data], r14w
0x180006dc4  lea     r8d, [r14+20h]; fdwOpen
0x180006dc8  call    cs:__imp_mmioOpenW
0x180006dce  mov     rbx, rax
0x180006dd1  test    rax, rax
0x180006dd4  jnz     short loc_180006E03
0x180006dd6  xor     edx, edx; pmmioinfo
0x180006dd8  lea     r8d, [r14+40h]; fdwOpen
0x180006ddc  mov     rcx, rdi; pszFileName
0x180006ddf  call    cs:__imp_mmioOpenW
0x180006de5  mov     rbx, rax
0x180006de8  test    rax, rax
0x180006deb  jnz     short loc_180006E03
0x180006ded  xor     r8d, r8d; fdwOpen
0x180006df0  xor     edx, edx; pmmioinfo
0x180006df2  mov     rcx, rdi; pszFileName
0x180006df5  call    cs:__imp_mmioOpenW
0x180006dfb  mov     rbx, rax
0x180006dfe  test    rax, rax
0x180006e01  jz      short loc_180006E2B
0x180006e03  mov     r8d, 0Ch; cch
0x180006e09  lea     rdx, [rsp+210h+pch]; pch
0x180006e0e  mov     rcx, rbx; hmmio
0x180006e11  call    cs:__imp_mmioRead
0x180006e17  xor     edx, edx; fuClose
0x180006e19  mov     rcx, rbx; hmmio
0x180006e1c  cmp     eax, 0Ch
0x180006e1f  jz      loc_180006EAF
0x180006e25  call    cs:__imp_mmioClose
0x180006e2b  mov     rcx, rdi
0x180006e2e  cmp     [rdi], r14w
0x180006e32  jz      short loc_180006E3E
0x180006e34  add     rcx, 2
0x180006e38  cmp     [rcx], r14w
0x180006e3c  jnz     short loc_180006E34
0x180006e3e  mov     rax, rcx
0x180006e41  sub     rax, rdi
0x180006e44  sar     rax, 1
0x180006e47  cmp     rax, 4
0x180006e4b  jb      short loc_180006E86
0x180006e4d  lea     rax, [rcx-2]
0x180006e51  cmp     word ptr [rax], 2Eh ; '.'
0x180006e55  jz      short loc_180006E86
0x180006e57  sub     rax, 2
0x180006e5b  mov     ecx, 1
0x180006e60  cmp     word ptr [rax], 2Fh ; '/'
0x180006e64  jz      short loc_180006E86
0x180006e66  cmp     word ptr [rax], 5Ch ; '\'
0x180006e6a  jz      short loc_180006E86
0x180006e6c  cmp     word ptr [rax], 2Eh ; '.'
0x180006e70  jz      loc_180006F3C
0x180006e76  cmp     rax, rdi
0x180006e79  jz      short loc_180006E86
0x180006e7b  sub     rax, 2
0x180006e7f  inc     ecx
0x180006e81  cmp     ecx, 3
0x180006e84  jle     short loc_180006E60
0x180006e86  xor     eax, eax
0x180006e88  mov     rcx, [rbp+110h+var_20]
0x180006e8f  xor     rcx, rsp; StackCookie
0x180006e92  call    __security_check_cookie
0x180006e97  lea     r11, [rsp+210h+var_10]
0x180006e9f  mov     rbx, [r11+30h]
0x180006ea3  mov     rsi, [r11+38h]
0x180006ea7  mov     rsp, r11
0x180006eaa  pop     r14
0x180006eac  pop     rdi
0x180006ead  pop     rbp
0x180006eae  retn
0x180006eaf  call    cs:__imp_mmioClose
0x180006eb5  cmp     dword ptr [rsp+210h+pch], 46464952h
0x180006ebd  jnz     loc_180006E2B
0x180006ec3  mov     eax, 3
0x180006ec8  mov     ecx, eax
0x180006eca  cmp     [rsp+rcx+210h+var_1C8], 20h ; ' '
0x180006ecf  jnz     short loc_180006EDB
0x180006ed1  sub     eax, 1
0x180006ed4  mov     [rsp+rcx+210h+var_1C8], r14b
0x180006ed9  jns     short loc_180006EC8
0x180006edb  lea     r9, [rsp+210h+var_1C8]
0x180006ee0  mov     edx, 64h ; 'd'; unsigned __int64
0x180006ee5  lea     r8, aAvifileRiffhan; "AVIFile\\RIFFHandlers\\%.4hs"
0x180006eec  lea     rcx, [rbp+110h+SubKey]; unsigned __int16 *
0x180006ef0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006ef5  lea     r9, [rsp+210h+cbData]; lpcbData
0x180006efa  mov     [rsp+210h+cbData], 0C8h
0x180006f02  lea     r8, [rsp+210h+Data]; lpData
0x180006f07  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180006f0e  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x180006f12  call    cs:__imp_RegQueryValueW
0x180006f18  mov     rdx, rsi
0x180006f1b  mov     [rbp+110h+var_FA], r14w
0x180006f20  lea     rcx, [rsp+210h+Data]
0x180006f25  call    GUIDFromString
0x180006f2a  test    eax, eax
0x180006f2c  jz      loc_180006E2B
0x180006f32  mov     eax, 1
0x180006f37  jmp     loc_180006E88
0x180006f3c  add     rax, 2
0x180006f40  jz      loc_180006E86
0x180006f46  lea     r9, SubKey; "AVIFile\\Extensions"
0x180006f4d  mov     [rsp+210h+var_1F0], rax
0x180006f52  lea     r8, aS3ls; "%s\\%.3ls"
0x180006f59  mov     edx, 64h ; 'd'; unsigned __int64
0x180006f5e  lea     rcx, [rbp+110h+SubKey]; unsigned __int16 *
0x180006f62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006f67  lea     r9, [rsp+210h+cbData]; lpcbData
0x180006f6c  mov     [rsp+210h+cbData], 0C8h
0x180006f74  lea     r8, [rsp+210h+Data]; lpData
0x180006f79  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180006f80  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x180006f84  call    cs:__imp_RegQueryValueW
0x180006f8a  mov     rdx, rsi
0x180006f8d  mov     [rbp+110h+var_FA], r14w
0x180006f92  lea     rcx, [rsp+210h+Data]
0x180006f97  call    GUIDFromString
0x180006f9c  test    eax, eax
0x180006f9e  mov     ecx, r14d
0x180006fa1  setnz   cl
0x180006fa4  mov     eax, ecx
0x180006fa6  jmp     loc_180006E88
```
