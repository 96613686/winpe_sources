# gpm::TraceProvider::LogCheckProcess(ulong,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,PresentTraceConsumerCore::Config,_GUID)

- ea: `0x1800124b0`
- end: `0x1800125f6`
- name: `?LogCheckProcess@TraceProvider@gpm@@SAXKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UConfig@PresentTraceConsumerCore@@U_GUID@@@Z`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013530`

## callees

- `0x1800018ac`
- `0x180002414`
- `0x18000d778`
- `0x1800124b0`

## pseudocode

```c
void __fastcall gpm::TraceProvider::LogCheckProcess(__int64 a1, const char *a2)
{
  __int64 v3; // rcx
  int *v4; // r8
  __int64 v5; // r9
  int v6; // r10d
  bool v7; // cc
  const char *v8; // rax
  int v9; // [rsp+80h] [rbp-9h] BYREF
  int v10; // [rsp+84h] [rbp-5h] BYREF
  int v11; // [rsp+88h] [rbp-1h] BYREF
  int v12; // [rsp+8Ch] [rbp+3h] BYREF
  int v13; // [rsp+90h] [rbp+7h] BYREF
  int v14; // [rsp+94h] [rbp+Bh] BYREF
  int v15; // [rsp+98h] [rbp+Fh] BYREF
  const char *v16; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+1Fh] BYREF
  __int64 v18; // [rsp+B0h] [rbp+27h] BYREF
  const float near *const *v19; // [rsp+B8h] [rbp+2Fh] BYREF
  int v20; // [rsp+C0h] [rbp+37h]
  const float near *const *v21; // [rsp+C8h] [rbp+3Fh] BYREF
  int v22; // [rsp+D0h] [rbp+47h]

  if ( (unsigned int)dword_180042048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180042048, 0x400000000000LL) )
  {
    v7 = *((_QWORD *)a2 + 3) <= 0xFu;
    v9 = v4[1];
    v10 = *v4;
    v19 = &PresentStatistics::c_HistogramTimingMsBuckets;
    v21 = &PresentStatistics::c_HistogramBuckets;
    v11 = 42;
    v20 = 164;
    v12 = 40;
    v22 = 156;
    if ( v7 )
      v8 = a2;
    else
      v8 = *(const char **)a2;
    v16 = v8;
    v13 = v6;
    v17 = v5;
    v14 = 2;
    v15 = 1;
    v18 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v3,
      (__int64)byte_180039F45,
      (__int64)v4,
      v5,
      (__int64)&v18,
      (__int64)&v15,
      (__int64)&v14,
      &v17,
      (__int64)&v13,
      &v16,
      (__int64 *)&v21,
      (__int64)&v12,
      (__int64 *)&v19,
      (__int64)&v11,
      (__int64)&v10,
      (__int64)&v9);
  }
  std::string::_Tidy_deallocate((__int64)a2);
}

```

## disassembly

```asm
0x1800124b0  mov     [rsp-8+arg_0], rbx
0x1800124b5  push    rbp
0x1800124b6  lea     rbp, [rsp-57h]
0x1800124bb  sub     rsp, 0E0h
0x1800124c2  mov     eax, cs:dword_180042048
0x1800124c8  mov     rbx, rdx
0x1800124cb  mov     r10d, ecx
0x1800124ce  cmp     eax, 5
0x1800124d1  jbe     loc_1800125DD
0x1800124d7  mov     rdx, 400000000000h
0x1800124e1  lea     rcx, dword_180042048
0x1800124e8  call    _tlgKeywordOn
0x1800124ed  test    al, al
0x1800124ef  jz      loc_1800125DD
0x1800124f5  cmp     qword ptr [rbx+18h], 0Fh
0x1800124fa  mov     eax, [r8+4]
0x1800124fe  mov     [rbp+57h+var_60], eax
0x180012501  mov     eax, [r8]
0x180012504  mov     [rbp+57h+var_5C], eax
0x180012507  lea     rax, ?c_HistogramTimingMsBuckets@PresentStatistics@@2QBMB; float const near * const PresentStatistics::c_HistogramTimingMsBuckets
0x18001250e  mov     [rbp+57h+var_28], rax
0x180012512  lea     rax, ?c_HistogramBuckets@PresentStatistics@@2QBMB; float const near * const PresentStatistics::c_HistogramBuckets
0x180012519  mov     [rbp+57h+var_18], rax
0x18001251d  mov     [rbp+57h+var_58], 2Ah ; '*'
0x180012524  mov     [rbp+57h+var_20], 0A4h
0x18001252b  mov     [rbp+57h+var_54], 28h ; '('
0x180012532  mov     [rbp+57h+var_10], 9Ch
0x180012539  jbe     short loc_180012540
0x18001253b  mov     rax, [rbx]
0x18001253e  jmp     short loc_180012543
0x180012540  mov     rax, rbx
0x180012543  mov     [rbp+57h+var_40], rax
0x180012547  lea     rdx, byte_180039F45
0x18001254e  lea     rax, [rbp+57h+var_60]
0x180012552  mov     [rbp+57h+var_50], r10d
0x180012556  mov     [rsp+0E0h+var_68], rax
0x18001255b  lea     rax, [rbp+57h+var_5C]
0x18001255f  mov     [rsp+0E0h+var_70], rax
0x180012564  lea     rax, [rbp+57h+var_58]
0x180012568  mov     [rsp+0E0h+var_78], rax
0x18001256d  lea     rax, [rbp+57h+var_28]
0x180012571  mov     [rsp+0E0h+var_80], rax
0x180012576  lea     rax, [rbp+57h+var_54]
0x18001257a  mov     [rsp+0E0h+var_88], rax
0x18001257f  lea     rax, [rbp+57h+var_18]
0x180012583  mov     [rsp+0E0h+var_90], rax
0x180012588  lea     rax, [rbp+57h+var_40]
0x18001258c  mov     [rsp+0E0h+var_98], rax
0x180012591  lea     rax, [rbp+57h+var_50]
0x180012595  mov     [rsp+0E0h+var_A0], rax
0x18001259a  lea     rax, [rbp+57h+var_38]
0x18001259e  mov     [rsp+0E0h+var_A8], rax
0x1800125a3  lea     rax, [rbp+57h+var_4C]
0x1800125a7  mov     [rsp+0E0h+var_B0], rax
0x1800125ac  lea     rax, [rbp+57h+var_48]
0x1800125b0  mov     [rsp+0E0h+var_B8], rax
0x1800125b5  lea     rax, [rbp+57h+var_30]
0x1800125b9  mov     [rsp+0E0h+var_C0], rax
0x1800125be  mov     [rbp+57h+var_38], r9
0x1800125c2  mov     [rbp+57h+var_4C], 2
0x1800125c9  mov     [rbp+57h+var_48], 1
0x1800125d0  mov     [rbp+57h+var_30], 1000000h
0x1800125d8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapSz@D@@U_tlgWrapperPtrSize@@U2@U5@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapSz@D@@AEBU_tlgWrapperPtrSize@@47444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800125dd  mov     rcx, rbx
0x1800125e0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800125e5  mov     rbx, [rsp+0E0h+arg_0]
0x1800125ed  add     rsp, 0E0h
0x1800125f4  pop     rbp
0x1800125f5  retn
```
