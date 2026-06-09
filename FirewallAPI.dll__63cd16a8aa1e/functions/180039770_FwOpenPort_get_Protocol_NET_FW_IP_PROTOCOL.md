# FwOpenPort::get_Protocol(NET_FW_IP_PROTOCOL_ *)

- ea: `0x180039770`
- end: `0x180039802`
- name: `?get_Protocol@FwOpenPort@@UEAAJPEAW4NET_FW_IP_PROTOCOL_@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, enum NET_FW_IP_PROTOCOL_ *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180039770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039786`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039786`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800397dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800397dc`
- `fwbase!FwReportReturnError` at `0x18003979f`
- `fwbase!FwReportReturnError` at `0x1800397ef`
- `fwbase!FwReportReturnError` at `0x18003979f`
- `fwbase!FwReportReturnError` at `0x1800397ef`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x1800397d1`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x1800397d1`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x1800397b7`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x1800397b7`

## string_xrefs

- `0x180039798`: `FwOpenPort::get_Protocol`
- `0x1800397e8`: `FwOpenPort::get_Protocol`

## pseudocode

```c
__int64 __fastcall FwOpenPort::get_Protocol(FwOpenPort *this, enum NET_FW_IP_PROTOCOL_ *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v5; // ebx
  __int64 v6; // rdx
  char *v7; // rdi
  int DefaultOpenPortRule; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a2 )
  {
    v5 = -2147467261;
    v6 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwOpenPort::get_Protocol", v6);
    goto LABEL_8;
  }
  v7 = (char *)this + 72;
  if ( !*((_QWORD *)this + 9) )
  {
    DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16));
    v5 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule < 0 )
    {
      v6 = (unsigned int)DefaultOpenPortRule;
      goto LABEL_3;
    }
  }
  v5 = FwWfProtocolToICFProtocol(*(unsigned __int16 *)(*(_QWORD *)v7 + 48LL), a2);
LABEL_8:
  LeaveCriticalSection(v2);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::get_Protocol", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180039770  push    rbx
0x180039772  push    rbp
0x180039773  push    rsi
0x180039774  push    rdi
0x180039775  sub     rsp, 28h
0x180039779  lea     rsi, [rcx+10h]
0x18003977d  mov     rbx, rcx
0x180039780  mov     rcx, rsi; lpCriticalSection
0x180039783  mov     rbp, rdx
0x180039786  call    cs:__imp_EnterCriticalSection
0x18003978c  test    rbp, rbp
0x18003978f  jnz     short loc_1800397A7
0x180039791  mov     ebx, 80004003h
0x180039796  mov     edx, ebx
0x180039798  lea     rcx, aFwopenportGetP; "FwOpenPort::get_Protocol"
0x18003979f  call    cs:__imp_FwReportReturnError
0x1800397a5  jmp     short loc_1800397D9
0x1800397a7  lea     rdi, [rbx+48h]
0x1800397ab  cmp     qword ptr [rdi], 0
0x1800397af  jnz     short loc_1800397C7
0x1800397b1  mov     edx, [rbx+40h]
0x1800397b4  mov     rcx, rdi
0x1800397b7  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x1800397bd  mov     ebx, eax
0x1800397bf  test    eax, eax
0x1800397c1  jns     short loc_1800397C7
0x1800397c3  mov     edx, eax
0x1800397c5  jmp     short loc_180039798
0x1800397c7  mov     rcx, [rdi]
0x1800397ca  mov     rdx, rbp
0x1800397cd  movzx   ecx, word ptr [rcx+30h]
0x1800397d1  call    cs:__imp_FwWfProtocolToICFProtocol
0x1800397d7  mov     ebx, eax
0x1800397d9  mov     rcx, rsi; lpCriticalSection
0x1800397dc  call    cs:__imp_LeaveCriticalSection
0x1800397e2  test    ebx, ebx
0x1800397e4  jns     short loc_1800397F7
0x1800397e6  mov     edx, ebx
0x1800397e8  lea     rcx, aFwopenportGetP; "FwOpenPort::get_Protocol"
0x1800397ef  call    cs:__imp_FwReportReturnError
0x1800397f5  mov     ebx, eax
0x1800397f7  mov     eax, ebx
0x1800397f9  add     rsp, 28h
0x1800397fd  pop     rdi
0x1800397fe  pop     rsi
0x1800397ff  pop     rbp
0x180039800  pop     rbx
0x180039801  retn
```
