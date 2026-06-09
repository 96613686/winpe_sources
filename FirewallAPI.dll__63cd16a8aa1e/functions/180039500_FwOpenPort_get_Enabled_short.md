# FwOpenPort::get_Enabled(short *)

- ea: `0x180039500`
- end: `0x1800395a3`
- name: `?get_Enabled@FwOpenPort@@UEAAJPEAF@Z`
- size: `163`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180039500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039515`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039515`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003957b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003957b`
- `fwbase!FwReportReturnError` at `0x18003952e`
- `fwbase!FwReportReturnError` at `0x18003958e`
- `fwbase!FwReportReturnError` at `0x18003952e`
- `fwbase!FwReportReturnError` at `0x18003958e`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039547`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039547`

## string_xrefs

- `0x180039527`: `FwOpenPort::get_Enabled`
- `0x180039587`: `FwOpenPort::get_Enabled`

## pseudocode

```c
__int64 __fastcall FwOpenPort::get_Enabled(FwOpenPort *this, __int16 *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  char *v6; // rdi
  int DefaultOpenPortRule; // eax
  __int16 v8; // ax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwOpenPort::get_Enabled", v5);
    goto LABEL_12;
  }
  v4 = 0;
  v6 = (char *)this + 72;
  if ( !*((_QWORD *)this + 9) )
  {
    DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16));
    v4 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule < 0 )
    {
      v5 = (unsigned int)DefaultOpenPortRule;
      goto LABEL_3;
    }
  }
  if ( (*(_BYTE *)(*(_QWORD *)v6 + 292LL) & 1) != 0 && *(_DWORD *)(*(_QWORD *)v6 + 288LL) == 3 )
    v8 = -1;
  else
    v8 = 0;
  *a2 = v8;
LABEL_12:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::get_Enabled", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180039500  push    rbx
0x180039502  push    rbp
0x180039503  push    rsi
0x180039504  push    rdi
0x180039505  push    r14
0x180039507  sub     rsp, 20h
0x18003950b  mov     rsi, rcx
0x18003950e  mov     r14, rdx
0x180039511  add     rcx, 10h; lpCriticalSection
0x180039515  call    cs:__imp_EnterCriticalSection
0x18003951b  test    r14, r14
0x18003951e  jnz     short loc_180039536
0x180039520  mov     ebx, 80004003h
0x180039525  mov     edx, ebx
0x180039527  lea     rcx, aFwopenportGetE; "FwOpenPort::get_Enabled"
0x18003952e  call    cs:__imp_FwReportReturnError
0x180039534  jmp     short loc_180039577
0x180039536  xor     ebx, ebx
0x180039538  lea     rdi, [rsi+48h]
0x18003953c  cmp     [rdi], rbx
0x18003953f  jnz     short loc_180039557
0x180039541  mov     edx, [rsi+40h]
0x180039544  mov     rcx, rdi
0x180039547  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003954d  mov     ebx, eax
0x18003954f  test    eax, eax
0x180039551  jns     short loc_180039557
0x180039553  mov     edx, eax
0x180039555  jmp     short loc_180039527
0x180039557  mov     rax, [rdi]
0x18003955a  test    byte ptr [rax+124h], 1
0x180039561  jz      short loc_180039571
0x180039563  cmp     dword ptr [rax+120h], 3
0x18003956a  jnz     short loc_180039571
0x18003956c  or      eax, 0FFFFFFFFh
0x18003956f  jmp     short loc_180039573
0x180039571  xor     eax, eax
0x180039573  mov     [r14], ax
0x180039577  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003957b  call    cs:__imp_LeaveCriticalSection
0x180039581  test    ebx, ebx
0x180039583  jns     short loc_180039596
0x180039585  mov     edx, ebx
0x180039587  lea     rcx, aFwopenportGetE; "FwOpenPort::get_Enabled"
0x18003958e  call    cs:__imp_FwReportReturnError
0x180039594  mov     ebx, eax
0x180039596  mov     eax, ebx
0x180039598  add     rsp, 20h
0x18003959c  pop     r14
0x18003959e  pop     rdi
0x18003959f  pop     rsi
0x1800395a0  pop     rbp
0x1800395a1  pop     rbx
0x1800395a2  retn
```
