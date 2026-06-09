# LogProvider::NgcIsoContainerOpenBuffer::Stop(ulong)

- ea: `0x14002e7f4`
- end: `0x14002ea49`
- name: `?Stop@NgcIsoContainerOpenBuffer@LogProvider@@QEAAXK@Z`
- size: `597`
- prototype: `void __fastcall(LogProvider::NgcIsoContainerOpenBuffer *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140024290`

## callees

- `0x140001c98`
- `0x1400033f4`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14002e7f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e9d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e9d9`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoContainerOpenBuffer::Stop(LogProvider::NgcIsoContainerOpenBuffer *this, int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  int v18; // [rsp+C4h] [rbp-7Ch] BYREF
  int v19; // [rsp+C8h] [rbp-78h] BYREF
  int v20; // [rsp+CCh] [rbp-74h] BYREF
  int v21; // [rsp+D0h] [rbp-70h] BYREF
  int v22; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v23; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+100h] [rbp-40h] BYREF
  __int64 v29; // [rsp+108h] [rbp-38h] BYREF
  __int64 v30; // [rsp+110h] [rbp-30h] BYREF
  __int64 v31; // [rsp+118h] [rbp-28h] BYREF
  __int64 v32; // [rsp+120h] [rbp-20h] BYREF
  __int64 v33[3]; // [rsp+128h] [rbp-18h] BYREF
  int v34; // [rsp+150h] [rbp+10h] BYREF
  DWORD v35; // [rsp+160h] [rbp+20h] BYREF
  int v36; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = LogProvider::Provider();
    if ( *(_DWORD *)v9 > 5u )
    {
      v10 = *((_QWORD *)v6 + 6);
      v26 = *((_QWORD *)v6 + 14);
      v17 = v6[26];
      v11 = *((_QWORD *)this + 34);
      v27 = *((_QWORD *)v6 + 12);
      v28 = *((_QWORD *)v6 + 11);
      v18 = v6[20];
      v29 = *((_QWORD *)v6 + 9);
      v19 = v6[8];
      v30 = *((_QWORD *)v6 + 3);
      v20 = *v6;
      v31 = *((_QWORD *)v6 + 16);
      v21 = v6[16];
      v32 = *((_QWORD *)v6 + 7);
      v22 = v6[2];
      v24 = v10;
      v35 = v6[17];
      v36 = v6[4];
      v25 = *((_QWORD *)v6 + 15);
      v34 = a2;
      v33[0] = 0x1000000;
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)&word_14008A9EE,
        v11 + 8,
        (_DWORD)v9,
        (__int64)&v23,
        (__int64)v33,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v24,
        (__int64)&v34);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LogProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 5u )
    {
      v34 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v35 = CurrentThreadId;
      v36 = *(_DWORD *)(v15 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_14008AB55,
        v15 + 8,
        v16,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v8,
    v9);
}

```

## disassembly

```asm
0x14002e7f4  mov     [rsp-8+arg_8], rbx
0x14002e7f9  push    rbp
0x14002e7fa  push    rsi
0x14002e7fb  push    rdi
0x14002e7fc  lea     rbp, [rsp+10h]
0x14002e801  sub     rsp, 130h
0x14002e808  mov     rdi, [rcx+110h]
0x14002e80f  mov     esi, edx
0x14002e811  mov     rbx, rcx
0x14002e814  mov     eax, [rdi+48h]
0x14002e817  test    eax, eax
0x14002e819  jns     loc_14002E9C2
0x14002e81f  add     rdi, 50h ; 'P'
0x14002e823  cmp     eax, [rdi+8]
0x14002e826  jnz     loc_14002E9C2
0x14002e82c  test    rdi, rdi
0x14002e82f  jz      loc_14002E9C2
0x14002e835  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002e83a  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002e83f  mov     r9, rax
0x14002e842  mov     ecx, [rax]
0x14002e844  cmp     ecx, 5
0x14002e847  jbe     loc_14002EA2F
0x14002e84d  mov     rax, [rdi+70h]
0x14002e851  lea     rdx, word_14008A9EE
0x14002e858  mov     rcx, [rdi+30h]
0x14002e85c  mov     [rbp+var_50], rax
0x14002e860  mov     eax, [rdi+68h]
0x14002e863  mov     [rbp+var_80], eax
0x14002e866  mov     rax, [rdi+60h]
0x14002e86a  mov     r8, [rbx+110h]
0x14002e871  mov     [rbp+var_48], rax
0x14002e875  add     r8, 8
0x14002e879  mov     rax, [rdi+58h]
0x14002e87d  mov     [rbp+var_40], rax
0x14002e881  mov     eax, [rdi+50h]
0x14002e884  mov     [rbp+var_7C], eax
0x14002e887  mov     rax, [rdi+48h]
0x14002e88b  mov     [rbp+var_38], rax
0x14002e88f  mov     eax, [rdi+20h]
0x14002e892  mov     [rbp+var_78], eax
0x14002e895  mov     rax, [rdi+18h]
0x14002e899  mov     [rbp+var_30], rax
0x14002e89d  mov     eax, [rdi]
0x14002e89f  mov     [rbp+var_74], eax
0x14002e8a2  mov     rax, [rdi+80h]
0x14002e8a9  mov     [rbp+var_28], rax
0x14002e8ad  mov     eax, [rdi+40h]
0x14002e8b0  mov     [rbp+var_70], eax
0x14002e8b3  mov     rax, [rdi+38h]
0x14002e8b7  mov     [rbp+var_20], rax
0x14002e8bb  mov     eax, [rdi+8]
0x14002e8be  mov     [rbp+var_6C], eax
0x14002e8c1  lea     rax, [rbp+arg_0]
0x14002e8c5  mov     [rsp+140h+var_88], rax
0x14002e8cd  lea     rax, [rbp+var_60]
0x14002e8d1  mov     [rsp+140h+var_90], rax
0x14002e8d9  lea     rax, [rbp+arg_10]
0x14002e8dd  mov     [rsp+140h+var_98], rax
0x14002e8e5  lea     rax, [rbp+arg_18]
0x14002e8e9  mov     [rsp+140h+var_A0], rax
0x14002e8f1  lea     rax, [rbp+var_58]
0x14002e8f5  mov     [rsp+140h+var_A8], rax
0x14002e8fd  lea     rax, [rbp+var_50]
0x14002e901  mov     [rsp+140h+var_B0], rax
0x14002e909  lea     rax, [rbp+var_80]
0x14002e90d  mov     [rsp+140h+var_B8], rax
0x14002e915  lea     rax, [rbp+var_48]
0x14002e919  mov     [rsp+140h+var_C0], rax
0x14002e921  lea     rax, [rbp+var_40]
0x14002e925  mov     [rsp+140h+var_C8], rax
0x14002e92a  lea     rax, [rbp+var_7C]
0x14002e92e  mov     [rsp+140h+var_D0], rax
0x14002e933  lea     rax, [rbp+var_38]
0x14002e937  mov     [rsp+140h+var_D8], rax
0x14002e93c  lea     rax, [rbp+var_78]
0x14002e940  mov     [rsp+140h+var_E0], rax
0x14002e945  lea     rax, [rbp+var_30]
0x14002e949  mov     [rsp+140h+var_E8], rax
0x14002e94e  lea     rax, [rbp+var_74]
0x14002e952  mov     [rsp+140h+var_F0], rax
0x14002e957  lea     rax, [rbp+var_28]
0x14002e95b  mov     [rsp+140h+var_F8], rax
0x14002e960  lea     rax, [rbp+var_70]
0x14002e964  mov     [rsp+140h+var_100], rax
0x14002e969  lea     rax, [rbp+var_20]
0x14002e96d  mov     [rsp+140h+var_108], rax
0x14002e972  lea     rax, [rbp+var_6C]
0x14002e976  mov     [rbp+var_60], rcx
0x14002e97a  mov     ecx, [rdi+44h]
0x14002e97d  mov     [rsp+140h+var_110], rax
0x14002e982  lea     rax, [rbp+var_18]
0x14002e986  mov     [rbp+arg_10], ecx
0x14002e989  mov     ecx, [rdi+10h]
0x14002e98c  mov     [rbp+arg_18], ecx
0x14002e98f  mov     rcx, [rdi+78h]
0x14002e993  mov     [rsp+140h+var_118], rax
0x14002e998  lea     rax, [rbp+var_68]
0x14002e99c  mov     [rbp+var_58], rcx
0x14002e9a0  mov     rcx, r9
0x14002e9a3  mov     [rsp+140h+var_120], rax
0x14002e9a8  mov     [rbp+arg_0], esi
0x14002e9ab  mov     [rbp+var_18], 1000000h
0x14002e9b3  mov     [rbp+var_68], 0
0x14002e9bb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14002e9c0  jmp     short loc_14002EA2F
0x14002e9c2  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002e9c7  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002e9cc  mov     rdi, rax
0x14002e9cf  mov     ecx, [rax]
0x14002e9d1  cmp     ecx, 5
0x14002e9d4  jbe     short loc_14002EA2F
0x14002e9d6  mov     [rbp+arg_0], esi
0x14002e9d9  call    cs:__imp_GetCurrentThreadId
0x14002e9df  mov     r8, [rbx+110h]
0x14002e9e6  lea     rdx, byte_14008AB55
0x14002e9ed  mov     [rbp+arg_10], eax
0x14002e9f0  lea     rax, [rbp+arg_0]
0x14002e9f4  mov     [rsp+140h+var_108], rax
0x14002e9f9  lea     rax, [rbp+arg_10]
0x14002e9fd  mov     [rsp+140h+var_110], rax
0x14002ea02  lea     rax, [rbp+arg_18]
0x14002ea06  mov     ecx, [r8+48h]
0x14002ea0a  add     r8, 8
0x14002ea0e  mov     [rsp+140h+var_118], rax
0x14002ea13  lea     rax, [rbp+var_68]
0x14002ea17  mov     [rbp+arg_18], ecx
0x14002ea1a  mov     rcx, rdi
0x14002ea1d  mov     [rsp+140h+var_120], rax
0x14002ea22  mov     [rbp+var_68], 0
0x14002ea2a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002ea2f  mov     rcx, rbx
0x14002ea32  mov     rbx, [rsp+140h+arg_8]
0x14002ea3a  add     rsp, 130h
0x14002ea41  pop     rdi
0x14002ea42  pop     rsi
0x14002ea43  pop     rbp
0x14002ea44  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
