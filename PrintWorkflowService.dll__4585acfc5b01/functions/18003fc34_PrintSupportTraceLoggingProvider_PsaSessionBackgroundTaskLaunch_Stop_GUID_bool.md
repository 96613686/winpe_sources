# PrintSupportTraceLoggingProvider::PsaSessionBackgroundTaskLaunch::Stop(_GUID,bool)

- ea: `0x18003fc34`
- end: `0x18003ff02`
- name: `?Stop@PsaSessionBackgroundTaskLaunch@PrintSupportTraceLoggingProvider@@QEAAXU_GUID@@_N@Z`
- size: `718`
- prototype: `void __fastcall(PrintSupportTraceLoggingProvider::PsaSessionBackgroundTaskLaunch *__hidden this, struct _GUID *__struct_ptr, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18003ce08`

## callees

- `0x1800014bc`
- `0x1800014e8`
- `0x180002a20`
- `0x180003ca0`
- `0x18001b0d4`
- `0x18001ccb0`
- `0x18003e98c`
- `0x18003fc34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fe43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fe43`

## pseudocode

```c
void __fastcall PrintSupportTraceLoggingProvider::PsaSessionBackgroundTaskLaunch::Stop(
        PrintSupportTraceLoggingProvider::PsaSessionBackgroundTaskLaunch *this,
        struct _GUID *a2,
        char a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int *v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  _BYTE v18[4]; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  DWORD v20; // [rsp+B8h] [rbp-78h] BYREF
  int v21; // [rsp+BCh] [rbp-74h] BYREF
  int v22; // [rsp+C0h] [rbp-70h] BYREF
  int v23; // [rsp+C4h] [rbp-6Ch] BYREF
  int v24; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v25; // [rsp+D0h] [rbp-60h] BYREF
  struct _GUID *v26; // [rsp+D8h] [rbp-58h] BYREF
  const WCHAR *v27; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v28; // [rsp+E8h] [rbp-48h] BYREF
  const WCHAR *v29; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v30; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v31; // [rsp+100h] [rbp-30h] BYREF
  const WCHAR *v32; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v33; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v34; // [rsp+118h] [rbp-18h] BYREF
  __int64 v35; // [rsp+120h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+130h] [rbp+0h] BYREF
  __int64 *v37; // [rsp+150h] [rbp+20h]
  __int64 v38; // [rsp+158h] [rbp+28h]
  int *v39; // [rsp+160h] [rbp+30h]
  __int64 v40; // [rsp+168h] [rbp+38h]
  DWORD *v41; // [rsp+170h] [rbp+40h]
  __int64 v42; // [rsp+178h] [rbp+48h]
  struct _GUID *v43; // [rsp+180h] [rbp+50h]
  __int64 v44; // [rsp+188h] [rbp+58h]
  _BYTE *v45; // [rsp+190h] [rbp+60h]
  __int64 v46; // [rsp+198h] [rbp+68h]

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<PrintSupportTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = PrintSupportTraceLoggingProvider::Provider();
    v12 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    {
      v27 = (const WCHAR *)*((_QWORD *)v8 + 15);
      v28 = (const unsigned __int16 *)*((_QWORD *)v8 + 14);
      v13 = *((_QWORD *)this + 34);
      v21 = v8[26];
      v29 = (const WCHAR *)*((_QWORD *)v8 + 12);
      v30 = (const unsigned __int16 *)*((_QWORD *)v8 + 11);
      v22 = v8[20];
      v31 = (const unsigned __int16 *)*((_QWORD *)v8 + 9);
      v23 = v8[8];
      v32 = (const WCHAR *)*((_QWORD *)v8 + 3);
      v24 = *v8;
      v33 = (const unsigned __int16 *)*((_QWORD *)v8 + 16);
      v19 = v8[16];
      v34 = (const unsigned __int16 *)*((_QWORD *)v8 + 7);
      v20 = v8[2];
      v35 = 0x1000000;
      v25 = 0x1000000;
      v18[0] = a3;
      v26 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
        v12,
        (__int64)byte_18007416D,
        v13 + 8,
        v12,
        (__int64)&v25,
        (__int64)&v35,
        (__int64)&v20,
        &v34,
        (__int64)&v19,
        &v33,
        (__int64)&v24,
        &v32,
        (__int64)&v23,
        &v31,
        (__int64)&v22,
        &v30,
        &v29,
        (__int64)&v21,
        &v28,
        &v27,
        (__int64 *)&v26,
        (__int64)v18);
    }
  }
  else
  {
    wil::ActivityBase<PrintSupportTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = PrintSupportTraceLoggingProvider::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL) )
    {
      v18[0] = a3;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v20 = CurrentThreadId;
      v46 = 1;
      v43 = a2;
      v19 = *(_DWORD *)(v17 + 72);
      v25 = 0x1000000;
      v45 = v18;
      v41 = &v20;
      v39 = &v19;
      v37 = &v25;
      v44 = 16;
      v42 = 4;
      v40 = 4;
      v38 = 8;
      tlgWriteTransfer_EventWriteTransfer(v15, (unsigned __int8 *)byte_1800742C3, (const GUID *)(v17 + 8), 0, 7u, &v36);
    }
  }
  wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v10,
    v11,
    v12);
}

```

## disassembly

```asm
0x18003fc34  mov     [rsp-8+arg_8], rbx
0x18003fc39  mov     [rsp-8+arg_10], rsi
0x18003fc3e  push    rbp
0x18003fc3f  push    rdi
0x18003fc40  push    r14
0x18003fc42  lea     rbp, [rsp-80h]
0x18003fc47  sub     rsp, 1B0h
0x18003fc4e  mov     rax, cs:__security_cookie
0x18003fc55  xor     rax, rsp
0x18003fc58  mov     [rbp+90h+var_20], rax
0x18003fc5c  mov     rdi, [rcx+110h]
0x18003fc63  mov     sil, r8b
0x18003fc66  mov     r14, rdx
0x18003fc69  mov     rbx, rcx
0x18003fc6c  mov     eax, [rdi+48h]
0x18003fc6f  test    eax, eax
0x18003fc71  jns     loc_18003FE0D
0x18003fc77  add     rdi, 50h ; 'P'
0x18003fc7b  cmp     eax, [rdi+8]
0x18003fc7e  jnz     loc_18003FE0D
0x18003fc84  test    rdi, rdi
0x18003fc87  jz      loc_18003FE0D
0x18003fc8d  call    ?zInternalStop@?$ActivityBase@VPrintSupportTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PrintSupportTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003fc92  call    ?Provider@PrintSupportTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PrintSupportTraceLoggingProvider::Provider(void)
0x18003fc97  mov     r9, rax
0x18003fc9a  mov     ecx, [rax]
0x18003fc9c  cmp     ecx, 5
0x18003fc9f  jbe     loc_18003FED6
0x18003fca5  mov     rdx, 400000000000h
0x18003fcaf  mov     rcx, rax
0x18003fcb2  call    _tlgKeywordOn
0x18003fcb7  test    al, al
0x18003fcb9  jz      loc_18003FED6
0x18003fcbf  mov     rax, [rdi+78h]
0x18003fcc3  lea     rdx, byte_18007416D
0x18003fcca  mov     [rbp+90h+var_E0], rax
0x18003fcce  mov     rcx, r9
0x18003fcd1  mov     rax, [rdi+70h]
0x18003fcd5  mov     [rbp+90h+var_D8], rax
0x18003fcd9  mov     eax, [rdi+68h]
0x18003fcdc  mov     r8, [rbx+110h]
0x18003fce3  mov     [rbp+90h+var_104], eax
0x18003fce6  add     r8, 8
0x18003fcea  mov     rax, [rdi+60h]
0x18003fcee  mov     [rbp+90h+var_D0], rax
0x18003fcf2  mov     rax, [rdi+58h]
0x18003fcf6  mov     [rbp+90h+var_C8], rax
0x18003fcfa  mov     eax, [rdi+50h]
0x18003fcfd  mov     [rbp+90h+var_100], eax
0x18003fd00  mov     rax, [rdi+48h]
0x18003fd04  mov     [rbp+90h+var_C0], rax
0x18003fd08  mov     eax, [rdi+20h]
0x18003fd0b  mov     [rbp+90h+var_FC], eax
0x18003fd0e  mov     rax, [rdi+18h]
0x18003fd12  mov     [rbp+90h+var_B8], rax
0x18003fd16  mov     eax, [rdi]
0x18003fd18  mov     [rbp+90h+var_F8], eax
0x18003fd1b  mov     rax, [rdi+80h]
0x18003fd22  mov     [rbp+90h+var_B0], rax
0x18003fd26  mov     eax, [rdi+40h]
0x18003fd29  mov     [rbp+90h+var_10C], eax
0x18003fd2c  mov     rax, [rdi+38h]
0x18003fd30  mov     [rbp+90h+var_A8], rax
0x18003fd34  mov     eax, [rdi+8]
0x18003fd37  mov     [rbp+90h+var_108], eax
0x18003fd3a  mov     eax, 1000000h
0x18003fd3f  mov     [rbp+90h+var_A0], rax
0x18003fd43  mov     [rbp+90h+var_F0], rax
0x18003fd47  lea     rax, [rbp+90h+var_110]
0x18003fd4b  mov     [rsp+1C0h+var_118], rax
0x18003fd53  lea     rax, [rbp+90h+var_E8]
0x18003fd57  mov     [rsp+1C0h+var_120], rax
0x18003fd5f  lea     rax, [rbp+90h+var_E0]
0x18003fd63  mov     [rsp+1C0h+var_128], rax
0x18003fd6b  lea     rax, [rbp+90h+var_D8]
0x18003fd6f  mov     [rsp+1C0h+var_130], rax
0x18003fd77  lea     rax, [rbp+90h+var_104]
0x18003fd7b  mov     [rsp+1C0h+var_138], rax
0x18003fd83  lea     rax, [rbp+90h+var_D0]
0x18003fd87  mov     [rsp+1C0h+var_140], rax
0x18003fd8f  lea     rax, [rbp+90h+var_C8]
0x18003fd93  mov     [rsp+1C0h+var_148], rax
0x18003fd98  lea     rax, [rbp+90h+var_100]
0x18003fd9c  mov     [rsp+1C0h+var_150], rax
0x18003fda1  lea     rax, [rbp+90h+var_C0]
0x18003fda5  mov     [rsp+1C0h+var_158], rax
0x18003fdaa  lea     rax, [rbp+90h+var_FC]
0x18003fdae  mov     [rsp+1C0h+var_160], rax
0x18003fdb3  lea     rax, [rbp+90h+var_B8]
0x18003fdb7  mov     [rsp+1C0h+var_168], rax
0x18003fdbc  lea     rax, [rbp+90h+var_F8]
0x18003fdc0  mov     [rsp+1C0h+var_170], rax
0x18003fdc5  lea     rax, [rbp+90h+var_B0]
0x18003fdc9  mov     [rsp+1C0h+var_178], rax
0x18003fdce  lea     rax, [rbp+90h+var_10C]
0x18003fdd2  mov     [rsp+1C0h+var_180], rax
0x18003fdd7  lea     rax, [rbp+90h+var_A8]
0x18003fddb  mov     [rsp+1C0h+var_188], rax
0x18003fde0  lea     rax, [rbp+90h+var_108]
0x18003fde4  mov     [rsp+1C0h+var_190], rax
0x18003fde9  lea     rax, [rbp+90h+var_A0]
0x18003fded  mov     [rsp+1C0h+var_198], rax
0x18003fdf2  lea     rax, [rbp+90h+var_F0]
0x18003fdf6  mov     [rsp+1C0h+var_1A0], rax
0x18003fdfb  mov     [rbp+90h+var_110], sil
0x18003fdff  mov     [rbp+90h+var_E8], r14
0x18003fe03  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x18003fe08  jmp     loc_18003FED6
0x18003fe0d  call    ?zInternalStop@?$ActivityBase@VPrintSupportTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PrintSupportTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003fe12  call    ?Provider@PrintSupportTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PrintSupportTraceLoggingProvider::Provider(void)
0x18003fe17  mov     rdi, rax
0x18003fe1a  mov     ecx, [rax]
0x18003fe1c  cmp     ecx, 5
0x18003fe1f  jbe     loc_18003FED6
0x18003fe25  mov     rdx, 400000000000h
0x18003fe2f  mov     rcx, rax
0x18003fe32  call    _tlgKeywordOn
0x18003fe37  test    al, al
0x18003fe39  jz      loc_18003FED6
0x18003fe3f  mov     [rbp+90h+var_110], sil
0x18003fe43  call    cs:__imp_GetCurrentThreadId
0x18003fe49  mov     r8, [rbx+110h]
0x18003fe50  lea     rdx, byte_1800742C3
0x18003fe57  mov     [rbp+90h+var_108], eax
0x18003fe5a  xor     r9d, r9d
0x18003fe5d  mov     rcx, rdi
0x18003fe60  mov     [rbp+90h+var_28], 1
0x18003fe68  mov     [rbp+90h+var_40], r14
0x18003fe6c  mov     eax, [r8+48h]
0x18003fe70  add     r8, 8
0x18003fe74  mov     [rbp+90h+var_10C], eax
0x18003fe77  mov     eax, 1000000h
0x18003fe7c  mov     [rbp+90h+var_F0], rax
0x18003fe80  lea     rax, [rbp+90h+var_110]
0x18003fe84  mov     [rbp+90h+var_30], rax
0x18003fe88  lea     rax, [rbp+90h+var_108]
0x18003fe8c  mov     [rbp+90h+var_50], rax
0x18003fe90  lea     rax, [rbp+90h+var_10C]
0x18003fe94  mov     [rbp+90h+var_60], rax
0x18003fe98  lea     rax, [rbp+90h+var_F0]
0x18003fe9c  mov     [rbp+90h+var_70], rax
0x18003fea0  lea     rax, [rbp+90h+var_90]
0x18003fea4  mov     [rsp+1C0h+var_198], rax
0x18003fea9  mov     dword ptr [rsp+1C0h+var_1A0], 7
0x18003feb1  mov     [rbp+90h+var_38], 10h
0x18003feb9  mov     [rbp+90h+var_48], 4
0x18003fec1  mov     [rbp+90h+var_58], 4
0x18003fec9  mov     [rbp+90h+var_68], 8
0x18003fed1  call    _tlgWriteTransfer_EventWriteTransfer
0x18003fed6  mov     rcx, rbx
0x18003fed9  call    ?IgnoreCurrentThread@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18003fede  mov     rcx, [rbp+90h+var_20]
0x18003fee2  xor     rcx, rsp; StackCookie
0x18003fee5  call    __security_check_cookie
0x18003feea  lea     r11, [rsp+1C0h+var_10]
0x18003fef2  mov     rbx, [r11+28h]
0x18003fef6  mov     rsi, [r11+30h]
0x18003fefa  mov     rsp, r11
0x18003fefd  pop     r14
0x18003feff  pop     rdi
0x18003ff00  pop     rbp
0x18003ff01  retn
```
