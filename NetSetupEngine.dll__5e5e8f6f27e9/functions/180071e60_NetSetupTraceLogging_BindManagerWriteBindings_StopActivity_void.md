# NetSetupTraceLogging::BindManagerWriteBindings::StopActivity(void)

- ea: `0x180071e60`
- end: `0x1800720b2`
- name: `?StopActivity@BindManagerWriteBindings@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::BindManagerWriteBindings *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18000154c`
- `0x180001860`
- `0x18000e54c`
- `0x180033720`
- `0x18003ae24`
- `0x180046ed0`
- `0x180071e60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180072053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180072053`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::BindManagerWriteBindings::StopActivity(
        NetSetupTraceLogging::BindManagerWriteBindings *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+120h] [rbp-20h] BYREF
  __int64 v30; // [rsp+150h] [rbp+10h] BYREF
  __int64 v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  __int64 v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = NetSetupTraceLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 1, v7, v5) )
    {
      v19 = *((_QWORD *)v4 + 6);
      LODWORD(v30) = v4[17];
      LODWORD(v31) = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v21 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      LODWORD(v33) = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v8,
        (int)&byte_1800B320B,
        v9 + 8,
        v8,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (const wchar_t **)&v27,
        (__int64)&v17,
        (const wchar_t **)&v26,
        (__int64)&v16,
        (const WCHAR **)&v25,
        (__int64)&v15,
        (const wchar_t **)&v24,
        (__int64)&v33,
        (const wchar_t **)&v23,
        (const WCHAR **)&v22,
        (__int64)&v32,
        (const wchar_t **)&v21,
        (const WCHAR **)&v20,
        (__int64)&v31,
        (__int64)&v30,
        (const wchar_t **)&v19);
    }
  }
  else
  {
    wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = NetSetupTraceLogging::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 1, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      LODWORD(v30) = CurrentThreadId;
      LODWORD(v31) = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (int)&word_1800B335E,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180071e60  push    rbp
0x180071e62  push    rbx
0x180071e63  push    rdi
0x180071e64  lea     rbp, [rsp+10h]
0x180071e69  sub     rsp, 130h
0x180071e70  mov     rdi, [rcx+110h]
0x180071e77  mov     rbx, rcx
0x180071e7a  mov     eax, [rdi+48h]
0x180071e7d  test    eax, eax
0x180071e7f  jns     loc_18007202E
0x180071e85  add     rdi, 50h ; 'P'
0x180071e89  cmp     eax, [rdi+8]
0x180071e8c  jnz     loc_18007202E
0x180071e92  test    rdi, rdi
0x180071e95  jz      loc_18007202E
0x180071e9b  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180071ea0  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180071ea5  mov     r9, rax
0x180071ea8  mov     ecx, [rax]
0x180071eaa  cmp     ecx, 5
0x180071ead  jbe     loc_1800720A0
0x180071eb3  mov     edx, 1
0x180071eb8  mov     rcx, rax
0x180071ebb  call    _tlgKeywordOn
0x180071ec0  test    al, al
0x180071ec2  jz      loc_1800720A0
0x180071ec8  mov     rax, [rdi+30h]
0x180071ecc  lea     rdx, byte_1800B320B; int
0x180071ed3  mov     [rbp+var_70], rax
0x180071ed7  mov     rcx, r9; int
0x180071eda  mov     eax, [rdi+44h]
0x180071edd  mov     dword ptr [rbp+arg_0], eax
0x180071ee0  mov     eax, [rdi+10h]
0x180071ee3  mov     dword ptr [rbp+arg_8], eax
0x180071ee6  mov     rax, [rdi+78h]
0x180071eea  mov     [rbp+var_68], rax
0x180071eee  mov     rax, [rdi+70h]
0x180071ef2  mov     [rbp+var_60], rax
0x180071ef6  mov     eax, [rdi+68h]
0x180071ef9  mov     r8, [rbx+110h]
0x180071f00  mov     dword ptr [rbp+arg_10], eax
0x180071f03  add     r8, 8; int
0x180071f07  mov     rax, [rdi+60h]
0x180071f0b  mov     [rbp+var_58], rax
0x180071f0f  mov     rax, [rdi+58h]
0x180071f13  mov     [rbp+var_50], rax
0x180071f17  mov     eax, [rdi+50h]
0x180071f1a  mov     dword ptr [rbp+arg_18], eax
0x180071f1d  mov     rax, [rdi+48h]
0x180071f21  mov     [rbp+var_48], rax
0x180071f25  mov     eax, [rdi+20h]
0x180071f28  mov     dword ptr [rbp+var_80], eax
0x180071f2b  mov     rax, [rdi+18h]
0x180071f2f  mov     [rbp+var_40], rax
0x180071f33  mov     eax, [rdi]
0x180071f35  mov     dword ptr [rbp+var_80+4], eax
0x180071f38  mov     rax, [rdi+80h]
0x180071f3f  mov     [rbp+var_38], rax
0x180071f43  mov     eax, [rdi+40h]
0x180071f46  mov     dword ptr [rbp+var_78], eax
0x180071f49  mov     rax, [rdi+38h]
0x180071f4d  mov     [rbp+var_30], rax
0x180071f51  mov     eax, [rdi+8]
0x180071f54  mov     dword ptr [rbp+var_78+4], eax
0x180071f57  lea     rax, [rbp+var_70]
0x180071f5b  mov     [rsp+140h+var_90], rax; __int64
0x180071f63  lea     rax, [rbp+arg_0]
0x180071f67  mov     [rsp+140h+var_98], rax; __int64
0x180071f6f  lea     rax, [rbp+arg_8]
0x180071f73  mov     [rsp+140h+var_A0], rax; __int64
0x180071f7b  lea     rax, [rbp+var_68]
0x180071f7f  mov     [rsp+140h+var_A8], rax; __int64
0x180071f87  lea     rax, [rbp+var_60]
0x180071f8b  mov     [rsp+140h+var_B0], rax; __int64
0x180071f93  lea     rax, [rbp+arg_10]
0x180071f97  mov     [rsp+140h+var_B8], rax; __int64
0x180071f9f  lea     rax, [rbp+var_58]
0x180071fa3  mov     [rsp+140h+var_C0], rax; __int64
0x180071fab  lea     rax, [rbp+var_50]
0x180071faf  mov     [rsp+140h+var_C8], rax; __int64
0x180071fb4  lea     rax, [rbp+arg_18]
0x180071fb8  mov     [rsp+140h+var_D0], rax; __int64
0x180071fbd  lea     rax, [rbp+var_48]
0x180071fc1  mov     [rsp+140h+var_D8], rax; __int64
0x180071fc6  lea     rax, [rbp+var_80]
0x180071fca  mov     [rsp+140h+var_E0], rax; __int64
0x180071fcf  lea     rax, [rbp+var_40]
0x180071fd3  mov     [rsp+140h+var_E8], rax; __int64
0x180071fd8  lea     rax, [rbp+var_80+4]
0x180071fdc  mov     [rsp+140h+var_F0], rax; __int64
0x180071fe1  lea     rax, [rbp+var_38]
0x180071fe5  mov     [rsp+140h+var_F8], rax; __int64
0x180071fea  lea     rax, [rbp+var_78]
0x180071fee  mov     [rsp+140h+var_100], rax; __int64
0x180071ff3  lea     rax, [rbp+var_30]
0x180071ff7  mov     [rsp+140h+var_108], rax; __int64
0x180071ffc  lea     rax, [rbp+var_78+4]
0x180072000  mov     [rsp+140h+var_110], rax; __int64
0x180072005  lea     rax, [rbp+var_28]
0x180072009  mov     [rsp+140h+var_118], rax; __int64
0x18007200e  lea     rax, [rbp+var_20]
0x180072012  mov     [rsp+140h+var_120], rax; __int64
0x180072017  mov     [rbp+var_28], 1000000h
0x18007201f  mov     [rbp+var_20], 0
0x180072027  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007202c  jmp     short loc_1800720A0
0x18007202e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180072033  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180072038  mov     rdi, rax
0x18007203b  mov     ecx, [rax]
0x18007203d  cmp     ecx, 5
0x180072040  jbe     short loc_1800720A0
0x180072042  mov     edx, 1
0x180072047  mov     rcx, rax
0x18007204a  call    _tlgKeywordOn
0x18007204f  test    al, al
0x180072051  jz      short loc_1800720A0
0x180072053  call    cs:__imp_GetCurrentThreadId
0x180072059  mov     r8, [rbx+110h]
0x180072060  lea     rdx, word_1800B335E
0x180072067  mov     dword ptr [rbp+arg_0], eax
0x18007206a  mov     rcx, rdi
0x18007206d  mov     eax, [r8+48h]
0x180072071  add     r8, 8
0x180072075  mov     dword ptr [rbp+arg_8], eax
0x180072078  lea     rax, [rbp+arg_0]
0x18007207c  mov     [rsp+140h+var_110], rax
0x180072081  lea     rax, [rbp+arg_8]
0x180072085  mov     [rsp+140h+var_118], rax
0x18007208a  lea     rax, [rbp+arg_10]
0x18007208e  mov     [rsp+140h+var_120], rax
0x180072093  mov     [rbp+arg_10], 0
0x18007209b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800720a0  mov     rcx, rbx
0x1800720a3  add     rsp, 130h
0x1800720aa  pop     rdi
0x1800720ab  pop     rbx
0x1800720ac  pop     rbp
0x1800720ad  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
