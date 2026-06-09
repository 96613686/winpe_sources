# FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)

- ea: `0x18002db3c`
- end: `0x18002dc39`
- name: `?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z`
- size: `253`
- prototype: `unsigned int __fastcall(SC_HANDLE hSCObject, SC_HANDLE)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002dc40`
- `0x18002e5ac`
- `0x18002ebe4`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002db3c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002db98`
- `KERNEL32!GetLastError` at `0x18002dbee`
- `KERNEL32!GetLastError` at `0x18002db98`
- `KERNEL32!GetLastError` at `0x18002dbee`
- `ADVAPI32!CloseServiceHandle` at `0x18002db88`
- `ADVAPI32!CloseServiceHandle` at `0x18002dbde`
- `ADVAPI32!CloseServiceHandle` at `0x18002db88`
- `ADVAPI32!CloseServiceHandle` at `0x18002dbde`

## pseudocode

```c
__int64 __fastcall FaxCloseService(SC_HANDLE hSCObject, SC_HANDLE a2)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  DWORD v6; // eax

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  if ( a2 )
  {
    if ( !CloseServiceHandle(a2) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      }
    }
  }
  if ( hSCObject )
  {
    if ( !CloseServiceHandle(hSCObject) )
    {
      v6 = GetLastError();
      v4 = v6;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_db036311db36307996a98c23702218b2_Traceguids, v6);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002db3c  push    rbx
0x18002db3e  push    rsi
0x18002db3f  push    rdi
0x18002db40  push    r14
0x18002db42  sub     rsp, 28h
0x18002db46  mov     rdi, rdx
0x18002db49  mov     rsi, rcx
0x18002db4c  xor     ebx, ebx
0x18002db4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db55  lea     r14, WPP_GLOBAL_Control
0x18002db5c  cmp     rcx, r14
0x18002db5f  jz      short loc_18002DB80
0x18002db61  test    byte ptr [rcx+1Ch], 2
0x18002db65  jz      short loc_18002DB80
0x18002db67  cmp     byte ptr [rcx+19h], 5
0x18002db6b  jb      short loc_18002DB80
0x18002db6d  mov     rcx, [rcx+10h]
0x18002db71  lea     edx, [rbx+0Eh]
0x18002db74  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002db7b  call    WPP_SF_
0x18002db80  test    rdi, rdi
0x18002db83  jz      short loc_18002DBD6
0x18002db85  mov     rcx, rdi; hSCObject
0x18002db88  call    cs:__imp_CloseServiceHandle
0x18002db8f  nop     dword ptr [rax+rax+00h]
0x18002db94  test    eax, eax
0x18002db96  jnz     short loc_18002DBD6
0x18002db98  call    cs:__imp_GetLastError
0x18002db9f  nop     dword ptr [rax+rax+00h]
0x18002dba4  mov     ebx, eax
0x18002dba6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbad  cmp     rcx, r14
0x18002dbb0  jz      short loc_18002DBD6
0x18002dbb2  test    byte ptr [rcx+1Ch], 2
0x18002dbb6  jz      short loc_18002DBD6
0x18002dbb8  cmp     byte ptr [rcx+19h], 2
0x18002dbbc  jb      short loc_18002DBD6
0x18002dbbe  mov     rcx, [rcx+10h]
0x18002dbc2  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002dbc9  mov     edx, 0Fh
0x18002dbce  mov     r9d, eax
0x18002dbd1  call    WPP_SF_d
0x18002dbd6  test    rsi, rsi
0x18002dbd9  jz      short loc_18002DC2C
0x18002dbdb  mov     rcx, rsi; hSCObject
0x18002dbde  call    cs:__imp_CloseServiceHandle
0x18002dbe5  nop     dword ptr [rax+rax+00h]
0x18002dbea  test    eax, eax
0x18002dbec  jnz     short loc_18002DC2C
0x18002dbee  call    cs:__imp_GetLastError
0x18002dbf5  nop     dword ptr [rax+rax+00h]
0x18002dbfa  mov     ebx, eax
0x18002dbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc03  cmp     rcx, r14
0x18002dc06  jz      short loc_18002DC2C
0x18002dc08  test    byte ptr [rcx+1Ch], 2
0x18002dc0c  jz      short loc_18002DC2C
0x18002dc0e  cmp     byte ptr [rcx+19h], 2
0x18002dc12  jb      short loc_18002DC2C
0x18002dc14  mov     rcx, [rcx+10h]
0x18002dc18  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002dc1f  mov     edx, 10h
0x18002dc24  mov     r9d, eax
0x18002dc27  call    WPP_SF_d
0x18002dc2c  mov     eax, ebx
0x18002dc2e  add     rsp, 28h
0x18002dc32  pop     r14
0x18002dc34  pop     rdi
0x18002dc35  pop     rsi
0x18002dc36  pop     rbx
0x18002dc37  retn
```
