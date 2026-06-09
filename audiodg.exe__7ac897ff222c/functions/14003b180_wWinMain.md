# wWinMain

- ea: `0x14003b180`
- end: `0x14003b34b`
- name: `wWinMain`
- size: `459`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14005cf30`

## callees

- `0x140005b40`
- `0x140016a94`
- `0x14003b180`
- `0x14003b354`
- `0x14003e7cc`
- `0x14004bcc4`
- `0x140053e80`
- `0x14005486c`
- `0x140068d1c`
- `0x140069128`
- `0x140069168`
- `0x140083fe4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14003b210`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14003b210`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14003b26f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14003b26f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14003b293`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14003b293`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // ebx
  const unsigned __int16 *CommandLineW; // rax
  int *v10; // r8
  void *v11; // rdx
  LPVOID Context; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v14[8]; // [rsp+28h] [rbp-40h] BYREF

  byte_1400E8080 = 0;
  qword_1400E7FA8 = 0;
  WPP_MAIN_CB = 0;
  qword_1400E7FB0 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_AudioTrace;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WppInitUm(hInstance, hPrevInstance);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, lpCmdLine);
  }
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  McGenEventRegister_EtwEventRegister();
  Context = 0;
  if ( gMaxSize )
  {
    v8 = -2147023649;
    goto LABEL_23;
  }
  gInitialSize = 0x200000;
  gMinSize = 4;
  gMaxSize = 0x8000;
  if ( !InitOnceExecuteOnce(&gRTHeapInitOnce, AERTMemoryInitOnce, 0, &Context) )
  {
    v8 = -2147024882;
    goto LABEL_23;
  }
  if ( ATL::CAtlBaseModule::m_bInitFailed )
  {
    v8 = -1;
    goto LABEL_18;
  }
  v8 = 0;
  CommandLineW = GetCommandLineW();
  if ( CAudioDGModule::ParseCommandLine((CAudioDGModule *)&_AtlModule, CommandLineW, v10) )
  {
    LODWORD(Context) = nShowCmd;
    v14[0] = &_AtlModule;
    v14[1] = &Context;
    v8 = lambda_29a295f24fb795ae86329e868208ab38_::operator()(v14);
    dword_1400E8090 = v8;
    if ( hHandle )
    {
      wil::details::SetEvent((wil::details *)hHandle, v11);
      v8 = dword_1400E8090;
    }
    if ( v8 )
    {
      if ( v8 < 0 )
        goto LABEL_18;
    }
    else
    {
      CAudioDGModule::RunMessageLoop((CAudioDGModule *)&_AtlModule);
    }
    v8 = CAudioDGModule::PostMessageLoop((CAudioDGModule *)&_AtlModule);
  }
LABEL_18:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids, (unsigned int)v8);
  }
  AERTMemoryShutdown();
LABEL_23:
  WppCleanupUm();
  return v8;
}

```

## disassembly

```asm
0x14003b180  push    rbx
0x14003b182  push    rbp
0x14003b183  push    rdi
0x14003b184  push    r14
0x14003b186  sub     rsp, 48h
0x14003b18a  mov     edi, r9d
0x14003b18d  mov     rbx, r8
0x14003b190  mov     cs:byte_1400E8080, 0
0x14003b197  mov     cs:qword_1400E7FA8, 0
0x14003b1a2  mov     cs:WPP_MAIN_CB, 0
0x14003b1ad  mov     cs:qword_1400E7FB0, 1
0x14003b1b8  lea     rax, WPP_ThisDir_CTLGUID_AudioTrace
0x14003b1bf  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x14003b1c6  lea     rax, WPP_MAIN_CB
0x14003b1cd  mov     cs:WPP_GLOBAL_Control, rax
0x14003b1d4  call    WppInitUm
0x14003b1d9  lea     r14, WPP_GLOBAL_Control
0x14003b1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b1e7  cmp     rcx, r14
0x14003b1ea  jz      short loc_14003B204
0x14003b1ec  test    byte ptr [rcx+1Ch], 10h
0x14003b1f0  jz      short loc_14003B204
0x14003b1f2  cmp     byte ptr [rcx+19h], 4
0x14003b1f6  jb      short loc_14003B204
0x14003b1f8  mov     r9, rbx
0x14003b1fb  mov     rcx, [rcx+10h]
0x14003b1ff  call    WPP_SF_S
0x14003b204  xor     r9d, r9d; HeapInformationLength
0x14003b207  xor     r8d, r8d; HeapInformation
0x14003b20a  lea     edx, [r9+1]; HeapInformationClass
0x14003b20e  xor     ecx, ecx; HeapHandle
0x14003b210  call    cs:__imp_HeapSetInformation
0x14003b216  call    McGenEventRegister_EtwEventRegister
0x14003b21b  mov     [rsp+68h+Context], 0
0x14003b224  cmp     cs:?gMaxSize@@3_KA, 0; unsigned __int64 gMaxSize
0x14003b22c  jz      short loc_14003B238
0x14003b22e  mov     ebx, 800704DFh
0x14003b233  jmp     loc_14003B33A
0x14003b238  mov     cs:?gInitialSize@@3_KA, 200000h; unsigned __int64 gInitialSize
0x14003b243  mov     cs:?gMinSize@@3_KA, 4; unsigned __int64 gMinSize
0x14003b24e  mov     cs:?gMaxSize@@3_KA, 8000h; unsigned __int64 gMaxSize
0x14003b259  lea     r9, [rsp+68h+Context]; Context
0x14003b25e  xor     r8d, r8d; Parameter
0x14003b261  lea     rdx, ?AERTMemoryInitOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x14003b268  lea     rcx, ?gRTHeapInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x14003b26f  call    cs:__imp_InitOnceExecuteOnce
0x14003b275  test    eax, eax
0x14003b277  jnz     short loc_14003B283
0x14003b279  mov     ebx, 8007000Eh
0x14003b27e  jmp     loc_14003B33A
0x14003b283  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x14003b28a  jz      short loc_14003B291
0x14003b28c  or      ebx, 0FFFFFFFFh
0x14003b28f  jmp     short loc_14003B305
0x14003b291  xor     ebx, ebx
0x14003b293  call    cs:__imp_GetCommandLineW
0x14003b299  mov     rdx, rax; unsigned __int16 *
0x14003b29c  lea     rbp, ?_AtlModule@@3VCAudioDGModule@@A; CAudioDGModule _AtlModule
0x14003b2a3  mov     rcx, rbp; this
0x14003b2a6  call    ?ParseCommandLine@CAudioDGModule@@QEAA_NPEBGPEAJ@Z; CAudioDGModule::ParseCommandLine(ushort const *,long *)
0x14003b2ab  cmp     al, 1
0x14003b2ad  jnz     short loc_14003B305
0x14003b2af  mov     dword ptr [rsp+68h+Context], edi
0x14003b2b3  mov     [rsp+68h+var_40], rbp
0x14003b2b8  lea     rax, [rsp+68h+Context]
0x14003b2bd  mov     [rsp+68h+var_38], rax
0x14003b2c2  lea     rcx, [rsp+68h+var_40]
0x14003b2c7  call    _lambda_29a295f24fb795ae86329e868208ab38___operator__
0x14003b2cc  mov     ebx, eax
0x14003b2ce  mov     cs:dword_1400E8090, eax
0x14003b2d4  mov     rcx, cs:hHandle; this
0x14003b2db  test    rcx, rcx
0x14003b2de  jz      short loc_14003B2EB
0x14003b2e0  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14003b2e5  mov     ebx, cs:dword_1400E8090
0x14003b2eb  test    ebx, ebx
0x14003b2ed  jnz     short loc_14003B2F9
0x14003b2ef  mov     rcx, rbp; this
0x14003b2f2  call    ?RunMessageLoop@CAudioDGModule@@QEAAJXZ; CAudioDGModule::RunMessageLoop(void)
0x14003b2f7  jmp     short loc_14003B2FB
0x14003b2f9  js      short loc_14003B305
0x14003b2fb  mov     rcx, rbp; this
0x14003b2fe  call    ?PostMessageLoop@CAudioDGModule@@QEAAJXZ; CAudioDGModule::PostMessageLoop(void)
0x14003b303  mov     ebx, eax
0x14003b305  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b30c  cmp     rcx, r14
0x14003b30f  jz      short loc_14003B335
0x14003b311  test    byte ptr [rcx+1Ch], 10h
0x14003b315  jz      short loc_14003B335
0x14003b317  cmp     byte ptr [rcx+19h], 4
0x14003b31b  jb      short loc_14003B335
0x14003b31d  mov     edx, 19h
0x14003b322  mov     r9d, ebx
0x14003b325  lea     r8, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids
0x14003b32c  mov     rcx, [rcx+10h]
0x14003b330  call    WPP_SF_d
0x14003b335  call    ?AERTMemoryShutdown@@YAJXZ; AERTMemoryShutdown(void)
0x14003b33a  call    WppCleanupUm
0x14003b33f  mov     eax, ebx
0x14003b341  add     rsp, 48h
0x14003b345  pop     r14
0x14003b347  pop     rdi
0x14003b348  pop     rbp
0x14003b349  pop     rbx
0x14003b34a  retn
```
