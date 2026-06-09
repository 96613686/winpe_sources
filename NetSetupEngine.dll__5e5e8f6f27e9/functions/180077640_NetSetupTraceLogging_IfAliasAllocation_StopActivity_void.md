# NetSetupTraceLogging::IfAliasAllocation::StopActivity(void)

- ea: `0x180077640`
- end: `0x180077892`
- name: `?StopActivity@IfAliasAllocation@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::IfAliasAllocation *__hidden this)`
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
- `0x180077640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077833`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::IfAliasAllocation::StopActivity(NetSetupTraceLogging::IfAliasAllocation *this)
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
        (int)&byte_1800B4627,
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
        (int)byte_1800B4773,
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
0x180077640  push    rbp
0x180077642  push    rbx
0x180077643  push    rdi
0x180077644  lea     rbp, [rsp+10h]
0x180077649  sub     rsp, 130h
0x180077650  mov     rdi, [rcx+110h]
0x180077657  mov     rbx, rcx
0x18007765a  mov     eax, [rdi+48h]
0x18007765d  test    eax, eax
0x18007765f  jns     loc_18007780E
0x180077665  add     rdi, 50h ; 'P'
0x180077669  cmp     eax, [rdi+8]
0x18007766c  jnz     loc_18007780E
0x180077672  test    rdi, rdi
0x180077675  jz      loc_18007780E
0x18007767b  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180077680  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180077685  mov     r9, rax
0x180077688  mov     ecx, [rax]
0x18007768a  cmp     ecx, 5
0x18007768d  jbe     loc_180077880
0x180077693  mov     edx, 1
0x180077698  mov     rcx, rax
0x18007769b  call    _tlgKeywordOn
0x1800776a0  test    al, al
0x1800776a2  jz      loc_180077880
0x1800776a8  mov     rax, [rdi+30h]
0x1800776ac  lea     rdx, byte_1800B4627; int
0x1800776b3  mov     [rbp+var_70], rax
0x1800776b7  mov     rcx, r9; int
0x1800776ba  mov     eax, [rdi+44h]
0x1800776bd  mov     dword ptr [rbp+arg_0], eax
0x1800776c0  mov     eax, [rdi+10h]
0x1800776c3  mov     dword ptr [rbp+arg_8], eax
0x1800776c6  mov     rax, [rdi+78h]
0x1800776ca  mov     [rbp+var_68], rax
0x1800776ce  mov     rax, [rdi+70h]
0x1800776d2  mov     [rbp+var_60], rax
0x1800776d6  mov     eax, [rdi+68h]
0x1800776d9  mov     r8, [rbx+110h]
0x1800776e0  mov     dword ptr [rbp+arg_10], eax
0x1800776e3  add     r8, 8; int
0x1800776e7  mov     rax, [rdi+60h]
0x1800776eb  mov     [rbp+var_58], rax
0x1800776ef  mov     rax, [rdi+58h]
0x1800776f3  mov     [rbp+var_50], rax
0x1800776f7  mov     eax, [rdi+50h]
0x1800776fa  mov     dword ptr [rbp+arg_18], eax
0x1800776fd  mov     rax, [rdi+48h]
0x180077701  mov     [rbp+var_48], rax
0x180077705  mov     eax, [rdi+20h]
0x180077708  mov     dword ptr [rbp+var_80], eax
0x18007770b  mov     rax, [rdi+18h]
0x18007770f  mov     [rbp+var_40], rax
0x180077713  mov     eax, [rdi]
0x180077715  mov     dword ptr [rbp+var_80+4], eax
0x180077718  mov     rax, [rdi+80h]
0x18007771f  mov     [rbp+var_38], rax
0x180077723  mov     eax, [rdi+40h]
0x180077726  mov     dword ptr [rbp+var_78], eax
0x180077729  mov     rax, [rdi+38h]
0x18007772d  mov     [rbp+var_30], rax
0x180077731  mov     eax, [rdi+8]
0x180077734  mov     dword ptr [rbp+var_78+4], eax
0x180077737  lea     rax, [rbp+var_70]
0x18007773b  mov     [rsp+140h+var_90], rax; __int64
0x180077743  lea     rax, [rbp+arg_0]
0x180077747  mov     [rsp+140h+var_98], rax; __int64
0x18007774f  lea     rax, [rbp+arg_8]
0x180077753  mov     [rsp+140h+var_A0], rax; __int64
0x18007775b  lea     rax, [rbp+var_68]
0x18007775f  mov     [rsp+140h+var_A8], rax; __int64
0x180077767  lea     rax, [rbp+var_60]
0x18007776b  mov     [rsp+140h+var_B0], rax; __int64
0x180077773  lea     rax, [rbp+arg_10]
0x180077777  mov     [rsp+140h+var_B8], rax; __int64
0x18007777f  lea     rax, [rbp+var_58]
0x180077783  mov     [rsp+140h+var_C0], rax; __int64
0x18007778b  lea     rax, [rbp+var_50]
0x18007778f  mov     [rsp+140h+var_C8], rax; __int64
0x180077794  lea     rax, [rbp+arg_18]
0x180077798  mov     [rsp+140h+var_D0], rax; __int64
0x18007779d  lea     rax, [rbp+var_48]
0x1800777a1  mov     [rsp+140h+var_D8], rax; __int64
0x1800777a6  lea     rax, [rbp+var_80]
0x1800777aa  mov     [rsp+140h+var_E0], rax; __int64
0x1800777af  lea     rax, [rbp+var_40]
0x1800777b3  mov     [rsp+140h+var_E8], rax; __int64
0x1800777b8  lea     rax, [rbp+var_80+4]
0x1800777bc  mov     [rsp+140h+var_F0], rax; __int64
0x1800777c1  lea     rax, [rbp+var_38]
0x1800777c5  mov     [rsp+140h+var_F8], rax; __int64
0x1800777ca  lea     rax, [rbp+var_78]
0x1800777ce  mov     [rsp+140h+var_100], rax; __int64
0x1800777d3  lea     rax, [rbp+var_30]
0x1800777d7  mov     [rsp+140h+var_108], rax; __int64
0x1800777dc  lea     rax, [rbp+var_78+4]
0x1800777e0  mov     [rsp+140h+var_110], rax; __int64
0x1800777e5  lea     rax, [rbp+var_28]
0x1800777e9  mov     [rsp+140h+var_118], rax; __int64
0x1800777ee  lea     rax, [rbp+var_20]
0x1800777f2  mov     [rsp+140h+var_120], rax; __int64
0x1800777f7  mov     [rbp+var_28], 1000000h
0x1800777ff  mov     [rbp+var_20], 0
0x180077807  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007780c  jmp     short loc_180077880
0x18007780e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180077813  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180077818  mov     rdi, rax
0x18007781b  mov     ecx, [rax]
0x18007781d  cmp     ecx, 5
0x180077820  jbe     short loc_180077880
0x180077822  mov     edx, 1
0x180077827  mov     rcx, rax
0x18007782a  call    _tlgKeywordOn
0x18007782f  test    al, al
0x180077831  jz      short loc_180077880
0x180077833  call    cs:__imp_GetCurrentThreadId
0x180077839  mov     r8, [rbx+110h]
0x180077840  lea     rdx, byte_1800B4773
0x180077847  mov     dword ptr [rbp+arg_0], eax
0x18007784a  mov     rcx, rdi
0x18007784d  mov     eax, [r8+48h]
0x180077851  add     r8, 8
0x180077855  mov     dword ptr [rbp+arg_8], eax
0x180077858  lea     rax, [rbp+arg_0]
0x18007785c  mov     [rsp+140h+var_110], rax
0x180077861  lea     rax, [rbp+arg_8]
0x180077865  mov     [rsp+140h+var_118], rax
0x18007786a  lea     rax, [rbp+arg_10]
0x18007786e  mov     [rsp+140h+var_120], rax
0x180077873  mov     [rbp+arg_10], 0
0x18007787b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180077880  mov     rcx, rbx
0x180077883  add     rsp, 130h
0x18007788a  pop     rdi
0x18007788b  pop     rbx
0x18007788c  pop     rbp
0x18007788d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
