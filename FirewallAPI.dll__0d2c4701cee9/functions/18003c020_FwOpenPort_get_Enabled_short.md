# FwOpenPort::get_Enabled(short *)

- ea: `0x18003c020`
- end: `0x18003c0e2`
- name: `?get_Enabled@FwOpenPort@@UEAAJPEAF@Z`
- size: `194`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18003c020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c035`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c035`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c0ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c0ad`
- `fwbase!FwReportReturnError` at `0x18003c054`
- `fwbase!FwReportReturnError` at `0x18003c0c6`
- `fwbase!FwReportReturnError` at `0x18003c054`
- `fwbase!FwReportReturnError` at `0x18003c0c6`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c073`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c073`

## string_xrefs

- `0x18003c04d`: `FwOpenPort::get_Enabled`
- `0x18003c0bf`: `FwOpenPort::get_Enabled`

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
0x18003c020  push    rbx
0x18003c022  push    rbp
0x18003c023  push    rsi
0x18003c024  push    rdi
0x18003c025  push    r14
0x18003c027  sub     rsp, 20h
0x18003c02b  mov     rsi, rcx
0x18003c02e  mov     r14, rdx
0x18003c031  add     rcx, 10h; lpCriticalSection
0x18003c035  call    cs:__imp_EnterCriticalSection
0x18003c03c  nop     dword ptr [rax+rax+00h]
0x18003c041  test    r14, r14
0x18003c044  jnz     short loc_18003C062
0x18003c046  mov     ebx, 80004003h
0x18003c04b  mov     edx, ebx
0x18003c04d  lea     rcx, aFwopenportGetE; "FwOpenPort::get_Enabled"
0x18003c054  call    cs:__imp_FwReportReturnError
0x18003c05b  nop     dword ptr [rax+rax+00h]
0x18003c060  jmp     short loc_18003C0A9
0x18003c062  xor     ebx, ebx
0x18003c064  lea     rdi, [rsi+48h]
0x18003c068  cmp     [rdi], rbx
0x18003c06b  jnz     short loc_18003C089
0x18003c06d  mov     edx, [rsi+40h]
0x18003c070  mov     rcx, rdi
0x18003c073  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003c07a  nop     dword ptr [rax+rax+00h]
0x18003c07f  mov     ebx, eax
0x18003c081  test    eax, eax
0x18003c083  jns     short loc_18003C089
0x18003c085  mov     edx, eax
0x18003c087  jmp     short loc_18003C04D
0x18003c089  mov     rax, [rdi]
0x18003c08c  test    byte ptr [rax+124h], 1
0x18003c093  jz      short loc_18003C0A3
0x18003c095  cmp     dword ptr [rax+120h], 3
0x18003c09c  jnz     short loc_18003C0A3
0x18003c09e  or      eax, 0FFFFFFFFh
0x18003c0a1  jmp     short loc_18003C0A5
0x18003c0a3  xor     eax, eax
0x18003c0a5  mov     [r14], ax
0x18003c0a9  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003c0ad  call    cs:__imp_LeaveCriticalSection
0x18003c0b4  nop     dword ptr [rax+rax+00h]
0x18003c0b9  test    ebx, ebx
0x18003c0bb  jns     short loc_18003C0D4
0x18003c0bd  mov     edx, ebx
0x18003c0bf  lea     rcx, aFwopenportGetE; "FwOpenPort::get_Enabled"
0x18003c0c6  call    cs:__imp_FwReportReturnError
0x18003c0cd  nop     dword ptr [rax+rax+00h]
0x18003c0d2  mov     ebx, eax
0x18003c0d4  mov     eax, ebx
0x18003c0d6  add     rsp, 20h
0x18003c0da  pop     r14
0x18003c0dc  pop     rdi
0x18003c0dd  pop     rsi
0x18003c0de  pop     rbp
0x18003c0df  pop     rbx
0x18003c0e0  retn
```
