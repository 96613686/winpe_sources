# Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::Stop(Platform::String *)

- ea: `0x18003d830`
- end: `0x18003da94`
- name: `?Stop@CSGSuggester_GetEntitiesAsJson@CSGSuggestionTelemetry@CSGSuggestion@ConstraintIndex@Cortana@@QEAAXPE$AAVString@Platform@@@Z`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003e52c`

## callees

- `0x180001628`
- `0x180001b78`
- `0x18000619e`
- `0x18003bf74`
- `0x18003c9b8`
- `0x18003d830`
- `0x180040bb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003da29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003da29`

## pseudocode

```c
__int64 __fastcall Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::Stop(
        __int64 a1,
        HSTRING a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  int v8; // esi
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v16; // [rsp+C0h] [rbp-80h] BYREF
  int v17; // [rsp+C4h] [rbp-7Ch] BYREF
  int v18; // [rsp+C8h] [rbp-78h] BYREF
  int v19; // [rsp+CCh] [rbp-74h] BYREF
  int v20; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+D8h] [rbp-68h] BYREF
  __int64 StringRawBuffer_0; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+100h] [rbp-40h] BYREF
  __int64 v27; // [rsp+108h] [rbp-38h] BYREF
  __int64 v28; // [rsp+110h] [rbp-30h] BYREF
  __int64 v29; // [rsp+118h] [rbp-28h] BYREF
  __int64 v30; // [rsp+120h] [rbp-20h] BYREF
  __int64 v31; // [rsp+128h] [rbp-18h] BYREF
  __int64 v32; // [rsp+130h] [rbp-10h] BYREF
  __int64 v33; // [rsp+170h] [rbp+30h] BYREF
  __int64 v34; // [rsp+180h] [rbp+40h] BYREF
  __int64 v35; // [rsp+188h] [rbp+48h] BYREF

  v2 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = CortanaSearchTelemetryLogging::Provider();
    v8 = (int)v7;
    if ( *(_DWORD *)v7 > 5u )
    {
      StringRawBuffer_0 = (__int64)WindowsGetStringRawBuffer_0(a2, 0);
      LODWORD(v34) = v6[4];
      v24 = *((_QWORD *)v6 + 15);
      v25 = *((_QWORD *)v6 + 14);
      v9 = *((_QWORD *)v6 + 6);
      LODWORD(v35) = v6[26];
      v10 = *(_QWORD *)(a1 + 272);
      v26 = *((_QWORD *)v6 + 12);
      v27 = *((_QWORD *)v6 + 11);
      v16 = v6[20];
      v28 = *((_QWORD *)v6 + 9);
      v17 = v6[8];
      v29 = *((_QWORD *)v6 + 3);
      v18 = *v6;
      v30 = *((_QWORD *)v6 + 16);
      v19 = v6[16];
      v31 = *((_QWORD *)v6 + 7);
      v20 = v6[2];
      v23 = v9;
      LODWORD(v33) = v6[17];
      v32 = 0x1000000;
      v21 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v8,
        (int)&byte_180111611,
        v10 + 8,
        (__int64)&v21,
        (__int64)&v32,
        (__int64)&v20,
        (__int64)&v31,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&v18,
        (__int64)&v29,
        (__int64)&v17,
        (__int64)&v28,
        (__int64)&v16,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&StringRawBuffer_0);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = CortanaSearchTelemetryLogging::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v35 = (__int64)WindowsGetStringRawBuffer_0(a2, 0);
      CurrentThreadId = GetCurrentThreadId();
      v14 = *(_QWORD *)(a1 + 272);
      LODWORD(v33) = CurrentThreadId;
      LODWORD(v34) = *(_DWORD *)(v14 + 72);
      v21 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v12,
        (__int64)&v21,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v35);
    }
  }
  return wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18003d830  push    rbp
0x18003d832  push    rbx
0x18003d833  push    rsi
0x18003d834  push    rdi
0x18003d835  push    r14
0x18003d837  mov     rbp, rsp
0x18003d83a  sub     rsp, 140h
0x18003d841  mov     rdi, [rcx+110h]
0x18003d848  mov     r14, rdx
0x18003d84b  mov     rbx, rcx
0x18003d84e  mov     eax, [rdi+48h]
0x18003d851  test    eax, eax
0x18003d853  jns     loc_18003DA07
0x18003d859  add     rdi, 50h ; 'P'
0x18003d85d  cmp     eax, [rdi+8]
0x18003d860  jnz     loc_18003DA07
0x18003d866  test    rdi, rdi
0x18003d869  jz      loc_18003DA07
0x18003d86f  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003d874  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18003d879  mov     rsi, rax
0x18003d87c  mov     ecx, [rax]
0x18003d87e  cmp     ecx, 5
0x18003d881  jbe     loc_18003DA7F
0x18003d887  xor     edx, edx; length
0x18003d889  mov     rcx, r14; string
0x18003d88c  call    WindowsGetStringRawBuffer_0
0x18003d891  mov     [rbp+var_60], rax
0x18003d895  mov     eax, [rdi+10h]
0x18003d898  mov     dword ptr [rbp+arg_10], eax
0x18003d89b  mov     rax, [rdi+78h]
0x18003d89f  mov     [rbp+var_50], rax
0x18003d8a3  mov     rax, [rdi+70h]
0x18003d8a7  mov     [rbp+var_48], rax
0x18003d8ab  mov     eax, [rdi+68h]
0x18003d8ae  mov     rcx, [rdi+30h]
0x18003d8b2  mov     dword ptr [rbp+arg_18], eax
0x18003d8b5  mov     rax, [rdi+60h]
0x18003d8b9  mov     r8, [rbx+110h]
0x18003d8c0  mov     [rbp+var_40], rax
0x18003d8c4  add     r8, 8; int
0x18003d8c8  mov     rax, [rdi+58h]
0x18003d8cc  mov     [rbp+var_38], rax
0x18003d8d0  mov     eax, [rdi+50h]
0x18003d8d3  mov     dword ptr [rbp+var_80], eax
0x18003d8d6  mov     rax, [rdi+48h]
0x18003d8da  mov     [rbp+var_30], rax
0x18003d8de  mov     eax, [rdi+20h]
0x18003d8e1  mov     dword ptr [rbp+var_80+4], eax
0x18003d8e4  mov     rax, [rdi+18h]
0x18003d8e8  mov     [rbp+var_28], rax
0x18003d8ec  mov     eax, [rdi]
0x18003d8ee  mov     dword ptr [rbp+var_78], eax
0x18003d8f1  mov     rax, [rdi+80h]
0x18003d8f8  mov     [rbp+var_20], rax
0x18003d8fc  mov     eax, [rdi+40h]
0x18003d8ff  mov     dword ptr [rbp+var_78+4], eax
0x18003d902  mov     rax, [rdi+38h]
0x18003d906  mov     [rbp+var_18], rax
0x18003d90a  mov     eax, [rdi+8]
0x18003d90d  mov     [rbp+var_70], eax
0x18003d910  lea     rax, [rbp+var_60]
0x18003d914  mov     [rsp+140h+var_88], rax; __int64
0x18003d91c  lea     rax, [rbp+var_58]
0x18003d920  mov     [rsp+140h+var_90], rax; __int64
0x18003d928  lea     rax, [rbp+arg_0]
0x18003d92c  mov     [rsp+140h+var_98], rax; __int64
0x18003d934  lea     rax, [rbp+arg_10]
0x18003d938  mov     [rsp+140h+var_A0], rax; __int64
0x18003d940  lea     rax, [rbp+var_50]
0x18003d944  mov     [rsp+140h+var_A8], rax; __int64
0x18003d94c  lea     rax, [rbp+var_48]
0x18003d950  mov     [rsp+140h+var_B0], rax; __int64
0x18003d958  lea     rax, [rbp+arg_18]
0x18003d95c  mov     [rsp+140h+var_B8], rax; __int64
0x18003d964  lea     rax, [rbp+var_40]
0x18003d968  mov     [rsp+140h+var_C0], rax; __int64
0x18003d970  lea     rax, [rbp+var_38]
0x18003d974  mov     [rsp+140h+var_C8], rax; __int64
0x18003d979  lea     rax, [rbp+var_80]
0x18003d97d  mov     [rsp+140h+var_D0], rax; __int64
0x18003d982  lea     rax, [rbp+var_30]
0x18003d986  mov     [rsp+140h+var_D8], rax; __int64
0x18003d98b  lea     rax, [rbp+var_80+4]
0x18003d98f  mov     [rsp+140h+var_E0], rax; __int64
0x18003d994  lea     rax, [rbp+var_28]
0x18003d998  mov     [rsp+140h+var_E8], rax; __int64
0x18003d99d  lea     rax, [rbp+var_78]
0x18003d9a1  mov     [rsp+140h+var_F0], rax; __int64
0x18003d9a6  lea     rax, [rbp+var_20]
0x18003d9aa  mov     [rsp+140h+var_F8], rax; __int64
0x18003d9af  lea     rax, [rbp+var_78+4]
0x18003d9b3  mov     [rsp+140h+var_100], rax; __int64
0x18003d9b8  lea     rax, [rbp+var_18]
0x18003d9bc  mov     [rsp+140h+var_108], rax; __int64
0x18003d9c1  lea     rax, [rbp+var_70]
0x18003d9c5  mov     [rsp+140h+var_110], rax; __int64
0x18003d9ca  lea     rax, [rbp+var_10]
0x18003d9ce  mov     [rbp+var_58], rcx
0x18003d9d2  mov     ecx, [rdi+44h]
0x18003d9d5  mov     [rsp+140h+var_118], rax; __int64
0x18003d9da  lea     rax, [rbp+var_68]
0x18003d9de  mov     dword ptr [rbp+arg_0], ecx
0x18003d9e1  mov     [rbp+var_10], 1000000h
0x18003d9e9  mov     [rbp+var_68], 2000000h
0x18003d9f1  lea     rdx, byte_180111611; int
0x18003d9f8  mov     [rsp+140h+var_120], rax; __int64
0x18003d9fd  mov     rcx, rsi; int
0x18003da00  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564564456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x18003da05  jmp     short loc_18003DA7F
0x18003da07  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003da0c  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18003da11  mov     rdi, rax
0x18003da14  mov     ecx, [rax]
0x18003da16  cmp     ecx, 5
0x18003da19  jbe     short loc_18003DA7F
0x18003da1b  xor     edx, edx; length
0x18003da1d  mov     rcx, r14; string
0x18003da20  call    WindowsGetStringRawBuffer_0
0x18003da25  mov     [rbp+arg_18], rax
0x18003da29  call    cs:__imp_GetCurrentThreadId
0x18003da2f  mov     r8, [rbx+110h]
0x18003da36  lea     rdx, dword_1801115AC
0x18003da3d  mov     dword ptr [rbp+arg_0], eax
0x18003da40  lea     rax, [rbp+arg_18]
0x18003da44  mov     [rsp+140h+var_108], rax; __int64
0x18003da49  lea     rax, [rbp+arg_0]
0x18003da4d  mov     [rsp+140h+var_110], rax; __int64
0x18003da52  lea     rax, [rbp+arg_10]
0x18003da56  mov     ecx, [r8+48h]
0x18003da5a  add     r8, 8
0x18003da5e  mov     [rsp+140h+var_118], rax; __int64
0x18003da63  lea     rax, [rbp+var_68]
0x18003da67  mov     dword ptr [rbp+arg_10], ecx
0x18003da6a  mov     rcx, rdi; int
0x18003da6d  mov     [rsp+140h+var_120], rax; __int64
0x18003da72  mov     [rbp+var_68], 2000000h
0x18003da7a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18003da7f  mov     rcx, rbx
0x18003da82  add     rsp, 140h
0x18003da89  pop     r14
0x18003da8b  pop     rdi
0x18003da8c  pop     rsi
0x18003da8d  pop     rbx
0x18003da8e  pop     rbp
0x18003da8f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
