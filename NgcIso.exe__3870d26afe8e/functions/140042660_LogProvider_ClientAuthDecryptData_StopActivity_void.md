# LogProvider::ClientAuthDecryptData::StopActivity(void)

- ea: `0x140042660`
- end: `0x140042885`
- name: `?StopActivity@ClientAuthDecryptData@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::ClientAuthDecryptData *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140002cc0`
- `0x140003124`
- `0x14000330c`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x140042660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140042822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140042822`

## pseudocode

```c
void __fastcall LogProvider::ClientAuthDecryptData::StopActivity(LogProvider::ClientAuthDecryptData *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = LogProvider::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 4u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = (__int64 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (__int64 *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (__int64 *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0x1000000;
      v17 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (unsigned __int8 *)byte_14008D72B,
        (const GUID *)(v10 + 8),
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LogProvider::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&unk_14008D858,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x140042660  push    rbp
0x140042662  push    rbx
0x140042663  push    rdi
0x140042664  lea     rbp, [rsp-47h]
0x140042669  sub     rsp, 100h
0x140042670  mov     rdi, [rcx+110h]
0x140042677  mov     rbx, rcx
0x14004267a  mov     eax, [rdi+48h]
0x14004267d  test    eax, eax
0x14004267f  jns     loc_1400427F8
0x140042685  add     rdi, 50h ; 'P'
0x140042689  cmp     eax, [rdi+8]
0x14004268c  jnz     loc_1400427F8
0x140042692  test    rdi, rdi
0x140042695  jz      loc_1400427F8
0x14004269b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400426a0  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1400426a5  mov     r9, rax
0x1400426a8  mov     ecx, [rax]
0x1400426aa  cmp     ecx, 4
0x1400426ad  jbe     loc_140042873
0x1400426b3  mov     rdx, 400000000000h
0x1400426bd  mov     rcx, rax
0x1400426c0  call    _tlgKeywordOn
0x1400426c5  test    al, al
0x1400426c7  jz      loc_140042873
0x1400426cd  mov     rax, [rdi+70h]
0x1400426d1  lea     rdx, byte_14008D72B
0x1400426d8  mov     rcx, [rdi+78h]
0x1400426dc  mov     r8, [rbx+110h]
0x1400426e3  mov     [rbp+57h+var_60], rax
0x1400426e7  add     r8, 8
0x1400426eb  mov     eax, [rdi+68h]
0x1400426ee  mov     [rbp+57h+arg_0], eax
0x1400426f1  mov     rax, [rdi+60h]
0x1400426f5  mov     [rbp+57h+var_58], rax
0x1400426f9  mov     rax, [rdi+58h]
0x1400426fd  mov     [rbp+57h+var_50], rax
0x140042701  mov     eax, [rdi+50h]
0x140042704  mov     [rbp+57h+arg_8], eax
0x140042707  mov     rax, [rdi+48h]
0x14004270b  mov     [rbp+57h+var_48], rax
0x14004270f  mov     eax, [rdi+20h]
0x140042712  mov     dword ptr [rbp+57h+arg_10], eax
0x140042715  mov     rax, [rdi+18h]
0x140042719  mov     [rbp+57h+var_40], rax
0x14004271d  mov     eax, [rdi]
0x14004271f  mov     [rbp+57h+arg_18], eax
0x140042722  mov     rax, [rdi+80h]
0x140042729  mov     [rbp+57h+var_38], rax
0x14004272d  mov     eax, [rdi+40h]
0x140042730  mov     [rbp+57h+var_70], eax
0x140042733  mov     rax, [rdi+38h]
0x140042737  mov     [rbp+57h+var_30], rax
0x14004273b  mov     eax, [rdi+8]
0x14004273e  mov     [rbp+57h+var_6C], eax
0x140042741  mov     eax, 1000000h
0x140042746  mov     [rbp+57h+var_28], rax
0x14004274a  mov     [rbp+57h+var_20], rax
0x14004274e  lea     rax, [rbp+57h+var_68]
0x140042752  mov     [rsp+110h+var_78], rax
0x14004275a  lea     rax, [rbp+57h+var_60]
0x14004275e  mov     [rsp+110h+var_80], rax
0x140042766  lea     rax, [rbp+57h+arg_0]
0x14004276a  mov     [rsp+110h+var_88], rax
0x140042772  lea     rax, [rbp+57h+var_58]
0x140042776  mov     [rsp+110h+var_90], rax
0x14004277e  lea     rax, [rbp+57h+var_50]
0x140042782  mov     [rsp+110h+var_98], rax
0x140042787  lea     rax, [rbp+57h+arg_8]
0x14004278b  mov     [rsp+110h+var_A0], rax
0x140042790  lea     rax, [rbp+57h+var_48]
0x140042794  mov     [rsp+110h+var_A8], rax
0x140042799  lea     rax, [rbp+57h+arg_10]
0x14004279d  mov     [rsp+110h+var_B0], rax
0x1400427a2  lea     rax, [rbp+57h+var_40]
0x1400427a6  mov     [rsp+110h+var_B8], rax
0x1400427ab  lea     rax, [rbp+57h+arg_18]
0x1400427af  mov     [rsp+110h+var_C0], rax
0x1400427b4  lea     rax, [rbp+57h+var_38]
0x1400427b8  mov     [rsp+110h+var_C8], rax
0x1400427bd  lea     rax, [rbp+57h+var_70]
0x1400427c1  mov     [rsp+110h+var_D0], rax
0x1400427c6  lea     rax, [rbp+57h+var_30]
0x1400427ca  mov     [rsp+110h+var_D8], rax
0x1400427cf  lea     rax, [rbp+57h+var_6C]
0x1400427d3  mov     [rsp+110h+var_E0], rax
0x1400427d8  lea     rax, [rbp+57h+var_28]
0x1400427dc  mov     [rsp+110h+var_E8], rax
0x1400427e1  lea     rax, [rbp+57h+var_20]
0x1400427e5  mov     [rbp+57h+var_68], rcx
0x1400427e9  mov     rcx, r9
0x1400427ec  mov     [rsp+110h+var_F0], rax
0x1400427f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400427f6  jmp     short loc_140042873
0x1400427f8  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400427fd  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140042802  mov     rdi, rax
0x140042805  mov     ecx, [rax]
0x140042807  cmp     ecx, 4
0x14004280a  jbe     short loc_140042873
0x14004280c  mov     rdx, 400000000000h
0x140042816  mov     rcx, rax
0x140042819  call    _tlgKeywordOn
0x14004281e  test    al, al
0x140042820  jz      short loc_140042873
0x140042822  call    cs:__imp_GetCurrentThreadId
0x140042828  mov     r8, [rbx+110h]
0x14004282f  lea     rdx, unk_14008D858
0x140042836  mov     [rbp+57h+arg_0], eax
0x140042839  xor     r9d, r9d
0x14004283c  mov     rcx, rdi
0x14004283f  mov     eax, [r8+48h]
0x140042843  add     r8, 8
0x140042847  mov     [rbp+57h+arg_8], eax
0x14004284a  mov     eax, 1000000h
0x14004284f  mov     [rbp+57h+arg_10], rax
0x140042853  lea     rax, [rbp+57h+arg_0]
0x140042857  mov     [rsp+110h+var_E0], rax
0x14004285c  lea     rax, [rbp+57h+arg_8]
0x140042860  mov     [rsp+110h+var_E8], rax
0x140042865  lea     rax, [rbp+57h+arg_10]
0x140042869  mov     [rsp+110h+var_F0], rax
0x14004286e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140042873  mov     rcx, rbx
0x140042876  add     rsp, 100h
0x14004287d  pop     rdi
0x14004287e  pop     rbx
0x14004287f  pop     rbp
0x140042880  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
