# CApplicationFrameTelemetry::MoveSizeLoop::StartActivity(ushort const *,HWND__ *)

- ea: `0x180052120`
- end: `0x180052258`
- name: `?StartActivity@MoveSizeLoop@CApplicationFrameTelemetry@@QEAAXPEBGPEAUHWND__@@@Z`
- size: `312`
- prototype: `void(CApplicationFrameTelemetry::MoveSizeLoop *__hidden this, const unsigned __int16 *, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18004db14`

## callees

- `0x180027c3c`
- `0x180030190`
- `0x18003610c`
- `0x1800381b4`
- `0x180039fec`
- `0x18003e394`
- `0x180043c30`
- `0x180052120`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800521ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800521ae`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x180052156`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x180052156`

## pseudocode

```c
void __fastcall CApplicationFrameTelemetry::MoveSizeLoop::StartActivity(
        CApplicationFrameTelemetry::MoveSizeLoop *this,
        const unsigned __int16 *a2,
        HWND a3)
{
  _DWORD *v5; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  int v8; // ecx
  LONG bottom; // [rsp+60h] [rbp+7h] BYREF
  LONG right; // [rsp+64h] [rbp+Bh] BYREF
  LONG top; // [rsp+68h] [rbp+Fh] BYREF
  LONG left; // [rsp+6Ch] [rbp+13h] BYREF
  DWORD v13; // [rsp+70h] [rbp+17h] BYREF
  const unsigned __int16 *v14; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v15; // [rsp+80h] [rbp+27h] BYREF
  struct tagRECT Rect; // [rsp+88h] [rbp+2Fh] BYREF

  Rect = 0;
  GetWindowRect(a3, &Rect);
  wil::ActivityBase<CApplicationFrameLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v5 = (_DWORD *)*((_QWORD *)CApplicationFrameLogging::Instance() + 1);
  if ( *v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
  {
    bottom = Rect.bottom;
    right = Rect.right;
    top = Rect.top;
    left = Rect.left;
    v14 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v7 = *((_QWORD *)this + 34);
    v13 = CurrentThreadId;
    v15 = 0;
    if ( !*(_BYTE *)(v7 + 4) || _tlgGuidIsZero((const struct _GUID *)(v7 + 24)) )
      v8 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v5,
      (unsigned int)&dword_18007EF0C,
      v7 + 8,
      v8,
      (__int64)&v15,
      (__int64)&v13,
      (__int64)&v14,
      (__int64)&left,
      (__int64)&top,
      (__int64)&right,
      (__int64)&bottom);
  }
  wil::ActivityBase<CApplicationFrameLogging,1,35184372088833,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180052120  mov     [rsp-8+arg_8], rbx
0x180052125  push    rbp
0x180052126  push    rsi
0x180052127  push    rdi
0x180052128  lea     rbp, [rsp-47h]
0x18005212d  sub     rsp, 0A0h
0x180052134  mov     rax, cs:__security_cookie
0x18005213b  xor     rax, rsp
0x18005213e  mov     [rbp+57h+var_18], rax
0x180052142  mov     rsi, rdx
0x180052145  mov     rbx, rcx
0x180052148  xorps   xmm0, xmm0
0x18005214b  lea     rdx, [rbp+57h+Rect]; lpRect
0x18005214f  mov     rcx, r8; hWnd
0x180052152  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180052156  call    cs:__imp_GetWindowRect
0x18005215c  mov     rcx, rbx
0x18005215f  call    ?zInternalStart@?$ActivityBase@VCApplicationFrameLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180052164  call    ?Instance@CApplicationFrameLogging@@KAPEAV1@XZ; CApplicationFrameLogging::Instance(void)
0x180052169  mov     rdi, [rax+8]
0x18005216d  mov     eax, [rdi]
0x18005216f  cmp     eax, 5
0x180052172  jbe     loc_180052231
0x180052178  mov     rdx, 400000000000h
0x180052182  mov     rcx, rdi
0x180052185  call    _tlgKeywordOn
0x18005218a  test    al, al
0x18005218c  jz      loc_180052231
0x180052192  mov     eax, [rbp+57h+Rect.bottom]
0x180052195  mov     [rbp+57h+var_50], eax
0x180052198  mov     eax, [rbp+57h+Rect.right]
0x18005219b  mov     [rbp+57h+var_4C], eax
0x18005219e  mov     eax, [rbp+57h+Rect.top]
0x1800521a1  mov     [rbp+57h+var_48], eax
0x1800521a4  mov     eax, [rbp+57h+Rect.left]
0x1800521a7  mov     [rbp+57h+var_44], eax
0x1800521aa  mov     [rbp+57h+var_38], rsi
0x1800521ae  call    cs:__imp_GetCurrentThreadId
0x1800521b4  mov     r8, [rbx+110h]
0x1800521bb  mov     [rbp+57h+var_40], eax
0x1800521be  mov     [rbp+57h+var_30], 0
0x1800521c6  cmp     byte ptr [r8+4], 0
0x1800521cb  jz      short loc_1800521DA
0x1800521cd  lea     rcx, [r8+18h]; struct _GUID *
0x1800521d1  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800521d6  test    al, al
0x1800521d8  jz      short loc_1800521DC
0x1800521da  xor     ecx, ecx
0x1800521dc  lea     rax, [rbp+57h+var_50]
0x1800521e0  mov     r9, rcx
0x1800521e3  mov     [rsp+0B0h+var_60], rax
0x1800521e8  lea     rdx, dword_18007EF0C
0x1800521ef  lea     rax, [rbp+57h+var_4C]
0x1800521f3  add     r8, 8
0x1800521f7  mov     [rsp+0B0h+var_68], rax
0x1800521fc  mov     rcx, rdi
0x1800521ff  lea     rax, [rbp+57h+var_48]
0x180052203  mov     [rsp+0B0h+var_70], rax
0x180052208  lea     rax, [rbp+57h+var_44]
0x18005220c  mov     [rsp+0B0h+var_78], rax
0x180052211  lea     rax, [rbp+57h+var_38]
0x180052215  mov     [rsp+0B0h+var_80], rax
0x18005221a  lea     rax, [rbp+57h+var_40]
0x18005221e  mov     [rsp+0B0h+var_88], rax
0x180052223  lea     rax, [rbp+57h+var_30]
0x180052227  mov     [rsp+0B0h+var_90], rax
0x18005222c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180052231  mov     rcx, rbx
0x180052234  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCApplicationFrameLogging@@$00$0CAAAAAAAAAAB@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,1,35184372088833,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180052239  mov     rcx, [rbp+57h+var_18]
0x18005223d  xor     rcx, rsp; StackCookie
0x180052240  call    __security_check_cookie
0x180052245  mov     rbx, [rsp+0B0h+arg_8]
0x18005224d  add     rsp, 0A0h
0x180052254  pop     rdi
0x180052255  pop     rsi
0x180052256  pop     rbp
0x180052257  retn
```
