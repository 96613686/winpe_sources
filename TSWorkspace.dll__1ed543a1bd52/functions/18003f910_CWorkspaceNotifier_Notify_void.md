# CWorkspaceNotifier::Notify(void)

- ea: `0x18003f910`
- end: `0x18003fb7c`
- name: `?Notify@CWorkspaceNotifier@@QEAAJXZ`
- size: `620`
- prototype: `__int64 __fastcall(CWorkspaceNotifier *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003fd88`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18003f270`
- `0x18003f6d4`
- `0x18003f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb3b`
- `USER32!PostMessageW` at `0x18003fad1`
- `USER32!PostMessageW` at `0x18003fad1`
- `USER32!DestroyWindow` at `0x18003fb5d`
- `USER32!DestroyWindow` at `0x18003fb5d`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18003fa68`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18003fa68`

## pseudocode

```c
__int64 __fastcall CWorkspaceNotifier::Notify(CWorkspaceNotifier *this)
{
  unsigned int GlobalNotifierLock; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  CWorkspaceNotifier *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // eax
  HWND v7; // rax
  signed int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  signed int LastError; // eax
  signed int v13; // eax
  HWND v14; // rcx
  unsigned int v16; // [rsp+28h] [rbp-10h]

  if ( *((_QWORD *)this + 8) )
  {
    GlobalNotifierLock = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids,
        CurrentThreadActivityIdPrefix,
        1);
    }
    return GlobalNotifierLock;
  }
  GlobalNotifierLock = CWorkspaceNotifier::GetGlobalNotifierLock(this);
  if ( (GlobalNotifierLock & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = GlobalNotifierLock;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids,
        v5,
        (__int64)"GetGlobalNotifierLock failed",
        v16);
    }
LABEL_34:
    v14 = (HWND)*((_QWORD *)this + 8);
    if ( v14 )
    {
      DestroyWindow(v14);
      *((_QWORD *)this + 8) = 0;
    }
    return GlobalNotifierLock;
  }
  if ( !(unsigned int)CWorkspaceNotifier::IsNotificationRequired(v4) )
  {
    GlobalNotifierLock = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids, v6);
    }
    return GlobalNotifierLock;
  }
  v7 = (HWND)SHCreateWorkerWindowW(CWorkspaceNotifier::WorkerWindowProc, 0, 0, 0, 0, this);
  *((_QWORD *)this + 8) = v7;
  if ( v7 )
  {
    if ( PostMessageW(v7, 0x80CBu, 0, 0) )
      return 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 52;
      goto LABEL_30;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 51;
LABEL_30:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids, v10, v9);
  }
  v13 = GetLastError();
  GlobalNotifierLock = v13;
  if ( v13 > 0 )
    GlobalNotifierLock = (unsigned __int16)v13 | 0x80070000;
  if ( (GlobalNotifierLock & 0x80000000) != 0 )
    goto LABEL_34;
  return GlobalNotifierLock;
}

```

## disassembly

```asm
0x18003f910  mov     [rsp+arg_0], rbx
0x18003f915  push    rdi
0x18003f916  sub     rsp, 30h
0x18003f91a  cmp     qword ptr [rcx+40h], 0
0x18003f91f  mov     rdi, rcx
0x18003f922  jz      short loc_18003F97F
0x18003f924  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f92b  lea     rax, WPP_GLOBAL_Control
0x18003f932  mov     ebx, 1
0x18003f937  cmp     rcx, rax
0x18003f93a  jz      loc_18003FB6F
0x18003f940  test    byte ptr [rcx+1Ch], 8
0x18003f944  jz      loc_18003FB6F
0x18003f94a  cmp     byte ptr [rcx+19h], 2
0x18003f94e  jb      loc_18003FB6F
0x18003f954  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003f959  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f960  lea     edx, [rbx+2Fh]
0x18003f963  mov     r9d, eax
0x18003f966  mov     dword ptr [rsp+38h+var_18], ebx
0x18003f96a  lea     r8, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids
0x18003f971  mov     rcx, [rcx+10h]
0x18003f975  call    WPP_SF_Dd
0x18003f97a  jmp     loc_18003FB6F
0x18003f97f  call    ?GetGlobalNotifierLock@CWorkspaceNotifier@@AEAAJXZ; CWorkspaceNotifier::GetGlobalNotifierLock(void)
0x18003f984  mov     ebx, eax
0x18003f986  test    eax, eax
0x18003f988  jns     short loc_18003F9EE
0x18003f98a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f991  lea     rax, WPP_GLOBAL_Control
0x18003f998  cmp     rcx, rax
0x18003f99b  jz      loc_18003FB54
0x18003f9a1  test    byte ptr [rcx+1Ch], 8
0x18003f9a5  jz      loc_18003FB54
0x18003f9ab  cmp     byte ptr [rcx+19h], 2
0x18003f9af  jb      loc_18003FB54
0x18003f9b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003f9ba  lea     rcx, aGetglobalnotif; "GetGlobalNotifierLock failed"
0x18003f9c1  mov     [rsp+38h+var_10], ebx
0x18003f9c5  mov     [rsp+38h+var_18], rcx
0x18003f9ca  lea     r8, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids
0x18003f9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f9d8  mov     edx, 31h ; '1'
0x18003f9dd  mov     r9d, eax
0x18003f9e0  mov     rcx, [rcx+10h]
0x18003f9e4  call    WPP_SF_DsD
0x18003f9e9  jmp     loc_18003FB54
0x18003f9ee  call    ?IsNotificationRequired@CWorkspaceNotifier@@IEAAHXZ; CWorkspaceNotifier::IsNotificationRequired(void)
0x18003f9f3  test    eax, eax
0x18003f9f5  jnz     short loc_18003FA4B
0x18003f9f7  lea     ebx, [rax+1]
0x18003f9fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa01  lea     rax, WPP_GLOBAL_Control
0x18003fa08  cmp     rcx, rax
0x18003fa0b  jz      loc_18003FB6F
0x18003fa11  test    [rcx+1Ch], bl
0x18003fa14  jz      loc_18003FB6F
0x18003fa1a  cmp     byte ptr [rcx+19h], 4
0x18003fa1e  jb      loc_18003FB6F
0x18003fa24  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fa29  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa30  lea     edx, [rbx+31h]
0x18003fa33  mov     r9d, eax
0x18003fa36  lea     r8, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids
0x18003fa3d  mov     rcx, [rcx+10h]
0x18003fa41  call    WPP_SF_D
0x18003fa46  jmp     loc_18003FB6F
0x18003fa4b  mov     qword ptr [rsp+38h+var_10], rdi
0x18003fa50  lea     rcx, ?WorkerWindowProc@CWorkspaceNotifier@@KA_JPEAUHWND__@@I_K_J@Z; CWorkspaceNotifier::WorkerWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18003fa57  xor     r9d, r9d
0x18003fa5a  mov     [rsp+38h+var_18], 0
0x18003fa63  xor     r8d, r8d
0x18003fa66  xor     edx, edx
0x18003fa68  call    cs:__imp_SHCreateWorkerWindowW
0x18003fa6e  mov     [rdi+40h], rax
0x18003fa72  test    rax, rax
0x18003fa75  jnz     short loc_18003FAC3
0x18003fa77  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa7e  lea     rax, WPP_GLOBAL_Control
0x18003fa85  cmp     rcx, rax
0x18003fa88  jz      loc_18003FB3B
0x18003fa8e  test    byte ptr [rcx+1Ch], 8
0x18003fa92  jz      loc_18003FB3B
0x18003fa98  cmp     byte ptr [rcx+19h], 2
0x18003fa9c  jb      loc_18003FB3B
0x18003faa2  call    cs:__imp_GetLastError
0x18003faa8  mov     ebx, eax
0x18003faaa  test    eax, eax
0x18003faac  jle     short loc_18003FAB7
0x18003faae  movzx   ebx, ax
0x18003fab1  or      ebx, 80070000h
0x18003fab7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fabc  mov     edx, 33h ; '3'
0x18003fac1  jmp     short loc_18003FB1D
0x18003fac3  xor     r9d, r9d; lParam
0x18003fac6  xor     r8d, r8d; wParam
0x18003fac9  mov     edx, 80CBh; Msg
0x18003face  mov     rcx, rax; hWnd
0x18003fad1  call    cs:__imp_PostMessageW
0x18003fad7  test    eax, eax
0x18003fad9  jnz     loc_18003FB6D
0x18003fadf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fae6  lea     rax, WPP_GLOBAL_Control
0x18003faed  cmp     rcx, rax
0x18003faf0  jz      short loc_18003FB3B
0x18003faf2  test    byte ptr [rcx+1Ch], 8
0x18003faf6  jz      short loc_18003FB3B
0x18003faf8  cmp     byte ptr [rcx+19h], 2
0x18003fafc  jb      short loc_18003FB3B
0x18003fafe  call    cs:__imp_GetLastError
0x18003fb04  mov     ebx, eax
0x18003fb06  test    eax, eax
0x18003fb08  jle     short loc_18003FB13
0x18003fb0a  movzx   ebx, ax
0x18003fb0d  or      ebx, 80070000h
0x18003fb13  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fb18  mov     edx, 34h ; '4'
0x18003fb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb24  lea     r8, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids
0x18003fb2b  mov     r9d, eax
0x18003fb2e  mov     dword ptr [rsp+38h+var_18], ebx
0x18003fb32  mov     rcx, [rcx+10h]
0x18003fb36  call    WPP_SF_Dd
0x18003fb3b  call    cs:__imp_GetLastError
0x18003fb41  mov     ebx, eax
0x18003fb43  test    eax, eax
0x18003fb45  jle     short loc_18003FB50
0x18003fb47  movzx   ebx, ax
0x18003fb4a  or      ebx, 80070000h
0x18003fb50  test    ebx, ebx
0x18003fb52  jns     short loc_18003FB6F
0x18003fb54  mov     rcx, [rdi+40h]; hWnd
0x18003fb58  test    rcx, rcx
0x18003fb5b  jz      short loc_18003FB6F
0x18003fb5d  call    cs:__imp_DestroyWindow
0x18003fb63  mov     qword ptr [rdi+40h], 0
0x18003fb6b  jmp     short loc_18003FB6F
0x18003fb6d  xor     ebx, ebx
0x18003fb6f  mov     eax, ebx
0x18003fb71  mov     rbx, [rsp+38h+arg_0]
0x18003fb76  add     rsp, 30h
0x18003fb7a  pop     rdi
0x18003fb7b  retn
```
