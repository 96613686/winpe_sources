# WaasMedic::TelemetryProvider::DetectionActivity::StartActivity(char const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001aa34`
- end: `0x18001ab96`
- name: `?StartActivity@DetectionActivity@TelemetryProvider@WaasMedic@@QEAAXPEBDPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x18001aa34`
- `0x18001df78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aaae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ab6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aaae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ab6f`

## pseudocode

```c
int __fastcall WaasMedic::TelemetryProvider::DetectionActivity::StartActivity(
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
                           (unsigned int)&byte_180092137,
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
0x18001aa34  mov     [rsp+arg_8], rbx
0x18001aa39  mov     [rsp+arg_10], rbp
0x18001aa3e  push    rsi
0x18001aa3f  push    rdi
0x18001aa40  push    r14
0x18001aa42  sub     rsp, 70h
0x18001aa46  mov     rbx, r9
0x18001aa49  mov     rbp, r8
0x18001aa4c  mov     r14, rdx
0x18001aa4f  mov     rdi, rcx
0x18001aa52  call    ?zInternalStart@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001aa57  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001aa5c  mov     rsi, [rax+8]
0x18001aa60  mov     eax, [rsi]
0x18001aa62  cmp     eax, 5
0x18001aa65  jbe     loc_18001AB3C
0x18001aa6b  mov     rcx, [rsi+18h]
0x18001aa6f  mov     rdx, 400000000000h
0x18001aa79  mov     rax, [rsi+10h]
0x18001aa7d  test    rdx, rax
0x18001aa80  jz      loc_18001AB3C
0x18001aa86  mov     rax, rcx
0x18001aa89  and     rax, rdx
0x18001aa8c  cmp     rax, rcx
0x18001aa8f  jnz     loc_18001AB3C
0x18001aa95  cmp     qword ptr [rbx+18h], 7
0x18001aa9a  jbe     short loc_18001AA9F
0x18001aa9c  mov     rbx, [rbx]
0x18001aa9f  mov     [rsp+88h+var_38], rbx
0x18001aaa4  mov     [rsp+88h+var_30], rbp
0x18001aaa9  mov     [rsp+88h+var_28], r14
0x18001aaae  call    cs:__imp_GetCurrentThreadId
0x18001aab4  mov     r8, [rdi+110h]
0x18001aabb  mov     [rsp+88h+arg_0], eax
0x18001aac2  mov     [rsp+88h+var_20], 1000000h
0x18001aacb  cmp     byte ptr [r8+4], 0
0x18001aad0  jz      short loc_18001AAF1
0x18001aad2  lea     r9, [r8+18h]
0x18001aad6  cmp     dword ptr [r9], 0
0x18001aada  jnz     short loc_18001AAF4
0x18001aadc  cmp     dword ptr [r9+4], 0
0x18001aae1  jnz     short loc_18001AAF4
0x18001aae3  cmp     dword ptr [r9+8], 0
0x18001aae8  jnz     short loc_18001AAF4
0x18001aaea  cmp     dword ptr [r9+0Ch], 0
0x18001aaef  jnz     short loc_18001AAF4
0x18001aaf1  xor     r9d, r9d
0x18001aaf4  lea     rax, [rsp+88h+var_38]
0x18001aaf9  add     r8, 8
0x18001aafd  mov     [rsp+88h+var_48], rax
0x18001ab02  lea     rdx, byte_180092137
0x18001ab09  lea     rax, [rsp+88h+var_30]
0x18001ab0e  mov     rcx, rsi
0x18001ab11  mov     [rsp+88h+var_50], rax
0x18001ab16  lea     rax, [rsp+88h+var_28]
0x18001ab1b  mov     [rsp+88h+var_58], rax
0x18001ab20  lea     rax, [rsp+88h+arg_0]
0x18001ab28  mov     [rsp+88h+var_60], rax
0x18001ab2d  lea     rax, [rsp+88h+var_20]
0x18001ab32  mov     [rsp+88h+var_68], rax
0x18001ab37  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001ab3c  cmp     dword ptr [rdi+138h], 0
0x18001ab43  jnz     short loc_18001AB81
0x18001ab45  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001ab4d  lea     rbx, [rdi+120h]
0x18001ab54  jz      short loc_18001AB7A
0x18001ab56  mov     dl, 1
0x18001ab58  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001ab5d  mov     [rbx], rax
0x18001ab60  test    rax, rax
0x18001ab63  jz      short loc_18001AB81
0x18001ab65  mov     rcx, [rax]
0x18001ab68  mov     [rbx+10h], rcx
0x18001ab6c  mov     [rax], rbx
0x18001ab6f  call    cs:__imp_GetCurrentThreadId
0x18001ab75  mov     [rbx+18h], eax
0x18001ab78  jmp     short loc_18001AB81
0x18001ab7a  mov     qword ptr [rbx], 0
0x18001ab81  lea     r11, [rsp+88h+var_18]
0x18001ab86  mov     rbx, [r11+28h]
0x18001ab8a  mov     rbp, [r11+30h]
0x18001ab8e  mov     rsp, r11
0x18001ab91  pop     r14
0x18001ab93  pop     rdi
0x18001ab94  pop     rsi
0x18001ab95  retn
```
