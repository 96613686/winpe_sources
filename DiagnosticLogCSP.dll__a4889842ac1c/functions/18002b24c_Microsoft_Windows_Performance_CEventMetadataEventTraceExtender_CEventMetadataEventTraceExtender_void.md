# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)

- ea: `0x18002b24c`
- end: `0x18002b422`
- name: `??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `470`
- prototype: `Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002bbf4`

## callees

- `0x180001b84`
- `0x1800271c8`
- `0x18002b24c`
- `0x180037010`

## string_xrefs

- `0x18002b2db`: `tdh.dll`
- `0x18002b2d0`: `api-ms-win-eventing-tdh-l1-1-0.dll`
- `0x18002b388`: `ext-ms-win-eventing-tdh-ext-l1-1-0.dll`
- `0x18002b3e2`: `TdhLoadManifestFromBinary`

## pseudocode

```c
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
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288) )
    *((_BYTE *)this + 32) = 1;
  return this;
}

```

## disassembly

```asm
0x18002b24c  mov     [rsp+arg_10], rbx
0x18002b251  mov     [rsp+arg_18], rbp
0x18002b256  mov     [rsp+arg_0], rcx
0x18002b25b  push    rsi
0x18002b25c  push    rdi
0x18002b25d  push    r14
0x18002b25f  sub     rsp, 20h
0x18002b263  mov     rdi, rcx
0x18002b266  xor     r14d, r14d
0x18002b269  mov     [rcx+18h], r14d
0x18002b26d  mov     [rcx+8], r14
0x18002b271  mov     [rcx+10h], r14
0x18002b275  lea     rax, ??_7CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable'
0x18002b27c  mov     [rcx], rax
0x18002b27f  mov     [rcx+20h], r14b
0x18002b283  mov     [rcx+28h], r14
0x18002b287  mov     [rcx+30h], r14
0x18002b28b  lea     ecx, [r14+78h]; Size
0x18002b28f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b294  mov     [rax], rax
0x18002b297  mov     [rax+8], rax
0x18002b29b  mov     [rax+10h], rax
0x18002b29f  mov     word ptr [rax+18h], 101h
0x18002b2a5  mov     [rdi+28h], rax
0x18002b2a9  mov     [rdi+38h], r14
0x18002b2ad  mov     [rdi+40h], r14d
0x18002b2b1  mov     [rdi+48h], r14
0x18002b2b5  mov     [rdi+50h], r14d
0x18002b2b9  mov     [rdi+58h], r14
0x18002b2bd  mov     [rdi+60h], r14d
0x18002b2c1  mov     [rdi+68h], r14
0x18002b2c5  mov     [rdi+70h], r14
0x18002b2c9  lea     rax, [rdi+78h]
0x18002b2cd  mov     [rax], r14
0x18002b2d0  lea     rsi, aApiMsWinEventi_3; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x18002b2d7  mov     [rax+8], rsi
0x18002b2db  lea     rbp, aTdhDll; "tdh.dll"
0x18002b2e2  mov     [rax+10h], rbp
0x18002b2e6  mov     [rax+18h], r14b
0x18002b2ea  mov     [rdi+98h], rax
0x18002b2f1  lea     rax, aTdhqueryprovid; "TdhQueryProviderFieldInformation"
0x18002b2f8  mov     [rdi+0A0h], rax
0x18002b2ff  mov     [rdi+0A8h], r14
0x18002b306  mov     [rdi+0B0h], r14b
0x18002b30d  mov     [rdi+0B8h], r14
0x18002b314  mov     [rdi+0C0h], r14
0x18002b31b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002b322  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002b329  mov     rax, [rax+18h]
0x18002b32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b332  add     rax, 18h
0x18002b336  mov     [rdi+0C8h], rax
0x18002b33d  lea     rbx, [rdi+0D0h]
0x18002b344  mov     [rbx], r14
0x18002b347  mov     [rbx+8], r14
0x18002b34b  lea     ecx, [r14+68h]; Size
0x18002b34f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b354  mov     [rax], rax
0x18002b357  mov     [rax+8], rax
0x18002b35b  mov     [rax+10h], rax
0x18002b35f  mov     word ptr [rax+18h], 101h
0x18002b365  mov     [rbx], rax
0x18002b368  lea     rdx, [rdi+0E0h]
0x18002b36f  mov     [rdx], r14
0x18002b372  mov     [rdx+8], rsi
0x18002b376  mov     [rdx+10h], rbp
0x18002b37a  mov     [rdx+18h], r14b
0x18002b37e  lea     rax, [rdi+100h]
0x18002b385  mov     [rax], r14
0x18002b388  lea     rcx, aExtMsWinEventi; "ext-ms-win-eventing-tdh-ext-l1-1-0.dll"
0x18002b38f  mov     [rax+8], rcx
0x18002b393  mov     [rax+10h], rbp
0x18002b397  mov     [rax+18h], r14b
0x18002b39b  lea     rcx, [rdi+120h]
0x18002b3a2  mov     [rcx], rdx
0x18002b3a5  lea     r8, aTdhgeteventinf; "TdhGetEventInformation"
0x18002b3ac  mov     [rcx+8], r8
0x18002b3b0  mov     [rcx+10h], r14
0x18002b3b4  mov     [rcx+18h], r14b
0x18002b3b8  mov     [rdi+140h], rdx
0x18002b3bf  lea     rdx, aTdhgeteventmap; "TdhGetEventMapInformation"
0x18002b3c6  mov     [rdi+148h], rdx
0x18002b3cd  mov     [rdi+150h], r14
0x18002b3d4  mov     [rdi+158h], r14b
0x18002b3db  mov     [rdi+160h], rax
0x18002b3e2  lea     rax, aTdhloadmanifes_0; "TdhLoadManifestFromBinary"
0x18002b3e9  mov     [rdi+168h], rax
0x18002b3f0  mov     [rdi+170h], r14
0x18002b3f7  mov     [rdi+178h], r14b
0x18002b3fe  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002b403  test    rax, rax
0x18002b406  jnz     short loc_18002B40C
0x18002b408  mov     byte ptr [rdi+20h], 1
0x18002b40c  mov     rax, rdi
0x18002b40f  mov     rbx, [rsp+38h+arg_10]
0x18002b414  mov     rbp, [rsp+38h+arg_18]
0x18002b419  add     rsp, 20h
0x18002b41d  pop     r14
0x18002b41f  pop     rdi
0x18002b420  pop     rsi
0x18002b421  retn
```
