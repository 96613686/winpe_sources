# CMyAtlServiceModuleT<CTieringEngineService,102>::_Handler(ulong)

- ea: `0x1400047e0`
- end: `0x1400048b0`
- name: `?_Handler@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@KAXK@Z`
- size: `208`
- prototype: `void __fastcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x1400037bc`
- `0x1400045d0`
- `0x1400046d4`
- `0x1400047e0`
- `0x140004a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004868`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004868`

## pseudocode

```c
void __fastcall CMyAtlServiceModuleT<CTieringEngineService,102>::_Handler(DWORD dwControl)
{
  HANDLE *v1; // rbx
  DWORD v2; // ecx

  v1 = (HANDLE *)ATL::_pAtlModule;
  v2 = dwControl - 1;
  if ( v2 )
  {
    if ( v2 == 4 )
    {
      CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ATL::_pAtlModule, 3);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
      }
      CTieringEngineService::WaitForTieringEngineToStop((CTieringEngineService *)v1);
      CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(v1, 1);
      SetEvent(v1[84]);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
      }
    }
  }
  else
  {
    CTieringEngineService::OnStop(ATL::_pAtlModule);
  }
}

```

## disassembly

```asm
0x1400047e0  mov     [rsp+arg_0], rbx
0x1400047e5  push    rdi
0x1400047e6  sub     rsp, 20h
0x1400047ea  mov     rbx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400047f1  sub     ecx, 1
0x1400047f4  jz      loc_14000489D
0x1400047fa  mov     edx, 3
0x1400047ff  sub     ecx, edx
0x140004801  jz      loc_1400048A5
0x140004807  cmp     ecx, 1
0x14000480a  jnz     loc_1400048A5
0x140004810  mov     rcx, rbx
0x140004813  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x140004818  mov     rcx, cs:WPP_GLOBAL_Control
0x14000481f  lea     rdi, WPP_GLOBAL_Control
0x140004826  cmp     rcx, rdi
0x140004829  jz      short loc_14000484C
0x14000482b  test    byte ptr [rcx+1Ch], 1
0x14000482f  jz      short loc_14000484C
0x140004831  cmp     byte ptr [rcx+19h], 4
0x140004835  jb      short loc_14000484C
0x140004837  mov     rcx, [rcx+10h]
0x14000483b  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004842  mov     edx, 19h
0x140004847  call    WPP_SF_
0x14000484c  mov     rcx, rbx; this
0x14000484f  call    ?WaitForTieringEngineToStop@CTieringEngineService@@QEAAXXZ; CTieringEngineService::WaitForTieringEngineToStop(void)
0x140004854  mov     edx, 1
0x140004859  mov     rcx, rbx
0x14000485c  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x140004861  mov     rcx, [rbx+2A0h]; hEvent
0x140004868  call    cs:__imp_SetEvent
0x14000486e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004875  cmp     rcx, rdi
0x140004878  jz      short loc_1400048A5
0x14000487a  test    byte ptr [rcx+1Ch], 1
0x14000487e  jz      short loc_1400048A5
0x140004880  cmp     byte ptr [rcx+19h], 4
0x140004884  jb      short loc_1400048A5
0x140004886  mov     rcx, [rcx+10h]
0x14000488a  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004891  mov     edx, 1Ah
0x140004896  call    WPP_SF_
0x14000489b  jmp     short loc_1400048A5
0x14000489d  mov     rcx, rbx; this
0x1400048a0  call    ?OnStop@CTieringEngineService@@QEAAXXZ; CTieringEngineService::OnStop(void)
0x1400048a5  mov     rbx, [rsp+28h+arg_0]
0x1400048aa  add     rsp, 20h
0x1400048ae  pop     rdi
0x1400048af  retn
```
