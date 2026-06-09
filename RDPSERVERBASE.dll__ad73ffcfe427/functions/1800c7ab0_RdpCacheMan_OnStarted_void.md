# RdpCacheMan::OnStarted(void)

- ea: `0x1800c7ab0`
- end: `0x1800c7db4`
- name: `?OnStarted@RdpCacheMan@@UEAAJXZ`
- size: `772`
- prototype: `__int64 __fastcall(RdpCacheMan *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000ce04`
- `0x180079724`
- `0x180079770`
- `0x1800c5c04`
- `0x1800c5cb4`
- `0x1800c7ab0`
- `0x1800c81b8`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!?CreateInstance@Evict@@SAJKKKKKPEAPEAV1@@Z` at `0x1800c7c28`
- `RDPBASE!?CreateInstance@Evict@@SAJKKKKKPEAPEAV1@@Z` at `0x1800c7c28`
- `RDPBASE!?CreateInstance@HashTable@@SAJKKPEAPEAUIHashBucket@@@Z` at `0x1800c7be6`
- `RDPBASE!?CreateInstance@HashTable@@SAJKKPEAPEAUIHashBucket@@@Z` at `0x1800c7be6`

## string_xrefs

- `0x1800c7b51`: `IID_IRdpCacheMan`
- `0x1800c7c45`: `IID_IRdpCacheMan`
- `0x1800c7d36`: `IID_IRdpCacheMan`
- `0x1800c7b44`: `RdpCacheManError_OnStartedGetClientModeFail`
- `0x1800c7bf3`: `RdpCacheManError_OnStartedHashTableCreateInstanceFail`
- `0x1800c7d29`: `RdpCacheManError_OnStartedBadCachingMethod`
- `0x1800c7c38`: `RdpCacheManError_OnStartedEvictCreateInstanceFail`

## pseudocode

```c
__int64 __fastcall RdpCacheMan::OnStarted(RdpCacheMan *this)
{
  struct IUnknown *v1; // rdx
  __int64 v3; // rcx
  signed int v4; // eax
  signed int Instance; // r13d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  char *v9; // rdx
  __int64 v10; // r8
  signed int v11; // eax
  int v12; // ebx
  int v13; // edi
  int v14; // esi
  int v15; // r14d
  int v16; // r15d
  int v17; // r12d
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  int v22; // [rsp+20h] [rbp-60h]
  int v23; // [rsp+20h] [rbp-60h]
  _DWORD v24[4]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v25[16]; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v26; // [rsp+70h] [rbp-10h]
  int v27; // [rsp+C0h] [rbp+40h] BYREF
  int v28; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v29; // [rsp+D0h] [rbp+50h] BYREF

  v1 = (struct IUnknown *)*((_QWORD *)this + 1);
  v27 = 0;
  v29 = 0;
  v28 = 0;
  CacheSettings::CacheSettings((CacheSettings *)v25, v1);
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 1))(
         *((_QWORD *)this + 1),
         &IID_IRDPENCPlatformContext,
         &v29) >= 0 )
    (*(void (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v29 + 32LL))(
      v29,
      L"GfxPipeline::ForceLyncMCUProfile",
      &v28);
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v3 + 88LL))(v3, &v27);
    Instance = v4;
    if ( v4 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
        "RdpCacheManError_OnStartedGetClientModeFail",
        (char *)0x2ED,
        v4,
        v22);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 49;
LABEL_26:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
          CurrentThreadActivityIdPrefix,
          Instance);
        goto LABEL_27;
      }
      goto LABEL_27;
    }
  }
  CacheDatabaseSettings::CacheDatabaseSettings((CacheDatabaseSettings *)v24, v28, v27 != 0);
  v8 = v24[1] / v24[0];
  *((_DWORD *)this + 32) = v24[0];
  *((_DWORD *)this + 33) = v8;
  *((_DWORD *)this + 34) = v8;
  if ( *((_DWORD *)this + 16) )
  {
    Instance = -2147024809;
    v9 = "RdpCacheManError_OnStartedBadCachingMethod";
    v10 = 776;
    goto LABEL_22;
  }
  Instance = HashTable::CreateInstance(4u, v8, (struct IHashBucket **)this + 10);
  if ( Instance < 0 )
  {
    v9 = "RdpCacheManError_OnStartedHashTableCreateInstanceFail";
    v10 = 771;
LABEL_22:
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      v9,
      (char *)v10,
      Instance,
      v22);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 50;
      goto LABEL_26;
    }
    goto LABEL_27;
  }
  v11 = Evict::CreateInstance(
          v26,
          *((_DWORD *)this + 33),
          *((_DWORD *)this + 33),
          0x400u,
          0x400u,
          (struct Evict **)this + 11);
  Instance = v11;
  if ( v11 >= 0 )
  {
    Instance = 0;
    *((_DWORD *)this + 43) = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v12 = *((_DWORD *)this + 32);
      v13 = *((_DWORD *)this + 33);
      v14 = *((_DWORD *)this + 16);
      v15 = *((_DWORD *)this + 15);
      v16 = *((unsigned __int16 *)this + 29);
      v17 = *((unsigned __int16 *)this + 28);
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DDDDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, v18, v17, v16, v15, v14, v13, v12);
    }
  }
  else
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_OnStartedEvictCreateInstanceFail",
      (char *)0x316,
      v11,
      v23);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 51;
      goto LABEL_26;
    }
  }
LABEL_27:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v29);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800c7ab0  mov     [rsp-38h+arg_18], rbx
0x1800c7ab5  push    rbp
0x1800c7ab6  push    rsi
0x1800c7ab7  push    rdi
0x1800c7ab8  push    r12
0x1800c7aba  push    r13
0x1800c7abc  push    r14
0x1800c7abe  push    r15
0x1800c7ac0  mov     rbp, rsp
0x1800c7ac3  sub     rsp, 80h
0x1800c7aca  mov     rdx, [rcx+8]; struct IUnknown *
0x1800c7ace  xor     ebx, ebx
0x1800c7ad0  mov     r12, rcx
0x1800c7ad3  mov     [rbp+arg_0], ebx
0x1800c7ad6  lea     rcx, [rbp+var_20]; this
0x1800c7ada  mov     [rbp+arg_10], rbx
0x1800c7ade  mov     [rbp+arg_8], ebx
0x1800c7ae1  call    ??0CacheSettings@@QEAA@PEAUIUnknown@@@Z; CacheSettings::CacheSettings(IUnknown *)
0x1800c7ae6  mov     rcx, [r12+8]
0x1800c7aeb  lea     r8, [rbp+arg_10]
0x1800c7aef  lea     rdx, IID_IRDPENCPlatformContext
0x1800c7af6  mov     rax, [rcx]
0x1800c7af9  mov     rax, [rax]
0x1800c7afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7b01  test    eax, eax
0x1800c7b03  js      short loc_1800C7B20
0x1800c7b05  mov     rcx, [rbp+arg_10]
0x1800c7b09  lea     r8, [rbp+arg_8]
0x1800c7b0d  lea     rdx, aGfxpipelineFor_1; "GfxPipeline::ForceLyncMCUProfile"
0x1800c7b14  mov     rax, [rcx]
0x1800c7b17  mov     rax, [rax+20h]
0x1800c7b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7b20  mov     rcx, [r12+70h]
0x1800c7b25  test    rcx, rcx
0x1800c7b28  jz      short loc_1800C7B97
0x1800c7b2a  mov     rax, [rcx]
0x1800c7b2d  lea     rdx, [rbp+arg_0]
0x1800c7b31  mov     rax, [rax+58h]
0x1800c7b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7b3a  mov     r13d, eax
0x1800c7b3d  test    eax, eax
0x1800c7b3f  jns     short loc_1800C7B97
0x1800c7b41  mov     r9d, eax; unsigned int
0x1800c7b44  lea     rdx, aRdpcachemanerr_13; "RdpCacheManError_OnStartedGetClientMode"...
0x1800c7b4b  mov     r8d, 2EDh; char *
0x1800c7b51  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x1800c7b58  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800c7b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7b64  lea     rax, WPP_GLOBAL_Control
0x1800c7b6b  cmp     rcx, rax
0x1800c7b6e  jz      loc_1800C7D8D
0x1800c7b74  test    byte ptr [rcx+1Ch], 8
0x1800c7b78  jz      loc_1800C7D8D
0x1800c7b7e  cmp     byte ptr [rcx+19h], 2
0x1800c7b82  jb      loc_1800C7D8D
0x1800c7b88  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c7b8d  mov     edx, 31h ; '1'
0x1800c7b92  jmp     loc_1800C7D6E
0x1800c7b97  cmp     [rbp+arg_0], ebx
0x1800c7b9a  lea     rcx, [rbp+var_30]; this
0x1800c7b9e  mov     edx, [rbp+arg_8]; int
0x1800c7ba1  mov     r8d, ebx
0x1800c7ba4  setnz   r8b; int
0x1800c7ba8  call    ??0CacheDatabaseSettings@@QEAA@HH@Z; CacheDatabaseSettings::CacheDatabaseSettings(int,int)
0x1800c7bad  mov     ecx, [rbp+var_30]
0x1800c7bb0  xor     edx, edx
0x1800c7bb2  mov     eax, [rbp+var_2C]
0x1800c7bb5  div     ecx
0x1800c7bb7  mov     [r12+80h], ecx
0x1800c7bbf  mov     [r12+84h], eax
0x1800c7bc7  mov     [r12+88h], eax
0x1800c7bcf  cmp     [r12+40h], ebx
0x1800c7bd4  jnz     loc_1800C7D23
0x1800c7bda  lea     r8, [r12+50h]
0x1800c7bdf  mov     edx, eax
0x1800c7be1  mov     ecx, 4
0x1800c7be6  call    cs:__imp_?CreateInstance@HashTable@@SAJKKPEAPEAUIHashBucket@@@Z; HashTable::CreateInstance(ulong,ulong,IHashBucket * *)
0x1800c7bec  mov     r13d, eax
0x1800c7bef  test    eax, eax
0x1800c7bf1  jns     short loc_1800C7C05
0x1800c7bf3  lea     rdx, aRdpcachemanerr_0; "RdpCacheManError_OnStartedHashTableCrea"...
0x1800c7bfa  mov     r8d, 303h
0x1800c7c00  jmp     loc_1800C7D36
0x1800c7c05  mov     edx, [r12+84h]
0x1800c7c0d  lea     rax, [r12+58h]
0x1800c7c12  mov     ecx, [rbp+var_10]
0x1800c7c15  mov     r9d, 400h
0x1800c7c1b  mov     [rsp+80h+var_58], rax
0x1800c7c20  mov     r8d, edx
0x1800c7c23  mov     [rsp+80h+var_60], r9d; int
0x1800c7c28  call    cs:__imp_?CreateInstance@Evict@@SAJKKKKKPEAPEAV1@@Z; Evict::CreateInstance(ulong,ulong,ulong,ulong,ulong,Evict * *)
0x1800c7c2e  mov     r13d, eax
0x1800c7c31  test    eax, eax
0x1800c7c33  jns     short loc_1800C7C8B
0x1800c7c35  mov     r9d, eax; unsigned int
0x1800c7c38  lea     rdx, aRdpcachemanerr_5; "RdpCacheManError_OnStartedEvictCreateIn"...
0x1800c7c3f  mov     r8d, 316h; char *
0x1800c7c45  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x1800c7c4c  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800c7c51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7c58  lea     rax, WPP_GLOBAL_Control
0x1800c7c5f  cmp     rcx, rax
0x1800c7c62  jz      loc_1800C7D8D
0x1800c7c68  test    byte ptr [rcx+1Ch], 8
0x1800c7c6c  jz      loc_1800C7D8D
0x1800c7c72  cmp     byte ptr [rcx+19h], 2
0x1800c7c76  jb      loc_1800C7D8D
0x1800c7c7c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c7c81  mov     edx, 33h ; '3'
0x1800c7c86  jmp     loc_1800C7D6E
0x1800c7c8b  mov     r13d, ebx
0x1800c7c8e  mov     dword ptr [r12+0ACh], 1
0x1800c7c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7ca1  lea     rax, WPP_GLOBAL_Control
0x1800c7ca8  cmp     rcx, rax
0x1800c7cab  jz      loc_1800C7D8D
0x1800c7cb1  test    dword ptr [rcx+1Ch], 100h
0x1800c7cb8  jz      loc_1800C7D8D
0x1800c7cbe  cmp     byte ptr [rcx+19h], 4
0x1800c7cc2  jb      loc_1800C7D8D
0x1800c7cc8  mov     ebx, [r12+80h]
0x1800c7cd0  mov     edi, [r12+84h]
0x1800c7cd8  mov     esi, [r12+40h]
0x1800c7cdd  mov     r14d, [r12+3Ch]
0x1800c7ce2  movzx   r15d, word ptr [r12+3Ah]
0x1800c7ce8  movzx   r12d, word ptr [r12+38h]
0x1800c7cee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c7cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7cfa  mov     r9d, eax
0x1800c7cfd  mov     [rsp+80h+var_38], ebx
0x1800c7d01  mov     [rsp+80h+var_40], edi
0x1800c7d05  mov     [rsp+80h+var_48], esi
0x1800c7d09  mov     rcx, [rcx+10h]
0x1800c7d0d  mov     [rsp+80h+var_50], r14d
0x1800c7d12  mov     dword ptr [rsp+80h+var_58], r15d
0x1800c7d17  mov     [rsp+80h+var_60], r12d
0x1800c7d1c  call    WPP_SF_DDDDDDD
0x1800c7d21  jmp     short loc_1800C7D8D
0x1800c7d23  mov     r13d, 80070057h
0x1800c7d29  lea     rdx, aRdpcachemanerr_19; "RdpCacheManError_OnStartedBadCachingMet"...
0x1800c7d30  mov     r8d, 308h; char *
0x1800c7d36  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x1800c7d3d  mov     r9d, r13d; unsigned int
0x1800c7d40  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800c7d45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7d4c  lea     rax, WPP_GLOBAL_Control
0x1800c7d53  cmp     rcx, rax
0x1800c7d56  jz      short loc_1800C7D8D
0x1800c7d58  test    byte ptr [rcx+1Ch], 8
0x1800c7d5c  jz      short loc_1800C7D8D
0x1800c7d5e  cmp     byte ptr [rcx+19h], 2
0x1800c7d62  jb      short loc_1800C7D8D
0x1800c7d64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c7d69  mov     edx, 32h ; '2'
0x1800c7d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7d75  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x1800c7d7c  mov     r9d, eax
0x1800c7d7f  mov     [rsp+80h+var_60], r13d
0x1800c7d84  mov     rcx, [rcx+10h]
0x1800c7d88  call    WPP_SF_Dd
0x1800c7d8d  lea     rcx, [rbp+arg_10]
0x1800c7d91  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800c7d96  mov     rbx, [rsp+80h+arg_18]
0x1800c7d9e  mov     eax, r13d
0x1800c7da1  add     rsp, 80h
0x1800c7da8  pop     r15
0x1800c7daa  pop     r14
0x1800c7dac  pop     r13
0x1800c7dae  pop     r12
0x1800c7db0  pop     rdi
0x1800c7db1  pop     rsi
0x1800c7db2  pop     rbp
0x1800c7db3  retn
```
