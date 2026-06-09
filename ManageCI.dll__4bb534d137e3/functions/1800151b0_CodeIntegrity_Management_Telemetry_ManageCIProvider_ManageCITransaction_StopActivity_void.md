# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::StopActivity(void)

- ea: `0x1800151b0`
- end: `0x1800153d2`
- name: `?StopActivity@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800019bc`
- `0x180002054`
- `0x1800137d4`
- `0x180014ce4`
- `0x1800151b0`
- `0x180016330`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015372`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015372`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::StopActivity(
        CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  int *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  int *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  int *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  int *v23; // [rsp+D0h] [rbp+17h] BYREF
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
    wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6) )
    {
      v8 = (int *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (int *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (int *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v26 = 0x1000000;
      v27[0] = 0x1000000;
      v18 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)&unk_180031D10,
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
    wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
    v12 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)word_180031BF2,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800151b0  push    rbp
0x1800151b2  push    rbx
0x1800151b3  push    rdi
0x1800151b4  lea     rbp, [rsp-47h]
0x1800151b9  sub     rsp, 100h
0x1800151c0  mov     rdi, [rcx+110h]
0x1800151c7  mov     rbx, rcx
0x1800151ca  mov     eax, [rdi+48h]
0x1800151cd  test    eax, eax
0x1800151cf  jns     loc_180015348
0x1800151d5  add     rdi, 50h ; 'P'
0x1800151d9  cmp     eax, [rdi+8]
0x1800151dc  jnz     loc_180015348
0x1800151e2  test    rdi, rdi
0x1800151e5  jz      loc_180015348
0x1800151eb  call    ?zInternalStop@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800151f0  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x1800151f5  mov     r9, rax
0x1800151f8  mov     ecx, [rax]
0x1800151fa  cmp     ecx, 5
0x1800151fd  jbe     loc_1800153C0
0x180015203  mov     rdx, 400000000000h
0x18001520d  mov     rcx, rax
0x180015210  call    _tlgKeywordOn
0x180015215  test    al, al
0x180015217  jz      loc_1800153C0
0x18001521d  mov     rax, [rdi+70h]
0x180015221  lea     rdx, unk_180031D10
0x180015228  mov     rcx, [rdi+78h]
0x18001522c  mov     r8, [rbx+110h]
0x180015233  mov     [rbp+57h+var_60], rax
0x180015237  add     r8, 8
0x18001523b  mov     eax, [rdi+68h]
0x18001523e  mov     [rbp+57h+arg_0], eax
0x180015241  mov     rax, [rdi+60h]
0x180015245  mov     [rbp+57h+var_58], rax
0x180015249  mov     rax, [rdi+58h]
0x18001524d  mov     [rbp+57h+var_50], rax
0x180015251  mov     eax, [rdi+50h]
0x180015254  mov     [rbp+57h+arg_8], eax
0x180015257  mov     rax, [rdi+48h]
0x18001525b  mov     [rbp+57h+var_48], rax
0x18001525f  mov     eax, [rdi+20h]
0x180015262  mov     dword ptr [rbp+57h+arg_10], eax
0x180015265  mov     rax, [rdi+18h]
0x180015269  mov     [rbp+57h+var_40], rax
0x18001526d  mov     eax, [rdi]
0x18001526f  mov     [rbp+57h+arg_18], eax
0x180015272  mov     rax, [rdi+80h]
0x180015279  mov     [rbp+57h+var_38], rax
0x18001527d  mov     eax, [rdi+40h]
0x180015280  mov     [rbp+57h+var_70], eax
0x180015283  mov     rax, [rdi+38h]
0x180015287  mov     [rbp+57h+var_30], rax
0x18001528b  mov     eax, [rdi+8]
0x18001528e  mov     [rbp+57h+var_6C], eax
0x180015291  mov     eax, 1000000h
0x180015296  mov     [rbp+57h+var_28], rax
0x18001529a  mov     [rbp+57h+var_20], rax
0x18001529e  lea     rax, [rbp+57h+var_68]
0x1800152a2  mov     [rsp+110h+var_78], rax
0x1800152aa  lea     rax, [rbp+57h+var_60]
0x1800152ae  mov     [rsp+110h+var_80], rax
0x1800152b6  lea     rax, [rbp+57h+arg_0]
0x1800152ba  mov     [rsp+110h+var_88], rax
0x1800152c2  lea     rax, [rbp+57h+var_58]
0x1800152c6  mov     [rsp+110h+var_90], rax
0x1800152ce  lea     rax, [rbp+57h+var_50]
0x1800152d2  mov     [rsp+110h+var_98], rax
0x1800152d7  lea     rax, [rbp+57h+arg_8]
0x1800152db  mov     [rsp+110h+var_A0], rax
0x1800152e0  lea     rax, [rbp+57h+var_48]
0x1800152e4  mov     [rsp+110h+var_A8], rax
0x1800152e9  lea     rax, [rbp+57h+arg_10]
0x1800152ed  mov     [rsp+110h+var_B0], rax
0x1800152f2  lea     rax, [rbp+57h+var_40]
0x1800152f6  mov     [rsp+110h+var_B8], rax
0x1800152fb  lea     rax, [rbp+57h+arg_18]
0x1800152ff  mov     [rsp+110h+var_C0], rax
0x180015304  lea     rax, [rbp+57h+var_38]
0x180015308  mov     [rsp+110h+var_C8], rax
0x18001530d  lea     rax, [rbp+57h+var_70]
0x180015311  mov     [rsp+110h+var_D0], rax
0x180015316  lea     rax, [rbp+57h+var_30]
0x18001531a  mov     [rsp+110h+var_D8], rax
0x18001531f  lea     rax, [rbp+57h+var_6C]
0x180015323  mov     [rsp+110h+var_E0], rax
0x180015328  lea     rax, [rbp+57h+var_28]
0x18001532c  mov     [rsp+110h+var_E8], rax
0x180015331  lea     rax, [rbp+57h+var_20]
0x180015335  mov     [rbp+57h+var_68], rcx
0x180015339  mov     rcx, r9
0x18001533c  mov     [rsp+110h+var_F0], rax
0x180015341  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180015346  jmp     short loc_1800153C0
0x180015348  call    ?zInternalStop@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001534d  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180015352  mov     rdi, rax
0x180015355  mov     ecx, [rax]
0x180015357  cmp     ecx, 5
0x18001535a  jbe     short loc_1800153C0
0x18001535c  mov     rdx, 400000000000h
0x180015366  mov     rcx, rax
0x180015369  call    _tlgKeywordOn
0x18001536e  test    al, al
0x180015370  jz      short loc_1800153C0
0x180015372  call    cs:__imp_GetCurrentThreadId
0x180015378  mov     r8, [rbx+110h]
0x18001537f  lea     rdx, word_180031BF2
0x180015386  mov     [rbp+57h+arg_0], eax
0x180015389  mov     rcx, rdi
0x18001538c  mov     eax, [r8+48h]
0x180015390  add     r8, 8
0x180015394  mov     [rbp+57h+arg_8], eax
0x180015397  mov     eax, 1000000h
0x18001539c  mov     [rbp+57h+arg_10], rax
0x1800153a0  lea     rax, [rbp+57h+arg_0]
0x1800153a4  mov     [rsp+110h+var_E0], rax
0x1800153a9  lea     rax, [rbp+57h+arg_8]
0x1800153ad  mov     [rsp+110h+var_E8], rax
0x1800153b2  lea     rax, [rbp+57h+arg_10]
0x1800153b6  mov     [rsp+110h+var_F0], rax
0x1800153bb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800153c0  mov     rcx, rbx
0x1800153c3  add     rsp, 100h
0x1800153ca  pop     rdi
0x1800153cb  pop     rbx
0x1800153cc  pop     rbp
0x1800153cd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
