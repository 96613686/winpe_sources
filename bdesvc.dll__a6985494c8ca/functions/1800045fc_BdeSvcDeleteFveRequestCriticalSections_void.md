# BdeSvcDeleteFveRequestCriticalSections(void)

- ea: `0x1800045fc`
- end: `0x180004689`
- name: `?BdeSvcDeleteFveRequestCriticalSections@@YAXXZ`
- size: `141`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042f0`

## callees

- `0x1800045fc`
- `0x180004690`
- `0x180009f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004637`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000464a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004637`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000464a`

## pseudocode

```c
void BdeSvcDeleteFveRequestCriticalSections(void)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
  DeleteCriticalSection(&gBdesvcServerRotationStatusCS);
  DeleteCriticalSection(&gBdesvcPersistentReqTimerObjectCS);
  FveDeletePersistentRequestTimerCriticalSection();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
}

```

## disassembly

```asm
0x1800045fc  push    rbx
0x1800045fe  sub     rsp, 20h
0x180004602  mov     rcx, cs:WPP_GLOBAL_Control
0x180004609  lea     rbx, WPP_GLOBAL_Control
0x180004610  cmp     rcx, rbx
0x180004613  jz      short loc_180004630
0x180004615  test    byte ptr [rcx+1Ch], 20h
0x180004619  jz      short loc_180004630
0x18000461b  mov     rcx, [rcx+10h]
0x18000461f  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x180004626  mov     edx, 15h
0x18000462b  call    WPP_SF_
0x180004630  lea     rcx, ?gBdesvcServerRotationStatusCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004637  call    cs:__imp_DeleteCriticalSection
0x18000463e  nop     dword ptr [rax+rax+00h]
0x180004643  lea     rcx, ?gBdesvcPersistentReqTimerObjectCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000464a  call    cs:__imp_DeleteCriticalSection
0x180004651  nop     dword ptr [rax+rax+00h]
0x180004656  call    ?FveDeletePersistentRequestTimerCriticalSection@@YAXXZ; FveDeletePersistentRequestTimerCriticalSection(void)
0x18000465b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004662  cmp     rcx, rbx
0x180004665  jz      short loc_180004682
0x180004667  test    byte ptr [rcx+1Ch], 20h
0x18000466b  jz      short loc_180004682
0x18000466d  mov     rcx, [rcx+10h]
0x180004671  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x180004678  mov     edx, 16h
0x18000467d  call    WPP_SF_
0x180004682  add     rsp, 20h
0x180004686  pop     rbx
0x180004687  retn
```
