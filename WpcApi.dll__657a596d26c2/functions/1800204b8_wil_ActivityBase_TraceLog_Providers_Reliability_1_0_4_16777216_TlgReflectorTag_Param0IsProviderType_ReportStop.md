# wil::ActivityBase<TraceLog::Providers::Reliability,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x1800204b8`
- end: `0x180020719`
- name: `?ReportStopActivity@?$ActivityBase@VReliability@Providers@TraceLog@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `609`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001fe44`
- `0x1800208d8`

## callees

- `0x180001660`
- `0x18000175c`
- `0x1800203f8`
- `0x1800204b8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800206a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800206a4`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<TraceLog::Providers::Reliability,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-11h] BYREF
  const WCHAR *v22; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v23; // [rsp+B8h] [rbp-1h] BYREF
  const WCHAR *v24; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v25; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v26; // [rsp+D0h] [rbp+17h] BYREF
  const WCHAR *v27; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v28; // [rsp+E0h] [rbp+27h] BYREF
  const unsigned __int16 *v29; // [rsp+E8h] [rbp+2Fh] BYREF
  int v30; // [rsp+120h] [rbp+67h] BYREF
  DWORD v31; // [rsp+128h] [rbp+6Fh] BYREF
  const WCHAR *v32; // [rsp+130h] [rbp+77h] BYREF
  const unsigned __int16 *v33; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = TraceLog::Providers::Reliability::Provider();
      v8 = (__int64)v7;
      if ( *(_DWORD *)v7 > 2u )
      {
        v9 = *((_QWORD *)v7 + 3);
        if ( (*(_QWORD *)(v8 + 16) & 0x200000000000LL) != 0 && (v9 & 0x200000000000LL) == v9 )
        {
          v10 = a1[34];
          v22 = *(const WCHAR **)(v6 + 120);
          v23 = *(const unsigned __int16 **)(v6 + 112);
          v31 = *(_DWORD *)(v6 + 104);
          v24 = *(const WCHAR **)(v6 + 96);
          v25 = *(const unsigned __int16 **)(v6 + 88);
          v30 = *(_DWORD *)(v6 + 80);
          v26 = *(const unsigned __int16 **)(v6 + 72);
          LODWORD(v32) = *(_DWORD *)(v6 + 32);
          v27 = *(const WCHAR **)(v6 + 24);
          LODWORD(v33) = *(_DWORD *)v6;
          v28 = *(const unsigned __int16 **)(v6 + 128);
          v19 = *(_DWORD *)(v6 + 64);
          v29 = *(const unsigned __int16 **)(v6 + 56);
          v20 = *(_DWORD *)(v6 + 8);
          v21 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v8,
            (__int64)byte_18003D04B,
            v10 + 8,
            v8,
            (__int64)&v21,
            (__int64)&v20,
            &v29,
            (__int64)&v19,
            &v28,
            (__int64)&v33,
            &v27,
            (__int64)&v32,
            &v26,
            (__int64)&v30,
            &v25,
            &v24,
            (__int64)&v31,
            &v23,
            &v22);
        }
      }
    }
    else
    {
      v11 = TraceLog::Providers::Reliability::Provider();
      v12 = (__int64)v11;
      if ( *(_DWORD *)v11 > 2u )
      {
        v13 = *((_QWORD *)v11 + 3);
        if ( (*(_QWORD *)(v12 + 16) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
        {
          v14 = a1[34];
          v32 = *(const WCHAR **)(v14 + 56);
          v33 = *(const unsigned __int16 **)(v14 + 48);
          CurrentThreadId = GetCurrentThreadId();
          v16 = a1[34];
          v31 = CurrentThreadId;
          v30 = a2;
          v21 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v12,
            (__int64)word_18003D162,
            v16 + 8,
            v17,
            (__int64)&v21,
            (__int64)&v30,
            (__int64)&v31,
            &v33,
            &v32);
        }
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x1800204b8  push    rbp
0x1800204ba  push    rbx
0x1800204bb  push    rsi
0x1800204bc  push    rdi
0x1800204bd  lea     rbp, [rsp-3Fh]
0x1800204c2  sub     rsp, 0F8h
0x1800204c9  mov     esi, edx
0x1800204cb  mov     rbx, rcx
0x1800204ce  test    edx, edx
0x1800204d0  jns     loc_1800206FF
0x1800204d6  mov     rdi, [rcx+110h]
0x1800204dd  mov     eax, [rdi+48h]
0x1800204e0  test    eax, eax
0x1800204e2  jns     loc_180020658
0x1800204e8  add     rdi, 50h ; 'P'
0x1800204ec  cmp     eax, [rdi+8]
0x1800204ef  jnz     loc_180020658
0x1800204f5  test    rdi, rdi
0x1800204f8  jz      loc_180020658
0x1800204fe  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x180020503  mov     r9, rax
0x180020506  mov     ecx, [rax]
0x180020508  cmp     ecx, 2
0x18002050b  jbe     loc_1800206FF
0x180020511  mov     rax, [rax+18h]
0x180020515  mov     rdx, 200000000000h
0x18002051f  mov     rcx, [r9+10h]
0x180020523  test    rdx, rcx
0x180020526  jz      loc_1800206FF
0x18002052c  mov     rcx, rax
0x18002052f  and     rcx, rdx
0x180020532  cmp     rcx, rax
0x180020535  jnz     loc_1800206FF
0x18002053b  mov     rax, [rdi+78h]
0x18002053f  lea     rdx, byte_18003D04B
0x180020546  mov     r8, [rbx+110h]
0x18002054d  mov     rcx, r9
0x180020550  mov     [rbp+57h+var_60], rax
0x180020554  add     r8, 8
0x180020558  mov     rax, [rdi+70h]
0x18002055c  mov     [rbp+57h+var_58], rax
0x180020560  mov     eax, [rdi+68h]
0x180020563  mov     [rbp+57h+arg_8], eax
0x180020566  mov     rax, [rdi+60h]
0x18002056a  mov     [rbp+57h+var_50], rax
0x18002056e  mov     rax, [rdi+58h]
0x180020572  mov     [rbp+57h+var_48], rax
0x180020576  mov     eax, [rdi+50h]
0x180020579  mov     [rbp+57h+arg_0], eax
0x18002057c  mov     rax, [rdi+48h]
0x180020580  mov     [rbp+57h+var_40], rax
0x180020584  mov     eax, [rdi+20h]
0x180020587  mov     dword ptr [rbp+57h+arg_10], eax
0x18002058a  mov     rax, [rdi+18h]
0x18002058e  mov     [rbp+57h+var_38], rax
0x180020592  mov     eax, [rdi]
0x180020594  mov     dword ptr [rbp+57h+arg_18], eax
0x180020597  mov     rax, [rdi+80h]
0x18002059e  mov     [rbp+57h+var_30], rax
0x1800205a2  mov     eax, [rdi+40h]
0x1800205a5  mov     [rbp+57h+var_70], eax
0x1800205a8  mov     rax, [rdi+38h]
0x1800205ac  mov     [rbp+57h+var_28], rax
0x1800205b0  mov     eax, [rdi+8]
0x1800205b3  mov     [rbp+57h+var_6C], eax
0x1800205b6  lea     rax, [rbp+57h+var_60]
0x1800205ba  mov     [rsp+110h+var_80], rax
0x1800205c2  lea     rax, [rbp+57h+var_58]
0x1800205c6  mov     [rsp+110h+var_88], rax
0x1800205ce  lea     rax, [rbp+57h+arg_8]
0x1800205d2  mov     [rsp+110h+var_90], rax
0x1800205da  lea     rax, [rbp+57h+var_50]
0x1800205de  mov     [rsp+110h+var_98], rax
0x1800205e3  lea     rax, [rbp+57h+var_48]
0x1800205e7  mov     [rsp+110h+var_A0], rax
0x1800205ec  lea     rax, [rbp+57h+arg_0]
0x1800205f0  mov     [rsp+110h+var_A8], rax
0x1800205f5  lea     rax, [rbp+57h+var_40]
0x1800205f9  mov     [rsp+110h+var_B0], rax
0x1800205fe  lea     rax, [rbp+57h+arg_10]
0x180020602  mov     [rsp+110h+var_B8], rax
0x180020607  lea     rax, [rbp+57h+var_38]
0x18002060b  mov     [rsp+110h+var_C0], rax
0x180020610  lea     rax, [rbp+57h+arg_18]
0x180020614  mov     [rsp+110h+var_C8], rax
0x180020619  lea     rax, [rbp+57h+var_30]
0x18002061d  mov     [rsp+110h+var_D0], rax
0x180020622  lea     rax, [rbp+57h+var_70]
0x180020626  mov     [rsp+110h+var_D8], rax
0x18002062b  lea     rax, [rbp+57h+var_28]
0x18002062f  mov     [rsp+110h+var_E0], rax
0x180020634  lea     rax, [rbp+57h+var_6C]
0x180020638  mov     [rsp+110h+var_E8], rax
0x18002063d  lea     rax, [rbp+57h+var_68]
0x180020641  mov     [rsp+110h+var_F0], rax
0x180020646  mov     [rbp+57h+var_68], 1000000h
0x18002064e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180020653  jmp     loc_1800206FF
0x180020658  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x18002065d  mov     rdi, rax
0x180020660  mov     ecx, [rax]
0x180020662  cmp     ecx, 2
0x180020665  jbe     loc_1800206FF
0x18002066b  mov     rax, [rax+18h]
0x18002066f  mov     rdx, 200000000000h
0x180020679  mov     rcx, [rdi+10h]
0x18002067d  test    rdx, rcx
0x180020680  jz      short loc_1800206FF
0x180020682  mov     rcx, rax
0x180020685  and     rcx, rdx
0x180020688  cmp     rcx, rax
0x18002068b  jnz     short loc_1800206FF
0x18002068d  mov     rcx, [rbx+110h]
0x180020694  mov     rax, [rcx+38h]
0x180020698  mov     [rbp+57h+arg_10], rax
0x18002069c  mov     rax, [rcx+30h]
0x1800206a0  mov     [rbp+57h+arg_18], rax
0x1800206a4  call    cs:__imp_GetCurrentThreadId
0x1800206aa  mov     r8, [rbx+110h]
0x1800206b1  lea     rdx, word_18003D162
0x1800206b8  mov     [rbp+57h+arg_8], eax
0x1800206bb  add     r8, 8
0x1800206bf  lea     rax, [rbp+57h+arg_10]
0x1800206c3  mov     [rbp+57h+arg_0], esi
0x1800206c6  mov     [rsp+110h+var_D0], rax
0x1800206cb  mov     rcx, rdi
0x1800206ce  lea     rax, [rbp+57h+arg_18]
0x1800206d2  mov     [rbp+57h+var_68], 1000000h
0x1800206da  mov     [rsp+110h+var_D8], rax
0x1800206df  lea     rax, [rbp+57h+arg_8]
0x1800206e3  mov     [rsp+110h+var_E0], rax
0x1800206e8  lea     rax, [rbp+57h+arg_0]
0x1800206ec  mov     [rsp+110h+var_E8], rax
0x1800206f1  lea     rax, [rbp+57h+var_68]
0x1800206f5  mov     [rsp+110h+var_F0], rax
0x1800206fa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800206ff  mov     rax, [rbx]
0x180020702  mov     rcx, rbx
0x180020705  mov     rax, [rax+8]
0x180020709  add     rsp, 0F8h
0x180020710  pop     rdi
0x180020711  pop     rsi
0x180020712  pop     rbx
0x180020713  pop     rbp
0x180020714  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
