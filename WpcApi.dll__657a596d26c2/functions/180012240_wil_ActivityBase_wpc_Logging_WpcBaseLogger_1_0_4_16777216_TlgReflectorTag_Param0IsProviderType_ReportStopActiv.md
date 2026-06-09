# wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x180012240`
- end: `0x1800124a1`
- name: `?ReportStopActivity@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `609`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ff10`
- `0x180013010`

## callees

- `0x180001660`
- `0x18000175c`
- `0x180010d90`
- `0x180012240`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001242c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001242c`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
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
      v7 = wpc::Logging::WpcBaseLogger::Provider();
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
            (__int64)byte_18003C9F1,
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
      v11 = wpc::Logging::WpcBaseLogger::Provider();
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
            (__int64)&unk_18003C6E0,
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
0x180012240  push    rbp
0x180012242  push    rbx
0x180012243  push    rsi
0x180012244  push    rdi
0x180012245  lea     rbp, [rsp-3Fh]
0x18001224a  sub     rsp, 0F8h
0x180012251  mov     esi, edx
0x180012253  mov     rbx, rcx
0x180012256  test    edx, edx
0x180012258  jns     loc_180012487
0x18001225e  mov     rdi, [rcx+110h]
0x180012265  mov     eax, [rdi+48h]
0x180012268  test    eax, eax
0x18001226a  jns     loc_1800123E0
0x180012270  add     rdi, 50h ; 'P'
0x180012274  cmp     eax, [rdi+8]
0x180012277  jnz     loc_1800123E0
0x18001227d  test    rdi, rdi
0x180012280  jz      loc_1800123E0
0x180012286  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x18001228b  mov     r9, rax
0x18001228e  mov     ecx, [rax]
0x180012290  cmp     ecx, 2
0x180012293  jbe     loc_180012487
0x180012299  mov     rax, [rax+18h]
0x18001229d  mov     rdx, 200000000000h
0x1800122a7  mov     rcx, [r9+10h]
0x1800122ab  test    rdx, rcx
0x1800122ae  jz      loc_180012487
0x1800122b4  mov     rcx, rax
0x1800122b7  and     rcx, rdx
0x1800122ba  cmp     rcx, rax
0x1800122bd  jnz     loc_180012487
0x1800122c3  mov     rax, [rdi+78h]
0x1800122c7  lea     rdx, byte_18003C9F1
0x1800122ce  mov     r8, [rbx+110h]
0x1800122d5  mov     rcx, r9
0x1800122d8  mov     [rbp+57h+var_60], rax
0x1800122dc  add     r8, 8
0x1800122e0  mov     rax, [rdi+70h]
0x1800122e4  mov     [rbp+57h+var_58], rax
0x1800122e8  mov     eax, [rdi+68h]
0x1800122eb  mov     [rbp+57h+arg_8], eax
0x1800122ee  mov     rax, [rdi+60h]
0x1800122f2  mov     [rbp+57h+var_50], rax
0x1800122f6  mov     rax, [rdi+58h]
0x1800122fa  mov     [rbp+57h+var_48], rax
0x1800122fe  mov     eax, [rdi+50h]
0x180012301  mov     [rbp+57h+arg_0], eax
0x180012304  mov     rax, [rdi+48h]
0x180012308  mov     [rbp+57h+var_40], rax
0x18001230c  mov     eax, [rdi+20h]
0x18001230f  mov     dword ptr [rbp+57h+arg_10], eax
0x180012312  mov     rax, [rdi+18h]
0x180012316  mov     [rbp+57h+var_38], rax
0x18001231a  mov     eax, [rdi]
0x18001231c  mov     dword ptr [rbp+57h+arg_18], eax
0x18001231f  mov     rax, [rdi+80h]
0x180012326  mov     [rbp+57h+var_30], rax
0x18001232a  mov     eax, [rdi+40h]
0x18001232d  mov     [rbp+57h+var_70], eax
0x180012330  mov     rax, [rdi+38h]
0x180012334  mov     [rbp+57h+var_28], rax
0x180012338  mov     eax, [rdi+8]
0x18001233b  mov     [rbp+57h+var_6C], eax
0x18001233e  lea     rax, [rbp+57h+var_60]
0x180012342  mov     [rsp+110h+var_80], rax
0x18001234a  lea     rax, [rbp+57h+var_58]
0x18001234e  mov     [rsp+110h+var_88], rax
0x180012356  lea     rax, [rbp+57h+arg_8]
0x18001235a  mov     [rsp+110h+var_90], rax
0x180012362  lea     rax, [rbp+57h+var_50]
0x180012366  mov     [rsp+110h+var_98], rax
0x18001236b  lea     rax, [rbp+57h+var_48]
0x18001236f  mov     [rsp+110h+var_A0], rax
0x180012374  lea     rax, [rbp+57h+arg_0]
0x180012378  mov     [rsp+110h+var_A8], rax
0x18001237d  lea     rax, [rbp+57h+var_40]
0x180012381  mov     [rsp+110h+var_B0], rax
0x180012386  lea     rax, [rbp+57h+arg_10]
0x18001238a  mov     [rsp+110h+var_B8], rax
0x18001238f  lea     rax, [rbp+57h+var_38]
0x180012393  mov     [rsp+110h+var_C0], rax
0x180012398  lea     rax, [rbp+57h+arg_18]
0x18001239c  mov     [rsp+110h+var_C8], rax
0x1800123a1  lea     rax, [rbp+57h+var_30]
0x1800123a5  mov     [rsp+110h+var_D0], rax
0x1800123aa  lea     rax, [rbp+57h+var_70]
0x1800123ae  mov     [rsp+110h+var_D8], rax
0x1800123b3  lea     rax, [rbp+57h+var_28]
0x1800123b7  mov     [rsp+110h+var_E0], rax
0x1800123bc  lea     rax, [rbp+57h+var_6C]
0x1800123c0  mov     [rsp+110h+var_E8], rax
0x1800123c5  lea     rax, [rbp+57h+var_68]
0x1800123c9  mov     [rsp+110h+var_F0], rax
0x1800123ce  mov     [rbp+57h+var_68], 1000000h
0x1800123d6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800123db  jmp     loc_180012487
0x1800123e0  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x1800123e5  mov     rdi, rax
0x1800123e8  mov     ecx, [rax]
0x1800123ea  cmp     ecx, 2
0x1800123ed  jbe     loc_180012487
0x1800123f3  mov     rax, [rax+18h]
0x1800123f7  mov     rdx, 200000000000h
0x180012401  mov     rcx, [rdi+10h]
0x180012405  test    rdx, rcx
0x180012408  jz      short loc_180012487
0x18001240a  mov     rcx, rax
0x18001240d  and     rcx, rdx
0x180012410  cmp     rcx, rax
0x180012413  jnz     short loc_180012487
0x180012415  mov     rcx, [rbx+110h]
0x18001241c  mov     rax, [rcx+38h]
0x180012420  mov     [rbp+57h+arg_10], rax
0x180012424  mov     rax, [rcx+30h]
0x180012428  mov     [rbp+57h+arg_18], rax
0x18001242c  call    cs:__imp_GetCurrentThreadId
0x180012432  mov     r8, [rbx+110h]
0x180012439  lea     rdx, unk_18003C6E0
0x180012440  mov     [rbp+57h+arg_8], eax
0x180012443  add     r8, 8
0x180012447  lea     rax, [rbp+57h+arg_10]
0x18001244b  mov     [rbp+57h+arg_0], esi
0x18001244e  mov     [rsp+110h+var_D0], rax
0x180012453  mov     rcx, rdi
0x180012456  lea     rax, [rbp+57h+arg_18]
0x18001245a  mov     [rbp+57h+var_68], 1000000h
0x180012462  mov     [rsp+110h+var_D8], rax
0x180012467  lea     rax, [rbp+57h+arg_8]
0x18001246b  mov     [rsp+110h+var_E0], rax
0x180012470  lea     rax, [rbp+57h+arg_0]
0x180012474  mov     [rsp+110h+var_E8], rax
0x180012479  lea     rax, [rbp+57h+var_68]
0x18001247d  mov     [rsp+110h+var_F0], rax
0x180012482  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180012487  mov     rax, [rbx]
0x18001248a  mov     rcx, rbx
0x18001248d  mov     rax, [rax+8]
0x180012491  add     rsp, 0F8h
0x180012498  pop     rdi
0x180012499  pop     rsi
0x18001249a  pop     rbx
0x18001249b  pop     rbp
0x18001249c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
