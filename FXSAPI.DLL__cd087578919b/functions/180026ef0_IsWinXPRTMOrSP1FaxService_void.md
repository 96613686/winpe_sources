# IsWinXPRTMOrSP1FaxService(void)

- ea: `0x180026ef0`
- end: `0x1800270c9`
- name: `?IsWinXPRTMOrSP1FaxService@@YAHXZ`
- size: `473`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180026b04`

## callees

- `0x1800084ac`
- `0x18000abe4`
- `0x18000ac14`
- `0x180026ef0`
- `0x180031f94`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026f89`
- `KERNEL32!GetLastError` at `0x180026f89`
- `KERNEL32!GetSystemDirectoryW` at `0x180026f79`
- `KERNEL32!GetSystemDirectoryW` at `0x180026f79`

## pseudocode

```c
__int64 IsWinXPRTMOrSP1FaxService(void)
{
  DWORD LastError; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // r9
  int v4; // eax
  unsigned int FileVersion; // ebx
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR tstrFilename[520]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids);
  }
  if ( GetSystemDirectoryW(Buffer, 0x105u) )
  {
    v4 = StringCchPrintfW(tstrFilename, 0x208u, L"%s\\FXSSVC.EXE", Buffer);
    if ( v4 >= 0 )
    {
      FileVersion = GetFileVersion(tstrFilename);
      if ( (unsigned int)GetFileVersion(tstrFilename) )
      {
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v2 = 39;
          v3 = FileVersion;
          goto LABEL_21;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_6e3acdab872831c35b7514c03928d94f_Traceguids,
        (unsigned int)v4);
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = 37;
      v3 = LastError;
LABEL_21:
      WPP_SF_d(v1[2], v2, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids, v3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180026ef0  push    rbp
0x180026ef2  push    rbx
0x180026ef3  push    rsi
0x180026ef4  push    rdi
0x180026ef5  push    r15
0x180026ef7  lea     rbp, [rsp-570h]
0x180026eff  sub     rsp, 670h
0x180026f06  mov     rax, cs:__security_cookie
0x180026f0d  xor     rax, rsp
0x180026f10  mov     [rbp+590h+var_30], rax
0x180026f17  xorps   xmm0, xmm0
0x180026f1a  lea     rcx, [rsp+690h+Buffer]; void *
0x180026f1f  xor     edx, edx; Val
0x180026f21  mov     r8d, 20Ah; Size
0x180026f27  movdqu  [rsp+690h+var_66C], xmm0
0x180026f2d  call    memset_0
0x180026f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f39  lea     rsi, WPP_GLOBAL_Control
0x180026f40  mov     edi, 1000h
0x180026f45  mov     r15d, 5
0x180026f4b  cmp     rcx, rsi
0x180026f4e  jz      short loc_180026F6F
0x180026f50  test    [rcx+1Ch], edi
0x180026f53  jz      short loc_180026F6F
0x180026f55  cmp     [rcx+19h], r15b
0x180026f59  jb      short loc_180026F6F
0x180026f5b  mov     rcx, [rcx+10h]
0x180026f5f  lea     edx, [r15+1Fh]
0x180026f63  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180026f6a  call    WPP_SF_
0x180026f6f  mov     edx, 105h; uSize
0x180026f74  lea     rcx, [rsp+690h+Buffer]; lpBuffer
0x180026f79  call    cs:__imp_GetSystemDirectoryW
0x180026f80  nop     dword ptr [rax+rax+00h]
0x180026f85  test    eax, eax
0x180026f87  jnz     short loc_180026FBD
0x180026f89  call    cs:__imp_GetLastError
0x180026f90  nop     dword ptr [rax+rax+00h]
0x180026f95  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f9c  cmp     rcx, rsi
0x180026f9f  jz      short loc_180027011
0x180026fa1  test    [rcx+1Ch], edi
0x180026fa4  jz      short loc_180027011
0x180026fa6  mov     edx, 2
0x180026fab  cmp     [rcx+19h], dl
0x180026fae  jb      short loc_180027011
0x180026fb0  mov     edx, 25h ; '%'
0x180026fb5  mov     r9d, eax
0x180026fb8  jmp     loc_180027084
0x180026fbd  lea     r9, [rsp+690h+Buffer]
0x180026fc2  mov     edx, 208h; unsigned __int64
0x180026fc7  lea     r8, aSFxssvcExe; "%s\\FXSSVC.EXE"
0x180026fce  lea     rcx, [rbp+590h+tstrFilename]; unsigned __int16 *
0x180026fd5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026fda  test    eax, eax
0x180026fdc  jns     short loc_180027031
0x180026fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180026fe5  cmp     rcx, rsi
0x180026fe8  jz      short loc_180027011
0x180026fea  test    [rcx+1Ch], edi
0x180026fed  jz      short loc_180027011
0x180026fef  mov     edx, 2
0x180026ff4  cmp     [rcx+19h], dl
0x180026ff7  jb      short loc_180027011
0x180026ff9  mov     rcx, [rcx+10h]
0x180026ffd  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180027004  mov     edx, 26h ; '&'
0x180027009  mov     r9d, eax
0x18002700c  call    WPP_SF_d
0x180027011  xor     eax, eax
0x180027013  mov     rcx, [rbp+590h+var_30]
0x18002701a  xor     rcx, rsp; StackCookie
0x18002701d  call    __security_check_cookie
0x180027022  add     rsp, 670h
0x180027029  pop     r15
0x18002702b  pop     rdi
0x18002702c  pop     rsi
0x18002702d  pop     rbx
0x18002702e  pop     rbp
0x18002702f  retn
0x180027031  lea     rdx, [rsp+690h+var_670]
0x180027036  mov     [rsp+690h+var_670], 14h
0x18002703e  lea     rcx, [rbp+590h+tstrFilename]; lptstrFilename
0x180027045  call    GetFileVersion
0x18002704a  lea     rdx, [rsp+690h+var_670]
0x18002704f  mov     ebx, eax
0x180027051  lea     rcx, [rbp+590h+tstrFilename]; lptstrFilename
0x180027058  call    GetFileVersion
0x18002705d  test    eax, eax
0x18002705f  jz      short loc_180027099
0x180027061  mov     rcx, cs:WPP_GLOBAL_Control
0x180027068  cmp     rcx, rsi
0x18002706b  jz      short loc_180027011
0x18002706d  test    [rcx+1Ch], edi
0x180027070  jz      short loc_180027011
0x180027072  mov     edx, 2
0x180027077  cmp     [rcx+19h], dl
0x18002707a  jb      short loc_180027011
0x18002707c  mov     edx, 27h ; '''
0x180027081  mov     r9d, ebx
0x180027084  mov     rcx, [rcx+10h]
0x180027088  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x18002708f  call    WPP_SF_d
0x180027094  jmp     loc_180027011
0x180027099  cmp     r15w, word ptr [rsp+690h+var_66C+4]
0x18002709f  jnz     loc_180027011
0x1800270a5  mov     edx, 2
0x1800270aa  cmp     dx, word ptr [rsp+690h+var_66C+6]
0x1800270af  jnz     loc_180027011
0x1800270b5  xor     eax, eax
0x1800270b7  mov     ecx, 6F0h
0x1800270bc  cmp     cx, word ptr [rsp+690h+var_66C+8]
0x1800270c1  setz    al
0x1800270c4  jmp     loc_180027013
```
