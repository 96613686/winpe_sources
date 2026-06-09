# CTieringEngineService::OnStop(void)

- ea: `0x1400037bc`
- end: `0x1400038ba`
- name: `?OnStop@CTieringEngineService@@QEAAXXZ`
- size: `254`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400047e0`

## callees

- `0x1400037bc`
- `0x1400045d0`
- `0x1400046d4`
- `0x140004a10`
- `0x140004a40`
- `0x140004a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000387b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000387b`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140003861`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140003861`

## pseudocode

```c
void __fastcall CTieringEngineService::OnStop(HANDLE *this)
{
  unsigned int v2; // eax
  REGHANDLE v3; // rcx

  CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(this, 3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
  }
  CTieringEngineService::WaitForTieringEngineToStop((CTieringEngineService *)this);
  v2 = McGenEventUnregister_EventUnregister();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids, v2);
  }
  v3 = RegHandle;
  dword_14004C098 = 0;
  RegHandle = 0;
  EventUnregister(v3);
  CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(this, 1);
  SetEvent(this[84]);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
  }
}

```

## disassembly

```asm
0x1400037bc  mov     [rsp+arg_0], rbx
0x1400037c1  push    r14
0x1400037c3  sub     rsp, 20h
0x1400037c7  mov     edx, 3
0x1400037cc  mov     rbx, rcx
0x1400037cf  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x1400037d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037db  lea     r14, WPP_GLOBAL_Control
0x1400037e2  cmp     rcx, r14
0x1400037e5  jz      short loc_140003808
0x1400037e7  test    byte ptr [rcx+1Ch], 1
0x1400037eb  jz      short loc_140003808
0x1400037ed  cmp     byte ptr [rcx+19h], 4
0x1400037f1  jb      short loc_140003808
0x1400037f3  mov     rcx, [rcx+10h]
0x1400037f7  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x1400037fe  mov     edx, 16h
0x140003803  call    WPP_SF_
0x140003808  mov     rcx, rbx; this
0x14000380b  call    ?WaitForTieringEngineToStop@CTieringEngineService@@QEAAXXZ; CTieringEngineService::WaitForTieringEngineToStop(void)
0x140003810  call    McGenEventUnregister_EventUnregister
0x140003815  mov     rcx, cs:WPP_GLOBAL_Control
0x14000381c  cmp     rcx, r14
0x14000381f  jz      short loc_140003845
0x140003821  test    byte ptr [rcx+1Ch], 1
0x140003825  jz      short loc_140003845
0x140003827  cmp     byte ptr [rcx+19h], 4
0x14000382b  jb      short loc_140003845
0x14000382d  mov     rcx, [rcx+10h]
0x140003831  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140003838  mov     edx, 17h
0x14000383d  mov     r9d, eax
0x140003840  call    WPP_SF_d
0x140003845  mov     rcx, cs:RegHandle; RegHandle
0x14000384c  mov     cs:dword_14004C098, 0
0x140003856  mov     cs:RegHandle, 0
0x140003861  call    cs:__imp_EventUnregister
0x140003867  mov     edx, 1
0x14000386c  mov     rcx, rbx
0x14000386f  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x140003874  mov     rcx, [rbx+2A0h]; hEvent
0x14000387b  call    cs:__imp_SetEvent
0x140003881  mov     rcx, cs:WPP_GLOBAL_Control
0x140003888  cmp     rcx, r14
0x14000388b  jz      short loc_1400038AE
0x14000388d  test    byte ptr [rcx+1Ch], 1
0x140003891  jz      short loc_1400038AE
0x140003893  cmp     byte ptr [rcx+19h], 4
0x140003897  jb      short loc_1400038AE
0x140003899  mov     rcx, [rcx+10h]
0x14000389d  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x1400038a4  mov     edx, 18h
0x1400038a9  call    WPP_SF_
0x1400038ae  mov     rbx, [rsp+28h+arg_0]
0x1400038b3  add     rsp, 20h
0x1400038b7  pop     r14
0x1400038b9  retn
```
