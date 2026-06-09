# LoadLibraryFromLocalFolder

- ea: `0x14007ad20`
- end: `0x14007afa2`
- name: `LoadLibraryFromLocalFolder`
- size: `642`
- prototype: `HMODULE()`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14007abf8`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14007ad20`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14007add1`
- `KERNEL32!GetModuleFileNameW` at `0x14007add1`
- `KERNEL32!GetLastError` at `0x14007ae25`
- `KERNEL32!GetLastError` at `0x14007af52`
- `KERNEL32!GetLastError` at `0x14007ae25`
- `KERNEL32!GetLastError` at `0x14007af52`
- `KERNEL32!LoadLibraryW` at `0x14007af2b`
- `KERNEL32!LoadLibraryW` at `0x14007af2b`
- `KERNEL32!SetLastError` at `0x14007adf7`
- `KERNEL32!SetLastError` at `0x14007adf7`
- `msvcrt!_wsplitpath_s` at `0x14007ae76`
- `msvcrt!_wsplitpath_s` at `0x14007ae76`

## string_xrefs

- `0x14007aec1`: `FXSRESM.DLL`

## pseudocode

```c
HMODULE LoadLibraryFromLocalFolder()
{
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  CMapDeviceId *v2; // rcx
  __int64 v3; // rdx
  int v4; // eax
  HMODULE result; // rax
  char v6; // al
  wchar_t Drive[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v8; // [rsp+54h] [rbp-ACh]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR LibFileName[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Dir[264]; // [rsp+480h] [rbp+380h] BYREF

  memset_0(LibFileName, 0, 0x208u);
  memset_0(Filename, 0, 0x208u);
  *(_DWORD *)Drive = 0;
  v8 = 0;
  memset_0(Dir, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids);
  }
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Filename[0] = 0;
    goto LABEL_9;
  }
  if ( ModuleFileNameW == 260 )
  {
    Filename[0] = 0;
    SetLastError(0x7Au);
LABEL_9:
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v2 = WPP_GLOBAL_Control;
    v3 = 14;
    goto LABEL_18;
  }
  Filename[259] = 0;
  LastError = _wsplitpath_s(Filename, Drive, 3u, Dir, 0x104u, 0, 0, 0, 0);
  if ( LastError )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v3 = 15;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v2 + 2), v3, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids, LastError);
    return 0;
  }
  v4 = StringCchPrintfW(LibFileName, 0x104u, L"%s%s%s", Drive, Dir, L"FXSRESM.DLL");
  if ( v4 >= 0 )
  {
    result = LoadLibraryW(LibFileName);
    if ( result )
      return result;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids,
        (unsigned int)LibFileName,
        v6);
    }
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids, (unsigned int)v4);
  }
  return 0;
}

```

## disassembly

```asm
0x14007ad20  push    rbp
0x14007ad22  push    rbx
0x14007ad23  push    rsi
0x14007ad24  push    r14
0x14007ad26  push    r15
0x14007ad28  lea     rbp, [rsp-5A0h]
0x14007ad30  sub     rsp, 6A0h
0x14007ad37  mov     rax, cs:__security_cookie
0x14007ad3e  xor     rax, rsp
0x14007ad41  mov     [rbp+5C0h+var_30], rax
0x14007ad48  mov     ebx, 208h
0x14007ad4d  lea     rcx, [rbp+5C0h+LibFileName]; void *
0x14007ad54  mov     r8d, ebx; Size
0x14007ad57  xor     edx, edx; Val
0x14007ad59  call    memset_0
0x14007ad5e  mov     r8d, ebx; Size
0x14007ad61  lea     rcx, [rsp+6C0h+Filename]; void *
0x14007ad66  xor     edx, edx; Val
0x14007ad68  call    memset_0
0x14007ad6d  xor     eax, eax
0x14007ad6f  lea     rcx, [rbp+5C0h+Dir]; void *
0x14007ad76  mov     r8d, ebx; Size
0x14007ad79  mov     dword ptr [rsp+6C0h+Drive], eax
0x14007ad7d  xor     edx, edx; Val
0x14007ad7f  mov     [rsp+6C0h+var_66C], ax
0x14007ad84  call    memset_0
0x14007ad89  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ad90  lea     rsi, WPP_GLOBAL_Control
0x14007ad97  lea     r14, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x14007ad9e  mov     bl, 2
0x14007ada0  cmp     rcx, rsi
0x14007ada3  jz      short loc_14007ADC1
0x14007ada5  test    [rcx+1Ch], bl
0x14007ada8  jz      short loc_14007ADC1
0x14007adaa  cmp     byte ptr [rcx+19h], 5
0x14007adae  jb      short loc_14007ADC1
0x14007adb0  mov     rcx, [rcx+10h]
0x14007adb4  mov     edx, 0Dh
0x14007adb9  mov     r8, r14
0x14007adbc  call    WPP_SF_
0x14007adc1  mov     r15d, 104h
0x14007adc7  lea     rdx, [rsp+6C0h+Filename]; lpFilename
0x14007adcc  mov     r8d, r15d; nSize
0x14007adcf  xor     ecx, ecx; hModule
0x14007add1  call    cs:__imp_GetModuleFileNameW
0x14007add8  nop     dword ptr [rax+rax+00h]
0x14007addd  test    eax, eax
0x14007addf  jnz     short loc_14007ADE8
0x14007ade1  mov     [rsp+6C0h+Filename], ax
0x14007ade6  jmp     short loc_14007AE03
0x14007ade8  cmp     eax, r15d
0x14007adeb  jnz     short loc_14007AE3F
0x14007aded  xor     eax, eax
0x14007adef  mov     [rsp+6C0h+Filename], ax
0x14007adf4  lea     ecx, [rax+7Ah]; dwErrCode
0x14007adf7  call    cs:__imp_SetLastError
0x14007adfe  nop     dword ptr [rax+rax+00h]
0x14007ae03  mov     rax, cs:WPP_GLOBAL_Control
0x14007ae0a  cmp     rax, rsi
0x14007ae0d  jz      loc_14007AF81
0x14007ae13  test    [rax+1Ch], bl
0x14007ae16  jz      loc_14007AF81
0x14007ae1c  cmp     [rax+19h], bl
0x14007ae1f  jb      loc_14007AF81
0x14007ae25  call    cs:__imp_GetLastError
0x14007ae2c  nop     dword ptr [rax+rax+00h]
0x14007ae31  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ae38  mov     edx, 0Eh
0x14007ae3d  jmp     short loc_14007AEAD
0x14007ae3f  xor     eax, eax
0x14007ae41  mov     [rbp+5C0h+var_45A], ax
0x14007ae48  mov     [rsp+6C0h+ExtCount], rax; ExtCount
0x14007ae4d  lea     r9, [rbp+5C0h+Dir]; Dir
0x14007ae54  mov     [rsp+6C0h+Ext], rax; Ext
0x14007ae59  lea     r8d, [rax+3]; DriveCount
0x14007ae5d  mov     [rsp+6C0h+FilenameCount], rax; FilenameCount
0x14007ae62  lea     rdx, [rsp+6C0h+Drive]; Drive
0x14007ae67  mov     [rsp+6C0h+var_698], rax; Filename
0x14007ae6c  lea     rcx, [rsp+6C0h+Filename]; FullPath
0x14007ae71  mov     [rsp+6C0h+DirCount], r15; DirCount
0x14007ae76  call    cs:__imp__wsplitpath_s
0x14007ae7d  nop     dword ptr [rax+rax+00h]
0x14007ae82  test    eax, eax
0x14007ae84  jz      short loc_14007AEC1
0x14007ae86  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ae8d  cmp     rcx, rsi
0x14007ae90  jz      loc_14007AF81
0x14007ae96  test    [rcx+1Ch], bl
0x14007ae99  jz      loc_14007AF81
0x14007ae9f  cmp     [rcx+19h], bl
0x14007aea2  jb      loc_14007AF81
0x14007aea8  mov     edx, 0Fh
0x14007aead  mov     rcx, [rcx+10h]
0x14007aeb1  mov     r8, r14
0x14007aeb4  mov     r9d, eax
0x14007aeb7  call    WPP_SF_d
0x14007aebc  jmp     loc_14007AF81
0x14007aec1  lea     rax, aFxsresmDll; "FXSRESM.DLL"
0x14007aec8  mov     rdx, r15; unsigned __int64
0x14007aecb  mov     [rsp+6C0h+var_698], rax
0x14007aed0  lea     r9, [rsp+6C0h+Drive]
0x14007aed5  lea     rax, [rbp+5C0h+Dir]
0x14007aedc  lea     r8, aSSS; "%s%s%s"
0x14007aee3  mov     [rsp+6C0h+DirCount], rax
0x14007aee8  lea     rcx, [rbp+5C0h+LibFileName]; unsigned __int16 *
0x14007aeef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007aef4  test    eax, eax
0x14007aef6  jns     short loc_14007AF24
0x14007aef8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aeff  cmp     rcx, rsi
0x14007af02  jz      short loc_14007AF81
0x14007af04  test    [rcx+1Ch], bl
0x14007af07  jz      short loc_14007AF81
0x14007af09  cmp     [rcx+19h], bl
0x14007af0c  jb      short loc_14007AF81
0x14007af0e  mov     rcx, [rcx+10h]
0x14007af12  mov     edx, 10h
0x14007af17  mov     r9d, eax
0x14007af1a  mov     r8, r14
0x14007af1d  call    WPP_SF_d
0x14007af22  jmp     short loc_14007AF81
0x14007af24  lea     rcx, [rbp+5C0h+LibFileName]; lpLibFileName
0x14007af2b  call    cs:__imp_LoadLibraryW
0x14007af32  nop     dword ptr [rax+rax+00h]
0x14007af37  test    rax, rax
0x14007af3a  jnz     short loc_14007AF83
0x14007af3c  mov     rax, cs:WPP_GLOBAL_Control
0x14007af43  cmp     rax, rsi
0x14007af46  jz      short loc_14007AF81
0x14007af48  test    [rax+1Ch], bl
0x14007af4b  jz      short loc_14007AF81
0x14007af4d  cmp     [rax+19h], bl
0x14007af50  jb      short loc_14007AF81
0x14007af52  call    cs:__imp_GetLastError
0x14007af59  nop     dword ptr [rax+rax+00h]
0x14007af5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007af65  lea     r9, [rbp+5C0h+LibFileName]
0x14007af6c  mov     edx, 11h
0x14007af71  mov     dword ptr [rsp+6C0h+DirCount], eax
0x14007af75  mov     r8, r14
0x14007af78  mov     rcx, [rcx+10h]
0x14007af7c  call    WPP_SF_Sd
0x14007af81  xor     eax, eax
0x14007af83  mov     rcx, [rbp+5C0h+var_30]
0x14007af8a  xor     rcx, rsp; StackCookie
0x14007af8d  call    __security_check_cookie
0x14007af92  add     rsp, 6A0h
0x14007af99  pop     r15
0x14007af9b  pop     r14
0x14007af9d  pop     rsi
0x14007af9e  pop     rbx
0x14007af9f  pop     rbp
0x14007afa0  retn
```
