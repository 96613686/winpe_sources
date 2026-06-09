# ShieldProvider::ShieldProviderMain::Initialize(void)

- ea: `0x14000373c`
- end: `0x140003852`
- name: `?Initialize@ShieldProviderMain@ShieldProvider@@QEAAJXZ`
- size: `278`
- prototype: `__int64 __fastcall(ShieldProvider::ShieldProviderMain *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x140003640`
- `0x14000373c`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400037b3`
- `KERNEL32!GetLastError` at `0x1400037b3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14000378d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14000378d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1400037a4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1400037a4`

## string_xrefs

- `0x14000379d`: `SecurityHealthService`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldProviderMain::Initialize(ShieldProvider::ShieldProviderMain *this)
{
  struct ShieldProvider::ShieldProviderMain *v1; // rdi
  BOOL v2; // ecx
  SERVICE_STATUS_HANDLE v3; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  v1 = ShieldProvider::g_pMain;
  v2 = ShieldProvider::g_fDevMode;
  *((_DWORD *)ShieldProvider::g_pMain + 14) = 16;
  *((_DWORD *)v1 + 16) = v2 + 448;
  *(_QWORD *)((char *)v1 + 68) = 0;
  *((_DWORD *)v1 + 15) = 1;
  *(_QWORD *)((char *)v1 + 76) = 0;
  *((_DWORD *)v1 + 5) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)v1 + 8), 0);
  v3 = RegisterServiceCtrlHandlerExW(L"SecurityHealthService", ShieldProvider::ShieldProviderMain::s_ServiceHandler, 0);
  *((_QWORD *)v1 + 6) = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v5;
      v7 = 11;
LABEL_8:
      WPP_SF_d(v6[2], v7, WPP_67aca3ab02c63d3dd3f4137d6d70ea03_Traceguids, v5);
      return v5;
    }
  }
  v5 = (*(__int64 (__fastcall **)(struct ShieldProvider::ShieldProviderMain *, __int64, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
         v1,
         2,
         1,
         30000);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v5;
    v7 = 12;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x14000373c  mov     [rsp+arg_0], rbx
0x140003741  push    rdi
0x140003742  sub     rsp, 30h
0x140003746  mov     al, cs:?g_fDevMode@ShieldProvider@@3_NA; bool ShieldProvider::g_fDevMode
0x14000374c  mov     rdi, cs:?g_pMain@ShieldProvider@@3PEAVShieldProviderMain@1@EA; ShieldProvider::ShieldProviderMain * ShieldProvider::g_pMain
0x140003753  neg     al
0x140003755  sbb     ecx, ecx
0x140003757  xor     edx, edx; dwSpinCount
0x140003759  neg     ecx
0x14000375b  add     ecx, 1C0h
0x140003761  mov     dword ptr [rdi+38h], 10h
0x140003768  mov     [rdi+40h], ecx
0x14000376b  lea     rcx, [rdi+8]; lpCriticalSection
0x14000376f  mov     qword ptr [rdi+44h], 0
0x140003777  mov     dword ptr [rdi+3Ch], 1
0x14000377e  mov     qword ptr [rdi+4Ch], 0
0x140003786  mov     dword ptr [rcx+0Ch], 0
0x14000378d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140003793  xor     r8d, r8d; lpContext
0x140003796  lea     rdx, ?s_ServiceHandler@ShieldProviderMain@ShieldProvider@@SAKKKPEAX0@Z; lpHandlerProc
0x14000379d  lea     rcx, ServiceName; "SecurityHealthService"
0x1400037a4  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1400037aa  mov     [rdi+30h], rax
0x1400037ae  test    rax, rax
0x1400037b1  jnz     short loc_140003801
0x1400037b3  call    cs:__imp_GetLastError
0x1400037b9  mov     ebx, eax
0x1400037bb  test    eax, eax
0x1400037bd  jle     short loc_1400037C8
0x1400037bf  movzx   ebx, ax
0x1400037c2  or      ebx, 80070000h
0x1400037c8  test    ebx, ebx
0x1400037ca  jns     short loc_140003801
0x1400037cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037d3  lea     rax, WPP_GLOBAL_Control
0x1400037da  cmp     rcx, rax
0x1400037dd  jz      short loc_1400037FD
0x1400037df  test    byte ptr [rcx+1Ch], 1
0x1400037e3  jz      short loc_1400037FD
0x1400037e5  mov     edx, 0Bh
0x1400037ea  mov     rcx, [rcx+10h]
0x1400037ee  lea     r8, WPP_67aca3ab02c63d3dd3f4137d6d70ea03_Traceguids
0x1400037f5  mov     r9d, ebx
0x1400037f8  call    WPP_SF_d
0x1400037fd  mov     eax, ebx
0x1400037ff  jmp     short loc_140003847
0x140003801  mov     rax, [rdi]
0x140003804  mov     edx, 2
0x140003809  mov     r9d, 7530h
0x14000380f  mov     rcx, rdi
0x140003812  mov     rax, [rax+18h]
0x140003816  lea     r8d, [rdx-1]
0x14000381a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000381f  mov     ebx, eax
0x140003821  test    eax, eax
0x140003823  jns     short loc_140003845
0x140003825  mov     rcx, cs:WPP_GLOBAL_Control
0x14000382c  lea     rax, WPP_GLOBAL_Control
0x140003833  cmp     rcx, rax
0x140003836  jz      short loc_1400037FD
0x140003838  test    byte ptr [rcx+1Ch], 1
0x14000383c  jz      short loc_1400037FD
0x14000383e  mov     edx, 0Ch
0x140003843  jmp     short loc_1400037EA
0x140003845  xor     eax, eax
0x140003847  mov     rbx, [rsp+38h+arg_0]
0x14000384c  add     rsp, 30h
0x140003850  pop     rdi
0x140003851  retn
```
