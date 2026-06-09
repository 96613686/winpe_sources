# LogProvider::ClientAuthAddKeyRefCount::Stop(uchar,unsigned __int64)

- ea: `0x140041f08`
- end: `0x140042189`
- name: `?Stop@ClientAuthAddKeyRefCount@LogProvider@@QEAAXE_K@Z`
- size: `641`
- prototype: `void __fastcall(LogProvider::ClientAuthAddKeyRefCount *__hidden this, unsigned __int8, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140040cb8`

## callees

- `0x14000131c`
- `0x140003634`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x140041f08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004210b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004210b`

## pseudocode

```c
void __fastcall LogProvider::ClientAuthAddKeyRefCount::Stop(
        LogProvider::ClientAuthAddKeyRefCount *this,
        char a2,
        __int64 a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  int v15; // edi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  int v18; // r9d
  int v19; // [rsp+D0h] [rbp-80h] BYREF
  int v20; // [rsp+D4h] [rbp-7Ch] BYREF
  int v21; // [rsp+D8h] [rbp-78h] BYREF
  int v22; // [rsp+DCh] [rbp-74h] BYREF
  int v23; // [rsp+E0h] [rbp-70h] BYREF
  int v24; // [rsp+E4h] [rbp-6Ch] BYREF
  int v25; // [rsp+E8h] [rbp-68h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+100h] [rbp-50h] BYREF
  __int64 v29; // [rsp+108h] [rbp-48h] BYREF
  __int64 v30; // [rsp+110h] [rbp-40h] BYREF
  __int64 v31; // [rsp+118h] [rbp-38h] BYREF
  __int64 v32; // [rsp+120h] [rbp-30h] BYREF
  __int64 v33; // [rsp+128h] [rbp-28h] BYREF
  __int64 v34; // [rsp+130h] [rbp-20h] BYREF
  __int64 v35; // [rsp+138h] [rbp-18h] BYREF
  __int64 v36; // [rsp+140h] [rbp-10h] BYREF
  __int64 v37; // [rsp+148h] [rbp-8h] BYREF
  char v38; // [rsp+170h] [rbp+20h] BYREF
  DWORD v39; // [rsp+188h] [rbp+38h] BYREF

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LogProvider::Provider();
    if ( *(_DWORD *)v11 > 4u )
    {
      v30 = *((_QWORD *)v8 + 15);
      v31 = *((_QWORD *)v8 + 14);
      v21 = v8[26];
      v12 = *((_QWORD *)v8 + 6);
      v32 = *((_QWORD *)v8 + 12);
      v13 = *((_QWORD *)this + 34);
      v33 = *((_QWORD *)v8 + 11);
      v22 = v8[20];
      v34 = *((_QWORD *)v8 + 9);
      v23 = v8[8];
      v35 = *((_QWORD *)v8 + 3);
      v24 = *v8;
      v36 = *((_QWORD *)v8 + 16);
      v25 = v8[16];
      v37 = *((_QWORD *)v8 + 7);
      v19 = v8[2];
      v29 = v12;
      v39 = v8[17];
      LODWORD(v12) = v8[4];
      v28 = a3;
      v38 = a2;
      v20 = v12;
      v26 = 0x1000000;
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        (_DWORD)v11,
        (unsigned int)byte_14008D20B,
        v13 + 8,
        (_DWORD)v11,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v19,
        (__int64)&v37,
        (__int64)&v25,
        (__int64)&v36,
        (__int64)&v24,
        (__int64)&v35,
        (__int64)&v23,
        (__int64)&v34,
        (__int64)&v22,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v20,
        (__int64)&v39,
        (__int64)&v29,
        (__int64)&v38,
        (__int64)&v28);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = LogProvider::Provider();
    v15 = (int)v14;
    if ( *(_DWORD *)v14 > 4u )
    {
      v27 = a3;
      v38 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v39 = CurrentThreadId;
      v19 = *(_DWORD *)(v17 + 72);
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        v15,
        (unsigned int)&unk_14008D370,
        v17 + 8,
        v18,
        (__int64)&v26,
        (__int64)&v19,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v27);
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
0x140041f08  mov     [rsp-18h+arg_8], rbx
0x140041f0d  mov     [rsp-18h+arg_10], rsi
0x140041f12  push    rbp
0x140041f13  push    rdi
0x140041f14  push    r14
0x140041f16  mov     rbp, rsp
0x140041f19  sub     rsp, 150h
0x140041f20  mov     rdi, [rcx+110h]
0x140041f27  mov     rsi, r8
0x140041f2a  mov     r14b, dl
0x140041f2d  mov     rbx, rcx
0x140041f30  mov     eax, [rdi+48h]
0x140041f33  test    eax, eax
0x140041f35  jns     loc_1400420EF
0x140041f3b  add     rdi, 50h ; 'P'
0x140041f3f  cmp     eax, [rdi+8]
0x140041f42  jnz     loc_1400420EF
0x140041f48  test    rdi, rdi
0x140041f4b  jz      loc_1400420EF
0x140041f51  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140041f56  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140041f5b  mov     r9, rax
0x140041f5e  mov     ecx, [rax]
0x140041f60  cmp     ecx, 4
0x140041f63  jbe     loc_14004216A
0x140041f69  mov     rax, [rdi+78h]
0x140041f6d  mov     [rbp+var_40], rax
0x140041f71  mov     rax, [rdi+70h]
0x140041f75  mov     [rbp+var_38], rax
0x140041f79  mov     eax, [rdi+68h]
0x140041f7c  mov     [rbp+var_78], eax
0x140041f7f  mov     rax, [rdi+60h]
0x140041f83  mov     rcx, [rdi+30h]
0x140041f87  mov     [rbp+var_30], rax
0x140041f8b  mov     rax, [rdi+58h]
0x140041f8f  mov     r8, [rbx+110h]
0x140041f96  mov     [rbp+var_28], rax
0x140041f9a  add     r8, 8
0x140041f9e  mov     eax, [rdi+50h]
0x140041fa1  mov     [rbp+var_74], eax
0x140041fa4  mov     rax, [rdi+48h]
0x140041fa8  mov     [rbp+var_20], rax
0x140041fac  mov     eax, [rdi+20h]
0x140041faf  mov     [rbp+var_70], eax
0x140041fb2  mov     rax, [rdi+18h]
0x140041fb6  mov     [rbp+var_18], rax
0x140041fba  mov     eax, [rdi]
0x140041fbc  mov     [rbp+var_6C], eax
0x140041fbf  mov     rax, [rdi+80h]
0x140041fc6  mov     [rbp+var_10], rax
0x140041fca  mov     eax, [rdi+40h]
0x140041fcd  mov     [rbp+var_68], eax
0x140041fd0  mov     rax, [rdi+38h]
0x140041fd4  mov     [rbp+var_8], rax
0x140041fd8  mov     eax, [rdi+8]
0x140041fdb  mov     [rbp+var_80], eax
0x140041fde  lea     rax, [rbp+var_50]
0x140041fe2  mov     [rsp+150h+var_90], rax
0x140041fea  lea     rax, [rbp+arg_0]
0x140041fee  mov     [rsp+150h+var_98], rax
0x140041ff6  lea     rax, [rbp+var_48]
0x140041ffa  mov     [rsp+150h+var_A0], rax
0x140042002  lea     rax, [rbp+arg_18]
0x140042006  mov     [rsp+150h+var_A8], rax
0x14004200e  lea     rax, [rbp+var_7C]
0x140042012  mov     [rsp+150h+var_B0], rax
0x14004201a  lea     rax, [rbp+var_40]
0x14004201e  mov     [rsp+150h+var_B8], rax
0x140042026  lea     rax, [rbp+var_38]
0x14004202a  mov     [rsp+150h+var_C0], rax
0x140042032  lea     rax, [rbp+var_78]
0x140042036  mov     [rsp+150h+var_C8], rax
0x14004203e  lea     rax, [rbp+var_30]
0x140042042  mov     [rsp+150h+var_D0], rax
0x14004204a  lea     rax, [rbp+var_28]
0x14004204e  mov     [rsp+150h+var_D8], rax
0x140042053  lea     rax, [rbp+var_74]
0x140042057  mov     [rsp+150h+var_E0], rax
0x14004205c  lea     rax, [rbp+var_20]
0x140042060  mov     [rsp+150h+var_E8], rax
0x140042065  lea     rax, [rbp+var_70]
0x140042069  mov     [rsp+150h+var_F0], rax
0x14004206e  lea     rax, [rbp+var_18]
0x140042072  mov     [rsp+150h+var_F8], rax
0x140042077  lea     rax, [rbp+var_6C]
0x14004207b  mov     [rsp+150h+var_100], rax
0x140042080  lea     rax, [rbp+var_10]
0x140042084  mov     [rsp+150h+var_108], rax
0x140042089  lea     rax, [rbp+var_68]
0x14004208d  mov     [rsp+150h+var_110], rax
0x140042092  lea     rax, [rbp+var_8]
0x140042096  mov     [rsp+150h+var_118], rax
0x14004209b  lea     rax, [rbp+var_80]
0x14004209f  mov     [rsp+150h+var_120], rax
0x1400420a4  lea     rax, [rbp+var_60]
0x1400420a8  mov     [rbp+var_48], rcx
0x1400420ac  mov     ecx, [rdi+44h]
0x1400420af  mov     [rbp+arg_18], ecx
0x1400420b2  mov     ecx, [rdi+10h]
0x1400420b5  mov     [rsp+150h+var_128], rax
0x1400420ba  lea     rax, [rbp+var_58]
0x1400420be  mov     [rbp+var_50], rsi
0x1400420c2  mov     [rbp+arg_0], r14b
0x1400420c6  mov     [rbp+var_7C], ecx
0x1400420c9  mov     [rbp+var_60], 1000000h
0x1400420d1  mov     [rbp+var_58], 0
0x1400420d9  lea     rdx, byte_14008D20B
0x1400420e0  mov     [rsp+150h+var_130], rax
0x1400420e5  mov     rcx, r9
0x1400420e8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x1400420ed  jmp     short loc_14004216A
0x1400420ef  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400420f4  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1400420f9  mov     rdi, rax
0x1400420fc  mov     ecx, [rax]
0x1400420fe  cmp     ecx, 4
0x140042101  jbe     short loc_14004216A
0x140042103  mov     [rbp+var_58], rsi
0x140042107  mov     [rbp+arg_0], r14b
0x14004210b  call    cs:__imp_GetCurrentThreadId
0x140042111  mov     r8, [rbx+110h]
0x140042118  lea     rdx, unk_14008D370
0x14004211f  mov     [rbp+arg_18], eax
0x140042122  lea     rax, [rbp+var_58]
0x140042126  mov     [rsp+150h+var_110], rax
0x14004212b  lea     rax, [rbp+arg_0]
0x14004212f  mov     [rsp+150h+var_118], rax
0x140042134  lea     rax, [rbp+arg_18]
0x140042138  mov     ecx, [r8+48h]
0x14004213c  add     r8, 8
0x140042140  mov     [rsp+150h+var_120], rax
0x140042145  lea     rax, [rbp+var_80]
0x140042149  mov     [rsp+150h+var_128], rax
0x14004214e  lea     rax, [rbp+var_60]
0x140042152  mov     [rbp+var_80], ecx
0x140042155  mov     rcx, rdi
0x140042158  mov     [rsp+150h+var_130], rax
0x14004215d  mov     [rbp+var_60], 0
0x140042165  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x14004216a  mov     rcx, rbx
0x14004216d  lea     r11, [rsp+150h+var_s0]
0x140042175  mov     rbx, [r11+28h]
0x140042179  mov     rsi, [r11+30h]
0x14004217d  mov     rsp, r11
0x140042180  pop     r14
0x140042182  pop     rdi
0x140042183  pop     rbp
0x140042184  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
