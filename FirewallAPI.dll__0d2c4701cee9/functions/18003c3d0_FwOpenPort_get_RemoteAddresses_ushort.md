# FwOpenPort::get_RemoteAddresses(ushort * *)

- ea: `0x18003c3d0`
- end: `0x18003c493`
- name: `?get_RemoteAddresses@FwOpenPort@@UEAAJPEAPEAG@Z`
- size: `195`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18003c3d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c3e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c3e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c460`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c460`
- `fwbase!FwReportReturnError` at `0x18003c451`
- `fwbase!FwReportReturnError` at `0x18003c479`
- `fwbase!FwReportReturnError` at `0x18003c451`
- `fwbase!FwReportReturnError` at `0x18003c479`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18003c436`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18003c436`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c417`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c417`

## string_xrefs

- `0x18003c44a`: `FwOpenPort::get_RemoteAddresses`
- `0x18003c472`: `FwOpenPort::get_RemoteAddresses`

## pseudocode

```c
__int64 __fastcall FwOpenPort::get_RemoteAddresses(FwOpenPort *this, unsigned __int16 **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v5; // ebx
  __int64 v6; // rdx
  _QWORD *v7; // rdi
  int OpenPortorAuthAppAsBSTR; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    v7 = (_QWORD *)((char *)this + 72);
    *a2 = 0;
    if ( *((_QWORD *)this + 9)
      || (OpenPortorAuthAppAsBSTR = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16)),
          v5 = OpenPortorAuthAppAsBSTR,
          OpenPortorAuthAppAsBSTR >= 0) )
    {
      OpenPortorAuthAppAsBSTR = GetOpenPortorAuthAppAsBSTR(*v7 + 176LL, a2);
      v5 = OpenPortorAuthAppAsBSTR;
      if ( OpenPortorAuthAppAsBSTR >= 0 )
        goto LABEL_8;
    }
    v6 = (unsigned int)OpenPortorAuthAppAsBSTR;
  }
  else
  {
    v5 = -2147467261;
    v6 = 2147500035LL;
  }
  FwReportReturnError("FwOpenPort::get_RemoteAddresses", v6);
LABEL_8:
  LeaveCriticalSection(v2);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::get_RemoteAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003c3d0  push    rbx
0x18003c3d2  push    rbp
0x18003c3d3  push    rsi
0x18003c3d4  push    rdi
0x18003c3d5  sub     rsp, 28h
0x18003c3d9  lea     rbp, [rcx+10h]
0x18003c3dd  mov     rbx, rcx
0x18003c3e0  mov     rcx, rbp; lpCriticalSection
0x18003c3e3  mov     rsi, rdx
0x18003c3e6  call    cs:__imp_EnterCriticalSection
0x18003c3ed  nop     dword ptr [rax+rax+00h]
0x18003c3f2  test    rsi, rsi
0x18003c3f5  jnz     short loc_18003C400
0x18003c3f7  mov     ebx, 80004003h
0x18003c3fc  mov     edx, ebx
0x18003c3fe  jmp     short loc_18003C44A
0x18003c400  lea     rdi, [rbx+48h]
0x18003c404  mov     qword ptr [rsi], 0
0x18003c40b  cmp     qword ptr [rdi], 0
0x18003c40f  jnz     short loc_18003C429
0x18003c411  mov     edx, [rbx+40h]
0x18003c414  mov     rcx, rdi
0x18003c417  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003c41e  nop     dword ptr [rax+rax+00h]
0x18003c423  mov     ebx, eax
0x18003c425  test    eax, eax
0x18003c427  js      short loc_18003C448
0x18003c429  mov     rcx, [rdi]
0x18003c42c  mov     rdx, rsi
0x18003c42f  add     rcx, 0B0h
0x18003c436  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x18003c43d  nop     dword ptr [rax+rax+00h]
0x18003c442  mov     ebx, eax
0x18003c444  test    eax, eax
0x18003c446  jns     short loc_18003C45D
0x18003c448  mov     edx, eax
0x18003c44a  lea     rcx, aFwopenportGetR; "FwOpenPort::get_RemoteAddresses"
0x18003c451  call    cs:__imp_FwReportReturnError
0x18003c458  nop     dword ptr [rax+rax+00h]
0x18003c45d  mov     rcx, rbp; lpCriticalSection
0x18003c460  call    cs:__imp_LeaveCriticalSection
0x18003c467  nop     dword ptr [rax+rax+00h]
0x18003c46c  test    ebx, ebx
0x18003c46e  jns     short loc_18003C487
0x18003c470  mov     edx, ebx
0x18003c472  lea     rcx, aFwopenportGetR; "FwOpenPort::get_RemoteAddresses"
0x18003c479  call    cs:__imp_FwReportReturnError
0x18003c480  nop     dword ptr [rax+rax+00h]
0x18003c485  mov     ebx, eax
0x18003c487  mov     eax, ebx
0x18003c489  add     rsp, 28h
0x18003c48d  pop     rdi
0x18003c48e  pop     rsi
0x18003c48f  pop     rbp
0x18003c490  pop     rbx
0x18003c491  retn
```
