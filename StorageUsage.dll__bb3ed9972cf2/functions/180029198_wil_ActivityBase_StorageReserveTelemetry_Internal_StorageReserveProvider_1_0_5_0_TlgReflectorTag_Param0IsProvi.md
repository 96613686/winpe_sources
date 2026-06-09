# wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x180029198`
- end: `0x1800293dd`
- name: `?ReportStopActivity@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180027564`
- `0x180029aac`

## callees

- `0x1800010b0`
- `0x180003ae4`
- `0x180003be0`
- `0x18002832c`
- `0x180029198`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029368`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029368`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  int *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-11h] BYREF
  int *v21; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v22; // [rsp+B8h] [rbp-1h] BYREF
  int *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v25; // [rsp+D0h] [rbp+17h] BYREF
  int *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  const unsigned __int16 *v28; // [rsp+E8h] [rbp+2Fh] BYREF
  int v29; // [rsp+120h] [rbp+67h] BYREF
  DWORD v30; // [rsp+128h] [rbp+6Fh] BYREF
  int *v31; // [rsp+130h] [rbp+77h] BYREF
  const unsigned __int16 *v32; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
      {
        v9 = *(int **)(v6 + 120);
        v10 = a1[34];
        v22 = *(const unsigned __int16 **)(v6 + 112);
        v30 = *(_DWORD *)(v6 + 104);
        v23 = *(int **)(v6 + 96);
        v24 = *(const unsigned __int16 **)(v6 + 88);
        v29 = *(_DWORD *)(v6 + 80);
        v25 = *(const unsigned __int16 **)(v6 + 72);
        LODWORD(v31) = *(_DWORD *)(v6 + 32);
        v26 = *(int **)(v6 + 24);
        LODWORD(v32) = *(_DWORD *)v6;
        v27 = *(const unsigned __int16 **)(v6 + 128);
        v18 = *(_DWORD *)(v6 + 64);
        v28 = *(const unsigned __int16 **)(v6 + 56);
        v19 = *(_DWORD *)(v6 + 8);
        v21 = v9;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v8,
          (__int64)byte_180038741,
          v10 + 8,
          v8,
          (__int64)&v20,
          (__int64)&v19,
          &v28,
          (__int64)&v18,
          &v27,
          (__int64)&v32,
          &v26,
          (__int64)&v31,
          &v25,
          (__int64)&v29,
          &v24,
          &v23,
          (__int64)&v30,
          &v22,
          &v21);
      }
    }
    else
    {
      v11 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
      v12 = (__int64)v11;
      if ( *(_DWORD *)v11 > 2u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
      {
        v13 = a1[34];
        v31 = *(int **)(v13 + 56);
        v32 = *(const unsigned __int16 **)(v13 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v15 = a1[34];
        v30 = CurrentThreadId;
        v29 = a2;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (__int64)&word_1800386C6,
          v15 + 8,
          v16,
          (__int64)&v20,
          (__int64)&v29,
          (__int64)&v30,
          &v32,
          &v31);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x180029198  push    rbp
0x18002919a  push    rbx
0x18002919b  push    rsi
0x18002919c  push    rdi
0x18002919d  lea     rbp, [rsp-3Fh]
0x1800291a2  sub     rsp, 0F8h
0x1800291a9  mov     esi, edx
0x1800291ab  mov     rbx, rcx
0x1800291ae  test    edx, edx
0x1800291b0  jns     loc_1800293C3
0x1800291b6  mov     rdi, [rcx+110h]
0x1800291bd  mov     eax, [rdi+48h]
0x1800291c0  test    eax, eax
0x1800291c2  jns     loc_180029328
0x1800291c8  add     rdi, 50h ; 'P'
0x1800291cc  cmp     eax, [rdi+8]
0x1800291cf  jnz     loc_180029328
0x1800291d5  test    rdi, rdi
0x1800291d8  jz      loc_180029328
0x1800291de  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x1800291e3  mov     r9, rax
0x1800291e6  mov     ecx, [rax]
0x1800291e8  cmp     ecx, 2
0x1800291eb  jbe     loc_1800293C3
0x1800291f1  mov     rdx, 200000000000h
0x1800291fb  mov     rcx, rax
0x1800291fe  call    _tlgKeywordOn
0x180029203  test    al, al
0x180029205  jz      loc_1800293C3
0x18002920b  mov     rax, [rdi+70h]
0x18002920f  lea     rdx, byte_180038741
0x180029216  mov     rcx, [rdi+78h]
0x18002921a  mov     r8, [rbx+110h]
0x180029221  mov     [rbp+57h+var_58], rax
0x180029225  add     r8, 8
0x180029229  mov     eax, [rdi+68h]
0x18002922c  mov     [rbp+57h+arg_8], eax
0x18002922f  mov     rax, [rdi+60h]
0x180029233  mov     [rbp+57h+var_50], rax
0x180029237  mov     rax, [rdi+58h]
0x18002923b  mov     [rbp+57h+var_48], rax
0x18002923f  mov     eax, [rdi+50h]
0x180029242  mov     [rbp+57h+arg_0], eax
0x180029245  mov     rax, [rdi+48h]
0x180029249  mov     [rbp+57h+var_40], rax
0x18002924d  mov     eax, [rdi+20h]
0x180029250  mov     dword ptr [rbp+57h+arg_10], eax
0x180029253  mov     rax, [rdi+18h]
0x180029257  mov     [rbp+57h+var_38], rax
0x18002925b  mov     eax, [rdi]
0x18002925d  mov     dword ptr [rbp+57h+arg_18], eax
0x180029260  mov     rax, [rdi+80h]
0x180029267  mov     [rbp+57h+var_30], rax
0x18002926b  mov     eax, [rdi+40h]
0x18002926e  mov     [rbp+57h+var_70], eax
0x180029271  mov     rax, [rdi+38h]
0x180029275  mov     [rbp+57h+var_28], rax
0x180029279  mov     eax, [rdi+8]
0x18002927c  mov     [rbp+57h+var_6C], eax
0x18002927f  lea     rax, [rbp+57h+var_60]
0x180029283  mov     [rsp+110h+var_80], rax
0x18002928b  lea     rax, [rbp+57h+var_58]
0x18002928f  mov     [rsp+110h+var_88], rax
0x180029297  lea     rax, [rbp+57h+arg_8]
0x18002929b  mov     [rsp+110h+var_90], rax
0x1800292a3  lea     rax, [rbp+57h+var_50]
0x1800292a7  mov     [rsp+110h+var_98], rax
0x1800292ac  lea     rax, [rbp+57h+var_48]
0x1800292b0  mov     [rsp+110h+var_A0], rax
0x1800292b5  lea     rax, [rbp+57h+arg_0]
0x1800292b9  mov     [rsp+110h+var_A8], rax
0x1800292be  lea     rax, [rbp+57h+var_40]
0x1800292c2  mov     [rsp+110h+var_B0], rax
0x1800292c7  lea     rax, [rbp+57h+arg_10]
0x1800292cb  mov     [rsp+110h+var_B8], rax
0x1800292d0  lea     rax, [rbp+57h+var_38]
0x1800292d4  mov     [rsp+110h+var_C0], rax
0x1800292d9  lea     rax, [rbp+57h+arg_18]
0x1800292dd  mov     [rsp+110h+var_C8], rax
0x1800292e2  lea     rax, [rbp+57h+var_30]
0x1800292e6  mov     [rsp+110h+var_D0], rax
0x1800292eb  lea     rax, [rbp+57h+var_70]
0x1800292ef  mov     [rsp+110h+var_D8], rax
0x1800292f4  lea     rax, [rbp+57h+var_28]
0x1800292f8  mov     [rsp+110h+var_E0], rax
0x1800292fd  lea     rax, [rbp+57h+var_6C]
0x180029301  mov     [rsp+110h+var_E8], rax
0x180029306  lea     rax, [rbp+57h+var_68]
0x18002930a  mov     [rbp+57h+var_60], rcx
0x18002930e  mov     rcx, r9
0x180029311  mov     [rsp+110h+var_F0], rax
0x180029316  mov     [rbp+57h+var_68], 1000000h
0x18002931e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180029323  jmp     loc_1800293C3
0x180029328  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002932d  mov     rdi, rax
0x180029330  mov     ecx, [rax]
0x180029332  cmp     ecx, 2
0x180029335  jbe     loc_1800293C3
0x18002933b  mov     rdx, 200000000000h
0x180029345  mov     rcx, rax
0x180029348  call    _tlgKeywordOn
0x18002934d  test    al, al
0x18002934f  jz      short loc_1800293C3
0x180029351  mov     rcx, [rbx+110h]
0x180029358  mov     rax, [rcx+38h]
0x18002935c  mov     [rbp+57h+arg_10], rax
0x180029360  mov     rax, [rcx+30h]
0x180029364  mov     [rbp+57h+arg_18], rax
0x180029368  call    cs:__imp_GetCurrentThreadId
0x18002936e  mov     r8, [rbx+110h]
0x180029375  lea     rdx, word_1800386C6
0x18002937c  mov     [rbp+57h+arg_8], eax
0x18002937f  add     r8, 8
0x180029383  lea     rax, [rbp+57h+arg_10]
0x180029387  mov     [rbp+57h+arg_0], esi
0x18002938a  mov     [rsp+110h+var_D0], rax
0x18002938f  mov     rcx, rdi
0x180029392  lea     rax, [rbp+57h+arg_18]
0x180029396  mov     [rbp+57h+var_68], 1000000h
0x18002939e  mov     [rsp+110h+var_D8], rax
0x1800293a3  lea     rax, [rbp+57h+arg_8]
0x1800293a7  mov     [rsp+110h+var_E0], rax
0x1800293ac  lea     rax, [rbp+57h+arg_0]
0x1800293b0  mov     [rsp+110h+var_E8], rax
0x1800293b5  lea     rax, [rbp+57h+var_68]
0x1800293b9  mov     [rsp+110h+var_F0], rax
0x1800293be  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800293c3  mov     rax, [rbx]
0x1800293c6  mov     rcx, rbx
0x1800293c9  mov     rax, [rax+8]
0x1800293cd  add     rsp, 0F8h
0x1800293d4  pop     rdi
0x1800293d5  pop     rsi
0x1800293d6  pop     rbx
0x1800293d7  pop     rbp
0x1800293d8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
