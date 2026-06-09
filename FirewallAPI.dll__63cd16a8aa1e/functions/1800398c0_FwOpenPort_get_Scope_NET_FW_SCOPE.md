# FwOpenPort::get_Scope(NET_FW_SCOPE_ *)

- ea: `0x1800398c0`
- end: `0x180039956`
- name: `?get_Scope@FwOpenPort@@UEAAJPEAW4NET_FW_SCOPE_@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, enum NET_FW_SCOPE_ *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800398c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800398d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800398d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003992e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003992e`
- `fwbase!FwReportReturnError` at `0x1800398ee`
- `fwbase!FwReportReturnError` at `0x180039941`
- `fwbase!FwReportReturnError` at `0x1800398ee`
- `fwbase!FwReportReturnError` at `0x180039941`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180039921`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180039921`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039907`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039907`

## string_xrefs

- `0x1800398e7`: `FwOpenPort::get_Scope`
- `0x18003993a`: `FwOpenPort::get_Scope`

## pseudocode

```c
__int64 __fastcall FwOpenPort::get_Scope(FwOpenPort *this, enum NET_FW_SCOPE_ *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int DefaultOpenPortRule; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwOpenPort::get_Scope", v5);
    goto LABEL_8;
  }
  v4 = 0;
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
  *a2 = GetOpenPortOrAuthAppAddrScope(*((_QWORD *)this + 9) + 176LL);
LABEL_8:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::get_Scope", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800398c0  push    rbx
0x1800398c2  push    rbp
0x1800398c3  push    rsi
0x1800398c4  push    rdi
0x1800398c5  push    r14
0x1800398c7  sub     rsp, 20h
0x1800398cb  mov     rdi, rcx
0x1800398ce  mov     r14, rdx
0x1800398d1  add     rcx, 10h; lpCriticalSection
0x1800398d5  call    cs:__imp_EnterCriticalSection
0x1800398db  test    r14, r14
0x1800398de  jnz     short loc_1800398F6
0x1800398e0  mov     ebx, 80004003h
0x1800398e5  mov     edx, ebx
0x1800398e7  lea     rcx, aFwopenportGetS; "FwOpenPort::get_Scope"
0x1800398ee  call    cs:__imp_FwReportReturnError
0x1800398f4  jmp     short loc_18003992A
0x1800398f6  xor     ebx, ebx
0x1800398f8  lea     rsi, [rdi+48h]
0x1800398fc  cmp     [rsi], rbx
0x1800398ff  jnz     short loc_180039917
0x180039901  mov     edx, [rdi+40h]
0x180039904  mov     rcx, rsi
0x180039907  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003990d  mov     ebx, eax
0x18003990f  test    eax, eax
0x180039911  jns     short loc_180039917
0x180039913  mov     edx, eax
0x180039915  jmp     short loc_1800398E7
0x180039917  mov     rcx, [rsi]
0x18003991a  add     rcx, 0B0h
0x180039921  call    cs:__imp_GetOpenPortOrAuthAppAddrScope
0x180039927  mov     [r14], eax
0x18003992a  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003992e  call    cs:__imp_LeaveCriticalSection
0x180039934  test    ebx, ebx
0x180039936  jns     short loc_180039949
0x180039938  mov     edx, ebx
0x18003993a  lea     rcx, aFwopenportGetS; "FwOpenPort::get_Scope"
0x180039941  call    cs:__imp_FwReportReturnError
0x180039947  mov     ebx, eax
0x180039949  mov     eax, ebx
0x18003994b  add     rsp, 20h
0x18003994f  pop     r14
0x180039951  pop     rdi
0x180039952  pop     rsi
0x180039953  pop     rbp
0x180039954  pop     rbx
0x180039955  retn
```
