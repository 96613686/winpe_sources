# BfeFeInit

- ea: `0x1800695ec`
- end: `0x1800696c2`
- name: `BfeFeInit`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f520`

## callees

- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x180058b30`
- `0x1800695ec`
- `0x18006979c`
- `0x180077e8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006965d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069621`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069621`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180069653`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180069653`

## string_xrefs

- `0x180069666`: `CreateWellKnownSid`

## pseudocode

```c
__int64 BfeFeInit()
{
  __int64 v0; // rbx
  HLOCAL v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rax
  DWORD LastError; // eax
  __int64 v5; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  SIZE_T uBytes; // [rsp+20h] [rbp-18h] BYREF

  LODWORD(uBytes) = 68;
  v0 = FeInit(99);
  if ( v0 )
    goto LABEL_7;
  v1 = LocalAlloc(0, (unsigned int)uBytes);
  *(_QWORD *)&MEMORY[0x1800EF094][79] = v1;
  if ( v1 )
  {
    if ( CreateWellKnownSid(WinNullSid, 0, v1, (DWORD *)&uBytes) )
    {
      if ( (qword_1800F2668[376] & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = qword_1800F2668[376] & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline();
      MEMORY[0x1800EF094][77] = IsEnabledDeviceUsageNoInline != 0;
      return v0;
    }
    LastError = GetLastError();
    v3 = WfpReportSysErrorAsWinError(v5, "CreateWellKnownSid", LastError);
  }
  else
  {
    v3 = WfpReportSysErrorAsNtStatus(v2, "LocalAlloc", 3221225495LL);
  }
  v0 = v3;
  if ( v3 )
LABEL_7:
    WfpReportError(v0, "BfeFeInit");
  return v0;
}

```

## disassembly

```asm
0x1800695ec  push    rbx
0x1800695ee  sub     rsp, 30h
0x1800695f2  mov     rax, cs:__security_cookie
0x1800695f9  xor     rax, rsp
0x1800695fc  mov     [rsp+38h+var_10], rax
0x180069601  mov     ecx, 63h ; 'c'
0x180069606  mov     dword ptr [rsp+38h+uBytes], 44h ; 'D'
0x18006960e  call    FeInit
0x180069613  mov     rbx, rax
0x180069616  test    rax, rax
0x180069619  jnz     short loc_18006967A
0x18006961b  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x18006961f  xor     ecx, ecx; uFlags
0x180069621  call    cs:__imp_LocalAlloc
0x180069627  mov     cs:1800EF1D0h, rax
0x18006962e  test    rax, rax
0x180069631  jnz     short loc_180069647
0x180069633  mov     r8d, 0C0000017h
0x180069639  lea     rdx, aLocalalloc; "LocalAlloc"
0x180069640  call    WfpReportSysErrorAsNtStatus
0x180069645  jmp     short loc_180069672
0x180069647  lea     r9, [rsp+38h+uBytes]; cbSid
0x18006964c  mov     r8, rax; pSid
0x18006964f  xor     edx, edx; DomainSid
0x180069651  xor     ecx, ecx; WellKnownSidType
0x180069653  call    cs:__imp_CreateWellKnownSid
0x180069659  test    eax, eax
0x18006965b  jnz     short loc_18006969F
0x18006965d  call    cs:__imp_GetLastError
0x180069663  mov     r8d, eax
0x180069666  lea     rdx, aCreatewellknow; "CreateWellKnownSid"
0x18006966d  call    WfpReportSysErrorAsWinError
0x180069672  mov     rbx, rax
0x180069675  test    rax, rax
0x180069678  jz      short loc_180069689
0x18006967a  lea     rdx, aBfefeinit; "BfeFeInit"
0x180069681  mov     rcx, rbx
0x180069684  call    WfpReportError
0x180069689  mov     rax, rbx
0x18006968c  mov     rcx, [rsp+38h+var_10]
0x180069691  xor     rcx, rsp; StackCookie
0x180069694  call    __security_check_cookie
0x180069699  add     rsp, 30h
0x18006969d  pop     rbx
0x18006969e  retn
0x18006969f  mov     eax, dword ptr cs:qword_1800F2668+0BC0h
0x1800696a5  test    al, 10h
0x1800696a7  jz      short loc_1800696AE
0x1800696a9  and     eax, 1
0x1800696ac  jmp     short loc_1800696B3
0x1800696ae  call    Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline
0x1800696b3  xor     ecx, ecx
0x1800696b5  test    eax, eax
0x1800696b7  setnz   cl
0x1800696ba  mov     cs:1800EF1C8h, ecx
0x1800696c0  jmp     short loc_180069689
```
