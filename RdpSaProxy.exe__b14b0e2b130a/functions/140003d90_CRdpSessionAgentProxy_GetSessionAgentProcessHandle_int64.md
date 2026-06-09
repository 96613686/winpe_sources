# CRdpSessionAgentProxy::GetSessionAgentProcessHandle(__int64 *)

- ea: `0x140003d90`
- end: `0x140003eec`
- name: `?GetSessionAgentProcessHandle@CRdpSessionAgentProxy@@UEAAJPEA_J@Z`
- size: `348`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x1400035d8`
- `0x140003d90`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::GetSessionAgentProcessHandle(CRdpSessionAgentProxy *this, __int64 *a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v4 = CRdpSessionAgentProxy::AccessCheckWellKnownUser(this, WinLocalSystemSid);
  if ( v4 >= 0 )
  {
    if ( a2 )
    {
      v7 = *((_QWORD *)this + 10);
      if ( v7 )
      {
        *a2 = v7;
        *((_QWORD *)this + 10) = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
            CurrentThreadActivityIdPrefix,
            -2147418113);
        }
        return (unsigned int)-2147418113;
      }
    }
    else
    {
      v4 = 12;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids, v6, 12);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
      v5,
      (__int64)"User not authorized",
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140003d90  mov     [rsp+arg_0], rbx
0x140003d95  mov     [rsp+arg_8], rsi
0x140003d9a  push    rdi
0x140003d9b  sub     rsp, 30h
0x140003d9f  mov     rdi, rdx
0x140003da2  mov     rsi, rcx
0x140003da5  mov     edx, 16h; enum WELL_KNOWN_SID_TYPE
0x140003daa  call    ?AccessCheckWellKnownUser@CRdpSessionAgentProxy@@AEAAJW4WELL_KNOWN_SID_TYPE@@@Z; CRdpSessionAgentProxy::AccessCheckWellKnownUser(WELL_KNOWN_SID_TYPE)
0x140003daf  mov     ebx, eax
0x140003db1  test    eax, eax
0x140003db3  jns     short loc_140003E19
0x140003db5  mov     rax, cs:WPP_GLOBAL_Control
0x140003dbc  lea     rcx, WPP_GLOBAL_Control
0x140003dc3  cmp     rax, rcx
0x140003dc6  jz      loc_140003EDA
0x140003dcc  test    byte ptr [rax+1Ch], 8
0x140003dd0  jz      loc_140003EDA
0x140003dd6  cmp     byte ptr [rax+19h], 2
0x140003dda  jb      loc_140003EDA
0x140003de0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003de5  lea     rcx, aUserNotAuthori; "User not authorized"
0x140003dec  mov     [rsp+38h+var_10], ebx
0x140003df0  mov     [rsp+38h+var_18], rcx
0x140003df5  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e03  mov     edx, 16h
0x140003e08  mov     r9d, eax
0x140003e0b  mov     rcx, [rcx+10h]
0x140003e0f  call    WPP_SF_DsD
0x140003e14  jmp     loc_140003EDA
0x140003e19  test    rdi, rdi
0x140003e1c  jnz     short loc_140003E74
0x140003e1e  mov     rax, cs:WPP_GLOBAL_Control
0x140003e25  lea     rcx, WPP_GLOBAL_Control
0x140003e2c  lea     ebx, [rdi+0Ch]
0x140003e2f  cmp     rax, rcx
0x140003e32  jz      loc_140003EDA
0x140003e38  test    byte ptr [rax+1Ch], 8
0x140003e3c  jz      loc_140003EDA
0x140003e42  cmp     byte ptr [rax+19h], 2
0x140003e46  jb      loc_140003EDA
0x140003e4c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003e51  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e58  lea     edx, [rdi+17h]
0x140003e5b  mov     r9d, eax
0x140003e5e  mov     dword ptr [rsp+38h+var_18], ebx
0x140003e62  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003e69  mov     rcx, [rcx+10h]
0x140003e6d  call    WPP_SF_Dd
0x140003e72  jmp     short loc_140003EDA
0x140003e74  mov     rax, [rsi+50h]
0x140003e78  test    rax, rax
0x140003e7b  jnz     short loc_140003ECF
0x140003e7d  mov     rax, cs:WPP_GLOBAL_Control
0x140003e84  lea     rcx, WPP_GLOBAL_Control
0x140003e8b  cmp     rax, rcx
0x140003e8e  jz      short loc_140003EC8
0x140003e90  test    byte ptr [rax+1Ch], 8
0x140003e94  jz      short loc_140003EC8
0x140003e96  cmp     byte ptr [rax+19h], 2
0x140003e9a  jb      short loc_140003EC8
0x140003e9c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ea8  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003eaf  mov     edx, 18h
0x140003eb4  mov     dword ptr [rsp+38h+var_18], 8000FFFFh
0x140003ebc  mov     r9d, eax
0x140003ebf  mov     rcx, [rcx+10h]
0x140003ec3  call    WPP_SF_Dd
0x140003ec8  mov     ebx, 8000FFFFh
0x140003ecd  jmp     short loc_140003EDA
0x140003ecf  mov     [rdi], rax
0x140003ed2  mov     qword ptr [rsi+50h], 0
0x140003eda  mov     rsi, [rsp+38h+arg_8]
0x140003edf  mov     eax, ebx
0x140003ee1  mov     rbx, [rsp+38h+arg_0]
0x140003ee6  add     rsp, 30h
0x140003eea  pop     rdi
0x140003eeb  retn
```
