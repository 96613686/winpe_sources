# MSAClientTraceTelemetry::CreateConnectedAccountOobe::StopActivity(void)

- ea: `0x180017f30`
- end: `0x180018154`
- name: `?StopActivity@CreateConnectedAccountOobe@MSAClientTraceTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(MSAClientTraceTelemetry::CreateConnectedAccountOobe *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x1800019e0`
- `0x180001d58`
- `0x180002000`
- `0x180015540`
- `0x18001610c`
- `0x180017f30`
- `0x18001ba64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800180f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800180f5`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::CreateConnectedAccountOobe::StopActivity(
        MSAClientTraceTelemetry::CreateConnectedAccountOobe *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  const WCHAR *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = MSAClientTraceTelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6) )
    {
      v8 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      v27[0] = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)&unk_180046540,
        v9 + 8,
        v7,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = MSAClientTraceTelemetry::Provider();
    v12 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_1800464E5,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180017f30  push    rbp
0x180017f32  push    rbx
0x180017f33  push    rdi
0x180017f34  lea     rbp, [rsp-47h]
0x180017f39  sub     rsp, 100h
0x180017f40  mov     rdi, [rcx+110h]
0x180017f47  mov     rbx, rcx
0x180017f4a  mov     eax, [rdi+48h]
0x180017f4d  test    eax, eax
0x180017f4f  jns     loc_1800180CB
0x180017f55  add     rdi, 50h ; 'P'
0x180017f59  cmp     eax, [rdi+8]
0x180017f5c  jnz     loc_1800180CB
0x180017f62  test    rdi, rdi
0x180017f65  jz      loc_1800180CB
0x180017f6b  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180017f70  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180017f75  mov     r9, rax
0x180017f78  mov     ecx, [rax]
0x180017f7a  cmp     ecx, 5
0x180017f7d  jbe     loc_180018142
0x180017f83  mov     rdx, 400000000000h
0x180017f8d  mov     rcx, rax
0x180017f90  call    _tlgKeywordOn
0x180017f95  test    al, al
0x180017f97  jz      loc_180018142
0x180017f9d  mov     rax, [rdi+70h]
0x180017fa1  lea     rdx, unk_180046540
0x180017fa8  mov     rcx, [rdi+78h]
0x180017fac  mov     r8, [rbx+110h]
0x180017fb3  mov     [rbp+57h+var_60], rax
0x180017fb7  add     r8, 8
0x180017fbb  mov     eax, [rdi+68h]
0x180017fbe  mov     [rbp+57h+arg_0], eax
0x180017fc1  mov     rax, [rdi+60h]
0x180017fc5  mov     [rbp+57h+var_58], rax
0x180017fc9  mov     rax, [rdi+58h]
0x180017fcd  mov     [rbp+57h+var_50], rax
0x180017fd1  mov     eax, [rdi+50h]
0x180017fd4  mov     [rbp+57h+arg_8], eax
0x180017fd7  mov     rax, [rdi+48h]
0x180017fdb  mov     [rbp+57h+var_48], rax
0x180017fdf  mov     eax, [rdi+20h]
0x180017fe2  mov     dword ptr [rbp+57h+arg_10], eax
0x180017fe5  mov     rax, [rdi+18h]
0x180017fe9  mov     [rbp+57h+var_40], rax
0x180017fed  mov     eax, [rdi]
0x180017fef  mov     [rbp+57h+arg_18], eax
0x180017ff2  mov     rax, [rdi+80h]
0x180017ff9  mov     [rbp+57h+var_38], rax
0x180017ffd  mov     eax, [rdi+40h]
0x180018000  mov     [rbp+57h+var_70], eax
0x180018003  mov     rax, [rdi+38h]
0x180018007  mov     [rbp+57h+var_30], rax
0x18001800b  mov     eax, [rdi+8]
0x18001800e  mov     [rbp+57h+var_6C], eax
0x180018011  lea     rax, [rbp+57h+var_68]
0x180018015  mov     [rsp+110h+var_78], rax
0x18001801d  lea     rax, [rbp+57h+var_60]
0x180018021  mov     [rsp+110h+var_80], rax
0x180018029  lea     rax, [rbp+57h+arg_0]
0x18001802d  mov     [rsp+110h+var_88], rax
0x180018035  lea     rax, [rbp+57h+var_58]
0x180018039  mov     [rsp+110h+var_90], rax
0x180018041  lea     rax, [rbp+57h+var_50]
0x180018045  mov     [rsp+110h+var_98], rax
0x18001804a  lea     rax, [rbp+57h+arg_8]
0x18001804e  mov     [rsp+110h+var_A0], rax
0x180018053  lea     rax, [rbp+57h+var_48]
0x180018057  mov     [rsp+110h+var_A8], rax
0x18001805c  lea     rax, [rbp+57h+arg_10]
0x180018060  mov     [rsp+110h+var_B0], rax
0x180018065  lea     rax, [rbp+57h+var_40]
0x180018069  mov     [rsp+110h+var_B8], rax
0x18001806e  lea     rax, [rbp+57h+arg_18]
0x180018072  mov     [rsp+110h+var_C0], rax
0x180018077  lea     rax, [rbp+57h+var_38]
0x18001807b  mov     [rsp+110h+var_C8], rax
0x180018080  lea     rax, [rbp+57h+var_70]
0x180018084  mov     [rsp+110h+var_D0], rax
0x180018089  lea     rax, [rbp+57h+var_30]
0x18001808d  mov     [rsp+110h+var_D8], rax
0x180018092  lea     rax, [rbp+57h+var_6C]
0x180018096  mov     [rsp+110h+var_E0], rax
0x18001809b  lea     rax, [rbp+57h+var_28]
0x18001809f  mov     [rsp+110h+var_E8], rax
0x1800180a4  lea     rax, [rbp+57h+var_20]
0x1800180a8  mov     [rbp+57h+var_68], rcx
0x1800180ac  mov     rcx, r9
0x1800180af  mov     [rsp+110h+var_F0], rax
0x1800180b4  mov     [rbp+57h+var_28], 1000000h
0x1800180bc  mov     [rbp+57h+var_20], 2000000h
0x1800180c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800180c9  jmp     short loc_180018142
0x1800180cb  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800180d0  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x1800180d5  mov     rdi, rax
0x1800180d8  mov     ecx, [rax]
0x1800180da  cmp     ecx, 5
0x1800180dd  jbe     short loc_180018142
0x1800180df  mov     rdx, 400000000000h
0x1800180e9  mov     rcx, rax
0x1800180ec  call    _tlgKeywordOn
0x1800180f1  test    al, al
0x1800180f3  jz      short loc_180018142
0x1800180f5  call    cs:__imp_GetCurrentThreadId
0x1800180fb  mov     r8, [rbx+110h]
0x180018102  lea     rdx, byte_1800464E5
0x180018109  mov     [rbp+57h+arg_0], eax
0x18001810c  mov     rcx, rdi
0x18001810f  mov     eax, [r8+48h]
0x180018113  add     r8, 8
0x180018117  mov     [rbp+57h+arg_8], eax
0x18001811a  lea     rax, [rbp+57h+arg_0]
0x18001811e  mov     [rsp+110h+var_E0], rax
0x180018123  lea     rax, [rbp+57h+arg_8]
0x180018127  mov     [rsp+110h+var_E8], rax
0x18001812c  lea     rax, [rbp+57h+arg_10]
0x180018130  mov     [rsp+110h+var_F0], rax
0x180018135  mov     [rbp+57h+arg_10], 2000000h
0x18001813d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018142  mov     rcx, rbx
0x180018145  add     rsp, 100h
0x18001814c  pop     rdi
0x18001814d  pop     rbx
0x18001814e  pop     rbp
0x18001814f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
