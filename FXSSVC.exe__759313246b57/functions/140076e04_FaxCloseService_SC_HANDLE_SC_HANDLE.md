# FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)

- ea: `0x140076e04`
- end: `0x140076f01`
- name: `?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z`
- size: `253`
- prototype: `unsigned int __fastcall(SC_HANDLE hSCObject, SC_HANDLE)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140076f08`
- `0x140077814`
- `0x1400781f0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140076e04`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x140076e50`
- `ADVAPI32!CloseServiceHandle` at `0x140076ea6`
- `ADVAPI32!CloseServiceHandle` at `0x140076e50`
- `ADVAPI32!CloseServiceHandle` at `0x140076ea6`
- `KERNEL32!GetLastError` at `0x140076e60`
- `KERNEL32!GetLastError` at `0x140076eb6`
- `KERNEL32!GetLastError` at `0x140076e60`
- `KERNEL32!GetLastError` at `0x140076eb6`

## pseudocode

```c
__int64 __fastcall FaxCloseService(SC_HANDLE hSCObject, SC_HANDLE a2)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  DWORD v6; // eax

  v4 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
0x140076e04  push    rbx
0x140076e06  push    rsi
0x140076e07  push    rdi
0x140076e08  push    r14
0x140076e0a  sub     rsp, 28h
0x140076e0e  mov     rdi, rdx
0x140076e11  mov     rsi, rcx
0x140076e14  xor     ebx, ebx
0x140076e16  mov     rcx, cs:WPP_GLOBAL_Control
0x140076e1d  lea     r14, WPP_GLOBAL_Control
0x140076e24  cmp     rcx, r14
0x140076e27  jz      short loc_140076E48
0x140076e29  test    byte ptr [rcx+1Ch], 2
0x140076e2d  jz      short loc_140076E48
0x140076e2f  cmp     byte ptr [rcx+19h], 5
0x140076e33  jb      short loc_140076E48
0x140076e35  mov     rcx, [rcx+10h]
0x140076e39  lea     edx, [rbx+0Eh]
0x140076e3c  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140076e43  call    WPP_SF_
0x140076e48  test    rdi, rdi
0x140076e4b  jz      short loc_140076E9E
0x140076e4d  mov     rcx, rdi; hSCObject
0x140076e50  call    cs:__imp_CloseServiceHandle
0x140076e57  nop     dword ptr [rax+rax+00h]
0x140076e5c  test    eax, eax
0x140076e5e  jnz     short loc_140076E9E
0x140076e60  call    cs:__imp_GetLastError
0x140076e67  nop     dword ptr [rax+rax+00h]
0x140076e6c  mov     ebx, eax
0x140076e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140076e75  cmp     rcx, r14
0x140076e78  jz      short loc_140076E9E
0x140076e7a  test    byte ptr [rcx+1Ch], 2
0x140076e7e  jz      short loc_140076E9E
0x140076e80  cmp     byte ptr [rcx+19h], 2
0x140076e84  jb      short loc_140076E9E
0x140076e86  mov     rcx, [rcx+10h]
0x140076e8a  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140076e91  mov     edx, 0Fh
0x140076e96  mov     r9d, eax
0x140076e99  call    WPP_SF_d
0x140076e9e  test    rsi, rsi
0x140076ea1  jz      short loc_140076EF4
0x140076ea3  mov     rcx, rsi; hSCObject
0x140076ea6  call    cs:__imp_CloseServiceHandle
0x140076ead  nop     dword ptr [rax+rax+00h]
0x140076eb2  test    eax, eax
0x140076eb4  jnz     short loc_140076EF4
0x140076eb6  call    cs:__imp_GetLastError
0x140076ebd  nop     dword ptr [rax+rax+00h]
0x140076ec2  mov     ebx, eax
0x140076ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x140076ecb  cmp     rcx, r14
0x140076ece  jz      short loc_140076EF4
0x140076ed0  test    byte ptr [rcx+1Ch], 2
0x140076ed4  jz      short loc_140076EF4
0x140076ed6  cmp     byte ptr [rcx+19h], 2
0x140076eda  jb      short loc_140076EF4
0x140076edc  mov     rcx, [rcx+10h]
0x140076ee0  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140076ee7  mov     edx, 10h
0x140076eec  mov     r9d, eax
0x140076eef  call    WPP_SF_d
0x140076ef4  mov     eax, ebx
0x140076ef6  add     rsp, 28h
0x140076efa  pop     r14
0x140076efc  pop     rdi
0x140076efd  pop     rsi
0x140076efe  pop     rbx
0x140076eff  retn
```
