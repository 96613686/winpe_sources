# CRawImageReader::CRawImageReader(void)

- ea: `0x1800a4e48`
- end: `0x1800a5159`
- name: `??0CRawImageReader@@QEAA@XZ`
- size: `785`
- prototype: `CRawImageReader *__fastcall(CRawImageReader *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a444c`

## callees

- `0x180095a74`
- `0x1800a4e48`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a4eda`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a4eda`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CRawImageReader *__fastcall CRawImageReader::CRawImageReader(CRawImageReader *this)
{
  _QWORD *v2; // rdi

  v2 = (_QWORD *)((char *)this + 16);
  Microsoft::WRL::FtmBase::FtmBase((CRawImageReader *)((char *)this + 16));
  *((_DWORD *)this + 13) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'{for `IMFTelemetryComponent'};
  *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *((_DWORD *)this + 14) = 0;
  *(_QWORD *)this = &CRawImageReader::`vftable';
  *((_QWORD *)this + 1) = &CRawImageReader::`vftable'{for `IMFTelemetryComponent'};
  *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *((_DWORD *)this + 26) = 0;
  *((_BYTE *)this + 108) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *(_QWORD *)((char *)this + 284) = 0;
  *((_DWORD *)this + 70) &= 0xFFFFFFF9;
  *((_DWORD *)this + 70) |= 1u;
  *((_QWORD *)this + 37) = (char *)this + 304;
  *((_DWORD *)this + 73) = 128;
  *(_QWORD *)((char *)this + 436) = 0;
  *((_DWORD *)this + 108) &= 0xFFFFFFF9;
  *((_DWORD *)this + 108) |= 1u;
  *((_QWORD *)this + 56) = (char *)this + 456;
  *((_DWORD *)this + 111) = 128;
  *((_QWORD *)this + 73) = 0;
  *((_DWORD *)this + 148) = 0;
  *((_QWORD *)this + 75) = &CAggregationStatsStdDev<unsigned __int64>::`vftable';
  *((_BYTE *)this + 664) = 1;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_BYTE *)this + 640) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 84) = &CAggregationStatsStdDev<unsigned __int64>::`vftable';
  *((_BYTE *)this + 736) = 1;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_BYTE *)this + 712) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 93) = &CAggregationStatsStdDev<unsigned __int64>::`vftable';
  *((_BYTE *)this + 808) = 1;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_BYTE *)this + 784) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 102) = &CAggregationStatsStdDev<unsigned __int64>::`vftable';
  *((_BYTE *)this + 880) = 1;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 105) = 0;
  *((_QWORD *)this + 106) = 0;
  *((_BYTE *)this + 856) = 0;
  *((_QWORD *)this + 109) = 0;
  *((_QWORD *)this + 111) = &CAggregationStatsStdDev<unsigned __int64>::`vftable';
  *((_BYTE *)this + 952) = 1;
  *((_QWORD *)this + 113) = 0;
  *((_QWORD *)this + 112) = 0;
  *((_QWORD *)this + 114) = 0;
  *((_QWORD *)this + 115) = 0;
  *((_BYTE *)this + 928) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 120) = &CAggregationStatsStdDev<unsigned __int64>::`vftable';
  *((_BYTE *)this + 1024) = 1;
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 121) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_QWORD *)this + 124) = 0;
  *((_BYTE *)this + 1000) = 0;
  *((_QWORD *)this + 127) = 0;
  *((_QWORD *)this + 129) = 0;
  *((_DWORD *)this + 260) = 0;
  return this;
}

```

## disassembly

```asm
0x1800a4e48  mov     rax, rsp
0x1800a4e4b  mov     [rax+8], rcx
0x1800a4e4f  push    rdi
0x1800a4e50  sub     rsp, 30h
0x1800a4e54  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1800a4e5c  mov     [rax+10h], rbx
0x1800a4e60  mov     [rax+18h], rsi
0x1800a4e64  mov     rbx, rcx
0x1800a4e67  lea     rdi, [rcx+10h]
0x1800a4e6b  mov     rcx, rdi; this
0x1800a4e6e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800a4e73  mov     dword ptr [rbx+34h], 1
0x1800a4e7a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'
0x1800a4e81  mov     [rbx], rax
0x1800a4e84  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@WRL@Microsoft@@6BIMFTelemetryComponent@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'{for `IMFTelemetryComponent'}
0x1800a4e8b  mov     [rbx+8], rax
0x1800a4e8f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a4e96  mov     [rdi], rax
0x1800a4e99  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800a4ea0  xor     esi, esi
0x1800a4ea2  test    rcx, rcx
0x1800a4ea5  jz      short loc_1800A4EB4
0x1800a4ea7  mov     rax, [rcx]
0x1800a4eaa  mov     rax, [rax+8]
0x1800a4eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4eb3  nop
0x1800a4eb4  mov     [rbx+38h], esi
0x1800a4eb7  lea     rax, ??_7CRawImageReader@@6B@; const CRawImageReader::`vftable'
0x1800a4ebe  mov     [rbx], rax
0x1800a4ec1  lea     rax, ??_7CRawImageReader@@6BIMFTelemetryComponent@@@; const CRawImageReader::`vftable'{for `IMFTelemetryComponent'}
0x1800a4ec8  mov     [rbx+8], rax
0x1800a4ecc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a4ed3  mov     [rdi], rax
0x1800a4ed6  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800a4eda  call    cs:__imp_InitializeCriticalSection
0x1800a4ee1  nop     dword ptr [rax+rax+00h]
0x1800a4ee6  mov     [rbx+68h], esi
0x1800a4ee9  mov     [rbx+6Ch], sil
0x1800a4eed  mov     [rbx+70h], rsi
0x1800a4ef1  mov     [rbx+78h], rsi
0x1800a4ef5  mov     [rbx+80h], rsi
0x1800a4efc  mov     [rbx+88h], rsi
0x1800a4f03  mov     [rbx+90h], rsi
0x1800a4f0a  mov     [rbx+98h], rsi
0x1800a4f11  mov     [rbx+0A0h], rsi
0x1800a4f18  mov     [rbx+0A8h], rsi
0x1800a4f1f  mov     [rbx+0B0h], rsi
0x1800a4f26  mov     [rbx+0B8h], rsi
0x1800a4f2d  mov     [rbx+0C0h], rsi
0x1800a4f34  mov     [rbx+0C8h], rsi
0x1800a4f3b  mov     [rbx+0D0h], rsi
0x1800a4f42  mov     [rbx+0D8h], rsi
0x1800a4f49  mov     [rbx+0E0h], rsi
0x1800a4f50  mov     [rbx+0E8h], rsi
0x1800a4f57  mov     [rbx+0F0h], rsi
0x1800a4f5e  mov     [rbx+0F8h], rsi
0x1800a4f65  mov     [rbx+100h], rsi
0x1800a4f6c  mov     [rbx+108h], rsi
0x1800a4f73  mov     [rbx+110h], rsi
0x1800a4f7a  mov     [rbx+11Ch], rsi
0x1800a4f81  mov     edx, 0FFFFFFF9h
0x1800a4f86  and     [rbx+118h], edx
0x1800a4f8c  or      dword ptr [rbx+118h], 1
0x1800a4f93  lea     rax, [rbx+130h]
0x1800a4f9a  mov     [rbx+128h], rax
0x1800a4fa1  mov     ecx, 80h
0x1800a4fa6  mov     [rbx+124h], ecx
0x1800a4fac  mov     [rbx+1B4h], rsi
0x1800a4fb3  and     [rbx+1B0h], edx
0x1800a4fb9  or      dword ptr [rbx+1B0h], 1
0x1800a4fc0  lea     rax, [rbx+1C8h]
0x1800a4fc7  mov     [rbx+1C0h], rax
0x1800a4fce  mov     [rbx+1BCh], ecx
0x1800a4fd4  mov     [rbx+248h], rsi
0x1800a4fdb  mov     [rbx+250h], esi
0x1800a4fe1  lea     rax, ??_7?$CAggregationStatsStdDev@_K@@6B@; const CAggregationStatsStdDev<unsigned __int64>::`vftable'
0x1800a4fe8  mov     [rbx+258h], rax
0x1800a4fef  mov     byte ptr [rbx+298h], 1
0x1800a4ff6  mov     [rbx+268h], rsi
0x1800a4ffd  mov     [rbx+260h], rsi
0x1800a5004  mov     [rbx+270h], rsi
0x1800a500b  mov     [rbx+278h], rsi
0x1800a5012  mov     [rbx+280h], sil
0x1800a5019  mov     [rbx+290h], rsi
0x1800a5020  mov     [rbx+2A0h], rax
0x1800a5027  mov     byte ptr [rbx+2E0h], 1
0x1800a502e  mov     [rbx+2B0h], rsi
0x1800a5035  mov     [rbx+2A8h], rsi
0x1800a503c  mov     [rbx+2B8h], rsi
0x1800a5043  mov     [rbx+2C0h], rsi
0x1800a504a  mov     [rbx+2C8h], sil
0x1800a5051  mov     [rbx+2D8h], rsi
0x1800a5058  mov     [rbx+2E8h], rax
0x1800a505f  mov     byte ptr [rbx+328h], 1
0x1800a5066  mov     [rbx+2F8h], rsi
0x1800a506d  mov     [rbx+2F0h], rsi
0x1800a5074  mov     [rbx+300h], rsi
0x1800a507b  mov     [rbx+308h], rsi
0x1800a5082  mov     [rbx+310h], sil
0x1800a5089  mov     [rbx+320h], rsi
0x1800a5090  mov     [rbx+330h], rax
0x1800a5097  mov     byte ptr [rbx+370h], 1
0x1800a509e  mov     [rbx+340h], rsi
0x1800a50a5  mov     [rbx+338h], rsi
0x1800a50ac  mov     [rbx+348h], rsi
0x1800a50b3  mov     [rbx+350h], rsi
0x1800a50ba  mov     [rbx+358h], sil
0x1800a50c1  mov     [rbx+368h], rsi
0x1800a50c8  mov     [rbx+378h], rax
0x1800a50cf  mov     byte ptr [rbx+3B8h], 1
0x1800a50d6  mov     [rbx+388h], rsi
0x1800a50dd  mov     [rbx+380h], rsi
0x1800a50e4  mov     [rbx+390h], rsi
0x1800a50eb  mov     [rbx+398h], rsi
0x1800a50f2  mov     [rbx+3A0h], sil
0x1800a50f9  mov     [rbx+3B0h], rsi
0x1800a5100  mov     [rbx+3C0h], rax
0x1800a5107  mov     byte ptr [rbx+400h], 1
0x1800a510e  mov     [rbx+3D0h], rsi
0x1800a5115  mov     [rbx+3C8h], rsi
0x1800a511c  mov     [rbx+3D8h], rsi
0x1800a5123  mov     [rbx+3E0h], rsi
0x1800a512a  mov     [rbx+3E8h], sil
0x1800a5131  mov     [rbx+3F8h], rsi
0x1800a5138  mov     [rbx+408h], rsi
0x1800a513f  mov     [rbx+410h], esi
0x1800a5145  mov     rax, rbx
0x1800a5148  mov     rbx, [rsp+38h+arg_8]
0x1800a514d  mov     rsi, [rsp+38h+arg_10]
0x1800a5152  add     rsp, 30h
0x1800a5156  pop     rdi
0x1800a5157  retn
```
