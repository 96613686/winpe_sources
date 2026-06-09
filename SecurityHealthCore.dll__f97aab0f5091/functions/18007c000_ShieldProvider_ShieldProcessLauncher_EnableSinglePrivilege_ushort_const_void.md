# ShieldProvider::ShieldProcessLauncher::EnableSinglePrivilege(ushort const *,void *)

- ea: `0x18007c000`
- end: `0x18007c104`
- name: `?EnableSinglePrivilege@ShieldProcessLauncher@ShieldProvider@@AEAAJPEBGPEAX@Z`
- size: `260`
- prototype: `int(ShieldProvider::ShieldProcessLauncher *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007d0b8`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x18007c000`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007c031`
- `KERNEL32!GetLastError` at `0x18007c0b7`
- `KERNEL32!GetLastError` at `0x18007c031`
- `KERNEL32!GetLastError` at `0x18007c0b7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007c0ad`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18007c0ad`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18007c027`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18007c027`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldProcessLauncher::EnableSinglePrivilege(
        ShieldProvider::ShieldProcessLauncher *this,
        const unsigned __int16 *a2,
        void *a3)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  signed int v9; // eax
  struct _TOKEN_PRIVILEGES NewState; // [rsp+30h] [rbp-28h] BYREF

  NewState = 0;
  if ( !LookupPrivilegeValueW(0, a2, &NewState.Privileges[0].Luid) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v5;
    v7 = 10;
LABEL_7:
    WPP_SF_d(v6[2], v7, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, v5);
    return v5;
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  if ( !AdjustTokenPrivileges(a3, 0, &NewState, 0x10u, 0, 0) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v5;
    v7 = 11;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x18007c000  push    rbx
0x18007c002  sub     rsp, 50h
0x18007c006  mov     rax, cs:__security_cookie
0x18007c00d  xor     rax, rsp
0x18007c010  mov     [rsp+58h+var_18], rax
0x18007c015  mov     rbx, r8
0x18007c018  xorps   xmm0, xmm0
0x18007c01b  lea     r8, [rsp+58h+NewState.Privileges]; lpLuid
0x18007c020  xor     ecx, ecx; lpSystemName
0x18007c022  movups  xmmword ptr [rsp+30h], xmm0
0x18007c027  call    cs:__imp_LookupPrivilegeValueW
0x18007c02d  test    eax, eax
0x18007c02f  jnz     short loc_18007C07B
0x18007c031  call    cs:__imp_GetLastError
0x18007c037  mov     ebx, eax
0x18007c039  test    eax, eax
0x18007c03b  jle     short loc_18007C046
0x18007c03d  movzx   ebx, ax
0x18007c040  or      ebx, 80070000h
0x18007c046  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c04d  lea     rax, WPP_GLOBAL_Control
0x18007c054  cmp     rcx, rax
0x18007c057  jz      short loc_18007C077
0x18007c059  test    byte ptr [rcx+1Ch], 1
0x18007c05d  jz      short loc_18007C077
0x18007c05f  mov     edx, 0Ah
0x18007c064  mov     rcx, [rcx+10h]
0x18007c068  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007c06f  mov     r9d, ebx
0x18007c072  call    WPP_SF_d
0x18007c077  mov     eax, ebx
0x18007c079  jmp     short loc_18007C0F1
0x18007c07b  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18007c084  lea     r8, [rsp+58h+NewState]; NewState
0x18007c089  mov     r9d, 10h; BufferLength
0x18007c08f  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18007c098  xor     edx, edx; DisableAllPrivileges
0x18007c09a  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x18007c0a2  mov     rcx, rbx; TokenHandle
0x18007c0a5  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x18007c0ad  call    cs:__imp_AdjustTokenPrivileges
0x18007c0b3  test    eax, eax
0x18007c0b5  jnz     short loc_18007C0EF
0x18007c0b7  call    cs:__imp_GetLastError
0x18007c0bd  mov     ebx, eax
0x18007c0bf  test    eax, eax
0x18007c0c1  jle     short loc_18007C0CC
0x18007c0c3  movzx   ebx, ax
0x18007c0c6  or      ebx, 80070000h
0x18007c0cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c0d3  lea     rax, WPP_GLOBAL_Control
0x18007c0da  cmp     rcx, rax
0x18007c0dd  jz      short loc_18007C077
0x18007c0df  test    byte ptr [rcx+1Ch], 1
0x18007c0e3  jz      short loc_18007C077
0x18007c0e5  mov     edx, 0Bh
0x18007c0ea  jmp     loc_18007C064
0x18007c0ef  xor     eax, eax
0x18007c0f1  mov     rcx, [rsp+58h+var_18]
0x18007c0f6  xor     rcx, rsp; StackCookie
0x18007c0f9  call    __security_check_cookie
0x18007c0fe  add     rsp, 50h
0x18007c102  pop     rbx
0x18007c103  retn
```
