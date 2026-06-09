# CSessionManager::Add(ulong)

- ea: `0x18000b4a0`
- end: `0x18000b7c6`
- name: `?Add@CSessionManager@@SAJK@Z`
- size: `806`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006130`
- `0x18000b7cc`

## callees

- `0x180001444`
- `0x180006d40`
- `0x1800071d4`
- `0x180007248`
- `0x1800080dc`
- `0x18000a9f8`
- `0x18000ac3c`
- `0x18000add0`
- `0x18000ae30`
- `0x18000b370`
- `0x18000b4a0`
- `0x18000ba94`
- `0x18000bb00`
- `0x18000be90`
- `0x18000bedc`
- `0x18000c428`
- `0x18000c498`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6da`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b755`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b755`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b6cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b6cf`

## pseudocode

```c
__int64 __fastcall CSessionManager::Add(unsigned int a1)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  _QWORD *v4; // rax
  struct CSessionManager *v5; // rax
  struct CSessionManager *v6; // rax
  struct CSessionManager *v7; // rax
  unsigned int v8; // edi
  struct CSessionManager *v9; // rax
  __int64 v10; // rax
  struct CSessionManager *v11; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  __int64 v14; // rcx
  __int64; // rax
  int v16; // [rsp+30h] [rbp-88h] BYREF
  PVOID pv; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-78h] BYREF
  int v19; // [rsp+48h] [rbp-70h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-68h] BYREF
  _QWORD *v21; // [rsp+58h] [rbp-60h] BYREF
  __int64 v22; // [rsp+60h] [rbp-58h] BYREF
  std::_Ref_count_base *v23; // [rsp+68h] [rbp-50h]
  _QWORD v24[3]; // [rsp+70h] [rbp-48h] BYREF
  char v25[24]; // [rsp+88h] [rbp-30h] BYREF

  v18 = a1;
  v16 = 0;
  v19 = 0;
  strcpy(v25, "CSessionManager::Add");
  v24[0] = v25;
  v24[1] = &v19;
  v24[2] = &v16;
  lambda_d42e68d5593f7c83f3dd494735831e39_::operator()(v24);
  v19 = 1;
  v21 = v24;
  v16 = CSessionManager::Remove(a1);
  if ( v16 >= 0 )
  {
    pv = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v4 = operator new(0x10u);
      if ( v4 )
      {
        *v4 = 0;
        v4[1] = 0;
      }
      else
      {
        v4 = 0;
      }
      std::unique_ptr<std::shared_ptr<CSession>>::reset((_QWORD **)&pv, v4);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v16 = -2147024882;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000B78B);
        std::unique_ptr<std::shared_ptr<CSession>>::_Delete((_QWORD **)&pv);
        WppTraceUnwinder__lambda_d42e68d5593f7c83f3dd494735831e39____::_WppTraceUnwinder__lambda_d42e68d5593f7c83f3dd494735831e39____(&v21);
         = 2147942414LL;
LABEL_48:
        ;
      }
    }
    v5 = CSessionManager::Instance();
    Microsoft::WRL::Wrappers::CriticalSection::Lock(
      &lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16));
    v6 = CSessionManager::Instance();
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CSession>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CSession>>>,0>>::find(
      v6,
      &v22,
      &v18);
    v7 = CSessionManager::Instance();
    if ( v22 == *(_QWORD *)v7 )
    {
      if ( __eh34_try(-1, 2) )
      {
        __eh34_scope_strut(2);
        std::make_shared<CSession,unsigned long &>();
        v9 = CSessionManager::Instance();
        v10 = std::map<unsigned long,std::shared_ptr<CSession>>::operator[](v9, &v18);
        std::shared_ptr<CSession>::operator=(v10, &v22);
        std::shared_ptr<CSession>::operator=(pv, &v22);
        if ( v23 )
          std::_Ref_count_base::_Decref(v23);
      }
      if ( __eh34_catch(2) )
      {
        if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          v16 = -2147024882;
          __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18000B75D);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          std::unique_ptr<std::shared_ptr<CSession>>::_Delete((_QWORD **)&pv);
          v3 = -2147024882;
          goto LABEL_36;
        }
      }
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      v11 = CSessionManager::Instance();
      ThreadpoolWork = CreateThreadpoolWork(pfnwk, pv, (PTP_CALLBACK_ENVIRON)((char *)v11 + 56));
      if ( ThreadpoolWork )
      {
        pv = 0;
        SubmitThreadpoolWork(ThreadpoolWork);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v16 = LastError;
        WppTraceIndent(v14, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (int)&WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids,
            (int)WPP_pszIndent,
            v16);
        }
      }
      v3 = v16;
      std::unique_ptr<std::shared_ptr<CSession>>::_Delete((_QWORD **)&pv);
      goto LABEL_36;
    }
    WppTraceIndent(*(_QWORD *)v7, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (int)&WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids,
        (int)WPP_pszIndent,
        a1);
    }
    v8 = v16;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    std::unique_ptr<std::shared_ptr<CSession>>::_Delete((_QWORD **)&pv);
    v3 = v8;
  }
  else
  {
    WppTraceIndent(v2, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (int)&WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids,
        (int)WPP_pszIndent,
        a1,
        v16);
    }
    v3 = v16;
  }
LABEL_36:
  WppTraceUnwinder__lambda_d42e68d5593f7c83f3dd494735831e39____::_WppTraceUnwinder__lambda_d42e68d5593f7c83f3dd494735831e39____(&v21);
   = v3;
  goto LABEL_48;
}

```

## disassembly

```asm
0x18000b4a0  mov     r11, rsp
0x18000b4a3  mov     [r11+10h], rbx
0x18000b4a7  push    rdi
0x18000b4a8  sub     rsp, 0B0h
0x18000b4af  mov     rax, cs:__security_cookie
0x18000b4b6  xor     rax, rsp
0x18000b4b9  mov     [rsp+0B8h+var_18], rax
0x18000b4c1  mov     edi, ecx
0x18000b4c3  mov     [rsp+0B8h+var_78], ecx
0x18000b4c7  xor     ebx, ebx
0x18000b4c9  mov     [rsp+0B8h+var_88], ebx
0x18000b4cd  mov     [rsp+0B8h+var_70], ebx
0x18000b4d1  movups  xmm0, xmmword ptr cs:aCsessionmanage; "CSessionManager::Add"
0x18000b4d8  movups  xmmword ptr [r11-30h], xmm0
0x18000b4dd  movsd   xmm1, qword ptr cs:aCsessionmanage+0Dh; "er::Add"
0x18000b4e5  movsd   qword ptr [r11-23h], xmm1
0x18000b4eb  lea     rax, [r11-30h]
0x18000b4ef  mov     [r11-48h], rax
0x18000b4f3  lea     rax, [r11-70h]
0x18000b4f7  mov     [r11-40h], rax
0x18000b4fb  lea     rax, [rsp+0B8h+var_88]
0x18000b500  mov     [r11-38h], rax
0x18000b504  lea     rcx, [r11-48h]
0x18000b508  call    _lambda_d42e68d5593f7c83f3dd494735831e39___operator__
0x18000b50d  mov     [rsp+0B8h+var_70], 1
0x18000b515  lea     rax, [rsp+0B8h+var_48]
0x18000b51a  mov     [rsp+0B8h+var_60], rax
0x18000b51f  mov     ecx, edi; unsigned int
0x18000b521  call    ?Remove@CSessionManager@@SAJK@Z; CSessionManager::Remove(ulong)
0x18000b526  mov     [rsp+0B8h+var_88], eax
0x18000b52a  test    eax, eax
0x18000b52c  jns     short loc_18000B584
0x18000b52e  lea     edx, [rbx+2]
0x18000b531  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b536  lea     rax, WPP_GLOBAL_Control
0x18000b53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b544  cmp     rcx, rax
0x18000b547  jz      short loc_18000B57B
0x18000b549  test    byte ptr [rcx+1Ch], 1
0x18000b54d  jz      short loc_18000B57B
0x18000b54f  cmp     byte ptr [rcx+19h], 2
0x18000b553  jb      short loc_18000B57B
0x18000b555  lea     edx, [rbx+11h]
0x18000b558  mov     eax, [rsp+0B8h+var_88]
0x18000b55c  mov     [rsp+0B8h+var_90], eax
0x18000b560  mov     [rsp+0B8h+var_98], edi
0x18000b564  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000b56b  lea     r8, WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids
0x18000b572  mov     rcx, [rcx+10h]
0x18000b576  call    WPP_SF_sdd
0x18000b57b  mov     ebx, [rsp+0B8h+var_88]
0x18000b57f  jmp     loc_18000B77D
0x18000b584  mov     [rsp+0B8h+pv], rbx
0x18000b589  mov     ecx, 10h; Size
0x18000b58e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b593  test    rax, rax
0x18000b596  jz      short loc_18000B5A1
0x18000b598  mov     [rax], rbx
0x18000b59b  mov     [rax+8], rbx
0x18000b59f  jmp     short loc_18000B5A4
0x18000b5a1  mov     rax, rbx
0x18000b5a4  mov     rdx, rax
0x18000b5a7  lea     rcx, [rsp+0B8h+pv]
0x18000b5ac  call    ?reset@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@QEAAXPEAV?$shared_ptr@VCSession@@@2@@Z; std::unique_ptr<std::shared_ptr<CSession>>::reset(std::shared_ptr<CSession> *)
0x18000b5b1  nop
0x18000b5b2  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b5b7  lea     rdx, [rax+10h]
0x18000b5bb  lea     rcx, [rsp+0B8h+lpCriticalSection]
0x18000b5c0  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@SA?AVSyncLockCriticalSection@Details@234@PEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::CriticalSection::Lock(_RTL_CRITICAL_SECTION *)
0x18000b5c5  nop
0x18000b5c6  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b5cb  lea     r8, [rsp+0B8h+var_78]
0x18000b5d0  lea     rdx, [rsp+0B8h+var_58]
0x18000b5d5  mov     rcx, rax
0x18000b5d8  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VCSession@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CSession>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CSession>>>,0>>::find(ulong const &)
0x18000b5dd  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b5e2  mov     rcx, [rax]
0x18000b5e5  cmp     [rsp+0B8h+var_58], rcx
0x18000b5ea  jz      short loc_18000B65B
0x18000b5ec  mov     edx, 2
0x18000b5f1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b5f6  lea     rax, WPP_GLOBAL_Control
0x18000b5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b604  cmp     rcx, rax
0x18000b607  jz      short loc_18000B635
0x18000b609  test    byte ptr [rcx+1Ch], 1
0x18000b60d  jz      short loc_18000B635
0x18000b60f  cmp     byte ptr [rcx+19h], 4
0x18000b613  jb      short loc_18000B635
0x18000b615  mov     edx, 15h
0x18000b61a  mov     [rsp+0B8h+var_98], edi
0x18000b61e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000b625  lea     r8, WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids
0x18000b62c  mov     rcx, [rcx+10h]
0x18000b630  call    WPP_SF_sd
0x18000b635  mov     edi, [rsp+0B8h+var_88]
0x18000b639  mov     rcx, [rsp+0B8h+lpCriticalSection]; lpCriticalSection
0x18000b63e  test    rcx, rcx
0x18000b641  jz      short loc_18000B64A
0x18000b643  call    cs:__imp_LeaveCriticalSection
0x18000b649  nop
0x18000b64a  lea     rcx, [rsp+0B8h+pv]
0x18000b64f  call    ?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::shared_ptr<CSession>>::_Delete(void)
0x18000b654  mov     ebx, edi
0x18000b656  jmp     loc_18000B77D
0x18000b65b  lea     rdx, [rsp+0B8h+var_78]
0x18000b660  lea     rcx, [rsp+0B8h+var_58]
0x18000b665  call    ??$make_shared@VCSession@@AEAK@std@@YA?AV?$shared_ptr@VCSession@@@0@AEAK@Z; std::make_shared<CSession,ulong &>(ulong &)
0x18000b66a  nop
0x18000b66b  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b670  lea     rdx, [rsp+0B8h+var_78]
0x18000b675  mov     rcx, rax
0x18000b678  call    ??A?$map@KV?$shared_ptr@VCSession@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VCSession@@@1@AEBK@Z; std::map<ulong,std::shared_ptr<CSession>>::operator[](ulong const &)
0x18000b67d  lea     rdx, [rsp+0B8h+var_58]
0x18000b682  mov     rcx, rax
0x18000b685  call    ??4?$shared_ptr@VCSession@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CSession>::operator=(std::shared_ptr<CSession> const &)
0x18000b68a  lea     rdx, [rsp+0B8h+var_58]
0x18000b68f  mov     rcx, [rsp+0B8h+pv]
0x18000b694  call    ??4?$shared_ptr@VCSession@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CSession>::operator=(std::shared_ptr<CSession> const &)
0x18000b699  nop
0x18000b69a  mov     rcx, [rsp+0B8h+var_50]; this
0x18000b69f  test    rcx, rcx
0x18000b6a2  jz      short loc_18000B6AA
0x18000b6a4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000b6a9  nop
0x18000b6aa  mov     rcx, [rsp+0B8h+lpCriticalSection]; lpCriticalSection
0x18000b6af  test    rcx, rcx
0x18000b6b2  jz      short loc_18000B6BA
0x18000b6b4  call    cs:__imp_LeaveCriticalSection
0x18000b6ba  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000b6bf  lea     r8, [rax+38h]; pcbe
0x18000b6c3  mov     rdx, [rsp+0B8h+pv]; pv
0x18000b6c8  mov     rcx, cs:pfnwk; pfnwk
0x18000b6cf  call    cs:__imp_CreateThreadpoolWork
0x18000b6d5  test    rax, rax
0x18000b6d8  jnz     short loc_18000B74D
0x18000b6da  call    cs:__imp_GetLastError
0x18000b6e0  test    eax, eax
0x18000b6e2  jle     short loc_18000B6EC
0x18000b6e4  movzx   eax, ax
0x18000b6e7  or      eax, 80070000h
0x18000b6ec  mov     [rsp+0B8h+var_88], eax
0x18000b6f0  mov     edx, 2
0x18000b6f5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b6fa  lea     rax, WPP_GLOBAL_Control
0x18000b701  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b708  cmp     rcx, rax
0x18000b70b  jz      short loc_18000B73D
0x18000b70d  test    byte ptr [rcx+1Ch], 1
0x18000b711  jz      short loc_18000B73D
0x18000b713  cmp     byte ptr [rcx+19h], 2
0x18000b717  jb      short loc_18000B73D
0x18000b719  mov     edx, 16h
0x18000b71e  mov     eax, [rsp+0B8h+var_88]
0x18000b722  mov     [rsp+0B8h+var_98], eax
0x18000b726  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000b72d  lea     r8, WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids
0x18000b734  mov     rcx, [rcx+10h]
0x18000b738  call    WPP_SF_sd
0x18000b73d  mov     ebx, [rsp+0B8h+var_88]
0x18000b741  lea     rcx, [rsp+0B8h+pv]
0x18000b746  call    ?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::shared_ptr<CSession>>::_Delete(void)
0x18000b74b  jmp     short loc_18000B77D
0x18000b74d  mov     [rsp+0B8h+pv], rbx
0x18000b752  mov     rcx, rax; pwk
0x18000b755  call    cs:__imp_SubmitThreadpoolWork
0x18000b75b  jmp     short loc_18000B73D
0x18000b75d  mov     rcx, [rsp+0B8h+lpCriticalSection]; lpCriticalSection
0x18000b762  test    rcx, rcx
0x18000b765  jz      short loc_18000B76E
0x18000b767  call    cs:__imp_LeaveCriticalSection
0x18000b76d  nop
0x18000b76e  lea     rcx, [rsp+0B8h+pv]
0x18000b773  call    ?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::shared_ptr<CSession>>::_Delete(void)
0x18000b778  mov     ebx, 8007000Eh
0x18000b77d  lea     rcx, [rsp+0B8h+var_60]
0x18000b782  call    WppTraceUnwinder__lambda_d42e68d5593f7c83f3dd494735831e39_______WppTraceUnwinder__lambda_d42e68d5593f7c83f3dd494735831e39____
0x18000b787  mov     eax, ebx
0x18000b789  jmp     short loc_18000B7A5
0x18000b78b  lea     rcx, [rsp+0B8h+pv]
0x18000b790  call    ?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::shared_ptr<CSession>>::_Delete(void)
0x18000b795  nop
0x18000b796  lea     rcx, [rsp+0B8h+var_60]
0x18000b79b  call    WppTraceUnwinder__lambda_d42e68d5593f7c83f3dd494735831e39_______WppTraceUnwinder__lambda_d42e68d5593f7c83f3dd494735831e39____
0x18000b7a0  mov     eax, 8007000Eh
0x18000b7a5  mov     rcx, [rsp+0B8h+var_18]
0x18000b7ad  xor     rcx, rsp; StackCookie
0x18000b7b0  call    __security_check_cookie
0x18000b7b5  mov     rbx, [rsp+0B8h+arg_8]
0x18000b7bd  add     rsp, 0B0h
0x18000b7c4  pop     rdi
0x18000b7c5  retn
```
