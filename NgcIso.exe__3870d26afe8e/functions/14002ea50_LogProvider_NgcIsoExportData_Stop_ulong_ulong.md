# LogProvider::NgcIsoExportData::Stop(ulong,ulong)

- ea: `0x14002ea50`
- end: `0x14002ed2a`
- name: `?Stop@NgcIsoExportData@LogProvider@@QEAAXKK@Z`
- size: `730`
- prototype: `void __fastcall(LogProvider::NgcIsoExportData *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140025e40`

## callees

- `0x14000165c`
- `0x1400027f0`
- `0x14000c558`
- `0x14000f6a0`
- `0x14001648c`
- `0x1400174e8`
- `0x14002ea50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002ec68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002ec68`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoExportData::Stop(LogProvider::NgcIsoExportData *this, int a2, int a3)
{
  __int64 v3; // rdi
  int v7; // eax
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  int v17; // ecx
  int v18; // [rsp+D0h] [rbp-80h] BYREF
  DWORD v19; // [rsp+D4h] [rbp-7Ch] BYREF
  int v20; // [rsp+D8h] [rbp-78h] BYREF
  int v21; // [rsp+DCh] [rbp-74h] BYREF
  int v22; // [rsp+E0h] [rbp-70h] BYREF
  int v23; // [rsp+E4h] [rbp-6Ch] BYREF
  int v24; // [rsp+E8h] [rbp-68h] BYREF
  int v25; // [rsp+ECh] [rbp-64h] BYREF
  int v26; // [rsp+F0h] [rbp-60h] BYREF
  int v27; // [rsp+F4h] [rbp-5Ch] BYREF
  __int64 v28; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v29; // [rsp+100h] [rbp-50h] BYREF
  __int64 v30; // [rsp+108h] [rbp-48h] BYREF
  __int64 v31; // [rsp+110h] [rbp-40h] BYREF
  __int64 v32; // [rsp+118h] [rbp-38h] BYREF
  __int64 v33; // [rsp+120h] [rbp-30h] BYREF
  __int64 v34; // [rsp+128h] [rbp-28h] BYREF
  __int64 v35; // [rsp+130h] [rbp-20h] BYREF
  __int64 v36; // [rsp+138h] [rbp-18h] BYREF
  __int64 v37; // [rsp+140h] [rbp-10h] BYREF
  __int64 v38; // [rsp+148h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+150h] [rbp+0h] BYREF
  __int64 *v40; // [rsp+170h] [rbp+20h]
  __int64 v41; // [rsp+178h] [rbp+28h]
  int *v42; // [rsp+180h] [rbp+30h]
  __int64 v43; // [rsp+188h] [rbp+38h]
  DWORD *v44; // [rsp+190h] [rbp+40h]
  __int64 v45; // [rsp+198h] [rbp+48h]
  int *v46; // [rsp+1A0h] [rbp+50h]
  __int64 v47; // [rsp+1A8h] [rbp+58h]
  int *v48; // [rsp+1B0h] [rbp+60h]
  __int64 v49; // [rsp+1B8h] [rbp+68h]

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = v3 + 80, v7 == *(_DWORD *)(v8 + 8)) && v8 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LogProvider::Provider();
    if ( *(_DWORD *)v11 > 5u )
    {
      v30 = *(_QWORD *)(v8 + 120);
      v31 = *(_QWORD *)(v8 + 112);
      v26 = *(_DWORD *)(v8 + 104);
      v12 = *(_QWORD *)(v8 + 48);
      v32 = *(_QWORD *)(v8 + 96);
      v13 = *((_QWORD *)this + 34);
      v33 = *(_QWORD *)(v8 + 88);
      v27 = *(_DWORD *)(v8 + 80);
      v34 = *(_QWORD *)(v8 + 72);
      v18 = *(_DWORD *)(v8 + 32);
      v35 = *(_QWORD *)(v8 + 24);
      v19 = *(_DWORD *)v8;
      v36 = *(_QWORD *)(v8 + 128);
      v20 = *(_DWORD *)(v8 + 64);
      v37 = *(_QWORD *)(v8 + 56);
      v21 = *(_DWORD *)(v8 + 8);
      v29 = v12;
      v24 = *(_DWORD *)(v8 + 68);
      LODWORD(v12) = *(_DWORD *)(v8 + 16);
      v22 = a3;
      v23 = a2;
      v25 = v12;
      v38 = 0x1000000;
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v11,
        (unsigned int)&unk_14008A668,
        v13 + 8,
        (_DWORD)v11,
        (__int64)&v28,
        (__int64)&v38,
        (__int64)&v21,
        (__int64)&v37,
        (__int64)&v20,
        (__int64)&v36,
        (__int64)&v19,
        (__int64)&v35,
        (__int64)&v18,
        (__int64)&v34,
        (__int64)&v27,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v26,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v29,
        (__int64)&v23,
        (__int64)&v22);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = LogProvider::Provider();
    if ( *(_DWORD *)v14 > 5u )
    {
      v21 = a3;
      v20 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v19 = CurrentThreadId;
      v49 = 4;
      v48 = &v21;
      v17 = *(_DWORD *)(v16 + 72);
      v46 = &v20;
      v44 = &v19;
      v42 = &v18;
      v40 = &v28;
      v18 = v17;
      v28 = 0;
      v47 = 4;
      v45 = 4;
      v43 = 4;
      v41 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v14,
        (unsigned __int8 *)word_14008A7DA,
        (const GUID *)(v16 + 8),
        0,
        7u,
        &v39);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v9,
    v10,
    v11);
}

```

## disassembly

```asm
0x14002ea50  mov     [rsp-8+arg_8], rbx
0x14002ea55  mov     [rsp-8+arg_10], rsi
0x14002ea5a  push    rbp
0x14002ea5b  push    rdi
0x14002ea5c  push    r14
0x14002ea5e  lea     rbp, [rsp-80h]
0x14002ea63  sub     rsp, 1D0h
0x14002ea6a  mov     rax, cs:__security_cookie
0x14002ea71  xor     rax, rsp
0x14002ea74  mov     [rbp+90h+var_20], rax
0x14002ea78  mov     rdi, [rcx+110h]
0x14002ea7f  mov     esi, r8d
0x14002ea82  mov     r14d, edx
0x14002ea85  mov     rbx, rcx
0x14002ea88  mov     eax, [rdi+48h]
0x14002ea8b  test    eax, eax
0x14002ea8d  jns     loc_14002EC49
0x14002ea93  add     rdi, 50h ; 'P'
0x14002ea97  cmp     eax, [rdi+8]
0x14002ea9a  jnz     loc_14002EC49
0x14002eaa0  test    rdi, rdi
0x14002eaa3  jz      loc_14002EC49
0x14002eaa9  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002eaae  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002eab3  mov     r9, rax
0x14002eab6  mov     ecx, [rax]
0x14002eab8  cmp     ecx, 5
0x14002eabb  jbe     loc_14002ECFE
0x14002eac1  mov     rax, [rdi+78h]
0x14002eac5  mov     [rbp+90h+var_D8], rax
0x14002eac9  mov     rax, [rdi+70h]
0x14002eacd  mov     [rbp+90h+var_D0], rax
0x14002ead1  mov     eax, [rdi+68h]
0x14002ead4  mov     [rbp+90h+var_F0], eax
0x14002ead7  mov     rax, [rdi+60h]
0x14002eadb  mov     rcx, [rdi+30h]
0x14002eadf  mov     [rbp+90h+var_C8], rax
0x14002eae3  mov     rax, [rdi+58h]
0x14002eae7  mov     r8, [rbx+110h]
0x14002eaee  mov     [rbp+90h+var_C0], rax
0x14002eaf2  add     r8, 8
0x14002eaf6  mov     eax, [rdi+50h]
0x14002eaf9  mov     [rbp+90h+var_EC], eax
0x14002eafc  mov     rax, [rdi+48h]
0x14002eb00  mov     [rbp+90h+var_B8], rax
0x14002eb04  mov     eax, [rdi+20h]
0x14002eb07  mov     [rbp+90h+var_110], eax
0x14002eb0a  mov     rax, [rdi+18h]
0x14002eb0e  mov     [rbp+90h+var_B0], rax
0x14002eb12  mov     eax, [rdi]
0x14002eb14  mov     [rbp+90h+var_10C], eax
0x14002eb17  mov     rax, [rdi+80h]
0x14002eb1e  mov     [rbp+90h+var_A8], rax
0x14002eb22  mov     eax, [rdi+40h]
0x14002eb25  mov     [rbp+90h+var_108], eax
0x14002eb28  mov     rax, [rdi+38h]
0x14002eb2c  mov     [rbp+90h+var_A0], rax
0x14002eb30  mov     eax, [rdi+8]
0x14002eb33  mov     [rbp+90h+var_104], eax
0x14002eb36  lea     rax, [rbp+90h+var_100]
0x14002eb3a  mov     [rsp+1E0h+var_120], rax
0x14002eb42  lea     rax, [rbp+90h+var_FC]
0x14002eb46  mov     [rsp+1E0h+var_128], rax
0x14002eb4e  lea     rax, [rbp+90h+var_E0]
0x14002eb52  mov     [rsp+1E0h+var_130], rax
0x14002eb5a  lea     rax, [rbp+90h+var_F8]
0x14002eb5e  mov     [rsp+1E0h+var_138], rax
0x14002eb66  lea     rax, [rbp+90h+var_F4]
0x14002eb6a  mov     [rsp+1E0h+var_140], rax
0x14002eb72  lea     rax, [rbp+90h+var_D8]
0x14002eb76  mov     [rsp+1E0h+var_148], rax
0x14002eb7e  lea     rax, [rbp+90h+var_D0]
0x14002eb82  mov     [rsp+1E0h+var_150], rax
0x14002eb8a  lea     rax, [rbp+90h+var_F0]
0x14002eb8e  mov     [rsp+1E0h+var_158], rax
0x14002eb96  lea     rax, [rbp+90h+var_C8]
0x14002eb9a  mov     [rsp+1E0h+var_160], rax
0x14002eba2  lea     rax, [rbp+90h+var_C0]
0x14002eba6  mov     [rsp+1E0h+var_168], rax
0x14002ebab  lea     rax, [rbp+90h+var_EC]
0x14002ebaf  mov     [rsp+1E0h+var_170], rax
0x14002ebb4  lea     rax, [rbp+90h+var_B8]
0x14002ebb8  mov     [rsp+1E0h+var_178], rax
0x14002ebbd  lea     rax, [rbp+90h+var_110]
0x14002ebc1  mov     [rsp+1E0h+var_180], rax
0x14002ebc6  lea     rax, [rbp+90h+var_B0]
0x14002ebca  mov     [rsp+1E0h+var_188], rax
0x14002ebcf  lea     rax, [rbp+90h+var_10C]
0x14002ebd3  mov     [rsp+1E0h+var_190], rax
0x14002ebd8  lea     rax, [rbp+90h+var_A8]
0x14002ebdc  mov     [rsp+1E0h+var_198], rax
0x14002ebe1  lea     rax, [rbp+90h+var_108]
0x14002ebe5  mov     [rsp+1E0h+var_1A0], rax
0x14002ebea  lea     rax, [rbp+90h+var_A0]
0x14002ebee  mov     [rsp+1E0h+var_1A8], rax
0x14002ebf3  lea     rax, [rbp+90h+var_104]
0x14002ebf7  mov     [rsp+1E0h+var_1B0], rax
0x14002ebfc  lea     rax, [rbp+90h+var_98]
0x14002ec00  mov     [rbp+90h+var_E0], rcx
0x14002ec04  mov     ecx, [rdi+44h]
0x14002ec07  mov     [rbp+90h+var_F8], ecx
0x14002ec0a  mov     ecx, [rdi+10h]
0x14002ec0d  mov     [rsp+1E0h+var_1B8], rax
0x14002ec12  lea     rax, [rbp+90h+var_E8]
0x14002ec16  mov     [rbp+90h+var_100], esi
0x14002ec19  mov     [rbp+90h+var_FC], r14d
0x14002ec1d  mov     [rbp+90h+var_F4], ecx
0x14002ec20  mov     [rbp+90h+var_98], 1000000h
0x14002ec28  mov     [rbp+90h+var_E8], 0
0x14002ec30  lea     rdx, unk_14008A668
0x14002ec37  mov     [rsp+1E0h+var_1C0], rax
0x14002ec3c  mov     rcx, r9
0x14002ec3f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002ec44  jmp     loc_14002ECFE
0x14002ec49  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002ec4e  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002ec53  mov     rdi, rax
0x14002ec56  mov     ecx, [rax]
0x14002ec58  cmp     ecx, 5
0x14002ec5b  jbe     loc_14002ECFE
0x14002ec61  mov     [rbp+90h+var_104], esi
0x14002ec64  mov     [rbp+90h+var_108], r14d
0x14002ec68  call    cs:__imp_GetCurrentThreadId
0x14002ec6e  mov     r8, [rbx+110h]
0x14002ec75  lea     rdx, word_14008A7DA
0x14002ec7c  mov     [rbp+90h+var_10C], eax
0x14002ec7f  xor     r9d, r9d
0x14002ec82  lea     rax, [rbp+90h+var_104]
0x14002ec86  mov     [rbp+90h+var_28], 4
0x14002ec8e  mov     [rbp+90h+var_30], rax
0x14002ec92  lea     rax, [rbp+90h+var_108]
0x14002ec96  mov     ecx, [r8+48h]
0x14002ec9a  add     r8, 8
0x14002ec9e  mov     [rbp+90h+var_40], rax
0x14002eca2  lea     rax, [rbp+90h+var_10C]
0x14002eca6  mov     [rbp+90h+var_50], rax
0x14002ecaa  lea     rax, [rbp+90h+var_110]
0x14002ecae  mov     [rbp+90h+var_60], rax
0x14002ecb2  lea     rax, [rbp+90h+var_E8]
0x14002ecb6  mov     [rbp+90h+var_70], rax
0x14002ecba  lea     rax, [rbp+90h+var_90]
0x14002ecbe  mov     [rbp+90h+var_110], ecx
0x14002ecc1  mov     rcx, rdi
0x14002ecc4  mov     [rsp+1E0h+var_1B8], rax
0x14002ecc9  mov     dword ptr [rsp+1E0h+var_1C0], 7
0x14002ecd1  mov     [rbp+90h+var_E8], 0
0x14002ecd9  mov     [rbp+90h+var_38], 4
0x14002ece1  mov     [rbp+90h+var_48], 4
0x14002ece9  mov     [rbp+90h+var_58], 4
0x14002ecf1  mov     [rbp+90h+var_68], 8
0x14002ecf9  call    _tlgWriteTransfer_EventWriteTransfer
0x14002ecfe  mov     rcx, rbx
0x14002ed01  call    ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x14002ed06  mov     rcx, [rbp+90h+var_20]
0x14002ed0a  xor     rcx, rsp; StackCookie
0x14002ed0d  call    __security_check_cookie
0x14002ed12  lea     r11, [rsp+1E0h+var_10]
0x14002ed1a  mov     rbx, [r11+28h]
0x14002ed1e  mov     rsi, [r11+30h]
0x14002ed22  mov     rsp, r11
0x14002ed25  pop     r14
0x14002ed27  pop     rdi
0x14002ed28  pop     rbp
0x14002ed29  retn
```
