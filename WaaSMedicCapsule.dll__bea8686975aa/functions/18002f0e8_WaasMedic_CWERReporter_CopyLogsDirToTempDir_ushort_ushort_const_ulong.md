# WaasMedic::CWERReporter::CopyLogsDirToTempDir(ushort *,ushort * * const,ulong)

- ea: `0x18002f0e8`
- end: `0x18002f211`
- name: `?CopyLogsDirToTempDir@CWERReporter@WaasMedic@@AEAAJPEAGQEAPEAGK@Z`
- size: `297`
- prototype: `int(WaasMedic::CWERReporter *__hidden this, unsigned __int16 *, unsigned __int16 **const, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18002ed2c`

## callees

- `0x180003bb0`
- `0x18002543c`
- `0x18002a600`
- `0x18002f0e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1ba`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002f160`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002f160`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002f11a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002f11a`

## string_xrefs

- `0x18002f143`: `Failed to create directory %s! hr=0x%08x`
- `0x18002f1cf`: `Failed to expand log file share path %s! hr = 0x%08x`
- `0x18002f1b1`: `Failed to expand log file share path %s due to insufficient buffer! hr = 0x%08x`
- `0x18002f19e`: `Failed to copy directory from %s to %s! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CWERReporter::CopyLogsDirToTempDir(
        WaasMedic::CWERReporter *this,
        unsigned __int16 *a2,
        unsigned __int16 **const a3)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  DWORD v8; // eax
  const unsigned __int16 *v9; // r8
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  signed int LastError; // eax
  int v14; // [rsp+20h] [rbp-248h]
  WCHAR Dst[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( CreateDirectoryW(a2, 0) || (v5 = GetLastError(), v6 = v5, v5 == 183) )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = ExpandEnvironmentStringsW(a3[v7], Dst, 0x104u);
      if ( !v8 )
        break;
      if ( v8 > 0x104 )
      {
        v6 = -2147024774;
        v11 = L"Failed to expand log file share path %s due to insufficient buffer! hr = 0x%08x";
        goto LABEL_17;
      }
      v10 = WaasMedic::CopyDirectory((WaasMedic *)Dst, a2, v9);
      v6 = v10;
      if ( v10 < 0 )
      {
        v14 = v10;
        LogLevelW(2u, L"Failed to copy directory from %s to %s! hr = 0x%08x", Dst, a2, v14);
        return v6;
      }
      v7 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v7 >= 3 )
        return v6;
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v11 = L"Failed to expand log file share path %s! hr = 0x%08x";
LABEL_17:
    LogLevelW(2u, v11, a3[v7], v6);
  }
  else
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    LogLevelW(2u, L"Failed to create directory %s! hr=0x%08x", a2, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18002f0e8  mov     [rsp+arg_0], rbx
0x18002f0ed  mov     [rsp+arg_18], rbp
0x18002f0f2  push    rsi
0x18002f0f3  push    rdi
0x18002f0f4  push    r14
0x18002f0f6  sub     rsp, 250h
0x18002f0fd  mov     rax, cs:__security_cookie
0x18002f104  xor     rax, rsp
0x18002f107  mov     [rsp+268h+var_28], rax
0x18002f10f  mov     rsi, rdx
0x18002f112  mov     r14, r8
0x18002f115  mov     rcx, rsi; lpPathName
0x18002f118  xor     edx, edx; lpSecurityAttributes
0x18002f11a  call    cs:__imp_CreateDirectoryW
0x18002f120  test    eax, eax
0x18002f122  jnz     short loc_18002F14F
0x18002f124  call    cs:__imp_GetLastError
0x18002f12a  mov     ebx, eax
0x18002f12c  cmp     eax, 0B7h
0x18002f131  jz      short loc_18002F14F
0x18002f133  test    eax, eax
0x18002f135  jle     short loc_18002F140
0x18002f137  movzx   ebx, ax
0x18002f13a  or      ebx, 80070000h
0x18002f140  mov     r8, rsi
0x18002f143  lea     rdx, aFailedToCreate_3; "Failed to create directory %s! hr=0x%08"...
0x18002f14a  jmp     loc_18002F1DA
0x18002f14f  xor     edi, edi
0x18002f151  mov     rcx, [r14+rdi*8]; lpSrc
0x18002f155  lea     rdx, [rsp+268h+Dst]; lpDst
0x18002f15a  mov     r8d, 104h; nSize
0x18002f160  call    cs:__imp_ExpandEnvironmentStringsW
0x18002f166  test    eax, eax
0x18002f168  jz      short loc_18002F1BA
0x18002f16a  cmp     eax, 104h
0x18002f16f  ja      short loc_18002F1AC
0x18002f171  mov     rdx, rsi; unsigned __int16 *
0x18002f174  lea     rcx, [rsp+268h+Dst]; this
0x18002f179  call    ?CopyDirectory@WaasMedic@@YAJPEBG0@Z; WaasMedic::CopyDirectory(ushort const *,ushort const *)
0x18002f17e  mov     ebx, eax
0x18002f180  test    eax, eax
0x18002f182  js      short loc_18002F18D
0x18002f184  inc     edi
0x18002f186  cmp     edi, 3
0x18002f189  jb      short loc_18002F151
0x18002f18b  jmp     short loc_18002F1E7
0x18002f18d  mov     r9, rsi
0x18002f190  mov     [rsp+268h+var_248], eax
0x18002f194  lea     r8, [rsp+268h+Dst]
0x18002f199  mov     ecx, 2; unsigned __int8
0x18002f19e  lea     rdx, aFailedToCopyDi; "Failed to copy directory from %s to %s!"...
0x18002f1a5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f1aa  jmp     short loc_18002F1E7
0x18002f1ac  mov     ebx, 8007007Ah
0x18002f1b1  lea     rdx, aFailedToExpand_2; "Failed to expand log file share path %s"...
0x18002f1b8  jmp     short loc_18002F1D6
0x18002f1ba  call    cs:__imp_GetLastError
0x18002f1c0  mov     ebx, eax
0x18002f1c2  test    eax, eax
0x18002f1c4  jle     short loc_18002F1CF
0x18002f1c6  movzx   ebx, ax
0x18002f1c9  or      ebx, 80070000h
0x18002f1cf  lea     rdx, aFailedToExpand_0; "Failed to expand log file share path %s"...
0x18002f1d6  mov     r8, [r14+rdi*8]
0x18002f1da  mov     r9d, ebx
0x18002f1dd  mov     ecx, 2; unsigned __int8
0x18002f1e2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f1e7  mov     eax, ebx
0x18002f1e9  mov     rcx, [rsp+268h+var_28]
0x18002f1f1  xor     rcx, rsp; StackCookie
0x18002f1f4  call    __security_check_cookie
0x18002f1f9  lea     r11, [rsp+268h+var_18]
0x18002f201  mov     rbx, [r11+20h]
0x18002f205  mov     rbp, [r11+38h]
0x18002f209  mov     rsp, r11
0x18002f20c  pop     r14
0x18002f20e  pop     rdi
0x18002f20f  pop     rsi
0x18002f210  retn
```
