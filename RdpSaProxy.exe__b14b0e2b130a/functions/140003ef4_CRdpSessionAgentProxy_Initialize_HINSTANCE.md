# CRdpSessionAgentProxy::Initialize(HINSTANCE__ *)

- ea: `0x140003ef4`
- end: `0x1400040e3`
- name: `?Initialize@CRdpSessionAgentProxy@@QEAAJPEAUHINSTANCE__@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140004750`

## callees

- `0x14000186f`
- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x140003ef4`
- `0x1400054f0`
- `0x1400056f0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140003f46`
- `KERNEL32!GetCurrentProcessId` at `0x140003f46`
- `KERNEL32!ProcessIdToSessionId` at `0x140003f52`
- `KERNEL32!ProcessIdToSessionId` at `0x140003f52`
- `KERNEL32!GetLastError` at `0x140003f5c`
- `KERNEL32!GetLastError` at `0x140004072`
- `KERNEL32!GetLastError` at `0x140003f5c`
- `KERNEL32!GetLastError` at `0x140004072`
- `SHELL32!ShellExecuteExW` at `0x140004068`
- `SHELL32!ShellExecuteExW` at `0x140004068`

## string_xrefs

- `0x14000400a`: `CRdpSaComUtils::s_GetKnownFolderFilePath failed!`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::Initialize(CRdpSessionAgentProxy *this, HINSTANCE a2)
{
  DWORD CurrentProcessId; // eax
  const unsigned __int16 *v5; // rdx
  const struct _GUID *v6; // rcx
  unsigned __int64 v7; // r8
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-298h] BYREF
  unsigned __int16 v14[264]; // [rsp+A0h] [rbp-228h] BYREF

  memset_0(v14, 0, 0x208u);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  *((_DWORD *)this + 11) |= 2u;
  *((_QWORD *)this + 9) = a2;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, (DWORD *)this + 20) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 13;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
LABEL_7:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  LastError = CRdpSaShellUtils::s_GetKnownFolderFilePath(v6, v5, v7, v14);
  if ( LastError >= 0 )
  {
    pExecInfo.cbSize = 112;
    pExecInfo.lpFile = v14;
    pExecInfo.fMask = 320;
    pExecInfo.nShow = 0;
    if ( ShellExecuteExW(&pExecInfo) )
    {
      *((_QWORD *)this + 11) = pExecInfo.hProcess;
      return (unsigned int)LastError;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 15;
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
      v11,
      (__int64)"CRdpSaComUtils::s_GetKnownFolderFilePath failed!",
      LastError);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140003ef4  mov     [rsp+arg_8], rbx
0x140003ef9  push    rdi
0x140003efa  sub     rsp, 2C0h
0x140003f01  mov     rax, cs:__security_cookie
0x140003f08  xor     rax, rsp
0x140003f0b  mov     [rsp+2C8h+var_18], rax
0x140003f13  mov     rbx, rdx
0x140003f16  mov     rdi, rcx
0x140003f19  xor     edx, edx; Val
0x140003f1b  lea     rcx, [rsp+2C8h+var_228]; void *
0x140003f23  mov     r8d, 208h; Size
0x140003f29  call    memset_0
0x140003f2e  xor     edx, edx; Val
0x140003f30  lea     rcx, [rsp+2C8h+pExecInfo]; void *
0x140003f35  lea     r8d, [rdx+70h]; Size
0x140003f39  call    memset_0
0x140003f3e  or      dword ptr [rdi+2Ch], 2
0x140003f42  mov     [rdi+48h], rbx
0x140003f46  call    cs:__imp_GetCurrentProcessId
0x140003f4c  mov     ecx, eax; dwProcessId
0x140003f4e  lea     rdx, [rdi+50h]; pSessionId
0x140003f52  call    cs:__imp_ProcessIdToSessionId
0x140003f58  test    eax, eax
0x140003f5a  jnz     short loc_140003FC7
0x140003f5c  call    cs:__imp_GetLastError
0x140003f62  mov     ebx, eax
0x140003f64  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f6b  lea     rax, WPP_GLOBAL_Control
0x140003f72  cmp     rcx, rax
0x140003f75  jz      short loc_140003FAB
0x140003f77  test    byte ptr [rcx+1Ch], 8
0x140003f7b  jz      short loc_140003FAB
0x140003f7d  cmp     byte ptr [rcx+19h], 2
0x140003f81  jb      short loc_140003FAB
0x140003f83  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003f88  mov     edx, 0Dh
0x140003f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f94  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003f9b  mov     r9d, eax
0x140003f9e  mov     dword ptr [rsp+2C8h+var_2A8], ebx
0x140003fa2  mov     rcx, [rcx+10h]
0x140003fa6  call    WPP_SF_Dd
0x140003fab  test    ebx, ebx
0x140003fad  jle     short loc_140003FB8
0x140003faf  movzx   ebx, bx
0x140003fb2  or      ebx, 80070000h
0x140003fb8  test    ebx, ebx
0x140003fba  mov     eax, 80004005h
0x140003fbf  cmovns  ebx, eax
0x140003fc2  jmp     loc_1400040C0
0x140003fc7  lea     r9, [rsp+2C8h+var_228]; unsigned __int16 *
0x140003fcf  call    ?s_GetKnownFolderFilePath@CRdpSaShellUtils@@SAJAEBU_GUID@@PEBG_KPEAG@Z; CRdpSaShellUtils::s_GetKnownFolderFilePath(_GUID const &,ushort const *,unsigned __int64,ushort *)
0x140003fd4  mov     ebx, eax
0x140003fd6  test    eax, eax
0x140003fd8  jns     short loc_14000403E
0x140003fda  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fe1  lea     rax, WPP_GLOBAL_Control
0x140003fe8  cmp     rcx, rax
0x140003feb  jz      loc_1400040C0
0x140003ff1  test    byte ptr [rcx+1Ch], 8
0x140003ff5  jz      loc_1400040C0
0x140003ffb  cmp     byte ptr [rcx+19h], 2
0x140003fff  jb      loc_1400040C0
0x140004005  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000400a  lea     rcx, aCrdpsacomutils; "CRdpSaComUtils::s_GetKnownFolderFilePat"...
0x140004011  mov     [rsp+2C8h+var_2A0], ebx
0x140004015  mov     [rsp+2C8h+var_2A8], rcx
0x14000401a  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140004021  mov     rcx, cs:WPP_GLOBAL_Control
0x140004028  mov     edx, 0Eh
0x14000402d  mov     r9d, eax
0x140004030  mov     rcx, [rcx+10h]
0x140004034  call    WPP_SF_DsD
0x140004039  jmp     loc_1400040C0
0x14000403e  lea     rax, [rsp+2C8h+var_228]
0x140004046  mov     [rsp+2C8h+pExecInfo.cbSize], 70h ; 'p'
0x14000404e  lea     rcx, [rsp+2C8h+pExecInfo]; pExecInfo
0x140004053  mov     [rsp+2C8h+pExecInfo.lpFile], rax
0x140004058  mov     [rsp+2C8h+pExecInfo.fMask], 140h
0x140004060  mov     [rsp+2C8h+pExecInfo.nShow], 0
0x140004068  call    cs:__imp_ShellExecuteExW
0x14000406e  test    eax, eax
0x140004070  jnz     short loc_1400040B4
0x140004072  call    cs:__imp_GetLastError
0x140004078  mov     ebx, eax
0x14000407a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004081  lea     rax, WPP_GLOBAL_Control
0x140004088  cmp     rcx, rax
0x14000408b  jz      loc_140003FAB
0x140004091  test    byte ptr [rcx+1Ch], 8
0x140004095  jz      loc_140003FAB
0x14000409b  cmp     byte ptr [rcx+19h], 2
0x14000409f  jb      loc_140003FAB
0x1400040a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400040aa  mov     edx, 0Fh
0x1400040af  jmp     loc_140003F8D
0x1400040b4  mov     rax, [rsp+2C8h+pExecInfo.hProcess]
0x1400040bc  mov     [rdi+58h], rax
0x1400040c0  mov     eax, ebx
0x1400040c2  mov     rcx, [rsp+2C8h+var_18]
0x1400040ca  xor     rcx, rsp; StackCookie
0x1400040cd  call    __security_check_cookie
0x1400040d2  mov     rbx, [rsp+2C8h+arg_8]
0x1400040da  add     rsp, 2C0h
0x1400040e1  pop     rdi
0x1400040e2  retn
```
