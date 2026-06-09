# StateRepository::CacheManagement::DeleteIndexKeysIfExists(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Context_NoThrow &,ushort const *,ushort const *)

- ea: `0x18004883c`
- end: `0x180048b22`
- name: `?DeleteIndexKeysIfExists@CacheManagement@StateRepository@@SAJAEAVManager_NoThrow@Cache@2@AEAVContext_NoThrow@42@PEBG2@Z`
- size: `742`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, struct StateRepository::Cache::Context_NoThrow *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `25`
- callee_count: `7`
- tags: ``

## callers

- `0x18002a258`
- `0x1800439cc`
- `0x18004492c`
- `0x180045bd0`
- `0x18004753c`
- `0x180048b28`
- `0x180049b2c`
- `0x18004b38c`
- `0x18004be70`
- `0x18004c958`
- `0x18005dea4`
- `0x18006c0b0`
- `0x18007325c`
- `0x180075968`
- `0x18007e878`
- `0x1800884cc`
- `0x18008a824`
- `0x180090a64`
- `0x1800998b4`
- `0x180131f14`
- `0x180160b98`
- `0x18016e1a4`
- `0x18018c668`
- `0x180269e9c`
- `0x180272ebc`

## callees

- `0x18001a9e0`
- `0x1800485e0`
- `0x18004883c`
- `0x18005b694`
- `0x18005b7c4`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004892a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800489fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180048a75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004892a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800489fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180048a75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004898f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800489e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180048a12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180048a48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180048a8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004898f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800489e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180048a12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180048a48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180048a8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180048906`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180048906`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180048a5a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180048a5a`

## string_xrefs

- `0x1800489ca`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x180048abb`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x180048adb`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x180048a9b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180048b00`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::CacheManagement::DeleteIndexKeysIfExists(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        struct StateRepository::Cache::Context_NoThrow *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int IndexKeys; // ebx
  __int64 v9; // rcx
  _QWORD *v10; // r8
  unsigned __int16 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned __int16 *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int16 *v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v30; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v31; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v32; // [rsp+38h] [rbp-C8h] BYREF
  char v33; // [rsp+40h] [rbp-C0h]
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+258h] [rbp+158h]
  __int64 v37; // [rsp+260h] [rbp+160h]
  _BYTE *v38; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v36 = 0;
  v38 = v35;
  v37 = 256;
  IndexKeys = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v34, a3);
  if ( IndexKeys < 0 )
  {
    v28 = 1489;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
      (const char *)(unsigned int)IndexKeys,
      v29[0]);
LABEL_19:
    v19 = v34;
    v34 = 0;
    if ( v19 )
      SRCache_Free(v19);
    return (unsigned int)IndexKeys;
  }
  IndexKeys = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v34, L"\\\\Index");
  if ( IndexKeys < 0 )
  {
    v28 = 1490;
    goto LABEL_33;
  }
  v9 = *(_QWORD *)a1;
  v31 = v29;
  *(_QWORD *)v29 = 0;
  v32 = 0;
  v33 = 1;
  IndexKeys = SRCacheContext_Open(v9, v38, 0, &v32);
  if ( v33 )
  {
    v10 = v31;
    v11 = v32;
    v12 = *v31;
    *v31 = v32;
    if ( v12 )
      SRCacheContext_Close(v12, v11, v10);
  }
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v29[0]);
    v27 = 1493;
    goto LABEL_31;
  }
  if ( *(_QWORD *)v29 )
  {
    v30 = 0;
    v31 = &v30;
    v32 = 0;
    v33 = 1;
    IndexKeys = StateRepository::CacheManagement::GetIndexKeys(a2, a4, &v32);
    if ( v33 )
    {
      v13 = *v31;
      *v31 = v32;
      if ( v13 )
        SRCache_Free(v13);
    }
    if ( IndexKeys != -2147023728 )
    {
      if ( IndexKeys < 0 )
      {
        v14 = 1501;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
          (const char *)(unsigned int)IndexKeys,
          v29[0]);
        v17 = v30;
        v30 = 0;
        if ( v17 )
          SRCache_Free(v17);
        goto LABEL_17;
      }
      IndexKeys = StateRepository::CacheManagement::DeleteIndexKeys(
                    (struct StateRepository::Cache::Context_NoThrow *)v29,
                    v30);
      if ( IndexKeys < 0 )
      {
        v14 = 1502;
        goto LABEL_15;
      }
    }
    v21 = v30;
    v30 = 0;
    if ( v21 )
      SRCache_Free(v21);
  }
  v22 = SRCacheContext_AddToCache(*(_QWORD *)v29, v38);
  IndexKeys = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v22,
      v29[0]);
    v27 = 1505;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
      (const char *)(unsigned int)IndexKeys,
      v29[0]);
LABEL_17:
    v18 = *(_QWORD *)v29;
    *(_QWORD *)v29 = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v15, v16);
    goto LABEL_19;
  }
  v25 = *(_QWORD *)v29;
  *(_QWORD *)v29 = 0;
  if ( v25 )
    SRCacheContext_Close(v25, v23, v24);
  v26 = v34;
  v34 = 0;
  if ( v26 )
    SRCache_Free(v26);
  return 0;
}

```

## disassembly

```asm
0x18004883c  push    rbp
0x18004883e  push    rbx
0x18004883f  push    rsi
0x180048840  push    rdi
0x180048841  push    r14
0x180048843  push    r15
0x180048845  lea     rbp, [rsp-188h]
0x18004884d  sub     rsp, 288h
0x180048854  mov     rax, cs:__security_cookie
0x18004885b  xor     rax, rsp
0x18004885e  mov     [rbp+1B0h+var_40], rax
0x180048865  mov     rbx, r8
0x180048868  mov     rsi, rdx
0x18004886b  mov     rdi, rcx
0x18004886e  xor     r15d, r15d
0x180048871  xor     edx, edx; Val
0x180048873  mov     [rsp+2B0h+var_260], r15
0x180048878  mov     r8d, 200h; Size
0x18004887e  lea     rcx, [rsp+2B0h+var_258]; void *
0x180048883  mov     r14, r9
0x180048886  call    memset_0
0x18004888b  lea     rax, [rsp+2B0h+var_258]
0x180048890  mov     [rbp+1B0h+var_58], r15
0x180048897  mov     rdx, rbx; unsigned __int16 *
0x18004889a  mov     [rbp+1B0h+var_48], rax
0x1800488a1  lea     rcx, [rsp+2B0h+var_260]; this
0x1800488a6  mov     [rbp+1B0h+var_50], 100h
0x1800488b1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800488b6  mov     ebx, eax
0x1800488b8  test    eax, eax
0x1800488ba  js      loc_180048ACF
0x1800488c0  lea     rdx, aIndex; "\\\\Index"
0x1800488c7  lea     rcx, [rsp+2B0h+var_260]; this
0x1800488cc  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800488d1  mov     ebx, eax
0x1800488d3  test    eax, eax
0x1800488d5  js      loc_180048B1B
0x1800488db  mov     rdx, [rbp+1B0h+var_48]
0x1800488e2  lea     rax, [rsp+2B0h+var_290]
0x1800488e7  mov     rcx, [rdi]
0x1800488ea  lea     r9, [rsp+2B0h+var_278]
0x1800488ef  xor     r8d, r8d
0x1800488f2  mov     [rsp+2B0h+var_280], rax
0x1800488f7  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x1800488fc  mov     [rsp+2B0h+var_278], r15
0x180048901  mov     [rsp+2B0h+var_270], 1
0x180048906  call    cs:__imp_SRCacheContext_Open
0x18004890c  mov     ebx, eax
0x18004890e  cmp     [rsp+2B0h+var_270], r15b
0x180048913  jz      short loc_180048930
0x180048915  mov     r8, [rsp+2B0h+var_280]
0x18004891a  mov     rdx, [rsp+2B0h+var_278]
0x18004891f  mov     rcx, [r8]
0x180048922  mov     [r8], rdx
0x180048925  test    rcx, rcx
0x180048928  jz      short loc_180048930
0x18004892a  call    cs:__imp_SRCacheContext_Close
0x180048930  test    ebx, ebx
0x180048932  js      loc_180048AF9
0x180048938  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18004893d  setnz   al
0x180048940  test    al, al
0x180048942  jz      loc_180048A4E
0x180048948  lea     rax, [rsp+2B0h+var_288]
0x18004894d  mov     [rsp+2B0h+var_288], r15
0x180048952  lea     r8, [rsp+2B0h+var_278]; unsigned __int16 **
0x180048957  mov     [rsp+2B0h+var_280], rax
0x18004895c  mov     rdx, r14; unsigned __int16 *
0x18004895f  mov     [rsp+2B0h+var_278], r15
0x180048964  mov     rcx, rsi; struct StateRepository::Cache::Context_NoThrow *
0x180048967  mov     [rsp+2B0h+var_270], 1
0x18004896c  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x180048971  mov     ebx, eax
0x180048973  cmp     [rsp+2B0h+var_270], r15b
0x180048978  jz      short loc_180048995
0x18004897a  mov     r8, [rsp+2B0h+var_280]
0x18004897f  mov     rdx, [rsp+2B0h+var_278]
0x180048984  mov     rcx, [r8]
0x180048987  mov     [r8], rdx
0x18004898a  test    rcx, rcx
0x18004898d  jz      short loc_180048995
0x18004898f  call    cs:__imp_SRCache_Free
0x180048995  cmp     ebx, 80070490h
0x18004899b  jz      loc_180048A39
0x1800489a1  test    ebx, ebx
0x1800489a3  js      loc_180048AEF
0x1800489a9  mov     rdx, [rsp+2B0h+var_288]; unsigned __int16 *
0x1800489ae  lea     rcx, [rsp+2B0h+var_290]; struct StateRepository::Cache::Context_NoThrow *
0x1800489b3  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x1800489b8  mov     ebx, eax
0x1800489ba  test    eax, eax
0x1800489bc  jns     short loc_180048A39
0x1800489be  mov     edx, 5DEh; void *
0x1800489c3  mov     rcx, [rbp+1B8h]; this
0x1800489ca  lea     r8, aOnecoreBaseApp_221; "onecore\\base\\appmodel\\staterepositor"...
0x1800489d1  mov     r9d, ebx; char *
0x1800489d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800489d9  mov     rcx, [rsp+2B0h+var_288]
0x1800489de  mov     [rsp+2B0h+var_288], r15
0x1800489e3  test    rcx, rcx
0x1800489e6  jz      short loc_1800489EE
0x1800489e8  call    cs:__imp_SRCache_Free
0x1800489ee  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800489f3  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800489f8  test    rcx, rcx
0x1800489fb  jz      short loc_180048A03
0x1800489fd  call    cs:__imp_SRCacheContext_Close
0x180048a03  mov     rcx, [rsp+2B0h+var_260]
0x180048a08  mov     [rsp+2B0h+var_260], r15
0x180048a0d  test    rcx, rcx
0x180048a10  jz      short loc_180048A18
0x180048a12  call    cs:__imp_SRCache_Free
0x180048a18  mov     eax, ebx
0x180048a1a  mov     rcx, [rbp+1B0h+var_40]
0x180048a21  xor     rcx, rsp; StackCookie
0x180048a24  call    __security_check_cookie
0x180048a29  add     rsp, 288h
0x180048a30  pop     r15
0x180048a32  pop     r14
0x180048a34  pop     rdi
0x180048a35  pop     rsi
0x180048a36  pop     rbx
0x180048a37  pop     rbp
0x180048a38  retn
0x180048a39  mov     rcx, [rsp+2B0h+var_288]
0x180048a3e  mov     [rsp+2B0h+var_288], r15
0x180048a43  test    rcx, rcx
0x180048a46  jz      short loc_180048A4E
0x180048a48  call    cs:__imp_SRCache_Free
0x180048a4e  mov     rdx, [rbp+1B0h+var_48]
0x180048a55  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180048a5a  call    cs:__imp_SRCacheContext_AddToCache
0x180048a60  mov     ebx, eax
0x180048a62  test    eax, eax
0x180048a64  js      short loc_180048A94
0x180048a66  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180048a6b  mov     qword ptr [rsp+2B0h+var_290], r15
0x180048a70  test    rcx, rcx
0x180048a73  jz      short loc_180048A7B
0x180048a75  call    cs:__imp_SRCacheContext_Close
0x180048a7b  mov     rcx, [rsp+2B0h+var_260]
0x180048a80  mov     [rsp+2B0h+var_260], r15
0x180048a85  test    rcx, rcx
0x180048a88  jz      short loc_180048A90
0x180048a8a  call    cs:__imp_SRCache_Free
0x180048a90  xor     eax, eax
0x180048a92  jmp     short loc_180048A1A
0x180048a94  mov     rcx, [rbp+1B8h]; this
0x180048a9b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180048aa2  mov     r9d, ebx; char *
0x180048aa5  mov     edx, 1A6h; void *
0x180048aaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048aaf  mov     edx, 5E1h; void *
0x180048ab4  mov     rcx, [rbp+1B8h]; this
0x180048abb  lea     r8, aOnecoreBaseApp_221; "onecore\\base\\appmodel\\staterepositor"...
0x180048ac2  mov     r9d, ebx; char *
0x180048ac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048aca  jmp     loc_1800489EE
0x180048acf  mov     edx, 5D1h; void *
0x180048ad4  mov     rcx, [rbp+1B8h]; this
0x180048adb  lea     r8, aOnecoreBaseApp_221; "onecore\\base\\appmodel\\staterepositor"...
0x180048ae2  mov     r9d, ebx; char *
0x180048ae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048aea  jmp     loc_180048A03
0x180048aef  mov     edx, 5DDh
0x180048af4  jmp     loc_1800489C3
0x180048af9  mov     rcx, [rbp+1B8h]; this
0x180048b00  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180048b07  mov     r9d, ebx; char *
0x180048b0a  mov     edx, 18Ch; void *
0x180048b0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048b14  mov     edx, 5D5h
0x180048b19  jmp     short loc_180048AB4
0x180048b1b  mov     edx, 5D2h
0x180048b20  jmp     short loc_180048AD4
```
