# IsSupportedVersion

- ea: `0x14000b03c`
- end: `0x14000b150`
- name: `IsSupportedVersion`
- size: `276`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c55c`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001a30`
- `0x140001b40`

## import_xrefs

- `ntoskrnl!RtlVerifyVersionInfo` at `0x14000b0fd`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14000b0fd`
- `ntoskrnl!VerSetConditionMask` at `0x14000b0b6`
- `ntoskrnl!VerSetConditionMask` at `0x14000b0cd`
- `ntoskrnl!VerSetConditionMask` at `0x14000b0e4`
- `ntoskrnl!VerSetConditionMask` at `0x14000b0b6`
- `ntoskrnl!VerSetConditionMask` at `0x14000b0cd`
- `ntoskrnl!VerSetConditionMask` at `0x14000b0e4`

## pseudocode

```c
bool IsSupportedVersion()
{
  __int64 v0; // r8
  ULONGLONG v1; // rax
  ULONGLONG v2; // rax
  ULONGLONG v3; // rax
  NTSTATUS v4; // eax
  const char *v5; // r8
  bool v6; // bl
  _OSVERSIONINFOEXW VersionInfo; // [rsp+20h] [rbp-138h] BYREF

  memset(&VersionInfo, 0, sizeof(VersionInfo));
  DbgTrace(2, "UevFilter.IsSupportedVersion: Entry\n", v0);
  memset(&VersionInfo.dwPlatformId, 0, 0x10Cu);
  VersionInfo.dwOSVersionInfoSize = 276;
  VersionInfo.dwMajorVersion = 6;
  VersionInfo.dwMinorVersion = 2;
  VersionInfo.dwBuildNumber = 9200;
  v1 = VerSetConditionMask(0, 2u, 3u);
  v2 = VerSetConditionMask(v1, 1u, 3u);
  v3 = VerSetConditionMask(v2, 4u, 3u);
  v4 = RtlVerifyVersionInfo(&VersionInfo, 7u, v3);
  v5 = "true";
  v6 = v4 >= 0;
  if ( v4 < 0 )
    v5 = "false";
  DbgTraceFrmt(2u, "UevFilter.IsSupportedVersion: Exit, supported = %s.\n", v5);
  return v6;
}

```

## disassembly

```asm
0x14000b03c  push    rbx
0x14000b03e  sub     rsp, 150h
0x14000b045  mov     rax, cs:__security_cookie
0x14000b04c  xor     rax, rsp
0x14000b04f  mov     [rsp+158h+var_18], rax
0x14000b057  xor     edx, edx; Val
0x14000b059  lea     rcx, [rsp+158h+VersionInfo]; void *
0x14000b05e  mov     r8d, 11Ch; Size
0x14000b064  call    memset
0x14000b069  lea     rdx, aUevfilterIssup; "UevFilter.IsSupportedVersion: Entry\n"
0x14000b070  mov     ecx, 2
0x14000b075  call    DbgTrace
0x14000b07a  xor     edx, edx; Val
0x14000b07c  lea     rcx, [rsp+158h+VersionInfo.dwPlatformId]; void *
0x14000b081  mov     r8d, 10Ch; Size
0x14000b087  call    memset
0x14000b08c  mov     r8b, 3; Condition
0x14000b08f  mov     [rsp+158h+VersionInfo.dwOSVersionInfoSize], 114h
0x14000b097  mov     edx, 2; TypeMask
0x14000b09c  mov     [rsp+158h+VersionInfo.dwMajorVersion], 6
0x14000b0a4  xor     ecx, ecx; ConditionMask
0x14000b0a6  mov     [rsp+158h+VersionInfo.dwMinorVersion], 2
0x14000b0ae  mov     [rsp+158h+VersionInfo.dwBuildNumber], 23F0h
0x14000b0b6  call    cs:__imp_VerSetConditionMask
0x14000b0bd  nop     dword ptr [rax+rax+00h]
0x14000b0c2  mov     r8b, 3; Condition
0x14000b0c5  mov     edx, 1; TypeMask
0x14000b0ca  mov     rcx, rax; ConditionMask
0x14000b0cd  call    cs:__imp_VerSetConditionMask
0x14000b0d4  nop     dword ptr [rax+rax+00h]
0x14000b0d9  mov     r8b, 3; Condition
0x14000b0dc  mov     edx, 4; TypeMask
0x14000b0e1  mov     rcx, rax; ConditionMask
0x14000b0e4  call    cs:__imp_VerSetConditionMask
0x14000b0eb  nop     dword ptr [rax+rax+00h]
0x14000b0f0  mov     edx, 7; TypeMask
0x14000b0f5  lea     rcx, [rsp+158h+VersionInfo]; VersionInfo
0x14000b0fa  mov     r8, rax; ConditionMask
0x14000b0fd  call    cs:__imp_RtlVerifyVersionInfo
0x14000b104  nop     dword ptr [rax+rax+00h]
0x14000b109  lea     r8, aTrue; "true"
0x14000b110  mov     ecx, 2
0x14000b115  mov     ebx, eax
0x14000b117  lea     rdx, aUevfilterIssup_0; "UevFilter.IsSupportedVersion: Exit, sup"...
0x14000b11e  shr     ebx, 1Fh
0x14000b121  lea     rax, aFalse; "false"
0x14000b128  xor     bl, 1
0x14000b12b  cmovz   r8, rax
0x14000b12f  call    DbgTraceFrmt
0x14000b134  mov     al, bl
0x14000b136  mov     rcx, [rsp+158h+var_18]
0x14000b13e  xor     rcx, rsp; StackCookie
0x14000b141  call    __security_check_cookie
0x14000b146  add     rsp, 150h
0x14000b14d  pop     rbx
0x14000b14e  retn
```
