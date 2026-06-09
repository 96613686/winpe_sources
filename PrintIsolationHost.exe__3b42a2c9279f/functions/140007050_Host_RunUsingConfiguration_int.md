# Host::RunUsingConfiguration(int)

- ea: `0x140007050`
- end: `0x140007149`
- name: `?RunUsingConfiguration@Host@@QEAAJH@Z`
- size: `249`
- prototype: `__int64 __fastcall(IUnknown *this, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006694`

## callees

- `0x14000634c`
- `0x140006dcc`
- `0x140007050`

## import_xrefs

- `KERNEL32!Sleep` at `0x14000711c`
- `KERNEL32!Sleep` at `0x14000711c`
- `USER32!GetMessageW` at `0x1400070c2`
- `USER32!GetMessageW` at `0x1400070c2`
- `USER32!DispatchMessageW` at `0x1400070af`
- `USER32!DispatchMessageW` at `0x1400070af`
- `USER32!TranslateMessage` at `0x1400070a4`
- `USER32!TranslateMessage` at `0x1400070a4`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400070f5`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400070f5`

## string_xrefs

- `0x14000706f`: `Host::RunUsingConfiguration`
- `0x140007130`: `Host::RunUsingConfiguration`

## pseudocode

```c
__int64 __fastcall Host::RunUsingConfiguration(IUnknown *this, DWORD a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rdi
  __int64 *v5; // rax
  DWORD v6; // ecx
  MSG Msg; // [rsp+20h] [rbp-38h] BYREF

  if ( ATL::CAtlBaseModule::m_bInitFailed )
  {
    v2 = -2147467259;
    SandboxTelemetry::WriteDbgTraceError(
      "Host::RunUsingConfiguration",
      L"Sandbox Host: CAtlBaseModule::m_bInitFailed failed");
    return v2;
  }
  v3 = Host::PreMessageLoop(this, a2);
  v2 = v3;
  if ( !v3 )
  {
    memset(&Msg, 0, sizeof(Msg));
    while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    goto LABEL_9;
  }
  if ( v3 >= 0 )
  {
LABEL_9:
    v4 = off_14000C0E0;
    v2 = 0;
    v5 = off_14000C0E8;
    while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 && !v2 )
    {
      if ( *v4 )
      {
        v6 = *((_DWORD *)*v4 + 10);
        if ( v6 )
        {
          v2 = CoRevokeClassObject(v6);
          v5 = off_14000C0E8;
        }
      }
      ++v4;
    }
    if ( byte_14000C580 )
      Sleep(dword_14000C57C);
  }
  if ( (v2 & 0x80000000) != 0 )
    SandboxTelemetry::WriteDbgTraceError("Host::RunUsingConfiguration", L"Sandbox Host: Run failed. Error hr: 0x%x", v2);
  return v2;
}

```

## disassembly

```asm
0x140007050  mov     [rsp+arg_0], rbx
0x140007055  push    rdi
0x140007056  sub     rsp, 50h
0x14000705a  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x140007061  jz      short loc_140007080
0x140007063  lea     rdx, aSandboxHostCat; "Sandbox Host: CAtlBaseModule::m_bInitFa"...
0x14000706a  mov     ebx, 80004005h
0x14000706f  lea     rcx, aHostRunusingco; "Host::RunUsingConfiguration"
0x140007076  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000707b  jmp     loc_14000713C
0x140007080  call    ?PreMessageLoop@Host@@QEAAJH@Z; Host::PreMessageLoop(int)
0x140007085  mov     ebx, eax
0x140007087  test    eax, eax
0x140007089  jnz     short loc_1400070CE
0x14000708b  xorps   xmm0, xmm0
0x14000708e  movups  xmmword ptr [rsp+58h+Msg.hwnd], xmm0
0x140007093  movups  xmmword ptr [rsp+58h+Msg.wParam], xmm0
0x140007098  movups  xmmword ptr [rsp+58h+Msg.time], xmm0
0x14000709d  jmp     short loc_1400070B5
0x14000709f  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400070a4  call    cs:__imp_TranslateMessage
0x1400070aa  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400070af  call    cs:__imp_DispatchMessageW
0x1400070b5  xor     r9d, r9d; wMsgFilterMax
0x1400070b8  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400070bd  xor     r8d, r8d; wMsgFilterMin
0x1400070c0  xor     edx, edx; hWnd
0x1400070c2  call    cs:__imp_GetMessageW
0x1400070c8  test    eax, eax
0x1400070ca  jg      short loc_14000709F
0x1400070cc  jmp     short loc_1400070D0
0x1400070ce  js      short loc_140007122
0x1400070d0  mov     rdi, cs:off_14000C0E0
0x1400070d7  xor     ebx, ebx
0x1400070d9  mov     rax, cs:off_14000C0E8
0x1400070e0  jmp     short loc_140007108
0x1400070e2  test    ebx, ebx
0x1400070e4  jnz     short loc_14000710D
0x1400070e6  mov     rcx, [rdi]
0x1400070e9  test    rcx, rcx
0x1400070ec  jz      short loc_140007104
0x1400070ee  mov     ecx, [rcx+28h]; dwRegister
0x1400070f1  test    ecx, ecx
0x1400070f3  jz      short loc_140007104
0x1400070f5  call    cs:__imp_CoRevokeClassObject
0x1400070fb  mov     ebx, eax
0x1400070fd  mov     rax, cs:off_14000C0E8
0x140007104  add     rdi, 8
0x140007108  cmp     rdi, rax
0x14000710b  jb      short loc_1400070E2
0x14000710d  cmp     cs:byte_14000C580, 0
0x140007114  jz      short loc_140007122
0x140007116  mov     ecx, cs:dword_14000C57C; dwMilliseconds
0x14000711c  call    cs:__imp_Sleep
0x140007122  test    ebx, ebx
0x140007124  jns     short loc_14000713C
0x140007126  mov     r8d, ebx
0x140007129  lea     rdx, aSandboxHostRun; "Sandbox Host: Run failed. Error hr: 0x%"...
0x140007130  lea     rcx, aHostRunusingco; "Host::RunUsingConfiguration"
0x140007137  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000713c  mov     eax, ebx
0x14000713e  mov     rbx, [rsp+58h+arg_0]
0x140007143  add     rsp, 50h
0x140007147  pop     rdi
0x140007148  retn
```
