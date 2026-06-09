# WSManHttpSenderConnection::StatusDataAvailable(ulong,InCritSecWithConditionVar *)

- ea: `0x1800535f0`
- end: `0x180053c1b`
- name: `?StatusDataAvailable@WSManHttpSenderConnection@@AEAAXKPEAVInCritSecWithConditionVar@@@Z`
- size: `1579`
- prototype: `void(WSManHttpSenderConnection *__hidden this, unsigned int, struct InCritSecWithConditionVar *)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800521b0`

## callees

- `0x180005d10`
- `0x180033c90`
- `0x18004a900`
- `0x18004e0d0`
- `0x1800535f0`
- `0x180053c24`
- `0x180053ccc`
- `0x180053ea8`
- `0x180054148`
- `0x18005d800`
- `0x180071cdc`
- `0x180112380`
- `0x1801123a8`
- `0x180112460`
- `0x18011a6d4`
- `0x18011aed0`
- `0x180123fa0`
- `0x1801296dc`
- `0x1801344d0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053a56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053a8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053a56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800538fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800538fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800538a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800538a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800536b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180053832`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800536b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180053832`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800539df`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180053a3c`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800539df`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180053a3c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18005388e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18005388e`
- `WINHTTP!WinHttpReadData` at `0x1800538f3`
- `WINHTTP!WinHttpReadData` at `0x1800538f3`

## string_xrefs

- `0x180053a77`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x180053b1c`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180053c08`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c
void __fastcall WSManHttpSenderConnection::StatusDataAvailable(
        WSManHttpSenderConnection *this,
        unsigned int a2,
        DWORD **a3)
{
  SIZE_T v3; // rbp
  PVOID *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 PoolItem; // rax
  CHeap *v10; // rcx
  __int64 LastError; // rdi
  const void *v12; // r15
  CHeap *v13; // rcx
  void *v14; // rax
  LPVOID v15; // r15
  void *v16; // rcx
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int v19; // esi
  const void *v20; // r15
  CHeap *v21; // rcx
  CHeap *v22; // rcx
  void *Handle; // rax
  void *v24; // rax
  __int64 v25; // rax
  const CHAR *v26; // rdi
  DWORD *v27; // rcx
  DWORD v28; // eax
  __int64 v29; // rsi
  __int64 v30; // r8
  void *v31; // rax
  void *Heap; // rax
  PacketParser *v33; // rcx

  v3 = a2;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_qqLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, a3, this, *((_QWORD *)this + 1), *((_DWORD *)this + 2284), a2);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !(_DWORD)v3 )
  {
    WSManHttpSenderConnection::EndOfResponse(this);
    return;
  }
  v6 = *((_QWORD *)this + 1141);
  if ( v6 )
  {
    v18 = *((_DWORD *)this + 2284);
    v19 = v18 + v3;
    if ( v18 + (unsigned int)v3 < v18 )
    {
      LODWORD(LastError) = 534;
      goto LABEL_50;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x400) != 0 )
      WPP_SF_qD(v5[2], 251, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v6, v18 + v3);
    LastError = *((_QWORD *)this + 1141);
    v20 = *(const void **)(LastError + 32);
    if ( v20 && (Heap = WSManMemory::GetHeap(), HeapSize(Heap, 0, v20) >= v19) )
    {
      v24 = *(void **)(LastError + 32);
    }
    else
    {
      v21 = *(CHeap **)(LastError + 32);
      if ( v21 )
      {
        v24 = WSManMemory::ReAlloc(v21, v19);
      }
      else if ( CHeap::GetHandle(0) )
      {
        Handle = CHeap::GetHandle(v22);
        v24 = HeapAlloc(Handle, 0, v19);
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
        v24 = 0;
      }
      if ( !v24 )
      {
        LODWORD(LastError) = 14;
        goto LABEL_33;
      }
      *(_QWORD *)(LastError + 32) = v24;
    }
    *(_QWORD *)(LastError + 40) = v24;
    *(_DWORD *)(LastError + 48) = v19;
    LODWORD(LastError) = 0;
    goto LABEL_33;
  }
  v7 = *(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 392LL;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 96LL))(v7);
  PoolItem = LocklessPool<Packet>::GetPoolItem(v8);
  *((_QWORD *)this + 1141) = PoolItem;
  LastError = PoolItem;
  if ( PoolItem )
  {
    v12 = *(const void **)(PoolItem + 32);
    if ( v12 )
    {
      v31 = WSManMemory::GetHeap();
      if ( HeapSize(v31, 0, v12) >= v3 )
      {
        *(_QWORD *)(LastError + 40) = *(_QWORD *)(LastError + 32);
LABEL_11:
        *(_DWORD *)(LastError + 48) = v3;
        LODWORD(LastError) = 0;
        goto LABEL_12;
      }
    }
    if ( CHeap::GetHandle(v10) )
    {
      v14 = CHeap::GetHandle(v13);
      v15 = HeapAlloc(v14, 0, v3);
      if ( v15 )
      {
        v16 = *(void **)(LastError + 32);
        if ( v16 )
          WSManMemory::Free(v16, 0);
        *(_QWORD *)(LastError + 32) = v15;
        *(_QWORD *)(LastError + 40) = v15;
        goto LABEL_11;
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    }
    LODWORD(LastError) = 14;
    Packet::Recycle(*((Packet **)this + 1141));
    *((_QWORD *)this + 1141) = 0;
  }
  else
  {
    LODWORD(LastError) = 14;
  }
LABEL_12:
  v17 = *((_QWORD *)this + 1141);
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v17, v3);
LABEL_33:
    if ( !(_DWORD)LastError )
    {
      v25 = *((_QWORD *)this + 1141);
      v26 = Buf1;
      v27 = *a3;
      if ( *(_QWORD *)(v25 + 40) )
        v26 = *(const CHAR **)(v25 + 40);
      if ( *v27 )
      {
        SetLastError(*v27);
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
          102,
          L"102",
          0x54Fu,
          0);
      }
      else
      {
        WakeAllConditionVariable((PCONDITION_VARIABLE)v27 + 6);
      }
      v28 = **a3;
      if ( v28 )
        SetLastError(v28);
      else
        LeaveCriticalSection((LPCRITICAL_SECTION)(*a3 + 2));
      *((_DWORD *)a3 + 2) = 1;
      v29 = *((unsigned int *)this + 2284);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          419,
          &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
          this,
          *((_QWORD *)this + 1),
          v3);
      if ( !*((_QWORD *)this + 1134) || *((_DWORD *)this + 2294) )
      {
        LODWORD(LastError) = 995;
      }
      else
      {
        if ( WinHttpReadData(*((HINTERNET *)this + 1134), (LPVOID)&v26[v29], v3, 0) )
          return;
        LastError = GetLastError();
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(
          *((_QWORD *)this + 1128),
          LastError);
        if ( !(_DWORD)LastError )
          return;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
      v30 = 0;
LABEL_51:
      WSManHttpSenderConnection::CompleteRequest(this, (unsigned int)LastError, v30);
      return;
    }
LABEL_50:
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1128) + 72LL))(
      *((_QWORD *)this + 1128),
      (unsigned int)LastError);
    v30 = 2;
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      249,
      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
      (unsigned int)v3);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1128) + 24LL))(*((_QWORD *)this + 1128));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qqdl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      447,
      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
      this,
      *((_QWORD *)this + 1),
      14,
      2);
  if ( !*((_QWORD *)this + 1) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 8357, L"8357", 0x54Fu, 0);
  WSManHttpSenderConnection::EndQueryingMoreDataFromHttp(this);
  if ( *((_BYTE *)this + 11381) )
  {
    v33 = (PacketParser *)*((_QWORD *)this + 1145);
    if ( v33 )
      PacketParser::EndOfStream(v33, 0xEu);
  }
  *((_DWORD *)this + 2278) = 0;
  *((_DWORD *)this + 2279) = 14;
  *((_DWORD *)this + 2280) = 2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 448, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
  (*(void (__fastcall **)(WSManHttpSenderConnection *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 96LL))(this, 0, 0, 0);
}

```

## disassembly

```asm
0x1800535f0  mov     [rsp+arg_0], rbx
0x1800535f5  mov     [rsp+arg_8], rbp
0x1800535fa  mov     [rsp+arg_10], r8
0x1800535ff  push    rsi
0x180053600  push    rdi
0x180053601  push    r12
0x180053603  push    r14
0x180053605  push    r15
0x180053607  sub     rsp, 40h
0x18005360b  mov     ebp, edx
0x18005360d  mov     rbx, rcx
0x180053610  mov     rcx, cs:WPP_GLOBAL_Control
0x180053617  lea     r15, WPP_GLOBAL_Control
0x18005361e  mov     r12d, 400h
0x180053624  cmp     rcx, r15
0x180053627  jnz     loc_180053795
0x18005362d  test    ebp, ebp
0x18005362f  jz      loc_180053939
0x180053635  mov     r9, [rbx+23A8h]
0x18005363c  lea     r14, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x180053643  test    r9, r9
0x180053646  jnz     loc_1800537D3
0x18005364c  mov     rax, [rbx+28h]
0x180053650  mov     rcx, [rax+80h]
0x180053657  add     rcx, 188h
0x18005365e  mov     rax, [rcx]
0x180053661  mov     rax, [rax+60h]
0x180053665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005366a  mov     rcx, rax
0x18005366d  call    ?GetPoolItem@?$LocklessPool@VPacket@@@@QEAAPEAVPacket@@PEA_N@Z; LocklessPool<Packet>::GetPoolItem(bool *)
0x180053672  mov     [rbx+23A8h], rax
0x180053679  mov     rdi, rax
0x18005367c  mov     esi, 0Eh
0x180053681  test    rax, rax
0x180053684  jz      loc_180053AFA
0x18005368a  mov     r15, [rax+20h]
0x18005368e  test    r15, r15
0x180053691  jnz     loc_1800539D2
0x180053697  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005369c  test    rax, rax
0x18005369f  jz      loc_180053B01
0x1800536a5  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800536aa  mov     r8, rbp; dwBytes
0x1800536ad  xor     edx, edx; dwFlags
0x1800536af  mov     rcx, rax; hHeap
0x1800536b2  call    cs:__imp_HeapAlloc
0x1800536b8  mov     r15, rax
0x1800536bb  test    rax, rax
0x1800536be  jz      loc_180053B28
0x1800536c4  mov     rcx, [rdi+20h]; void *
0x1800536c8  test    rcx, rcx
0x1800536cb  jnz     loc_180053B46
0x1800536d1  mov     [rdi+20h], r15
0x1800536d5  mov     [rdi+28h], r15
0x1800536d9  mov     [rdi+30h], ebp
0x1800536dc  xor     edi, edi
0x1800536de  lea     r15, WPP_GLOBAL_Control
0x1800536e5  mov     r9, [rbx+23A8h]
0x1800536ec  test    r9, r9
0x1800536ef  jnz     loc_1800539FB
0x1800536f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800536fc  lea     r14, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x180053703  cmp     rcx, r15
0x180053706  jnz     loc_180053B52
0x18005370c  mov     rcx, [rbx+2340h]
0x180053713  mov     rax, [rcx]
0x180053716  mov     rax, [rax+18h]
0x18005371a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005371f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053726  cmp     rcx, r15
0x180053729  jnz     loc_180053A95
0x18005372f  cmp     qword ptr [rbx+8], 0
0x180053734  jz      loc_180053B78
0x18005373a  mov     rcx, rbx; this
0x18005373d  call    ?EndQueryingMoreDataFromHttp@WSManHttpSenderConnection@@QEAAXXZ; WSManHttpSenderConnection::EndQueryingMoreDataFromHttp(void)
0x180053742  cmp     byte ptr [rbx+2C75h], 0
0x180053749  jnz     loc_180053BA4
0x18005374f  mov     dword ptr [rbx+2398h], 0
0x180053759  mov     [rbx+239Ch], esi
0x18005375f  mov     dword ptr [rbx+23A0h], 2
0x180053769  mov     rcx, cs:WPP_GLOBAL_Control
0x180053770  cmp     rcx, r15
0x180053773  jnz     loc_180053ACD
0x180053779  mov     rax, [rbx]
0x18005377c  xor     r9d, r9d
0x18005377f  xor     r8d, r8d
0x180053782  xor     edx, edx
0x180053784  mov     rcx, rbx
0x180053787  mov     rax, [rax+60h]
0x18005378b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053790  jmp     loc_180053922
0x180053795  test    [rcx+1Ch], r12d
0x180053799  jz      loc_18005362D
0x18005379f  mov     eax, [rbx+23B0h]
0x1800537a5  mov     edx, 0F8h
0x1800537aa  mov     rcx, [rcx+10h]
0x1800537ae  mov     r9, rbx
0x1800537b1  mov     [rsp+68h+var_38], ebp
0x1800537b5  mov     [rsp+68h+var_40], eax
0x1800537b9  mov     rax, [rbx+8]
0x1800537bd  mov     [rsp+68h+var_48], rax
0x1800537c2  call    WPP_SF_qqLL
0x1800537c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800537ce  jmp     loc_18005362D
0x1800537d3  mov     eax, [rbx+23B0h]
0x1800537d9  lea     esi, [rax+rbp]
0x1800537dc  cmp     esi, eax
0x1800537de  jb      loc_180053976
0x1800537e4  cmp     rcx, r15
0x1800537e7  jz      short loc_1800537F3
0x1800537e9  test    [rcx+1Ch], r12d
0x1800537ed  jnz     loc_180053BC0
0x1800537f3  mov     rdi, [rbx+23A8h]
0x1800537fa  mov     r12d, esi
0x1800537fd  mov     r15, [rdi+20h]
0x180053801  test    r15, r15
0x180053804  jnz     loc_180053A2F
0x18005380a  mov     rcx, [rdi+20h]; this
0x18005380e  test    rcx, rcx
0x180053811  jnz     loc_180053BDA
0x180053817  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005381c  test    rax, rax
0x18005381f  jz      loc_180053BED
0x180053825  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005382a  mov     r8, r12; dwBytes
0x18005382d  xor     edx, edx; dwFlags
0x18005382f  mov     rcx, rax; hHeap
0x180053832  call    cs:__imp_HeapAlloc
0x180053838  test    rax, rax
0x18005383b  jz      loc_180053AF0
0x180053841  mov     [rdi+20h], rax
0x180053845  mov     [rdi+28h], rax
0x180053849  mov     [rdi+30h], esi
0x18005384c  xor     edi, edi
0x18005384e  lea     r15, WPP_GLOBAL_Control
0x180053855  test    edi, edi
0x180053857  jnz     loc_18005397B
0x18005385d  mov     rax, [rbx+23A8h]
0x180053864  lea     rdi, Buf1
0x18005386b  mov     rsi, [rsp+68h+arg_10]
0x180053873  cmp     qword ptr [rax+28h], 0
0x180053878  mov     rcx, [rsi]
0x18005387b  cmovnz  rdi, [rax+28h]
0x180053880  mov     eax, [rcx]
0x180053882  test    eax, eax
0x180053884  jnz     loc_180053A54
0x18005388a  add     rcx, 30h ; '0'; ConditionVariable
0x18005388e  call    cs:__imp_WakeAllConditionVariable
0x180053894  mov     rcx, [rsi]
0x180053897  mov     eax, [rcx]
0x180053899  test    eax, eax
0x18005389b  jnz     loc_180053A88
0x1800538a1  add     rcx, 8; lpCriticalSection
0x1800538a5  call    cs:__imp_LeaveCriticalSection
0x1800538ab  mov     dword ptr [rsi+8], 1
0x1800538b2  mov     esi, [rbx+23B0h]
0x1800538b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538bf  cmp     rcx, r15
0x1800538c2  jnz     short loc_180053943
0x1800538c4  mov     rax, [rbx+2370h]
0x1800538cb  test    rax, rax
0x1800538ce  jz      loc_1800539A2
0x1800538d4  mov     eax, [rbx+23D8h]
0x1800538da  test    eax, eax
0x1800538dc  jnz     loc_1800539A2
0x1800538e2  mov     rcx, [rbx+2370h]; hRequest
0x1800538e9  lea     rdx, [rdi+rsi]; lpBuffer
0x1800538ed  xor     r9d, r9d; lpdwNumberOfBytesRead
0x1800538f0  mov     r8d, ebp; dwNumberOfBytesToRead
0x1800538f3  call    cs:__imp_WinHttpReadData
0x1800538f9  test    eax, eax
0x1800538fb  jnz     short loc_180053922
0x1800538fd  call    cs:__imp_GetLastError
0x180053903  mov     rcx, [rbx+2340h]
0x18005390a  mov     edi, eax
0x18005390c  mov     edx, edi
0x18005390e  mov     rax, [rcx]
0x180053911  mov     rax, [rax+48h]
0x180053915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005391a  test    edi, edi
0x18005391c  jnz     loc_1800539A7
0x180053922  mov     rbx, [rsp+68h+arg_0]
0x180053927  mov     rbp, [rsp+68h+arg_8]
0x18005392c  add     rsp, 40h
0x180053930  pop     r15
0x180053932  pop     r14
0x180053934  pop     r12
0x180053936  pop     rdi
0x180053937  pop     rsi
0x180053938  retn
0x180053939  mov     rcx, rbx; this
0x18005393c  call    ?EndOfResponse@WSManHttpSenderConnection@@AEAAXXZ; WSManHttpSenderConnection::EndOfResponse(void)
0x180053941  jmp     short loc_180053922
0x180053943  test    dword ptr [rcx+1Ch], 400h
0x18005394a  jz      loc_1800538C4
0x180053950  mov     rax, [rbx+8]
0x180053954  mov     edx, 1A3h
0x180053959  mov     rcx, [rcx+10h]
0x18005395d  mov     r9, rbx
0x180053960  mov     [rsp+68h+var_40], ebp
0x180053964  mov     r8, r14
0x180053967  mov     [rsp+68h+var_48], rax
0x18005396c  call    WPP_SF_qqd
0x180053971  jmp     loc_1800538C4
0x180053976  mov     edi, 216h
0x18005397b  mov     rcx, [rbx+2340h]
0x180053982  mov     edx, edi
0x180053984  mov     rax, [rcx]
0x180053987  mov     rax, [rax+48h]
0x18005398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053990  mov     r8d, 2
0x180053996  mov     edx, edi
0x180053998  mov     rcx, rbx
0x18005399b  call    ?CompleteRequest@WSManHttpSenderConnection@@AEAAXKW4Event@IChannelObserver@@@Z; WSManHttpSenderConnection::CompleteRequest(ulong,IChannelObserver::Event)
0x1800539a0  jmp     short loc_180053922
0x1800539a2  mov     edi, 3E3h
0x1800539a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539ae  cmp     rcx, r15
0x1800539b1  jz      short loc_1800539CD
0x1800539b3  test    dword ptr [rcx+1Ch], 200h
0x1800539ba  jz      short loc_1800539CD
0x1800539bc  mov     rcx, [rcx+10h]
0x1800539c0  mov     edx, 0FCh
0x1800539c5  mov     r8, r14
0x1800539c8  call    WPP_SF_
0x1800539cd  xor     r8d, r8d
0x1800539d0  jmp     short loc_180053996
0x1800539d2  call    ?GetHeap@WSManMemory@@SAPEAXXZ; WSManMemory::GetHeap(void)
0x1800539d7  mov     r8, r15; lpMem
0x1800539da  xor     edx, edx; dwFlags
0x1800539dc  mov     rcx, rax; hHeap
0x1800539df  call    cs:__imp_HeapSize
0x1800539e5  cmp     rax, rbp
0x1800539e8  jb      loc_180053697
0x1800539ee  mov     rax, [rdi+20h]
0x1800539f2  mov     [rdi+28h], rax
0x1800539f6  jmp     loc_1800536D9
0x1800539fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a02  cmp     rcx, r15
0x180053a05  jz      loc_180053855
0x180053a0b  test    [rcx+1Ch], r12d
0x180053a0f  jz      loc_180053855
0x180053a15  mov     rcx, [rcx+10h]
0x180053a19  mov     edx, 0FAh
0x180053a1e  mov     r8, r14
0x180053a21  mov     dword ptr [rsp+68h+var_48], ebp
0x180053a25  call    WPP_SF_qD
0x180053a2a  jmp     loc_180053855
0x180053a2f  call    ?GetHeap@WSManMemory@@SAPEAXXZ; WSManMemory::GetHeap(void)
0x180053a34  mov     r8, r15; lpMem
0x180053a37  xor     edx, edx; dwFlags
0x180053a39  mov     rcx, rax; hHeap
0x180053a3c  call    cs:__imp_HeapSize
0x180053a42  cmp     rax, r12
0x180053a45  jb      loc_18005380A
0x180053a4b  mov     rax, [rdi+20h]
0x180053a4f  jmp     loc_180053845
0x180053a54  mov     ecx, eax; dwErrCode
0x180053a56  call    cs:__imp_SetLastError
0x180053a5c  mov     r9d, 54Fh; unsigned int
0x180053a62  mov     [rsp+68h+var_48], 0; struct IRequestContext *
0x180053a6b  lea     r8, a102; "102"
0x180053a72  mov     edx, 66h ; 'f'; unsigned int
0x180053a77  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x180053a7e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180053a83  jmp     loc_180053894
0x180053a88  mov     ecx, eax; dwErrCode
0x180053a8a  call    cs:__imp_SetLastError
0x180053a90  jmp     loc_1800538AB
0x180053a95  test    [rcx+1Ch], r12d
0x180053a99  jz      loc_18005372F
0x180053a9f  mov     rax, [rbx+8]
0x180053aa3  mov     edx, 1BFh
0x180053aa8  mov     rcx, [rcx+10h]
0x180053aac  mov     r9, rbx
0x180053aaf  mov     [rsp+68h+var_38], 2
0x180053ab7  mov     r8, r14
0x180053aba  mov     [rsp+68h+var_40], esi
0x180053abe  mov     [rsp+68h+var_48], rax
0x180053ac3  call    WPP_SF_qqdl
0x180053ac8  jmp     loc_18005372F
0x180053acd  test    [rcx+1Ch], r12d
0x180053ad1  jz      loc_180053779
0x180053ad7  mov     rcx, [rcx+10h]
0x180053adb  mov     edx, 1C0h
0x180053ae0  mov     r9, rbx
0x180053ae3  mov     r8, r14
0x180053ae6  call    WPP_SF_q
0x180053aeb  jmp     loc_180053779
0x180053af0  mov     edi, 0Eh
0x180053af5  jmp     loc_18005384E
0x180053afa  mov     edi, esi
0x180053afc  jmp     loc_1800536E5
0x180053b01  mov     r9d, 54Fh; unsigned int
0x180053b07  mov     [rsp+68h+var_48], 0; struct IRequestContext *
0x180053b10  lea     r8, a170; "170"
0x180053b17  mov     edx, 0AAh; unsigned int
0x180053b1c  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x180053b23  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180053b28  mov     rcx, [rbx+23A8h]; this
  ... truncated ...
```
