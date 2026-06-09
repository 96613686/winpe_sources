# ClientsTracker::Unregister(ulong,MapsClientType)

- ea: `0x18000a538`
- end: `0x18000a78b`
- name: `?Unregister@ClientsTracker@@QEAAJKW4MapsClientType@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014c00`

## callees

- `0x180003410`
- `0x18000a198`
- `0x18000a538`
- `0x18000b1c8`
- `0x18000b220`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a74d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a74d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a570`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a570`
- `ZTrace_Maps!ZTraceHelper` at `0x18000a63b`
- `ZTrace_Maps!ZTraceHelper` at `0x18000a63b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000a5ae`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000a5ae`

## string_xrefs

- `0x18000a61c`: `Detaching client - type: %d | processId: %lu | moshost: %lu | odml: %lu | deleteAll: %lu | background: %lu | mapsStorage: %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClientsTracker::Unregister(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned int v6; // esi
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rcx
  _QWORD v17[2]; // [rsp+60h] [rbp-48h] BYREF

  if ( (a3 & 0xFFFFFFFA) != 0 )
  {
    v6 = 0;
    if ( !a2 )
      goto LABEL_7;
    goto LABEL_6;
  }
  v6 = 0;
  if ( a2 == GetCurrentProcessId() || !a2 )
LABEL_6:
    __int2c();
LABEL_7:
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)qword_180035648 + 24LL))(qword_180035648) )
  {
    if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v7, DeregisterClient, v8, 1, v17);
    EnterCriticalSection((LPCRITICAL_SECTION)a1);
    v17[0] = a1;
    ZTraceHelper(
      1,
      "ClientsTracker::Unregister",
      264,
      a1,
      "Detaching client - type: %d | processId: %lu | moshost: %lu | odml: %lu | deleteAll: %lu | background: %lu | mapsStorage: %lu",
      a3,
      a2,
      *(_DWORD *)(a1 + 116),
      *(_DWORD *)(a1 + 108),
      *(_DWORD *)(a1 + 120),
      *(_DWORD *)(a1 + 104),
      *(_DWORD *)(a1 + 124));
    if ( a3 )
    {
      switch ( a3 )
      {
        case 1u:
          if ( *(_DWORD *)(a1 + 108) != 1 )
            __int2c();
          ClientsTracker::RemoveFromClientsMap(a1, a2, 1);
          if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(v11, DecrementOdmlClientCount, v12, 1, v17);
          --*(_DWORD *)(a1 + 108);
          break;
        case 2u:
          v10 = *(_DWORD *)(a1 + 104);
          if ( v10 != 1 )
            __int2c();
          *(_DWORD *)(a1 + 104) = v10 - 1;
          break;
        case 3u:
          v9 = *(_DWORD *)(a1 + 120);
          if ( v9 != 1 )
            __int2c();
          *(_DWORD *)(a1 + 120) = v9 - 1;
          break;
        case 4u:
          if ( *(_DWORD *)(a1 + 124) != 1 )
            __int2c();
          ClientsTracker::RemoveFromClientsMap(a1, a2, 4);
          --*(_DWORD *)(a1 + 124);
          break;
        case 5u:
          if ( !*(_DWORD *)(a1 + 112) )
            __int2c();
          ClientsTracker::RemoveFromClientsMap(a1, a2, 5);
          --*(_DWORD *)(a1 + 112);
          break;
        default:
          __int2c();
          break;
      }
    }
    else
    {
      if ( !*(_DWORD *)(a1 + 116) )
        __int2c();
      ClientsTracker::RemoveFromClientsMap(a1, a2, 0);
      if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(v13, DecrementClientCount, v14, 1, v17);
      --*(_DWORD *)(a1 + 116);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)a1);
    if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
      McTemplateU0qq_EventWriteTransfer(v15, DeregisterClient_Info, a2, a3);
  }
  else
  {
    return (unsigned int)ZTraceReportOrigination(-2147024745, "ClientsTracker::Unregister", 255, (const void *)a1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a538  push    rbx
0x18000a53a  push    rbp
0x18000a53b  push    rsi
0x18000a53c  push    rdi
0x18000a53d  push    r14
0x18000a53f  sub     rsp, 80h
0x18000a546  mov     rax, cs:__security_cookie
0x18000a54d  xor     rax, rsp
0x18000a550  mov     [rsp+0A8h+var_38], rax
0x18000a555  mov     ebp, r8d
0x18000a558  mov     edi, edx
0x18000a55a  mov     rbx, rcx
0x18000a55d  test    r8d, 0FFFFFFFAh
0x18000a564  jz      short loc_18000A570
0x18000a566  xor     esi, esi
0x18000a568  test    edx, edx
0x18000a56a  jz      short loc_18000A582
0x18000a56c  int     2Ch; Windows NT - assertion failure
0x18000a56e  jmp     short loc_18000A582
0x18000a570  call    cs:__imp_GetCurrentProcessId
0x18000a576  xor     esi, esi
0x18000a578  cmp     edi, eax
0x18000a57a  jz      short loc_18000A580
0x18000a57c  test    edi, edi
0x18000a57e  jnz     short loc_18000A582
0x18000a580  int     2Ch; Windows NT - assertion failure
0x18000a582  mov     rcx, cs:qword_180035648
0x18000a589  mov     rax, [rcx]
0x18000a58c  mov     rax, [rax+18h]
0x18000a590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a595  test    eax, eax
0x18000a597  jnz     short loc_18000A5BB
0x18000a599  mov     r9, rbx
0x18000a59c  mov     r8d, 0FFh
0x18000a5a2  lea     rdx, aClientstracker_2; "ClientsTracker::Unregister"
0x18000a5a9  mov     ecx, 80070097h
0x18000a5ae  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000a5b4  mov     esi, eax
0x18000a5b6  jmp     loc_18000A76E
0x18000a5bb  mov     r14d, 1
0x18000a5c1  test    cs:Microsoft_Windows_MosHostEnableBits, r14b
0x18000a5c8  jz      short loc_18000A5E3
0x18000a5ca  lea     rax, [rsp+0A8h+var_48]
0x18000a5cf  mov     [rsp+0A8h+var_88], rax
0x18000a5d4  mov     r9d, r14d
0x18000a5d7  lea     rdx, DeregisterClient
0x18000a5de  call    McGenEventWrite_EventWriteTransfer
0x18000a5e3  mov     rcx, rbx; lpCriticalSection
0x18000a5e6  call    cs:__imp_EnterCriticalSection
0x18000a5ec  mov     [rsp+0A8h+var_48], rbx
0x18000a5f1  mov     eax, [rbx+7Ch]
0x18000a5f4  mov     [rsp+0A8h+var_50], eax
0x18000a5f8  mov     eax, [rbx+68h]
0x18000a5fb  mov     [rsp+0A8h+var_58], eax
0x18000a5ff  mov     eax, [rbx+78h]
0x18000a602  mov     [rsp+0A8h+var_60], eax
0x18000a606  mov     eax, [rbx+6Ch]
0x18000a609  mov     [rsp+0A8h+var_68], eax
0x18000a60d  mov     eax, [rbx+74h]
0x18000a610  mov     [rsp+0A8h+var_70], eax
0x18000a614  mov     [rsp+0A8h+var_78], edi
0x18000a618  mov     [rsp+0A8h+var_80], ebp
0x18000a61c  lea     rax, aDetachingClien; "Detaching client - type: %d | processId"...
0x18000a623  mov     [rsp+0A8h+var_88], rax
0x18000a628  mov     r9, rbx
0x18000a62b  mov     r8d, 108h
0x18000a631  lea     rdx, aClientstracker_2; "ClientsTracker::Unregister"
0x18000a638  mov     ecx, r14d
0x18000a63b  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000a641  mov     ecx, ebp
0x18000a643  test    ebp, ebp
0x18000a645  jz      loc_18000A710
0x18000a64b  sub     ecx, 1
0x18000a64e  jz      loc_18000A6D4
0x18000a654  sub     ecx, 1
0x18000a657  jz      short loc_18000A6C3
0x18000a659  sub     ecx, 1
0x18000a65c  jz      short loc_18000A6AF
0x18000a65e  sub     ecx, 1
0x18000a661  jz      short loc_18000A68F
0x18000a663  cmp     ecx, 1
0x18000a666  jz      short loc_18000A66F
0x18000a668  int     2Ch; Windows NT - assertion failure
0x18000a66a  jmp     loc_18000A74A
0x18000a66f  cmp     [rbx+70h], r14d
0x18000a673  jnb     short loc_18000A677
0x18000a675  int     2Ch; Windows NT - assertion failure
0x18000a677  mov     r8d, 5
0x18000a67d  mov     edx, edi
0x18000a67f  mov     rcx, rbx
0x18000a682  call    ?RemoveFromClientsMap@ClientsTracker@@AEAAXKW4MapsClientType@@@Z; ClientsTracker::RemoveFromClientsMap(ulong,MapsClientType)
0x18000a687  dec     dword ptr [rbx+70h]
0x18000a68a  jmp     loc_18000A74A
0x18000a68f  cmp     [rbx+7Ch], r14d
0x18000a693  jz      short loc_18000A697
0x18000a695  int     2Ch; Windows NT - assertion failure
0x18000a697  mov     r8d, 4
0x18000a69d  mov     edx, edi
0x18000a69f  mov     rcx, rbx
0x18000a6a2  call    ?RemoveFromClientsMap@ClientsTracker@@AEAAXKW4MapsClientType@@@Z; ClientsTracker::RemoveFromClientsMap(ulong,MapsClientType)
0x18000a6a7  dec     dword ptr [rbx+7Ch]
0x18000a6aa  jmp     loc_18000A74A
0x18000a6af  mov     eax, [rbx+78h]
0x18000a6b2  cmp     eax, r14d
0x18000a6b5  jz      short loc_18000A6B9
0x18000a6b7  int     2Ch; Windows NT - assertion failure
0x18000a6b9  dec     eax
0x18000a6bb  mov     [rbx+78h], eax
0x18000a6be  jmp     loc_18000A74A
0x18000a6c3  mov     eax, [rbx+68h]
0x18000a6c6  cmp     eax, r14d
0x18000a6c9  jz      short loc_18000A6CD
0x18000a6cb  int     2Ch; Windows NT - assertion failure
0x18000a6cd  dec     eax
0x18000a6cf  mov     [rbx+68h], eax
0x18000a6d2  jmp     short loc_18000A74A
0x18000a6d4  cmp     [rbx+6Ch], r14d
0x18000a6d8  jz      short loc_18000A6DC
0x18000a6da  int     2Ch; Windows NT - assertion failure
0x18000a6dc  mov     r8d, r14d
0x18000a6df  mov     edx, edi
0x18000a6e1  mov     rcx, rbx
0x18000a6e4  call    ?RemoveFromClientsMap@ClientsTracker@@AEAAXKW4MapsClientType@@@Z; ClientsTracker::RemoveFromClientsMap(ulong,MapsClientType)
0x18000a6e9  test    cs:Microsoft_Windows_MosHostEnableBits, r14b
0x18000a6f0  jz      short loc_18000A70B
0x18000a6f2  lea     rax, [rsp+0A8h+var_48]
0x18000a6f7  mov     [rsp+0A8h+var_88], rax
0x18000a6fc  mov     r9d, r14d
0x18000a6ff  lea     rdx, DecrementOdmlClientCount
0x18000a706  call    McGenEventWrite_EventWriteTransfer
0x18000a70b  dec     dword ptr [rbx+6Ch]
0x18000a70e  jmp     short loc_18000A74A
0x18000a710  cmp     [rbx+74h], r14d
0x18000a714  jnb     short loc_18000A718
0x18000a716  int     2Ch; Windows NT - assertion failure
0x18000a718  xor     r8d, r8d
0x18000a71b  mov     edx, edi
0x18000a71d  mov     rcx, rbx
0x18000a720  call    ?RemoveFromClientsMap@ClientsTracker@@AEAAXKW4MapsClientType@@@Z; ClientsTracker::RemoveFromClientsMap(ulong,MapsClientType)
0x18000a725  test    cs:Microsoft_Windows_MosHostEnableBits, r14b
0x18000a72c  jz      short loc_18000A747
0x18000a72e  lea     rax, [rsp+0A8h+var_48]
0x18000a733  mov     [rsp+0A8h+var_88], rax
0x18000a738  mov     r9d, r14d
0x18000a73b  lea     rdx, DecrementClientCount
0x18000a742  call    McGenEventWrite_EventWriteTransfer
0x18000a747  dec     dword ptr [rbx+74h]
0x18000a74a  mov     rcx, rbx; lpCriticalSection
0x18000a74d  call    cs:__imp_LeaveCriticalSection
0x18000a753  test    cs:Microsoft_Windows_MosHostEnableBits, r14b
0x18000a75a  jz      short loc_18000A76E
0x18000a75c  mov     r9d, ebp
0x18000a75f  mov     r8d, edi
0x18000a762  lea     rdx, DeregisterClient_Info
0x18000a769  call    McTemplateU0qq_EventWriteTransfer
0x18000a76e  mov     eax, esi
0x18000a770  mov     rcx, [rsp+0A8h+var_38]
0x18000a775  xor     rcx, rsp; StackCookie
0x18000a778  call    __security_check_cookie
0x18000a77d  add     rsp, 80h
0x18000a784  pop     r14
0x18000a786  pop     rdi
0x18000a787  pop     rsi
0x18000a788  pop     rbp
0x18000a789  pop     rbx
0x18000a78a  retn
```
