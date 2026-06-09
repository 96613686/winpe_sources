# FwOpenPort::get_Scope(NET_FW_SCOPE_ *)

- ea: `0x18003c4a0`
- end: `0x18003c55b`
- name: `?get_Scope@FwOpenPort@@UEAAJPEAW4NET_FW_SCOPE_@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, enum NET_FW_SCOPE_ *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18003c4a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c4b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c4b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c526`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c526`
- `fwbase!FwReportReturnError` at `0x18003c4d4`
- `fwbase!FwReportReturnError` at `0x18003c53f`
- `fwbase!FwReportReturnError` at `0x18003c4d4`
- `fwbase!FwReportReturnError` at `0x18003c53f`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x18003c513`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x18003c513`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c4f3`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c4f3`

## string_xrefs

- `0x18003c4cd`: `FwOpenPort::get_Scope`
- `0x18003c538`: `FwOpenPort::get_Scope`

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
0x18003c4a0  push    rbx
0x18003c4a2  push    rbp
0x18003c4a3  push    rsi
0x18003c4a4  push    rdi
0x18003c4a5  push    r14
0x18003c4a7  sub     rsp, 20h
0x18003c4ab  mov     rdi, rcx
0x18003c4ae  mov     r14, rdx
0x18003c4b1  add     rcx, 10h; lpCriticalSection
0x18003c4b5  call    cs:__imp_EnterCriticalSection
0x18003c4bc  nop     dword ptr [rax+rax+00h]
0x18003c4c1  test    r14, r14
0x18003c4c4  jnz     short loc_18003C4E2
0x18003c4c6  mov     ebx, 80004003h
0x18003c4cb  mov     edx, ebx
0x18003c4cd  lea     rcx, aFwopenportGetS; "FwOpenPort::get_Scope"
0x18003c4d4  call    cs:__imp_FwReportReturnError
0x18003c4db  nop     dword ptr [rax+rax+00h]
0x18003c4e0  jmp     short loc_18003C522
0x18003c4e2  xor     ebx, ebx
0x18003c4e4  lea     rsi, [rdi+48h]
0x18003c4e8  cmp     [rsi], rbx
0x18003c4eb  jnz     short loc_18003C509
0x18003c4ed  mov     edx, [rdi+40h]
0x18003c4f0  mov     rcx, rsi
0x18003c4f3  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003c4fa  nop     dword ptr [rax+rax+00h]
0x18003c4ff  mov     ebx, eax
0x18003c501  test    eax, eax
0x18003c503  jns     short loc_18003C509
0x18003c505  mov     edx, eax
0x18003c507  jmp     short loc_18003C4CD
0x18003c509  mov     rcx, [rsi]
0x18003c50c  add     rcx, 0B0h
0x18003c513  call    cs:__imp_GetOpenPortOrAuthAppAddrScope
0x18003c51a  nop     dword ptr [rax+rax+00h]
0x18003c51f  mov     [r14], eax
0x18003c522  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003c526  call    cs:__imp_LeaveCriticalSection
0x18003c52d  nop     dword ptr [rax+rax+00h]
0x18003c532  test    ebx, ebx
0x18003c534  jns     short loc_18003C54D
0x18003c536  mov     edx, ebx
0x18003c538  lea     rcx, aFwopenportGetS; "FwOpenPort::get_Scope"
0x18003c53f  call    cs:__imp_FwReportReturnError
0x18003c546  nop     dword ptr [rax+rax+00h]
0x18003c54b  mov     ebx, eax
0x18003c54d  mov     eax, ebx
0x18003c54f  add     rsp, 20h
0x18003c553  pop     r14
0x18003c555  pop     rdi
0x18003c556  pop     rsi
0x18003c557  pop     rbp
0x18003c558  pop     rbx
0x18003c559  retn
```
