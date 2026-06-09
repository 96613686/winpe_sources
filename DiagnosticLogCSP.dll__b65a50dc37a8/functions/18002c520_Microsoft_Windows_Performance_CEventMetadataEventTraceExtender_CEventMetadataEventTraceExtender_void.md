# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)

- ea: `0x18002c520`
- end: `0x18002c6f7`
- name: `??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `471`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002cf08`

## callees

- `0x180001bb4`
- `0x18002834c`
- `0x18002c520`
- `0x180039010`

## string_xrefs

- `0x18002c5af`: `tdh.dll`
- `0x18002c5a4`: `api-ms-win-eventing-tdh-l1-1-0.dll`
- `0x18002c65c`: `ext-ms-win-eventing-tdh-ext-l1-1-0.dll`
- `0x18002c6b6`: `TdhLoadManifestFromBinary`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax

  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable';
  *((_BYTE *)this + 32) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  v2 = operator new(0x78u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *((_QWORD *)this + 5) = v2;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 17) = L"tdh.dll";
  *((_BYTE *)this + 144) = 0;
  *((_QWORD *)this + 19) = (char *)this + 120;
  *((_QWORD *)this + 20) = "TdhQueryProviderFieldInformation";
  *((_QWORD *)this + 21) = 0;
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  v3 = operator new(0x68u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *((_QWORD *)this + 26) = v3;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 30) = L"tdh.dll";
  *((_BYTE *)this + 248) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = L"ext-ms-win-eventing-tdh-ext-l1-1-0.dll";
  *((_QWORD *)this + 34) = L"tdh.dll";
  *((_BYTE *)this + 280) = 0;
  *((_QWORD *)this + 36) = (char *)this + 224;
  *((_QWORD *)this + 37) = "TdhGetEventInformation";
  *((_QWORD *)this + 38) = 0;
  *((_BYTE *)this + 312) = 0;
  *((_QWORD *)this + 40) = (char *)this + 224;
  *((_QWORD *)this + 41) = "TdhGetEventMapInformation";
  *((_QWORD *)this + 42) = 0;
  *((_BYTE *)this + 344) = 0;
  *((_QWORD *)this + 44) = (char *)this + 256;
  *((_QWORD *)this + 45) = "TdhLoadManifestFromBinary";
  *((_QWORD *)this + 46) = 0;
  *((_BYTE *)this + 376) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 36) )
    *((_BYTE *)this + 32) = 1;
  return this;
}

```

## disassembly

```asm
0x18002c520  mov     [rsp+arg_10], rbx
0x18002c525  mov     [rsp+arg_18], rbp
0x18002c52a  mov     [rsp+arg_0], rcx
0x18002c52f  push    rsi
0x18002c530  push    rdi
0x18002c531  push    r14
0x18002c533  sub     rsp, 20h
0x18002c537  mov     rdi, rcx
0x18002c53a  xor     r14d, r14d
0x18002c53d  mov     [rcx+18h], r14d
0x18002c541  mov     [rcx+8], r14
0x18002c545  mov     [rcx+10h], r14
0x18002c549  lea     rax, ??_7CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable'
0x18002c550  mov     [rcx], rax
0x18002c553  mov     [rcx+20h], r14b
0x18002c557  mov     [rcx+28h], r14
0x18002c55b  mov     [rcx+30h], r14
0x18002c55f  lea     ecx, [r14+78h]; Size
0x18002c563  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c568  mov     [rax], rax
0x18002c56b  mov     [rax+8], rax
0x18002c56f  mov     [rax+10h], rax
0x18002c573  mov     word ptr [rax+18h], 101h
0x18002c579  mov     [rdi+28h], rax
0x18002c57d  mov     [rdi+38h], r14
0x18002c581  mov     [rdi+40h], r14d
0x18002c585  mov     [rdi+48h], r14
0x18002c589  mov     [rdi+50h], r14d
0x18002c58d  mov     [rdi+58h], r14
0x18002c591  mov     [rdi+60h], r14d
0x18002c595  mov     [rdi+68h], r14
0x18002c599  mov     [rdi+70h], r14
0x18002c59d  lea     rax, [rdi+78h]
0x18002c5a1  mov     [rax], r14
0x18002c5a4  lea     rsi, aApiMsWinEventi_3; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x18002c5ab  mov     [rax+8], rsi
0x18002c5af  lea     rbp, aTdhDll; "tdh.dll"
0x18002c5b6  mov     [rax+10h], rbp
0x18002c5ba  mov     [rax+18h], r14b
0x18002c5be  mov     [rdi+98h], rax
0x18002c5c5  lea     rax, aTdhqueryprovid; "TdhQueryProviderFieldInformation"
0x18002c5cc  mov     [rdi+0A0h], rax
0x18002c5d3  mov     [rdi+0A8h], r14
0x18002c5da  mov     [rdi+0B0h], r14b
0x18002c5e1  mov     [rdi+0B8h], r14
0x18002c5e8  mov     [rdi+0C0h], r14
0x18002c5ef  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002c5f6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002c5fd  mov     rax, [rax+18h]
0x18002c601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c606  add     rax, 18h
0x18002c60a  mov     [rdi+0C8h], rax
0x18002c611  lea     rbx, [rdi+0D0h]
0x18002c618  mov     [rbx], r14
0x18002c61b  mov     [rbx+8], r14
0x18002c61f  lea     ecx, [r14+68h]; Size
0x18002c623  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c628  mov     [rax], rax
0x18002c62b  mov     [rax+8], rax
0x18002c62f  mov     [rax+10h], rax
0x18002c633  mov     word ptr [rax+18h], 101h
0x18002c639  mov     [rbx], rax
0x18002c63c  lea     rdx, [rdi+0E0h]
0x18002c643  mov     [rdx], r14
0x18002c646  mov     [rdx+8], rsi
0x18002c64a  mov     [rdx+10h], rbp
0x18002c64e  mov     [rdx+18h], r14b
0x18002c652  lea     rax, [rdi+100h]
0x18002c659  mov     [rax], r14
0x18002c65c  lea     rcx, aExtMsWinEventi; "ext-ms-win-eventing-tdh-ext-l1-1-0.dll"
0x18002c663  mov     [rax+8], rcx
0x18002c667  mov     [rax+10h], rbp
0x18002c66b  mov     [rax+18h], r14b
0x18002c66f  lea     rcx, [rdi+120h]
0x18002c676  mov     [rcx], rdx
0x18002c679  lea     r8, aTdhgeteventinf; "TdhGetEventInformation"
0x18002c680  mov     [rcx+8], r8
0x18002c684  mov     [rcx+10h], r14
0x18002c688  mov     [rcx+18h], r14b
0x18002c68c  mov     [rdi+140h], rdx
0x18002c693  lea     rdx, aTdhgeteventmap; "TdhGetEventMapInformation"
0x18002c69a  mov     [rdi+148h], rdx
0x18002c6a1  mov     [rdi+150h], r14
0x18002c6a8  mov     [rdi+158h], r14b
0x18002c6af  mov     [rdi+160h], rax
0x18002c6b6  lea     rax, aTdhloadmanifes_0; "TdhLoadManifestFromBinary"
0x18002c6bd  mov     [rdi+168h], rax
0x18002c6c4  mov     [rdi+170h], r14
0x18002c6cb  mov     [rdi+178h], r14b
0x18002c6d2  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002c6d7  test    rax, rax
0x18002c6da  jnz     short loc_18002C6E0
0x18002c6dc  mov     byte ptr [rdi+20h], 1
0x18002c6e0  mov     rax, rdi
0x18002c6e3  mov     rbx, [rsp+38h+arg_10]
0x18002c6e8  mov     rbp, [rsp+38h+arg_18]
0x18002c6ed  add     rsp, 20h
0x18002c6f1  pop     r14
0x18002c6f3  pop     rdi
0x18002c6f4  pop     rsi
0x18002c6f5  retn
```
