# WaasMedic::TelemetryProvider::SandboxActivity::StartActivity(char const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001ae6c`
- end: `0x18001afce`
- name: `?StartActivity@SandboxActivity@TelemetryProvider@WaasMedic@@QEAAXPEBDPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180018d3c`

## callees

- `0x18000214c`
- `0x18000acc0`
- `0x18000d04c`
- `0x18001ae6c`
- `0x18001df78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aee6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001afa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aee6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001afa7`

## pseudocode

```c
int __fastcall WaasMedic::TelemetryProvider::SandboxActivity::StartActivity(
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
                           (unsigned int)byte_180091EA1,
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
0x18001ae6c  mov     [rsp+arg_8], rbx
0x18001ae71  mov     [rsp+arg_10], rbp
0x18001ae76  push    rsi
0x18001ae77  push    rdi
0x18001ae78  push    r14
0x18001ae7a  sub     rsp, 70h
0x18001ae7e  mov     rbx, r9
0x18001ae81  mov     rbp, r8
0x18001ae84  mov     r14, rdx
0x18001ae87  mov     rdi, rcx
0x18001ae8a  call    ?zInternalStart@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001ae8f  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001ae94  mov     rsi, [rax+8]
0x18001ae98  mov     eax, [rsi]
0x18001ae9a  cmp     eax, 5
0x18001ae9d  jbe     loc_18001AF74
0x18001aea3  mov     rcx, [rsi+18h]
0x18001aea7  mov     rdx, 400000000000h
0x18001aeb1  mov     rax, [rsi+10h]
0x18001aeb5  test    rdx, rax
0x18001aeb8  jz      loc_18001AF74
0x18001aebe  mov     rax, rcx
0x18001aec1  and     rax, rdx
0x18001aec4  cmp     rax, rcx
0x18001aec7  jnz     loc_18001AF74
0x18001aecd  cmp     qword ptr [rbx+18h], 7
0x18001aed2  jbe     short loc_18001AED7
0x18001aed4  mov     rbx, [rbx]
0x18001aed7  mov     [rsp+88h+var_38], rbx
0x18001aedc  mov     [rsp+88h+var_30], rbp
0x18001aee1  mov     [rsp+88h+var_28], r14
0x18001aee6  call    cs:__imp_GetCurrentThreadId
0x18001aeec  mov     r8, [rdi+110h]
0x18001aef3  mov     [rsp+88h+arg_0], eax
0x18001aefa  mov     [rsp+88h+var_20], 1000000h
0x18001af03  cmp     byte ptr [r8+4], 0
0x18001af08  jz      short loc_18001AF29
0x18001af0a  lea     r9, [r8+18h]
0x18001af0e  cmp     dword ptr [r9], 0
0x18001af12  jnz     short loc_18001AF2C
0x18001af14  cmp     dword ptr [r9+4], 0
0x18001af19  jnz     short loc_18001AF2C
0x18001af1b  cmp     dword ptr [r9+8], 0
0x18001af20  jnz     short loc_18001AF2C
0x18001af22  cmp     dword ptr [r9+0Ch], 0
0x18001af27  jnz     short loc_18001AF2C
0x18001af29  xor     r9d, r9d
0x18001af2c  lea     rax, [rsp+88h+var_38]
0x18001af31  add     r8, 8
0x18001af35  mov     [rsp+88h+var_48], rax
0x18001af3a  lea     rdx, byte_180091EA1
0x18001af41  lea     rax, [rsp+88h+var_30]
0x18001af46  mov     rcx, rsi
0x18001af49  mov     [rsp+88h+var_50], rax
0x18001af4e  lea     rax, [rsp+88h+var_28]
0x18001af53  mov     [rsp+88h+var_58], rax
0x18001af58  lea     rax, [rsp+88h+arg_0]
0x18001af60  mov     [rsp+88h+var_60], rax
0x18001af65  lea     rax, [rsp+88h+var_20]
0x18001af6a  mov     [rsp+88h+var_68], rax
0x18001af6f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001af74  cmp     dword ptr [rdi+138h], 0
0x18001af7b  jnz     short loc_18001AFB9
0x18001af7d  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001af85  lea     rbx, [rdi+120h]
0x18001af8c  jz      short loc_18001AFB2
0x18001af8e  mov     dl, 1
0x18001af90  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001af95  mov     [rbx], rax
0x18001af98  test    rax, rax
0x18001af9b  jz      short loc_18001AFB9
0x18001af9d  mov     rcx, [rax]
0x18001afa0  mov     [rbx+10h], rcx
0x18001afa4  mov     [rax], rbx
0x18001afa7  call    cs:__imp_GetCurrentThreadId
0x18001afad  mov     [rbx+18h], eax
0x18001afb0  jmp     short loc_18001AFB9
0x18001afb2  mov     qword ptr [rbx], 0
0x18001afb9  lea     r11, [rsp+88h+var_18]
0x18001afbe  mov     rbx, [r11+28h]
0x18001afc2  mov     rbp, [r11+30h]
0x18001afc6  mov     rsp, r11
0x18001afc9  pop     r14
0x18001afcb  pop     rdi
0x18001afcc  pop     rsi
0x18001afcd  retn
```
