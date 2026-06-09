# CRDPCodecCache::InsertCache(RDP_BITMAP_INFO const *,RDP_COMPRESSION_PARAMETERS const *,uchar const *,uint,int)

- ea: `0x18008224c`
- end: `0x18008249a`
- name: `?InsertCache@CRDPCodecCache@@IEAAJPEBURDP_BITMAP_INFO@@PEBURDP_COMPRESSION_PARAMETERS@@PEBEIH@Z`
- size: `590`
- prototype: `int(CRDPCodecCache *__hidden this, const struct RDP_BITMAP_INFO *, const struct RDP_COMPRESSION_PARAMETERS *, const unsigned __int8 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180080ff0`
- `0x180081520`

## callees

- `0x18000116c`
- `0x18000cdac`
- `0x180076090`
- `0x1800813cc`
- `0x180081930`
- `0x18008224c`
- `0x18019b31c`

## import_xrefs

- `RDPBASE!?SetCacheEntry@CRDPCache@@UEAAJIIPEAUIUnknown@@PEAI@Z` at `0x180082413`
- `RDPBASE!?SetCacheEntry@CRDPCache@@UEAAJIIPEAUIUnknown@@PEAI@Z` at `0x180082413`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800822c9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008231d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008243e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800822c9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008231d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008243e`

## string_xrefs

- `0x18008237e`: `onecore\termsrv\rdpplatform\codecs\cachedcodecs\rdpcodeccache.cpp`
- `0x1800822d4`: `FAILED to createObjectPool`
- `0x180082365`: `InsertCache`
- `0x180082390`: `Data size is too large to cache, skipping`
- `0x180082449`: `Failed to cache bitmap`

## pseudocode

```c
__int64 __fastcall CRDPCodecCache::InsertCache(
        CRDPCodecCache *this,
        const struct RDP_BITMAP_INFO *a2,
        const struct RDP_COMPRESSION_PARAMETERS *a3,
        const unsigned __int8 *a4,
        size_t Size,
        int a6)
{
  _QWORD *v6; // rbx
  bool v7; // zf
  __int64 v12; // rdx
  int PooledObject; // edi
  int ActivityIdPrefix; // eax
  int v15; // edx
  const char *v16; // rcx
  __int64 v17; // rdx
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rbx
  size_t v21; // rcx
  __int64 v22; // rdx
  int v24; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-2Ch] BYREF
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  const char *v27; // [rsp+60h] [rbp-20h] BYREF
  const char *v28; // [rsp+68h] [rbp-18h] BYREF
  const char *v29; // [rsp+70h] [rbp-10h] BYREF
  int v30; // [rsp+B0h] [rbp+30h] BYREF

  v6 = (_QWORD *)((char *)this + 264);
  v25 = 0;
  v7 = *((_QWORD *)this + 33) == 0;
  v26 = 0;
  if ( v7
    && (PooledObject = CTSObjectPool<CRDPCacheBuffer>::CreateInstance(this, a2, (char *)this + 264), PooledObject < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12);
      v15 = 23;
      v16 = "FAILED to createObjectPool";
LABEL_24:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)WPP_3bc4f7a008033dad978d3452ef221b55_Traceguids,
        ActivityIdPrefix,
        (__int64)v16,
        PooledObject);
    }
  }
  else
  {
    PooledObject = CTSObjectPool<CRDPCacheBuffer>::GetPooledObject(*v6, &v26);
    if ( PooledObject >= 0 )
    {
      v20 = v26;
      if ( !v26 )
        goto LABEL_25;
      if ( a6 )
      {
        v21 = (unsigned int)Size;
        if ( (unsigned int)Size > 0x10000 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v30 = 431;
            v27 = "InsertCache";
            v24 = -2147467259;
            v28 = "onecore\\termsrv\\rdpplatform\\codecs\\cachedcodecs\\rdpcodeccache.cpp";
            v29 = "Data size is too large to cache, skipping";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              Size,
              (unsigned int)&word_1802748CE,
              v18,
              v19,
              (__int64)&v29,
              (__int64)&v24,
              (__int64)&v28,
              (__int64)&v30,
              (__int64)&v27);
          }
          goto LABEL_25;
        }
        *(_DWORD *)(v26 + 112) = 1;
        *(_DWORD *)(v20 + 116) = v21;
        *(_DWORD *)(v20 + 108) = *((_DWORD *)a2 + 4);
        memcpy_0((void *)(v20 + 120), a4, v21);
      }
      else
      {
        *(_DWORD *)(v26 + 112) = 0;
      }
      PooledObject = CRDPCache::SetCacheEntry(
                       (CRDPCodecCache *)((char *)this + 112),
                       *((_DWORD *)a3 + 1),
                       *((_DWORD *)a3 + 2),
                       (struct IUnknown *)v20,
                       &v25);
      if ( PooledObject < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v22);
        v15 = 25;
        v16 = "Failed to cache bitmap";
        goto LABEL_24;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v17);
      v15 = 24;
      v16 = "Failed to get pooled buffer";
      goto LABEL_24;
    }
  }
LABEL_25:
  TCntPtr<CFakeGfxProvider>::SafeRelease(&v26);
  return (unsigned int)PooledObject;
}

```

## disassembly

```asm
0x18008224c  mov     [rsp-28h+arg_8], rbx
0x180082251  mov     [rsp-28h+arg_10], rsi
0x180082256  push    rbp
0x180082257  push    rdi
0x180082258  push    r13
0x18008225a  push    r14
0x18008225c  push    r15
0x18008225e  mov     rbp, rsp
0x180082261  sub     rsp, 80h
0x180082268  lea     rbx, [rcx+108h]
0x18008226f  mov     [rbp+var_2C], 0
0x180082276  cmp     qword ptr [rbx], 0
0x18008227a  mov     r15, r9
0x18008227d  mov     r14, r8
0x180082280  mov     [rbp+var_28], 0
0x180082288  mov     r13, rdx
0x18008228b  mov     rsi, rcx
0x18008228e  jnz     short loc_1800822E0
0x180082290  mov     r8, rbx
0x180082293  call    ?CreateInstance@?$CTSObjectPool@VCRDPCacheBuffer@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPCacheBuffer>::CreateInstance(uint,uint,CTSObjectPool<CRDPCacheBuffer> * *,int)
0x180082298  mov     edi, eax
0x18008229a  test    eax, eax
0x18008229c  jns     short loc_1800822E0
0x18008229e  mov     rax, cs:WPP_GLOBAL_Control
0x1800822a5  lea     rcx, WPP_GLOBAL_Control
0x1800822ac  cmp     rax, rcx
0x1800822af  jz      loc_180082473
0x1800822b5  test    byte ptr [rax+1Ch], 8
0x1800822b9  jz      loc_180082473
0x1800822bf  cmp     byte ptr [rax+19h], 2
0x1800822c3  jb      loc_180082473
0x1800822c9  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800822cf  mov     edx, 17h
0x1800822d4  lea     rcx, aFailedToCreate_30; "FAILED to createObjectPool"
0x1800822db  jmp     loc_180082450
0x1800822e0  mov     rcx, [rbx]
0x1800822e3  lea     rdx, [rbp+var_28]
0x1800822e7  call    ?GetPooledObject@?$CTSObjectPool@VCRDPCacheBuffer@@@@QEAAJPEAPEAVCRDPCacheBuffer@@H@Z; CTSObjectPool<CRDPCacheBuffer>::GetPooledObject(CRDPCacheBuffer * *,int)
0x1800822ec  mov     edi, eax
0x1800822ee  test    eax, eax
0x1800822f0  jns     short loc_180082334
0x1800822f2  mov     rax, cs:WPP_GLOBAL_Control
0x1800822f9  lea     rcx, WPP_GLOBAL_Control
0x180082300  cmp     rax, rcx
0x180082303  jz      loc_180082473
0x180082309  test    byte ptr [rax+1Ch], 8
0x18008230d  jz      loc_180082473
0x180082313  cmp     byte ptr [rax+19h], 2
0x180082317  jb      loc_180082473
0x18008231d  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180082323  mov     edx, 18h
0x180082328  lea     rcx, aFailedToGetPoo; "Failed to get pooled buffer"
0x18008232f  jmp     loc_180082450
0x180082334  mov     rbx, [rbp+var_28]
0x180082338  test    rbx, rbx
0x18008233b  jz      loc_180082473
0x180082341  cmp     [rbp+arg_28], 0
0x180082345  jz      loc_1800823F4
0x18008234b  mov     ecx, dword ptr [rbp+Size]
0x18008234e  cmp     ecx, 10000h
0x180082354  jbe     short loc_1800823D2
0x180082356  mov     eax, cs:CallbackContext
0x18008235c  cmp     eax, 2
0x18008235f  jbe     loc_180082473
0x180082365  lea     rax, aInsertcache; "InsertCache"
0x18008236c  mov     [rbp+arg_0], 1AFh
0x180082373  mov     [rbp+var_20], rax
0x180082377  lea     rdx, word_1802748CE
0x18008237e  lea     rax, aOnecoreTermsrv_34; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x180082385  mov     [rbp+var_30], 80004005h
0x18008238c  mov     [rbp+var_18], rax
0x180082390  lea     rax, aDataSizeIsTooL; "Data size is too large to cache, skippi"...
0x180082397  mov     [rbp+var_10], rax
0x18008239b  lea     rax, [rbp+var_20]
0x18008239f  mov     [rsp+80h+var_40], rax
0x1800823a4  lea     rax, [rbp+arg_0]
0x1800823a8  mov     [rsp+80h+var_48], rax
0x1800823ad  lea     rax, [rbp+var_18]
0x1800823b1  mov     [rsp+80h+var_50], rax
0x1800823b6  lea     rax, [rbp+var_30]
0x1800823ba  mov     [rsp+80h+var_58], rax
0x1800823bf  lea     rax, [rbp+var_10]
0x1800823c3  mov     [rsp+80h+var_60], rax
0x1800823c8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800823cd  jmp     loc_180082473
0x1800823d2  mov     dword ptr [rbx+70h], 1
0x1800823d9  mov     r8, rcx; Size
0x1800823dc  mov     [rbx+74h], ecx
0x1800823df  mov     rdx, r15; Src
0x1800823e2  mov     eax, [r13+10h]
0x1800823e6  lea     rcx, [rbx+78h]; void *
0x1800823ea  mov     [rbx+6Ch], eax
0x1800823ed  call    memcpy_0
0x1800823f2  jmp     short loc_1800823FB
0x1800823f4  mov     dword ptr [rbx+70h], 0
0x1800823fb  mov     r8d, [r14+8]
0x1800823ff  lea     rax, [rbp+var_2C]
0x180082403  mov     edx, [r14+4]
0x180082407  lea     rcx, [rsi+70h]
0x18008240b  mov     r9, rbx
0x18008240e  mov     [rsp+80h+var_60], rax
0x180082413  call    cs:__imp_?SetCacheEntry@CRDPCache@@UEAAJIIPEAUIUnknown@@PEAI@Z; CRDPCache::SetCacheEntry(uint,uint,IUnknown *,uint *)
0x180082419  mov     edi, eax
0x18008241b  test    eax, eax
0x18008241d  jns     short loc_180082473
0x18008241f  mov     rax, cs:WPP_GLOBAL_Control
0x180082426  lea     rcx, WPP_GLOBAL_Control
0x18008242d  cmp     rax, rcx
0x180082430  jz      short loc_180082473
0x180082432  test    byte ptr [rax+1Ch], 8
0x180082436  jz      short loc_180082473
0x180082438  cmp     byte ptr [rax+19h], 2
0x18008243c  jb      short loc_180082473
0x18008243e  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180082444  mov     edx, 19h
0x180082449  lea     rcx, aFailedToCacheB; "Failed to cache bitmap"
0x180082450  mov     dword ptr [rsp+80h+var_58], edi
0x180082454  lea     r8, WPP_3bc4f7a008033dad978d3452ef221b55_Traceguids
0x18008245b  mov     [rsp+80h+var_60], rcx
0x180082460  mov     r9d, eax
0x180082463  mov     rcx, cs:WPP_GLOBAL_Control
0x18008246a  mov     rcx, [rcx+10h]
0x18008246e  call    WPP_SF_DsD
0x180082473  lea     rcx, [rbp+var_28]
0x180082477  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18008247c  lea     r11, [rsp+80h+var_s0]
0x180082484  mov     eax, edi
0x180082486  mov     rbx, [r11+38h]
0x18008248a  mov     rsi, [r11+40h]
0x18008248e  mov     rsp, r11
0x180082491  pop     r15
0x180082493  pop     r14
0x180082495  pop     r13
0x180082497  pop     rdi
0x180082498  pop     rbp
0x180082499  retn
```
