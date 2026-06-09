# WaasMedic::TelemetryProvider::RemediationActivity::StartActivity(char const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001ad04`
- end: `0x18001ae66`
- name: `?StartActivity@RemediationActivity@TelemetryProvider@WaasMedic@@QEAAXPEBDPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180018d3c`

## callees

- `0x18000214c`
- `0x18000acc0`
- `0x18000d04c`
- `0x18001ad04`
- `0x18001df78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ad7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ae3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ad7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ae3f`

## pseudocode

```c
int __fastcall WaasMedic::TelemetryProvider::RemediationActivity::StartActivity(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 Local; // rax
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  __int64 *v15; // rbx
  _QWORD *v17; // [rsp+50h] [rbp-38h] BYREF
  __int64 v18; // [rsp+58h] [rbp-30h] BYREF
  __int64 v19; // [rsp+60h] [rbp-28h] BYREF
  __int64 v20; // [rsp+68h] [rbp-20h] BYREF
  DWORD v21; // [rsp+90h] [rbp+8h] BYREF

  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
  v10 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
  LODWORD(Local) = *(_DWORD *)v10;
  if ( *(_DWORD *)v10 > 5u )
  {
    v9 = *(_QWORD *)(v10 + 24);
    v8 = 0x400000000000LL;
    Local = *(_QWORD *)(v10 + 16);
    if ( (Local & 0x400000000000LL) != 0 )
    {
      LODWORD(Local) = 0;
      if ( (v9 & 0x400000000000LL) == v9 )
      {
        if ( a4[3] > 7u )
          a4 = (_QWORD *)*a4;
        v17 = a4;
        v18 = a3;
        v19 = a2;
        CurrentThreadId = GetCurrentThreadId();
        v13 = *(_QWORD *)(a1 + 272);
        v21 = CurrentThreadId;
        v20 = 0x1000000;
        if ( !*(_BYTE *)(v13 + 4)
          || (v14 = v13 + 24, !*(_DWORD *)(v13 + 24))
          && !*(_DWORD *)(v13 + 28)
          && !*(_DWORD *)(v13 + 32)
          && !*(_DWORD *)(v13 + 36) )
        {
          v14 = 0;
        }
        LODWORD(Local) = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                           v10,
                           (unsigned int)&unk_180092578,
                           (int)v13 + 8,
                           v14,
                           (__int64)&v20,
                           (__int64)&v21,
                           (__int64)&v19,
                           (__int64)&v18,
                           (__int64)&v17);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v15 = (__int64 *)(a1 + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v8) = 1;
      Local = wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(v9, v8);
      *v15 = Local;
      if ( Local )
      {
        *(_QWORD *)(a1 + 304) = *(_QWORD *)Local;
        *(_QWORD *)Local = v15;
        LODWORD(Local) = GetCurrentThreadId();
        *(_DWORD *)(a1 + 312) = Local;
      }
    }
    else
    {
      *v15 = 0;
    }
  }
  return Local;
}

```

## disassembly

```asm
0x18001ad04  mov     [rsp+arg_8], rbx
0x18001ad09  mov     [rsp+arg_10], rbp
0x18001ad0e  push    rsi
0x18001ad0f  push    rdi
0x18001ad10  push    r14
0x18001ad12  sub     rsp, 70h
0x18001ad16  mov     rbx, r9
0x18001ad19  mov     rbp, r8
0x18001ad1c  mov     r14, rdx
0x18001ad1f  mov     rdi, rcx
0x18001ad22  call    ?zInternalStart@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001ad27  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001ad2c  mov     rsi, [rax+8]
0x18001ad30  mov     eax, [rsi]
0x18001ad32  cmp     eax, 5
0x18001ad35  jbe     loc_18001AE0C
0x18001ad3b  mov     rcx, [rsi+18h]
0x18001ad3f  mov     rdx, 400000000000h
0x18001ad49  mov     rax, [rsi+10h]
0x18001ad4d  test    rdx, rax
0x18001ad50  jz      loc_18001AE0C
0x18001ad56  mov     rax, rcx
0x18001ad59  and     rax, rdx
0x18001ad5c  cmp     rax, rcx
0x18001ad5f  jnz     loc_18001AE0C
0x18001ad65  cmp     qword ptr [rbx+18h], 7
0x18001ad6a  jbe     short loc_18001AD6F
0x18001ad6c  mov     rbx, [rbx]
0x18001ad6f  mov     [rsp+88h+var_38], rbx
0x18001ad74  mov     [rsp+88h+var_30], rbp
0x18001ad79  mov     [rsp+88h+var_28], r14
0x18001ad7e  call    cs:__imp_GetCurrentThreadId
0x18001ad84  mov     r8, [rdi+110h]
0x18001ad8b  mov     [rsp+88h+arg_0], eax
0x18001ad92  mov     [rsp+88h+var_20], 1000000h
0x18001ad9b  cmp     byte ptr [r8+4], 0
0x18001ada0  jz      short loc_18001ADC1
0x18001ada2  lea     r9, [r8+18h]
0x18001ada6  cmp     dword ptr [r9], 0
0x18001adaa  jnz     short loc_18001ADC4
0x18001adac  cmp     dword ptr [r9+4], 0
0x18001adb1  jnz     short loc_18001ADC4
0x18001adb3  cmp     dword ptr [r9+8], 0
0x18001adb8  jnz     short loc_18001ADC4
0x18001adba  cmp     dword ptr [r9+0Ch], 0
0x18001adbf  jnz     short loc_18001ADC4
0x18001adc1  xor     r9d, r9d
0x18001adc4  lea     rax, [rsp+88h+var_38]
0x18001adc9  add     r8, 8
0x18001adcd  mov     [rsp+88h+var_48], rax
0x18001add2  lea     rdx, unk_180092578
0x18001add9  lea     rax, [rsp+88h+var_30]
0x18001adde  mov     rcx, rsi
0x18001ade1  mov     [rsp+88h+var_50], rax
0x18001ade6  lea     rax, [rsp+88h+var_28]
0x18001adeb  mov     [rsp+88h+var_58], rax
0x18001adf0  lea     rax, [rsp+88h+arg_0]
0x18001adf8  mov     [rsp+88h+var_60], rax
0x18001adfd  lea     rax, [rsp+88h+var_20]
0x18001ae02  mov     [rsp+88h+var_68], rax
0x18001ae07  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001ae0c  cmp     dword ptr [rdi+138h], 0
0x18001ae13  jnz     short loc_18001AE51
0x18001ae15  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001ae1d  lea     rbx, [rdi+120h]
0x18001ae24  jz      short loc_18001AE4A
0x18001ae26  mov     dl, 1
0x18001ae28  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001ae2d  mov     [rbx], rax
0x18001ae30  test    rax, rax
0x18001ae33  jz      short loc_18001AE51
0x18001ae35  mov     rcx, [rax]
0x18001ae38  mov     [rbx+10h], rcx
0x18001ae3c  mov     [rax], rbx
0x18001ae3f  call    cs:__imp_GetCurrentThreadId
0x18001ae45  mov     [rbx+18h], eax
0x18001ae48  jmp     short loc_18001AE51
0x18001ae4a  mov     qword ptr [rbx], 0
0x18001ae51  lea     r11, [rsp+88h+var_18]
0x18001ae56  mov     rbx, [r11+28h]
0x18001ae5a  mov     rbp, [r11+30h]
0x18001ae5e  mov     rsp, r11
0x18001ae61  pop     r14
0x18001ae63  pop     rdi
0x18001ae64  pop     rsi
0x18001ae65  retn
```
