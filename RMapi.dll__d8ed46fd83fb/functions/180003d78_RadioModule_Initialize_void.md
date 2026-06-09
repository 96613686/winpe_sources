# RadioModule::Initialize(void)

- ea: `0x180003d78`
- end: `0x180003e7d`
- name: `?Initialize@RadioModule@@QEAAJXZ`
- size: `261`
- prototype: `__int64 __fastcall(RadioModule *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800029e0`

## callees

- `0x180002ec0`
- `0x180003d50`
- `0x180003d78`
- `0x180003e84`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180003e03`
- `combase!__imp_CoGetSharedServiceId` at `0x180003e03`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180003dc2`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180003e3d`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180003dc2`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180003e3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RadioModule::Initialize(RadioModule *this)
{
  RadioModule *v1; // rsi
  int v2; // eax
  int SharedServiceId; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx

  v1 = g_ComServerModule;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids);
  v2 = CoRegisterServerShutdownDelay(g_ServiceStopEvent, 30000);
  SharedServiceId = v2;
  if ( v2 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        17,
        WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids,
        (unsigned int)v2);
    return (unsigned int)SharedServiceId;
  }
  SharedServiceId = CoGetSharedServiceId((char *)v1 + 24);
  if ( SharedServiceId < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v6 = 18;
LABEL_13:
    WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids, (unsigned int)SharedServiceId);
LABEL_14:
    CoRegisterServerShutdownDelay(0, 0);
    *((_DWORD *)v1 + 6) = 0;
    return (unsigned int)SharedServiceId;
  }
  SharedServiceId = RadioModule::COMRegisterClassObjects(v1);
  if ( SharedServiceId < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v6 = 19;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x180003d78  push    rbx
0x180003d7a  push    rbp
0x180003d7b  push    rsi
0x180003d7c  push    rdi
0x180003d7d  sub     rsp, 28h
0x180003d81  mov     rsi, cs:?g_ComServerModule@@3PEAVRadioModule@@EA; RadioModule * g_ComServerModule
0x180003d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d8f  lea     rbp, WPP_GLOBAL_Control
0x180003d96  cmp     rcx, rbp
0x180003d99  jz      short loc_180003DB6
0x180003d9b  test    byte ptr [rcx+1Ch], 4
0x180003d9f  jz      short loc_180003DB6
0x180003da1  mov     rcx, [rcx+10h]
0x180003da5  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180003dac  mov     edx, 10h
0x180003db1  call    WPP_SF_
0x180003db6  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; void * g_ServiceStopEvent
0x180003dbd  mov     edx, 7530h
0x180003dc2  call    cs:__imp_CoRegisterServerShutdownDelay
0x180003dc8  mov     ebx, eax
0x180003dca  test    eax, eax
0x180003dcc  jns     short loc_180003DFC
0x180003dce  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dd5  cmp     rcx, rbp
0x180003dd8  jz      short loc_180003DF8
0x180003dda  test    byte ptr [rcx+1Ch], 1
0x180003dde  jz      short loc_180003DF8
0x180003de0  mov     rcx, [rcx+10h]
0x180003de4  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180003deb  mov     edx, 11h
0x180003df0  mov     r9d, eax
0x180003df3  call    WPP_SF_d
0x180003df8  mov     eax, ebx
0x180003dfa  jmp     short loc_180003E74
0x180003dfc  lea     rdi, [rsi+18h]
0x180003e00  mov     rcx, rdi
0x180003e03  call    cs:__imp_CoGetSharedServiceId
0x180003e09  mov     ebx, eax
0x180003e0b  test    eax, eax
0x180003e0d  jns     short loc_180003E4B
0x180003e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e16  cmp     rcx, rbp
0x180003e19  jz      short loc_180003E39
0x180003e1b  test    byte ptr [rcx+1Ch], 1
0x180003e1f  jz      short loc_180003E39
0x180003e21  mov     edx, 12h
0x180003e26  mov     rcx, [rcx+10h]
0x180003e2a  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180003e31  mov     r9d, ebx
0x180003e34  call    WPP_SF_d
0x180003e39  xor     edx, edx
0x180003e3b  xor     ecx, ecx
0x180003e3d  call    cs:__imp_CoRegisterServerShutdownDelay
0x180003e43  mov     dword ptr [rdi], 0
0x180003e49  jmp     short loc_180003DF8
0x180003e4b  mov     rcx, rsi; this
0x180003e4e  call    ?COMRegisterClassObjects@RadioModule@@AEAAJXZ; RadioModule::COMRegisterClassObjects(void)
0x180003e53  mov     ebx, eax
0x180003e55  test    eax, eax
0x180003e57  jns     short loc_180003E72
0x180003e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e60  cmp     rcx, rbp
0x180003e63  jz      short loc_180003E39
0x180003e65  test    byte ptr [rcx+1Ch], 1
0x180003e69  jz      short loc_180003E39
0x180003e6b  mov     edx, 13h
0x180003e70  jmp     short loc_180003E26
0x180003e72  xor     eax, eax
0x180003e74  add     rsp, 28h
0x180003e78  pop     rdi
0x180003e79  pop     rsi
0x180003e7a  pop     rbp
0x180003e7b  pop     rbx
0x180003e7c  retn
```
