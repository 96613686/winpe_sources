# CRDPCodecCache::InitializeSelf(IUnknown *,uint)

- ea: `0x180081fb0`
- end: `0x180082246`
- name: `?InitializeSelf@CRDPCodecCache@@UEAAJPEAUIUnknown@@I@Z`
- size: `662`
- prototype: `__int64 __fastcall(CRDPCodecCache *__hidden this, struct IUnknown *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180082940`
- `0x180082ae0`
- `0x180082c80`

## callees

- `0x18000116c`
- `0x18000f660`
- `0x180076090`
- `0x180081c98`
- `0x180081fb0`

## import_xrefs

- `RDPBASE!?Reset@CRDPCache@@UEAAJI@Z` at `0x180082075`
- `RDPBASE!?Reset@CRDPCache@@UEAAJI@Z` at `0x180082075`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800820ac`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180082121`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800821a2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180082217`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800820ac`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180082121`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800821a2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180082217`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x18008216b`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x1800821ec`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x18008216b`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x1800821ec`

## string_xrefs

- `0x18008200b`: `onecore\termsrv\rdpplatform\codecs\cachedcodecs\rdpcodeccache.cpp`
- `0x1800820b7`: `FAILED to initialize cache`
- `0x180082144`: `RDV::RDP::Codecs::CacheCallsPerSec`
- `0x1800821c8`: `RDV::RDP::Codecs::CacheHitsPerSec`

## pseudocode

```c
__int64 __fastcall CRDPCodecCache::InitializeSelf(CRDPCodecCache *this, struct IUnknown *a2, unsigned int a3)
{
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int LongCounter; // ebx
  __int64 v9; // rdx
  int ActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  const char *v17; // [rsp+50h] [rbp-28h] BYREF
  const char *v18; // [rsp+58h] [rbp-20h] BYREF
  const char *v19; // [rsp+60h] [rbp-18h] BYREF
  int v20; // [rsp+80h] [rbp+8h] BYREF
  int v21; // [rsp+98h] [rbp+20h] BYREF

  if ( !(unsigned int)CTSCriticalSection::Initialize((CRDPCodecCache *)((char *)this + 240)) )
  {
    LongCounter = -2147467259;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v20 = 118;
      v17 = "InitializeSelf";
      v21 = -2147467259;
      v18 = "onecore\\termsrv\\rdpplatform\\codecs\\cachedcodecs\\rdpcodeccache.cpp";
      v19 = "Failed to initialize codec lock";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)word_1802749E2,
        v6,
        v7,
        (__int64)&v19,
        (__int64)&v21,
        (__int64)&v18,
        (__int64)&v20,
        (__int64)&v17);
    }
    return (unsigned int)LongCounter;
  }
  LongCounter = CRDPCache::Reset((CRDPCodecCache *)((char *)this + 112), 0x300u);
  if ( LongCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LongCounter;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v9);
    v11 = 19;
    v12 = "FAILED to initialize cache";
    goto LABEL_9;
  }
  LongCounter = CRDPCodecCache::InitializeCodecs(this, a3);
  if ( LongCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LongCounter;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v13);
    v11 = 20;
    v12 = "Failed to initialize codecs";
    goto LABEL_9;
  }
  LongCounter = RDPAPI_GetLongCounter(
                  L"RDV::RDP::Codecs::CacheCallsPerSec",
                  0xFFFFFFFFLL,
                  0xFFFFFFFFLL,
                  0xFFFFFFFFLL,
                  -2147483645,
                  1000,
                  1000,
                  (char *)this + 288);
  if ( LongCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LongCounter;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v14);
    v11 = 21;
    v12 = "Failed to get call counter";
LABEL_9:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_3bc4f7a008033dad978d3452ef221b55_Traceguids,
      ActivityIdPrefix,
      (__int64)v12,
      LongCounter);
    return (unsigned int)LongCounter;
  }
  LongCounter = RDPAPI_GetLongCounter(
                  L"RDV::RDP::Codecs::CacheHitsPerSec",
                  0xFFFFFFFFLL,
                  0xFFFFFFFFLL,
                  0xFFFFFFFFLL,
                  -2147483645,
                  1000,
                  1000,
                  (char *)this + 296);
  if ( LongCounter >= 0 )
  {
    *((_DWORD *)this + 7) |= 2u;
    return (unsigned int)LongCounter;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v15);
    v11 = 22;
    v12 = "Failed to get hit counter";
    goto LABEL_9;
  }
  return (unsigned int)LongCounter;
}

```

## disassembly

```asm
0x180081fb0  mov     [rsp+arg_8], rbx
0x180081fb5  mov     [rsp+arg_10], rsi
0x180081fba  push    rdi
0x180081fbb  sub     rsp, 70h
0x180081fbf  mov     rdi, rcx
0x180081fc2  mov     esi, r8d
0x180081fc5  add     rcx, 0F0h; this
0x180081fcc  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x180081fd1  test    eax, eax
0x180081fd3  jnz     loc_18008206C
0x180081fd9  mov     eax, cs:CallbackContext
0x180081fdf  mov     ebx, 80004005h
0x180081fe4  cmp     eax, 2
0x180081fe7  jbe     loc_180082232
0x180081fed  lea     rax, aInitializeself; "InitializeSelf"
0x180081ff4  mov     [rsp+78h+arg_0], 76h ; 'v'
0x180081fff  mov     [rsp+78h+var_28], rax
0x180082004  lea     rdx, word_1802749E2
0x18008200b  lea     rax, aOnecoreTermsrv_34; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x180082012  mov     [rsp+78h+arg_18], ebx
0x180082019  mov     [rsp+78h+var_20], rax
0x18008201e  lea     rax, aFailedToInitia_78; "Failed to initialize codec lock"
0x180082025  mov     [rsp+78h+var_18], rax
0x18008202a  lea     rax, [rsp+78h+var_28]
0x18008202f  mov     [rsp+78h+var_38], rax
0x180082034  lea     rax, [rsp+78h+arg_0]
0x18008203c  mov     [rsp+78h+var_40], rax
0x180082041  lea     rax, [rsp+78h+var_20]
0x180082046  mov     [rsp+78h+var_48], rax
0x18008204b  lea     rax, [rsp+78h+arg_18]
0x180082053  mov     [rsp+78h+var_50], rax
0x180082058  lea     rax, [rsp+78h+var_18]
0x18008205d  mov     [rsp+78h+var_58], rax
0x180082062  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180082067  jmp     loc_180082232
0x18008206c  lea     rcx, [rdi+70h]
0x180082070  mov     edx, 300h
0x180082075  call    cs:__imp_?Reset@CRDPCache@@UEAAJI@Z; CRDPCache::Reset(uint)
0x18008207b  mov     ebx, eax
0x18008207d  test    eax, eax
0x18008207f  jns     short loc_1800820E6
0x180082081  mov     rcx, cs:WPP_GLOBAL_Control
0x180082088  lea     rax, WPP_GLOBAL_Control
0x18008208f  cmp     rcx, rax
0x180082092  jz      loc_180082232
0x180082098  test    byte ptr [rcx+1Ch], 8
0x18008209c  jz      loc_180082232
0x1800820a2  cmp     byte ptr [rcx+19h], 2
0x1800820a6  jb      loc_180082232
0x1800820ac  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800820b2  mov     edx, 13h
0x1800820b7  lea     rcx, aFailedToInitia_61; "FAILED to initialize cache"
0x1800820be  mov     dword ptr [rsp+78h+var_50], ebx
0x1800820c2  lea     r8, WPP_3bc4f7a008033dad978d3452ef221b55_Traceguids
0x1800820c9  mov     [rsp+78h+var_58], rcx
0x1800820ce  mov     r9d, eax
0x1800820d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800820d8  mov     rcx, [rcx+10h]
0x1800820dc  call    WPP_SF_DsD
0x1800820e1  jmp     loc_180082232
0x1800820e6  mov     edx, esi; unsigned int
0x1800820e8  mov     rcx, rdi; this
0x1800820eb  call    ?InitializeCodecs@CRDPCodecCache@@IEAAJI@Z; CRDPCodecCache::InitializeCodecs(uint)
0x1800820f0  mov     ebx, eax
0x1800820f2  test    eax, eax
0x1800820f4  jns     short loc_180082135
0x1800820f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800820fd  lea     rax, WPP_GLOBAL_Control
0x180082104  cmp     rcx, rax
0x180082107  jz      loc_180082232
0x18008210d  test    byte ptr [rcx+1Ch], 8
0x180082111  jz      loc_180082232
0x180082117  cmp     byte ptr [rcx+19h], 2
0x18008211b  jb      loc_180082232
0x180082121  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180082127  mov     edx, 14h
0x18008212c  lea     rcx, aFailedToInitia_67; "Failed to initialize codecs"
0x180082133  jmp     short loc_1800820BE
0x180082135  or      esi, 0FFFFFFFFh
0x180082138  lea     rax, [rdi+120h]
0x18008213f  mov     [rsp+78h+var_40], rax
0x180082144  lea     rcx, aRdvRdpCodecsCa_0; "RDV::RDP::Codecs::CacheCallsPerSec"
0x18008214b  mov     dword ptr [rsp+78h+var_48], 3E8h
0x180082153  mov     r9d, esi
0x180082156  mov     dword ptr [rsp+78h+var_50], 3E8h
0x18008215e  mov     r8d, esi
0x180082161  mov     edx, esi
0x180082163  mov     dword ptr [rsp+78h+var_58], 80000003h
0x18008216b  call    cs:__imp_RDPAPI_GetLongCounter
0x180082171  mov     ebx, eax
0x180082173  test    eax, eax
0x180082175  jns     short loc_1800821B9
0x180082177  mov     rcx, cs:WPP_GLOBAL_Control
0x18008217e  lea     rax, WPP_GLOBAL_Control
0x180082185  cmp     rcx, rax
0x180082188  jz      loc_180082232
0x18008218e  test    byte ptr [rcx+1Ch], 8
0x180082192  jz      loc_180082232
0x180082198  cmp     byte ptr [rcx+19h], 2
0x18008219c  jb      loc_180082232
0x1800821a2  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800821a8  mov     edx, 15h
0x1800821ad  lea     rcx, aFailedToGetCal; "Failed to get call counter"
0x1800821b4  jmp     loc_1800820BE
0x1800821b9  lea     rax, [rdi+128h]
0x1800821c0  mov     r9d, esi
0x1800821c3  mov     [rsp+78h+var_40], rax
0x1800821c8  lea     rcx, aRdvRdpCodecsCa; "RDV::RDP::Codecs::CacheHitsPerSec"
0x1800821cf  mov     dword ptr [rsp+78h+var_48], 3E8h
0x1800821d7  mov     r8d, esi
0x1800821da  mov     dword ptr [rsp+78h+var_50], 3E8h
0x1800821e2  mov     edx, esi
0x1800821e4  mov     dword ptr [rsp+78h+var_58], 80000003h
0x1800821ec  call    cs:__imp_RDPAPI_GetLongCounter
0x1800821f2  mov     ebx, eax
0x1800821f4  test    eax, eax
0x1800821f6  jns     short loc_18008222E
0x1800821f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800821ff  lea     rax, WPP_GLOBAL_Control
0x180082206  cmp     rcx, rax
0x180082209  jz      short loc_180082232
0x18008220b  test    byte ptr [rcx+1Ch], 8
0x18008220f  jz      short loc_180082232
0x180082211  cmp     byte ptr [rcx+19h], 2
0x180082215  jb      short loc_180082232
0x180082217  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008221d  mov     edx, 16h
0x180082222  lea     rcx, aFailedToGetHit; "Failed to get hit counter"
0x180082229  jmp     loc_1800820BE
0x18008222e  or      dword ptr [rdi+1Ch], 2
0x180082232  lea     r11, [rsp+78h+var_8]
0x180082237  mov     eax, ebx
0x180082239  mov     rbx, [r11+18h]
0x18008223d  mov     rsi, [r11+20h]
0x180082241  mov     rsp, r11
0x180082244  pop     rdi
0x180082245  retn
```
