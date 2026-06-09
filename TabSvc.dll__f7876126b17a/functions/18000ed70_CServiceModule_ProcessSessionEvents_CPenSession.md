# CServiceModule::_ProcessSessionEvents(CPenSession *)

- ea: `0x18000ed70`
- end: `0x18000f0f4`
- name: `?_ProcessSessionEvents@CServiceModule@@AEAAXPEAVCPenSession@@@Z`
- size: `900`
- prototype: `void __fastcall(CServiceModule *__hidden this, struct CPenSession *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x18000f5d0`
- `0x18001506c`

## callees

- `0x18000ed70`
- `0x18000f0fc`
- `0x18000f260`
- `0x18000f428`
- `0x180010fc0`
- `0x180012c70`
- `0x18001bbe0`
- `0x1800244ec`
- `0x1800245fc`
- `0x180024730`
- `0x180026fa8`
- `0x18002b3a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000ee28`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000ee28`

## string_xrefs

- `0x18000ef3c`: `PENSERVICE_CServiceModule::_ProcessSessionEvents`
- `0x18000ef90`: `PENSERVICE_CServiceModule::_ProcessSessionEvents`
- `0x18000efce`: `PENSERVICE_CServiceModule::_ProcessSessionEvents`
- `0x18000f051`: `PENSERVICE_CServiceModule::_ProcessSessionEvents`
- `0x18000f072`: `PENSERVICE_CServiceModule::_ProcessSessionEvents`
- `0x18000f093`: `PENSERVICE_CServiceModule::_ProcessSessionEvents`

## pseudocode

```c
void __fastcall CServiceModule::_ProcessSessionEvents(CServiceModule *this, struct CPenSession *a2)
{
  int v4; // eax
  DWORD v5; // ebx
  void *v6; // rcx
  DWORD v7; // eax
  int v8; // edx
  int v9; // ecx
  bool v10; // zf
  HANDLE Handles[2]; // [rsp+40h] [rbp-A8h] BYREF
  __int128 v12; // [rsp+50h] [rbp-98h]
  __int128 v13; // [rsp+60h] [rbp-88h]
  __int128 v14; // [rsp+70h] [rbp-78h]
  __int64 v15; // [rsp+80h] [rbp-68h]
  _DWORD v16[10]; // [rsp+90h] [rbp-58h]

  while ( 1 )
  {
    v4 = 0;
    *(_OWORD *)Handles = 0;
    v15 = 0;
    v5 = 0;
    v12 = 0;
    v13 = 0;
    v14 = 0;
    do
    {
      if ( v4 == 7 )
      {
        v6 = (void *)*((_QWORD *)a2 + 10);
LABEL_6:
        Handles[v5] = v6;
      }
      else
      {
        switch ( v4 )
        {
          case 0:
            v6 = (void *)*((_QWORD *)a2 + 2);
            goto LABEL_6;
          case 1:
            v6 = (void *)*((_QWORD *)a2 + 8);
            goto LABEL_6;
          case 2:
            v6 = (void *)*((_QWORD *)a2 + 4);
            goto LABEL_6;
          case 3:
            v6 = (void *)*((_QWORD *)a2 + 5);
            goto LABEL_6;
          case 4:
            v6 = (void *)*((_QWORD *)a2 + 6);
            goto LABEL_6;
          case 5:
            v6 = (void *)*((_QWORD *)a2 + 7);
            goto LABEL_6;
          case 6:
            v6 = (void *)*((_QWORD *)a2 + 9);
            goto LABEL_6;
          case 7:
            break;
          case 8:
            v6 = (void *)*((_QWORD *)a2 + 11);
            goto LABEL_6;
        }
      }
      if ( Handles[v5] )
        v16[v5++] = v4;
      ++v4;
    }
    while ( v4 < 9 );
    if ( !v5 )
      break;
    v7 = WaitForMultipleObjectsEx(v5, Handles, 0, 0, 0);
    if ( v7 >= v5 )
      break;
    v9 = v16[v7];
    switch ( v9 )
    {
      case 2:
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_s(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            146,
            WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            "PENSERVICE_CServiceModule::_ProcessSessionEvents");
        CServiceModule::OnSystemTextInputProcessRequest(this, a2);
        break;
      case 8:
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_s(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            150,
            WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            "PENSERVICE_CServiceModule::_ProcessSessionEvents");
        CServiceModule::OnCtfmonRequest(this, a2);
        break;
      case 5:
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_s(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            149,
            WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            "PENSERVICE_CServiceModule::_ProcessSessionEvents");
        CServiceModule::OnSecureDesktopSwitch(this, a2);
        break;
      default:
        switch ( v9 )
        {
          case 0:
            if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
            {
              WPP_SF_s(
                *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
                145,
                WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
                "PENSERVICE_CServiceModule::_ProcessSessionEvents");
            }
            CServiceModule::OnTabtipRequest(this, a2, 0);
            continue;
          case 1:
            CServiceModule::OnTabtipRequest(this, a2, 1);
            continue;
          case 3:
            if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
            {
              WPP_SF_s(
                *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
                147,
                WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
                "PENSERVICE_CServiceModule::_ProcessSessionEvents");
            }
            CServiceModule::OnSystemTabtipRequest(this, a2);
            continue;
          case 4:
            if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
            {
              WPP_SF_s(
                *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
                148,
                WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
                "PENSERVICE_CServiceModule::_ProcessSessionEvents");
            }
            CServiceModule::OnUserDesktopSwitch(this, a2);
            continue;
          case 6:
            if ( !*((_BYTE *)a2 + 8) )
            {
              *((_BYTE *)a2 + 8) = 1;
              ++*((_DWORD *)this + 21);
              CServiceModule::StartEnabledPenProcesses(this);
            }
            continue;
          case 7:
            if ( *((_BYTE *)a2 + 8) )
            {
              *((_BYTE *)a2 + 8) = 0;
              v10 = (*((_DWORD *)this + 21))-- == 1;
              if ( v10 && *((_BYTE *)this + 64) )
                CServiceModule::UpdateHardwarePresenceStatus(this);
              CServiceModule::ShutdownDisabledPenProcesses(this, v8);
            }
            continue;
          default:
            return;
        }
        return;
    }
  }
}

```

## disassembly

```asm
0x18000ed70  mov     [rsp+arg_10], rbx
0x18000ed75  push    rbp
0x18000ed76  push    rsi
0x18000ed77  push    rdi
0x18000ed78  push    r14
0x18000ed7a  push    r15
0x18000ed7c  sub     rsp, 0C0h
0x18000ed83  mov     rax, cs:__security_cookie
0x18000ed8a  xor     rax, rsp
0x18000ed8d  mov     [rsp+0E8h+var_30], rax
0x18000ed95  mov     rsi, rdx
0x18000ed98  lea     rbp, __ImageBase
0x18000ed9f  mov     rdi, rcx
0x18000eda2  lea     r15, WPP_GLOBAL_Control
0x18000eda9  xor     r14d, r14d
0x18000edac  nop     dword ptr [rax+00h]
0x18000edb0  xorps   xmm0, xmm0
0x18000edb3  xor     eax, eax
0x18000edb5  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x18000edba  mov     [rsp+0E8h+var_68], rax
0x18000edc2  mov     ebx, r14d
0x18000edc5  movups  [rsp+0E8h+var_98], xmm0
0x18000edca  movups  [rsp+0E8h+var_88], xmm0
0x18000edcf  movups  [rsp+0E8h+var_78], xmm0
0x18000edd4  cmp     eax, 7
0x18000edd7  jz      short loc_18000EDEE
0x18000edd9  movsxd  rcx, eax
0x18000eddc  mov     edx, ss:(jpt_18000EDE6 - 180000000h)[rbp+rcx*4]; switch 9 cases
0x18000ede3  add     rdx, rbp
0x18000ede6  jmp     rdx; switch jump
0x18000ede8  mov     rcx, [rsi+58h]; jumptable 000000018000EDE6 case 8
0x18000edec  jmp     short loc_18000EDF2
0x18000edee  mov     rcx, [rsi+50h]
0x18000edf2  mov     edx, ebx
0x18000edf4  mov     [rsp+rdx*8+0E8h+Handles], rcx
0x18000edf9  mov     ecx, ebx; jumptable 000000018000EDE6 case 7
0x18000edfb  cmp     [rsp+rcx*8+0E8h+Handles], r14
0x18000ee00  jz      short loc_18000EE0B
0x18000ee02  mov     [rsp+rcx*4+0E8h+var_58], eax
0x18000ee09  inc     ebx
0x18000ee0b  inc     eax
0x18000ee0d  cmp     eax, 9
0x18000ee10  jl      short loc_18000EDD4
0x18000ee12  test    ebx, ebx
0x18000ee14  jz      short def_18000EF24; jumptable 000000018000EF24 default case, cases 2,5
0x18000ee16  xor     r9d, r9d; dwMilliseconds
0x18000ee19  mov     [rsp+0E8h+bAlertable], r14d; bAlertable
0x18000ee1e  xor     r8d, r8d; bWaitAll
0x18000ee21  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18000ee26  mov     ecx, ebx; nCount
0x18000ee28  call    cs:__imp_WaitForMultipleObjectsEx
0x18000ee2e  cmp     eax, ebx
0x18000ee30  jb      short loc_18000EE71
0x18000ee32  mov     rcx, [rsp+0E8h+var_30]; jumptable 000000018000EF24 default case, cases 2,5
0x18000ee3a  xor     rcx, rsp; StackCookie
0x18000ee3d  call    __security_check_cookie
0x18000ee42  mov     rbx, [rsp+0E8h+arg_10]
0x18000ee4a  add     rsp, 0C0h
0x18000ee51  pop     r15
0x18000ee53  pop     r14
0x18000ee55  pop     rdi
0x18000ee56  pop     rsi
0x18000ee57  pop     rbp
0x18000ee58  retn
0x18000ee59  mov     rcx, [rsi+30h]; jumptable 000000018000EDE6 case 4
0x18000ee5d  jmp     short loc_18000EDF2
0x18000ee5f  mov     rcx, [rsi+38h]; jumptable 000000018000EDE6 case 5
0x18000ee63  jmp     short loc_18000EDF2
0x18000ee65  mov     rcx, [rsi+48h]; jumptable 000000018000EDE6 case 6
0x18000ee69  jmp     short loc_18000EDF2
0x18000ee6b  mov     rcx, [rsi+10h]; jumptable 000000018000EDE6 case 0
0x18000ee6f  jmp     short loc_18000EDF2
0x18000ee71  mov     eax, eax
0x18000ee73  movsxd  rcx, [rsp+rax*4+0E8h+var_58]
0x18000ee7b  cmp     ecx, 2
0x18000ee7e  jz      short loc_18000EEAB
0x18000ee80  cmp     ecx, 8
0x18000ee83  jnz     short loc_18000EED1
0x18000ee85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee8c  cmp     rcx, r15
0x18000ee8f  jz      short loc_18000EE9B
0x18000ee91  test    byte ptr [rcx+1Ch], 10h
0x18000ee95  jnz     loc_18000F06E
0x18000ee9b  mov     rdx, rsi; struct CPenSession *
0x18000ee9e  mov     rcx, rdi; this
0x18000eea1  call    ?OnCtfmonRequest@CServiceModule@@QEAAXPEAVCPenSession@@@Z; CServiceModule::OnCtfmonRequest(CPenSession *)
0x18000eea6  jmp     loc_18000EDB0
0x18000eeab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eeb2  cmp     rcx, r15
0x18000eeb5  jz      short loc_18000EEC1
0x18000eeb7  test    byte ptr [rcx+1Ch], 10h
0x18000eebb  jnz     loc_18000F08F
0x18000eec1  mov     rdx, rsi; struct CPenSession *
0x18000eec4  mov     rcx, rdi; this
0x18000eec7  call    ?OnSystemTextInputProcessRequest@CServiceModule@@QEAAXPEAVCPenSession@@@Z; CServiceModule::OnSystemTextInputProcessRequest(CPenSession *)
0x18000eecc  jmp     loc_18000EDB0
0x18000eed1  cmp     ecx, 5
0x18000eed4  jnz     short loc_18000EF11
0x18000eed6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eedd  cmp     rcx, r15
0x18000eee0  jnz     loc_18000F043
0x18000eee6  mov     rdx, rsi; struct CPenSession *
0x18000eee9  mov     rcx, rdi; this
0x18000eeec  call    ?OnSecureDesktopSwitch@CServiceModule@@QEAAXPEAVCPenSession@@@Z; CServiceModule::OnSecureDesktopSwitch(CPenSession *)
0x18000eef1  jmp     loc_18000EDB0
0x18000eef6  mov     rcx, [rsi+40h]; jumptable 000000018000EDE6 case 1
0x18000eefa  jmp     loc_18000EDF2
0x18000eeff  mov     rcx, [rsi+20h]; jumptable 000000018000EDE6 case 2
0x18000ef03  jmp     loc_18000EDF2
0x18000ef08  mov     rcx, [rsi+28h]; jumptable 000000018000EDE6 case 3
0x18000ef0c  jmp     loc_18000EDF2
0x18000ef11  cmp     ecx, 7; switch 8 cases
0x18000ef14  ja      def_18000EF24; jumptable 000000018000EF24 default case, cases 2,5
0x18000ef1a  mov     ecx, ss:(jpt_18000EF24 - 180000000h)[rbp+rcx*4]
0x18000ef21  add     rcx, rbp
0x18000ef24  jmp     rcx; switch jump
0x18000ef26  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018000EF24 case 0
0x18000ef2d  cmp     rcx, r15
0x18000ef30  jz      short loc_18000EF54
0x18000ef32  test    byte ptr [rcx+1Ch], 10h
0x18000ef36  jz      short loc_18000EF54
0x18000ef38  mov     rcx, [rcx+10h]
0x18000ef3c  lea     r9, aPenserviceCser_20; "PENSERVICE_CServiceModule::_ProcessSess"...
0x18000ef43  mov     edx, 91h
0x18000ef48  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000ef4f  call    WPP_SF_s
0x18000ef54  xor     r8d, r8d; bool
0x18000ef57  mov     rdx, rsi; struct CPenSession *
0x18000ef5a  mov     rcx, rdi; Context
0x18000ef5d  call    ?OnTabtipRequest@CServiceModule@@QEAAXPEAVCPenSession@@_N@Z; CServiceModule::OnTabtipRequest(CPenSession *,bool)
0x18000ef62  jmp     loc_18000EDB0
0x18000ef67  mov     r8b, 1; jumptable 000000018000EF24 case 1
0x18000ef6a  mov     rdx, rsi; struct CPenSession *
0x18000ef6d  mov     rcx, rdi; Context
0x18000ef70  call    ?OnTabtipRequest@CServiceModule@@QEAAXPEAVCPenSession@@_N@Z; CServiceModule::OnTabtipRequest(CPenSession *,bool)
0x18000ef75  jmp     loc_18000EDB0
0x18000ef7a  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018000EF24 case 3
0x18000ef81  cmp     rcx, r15
0x18000ef84  jz      short loc_18000EFA8
0x18000ef86  test    byte ptr [rcx+1Ch], 10h
0x18000ef8a  jz      short loc_18000EFA8
0x18000ef8c  mov     rcx, [rcx+10h]
0x18000ef90  lea     r9, aPenserviceCser_20; "PENSERVICE_CServiceModule::_ProcessSess"...
0x18000ef97  mov     edx, 93h
0x18000ef9c  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000efa3  call    WPP_SF_s
0x18000efa8  mov     rdx, rsi; struct CPenSession *
0x18000efab  mov     rcx, rdi; this
0x18000efae  call    ?OnSystemTabtipRequest@CServiceModule@@QEAAXPEAVCPenSession@@@Z; CServiceModule::OnSystemTabtipRequest(CPenSession *)
0x18000efb3  jmp     loc_18000EDB0
0x18000efb8  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018000EF24 case 4
0x18000efbf  cmp     rcx, r15
0x18000efc2  jz      short loc_18000EFE6
0x18000efc4  test    byte ptr [rcx+1Ch], 10h
0x18000efc8  jz      short loc_18000EFE6
0x18000efca  mov     rcx, [rcx+10h]
0x18000efce  lea     r9, aPenserviceCser_20; "PENSERVICE_CServiceModule::_ProcessSess"...
0x18000efd5  mov     edx, 94h
0x18000efda  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000efe1  call    WPP_SF_s
0x18000efe6  mov     rdx, rsi; struct CPenSession *
0x18000efe9  mov     rcx, rdi; Context
0x18000efec  call    ?OnUserDesktopSwitch@CServiceModule@@QEAAXPEAVCPenSession@@@Z; CServiceModule::OnUserDesktopSwitch(CPenSession *)
0x18000eff1  jmp     loc_18000EDB0
0x18000eff6  cmp     [rsi+8], r14b; jumptable 000000018000EF24 case 6
0x18000effa  jnz     loc_18000EDB0
0x18000f000  mov     byte ptr [rsi+8], 1
0x18000f004  mov     rcx, rdi; Context
0x18000f007  inc     dword ptr [rdi+54h]
0x18000f00a  call    ?StartEnabledPenProcesses@CServiceModule@@QEAAXXZ; CServiceModule::StartEnabledPenProcesses(void)
0x18000f00f  jmp     loc_18000EDB0
0x18000f014  cmp     [rsi+8], r14b; jumptable 000000018000EF24 case 7
0x18000f018  jz      loc_18000EDB0
0x18000f01e  mov     [rsi+8], r14b
0x18000f022  sub     dword ptr [rdi+54h], 1
0x18000f026  jnz     short loc_18000F036
0x18000f028  cmp     [rdi+40h], r14b
0x18000f02c  jz      short loc_18000F036
0x18000f02e  mov     rcx, rdi; this
0x18000f031  call    ?UpdateHardwarePresenceStatus@CServiceModule@@QEAAXXZ; CServiceModule::UpdateHardwarePresenceStatus(void)
0x18000f036  mov     rcx, rdi; this
0x18000f039  call    ?ShutdownDisabledPenProcesses@CServiceModule@@QEAAXH@Z; CServiceModule::ShutdownDisabledPenProcesses(int)
0x18000f03e  jmp     loc_18000EDB0
0x18000f043  test    byte ptr [rcx+1Ch], 10h
0x18000f047  jz      loc_18000EEE6
0x18000f04d  mov     rcx, [rcx+10h]
0x18000f051  lea     r9, aPenserviceCser_20; "PENSERVICE_CServiceModule::_ProcessSess"...
0x18000f058  mov     edx, 95h
0x18000f05d  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f064  call    WPP_SF_s
0x18000f069  jmp     loc_18000EEE6
0x18000f06e  mov     rcx, [rcx+10h]
0x18000f072  lea     r9, aPenserviceCser_20; "PENSERVICE_CServiceModule::_ProcessSess"...
0x18000f079  mov     edx, 96h
0x18000f07e  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f085  call    WPP_SF_s
0x18000f08a  jmp     loc_18000EE9B
0x18000f08f  mov     rcx, [rcx+10h]
0x18000f093  lea     r9, aPenserviceCser_20; "PENSERVICE_CServiceModule::_ProcessSess"...
0x18000f09a  mov     edx, 92h
0x18000f09f  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f0a6  call    WPP_SF_s
0x18000f0ab  jmp     loc_18000EEC1
```
