# BfeDriverOpenDevice

- ea: `0x18006f1d0`
- end: `0x18006f2a3`
- name: `BfeDriverOpenDevice`
- size: `211`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006f0f8`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180037494`
- `0x1800592f4`
- `0x18006f1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f25d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f25d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f248`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f248`

## string_xrefs

- `0x18006f26c`: `CreateFileW`
- `0x18006f280`: `BfeDriverOpenDevice`

## pseudocode

```c
__int64 __fastcall BfeDriverOpenDevice(LPCWSTR lpFileName, _QWORD *a2)
{
  __int64 v2; // rbx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  __int64 v7; // rcx
  __int64 v8; // rax

  v2 = 0;
  if ( *a2 != -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_7ea328005f0c3ef97369fc26caca0b97_Traceguids, lpFileName);
  }
  FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 3u, 0, 0);
  *a2 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = WfpReportSysErrorAsWinError(v7, "CreateFileW", LastError);
    v2 = v8;
    if ( v8 )
      WfpReportError(v8, "BfeDriverOpenDevice");
  }
  return v2;
}

```

## disassembly

```asm
0x18006f1d0  mov     [rsp+arg_0], rbx
0x18006f1d5  mov     [rsp+arg_8], rsi
0x18006f1da  push    rdi
0x18006f1db  sub     rsp, 40h
0x18006f1df  xor     ebx, ebx
0x18006f1e1  mov     rdi, rdx
0x18006f1e4  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18006f1e8  mov     rsi, rcx
0x18006f1eb  jz      short loc_18006F1F2
0x18006f1ed  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "*device == INVALID_HANDLE_VALUE")
0x18006f1f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f1f9  lea     rax, WPP_GLOBAL_Control
0x18006f200  cmp     rcx, rax
0x18006f203  jz      short loc_18006F229
0x18006f205  cmp     byte ptr [rcx+19h], 4
0x18006f209  jb      short loc_18006F229
0x18006f20b  test    byte ptr [rcx+1Ch], 2
0x18006f20f  jz      short loc_18006F229
0x18006f211  mov     rcx, [rcx+10h]
0x18006f215  lea     r8, WPP_7ea328005f0c3ef97369fc26caca0b97_Traceguids
0x18006f21c  mov     edx, 10h
0x18006f221  mov     r9, rsi
0x18006f224  call    WPP_SF_S
0x18006f229  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18006f22e  xor     r9d, r9d; lpSecurityAttributes
0x18006f231  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18006f235  xor     r8d, r8d; dwShareMode
0x18006f238  mov     edx, 0C0000000h; dwDesiredAccess
0x18006f23d  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18006f245  mov     rcx, rsi; lpFileName
0x18006f248  call    cs:__imp_CreateFileW
0x18006f24f  nop     dword ptr [rax+rax+00h]
0x18006f254  mov     [rdi], rax
0x18006f257  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f25b  jnz     short loc_18006F28F
0x18006f25d  call    cs:__imp_GetLastError
0x18006f264  nop     dword ptr [rax+rax+00h]
0x18006f269  mov     r8d, eax
0x18006f26c  lea     rdx, aCreatefilew; "CreateFileW"
0x18006f273  call    WfpReportSysErrorAsWinError
0x18006f278  mov     rbx, rax
0x18006f27b  test    rax, rax
0x18006f27e  jz      short loc_18006F28F
0x18006f280  lea     rdx, aBfedriveropend; "BfeDriverOpenDevice"
0x18006f287  mov     rcx, rax
0x18006f28a  call    WfpReportError
0x18006f28f  mov     rsi, [rsp+48h+arg_8]
0x18006f294  mov     rax, rbx
0x18006f297  mov     rbx, [rsp+48h+arg_0]
0x18006f29c  add     rsp, 40h
0x18006f2a0  pop     rdi
0x18006f2a1  retn
```
