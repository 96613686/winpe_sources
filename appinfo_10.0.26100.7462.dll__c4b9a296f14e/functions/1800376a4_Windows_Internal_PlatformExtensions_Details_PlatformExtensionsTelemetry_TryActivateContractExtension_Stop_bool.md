# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)

- ea: `0x1800376a4`
- end: `0x18003794b`
- name: `?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z`
- size: `679`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this, bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180038aa0`

## callees

- `0x180002ec0`
- `0x18000329c`
- `0x18000cb30`
- `0x180010c48`
- `0x180018d70`
- `0x180035a98`
- `0x1800376a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800378bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800378bc`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this,
        char a2,
        char a3,
        const unsigned __int16 *a4)
{
  int *v4; // rax
  int v9; // ecx
  int *v10; // rdi
  const struct _tlgProvider_t *v11; // rcx
  int v12; // ecx
  int v13; // r9d
  __int64 v14; // r8
  __int64 v15; // rax
  const struct _tlgProvider_t *v16; // rax
  int v17; // edi
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  int v20; // eax
  int v21; // r9d
  _BYTE v22[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v23; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v24; // [rsp+C8h] [rbp-78h] BYREF
  int v25; // [rsp+CCh] [rbp-74h] BYREF
  int v26; // [rsp+D0h] [rbp-70h] BYREF
  int v27; // [rsp+D4h] [rbp-6Ch] BYREF
  int v28; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v30; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v31; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v33; // [rsp+100h] [rbp-40h] BYREF
  __int64 v34; // [rsp+108h] [rbp-38h] BYREF
  __int64 v35; // [rsp+110h] [rbp-30h] BYREF
  __int64 v36; // [rsp+118h] [rbp-28h] BYREF
  __int64 v37; // [rsp+120h] [rbp-20h] BYREF
  __int64 v38; // [rsp+128h] [rbp-18h] BYREF
  __int64 v39; // [rsp+130h] [rbp-10h] BYREF
  char v40; // [rsp+160h] [rbp+20h] BYREF

  v4 = (int *)*((_QWORD *)this + 34);
  v9 = v4[18];
  if ( v9 >= 0 || v9 != v4[22] || (v10 = v4 + 20, v4 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v16 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v17 = (int)v16;
    if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL) )
    {
      v30 = a4;
      v40 = a3;
      v22[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      v24 = CurrentThreadId;
      v20 = *(_DWORD *)(v19 + 72);
      v29 = 0;
      v23 = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)&unk_18005268D,
        v19 + 8,
        v21,
        (__int64)&v29,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)v22,
        (__int64)&v40,
        (__int64)&v30);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v32 = *((_QWORD *)v10 + 15);
      v33 = *((_QWORD *)v10 + 14);
      v14 = *((_QWORD *)this + 34);
      v25 = v10[26];
      v15 = *((_QWORD *)v10 + 12);
      v30 = 0;
      v34 = v15;
      v35 = *((_QWORD *)v10 + 11);
      v26 = v10[20];
      v36 = *((_QWORD *)v10 + 9);
      v27 = v10[8];
      v37 = *((_QWORD *)v10 + 3);
      v28 = *v10;
      v38 = *((_QWORD *)v10 + 16);
      v23 = v10[16];
      v39 = *((_QWORD *)v10 + 7);
      v24 = v10[2];
      v31 = a4;
      v40 = a3;
      v22[0] = a2;
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)&unk_18005344E,
        v14 + 8,
        v13,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v24,
        (__int64)&v39,
        (__int64)&v23,
        (__int64)&v38,
        (__int64)&v28,
        (__int64)&v37,
        (__int64)&v27,
        (__int64)&v36,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v25,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)v22,
        (__int64)&v40,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800376a4  mov     [rsp-18h+arg_8], rbx
0x1800376a9  mov     [rsp-18h+arg_10], rsi
0x1800376ae  mov     [rsp-18h+arg_18], rdi
0x1800376b3  push    rbp
0x1800376b4  push    r14
0x1800376b6  push    r15
0x1800376b8  mov     rbp, rsp
0x1800376bb  sub     rsp, 140h
0x1800376c2  mov     rax, [rcx+110h]
0x1800376c9  mov     rbx, rcx
0x1800376cc  mov     rsi, r9
0x1800376cf  mov     r14b, r8b
0x1800376d2  mov     r15b, dl
0x1800376d5  mov     ecx, [rax+48h]
0x1800376d8  test    ecx, ecx
0x1800376da  jns     loc_180037881
0x1800376e0  cmp     ecx, [rax+58h]
0x1800376e3  jnz     loc_180037881
0x1800376e9  lea     rdi, [rax+50h]
0x1800376ed  test    rdi, rdi
0x1800376f0  jz      loc_180037881
0x1800376f6  mov     rcx, rbx
0x1800376f9  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800376fe  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180037703  mov     rcx, rax
0x180037706  cmp     dword ptr [rax], 5
0x180037709  jbe     loc_180037927
0x18003770f  mov     rdx, 400000000000h
0x180037719  call    _tlgKeywordOn
0x18003771e  test    al, al
0x180037720  jz      loc_180037927
0x180037726  mov     rax, [rdi+78h]
0x18003772a  lea     rdx, unk_18005344E
0x180037731  mov     [rbp+var_48], rax
0x180037735  mov     rax, [rdi+70h]
0x180037739  mov     [rbp+var_40], rax
0x18003773d  mov     eax, [rdi+68h]
0x180037740  mov     r8, [rbx+110h]
0x180037747  mov     [rbp+var_74], eax
0x18003774a  add     r8, 8
0x18003774e  mov     rax, [rdi+60h]
0x180037752  and     [rbp+var_58], 0
0x180037757  mov     [rbp+var_38], rax
0x18003775b  mov     rax, [rdi+58h]
0x18003775f  mov     [rbp+var_30], rax
0x180037763  mov     eax, [rdi+50h]
0x180037766  mov     [rbp+var_70], eax
0x180037769  mov     rax, [rdi+48h]
0x18003776d  mov     [rbp+var_28], rax
0x180037771  mov     eax, [rdi+20h]
0x180037774  mov     [rbp+var_6C], eax
0x180037777  mov     rax, [rdi+18h]
0x18003777b  mov     [rbp+var_20], rax
0x18003777f  mov     eax, [rdi]
0x180037781  mov     [rbp+var_68], eax
0x180037784  mov     rax, [rdi+80h]
0x18003778b  mov     [rbp+var_18], rax
0x18003778f  mov     eax, [rdi+40h]
0x180037792  mov     [rbp+var_7C], eax
0x180037795  mov     rax, [rdi+38h]
0x180037799  mov     [rbp+var_10], rax
0x18003779d  mov     eax, [rdi+8]
0x1800377a0  mov     [rbp+var_78], eax
0x1800377a3  lea     rax, [rbp+var_50]
0x1800377a7  mov     [rsp+140h+var_90], rax
0x1800377af  lea     rax, [rbp+arg_0]
0x1800377b3  mov     [rsp+140h+var_98], rax
0x1800377bb  lea     rax, [rbp+var_80]
0x1800377bf  mov     [rsp+140h+var_A0], rax
0x1800377c7  lea     rax, [rbp+var_48]
0x1800377cb  mov     [rsp+140h+var_A8], rax
0x1800377d3  lea     rax, [rbp+var_40]
0x1800377d7  mov     [rsp+140h+var_B0], rax
0x1800377df  lea     rax, [rbp+var_74]
0x1800377e3  mov     [rsp+140h+var_B8], rax
0x1800377eb  lea     rax, [rbp+var_38]
0x1800377ef  mov     [rsp+140h+var_C0], rax
0x1800377f7  lea     rax, [rbp+var_30]
0x1800377fb  mov     [rsp+140h+var_C8], rax
0x180037800  lea     rax, [rbp+var_70]
0x180037804  mov     [rsp+140h+var_D0], rax
0x180037809  lea     rax, [rbp+var_28]
0x18003780d  mov     [rsp+140h+var_D8], rax
0x180037812  lea     rax, [rbp+var_6C]
0x180037816  mov     [rsp+140h+var_E0], rax
0x18003781b  lea     rax, [rbp+var_20]
0x18003781f  mov     [rsp+140h+var_E8], rax
0x180037824  lea     rax, [rbp+var_68]
0x180037828  mov     [rsp+140h+var_F0], rax
0x18003782d  lea     rax, [rbp+var_18]
0x180037831  mov     [rsp+140h+var_F8], rax
0x180037836  lea     rax, [rbp+var_7C]
0x18003783a  mov     [rsp+140h+var_100], rax
0x18003783f  lea     rax, [rbp+var_10]
0x180037843  mov     [rsp+140h+var_108], rax
0x180037848  lea     rax, [rbp+var_78]
0x18003784c  mov     [rsp+140h+var_110], rax
0x180037851  lea     rax, [rbp+var_60]
0x180037855  mov     [rsp+140h+var_118], rax
0x18003785a  lea     rax, [rbp+var_58]
0x18003785e  mov     [rsp+140h+var_120], rax
0x180037863  mov     [rbp+var_50], rsi
0x180037867  mov     [rbp+arg_0], r14b
0x18003786b  mov     [rbp+var_80], r15b
0x18003786f  mov     [rbp+var_60], 1000000h
0x180037877  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U5@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@76@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18003787c  jmp     loc_180037927
0x180037881  mov     rcx, rbx
0x180037884  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037889  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003788e  mov     rdi, rax
0x180037891  cmp     dword ptr [rax], 5
0x180037894  jbe     loc_180037927
0x18003789a  mov     rdx, 400000000000h
0x1800378a4  mov     rcx, rax
0x1800378a7  call    _tlgKeywordOn
0x1800378ac  test    al, al
0x1800378ae  jz      short loc_180037927
0x1800378b0  mov     [rbp+var_58], rsi
0x1800378b4  mov     [rbp+arg_0], r14b
0x1800378b8  mov     [rbp+var_80], r15b
0x1800378bc  call    cs:__imp_GetCurrentThreadId
0x1800378c3  nop     dword ptr [rax+rax+00h]
0x1800378c8  mov     r8, [rbx+110h]
0x1800378cf  lea     rdx, unk_18005268D
0x1800378d6  mov     [rbp+var_78], eax
0x1800378d9  mov     rcx, rdi
0x1800378dc  mov     eax, [r8+48h]
0x1800378e0  add     r8, 8
0x1800378e4  and     [rbp+var_60], 0
0x1800378e9  mov     [rbp+var_7C], eax
0x1800378ec  lea     rax, [rbp+var_58]
0x1800378f0  mov     [rsp+140h+var_F8], rax
0x1800378f5  lea     rax, [rbp+arg_0]
0x1800378f9  mov     [rsp+140h+var_100], rax
0x1800378fe  lea     rax, [rbp+var_80]
0x180037902  mov     [rsp+140h+var_108], rax
0x180037907  lea     rax, [rbp+var_78]
0x18003790b  mov     [rsp+140h+var_110], rax
0x180037910  lea     rax, [rbp+var_7C]
0x180037914  mov     [rsp+140h+var_118], rax
0x180037919  lea     rax, [rbp+var_60]
0x18003791d  mov     [rsp+140h+var_120], rax
0x180037922  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U3@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@5AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180037927  mov     rcx, rbx
0x18003792a  lea     r11, [rsp+140h+var_s0]
0x180037932  mov     rbx, [r11+28h]
0x180037936  mov     rsi, [r11+30h]
0x18003793a  mov     rdi, [r11+38h]
0x18003793e  mov     rsp, r11
0x180037941  pop     r15
0x180037943  pop     r14
0x180037945  pop     rbp
0x180037946  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
