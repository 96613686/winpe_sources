# BfeDriverOpenDevice

- ea: `0x18006cb0c`
- end: `0x18006cbd2`
- name: `BfeDriverOpenDevice`
- size: `198`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006ca34`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x1800389fc`
- `0x1800575c4`
- `0x18006cb0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006cb84`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006cb84`

## string_xrefs

- `0x18006cb9c`: `CreateFileW`
- `0x18006cbb0`: `BfeDriverOpenDevice`

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
0x18006cb0c  mov     [rsp+arg_0], rbx
0x18006cb11  mov     [rsp+arg_8], rsi
0x18006cb16  push    rdi
0x18006cb17  sub     rsp, 40h
0x18006cb1b  xor     ebx, ebx
0x18006cb1d  mov     rdi, rdx
0x18006cb20  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18006cb24  mov     rsi, rcx
0x18006cb27  jz      short loc_18006CB2E
0x18006cb29  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006cb2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cb35  lea     rax, WPP_GLOBAL_Control
0x18006cb3c  cmp     rcx, rax
0x18006cb3f  jz      short loc_18006CB65
0x18006cb41  cmp     byte ptr [rcx+19h], 4
0x18006cb45  jb      short loc_18006CB65
0x18006cb47  test    byte ptr [rcx+1Ch], 2
0x18006cb4b  jz      short loc_18006CB65
0x18006cb4d  mov     rcx, [rcx+10h]
0x18006cb51  lea     r8, WPP_7ea328005f0c3ef97369fc26caca0b97_Traceguids
0x18006cb58  mov     edx, 10h
0x18006cb5d  mov     r9, rsi
0x18006cb60  call    WPP_SF_S
0x18006cb65  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18006cb6a  xor     r9d, r9d; lpSecurityAttributes
0x18006cb6d  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18006cb71  xor     r8d, r8d; dwShareMode
0x18006cb74  mov     edx, 0C0000000h; dwDesiredAccess
0x18006cb79  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18006cb81  mov     rcx, rsi; lpFileName
0x18006cb84  call    cs:__imp_CreateFileW
0x18006cb8a  mov     [rdi], rax
0x18006cb8d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006cb91  jnz     short loc_18006CBBF
0x18006cb93  call    cs:__imp_GetLastError
0x18006cb99  mov     r8d, eax
0x18006cb9c  lea     rdx, aCreatefilew; "CreateFileW"
0x18006cba3  call    WfpReportSysErrorAsWinError
0x18006cba8  mov     rbx, rax
0x18006cbab  test    rax, rax
0x18006cbae  jz      short loc_18006CBBF
0x18006cbb0  lea     rdx, aBfedriveropend; "BfeDriverOpenDevice"
0x18006cbb7  mov     rcx, rax
0x18006cbba  call    WfpReportError
0x18006cbbf  mov     rsi, [rsp+48h+arg_8]
0x18006cbc4  mov     rax, rbx
0x18006cbc7  mov     rbx, [rsp+48h+arg_0]
0x18006cbcc  add     rsp, 40h
0x18006cbd0  pop     rdi
0x18006cbd1  retn
```
