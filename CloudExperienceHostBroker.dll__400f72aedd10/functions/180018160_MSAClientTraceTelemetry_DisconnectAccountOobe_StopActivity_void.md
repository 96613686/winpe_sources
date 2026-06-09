# MSAClientTraceTelemetry::DisconnectAccountOobe::StopActivity(void)

- ea: `0x180018160`
- end: `0x180018384`
- name: `?StopActivity@DisconnectAccountOobe@MSAClientTraceTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(MSAClientTraceTelemetry::DisconnectAccountOobe *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x1800019e0`
- `0x180001d58`
- `0x180002000`
- `0x180015540`
- `0x18001610c`
- `0x180018160`
- `0x18001ba64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018325`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::DisconnectAccountOobe::StopActivity(
        MSAClientTraceTelemetry::DisconnectAccountOobe *this)
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
        (__int64)&word_180046366,
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
        (__int64)&unk_180046310,
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
0x180018160  push    rbp
0x180018162  push    rbx
0x180018163  push    rdi
0x180018164  lea     rbp, [rsp-47h]
0x180018169  sub     rsp, 100h
0x180018170  mov     rdi, [rcx+110h]
0x180018177  mov     rbx, rcx
0x18001817a  mov     eax, [rdi+48h]
0x18001817d  test    eax, eax
0x18001817f  jns     loc_1800182FB
0x180018185  add     rdi, 50h ; 'P'
0x180018189  cmp     eax, [rdi+8]
0x18001818c  jnz     loc_1800182FB
0x180018192  test    rdi, rdi
0x180018195  jz      loc_1800182FB
0x18001819b  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800181a0  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x1800181a5  mov     r9, rax
0x1800181a8  mov     ecx, [rax]
0x1800181aa  cmp     ecx, 5
0x1800181ad  jbe     loc_180018372
0x1800181b3  mov     rdx, 400000000000h
0x1800181bd  mov     rcx, rax
0x1800181c0  call    _tlgKeywordOn
0x1800181c5  test    al, al
0x1800181c7  jz      loc_180018372
0x1800181cd  mov     rax, [rdi+70h]
0x1800181d1  lea     rdx, word_180046366
0x1800181d8  mov     rcx, [rdi+78h]
0x1800181dc  mov     r8, [rbx+110h]
0x1800181e3  mov     [rbp+57h+var_60], rax
0x1800181e7  add     r8, 8
0x1800181eb  mov     eax, [rdi+68h]
0x1800181ee  mov     [rbp+57h+arg_0], eax
0x1800181f1  mov     rax, [rdi+60h]
0x1800181f5  mov     [rbp+57h+var_58], rax
0x1800181f9  mov     rax, [rdi+58h]
0x1800181fd  mov     [rbp+57h+var_50], rax
0x180018201  mov     eax, [rdi+50h]
0x180018204  mov     [rbp+57h+arg_8], eax
0x180018207  mov     rax, [rdi+48h]
0x18001820b  mov     [rbp+57h+var_48], rax
0x18001820f  mov     eax, [rdi+20h]
0x180018212  mov     dword ptr [rbp+57h+arg_10], eax
0x180018215  mov     rax, [rdi+18h]
0x180018219  mov     [rbp+57h+var_40], rax
0x18001821d  mov     eax, [rdi]
0x18001821f  mov     [rbp+57h+arg_18], eax
0x180018222  mov     rax, [rdi+80h]
0x180018229  mov     [rbp+57h+var_38], rax
0x18001822d  mov     eax, [rdi+40h]
0x180018230  mov     [rbp+57h+var_70], eax
0x180018233  mov     rax, [rdi+38h]
0x180018237  mov     [rbp+57h+var_30], rax
0x18001823b  mov     eax, [rdi+8]
0x18001823e  mov     [rbp+57h+var_6C], eax
0x180018241  lea     rax, [rbp+57h+var_68]
0x180018245  mov     [rsp+110h+var_78], rax
0x18001824d  lea     rax, [rbp+57h+var_60]
0x180018251  mov     [rsp+110h+var_80], rax
0x180018259  lea     rax, [rbp+57h+arg_0]
0x18001825d  mov     [rsp+110h+var_88], rax
0x180018265  lea     rax, [rbp+57h+var_58]
0x180018269  mov     [rsp+110h+var_90], rax
0x180018271  lea     rax, [rbp+57h+var_50]
0x180018275  mov     [rsp+110h+var_98], rax
0x18001827a  lea     rax, [rbp+57h+arg_8]
0x18001827e  mov     [rsp+110h+var_A0], rax
0x180018283  lea     rax, [rbp+57h+var_48]
0x180018287  mov     [rsp+110h+var_A8], rax
0x18001828c  lea     rax, [rbp+57h+arg_10]
0x180018290  mov     [rsp+110h+var_B0], rax
0x180018295  lea     rax, [rbp+57h+var_40]
0x180018299  mov     [rsp+110h+var_B8], rax
0x18001829e  lea     rax, [rbp+57h+arg_18]
0x1800182a2  mov     [rsp+110h+var_C0], rax
0x1800182a7  lea     rax, [rbp+57h+var_38]
0x1800182ab  mov     [rsp+110h+var_C8], rax
0x1800182b0  lea     rax, [rbp+57h+var_70]
0x1800182b4  mov     [rsp+110h+var_D0], rax
0x1800182b9  lea     rax, [rbp+57h+var_30]
0x1800182bd  mov     [rsp+110h+var_D8], rax
0x1800182c2  lea     rax, [rbp+57h+var_6C]
0x1800182c6  mov     [rsp+110h+var_E0], rax
0x1800182cb  lea     rax, [rbp+57h+var_28]
0x1800182cf  mov     [rsp+110h+var_E8], rax
0x1800182d4  lea     rax, [rbp+57h+var_20]
0x1800182d8  mov     [rbp+57h+var_68], rcx
0x1800182dc  mov     rcx, r9
0x1800182df  mov     [rsp+110h+var_F0], rax
0x1800182e4  mov     [rbp+57h+var_28], 1000000h
0x1800182ec  mov     [rbp+57h+var_20], 2000000h
0x1800182f4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800182f9  jmp     short loc_180018372
0x1800182fb  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018300  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180018305  mov     rdi, rax
0x180018308  mov     ecx, [rax]
0x18001830a  cmp     ecx, 5
0x18001830d  jbe     short loc_180018372
0x18001830f  mov     rdx, 400000000000h
0x180018319  mov     rcx, rax
0x18001831c  call    _tlgKeywordOn
0x180018321  test    al, al
0x180018323  jz      short loc_180018372
0x180018325  call    cs:__imp_GetCurrentThreadId
0x18001832b  mov     r8, [rbx+110h]
0x180018332  lea     rdx, unk_180046310
0x180018339  mov     [rbp+57h+arg_0], eax
0x18001833c  mov     rcx, rdi
0x18001833f  mov     eax, [r8+48h]
0x180018343  add     r8, 8
0x180018347  mov     [rbp+57h+arg_8], eax
0x18001834a  lea     rax, [rbp+57h+arg_0]
0x18001834e  mov     [rsp+110h+var_E0], rax
0x180018353  lea     rax, [rbp+57h+arg_8]
0x180018357  mov     [rsp+110h+var_E8], rax
0x18001835c  lea     rax, [rbp+57h+arg_10]
0x180018360  mov     [rsp+110h+var_F0], rax
0x180018365  mov     [rbp+57h+arg_10], 2000000h
0x18001836d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018372  mov     rcx, rbx
0x180018375  add     rsp, 100h
0x18001837c  pop     rdi
0x18001837d  pop     rbx
0x18001837e  pop     rbp
0x18001837f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
