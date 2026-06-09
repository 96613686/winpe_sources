# CMidiXProc::MidiInWorker(void *)

- ea: `0x18000f4e0`
- end: `0x18000f56a`
- name: `?MidiInWorker@CMidiXProc@@CAKPEAX@Z`
- size: `138`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009014`
- `0x18000d854`
- `0x18000d8b0`
- `0x18000f4e0`
- `0x18000f570`
- `0x1800111c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f522`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f522`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f4f1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f4f1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f543`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f543`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidiXProc::MidiInWorker(LPVOID lpThreadParameter)
{
  HRESULT v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  unsigned int v5; // r8d
  const char *v6; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v3, v4, (const char *)(unsigned int)v2, v8);
  if ( lpThreadParameter && (int)EnableMmcss((void **)lpThreadParameter + 9, (DWORD *)lpThreadParameter + 20) >= 0 )
  {
    if ( !SetEvent(*((HANDLE *)lpThreadParameter + 16)) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v5, v6);
    CMidiXProc::ProcessMidiIn((CMidiXProc *)lpThreadParameter);
    DisableMmcss((void **)lpThreadParameter + 9);
  }
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18000f4e0  mov     [rsp+arg_0], rbx
0x18000f4e5  push    rdi; int
0x18000f4e6  sub     rsp, 20h
0x18000f4ea  mov     rbx, rcx
0x18000f4ed  xor     edx, edx; dwCoInit
0x18000f4ef  xor     ecx, ecx; pvReserved
0x18000f4f1  call    cs:__imp_CoInitializeEx
0x18000f4f7  mov     rcx, [rsp+28h]; this
0x18000f4fc  test    eax, eax
0x18000f4fe  js      short loc_18000F561
0x18000f500  mov     [rsp+28h+arg_8], 1
0x18000f505  test    rbx, rbx
0x18000f508  jz      short loc_18000F543
0x18000f50a  lea     rdx, [rbx+50h]
0x18000f50e  lea     rcx, [rbx+48h]
0x18000f512  call    ?EnableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z; EnableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)
0x18000f517  test    eax, eax
0x18000f519  js      short loc_18000F543
0x18000f51b  mov     rcx, [rbx+80h]; hEvent
0x18000f522  call    cs:__imp_SetEvent
0x18000f528  mov     rcx, [rsp+28h]; this
0x18000f52d  test    eax, eax
0x18000f52f  jz      short loc_18000F556
0x18000f531  mov     rcx, rbx; this
0x18000f534  call    ?ProcessMidiIn@CMidiXProc@@AEAAJXZ; CMidiXProc::ProcessMidiIn(void)
0x18000f539  lea     rcx, [rbx+48h]
0x18000f53d  call    ?DisableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DisableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000f542  nop
0x18000f543  call    cs:__imp_CoUninitialize
0x18000f549  xor     eax, eax
0x18000f54b  mov     rbx, [rsp+28h+arg_0]
0x18000f550  add     rsp, 20h
0x18000f554  pop     rdi
0x18000f555  retn
0x18000f556  mov     edx, 0A01h; void *
0x18000f55b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f561  mov     r9d, eax; char *
0x18000f564  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
