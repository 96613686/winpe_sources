# CSmsDeviceManager::Uninitialize(void)

- ea: `0x1800426a0`
- end: `0x180042af1`
- name: `?Uninitialize@CSmsDeviceManager@@UEAAJXZ`
- size: `1105`
- prototype: `__int64 __fastcall(CSmsDeviceManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003e138`

## callees

- `0x180003a60`
- `0x180003f50`
- `0x180028394`
- `0x18003d260`
- `0x18003d374`
- `0x18003db70`
- `0x18003e2a0`
- `0x1800426a0`
- `0x180042af8`
- `0x1800439fc`
- `0x180051420`
- `0x18006b4a0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042ac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042ac5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180042a29`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180042a82`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180042a29`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180042a82`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800428b6`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800428b6`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800427d4`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800427d4`

## string_xrefs

- `0x180042a44`: `UnregisterWaitEx(hWapMessageReadyWait, INVALID_HANDLE_VALUE)`
- `0x180042a9d`: `UnregisterWaitEx(hTextMessageReadyWait, INVALID_HANDLE_VALUE)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSmsDeviceManager::Uninitialize(CSmsDeviceManager *this)
{
  char *v2; // rdi
  _QWORD *v4; // r14
  __int64 *v5; // rbx
  _QWORD *v6; // r15
  __int64 v7; // rcx
  void *v8; // r12
  void *v9; // r13
  void *v10; // r15
  __int64 v11; // rbx
  char *v12; // rsi
  int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  unsigned int v18; // esi
  _QWORD *v19; // rdi
  _QWORD *i; // rbx
  __int64 *v21; // rbx
  __int64 **v22; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  _QWORD *v25; // rdi
  _QWORD *v26; // r14
  void *v27; // rbx
  _QWORD *v28; // rcx
  signed int LastError; // eax
  signed int v30; // eax
  HANDLE WaitHandle; // [rsp+20h] [rbp-118h]
  __int128 v32; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v33[120]; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v34; // [rsp+B8h] [rbp-80h]
  __int64 v35; // [rsp+C0h] [rbp-78h]

  v2 = (char *)this + 72;
  (**((void (__fastcall ***)(char *))this + 9))((char *)this + 72);
  if ( *((_DWORD *)this + 5) )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
    return 0;
  }
  else
  {
    *((_DWORD *)this + 3) = 0;
    *((_DWORD *)this + 5) = 1;
    v4 = (_QWORD *)*((_QWORD *)this + 26);
    v5 = (__int64 *)v4[1];
    while ( !*((_BYTE *)v5 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<ATL::CComPtr<ISmsDevice>>>::_Erase_tree<std::allocator<std::_Tree_node<ATL::CComPtr<ISmsDevice>,void *>>>(
        (__int64)this + 208,
        (__int64)this + 208,
        (__int64 *)v5[2]);
      v6 = v5;
      v5 = (__int64 *)*v5;
      v7 = v6[4];
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      operator delete(v6);
    }
    v4[1] = v4;
    *v4 = v4;
    v4[2] = v4;
    *((_QWORD *)this + 27) = 0;
    v8 = (void *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = 0;
    v9 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = 0;
    WaitHandle = (HANDLE)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = 0;
    v10 = (void *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
    v11 = 0;
    v12 = (char *)this + 72;
    (**((void (__fastcall ***)(char *))this + 9))((char *)this + 72);
    if ( *((_QWORD *)this + 8) )
    {
      v11 = *((_QWORD *)this + 8);
      *((_QWORD *)this + 8) = 0;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))((char *)this + 72);
    if ( v11 )
      UnsubscribeServiceChangeNotifications(v11);
    (**((void (__fastcall ***)(char *))this + 40))((char *)this + 320);
    *((_DWORD *)this + 100) = 0;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 40) + 8LL))((char *)this + 320);
    CExecutionManager::Uninitialize((CSmsDeviceManager *)((char *)this + 312));
    v14 = *((_QWORD *)this + 15);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 48LL))(*((_QWORD *)this + 15));
      v15 = *((_QWORD *)this + 15);
      if ( v15 )
      {
        *((_QWORD *)this + 15) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    v16 = CSmsDeviceManager::UninitializeWwanWatcher((CSmsDeviceManager *)((char *)this - 24), v13);
    if ( v16 < 0 )
      LogSmsRouterError("CSmsDeviceManager::Uninitialize", 0x6D2u, v16, "UninitializeWwanWatcher");
    (**(void (__fastcall ***)(char *))v12)((char *)this + 72);
    v17 = *((_QWORD *)this + 28);
    *((_QWORD *)this + 28) = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))((char *)this + 72);
    if ( v17 )
      DevCloseObjectQuery(v17);
    v18 = 0;
    v19 = (_QWORD *)*((_QWORD *)this + 19);
    for ( i = (_QWORD *)*v19; i != v19; i = (_QWORD *)*i )
    {
      SmsDeviceInformation::SmsDeviceInformation(
        (SmsDeviceInformation *)((char *)&v32 + 8),
        (const struct SmsDeviceInformation *)(i + 3));
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
      SmsDeviceInformation::~SmsDeviceInformation((SmsDeviceInformation *)((char *)&v32 + 8));
    }
    std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::clear((char *)this + 144);
    v21 = (__int64 *)**((_QWORD **)this + 35);
    while ( !*((_BYTE *)v21 + 25) )
    {
      v32 = *((_OWORD *)v21 + 2);
      SmsDeviceInformation::SmsDeviceInformation(
        (SmsDeviceInformation *)v33,
        (const struct SmsDeviceInformation *)(v21 + 6));
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 32LL))(v35);
      SmsDeviceInformation::~SmsDeviceInformation((SmsDeviceInformation *)v33);
      v22 = (__int64 **)v21[2];
      if ( *((_BYTE *)v22 + 25) )
      {
        for ( j = (__int64 *)v21[1]; !*((_BYTE *)j + 25) && v21 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v21 = j;
        v21 = j;
      }
      else
      {
        v21 = (__int64 *)v21[2];
        for ( k = *v22; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          v21 = k;
      }
    }
    v25 = (_QWORD *)*((_QWORD *)this + 35);
    v26 = (_QWORD *)v25[1];
    while ( !*((_BYTE *)v26 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SmsDeviceInformation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,SmsDeviceInformation>,void *>>>(
        (char *)this + 280,
        (char *)this + 280,
        v26[2]);
      v27 = v26;
      v28 = v26;
      v26 = (_QWORD *)*v26;
      SmsDeviceInformation::~SmsDeviceInformation((SmsDeviceInformation *)(v28 + 6));
      operator delete(v27);
    }
    v25[1] = v25;
    *v25 = v25;
    v25[2] = v25;
    *((_QWORD *)this + 36) = 0;
    if ( v8 && !UnregisterWaitEx(v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      LogSmsRouterError(
        "CSmsDeviceManager::Uninitialize",
        0x6F3u,
        v18,
        "UnregisterWaitEx(hWapMessageReadyWait, INVALID_HANDLE_VALUE)");
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( v9 )
      CloseHandle(v9);
    if ( WaitHandle && !UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v30 = GetLastError();
      v18 = v30;
      if ( v30 > 0 )
        v18 = (unsigned __int16)v30 | 0x80070000;
      LogSmsRouterError(
        "CSmsDeviceManager::Uninitialize",
        0x705u,
        v18,
        "UnregisterWaitEx(hTextMessageReadyWait, INVALID_HANDLE_VALUE)");
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( v10 )
      CloseHandle(v10);
    return v18;
  }
}

```

## disassembly

```asm
0x1800426a0  push    rbx
0x1800426a2  push    rbp
0x1800426a3  push    rsi
0x1800426a4  push    rdi
0x1800426a5  push    r12
0x1800426a7  push    r13
0x1800426a9  push    r14
0x1800426ab  push    r15
0x1800426ad  sub     rsp, 0F8h
0x1800426b4  mov     rax, cs:__security_cookie
0x1800426bb  xor     rax, rsp
0x1800426be  mov     [rsp+138h+var_58], rax
0x1800426c6  mov     rbp, rcx
0x1800426c9  lea     rdi, [rcx+48h]
0x1800426cd  mov     rax, [rdi]
0x1800426d0  mov     rcx, rdi
0x1800426d3  mov     rax, [rax]
0x1800426d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426db  xor     ecx, ecx
0x1800426dd  cmp     [rbp+14h], ecx
0x1800426e0  jz      short loc_1800426F9
0x1800426e2  mov     rax, [rdi]
0x1800426e5  mov     rcx, rdi
0x1800426e8  mov     rax, [rax+8]
0x1800426ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426f1  nop
0x1800426f2  xor     eax, eax
0x1800426f4  jmp     loc_180042ACD
0x1800426f9  mov     [rbp+0Ch], ecx
0x1800426fc  mov     dword ptr [rbp+14h], 1
0x180042703  lea     rsi, [rbp+0D0h]
0x18004270a  mov     r14, [rsi]
0x18004270d  mov     rbx, [r14+8]
0x180042711  jmp     short loc_18004274D
0x180042713  mov     r8, [rbx+10h]
0x180042717  mov     rdx, rsi
0x18004271a  mov     rcx, rsi
0x18004271d  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$CComPtr@UISmsDevice@@@ATL@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$CComPtr@UISmsDevice@@@ATL@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$CComPtr@UISmsDevice@@@ATL@@PEAX@std@@@1@PEAU?$_Tree_node@V?$CComPtr@UISmsDevice@@@ATL@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CComPtr<ISmsDevice>>>::_Erase_tree<std::allocator<std::_Tree_node<ATL::CComPtr<ISmsDevice>,void *>>>(std::allocator<std::_Tree_node<ATL::CComPtr<ISmsDevice>,void *>> &,std::_Tree_node<ATL::CComPtr<ISmsDevice>,void *> *)
0x180042722  mov     r15, rbx
0x180042725  mov     rbx, [rbx]
0x180042728  mov     rcx, [r15+20h]
0x18004272c  test    rcx, rcx
0x18004272f  jz      short loc_18004273E
0x180042731  mov     rax, [rcx]
0x180042734  mov     rax, [rax+10h]
0x180042738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004273d  nop
0x18004273e  mov     edx, 28h ; '('
0x180042743  mov     rcx, r15; Block
0x180042746  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004274b  xor     ecx, ecx
0x18004274d  cmp     [rbx+19h], cl
0x180042750  jz      short loc_180042713
0x180042752  mov     [r14+8], r14
0x180042756  mov     [r14], r14
0x180042759  mov     [r14+10h], r14
0x18004275d  mov     [rsi+8], rcx
0x180042761  mov     r12, [rbp+38h]
0x180042765  mov     [rbp+38h], rcx
0x180042769  mov     r13, [rbp+28h]
0x18004276d  mov     [rbp+28h], rcx
0x180042771  mov     rax, [rbp+30h]
0x180042775  mov     [rsp+138h+WaitHandle], rax
0x18004277a  mov     [rbp+30h], rcx
0x18004277e  mov     r15, [rbp+20h]
0x180042782  mov     [rbp+20h], rcx
0x180042786  mov     rax, [rdi]
0x180042789  mov     rcx, rdi
0x18004278c  mov     rax, [rax+8]
0x180042790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042795  nop
0x180042796  xor     ebx, ebx
0x180042798  lea     rsi, [rbp+48h]
0x18004279c  mov     rax, [rsi]
0x18004279f  mov     rcx, rsi
0x1800427a2  mov     rax, [rax]
0x1800427a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427aa  cmp     [rbp+40h], rbx
0x1800427ae  jz      short loc_1800427BC
0x1800427b0  mov     rbx, [rbp+40h]
0x1800427b4  mov     qword ptr [rbp+40h], 0
0x1800427bc  mov     rax, [rsi]
0x1800427bf  mov     rcx, rsi
0x1800427c2  mov     rax, [rax+8]
0x1800427c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427cb  nop
0x1800427cc  test    rbx, rbx
0x1800427cf  jz      short loc_1800427DA
0x1800427d1  mov     rcx, rbx
0x1800427d4  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x1800427da  lea     rdi, [rbp+138h]
0x1800427e1  lea     rbx, [rdi+8]
0x1800427e5  mov     rax, [rbx]
0x1800427e8  mov     rcx, rbx
0x1800427eb  mov     rax, [rax]
0x1800427ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427f3  mov     dword ptr [rdi+58h], 0
0x1800427fa  mov     rax, [rbx]
0x1800427fd  mov     rcx, rbx
0x180042800  mov     rax, [rax+8]
0x180042804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042809  nop
0x18004280a  mov     rcx, rdi; this
0x18004280d  call    ?Uninitialize@CExecutionManager@@QEAAJXZ; CExecutionManager::Uninitialize(void)
0x180042812  mov     rcx, [rbp+78h]
0x180042816  test    rcx, rcx
0x180042819  jz      short loc_180042856
0x18004281b  mov     rax, [rcx]
0x18004281e  mov     rax, [rax+28h]
0x180042822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042827  mov     rcx, [rbp+78h]
0x18004282b  mov     rax, [rcx]
0x18004282e  mov     rax, [rax+30h]
0x180042832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042837  nop
0x180042838  mov     rcx, [rbp+78h]
0x18004283c  test    rcx, rcx
0x18004283f  jz      short loc_180042856
0x180042841  mov     qword ptr [rbp+78h], 0
0x180042849  mov     rax, [rcx]
0x18004284c  mov     rax, [rax+10h]
0x180042850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042855  nop
0x180042856  lea     rcx, [rbp-18h]; this
0x18004285a  call    ?UninitializeWwanWatcher@CSmsDeviceManager@@AEAAJH@Z; CSmsDeviceManager::UninitializeWwanWatcher(int)
0x18004285f  test    eax, eax
0x180042861  jns     short loc_18004287E
0x180042863  lea     r9, aUninitializeww; "UninitializeWwanWatcher"
0x18004286a  mov     r8d, eax; int
0x18004286d  mov     edx, 6D2h; unsigned int
0x180042872  lea     rcx, aCsmsdevicemana_1; "CSmsDeviceManager::Uninitialize"
0x180042879  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004287e  mov     rax, [rsi]
0x180042881  mov     rcx, rsi
0x180042884  mov     rax, [rax]
0x180042887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004288c  mov     rbx, [rbp+0E0h]
0x180042893  mov     qword ptr [rbp+0E0h], 0
0x18004289e  mov     rax, [rsi]
0x1800428a1  mov     rcx, rsi
0x1800428a4  mov     rax, [rax+8]
0x1800428a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428ad  nop
0x1800428ae  test    rbx, rbx
0x1800428b1  jz      short loc_1800428BC
0x1800428b3  mov     rcx, rbx
0x1800428b6  call    cs:__imp_DevCloseObjectQuery
0x1800428bc  xor     esi, esi
0x1800428be  lea     r14, [rbp+90h]
0x1800428c5  mov     rdi, [r14+8]
0x1800428c9  mov     rbx, [rdi]
0x1800428cc  cmp     rbx, rdi
0x1800428cf  jz      short loc_180042912
0x1800428d1  mov     rax, [rbx+10h]
0x1800428d5  mov     qword ptr [rsp+138h+var_108], rax
0x1800428da  lea     rdx, [rbx+18h]; struct SmsDeviceInformation *
0x1800428de  lea     rcx, [rsp+138h+var_108+8]; this
0x1800428e3  call    ??0SmsDeviceInformation@@QEAA@AEBU0@@Z; SmsDeviceInformation::SmsDeviceInformation(SmsDeviceInformation const &)
0x1800428e8  nop
0x1800428e9  mov     rcx, [rsp+138h+var_80]
0x1800428f1  test    rcx, rcx
0x1800428f4  jz      short loc_180042903
0x1800428f6  mov     rax, [rcx]
0x1800428f9  mov     rax, [rax+20h]
0x1800428fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042902  nop
0x180042903  lea     rcx, [rsp+138h+var_108+8]; this
0x180042908  call    ??1SmsDeviceInformation@@QEAA@XZ; SmsDeviceInformation::~SmsDeviceInformation(void)
0x18004290d  mov     rbx, [rbx]
0x180042910  jmp     short loc_1800428CC
0x180042912  mov     rcx, r14
0x180042915  call    ?clear@?$_Hash@V?$_Hmap_traits@PEAUISmsModel@@USmsDeviceInformation@@V?$hash_compare@PEAUISmsModel@@U?$less@PEAUISmsModel@@@std@@@stdext@@V?$allocator@U?$pair@QEAUISmsModel@@USmsDeviceInformation@@@std@@@std@@$0A@@stdext@@@std@@QEAAXXZ; std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::clear(void)
0x18004291a  mov     rbx, [rbp+118h]
0x180042921  mov     rbx, [rbx]
0x180042924  xor     edi, edi
0x180042926  cmp     [rbx+19h], dil
0x18004292a  jnz     loc_1800429B5
0x180042930  movups  xmm0, xmmword ptr [rbx+20h]
0x180042934  movdqu  [rsp+138h+var_108], xmm0
0x18004293a  lea     rdx, [rbx+30h]; struct SmsDeviceInformation *
0x18004293e  lea     rcx, [rsp+138h+var_F8]; this
0x180042943  call    ??0SmsDeviceInformation@@QEAA@AEBU0@@Z; SmsDeviceInformation::SmsDeviceInformation(SmsDeviceInformation const &)
0x180042948  nop
0x180042949  mov     rcx, [rsp+138h+var_78]
0x180042951  test    rcx, rcx
0x180042954  jz      short loc_180042963
0x180042956  mov     rax, [rcx]
0x180042959  mov     rax, [rax+20h]
0x18004295d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042962  nop
0x180042963  lea     rcx, [rsp+138h+var_F8]; this
0x180042968  call    ??1SmsDeviceInformation@@QEAA@XZ; SmsDeviceInformation::~SmsDeviceInformation(void)
0x18004296d  mov     rcx, [rbx+10h]
0x180042971  cmp     [rcx+19h], dil
0x180042975  jz      short loc_180042995
0x180042977  mov     rax, [rbx+8]
0x18004297b  jmp     short loc_18004298A
0x18004297d  cmp     rbx, [rax+10h]
0x180042981  jnz     short loc_180042990
0x180042983  mov     rbx, rax
0x180042986  mov     rax, [rax+8]
0x18004298a  cmp     [rax+19h], dil
0x18004298e  jz      short loc_18004297D
0x180042990  mov     rbx, rax
0x180042993  jmp     short loc_180042926
0x180042995  mov     rbx, rcx
0x180042998  mov     rcx, [rcx]
0x18004299b  cmp     [rcx+19h], dil
0x18004299f  jnz     short loc_180042926
0x1800429a1  mov     rbx, rcx
0x1800429a4  mov     rax, [rcx]
0x1800429a7  mov     rcx, rax
0x1800429aa  cmp     [rax+19h], dil
0x1800429ae  jz      short loc_1800429A1
0x1800429b0  jmp     loc_180042926
0x1800429b5  mov     rdi, [rbp+118h]
0x1800429bc  mov     r14, [rdi+8]
0x1800429c0  jmp     short loc_1800429F8
0x1800429c2  mov     r8, [r14+10h]
0x1800429c6  lea     rdx, [rbp+118h]
0x1800429cd  lea     rcx, [rbp+118h]
0x1800429d4  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SmsDeviceInformation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,SmsDeviceInformation>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,SmsDeviceInformation>,void *>> &,std::_Tree_node<std::pair<_GUID const,SmsDeviceInformation>,void *> *)
0x1800429d9  mov     rbx, r14
0x1800429dc  mov     rcx, r14
0x1800429df  mov     r14, [r14]
0x1800429e2  add     rcx, 30h ; '0'; this
0x1800429e6  call    ??1SmsDeviceInformation@@QEAA@XZ; SmsDeviceInformation::~SmsDeviceInformation(void)
0x1800429eb  mov     edx, 0D0h
0x1800429f0  mov     rcx, rbx; Block
0x1800429f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800429f8  cmp     byte ptr [r14+19h], 0
0x1800429fd  jz      short loc_1800429C2
0x1800429ff  mov     [rdi+8], rdi
0x180042a03  mov     [rdi], rdi
0x180042a06  mov     [rdi+10h], rdi
0x180042a0a  mov     qword ptr [rbp+120h], 0
0x180042a15  mov     ebx, 80070000h
0x180042a1a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180042a1e  test    r12, r12
0x180042a21  jz      short loc_180042A64
0x180042a23  mov     rdx, rdi; CompletionEvent
0x180042a26  mov     rcx, r12; WaitHandle
0x180042a29  call    cs:__imp_UnregisterWaitEx
0x180042a2f  test    eax, eax
0x180042a31  jnz     short loc_180042A64
0x180042a33  call    cs:__imp_GetLastError
0x180042a39  mov     esi, eax
0x180042a3b  test    eax, eax
0x180042a3d  jle     short loc_180042A44
0x180042a3f  movzx   esi, ax
0x180042a42  or      esi, ebx
0x180042a44  lea     r9, aUnregisterwait_0; "UnregisterWaitEx(hWapMessageReadyWait, "...
0x180042a4b  mov     r8d, esi; int
0x180042a4e  mov     edx, 6F3h; unsigned int
0x180042a53  lea     rcx, aCsmsdevicemana_1; "CSmsDeviceManager::Uninitialize"
0x180042a5a  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180042a5f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180042a64  test    r13, r13
0x180042a67  jz      short loc_180042A72
0x180042a69  mov     rcx, r13; hObject
0x180042a6c  call    cs:__imp_CloseHandle
0x180042a72  mov     rax, [rsp+138h+WaitHandle]
0x180042a77  test    rax, rax
0x180042a7a  jz      short loc_180042ABD
0x180042a7c  mov     rdx, rdi; CompletionEvent
0x180042a7f  mov     rcx, rax; WaitHandle
0x180042a82  call    cs:__imp_UnregisterWaitEx
0x180042a88  test    eax, eax
0x180042a8a  jnz     short loc_180042ABD
0x180042a8c  call    cs:__imp_GetLastError
0x180042a92  mov     esi, eax
0x180042a94  test    eax, eax
0x180042a96  jle     short loc_180042A9D
0x180042a98  movzx   esi, ax
0x180042a9b  or      esi, ebx
0x180042a9d  lea     r9, aUnregisterwait; "UnregisterWaitEx(hTextMessageReadyWait,"...
0x180042aa4  mov     r8d, esi; int
0x180042aa7  mov     edx, 705h; unsigned int
0x180042aac  lea     rcx, aCsmsdevicemana_1; "CSmsDeviceManager::Uninitialize"
0x180042ab3  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180042ab8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180042abd  test    r15, r15
0x180042ac0  jz      short loc_180042ACB
0x180042ac2  mov     rcx, r15; hObject
0x180042ac5  call    cs:__imp_CloseHandle
0x180042acb  mov     eax, esi
0x180042acd  mov     rcx, [rsp+138h+var_58]
0x180042ad5  xor     rcx, rsp; StackCookie
0x180042ad8  call    __security_check_cookie
0x180042add  add     rsp, 0F8h
0x180042ae4  pop     r15
0x180042ae6  pop     r14
0x180042ae8  pop     r13
0x180042aea  pop     r12
0x180042aec  pop     rdi
0x180042aed  pop     rsi
0x180042aee  pop     rbp
0x180042aef  pop     rbx
0x180042af0  retn
```
