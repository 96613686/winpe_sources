# Service::LogError(ushort const *)

- ea: `0x180007f2c`
- end: `0x18000800a`
- name: `?LogError@Service@@QEAAXPEBG@Z`
- size: `222`
- prototype: `void __fastcall(Service *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180006670`
- `0x180007eb8`

## callees

- `0x180001364`
- `0x180007f2c`
- `0x180008a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f4e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180007fe7`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180007fe7`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180007f77`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180007f77`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180007fde`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180007fde`

## pseudocode

```c
void __fastcall Service::LogError(Service *this, const unsigned __int16 *a2)
{
  DWORD LastError; // esi
  HANDLE v4; // rbx
  LPCWSTR Strings[2]; // [rsp+50h] [rbp-E8h] BYREF
  unsigned __int16 v6[80]; // [rsp+60h] [rbp-D8h] BYREF

  LastError = GetLastError();
  if ( !byte_18000F664 )
  {
    *(_OWORD *)Strings = 0;
    v4 = RegisterEventSourceW(0, L"WarpJITSvc");
    if ( v4 )
    {
      StringCchPrintfW(v6, 0x50u, L"%s failed with %d", a2, LastError);
      Strings[0] = L"WarpJITSvc";
      Strings[1] = v6;
      ReportEventW(v4, 1u, 0, 0, 0, 2u, 0, Strings, 0);
      DeregisterEventSource(v4);
    }
  }
}

```

## disassembly

```asm
0x180007f2c  push    rbx
0x180007f2e  push    rsi
0x180007f2f  push    rdi
0x180007f30  push    r14
0x180007f32  sub     rsp, 118h
0x180007f39  mov     rax, cs:__security_cookie
0x180007f40  xor     rax, rsp
0x180007f43  mov     [rsp+138h+var_38], rax
0x180007f4b  mov     rdi, rdx
0x180007f4e  call    cs:__imp_GetLastError
0x180007f54  cmp     cs:byte_18000F664, 0
0x180007f5b  mov     esi, eax
0x180007f5d  jnz     loc_180007FED
0x180007f63  xorps   xmm0, xmm0
0x180007f66  lea     r14, SourceName; "WarpJITSvc"
0x180007f6d  mov     rdx, r14; lpSourceName
0x180007f70  xor     ecx, ecx; lpUNCServerName
0x180007f72  movups  xmmword ptr [rsp+138h+Strings], xmm0
0x180007f77  call    cs:__imp_RegisterEventSourceW
0x180007f7d  mov     rbx, rax
0x180007f80  test    rax, rax
0x180007f83  jz      short loc_180007FED
0x180007f85  mov     r9, rdi
0x180007f88  mov     dword ptr [rsp+138h+lpUserSid], esi
0x180007f8c  lea     r8, aSFailedWithD; "%s failed with %d"
0x180007f93  mov     edx, 50h ; 'P'; unsigned __int64
0x180007f98  lea     rcx, [rsp+138h+var_D8]; unsigned __int16 *
0x180007f9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007fa2  xor     r8d, r8d; wCategory
0x180007fa5  mov     [rsp+138h+Strings], r14
0x180007faa  mov     [rsp+138h+lpRawData], r8; lpRawData
0x180007faf  lea     rax, [rsp+138h+var_D8]
0x180007fb4  mov     [rsp+138h+Strings+8], rax
0x180007fb9  xor     r9d, r9d; dwEventID
0x180007fbc  lea     rax, [rsp+138h+Strings]
0x180007fc1  mov     rcx, rbx; hEventLog
0x180007fc4  mov     [rsp+138h+lpStrings], rax; lpStrings
0x180007fc9  lea     edx, [r8+1]; wType
0x180007fcd  mov     [rsp+138h+dwDataSize], r8d; dwDataSize
0x180007fd2  mov     [rsp+138h+wNumStrings], 2; wNumStrings
0x180007fd9  mov     [rsp+138h+lpUserSid], r8; lpUserSid
0x180007fde  call    cs:__imp_ReportEventW
0x180007fe4  mov     rcx, rbx; hEventLog
0x180007fe7  call    cs:__imp_DeregisterEventSource
0x180007fed  mov     rcx, [rsp+138h+var_38]
0x180007ff5  xor     rcx, rsp; StackCookie
0x180007ff8  call    __security_check_cookie
0x180007ffd  add     rsp, 118h
0x180008004  pop     r14
0x180008006  pop     rdi
0x180008007  pop     rsi
0x180008008  pop     rbx
0x180008009  retn
```
