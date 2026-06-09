# FwOpenPort::get_Port(long *)

- ea: `0x18003c250`
- end: `0x18003c2ff`
- name: `?get_Port@FwOpenPort@@UEAAJPEAJ@Z`
- size: `175`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18003c250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c265`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c265`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c2ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c2ca`
- `fwbase!FwReportReturnError` at `0x18003c284`
- `fwbase!FwReportReturnError` at `0x18003c2e3`
- `fwbase!FwReportReturnError` at `0x18003c284`
- `fwbase!FwReportReturnError` at `0x18003c2e3`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c2a3`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c2a3`

## string_xrefs

- `0x18003c27d`: `FwOpenPort::get_Port`
- `0x18003c2dc`: `FwOpenPort::get_Port`

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
0x18003c250  push    rbx
0x18003c252  push    rbp
0x18003c253  push    rsi
0x18003c254  push    rdi
0x18003c255  push    r14
0x18003c257  sub     rsp, 20h
0x18003c25b  mov     rdi, rcx
0x18003c25e  mov     r14, rdx
0x18003c261  add     rcx, 10h; lpCriticalSection
0x18003c265  call    cs:__imp_EnterCriticalSection
0x18003c26c  nop     dword ptr [rax+rax+00h]
0x18003c271  test    r14, r14
0x18003c274  jnz     short loc_18003C292
0x18003c276  mov     ebx, 80004003h
0x18003c27b  mov     edx, ebx
0x18003c27d  lea     rcx, aFwopenportGetP_0; "FwOpenPort::get_Port"
0x18003c284  call    cs:__imp_FwReportReturnError
0x18003c28b  nop     dword ptr [rax+rax+00h]
0x18003c290  jmp     short loc_18003C2C6
0x18003c292  xor     ebx, ebx
0x18003c294  lea     rsi, [rdi+48h]
0x18003c298  cmp     [rsi], rbx
0x18003c29b  jnz     short loc_18003C2B9
0x18003c29d  mov     edx, [rdi+40h]
0x18003c2a0  mov     rcx, rsi
0x18003c2a3  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003c2aa  nop     dword ptr [rax+rax+00h]
0x18003c2af  mov     ebx, eax
0x18003c2b1  test    eax, eax
0x18003c2b3  jns     short loc_18003C2B9
0x18003c2b5  mov     edx, eax
0x18003c2b7  jmp     short loc_18003C27D
0x18003c2b9  mov     rax, [rsi]
0x18003c2bc  mov     rdx, [rax+48h]
0x18003c2c0  movzx   eax, word ptr [rdx]
0x18003c2c3  mov     [r14], eax
0x18003c2c6  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003c2ca  call    cs:__imp_LeaveCriticalSection
0x18003c2d1  nop     dword ptr [rax+rax+00h]
0x18003c2d6  test    ebx, ebx
0x18003c2d8  jns     short loc_18003C2F1
0x18003c2da  mov     edx, ebx
0x18003c2dc  lea     rcx, aFwopenportGetP_0; "FwOpenPort::get_Port"
0x18003c2e3  call    cs:__imp_FwReportReturnError
0x18003c2ea  nop     dword ptr [rax+rax+00h]
0x18003c2ef  mov     ebx, eax
0x18003c2f1  mov     eax, ebx
0x18003c2f3  add     rsp, 20h
0x18003c2f7  pop     r14
0x18003c2f9  pop     rdi
0x18003c2fa  pop     rsi
0x18003c2fb  pop     rbp
0x18003c2fc  pop     rbx
0x18003c2fd  retn
```
