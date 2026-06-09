# CMidiXProc::MidiInWorker(void *)

- ea: `0x140046bf0`
- end: `0x140046c86`
- name: `?MidiInWorker@CMidiXProc@@CAKPEAX@Z`
- size: `150`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000c55c`
- `0x1400261b4`
- `0x140046548`
- `0x1400465a4`
- `0x140046bf0`
- `0x140046c8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140046c32`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140046c32`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140046c53`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140046c53`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140046c01`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140046c01`

## string_xrefs

- `0x140046c74`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidiXProc::MidiInWorker(LPVOID lpThreadParameter)
{
  HRESULT v2; // eax
  __int64 v3; // r8
  const char *v4; // r9
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      v6);
  if ( lpThreadParameter && (int)EnableMmcss((void **)lpThreadParameter + 9, (DWORD *)lpThreadParameter + 20) >= 0 )
  {
    if ( !SetEvent(*((HANDLE *)lpThreadParameter + 16)) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v3, v4);
    CMidiXProc::ProcessMidiIn((CMidiXProc *)lpThreadParameter);
    DisableMmcss((void **)lpThreadParameter + 9);
  }
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140046bf0  mov     [rsp+arg_0], rbx
0x140046bf5  push    rdi; int
0x140046bf6  sub     rsp, 20h
0x140046bfa  mov     rbx, rcx
0x140046bfd  xor     edx, edx; dwCoInit
0x140046bff  xor     ecx, ecx; pvReserved
0x140046c01  call    cs:__imp_CoInitializeEx
0x140046c07  mov     rcx, [rsp+28h]; this
0x140046c0c  test    eax, eax
0x140046c0e  js      short loc_140046C71
0x140046c10  mov     [rsp+28h+arg_8], 1
0x140046c15  test    rbx, rbx
0x140046c18  jz      short loc_140046C53
0x140046c1a  lea     rdx, [rbx+50h]
0x140046c1e  lea     rcx, [rbx+48h]
0x140046c22  call    ?EnableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z; EnableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)
0x140046c27  test    eax, eax
0x140046c29  js      short loc_140046C53
0x140046c2b  mov     rcx, [rbx+80h]; hEvent
0x140046c32  call    cs:__imp_SetEvent
0x140046c38  mov     rcx, [rsp+28h]; this
0x140046c3d  test    eax, eax
0x140046c3f  jz      short loc_140046C66
0x140046c41  mov     rcx, rbx; this
0x140046c44  call    ?ProcessMidiIn@CMidiXProc@@AEAAJXZ; CMidiXProc::ProcessMidiIn(void)
0x140046c49  lea     rcx, [rbx+48h]
0x140046c4d  call    ?DisableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DisableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x140046c52  nop
0x140046c53  call    cs:__imp_CoUninitialize
0x140046c59  xor     eax, eax
0x140046c5b  mov     rbx, [rsp+28h+arg_0]
0x140046c60  add     rsp, 20h
0x140046c64  pop     rdi
0x140046c65  retn
0x140046c66  mov     edx, 0A01h; void *
0x140046c6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140046c71  mov     r9d, eax; char *
0x140046c74  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140046c7b  mov     edx, 14D3h; void *
0x140046c80  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
