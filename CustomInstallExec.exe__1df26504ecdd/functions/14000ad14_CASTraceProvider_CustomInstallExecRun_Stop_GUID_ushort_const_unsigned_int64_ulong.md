# CASTraceProvider::CustomInstallExecRun::Stop(_GUID,ushort const *,unsigned __int64,ulong)

- ea: `0x14000ad14`
- end: `0x14000afcd`
- name: `?Stop@CustomInstallExecRun@CASTraceProvider@@QEAAXU_GUID@@PEBG_KK@Z`
- size: `697`
- prototype: `void __fastcall(CASTraceProvider::CustomInstallExecRun *this, struct _GUID *, const unsigned __int16 *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14000a8a8`

## callees

- `0x1400014b4`
- `0x140001c5c`
- `0x14000258c`
- `0x140009730`
- `0x14000a594`
- `0x14000ad14`
- `0x14000babc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000af43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000af43`

## pseudocode

```c
void __fastcall CASTraceProvider::CustomInstallExecRun::Stop(
        CASTraceProvider::CustomInstallExecRun *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v5; // rdi
  int v10; // eax
  int *v11; // rdi
  __int64 v12; // rcx
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // rcx
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v26; // [rsp+C4h] [rbp-7Ch] BYREF
  unsigned int v27; // [rsp+C8h] [rbp-78h] BYREF
  unsigned int v28; // [rsp+CCh] [rbp-74h] BYREF
  int v29; // [rsp+D0h] [rbp-70h] BYREF
  int v30; // [rsp+D4h] [rbp-6Ch] BYREF
  int v31; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v32; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v33; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v34; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v35; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v37; // [rsp+108h] [rbp-38h] BYREF
  struct _GUID *v38; // [rsp+110h] [rbp-30h] BYREF
  const unsigned __int16 *v39; // [rsp+118h] [rbp-28h] BYREF
  const unsigned __int16 *v40; // [rsp+120h] [rbp-20h] BYREF
  const unsigned __int16 *v41; // [rsp+128h] [rbp-18h] BYREF
  const unsigned __int16 *v42; // [rsp+130h] [rbp-10h] BYREF
  const unsigned __int16 *v43; // [rsp+138h] [rbp-8h] BYREF
  const unsigned __int16 *v44; // [rsp+140h] [rbp+0h] BYREF

  v5 = *((_QWORD *)this + 34);
  v10 = *(_DWORD *)(v5 + 72);
  if ( v10 < 0 && (v11 = (int *)(v5 + 80), v10 == v11[2]) && v11 )
  {
    wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v13 = CASTraceProvider::Provider(v12);
    if ( *(_DWORD *)v13 > 5u && (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL, v14, v13) )
    {
      v39 = (const unsigned __int16 *)*((_QWORD *)v11 + 15);
      v40 = (const unsigned __int16 *)*((_QWORD *)v11 + 14);
      v29 = v11[26];
      v41 = (const unsigned __int16 *)*((_QWORD *)v11 + 12);
      v16 = *((_QWORD *)this + 34);
      v42 = (const unsigned __int16 *)*((_QWORD *)v11 + 11);
      v30 = v11[20];
      v43 = (const unsigned __int16 *)*((_QWORD *)v11 + 9);
      v31 = v11[8];
      v44 = (const unsigned __int16 *)*((_QWORD *)v11 + 3);
      v25 = *v11;
      v32 = *((_QWORD *)v11 + 16);
      v26 = v11[16];
      v33 = (const unsigned __int16 *)*((_QWORD *)v11 + 7);
      v27 = v11[2];
      v34 = 0x1000000;
      v35 = 0x1000000;
      v28 = a5;
      v36 = a4;
      v37 = a3;
      v38 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)&byte_140011D87,
        v16 + 8,
        v15,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v27,
        &v33,
        (__int64)&v26,
        (const unsigned __int16 **)&v32,
        (__int64)&v25,
        &v44,
        (__int64)&v31,
        &v43,
        (__int64)&v30,
        &v42,
        &v41,
        (__int64)&v29,
        &v40,
        &v39,
        (__int64 *)&v38,
        &v37,
        (__int64)&v36,
        (__int64)&v28);
    }
  }
  else
  {
    wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v18 = CASTraceProvider::Provider(v17);
    v21 = (__int64)v18;
    if ( *(_DWORD *)v18 > 5u && (unsigned __int8)tlgKeywordOn(v18, 0x400000000000LL, v19, v20) )
    {
      v27 = a5;
      v35 = a4;
      v34 = (__int64)a3;
      v33 = (const unsigned __int16 *)a2;
      CurrentThreadId = GetCurrentThreadId();
      v23 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v25 = *(_DWORD *)(v23 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v21,
        (__int64)byte_140011EF3,
        v23 + 8,
        v24,
        (__int64)&v32,
        (__int64)&v25,
        (__int64)&v26,
        (__int64 *)&v33,
        (const unsigned __int16 **)&v34,
        (__int64)&v35,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000ad14  push    rbp
0x14000ad16  push    rbx
0x14000ad17  push    rsi
0x14000ad18  push    rdi
0x14000ad19  push    r14
0x14000ad1b  push    r15
0x14000ad1d  lea     rbp, [rsp-18h]
0x14000ad22  sub     rsp, 158h
0x14000ad29  mov     rdi, [rcx+110h]
0x14000ad30  mov     rsi, r9
0x14000ad33  mov     r14, r8
0x14000ad36  mov     r15, rdx
0x14000ad39  mov     rbx, rcx
0x14000ad3c  mov     eax, [rdi+48h]
0x14000ad3f  test    eax, eax
0x14000ad41  jns     loc_14000AEFF
0x14000ad47  add     rdi, 50h ; 'P'
0x14000ad4b  cmp     eax, [rdi+8]
0x14000ad4e  jnz     loc_14000AEFF
0x14000ad54  test    rdi, rdi
0x14000ad57  jz      loc_14000AEFF
0x14000ad5d  call    ?zInternalStop@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000ad62  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000ad67  mov     r9, rax
0x14000ad6a  mov     ecx, [rax]
0x14000ad6c  cmp     ecx, 5
0x14000ad6f  jbe     loc_14000AFB5
0x14000ad75  mov     rdx, 400000000000h
0x14000ad7f  mov     rcx, rax
0x14000ad82  call    _tlgKeywordOn
0x14000ad87  test    al, al
0x14000ad89  jz      loc_14000AFB5
0x14000ad8f  mov     rax, [rdi+78h]
0x14000ad93  lea     rdx, byte_140011D87
0x14000ad9a  mov     [rbp+40h+var_68], rax
0x14000ad9e  mov     rax, [rdi+70h]
0x14000ada2  mov     [rbp+40h+var_60], rax
0x14000ada6  mov     eax, [rdi+68h]
0x14000ada9  mov     [rbp+40h+var_B0], eax
0x14000adac  mov     rax, [rdi+60h]
0x14000adb0  mov     [rbp+40h+var_58], rax
0x14000adb4  mov     rax, [rdi+58h]
0x14000adb8  mov     ecx, [rbp+40h+arg_20]
0x14000adbb  mov     r8, [rbx+110h]
0x14000adc2  mov     [rbp+40h+var_50], rax
0x14000adc6  add     r8, 8
0x14000adca  mov     eax, [rdi+50h]
0x14000adcd  mov     [rbp+40h+var_AC], eax
0x14000add0  mov     rax, [rdi+48h]
0x14000add4  mov     [rbp+40h+var_48], rax
0x14000add8  mov     eax, [rdi+20h]
0x14000addb  mov     [rbp+40h+var_A8], eax
0x14000adde  mov     rax, [rdi+18h]
0x14000ade2  mov     [rbp+40h+var_40], rax
0x14000ade6  mov     eax, [rdi]
0x14000ade8  mov     [rbp+40h+var_C0], eax
0x14000adeb  mov     rax, [rdi+80h]
0x14000adf2  mov     [rbp+40h+var_A0], rax
0x14000adf6  mov     eax, [rdi+40h]
0x14000adf9  mov     [rbp+40h+var_BC], eax
0x14000adfc  mov     rax, [rdi+38h]
0x14000ae00  mov     [rbp+40h+var_98], rax
0x14000ae04  mov     eax, [rdi+8]
0x14000ae07  mov     [rbp+40h+var_B8], eax
0x14000ae0a  mov     eax, 1000000h
0x14000ae0f  mov     [rbp+40h+var_90], rax
0x14000ae13  mov     [rbp+40h+var_88], rax
0x14000ae17  lea     rax, [rbp+40h+var_B4]
0x14000ae1b  mov     [rsp+180h+var_C8], rax
0x14000ae23  lea     rax, [rbp+40h+var_80]
0x14000ae27  mov     [rsp+180h+var_D0], rax
0x14000ae2f  lea     rax, [rbp+40h+var_78]
0x14000ae33  mov     [rsp+180h+var_D8], rax
0x14000ae3b  lea     rax, [rbp+40h+var_70]
0x14000ae3f  mov     [rsp+180h+var_E0], rax
0x14000ae47  lea     rax, [rbp+40h+var_68]
0x14000ae4b  mov     [rsp+180h+var_E8], rax
0x14000ae53  lea     rax, [rbp+40h+var_60]
0x14000ae57  mov     [rsp+180h+var_F0], rax
0x14000ae5f  lea     rax, [rbp+40h+var_B0]
0x14000ae63  mov     [rsp+180h+var_F8], rax
0x14000ae6b  lea     rax, [rbp+40h+var_58]
0x14000ae6f  mov     [rsp+180h+var_100], rax
0x14000ae77  lea     rax, [rbp+40h+var_50]
0x14000ae7b  mov     [rsp+180h+var_108], rax
0x14000ae80  lea     rax, [rbp+40h+var_AC]
0x14000ae84  mov     [rsp+180h+var_110], rax
0x14000ae89  lea     rax, [rbp+40h+var_48]
0x14000ae8d  mov     [rsp+180h+var_118], rax
0x14000ae92  lea     rax, [rbp+40h+var_A8]
0x14000ae96  mov     [rsp+180h+var_120], rax
0x14000ae9b  lea     rax, [rbp+40h+var_40]
0x14000ae9f  mov     [rsp+180h+var_128], rax
0x14000aea4  lea     rax, [rbp+40h+var_C0]
0x14000aea8  mov     [rsp+180h+var_130], rax
0x14000aead  lea     rax, [rbp+40h+var_A0]
0x14000aeb1  mov     [rsp+180h+var_138], rax
0x14000aeb6  lea     rax, [rbp+40h+var_BC]
0x14000aeba  mov     [rsp+180h+var_140], rax
0x14000aebf  lea     rax, [rbp+40h+var_98]
0x14000aec3  mov     [rsp+180h+var_148], rax
0x14000aec8  lea     rax, [rbp+40h+var_B8]
0x14000aecc  mov     [rsp+180h+var_150], rax
0x14000aed1  lea     rax, [rbp+40h+var_90]
0x14000aed5  mov     [rsp+180h+var_158], rax
0x14000aeda  lea     rax, [rbp+40h+var_88]
0x14000aede  mov     [rbp+40h+var_B4], ecx
0x14000aee1  mov     rcx, r9
0x14000aee4  mov     [rsp+180h+var_160], rax
0x14000aee9  mov     [rbp+40h+var_80], rsi
0x14000aeed  mov     [rbp+40h+var_78], r14
0x14000aef1  mov     [rbp+40h+var_70], r15
0x14000aef5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByRef@$0BA@@@U4@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByRef@$0BA@@@634@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14000aefa  jmp     loc_14000AFB5
0x14000aeff  call    ?zInternalStop@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000af04  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000af09  mov     rdi, rax
0x14000af0c  mov     ecx, [rax]
0x14000af0e  cmp     ecx, 5
0x14000af11  jbe     loc_14000AFB5
0x14000af17  mov     rdx, 400000000000h
0x14000af21  mov     rcx, rax
0x14000af24  call    _tlgKeywordOn
0x14000af29  test    al, al
0x14000af2b  jz      loc_14000AFB5
0x14000af31  mov     ecx, [rbp+40h+arg_20]
0x14000af34  mov     [rbp+40h+var_B8], ecx
0x14000af37  mov     [rbp+40h+var_88], rsi
0x14000af3b  mov     [rbp+40h+var_90], r14
0x14000af3f  mov     [rbp+40h+var_98], r15
0x14000af43  call    cs:__imp_GetCurrentThreadId
0x14000af49  mov     r8, [rbx+110h]
0x14000af50  lea     rdx, byte_140011EF3
0x14000af57  mov     [rbp+40h+var_BC], eax
0x14000af5a  mov     rcx, rdi
0x14000af5d  mov     eax, [r8+48h]
0x14000af61  add     r8, 8
0x14000af65  mov     [rbp+40h+var_C0], eax
0x14000af68  mov     eax, 1000000h
0x14000af6d  mov     [rbp+40h+var_A0], rax
0x14000af71  lea     rax, [rbp+40h+var_B8]
0x14000af75  mov     [rsp+180h+var_130], rax
0x14000af7a  lea     rax, [rbp+40h+var_88]
0x14000af7e  mov     [rsp+180h+var_138], rax
0x14000af83  lea     rax, [rbp+40h+var_90]
0x14000af87  mov     [rsp+180h+var_140], rax
0x14000af8c  lea     rax, [rbp+40h+var_98]
0x14000af90  mov     [rsp+180h+var_148], rax
0x14000af95  lea     rax, [rbp+40h+var_BC]
0x14000af99  mov     [rsp+180h+var_150], rax
0x14000af9e  lea     rax, [rbp+40h+var_C0]
0x14000afa2  mov     [rsp+180h+var_158], rax
0x14000afa7  lea     rax, [rbp+40h+var_A0]
0x14000afab  mov     [rsp+180h+var_160], rax
0x14000afb0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14000afb5  mov     rcx, rbx
0x14000afb8  call    ?IgnoreCurrentThread@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x14000afbd  add     rsp, 158h
0x14000afc4  pop     r15
0x14000afc6  pop     r14
0x14000afc8  pop     rdi
0x14000afc9  pop     rsi
0x14000afca  pop     rbx
0x14000afcb  pop     rbp
0x14000afcc  retn
```
