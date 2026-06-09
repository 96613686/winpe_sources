# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)

- ea: `0x18001af8c`
- end: `0x18001b162`
- name: `??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `470`
- prototype: `Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c4ac`

## callees

- `0x1800018a0`
- `0x1800163cc`
- `0x18001af8c`
- `0x18002a010`

## string_xrefs

- `0x18001b01b`: `tdh.dll`
- `0x18001b010`: `api-ms-win-eventing-tdh-l1-1-0.dll`
- `0x18001b0c8`: `ext-ms-win-eventing-tdh-ext-l1-1-0.dll`
- `0x18001b122`: `TdhLoadManifestFromBinary`

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
0x18001af8c  mov     [rsp+arg_10], rbx
0x18001af91  mov     [rsp+arg_18], rbp
0x18001af96  mov     [rsp+arg_0], rcx
0x18001af9b  push    rsi
0x18001af9c  push    rdi
0x18001af9d  push    r14
0x18001af9f  sub     rsp, 20h
0x18001afa3  mov     rdi, rcx
0x18001afa6  xor     r14d, r14d
0x18001afa9  mov     [rcx+18h], r14d
0x18001afad  mov     [rcx+8], r14
0x18001afb1  mov     [rcx+10h], r14
0x18001afb5  lea     rax, ??_7CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable'
0x18001afbc  mov     [rcx], rax
0x18001afbf  mov     [rcx+20h], r14b
0x18001afc3  mov     [rcx+28h], r14
0x18001afc7  mov     [rcx+30h], r14
0x18001afcb  lea     ecx, [r14+78h]; Size
0x18001afcf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001afd4  mov     [rax], rax
0x18001afd7  mov     [rax+8], rax
0x18001afdb  mov     [rax+10h], rax
0x18001afdf  mov     word ptr [rax+18h], 101h
0x18001afe5  mov     [rdi+28h], rax
0x18001afe9  mov     [rdi+38h], r14
0x18001afed  mov     [rdi+40h], r14d
0x18001aff1  mov     [rdi+48h], r14
0x18001aff5  mov     [rdi+50h], r14d
0x18001aff9  mov     [rdi+58h], r14
0x18001affd  mov     [rdi+60h], r14d
0x18001b001  mov     [rdi+68h], r14
0x18001b005  mov     [rdi+70h], r14
0x18001b009  lea     rax, [rdi+78h]
0x18001b00d  mov     [rax], r14
0x18001b010  lea     rsi, aApiMsWinEventi_3; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x18001b017  mov     [rax+8], rsi
0x18001b01b  lea     rbp, aTdhDll; "tdh.dll"
0x18001b022  mov     [rax+10h], rbp
0x18001b026  mov     [rax+18h], r14b
0x18001b02a  mov     [rdi+98h], rax
0x18001b031  lea     rax, aTdhqueryprovid; "TdhQueryProviderFieldInformation"
0x18001b038  mov     [rdi+0A0h], rax
0x18001b03f  mov     [rdi+0A8h], r14
0x18001b046  mov     [rdi+0B0h], r14b
0x18001b04d  mov     [rdi+0B8h], r14
0x18001b054  mov     [rdi+0C0h], r14
0x18001b05b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001b062  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001b069  mov     rax, [rax+18h]
0x18001b06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b072  add     rax, 18h
0x18001b076  mov     [rdi+0C8h], rax
0x18001b07d  lea     rbx, [rdi+0D0h]
0x18001b084  mov     [rbx], r14
0x18001b087  mov     [rbx+8], r14
0x18001b08b  lea     ecx, [r14+68h]; Size
0x18001b08f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b094  mov     [rax], rax
0x18001b097  mov     [rax+8], rax
0x18001b09b  mov     [rax+10h], rax
0x18001b09f  mov     word ptr [rax+18h], 101h
0x18001b0a5  mov     [rbx], rax
0x18001b0a8  lea     rdx, [rdi+0E0h]
0x18001b0af  mov     [rdx], r14
0x18001b0b2  mov     [rdx+8], rsi
0x18001b0b6  mov     [rdx+10h], rbp
0x18001b0ba  mov     [rdx+18h], r14b
0x18001b0be  lea     rax, [rdi+100h]
0x18001b0c5  mov     [rax], r14
0x18001b0c8  lea     rcx, aExtMsWinEventi; "ext-ms-win-eventing-tdh-ext-l1-1-0.dll"
0x18001b0cf  mov     [rax+8], rcx
0x18001b0d3  mov     [rax+10h], rbp
0x18001b0d7  mov     [rax+18h], r14b
0x18001b0db  lea     rcx, [rdi+120h]
0x18001b0e2  mov     [rcx], rdx
0x18001b0e5  lea     r8, aTdhgeteventinf; "TdhGetEventInformation"
0x18001b0ec  mov     [rcx+8], r8
0x18001b0f0  mov     [rcx+10h], r14
0x18001b0f4  mov     [rcx+18h], r14b
0x18001b0f8  mov     [rdi+140h], rdx
0x18001b0ff  lea     rdx, aTdhgeteventmap; "TdhGetEventMapInformation"
0x18001b106  mov     [rdi+148h], rdx
0x18001b10d  mov     [rdi+150h], r14
0x18001b114  mov     [rdi+158h], r14b
0x18001b11b  mov     [rdi+160h], rax
0x18001b122  lea     rax, aTdhloadmanifes_0; "TdhLoadManifestFromBinary"
0x18001b129  mov     [rdi+168h], rax
0x18001b130  mov     [rdi+170h], r14
0x18001b137  mov     [rdi+178h], r14b
0x18001b13e  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001b143  test    rax, rax
0x18001b146  jnz     short loc_18001B14C
0x18001b148  mov     byte ptr [rdi+20h], 1
0x18001b14c  mov     rax, rdi
0x18001b14f  mov     rbx, [rsp+38h+arg_10]
0x18001b154  mov     rbp, [rsp+38h+arg_18]
0x18001b159  add     rsp, 20h
0x18001b15d  pop     r14
0x18001b15f  pop     rdi
0x18001b160  pop     rsi
0x18001b161  retn
```
