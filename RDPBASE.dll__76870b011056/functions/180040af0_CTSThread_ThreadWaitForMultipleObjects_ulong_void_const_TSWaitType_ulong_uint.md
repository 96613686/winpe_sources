# CTSThread::ThreadWaitForMultipleObjects(ulong,void * const *,TSWaitType,ulong,uint *)

- ea: `0x180040af0`
- end: `0x180040f66`
- name: `?ThreadWaitForMultipleObjects@CTSThread@@UEAAJKPEBQEAXW4TSWaitType@@KPEAI@Z`
- size: `1142`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180040ab0`

## callees

- `0x1800018a4`
- `0x180040af0`
- `0x18004b918`
- `0x180057ac0`
- `0x180058c80`
- `0x18006f440`
- `0x1800711c8`
- `0x180071a60`
- `0x1800787d4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040eb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040eb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040ed2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040ed2`

## string_xrefs

- `0x180040e48`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180040d59`: `Unable to create blocking filter`
- `0x180040db2`: `Unable to create blocking filter`
- `0x180040c4c`: `Unable to create allow all filter`
- `0x180040e2a`: `ThreadWaitForMultipleObjects`
- `0x180040e5c`: `internalThreadWaitForMultipleObjects failed`

## pseudocode

```c
__int64 __fastcall CTSThread::ThreadWaitForMultipleObjects(
        __int64 a1,
        unsigned int a2,
        void *const *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6)
{
  struct ITSEventFilter *v7; // rbx
  struct ITSEventFilter *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  struct ITSEventFilter *v14; // rcx
  unsigned int BlockAllFilter; // edi
  int ActivityIdPrefix; // eax
  int v17; // edx
  const char *v18; // rcx
  struct ITSEventFilter *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  int v26; // eax
  __int64 v27; // rdx
  int v28; // r8d
  int v29; // r9d
  int v30; // eax
  struct _RTL_CRITICAL_SECTION *v31; // rcx
  __int64 v32; // rbp
  struct _RTL_CRITICAL_SECTION *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  int v37; // eax
  int v39; // [rsp+50h] [rbp-48h] BYREF
  const char *v40; // [rsp+58h] [rbp-40h] BYREF
  const char *v41; // [rsp+60h] [rbp-38h] BYREF
  const char *v42; // [rsp+68h] [rbp-30h] BYREF
  int v43; // [rsp+B8h] [rbp+20h] BYREF

  v7 = 0;
  if ( (_DWORD)a4 != 1 )
  {
    if ( (_DWORD)a4 != 2 )
    {
      if ( (_DWORD)a4 != 3 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_903e1551464439edae082eb88b6439cd_Traceguids, a4);
        }
        goto LABEL_35;
      }
      v7 = *(struct ITSEventFilter **)(a1 + 728);
      if ( v7 )
        goto LABEL_11;
      v10 = (struct ITSEventFilter *)operator new(0x38u);
      v7 = v10;
      if ( v10 )
      {
        *(_QWORD *)v10 = &IRdpPipeDecompress::`vftable';
        *((_QWORD *)v10 + 3) = "CTSEventFilterAllowAllEvents";
        *((_DWORD *)v10 + 8) = -607474739;
        *((_QWORD *)v10 + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
        *((_QWORD *)v10 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
        *((_DWORD *)v10 + 9) = 1;
        *((_DWORD *)v10 + 12) = 0;
        *((_QWORD *)v10 + 5) = (char *)v10 + 8;
        *(_QWORD *)v10 = &CTSEventFilterAllowAllEvents::`vftable';
        *((_QWORD *)v10 + 1) = &SlidingStats<double,5,1>::`vftable'{for `INonDelegatingUnknown'};
        *((_QWORD *)v10 + 2) = &CTSEventFilterAllowAllEvents::`vftable'{for `CTSObject'};
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 5) + 8LL))(*((_QWORD *)v10 + 5));
        *(_QWORD *)(a1 + 728) = v7;
LABEL_11:
        v14 = v7;
        goto LABEL_34;
      }
      BlockAllFilter = -2147024882;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return BlockAllFilter;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v12, v11, v13);
      v17 = 83;
      v18 = "Unable to create allow all filter";
LABEL_16:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        ActivityIdPrefix,
        (__int64)v18,
        14);
      return BlockAllFilter;
    }
    v7 = *(struct ITSEventFilter **)(a1 + 720);
    if ( !v7 )
    {
      v19 = (struct ITSEventFilter *)operator new(0x38u);
      v7 = v19;
      if ( !v19 )
      {
        BlockAllFilter = -2147024882;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return BlockAllFilter;
        }
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(v21, v20, v22);
        v17 = 82;
        v18 = "Unable to create blocking filter";
        goto LABEL_16;
      }
      *(_QWORD *)v19 = &IRdpPipeDecompress::`vftable';
      *((_QWORD *)v19 + 3) = "CTSEventFilterAllowSyncEventsOnly";
      *((_DWORD *)v19 + 8) = -607474739;
      *((_QWORD *)v19 + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
      *((_QWORD *)v19 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
      *((_DWORD *)v19 + 9) = 1;
      *((_DWORD *)v19 + 12) = 0;
      *((_QWORD *)v19 + 5) = (char *)v19 + 8;
      *(_QWORD *)v19 = &CTSEventFilterAllowSyncEventsOnly::`vftable';
      *((_QWORD *)v19 + 1) = &SlidingStats<double,5,1>::`vftable'{for `INonDelegatingUnknown'};
      *((_QWORD *)v19 + 2) = &CTSEventFilterAllowSyncEventsOnly::`vftable'{for `CTSObject'};
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 + 5) + 8LL))(*((_QWORD *)v19 + 5));
      *(_QWORD *)(a1 + 720) = v7;
    }
    v14 = v7;
    goto LABEL_34;
  }
  if ( *(_QWORD *)(a1 + 712)
    || (BlockAllFilter = CTSEventFilterFactory::CreateBlockAllFilter((struct ITSEventFilter **)(a1 + 712)),
        (BlockAllFilter & 0x80000000) == 0) )
  {
    v14 = *(struct ITSEventFilter **)(a1 + 712);
    if ( !v14 )
      goto LABEL_35;
    v7 = *(struct ITSEventFilter **)(a1 + 712);
LABEL_34:
    (*(void (__fastcall **)(struct ITSEventFilter *))(*(_QWORD *)v14 + 8LL))(v14);
LABEL_35:
    BlockAllFilter = CTSThread::internalThreadWaitForMultipleObjects((CTSThread *)a1, a2, a3, v7, a5, a6);
    if ( (int)(BlockAllFilter + 0x80000000) >= 0 && BlockAllFilter != -2092630012 && (unsigned int)CallbackContext > 2 )
    {
      v43 = 1568;
      v40 = "ThreadWaitForMultipleObjects";
      v39 = -2147467259;
      v41 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v42 = "internalThreadWaitForMultipleObjects failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0x80000000,
        (unsigned int)byte_1801B7DCD,
        v28,
        v29,
        (__int64)&v42,
        (__int64)&v39,
        (__int64)&v41,
        (__int64)&v43,
        (__int64)&v40);
    }
    v30 = *(_DWORD *)(a1 + 112);
    if ( v30 )
    {
      v31 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 104);
      if ( v31 )
      {
        EnterCriticalSection(v31);
        v30 = *(_DWORD *)(a1 + 112);
      }
    }
    v32 = *(_QWORD *)(a1 + 128);
    if ( v30 )
    {
      v33 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 104);
      if ( v33 )
        LeaveCriticalSection(v33);
    }
    if ( v32 != a1 + 128 )
    {
      BlockAllFilter = CTSThread::SignalEventQueue((CTSThread *)a1, v27, v28, v29);
      if ( (BlockAllFilter & 0x80000000) != 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v37 = RdpX_GetActivityIdPrefix(v35, v34, v36);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          v37,
          (__int64)"Failed to Signal Event Queue",
          BlockAllFilter);
      }
    }
    if ( v7 )
      (*(void (__fastcall **)(struct ITSEventFilter *))(*(_QWORD *)v7 + 16LL))(v7);
    return BlockAllFilter;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = RdpX_GetActivityIdPrefix(v24, v23, v25);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      81,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      v26,
      (__int64)"Unable to create blocking filter",
      BlockAllFilter);
  }
  return BlockAllFilter;
}

```

## disassembly

```asm
0x180040af0  mov     [rsp+arg_0], rbx
0x180040af5  mov     [rsp+arg_8], rbp
0x180040afa  push    rsi
0x180040afb  push    rdi
0x180040afc  push    r12
0x180040afe  push    r14
0x180040b00  push    r15
0x180040b02  sub     rsp, 70h
0x180040b06  xor     edi, edi
0x180040b08  mov     rbp, r8
0x180040b0b  mov     ebx, edi
0x180040b0d  mov     r15d, edx
0x180040b10  mov     rsi, rcx
0x180040b13  mov     ecx, r9d
0x180040b16  lea     r12, WPP_GLOBAL_Control
0x180040b1d  sub     ecx, 1
0x180040b20  jz      loc_180040D65
0x180040b26  sub     ecx, 1
0x180040b29  jz      loc_180040C7F
0x180040b2f  cmp     ecx, 1
0x180040b32  jz      short loc_180040B72
0x180040b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b3b  cmp     rcx, r12
0x180040b3e  jz      loc_180040DD9
0x180040b44  test    byte ptr [rcx+1Ch], 1
0x180040b48  jz      loc_180040DD9
0x180040b4e  cmp     byte ptr [rcx+19h], 1
0x180040b52  jb      loc_180040DD9
0x180040b58  mov     rcx, [rcx+10h]
0x180040b5c  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180040b63  mov     edx, 54h ; 'T'
0x180040b68  call    WPP_SF_d
0x180040b6d  jmp     loc_180040DD9
0x180040b72  mov     rbx, [rsi+2D8h]
0x180040b79  test    rbx, rbx
0x180040b7c  jnz     loc_180040C11
0x180040b82  mov     ecx, 38h ; '8'; Size
0x180040b87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040b8c  mov     rbx, rax
0x180040b8f  test    rax, rax
0x180040b92  jz      loc_180040C19
0x180040b98  lea     rax, ??_7IRdpPipeDecompress@@6B@; const IRdpPipeDecompress::`vftable'
0x180040b9f  mov     [rbx], rax
0x180040ba2  lea     rcx, aCtseventfilter; "CTSEventFilterAllowAllEvents"
0x180040ba9  mov     [rbx+18h], rcx
0x180040bad  lea     rax, [rbx+8]
0x180040bb1  mov     dword ptr [rax+18h], 0DBCAABCDh
0x180040bb8  lea     rcx, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x180040bbf  mov     [rax], rcx
0x180040bc2  lea     rcx, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180040bc9  mov     [rax+8], rcx
0x180040bcd  lea     rcx, ??_7CTSEventFilterAllowAllEvents@@6B@; const CTSEventFilterAllowAllEvents::`vftable'
0x180040bd4  mov     dword ptr [rax+1Ch], 1
0x180040bdb  mov     [rax+28h], edi
0x180040bde  mov     [rax+20h], rax
0x180040be2  mov     [rbx], rcx
0x180040be5  lea     rcx, ??_7?$SlidingStats@N$04$00@@6BINonDelegatingUnknown@@@; const SlidingStats<double,5,1>::`vftable'{for `INonDelegatingUnknown'}
0x180040bec  mov     [rax], rcx
0x180040bef  lea     rax, ??_7CTSEventFilterAllowAllEvents@@6BCTSObject@@@; const CTSEventFilterAllowAllEvents::`vftable'{for `CTSObject'}
0x180040bf6  mov     [rbx+10h], rax
0x180040bfa  mov     rcx, [rbx+28h]
0x180040bfe  mov     rax, [rcx]
0x180040c01  mov     rax, [rax+8]
0x180040c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c0a  mov     [rsi+2D8h], rbx
0x180040c11  mov     rcx, rbx
0x180040c14  jmp     loc_180040DCD
0x180040c19  mov     edi, 8007000Eh
0x180040c1e  mov     rax, cs:WPP_GLOBAL_Control
0x180040c25  cmp     rax, r12
0x180040c28  jz      loc_180040F4B
0x180040c2e  test    byte ptr [rax+1Ch], 8
0x180040c32  jz      loc_180040F4B
0x180040c38  cmp     byte ptr [rax+19h], 2
0x180040c3c  jb      loc_180040F4B
0x180040c42  call    RdpX_GetActivityIdPrefix
0x180040c47  mov     edx, 53h ; 'S'
0x180040c4c  lea     rcx, aUnableToCreate_0; "Unable to create allow all filter"
0x180040c53  mov     dword ptr [rsp+98h+var_70], 8007000Eh
0x180040c5b  mov     qword ptr [rsp+98h+var_78], rcx
0x180040c60  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180040c67  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c6e  mov     r9d, eax
0x180040c71  mov     rcx, [rcx+10h]
0x180040c75  call    WPP_SF_DsD
0x180040c7a  jmp     loc_180040F4B
0x180040c7f  mov     rbx, [rsi+2D0h]
0x180040c86  test    rbx, rbx
0x180040c89  jnz     loc_180040D1E
0x180040c8f  mov     ecx, 38h ; '8'; Size
0x180040c94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040c99  mov     rbx, rax
0x180040c9c  test    rax, rax
0x180040c9f  jz      loc_180040D26
0x180040ca5  lea     rax, ??_7IRdpPipeDecompress@@6B@; const IRdpPipeDecompress::`vftable'
0x180040cac  mov     [rbx], rax
0x180040caf  lea     rcx, aCtseventfilter_0; "CTSEventFilterAllowSyncEventsOnly"
0x180040cb6  mov     [rbx+18h], rcx
0x180040cba  lea     rax, [rbx+8]
0x180040cbe  mov     dword ptr [rax+18h], 0DBCAABCDh
0x180040cc5  lea     rcx, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x180040ccc  mov     [rax], rcx
0x180040ccf  lea     rcx, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180040cd6  mov     [rax+8], rcx
0x180040cda  lea     rcx, ??_7CTSEventFilterAllowSyncEventsOnly@@6B@; const CTSEventFilterAllowSyncEventsOnly::`vftable'
0x180040ce1  mov     dword ptr [rax+1Ch], 1
0x180040ce8  mov     [rax+28h], edi
0x180040ceb  mov     [rax+20h], rax
0x180040cef  mov     [rbx], rcx
0x180040cf2  lea     rcx, ??_7?$SlidingStats@N$04$00@@6BINonDelegatingUnknown@@@; const SlidingStats<double,5,1>::`vftable'{for `INonDelegatingUnknown'}
0x180040cf9  mov     [rax], rcx
0x180040cfc  lea     rax, ??_7CTSEventFilterAllowSyncEventsOnly@@6BCTSObject@@@; const CTSEventFilterAllowSyncEventsOnly::`vftable'{for `CTSObject'}
0x180040d03  mov     [rbx+10h], rax
0x180040d07  mov     rcx, [rbx+28h]
0x180040d0b  mov     rax, [rcx]
0x180040d0e  mov     rax, [rax+8]
0x180040d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d17  mov     [rsi+2D0h], rbx
0x180040d1e  mov     rcx, rbx
0x180040d21  jmp     loc_180040DCD
0x180040d26  mov     edi, 8007000Eh
0x180040d2b  mov     rax, cs:WPP_GLOBAL_Control
0x180040d32  cmp     rax, r12
0x180040d35  jz      loc_180040F4B
0x180040d3b  test    byte ptr [rax+1Ch], 8
0x180040d3f  jz      loc_180040F4B
0x180040d45  cmp     byte ptr [rax+19h], 2
0x180040d49  jb      loc_180040F4B
0x180040d4f  call    RdpX_GetActivityIdPrefix
0x180040d54  mov     edx, 52h ; 'R'
0x180040d59  lea     rcx, aUnableToCreate_1; "Unable to create blocking filter"
0x180040d60  jmp     loc_180040C53
0x180040d65  cmp     [rsi+2C8h], rbx
0x180040d6c  jnz     short loc_180040DBE
0x180040d6e  lea     rcx, [rsi+2C8h]; struct ITSEventFilter **
0x180040d75  call    ?CreateBlockAllFilter@CTSEventFilterFactory@@SAJPEAPEAVITSEventFilter@@@Z; CTSEventFilterFactory::CreateBlockAllFilter(ITSEventFilter * *)
0x180040d7a  mov     edi, eax
0x180040d7c  test    eax, eax
0x180040d7e  jns     short loc_180040DBE
0x180040d80  mov     rax, cs:WPP_GLOBAL_Control
0x180040d87  cmp     rax, r12
0x180040d8a  jz      loc_180040F4B
0x180040d90  test    byte ptr [rax+1Ch], 8
0x180040d94  jz      loc_180040F4B
0x180040d9a  cmp     byte ptr [rax+19h], 2
0x180040d9e  jb      loc_180040F4B
0x180040da4  call    RdpX_GetActivityIdPrefix
0x180040da9  mov     edx, 51h ; 'Q'
0x180040dae  mov     dword ptr [rsp+98h+var_70], edi
0x180040db2  lea     rcx, aUnableToCreate_1; "Unable to create blocking filter"
0x180040db9  jmp     loc_180040C5B
0x180040dbe  mov     rcx, [rsi+2C8h]
0x180040dc5  test    rcx, rcx
0x180040dc8  jz      short loc_180040DD9
0x180040dca  mov     rbx, rcx
0x180040dcd  mov     rax, [rcx]
0x180040dd0  mov     rax, [rax+8]
0x180040dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dd9  mov     rax, [rsp+98h+arg_28]
0x180040de1  mov     r9, rbx; struct ITSEventFilter *
0x180040de4  mov     [rsp+98h+var_70], rax; unsigned int *
0x180040de9  mov     r8, rbp; void **
0x180040dec  mov     eax, [rsp+98h+arg_20]
0x180040df3  mov     edx, r15d; unsigned int
0x180040df6  mov     rcx, rsi; this
0x180040df9  mov     [rsp+98h+var_78], eax; unsigned int
0x180040dfd  call    ?internalThreadWaitForMultipleObjects@CTSThread@@IEAAJKPEBQEAXPEAVITSEventFilter@@KPEAI@Z; CTSThread::internalThreadWaitForMultipleObjects(ulong,void * const *,ITSEventFilter *,ulong,uint *)
0x180040e02  mov     ecx, 80000000h
0x180040e07  mov     edi, eax
0x180040e09  add     eax, ecx
0x180040e0b  test    ecx, eax
0x180040e0d  jnz     loc_180040EA2
0x180040e13  cmp     edi, 83450004h
0x180040e19  jz      loc_180040EA2
0x180040e1f  mov     eax, cs:CallbackContext
0x180040e25  cmp     eax, 2
0x180040e28  jbe     short loc_180040EA2
0x180040e2a  lea     rax, aThreadwaitform; "ThreadWaitForMultipleObjects"
0x180040e31  mov     [rsp+98h+arg_18], 620h
0x180040e3c  mov     [rsp+98h+var_40], rax
0x180040e41  lea     rdx, byte_1801B7DCD
0x180040e48  lea     rax, aOnecoreTermsrv_22; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180040e4f  mov     [rsp+98h+var_48], 80004005h
0x180040e57  mov     [rsp+98h+var_38], rax
0x180040e5c  lea     rax, aInternalthread; "internalThreadWaitForMultipleObjects fa"...
0x180040e63  mov     [rsp+98h+var_30], rax
0x180040e68  lea     rax, [rsp+98h+var_40]
0x180040e6d  mov     [rsp+98h+var_58], rax
0x180040e72  lea     rax, [rsp+98h+arg_18]
0x180040e7a  mov     [rsp+98h+var_60], rax
0x180040e7f  lea     rax, [rsp+98h+var_38]
0x180040e84  mov     [rsp+98h+var_68], rax
0x180040e89  lea     rax, [rsp+98h+var_48]
0x180040e8e  mov     [rsp+98h+var_70], rax
0x180040e93  lea     rax, [rsp+98h+var_30]
0x180040e98  mov     qword ptr [rsp+98h+var_78], rax
0x180040e9d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180040ea2  mov     eax, [rsi+70h]
0x180040ea5  test    eax, eax
0x180040ea7  jz      short loc_180040EBB
0x180040ea9  mov     rcx, [rsi+68h]; lpCriticalSection
0x180040ead  test    rcx, rcx
0x180040eb0  jz      short loc_180040EBB
0x180040eb2  call    cs:__imp_EnterCriticalSection
0x180040eb8  mov     eax, [rsi+70h]
0x180040ebb  lea     r14, [rsi+80h]
0x180040ec2  mov     rbp, [r14]
0x180040ec5  test    eax, eax
0x180040ec7  jz      short loc_180040ED8
0x180040ec9  mov     rcx, [rsi+68h]; lpCriticalSection
0x180040ecd  test    rcx, rcx
0x180040ed0  jz      short loc_180040ED8
0x180040ed2  call    cs:__imp_LeaveCriticalSection
0x180040ed8  cmp     rbp, r14
0x180040edb  jz      short loc_180040F37
0x180040edd  mov     rcx, rsi; this
0x180040ee0  call    ?SignalEventQueue@CTSThread@@MEAAJXZ; CTSThread::SignalEventQueue(void)
0x180040ee5  mov     edi, eax
0x180040ee7  test    eax, eax
0x180040ee9  jns     short loc_180040F37
0x180040eeb  mov     rax, cs:WPP_GLOBAL_Control
0x180040ef2  cmp     rax, r12
0x180040ef5  jz      short loc_180040F37
0x180040ef7  test    byte ptr [rax+1Ch], 8
0x180040efb  jz      short loc_180040F37
0x180040efd  cmp     byte ptr [rax+19h], 2
0x180040f01  jb      short loc_180040F37
0x180040f03  call    RdpX_GetActivityIdPrefix
0x180040f08  lea     rcx, aFailedToSignal_0; "Failed to Signal Event Queue"
0x180040f0f  mov     dword ptr [rsp+98h+var_70], edi
0x180040f13  mov     qword ptr [rsp+98h+var_78], rcx
0x180040f18  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180040f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f26  mov     edx, 55h ; 'U'
0x180040f2b  mov     r9d, eax
0x180040f2e  mov     rcx, [rcx+10h]
0x180040f32  call    WPP_SF_DsD
0x180040f37  test    rbx, rbx
0x180040f3a  jz      short loc_180040F4B
0x180040f3c  mov     rax, [rbx]
0x180040f3f  mov     rcx, rbx
0x180040f42  mov     rax, [rax+10h]
0x180040f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f4b  lea     r11, [rsp+98h+var_28]
0x180040f50  mov     eax, edi
0x180040f52  mov     rbx, [r11+30h]
0x180040f56  mov     rbp, [r11+38h]
0x180040f5a  mov     rsp, r11
0x180040f5d  pop     r15
0x180040f5f  pop     r14
0x180040f61  pop     r12
0x180040f63  pop     rdi
0x180040f64  pop     rsi
0x180040f65  retn
```
