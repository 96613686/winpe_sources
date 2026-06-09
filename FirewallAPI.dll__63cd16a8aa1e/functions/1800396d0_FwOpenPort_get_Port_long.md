# FwOpenPort::get_Port(long *)

- ea: `0x1800396d0`
- end: `0x180039760`
- name: `?get_Port@FwOpenPort@@UEAAJPEAJ@Z`
- size: `144`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800396d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800396e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800396e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039738`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039738`
- `fwbase!FwReportReturnError` at `0x1800396fe`
- `fwbase!FwReportReturnError` at `0x18003974b`
- `fwbase!FwReportReturnError` at `0x1800396fe`
- `fwbase!FwReportReturnError` at `0x18003974b`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039717`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039717`

## string_xrefs

- `0x1800396f7`: `FwOpenPort::get_Port`
- `0x180039744`: `FwOpenPort::get_Port`

## pseudocode

```c
__int64 __fastcall FwOpenPort::get_Port(FwOpenPort *this, int *a2)
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
    FwReportReturnError("FwOpenPort::get_Port", v5);
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
  *a2 = **(unsigned __int16 **)(*((_QWORD *)this + 9) + 72LL);
LABEL_8:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::get_Port", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800396d0  push    rbx
0x1800396d2  push    rbp
0x1800396d3  push    rsi
0x1800396d4  push    rdi
0x1800396d5  push    r14
0x1800396d7  sub     rsp, 20h
0x1800396db  mov     rdi, rcx
0x1800396de  mov     r14, rdx
0x1800396e1  add     rcx, 10h; lpCriticalSection
0x1800396e5  call    cs:__imp_EnterCriticalSection
0x1800396eb  test    r14, r14
0x1800396ee  jnz     short loc_180039706
0x1800396f0  mov     ebx, 80004003h
0x1800396f5  mov     edx, ebx
0x1800396f7  lea     rcx, aFwopenportGetP_0; "FwOpenPort::get_Port"
0x1800396fe  call    cs:__imp_FwReportReturnError
0x180039704  jmp     short loc_180039734
0x180039706  xor     ebx, ebx
0x180039708  lea     rsi, [rdi+48h]
0x18003970c  cmp     [rsi], rbx
0x18003970f  jnz     short loc_180039727
0x180039711  mov     edx, [rdi+40h]
0x180039714  mov     rcx, rsi
0x180039717  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003971d  mov     ebx, eax
0x18003971f  test    eax, eax
0x180039721  jns     short loc_180039727
0x180039723  mov     edx, eax
0x180039725  jmp     short loc_1800396F7
0x180039727  mov     rax, [rsi]
0x18003972a  mov     rdx, [rax+48h]
0x18003972e  movzx   eax, word ptr [rdx]
0x180039731  mov     [r14], eax
0x180039734  lea     rcx, [rdi+10h]; lpCriticalSection
0x180039738  call    cs:__imp_LeaveCriticalSection
0x18003973e  test    ebx, ebx
0x180039740  jns     short loc_180039753
0x180039742  mov     edx, ebx
0x180039744  lea     rcx, aFwopenportGetP_0; "FwOpenPort::get_Port"
0x18003974b  call    cs:__imp_FwReportReturnError
0x180039751  mov     ebx, eax
0x180039753  mov     eax, ebx
0x180039755  add     rsp, 20h
0x180039759  pop     r14
0x18003975b  pop     rdi
0x18003975c  pop     rsi
0x18003975d  pop     rbp
0x18003975e  pop     rbx
0x18003975f  retn
```
