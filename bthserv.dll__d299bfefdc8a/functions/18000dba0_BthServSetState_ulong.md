# BthServSetState(ulong)

- ea: `0x18000dba0`
- end: `0x18000dc38`
- name: `?BthServSetState@@YAHK@Z`
- size: `152`
- prototype: `int __fastcall(DWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000e3b4`
- `0x18000fdc0`
- `0x1800100c0`

## callees

- `0x18000dba0`
- `0x180011780`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000dc2b`

## pseudocode

```c
int __fastcall BthServSetState(DWORD a1)
{
  SERVICE_STATUS_HANDLE v1; // rax
  _UNKNOWN **v3; // rdx
  _UNKNOWN **v4; // r8

  v1 = hServiceStatus;
  if ( hServiceStatus )
  {
    v3 = &WPP_GLOBAL_Control;
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
    v4 = &WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v3,
        (_DWORD)v4,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
      v1 = hServiceStatus;
    }
    ServiceStatus.dwCurrentState = a1;
    LODWORD(v1) = SetServiceStatus(v1, &ServiceStatus);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18000dba0  push    rbx
0x18000dba2  sub     rsp, 60h
0x18000dba6  mov     rax, cs:hServiceStatus
0x18000dbad  mov     ebx, ecx
0x18000dbaf  test    rax, rax
0x18000dbb2  jz      short loc_18000DC32
0x18000dbb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbbb  lea     rdx, WPP_GLOBAL_Control
0x18000dbc2  cmp     rcx, rdx
0x18000dbc5  jz      short loc_18000DBD1
0x18000dbc7  cmp     byte ptr [rcx+19h], 5
0x18000dbcb  jb      short loc_18000DBD1
0x18000dbcd  mov     dl, 1
0x18000dbcf  jmp     short loc_18000DBD3
0x18000dbd1  xor     dl, dl
0x18000dbd3  lea     r8, WPP_RECORDER_INITIALIZED
0x18000dbda  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18000dbe1  setnz   r8b
0x18000dbe5  test    dl, dl
0x18000dbe7  jnz     short loc_18000DBEE
0x18000dbe9  test    r8b, r8b
0x18000dbec  jz      short loc_18000DC16
0x18000dbee  lea     r9, off_180039490; "<blank>"
0x18000dbf5  mov     rax, [r9+rbx*8]
0x18000dbf9  mov     r9, [rcx+28h]
0x18000dbfd  mov     rcx, [rcx+10h]
0x18000dc01  mov     [rsp+68h+var_18], rax
0x18000dc06  mov     [rsp+68h+var_20], ebx
0x18000dc0a  call    WPP_RECORDER_AND_TRACE_SF_sds
0x18000dc0f  mov     rax, cs:hServiceStatus
0x18000dc16  lea     rdx, ServiceStatus
0x18000dc1d  mov     cs:ServiceStatus.dwCurrentState, ebx
0x18000dc23  mov     rcx, rax
0x18000dc26  add     rsp, 60h
0x18000dc2a  pop     rbx
0x18000dc2b  jmp     cs:__imp_SetServiceStatus
0x18000dc32  add     rsp, 60h
0x18000dc36  pop     rbx
0x18000dc37  retn
```
