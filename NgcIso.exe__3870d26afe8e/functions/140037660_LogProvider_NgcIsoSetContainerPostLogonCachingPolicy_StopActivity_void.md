# LogProvider::NgcIsoSetContainerPostLogonCachingPolicy::StopActivity(void)

- ea: `0x140037660`
- end: `0x14003788f`
- name: `?StopActivity@NgcIsoSetContainerPostLogonCachingPolicy@LogProvider@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(LogProvider::NgcIsoSetContainerPostLogonCachingPolicy *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140001008`
- `0x140003124`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x140037660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003782d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003782d`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoSetContainerPostLogonCachingPolicy::StopActivity(
        LogProvider::NgcIsoSetContainerPostLogonCachingPolicy *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v29; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = LogProvider::Provider();
    if ( *(_DWORD *)v7 > 4u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v20 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)word_14008B422,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = LogProvider::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v13 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_14008B585,
        v13 + 8,
        0,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x140037660  push    rbp
0x140037662  push    rbx
0x140037663  push    rdi
0x140037664  lea     rbp, [rsp+10h]
0x140037669  sub     rsp, 130h
0x140037670  mov     rdi, [rcx+110h]
0x140037677  mov     rbx, rcx
0x14003767a  mov     eax, [rdi+48h]
0x14003767d  test    eax, eax
0x14003767f  jns     loc_140037819
0x140037685  add     rdi, 50h ; 'P'
0x140037689  cmp     eax, [rdi+8]
0x14003768c  jnz     loc_140037819
0x140037692  test    rdi, rdi
0x140037695  jz      loc_140037819
0x14003769b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400376a0  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1400376a5  mov     r9, rax
0x1400376a8  mov     ecx, [rax]
0x1400376aa  cmp     ecx, 4
0x1400376ad  jbe     loc_14003787D
0x1400376b3  mov     rax, [rdi+70h]
0x1400376b7  lea     rdx, word_14008B422
0x1400376be  mov     rcx, [rdi+30h]
0x1400376c2  mov     [rbp+var_60], rax
0x1400376c6  mov     eax, [rdi+68h]
0x1400376c9  mov     r8, [rbx+110h]
0x1400376d0  mov     dword ptr [rbp+arg_10], eax
0x1400376d3  add     r8, 8
0x1400376d7  mov     rax, [rdi+60h]
0x1400376db  mov     [rbp+var_58], rax
0x1400376df  mov     rax, [rdi+58h]
0x1400376e3  mov     [rbp+var_50], rax
0x1400376e7  mov     eax, [rdi+50h]
0x1400376ea  mov     [rbp+arg_18], eax
0x1400376ed  mov     rax, [rdi+48h]
0x1400376f1  mov     [rbp+var_48], rax
0x1400376f5  mov     eax, [rdi+20h]
0x1400376f8  mov     [rbp+var_80], eax
0x1400376fb  mov     rax, [rdi+18h]
0x1400376ff  mov     [rbp+var_40], rax
0x140037703  mov     eax, [rdi]
0x140037705  mov     [rbp+var_7C], eax
0x140037708  mov     rax, [rdi+80h]
0x14003770f  mov     [rbp+var_38], rax
0x140037713  mov     eax, [rdi+40h]
0x140037716  mov     [rbp+var_78], eax
0x140037719  mov     rax, [rdi+38h]
0x14003771d  mov     [rbp+var_30], rax
0x140037721  mov     eax, [rdi+8]
0x140037724  mov     [rbp+var_74], eax
0x140037727  lea     rax, [rbp+var_70]
0x14003772b  mov     [rsp+140h+var_90], rax
0x140037733  lea     rax, [rbp+arg_0]
0x140037737  mov     [rsp+140h+var_98], rax
0x14003773f  lea     rax, [rbp+arg_8]
0x140037743  mov     [rsp+140h+var_A0], rax
0x14003774b  lea     rax, [rbp+var_68]
0x14003774f  mov     [rsp+140h+var_A8], rax
0x140037757  lea     rax, [rbp+var_60]
0x14003775b  mov     [rsp+140h+var_B0], rax
0x140037763  lea     rax, [rbp+arg_10]
0x140037767  mov     [rsp+140h+var_B8], rax
0x14003776f  lea     rax, [rbp+var_58]
0x140037773  mov     [rsp+140h+var_C0], rax
0x14003777b  lea     rax, [rbp+var_50]
0x14003777f  mov     [rsp+140h+var_C8], rax
0x140037784  lea     rax, [rbp+arg_18]
0x140037788  mov     [rsp+140h+var_D0], rax
0x14003778d  lea     rax, [rbp+var_48]
0x140037791  mov     [rsp+140h+var_D8], rax
0x140037796  lea     rax, [rbp+var_80]
0x14003779a  mov     [rsp+140h+var_E0], rax
0x14003779f  lea     rax, [rbp+var_40]
0x1400377a3  mov     [rsp+140h+var_E8], rax
0x1400377a8  lea     rax, [rbp+var_7C]
0x1400377ac  mov     [rsp+140h+var_F0], rax
0x1400377b1  lea     rax, [rbp+var_38]
0x1400377b5  mov     [rsp+140h+var_F8], rax
0x1400377ba  lea     rax, [rbp+var_78]
0x1400377be  mov     [rsp+140h+var_100], rax
0x1400377c3  lea     rax, [rbp+var_30]
0x1400377c7  mov     [rsp+140h+var_108], rax
0x1400377cc  lea     rax, [rbp+var_74]
0x1400377d0  mov     [rbp+var_70], rcx
0x1400377d4  mov     ecx, [rdi+44h]
0x1400377d7  mov     [rsp+140h+var_110], rax
0x1400377dc  lea     rax, [rbp+var_28]
0x1400377e0  mov     [rbp+arg_0], ecx
0x1400377e3  mov     ecx, [rdi+10h]
0x1400377e6  mov     [rbp+arg_8], ecx
0x1400377e9  mov     rcx, [rdi+78h]
0x1400377ed  mov     [rsp+140h+var_118], rax
0x1400377f2  lea     rax, [rbp+var_20]
0x1400377f6  mov     [rbp+var_68], rcx
0x1400377fa  mov     rcx, r9
0x1400377fd  mov     [rsp+140h+var_120], rax
0x140037802  mov     [rbp+var_28], 1000000h
0x14003780a  mov     [rbp+var_20], 0
0x140037812  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140037817  jmp     short loc_14003787D
0x140037819  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14003781e  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140037823  mov     rdi, rax
0x140037826  mov     ecx, [rax]
0x140037828  cmp     ecx, 4
0x14003782b  jbe     short loc_14003787D
0x14003782d  call    cs:__imp_GetCurrentThreadId
0x140037833  mov     r8, [rbx+110h]
0x14003783a  lea     rdx, byte_14008B585
0x140037841  mov     [rbp+arg_0], eax
0x140037844  xor     r9d, r9d
0x140037847  lea     rax, [rbp+arg_0]
0x14003784b  mov     [rsp+140h+var_110], rax
0x140037850  lea     rax, [rbp+arg_8]
0x140037854  mov     ecx, [r8+48h]
0x140037858  add     r8, 8
0x14003785c  mov     [rsp+140h+var_118], rax
0x140037861  lea     rax, [rbp+arg_10]
0x140037865  mov     [rbp+arg_8], ecx
0x140037868  mov     rcx, rdi
0x14003786b  mov     [rsp+140h+var_120], rax
0x140037870  mov     [rbp+arg_10], 0
0x140037878  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003787d  mov     rcx, rbx
0x140037880  add     rsp, 130h
0x140037887  pop     rdi
0x140037888  pop     rbx
0x140037889  pop     rbp
0x14003788a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
