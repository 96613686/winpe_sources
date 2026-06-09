# CSessionManager::Remove(ulong)

- ea: `0x18000bb00`
- end: `0x18000bd6c`
- name: `?Remove@CSessionManager@@SAJK@Z`
- size: `620`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006130`
- `0x18000b4a0`

## callees

- `0x180001444`
- `0x180006d40`
- `0x1800071d4`
- `0x1800080dc`
- `0x18000ac04`
- `0x18000add0`
- `0x18000b12c`
- `0x18000ba94`
- `0x18000bb00`
- `0x18000bedc`
- `0x18000c148`
- `0x18000c428`
- `0x18000c498`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bc2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bc2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc99`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000bd25`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000bd25`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000bc8a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000bc8a`

## string_xrefs

- `0x18000bb3b`: `CSessionManager::Remove`

## pseudocode

```c
__int64 __fastcall CSessionManager::Remove(int a1)
{
  char v1; // si
  _QWORD *v2; // rax
  struct CSessionManager *v3; // rax
  struct CSessionManager *v4; // rax
  struct CSessionManager *v5; // rax
  __int64 v6; // rdi
  _QWORD *v7; // rbx
  struct CSessionManager *v8; // rax
  LPCRITICAL_SECTION v9; // rcx
  _QWORD *v10; // rcx
  int v11; // edx
  struct CSessionManager *v12; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  __int64 v15; // rcx
  unsigned int v16; // ebx
  __int64; // rax
  char v18; // [rsp+20h] [rbp-88h]
  int v19; // [rsp+30h] [rbp-78h] BYREF
  PVOID pv; // [rsp+38h] [rbp-70h] BYREF
  int v21; // [rsp+40h] [rbp-68h] BYREF
  _QWORD *v22; // [rsp+48h] [rbp-60h] BYREF
  __int64 v23; // [rsp+50h] [rbp-58h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v25[3]; // [rsp+60h] [rbp-48h] BYREF
  char v26[24]; // [rsp+78h] [rbp-30h] BYREF
  int v27; // [rsp+B0h] [rbp+8h] BYREF

  v27 = a1;
  v1 = a1;
  v19 = 0;
  v21 = 0;
  strcpy(v26, "CSessionManager::Remove");
  v25[0] = v26;
  v25[1] = &v21;
  v25[2] = &v19;
  lambda_9ccba3754627b32900d511621c8157e3_::operator()(v25);
  v21 = 1;
  v22 = v25;
  pv = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v2 = operator new(0x10u);
    if ( v2 )
    {
      *v2 = 0;
      v2[1] = 0;
    }
    std::unique_ptr<std::shared_ptr<CSession>>::reset((_QWORD **)&pv, v2);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v19 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000BD2D);
      std::unique_ptr<std::shared_ptr<CSession>>::_Delete((_QWORD **)&pv);
      WppTraceUnwinder__lambda_9ccba3754627b32900d511621c8157e3____::_WppTraceUnwinder__lambda_9ccba3754627b32900d511621c8157e3____(&v22);
       = 2147942414LL;
LABEL_31:
      ;
    }
  }
  v3 = CSessionManager::Instance();
  Microsoft::WRL::Wrappers::CriticalSection::Lock(&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 16));
  v4 = CSessionManager::Instance();
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CSession>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CSession>>>,0>>::find(
    v4,
    &v23,
    &v27);
  v5 = CSessionManager::Instance();
  v6 = v23;
  v7 = pv;
  if ( v23 != *(_QWORD *)v5 )
  {
    std::shared_ptr<CSession>::operator=(pv, v23 + 40);
    v8 = CSessionManager::Instance();
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CSession>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CSession>>>,0>>::erase(
      v8,
      &v23,
      v6);
  }
  v9 = lpCriticalSection;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( *v7 )
  {
    v12 = CSessionManager::Instance();
    ThreadpoolWork = CreateThreadpoolWork(off_18002B090, v7, (PTP_CALLBACK_ENVIRON)((char *)v12 + 56));
    if ( ThreadpoolWork )
    {
      pv = 0;
      SubmitThreadpoolWork(ThreadpoolWork);
      goto LABEL_22;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v19 = LastError;
    WppTraceIndent(v15, 2u);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v11 = 27;
    v18 = v19;
  }
  else
  {
    WppTraceIndent((__int64)v9, 2u);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_22;
    }
    v11 = 26;
    v18 = v1;
  }
  WPP_SF_sd(v10[2], v11, (int)&WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids, (int)WPP_pszIndent, v18);
LABEL_22:
  v16 = v19;
  std::unique_ptr<std::shared_ptr<CSession>>::_Delete((_QWORD **)&pv);
  WppTraceUnwinder__lambda_9ccba3754627b32900d511621c8157e3____::_WppTraceUnwinder__lambda_9ccba3754627b32900d511621c8157e3____(&v22);
   = v16;
  goto LABEL_31;
}

```

## disassembly

```asm
0x18000bb00  mov     r11, rsp
0x18000bb03  mov     [r11+10h], rbx
0x18000bb07  mov     [r11+18h], rsi
0x18000bb0b  mov     [rsp+arg_0], ecx
0x18000bb0f  push    rdi
0x18000bb10  sub     rsp, 0A0h
0x18000bb17  mov     rax, cs:__security_cookie
0x18000bb1e  xor     rax, rsp
0x18000bb21  mov     [rsp+0A8h+var_18], rax
0x18000bb29  mov     esi, ecx
0x18000bb2b  mov     [rsp+0A8h+var_78], 0
0x18000bb33  mov     [rsp+0A8h+var_68], 0
0x18000bb3b  movups  xmm0, xmmword ptr cs:aCsessionmanage_2; "CSessionManager::Remove"
0x18000bb42  movups  xmmword ptr [rsp+0A8h+var_30], xmm0
0x18000bb47  movsd   xmm1, qword ptr cs:aCsessionmanage_2+10h; ":Remove"
0x18000bb4f  movsd   qword ptr [r11-20h], xmm1
0x18000bb55  lea     rax, [r11-30h]
0x18000bb59  mov     [r11-48h], rax
0x18000bb5d  lea     rax, [r11-68h]
0x18000bb61  mov     [r11-40h], rax
0x18000bb65  lea     rax, [r11-78h]
0x18000bb69  mov     [r11-38h], rax
0x18000bb6d  lea     rcx, [r11-48h]
0x18000bb71  call    _lambda_9ccba3754627b32900d511621c8157e3___operator__
0x18000bb76  mov     [rsp+0A8h+var_68], 1
0x18000bb7e  lea     rax, [rsp+0A8h+var_48]
0x18000bb83  mov     [rsp+0A8h+var_60], rax
0x18000bb88  mov     [rsp+0A8h+pv], 0
0x18000bb91  mov     ecx, 10h; Size
0x18000bb96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb9b  test    rax, rax
0x18000bb9e  jz      short loc_18000BBAF
0x18000bba0  mov     qword ptr [rax], 0
0x18000bba7  mov     qword ptr [rax+8], 0
0x18000bbaf  mov     rdx, rax
0x18000bbb2  lea     rcx, [rsp+0A8h+pv]
0x18000bbb7  call    ?reset@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@QEAAXPEAV?$shared_ptr@VCSession@@@2@@Z; std::unique_ptr<std::shared_ptr<CSession>>::reset(std::shared_ptr<CSession> *)
0x18000bbbc  nop
0x18000bbbd  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bbc2  lea     rdx, [rax+10h]
0x18000bbc6  lea     rcx, [rsp+0A8h+lpCriticalSection]
0x18000bbcb  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@SA?AVSyncLockCriticalSection@Details@234@PEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::CriticalSection::Lock(_RTL_CRITICAL_SECTION *)
0x18000bbd0  nop
0x18000bbd1  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bbd6  lea     r8, [rsp+0A8h+arg_0]
0x18000bbde  lea     rdx, [rsp+0A8h+var_58]
0x18000bbe3  mov     rcx, rax
0x18000bbe6  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VCSession@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CSession>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CSession>>>,0>>::find(ulong const &)
0x18000bbeb  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bbf0  mov     rdi, [rsp+0A8h+var_58]
0x18000bbf5  mov     rbx, [rsp+0A8h+pv]
0x18000bbfa  cmp     rdi, [rax]
0x18000bbfd  jz      short loc_18000BC21
0x18000bbff  lea     rdx, [rdi+28h]
0x18000bc03  mov     rcx, rbx
0x18000bc06  call    ??4?$shared_ptr@VCSession@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CSession>::operator=(std::shared_ptr<CSession> const &)
0x18000bc0b  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bc10  mov     r8, rdi
0x18000bc13  lea     rdx, [rsp+0A8h+var_58]
0x18000bc18  mov     rcx, rax
0x18000bc1b  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VCSession@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CSession>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CSession>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CSession>>>>>)
0x18000bc20  nop
0x18000bc21  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x18000bc26  test    rcx, rcx
0x18000bc29  jz      short loc_18000BC31
0x18000bc2b  call    cs:__imp_LeaveCriticalSection
0x18000bc31  cmp     qword ptr [rbx], 0
0x18000bc35  jnz     short loc_18000BC77
0x18000bc37  mov     edx, 2
0x18000bc3c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000bc41  lea     rax, WPP_GLOBAL_Control
0x18000bc48  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc4f  cmp     rcx, rax
0x18000bc52  jz      loc_18000BCFC
0x18000bc58  test    byte ptr [rcx+1Ch], 1
0x18000bc5c  jz      loc_18000BCFC
0x18000bc62  cmp     byte ptr [rcx+19h], 4
0x18000bc66  jb      loc_18000BCFC
0x18000bc6c  mov     edx, 1Ah
0x18000bc71  mov     dword ptr [rsp+0A8h+var_88], esi
0x18000bc75  jmp     short loc_18000BCE5
0x18000bc77  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bc7c  lea     r8, [rax+38h]; pcbe
0x18000bc80  mov     rdx, rbx; pv
0x18000bc83  mov     rcx, cs:off_18002B090; pfnwk
0x18000bc8a  call    cs:__imp_CreateThreadpoolWork
0x18000bc90  test    rax, rax
0x18000bc93  jnz     loc_18000BD19
0x18000bc99  call    cs:__imp_GetLastError
0x18000bc9f  test    eax, eax
0x18000bca1  jle     short loc_18000BCAB
0x18000bca3  movzx   eax, ax
0x18000bca6  or      eax, 80070000h
0x18000bcab  mov     [rsp+0A8h+var_78], eax
0x18000bcaf  mov     edx, 2
0x18000bcb4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000bcb9  lea     rax, WPP_GLOBAL_Control
0x18000bcc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcc7  cmp     rcx, rax
0x18000bcca  jz      short loc_18000BCFC
0x18000bccc  test    byte ptr [rcx+1Ch], 1
0x18000bcd0  jz      short loc_18000BCFC
0x18000bcd2  cmp     byte ptr [rcx+19h], 2
0x18000bcd6  jb      short loc_18000BCFC
0x18000bcd8  mov     edx, 1Bh
0x18000bcdd  mov     eax, [rsp+0A8h+var_78]
0x18000bce1  mov     dword ptr [rsp+0A8h+var_88], eax
0x18000bce5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000bcec  lea     r8, WPP_98dc74bda8393d6d4c7ebafdbf154afa_Traceguids
0x18000bcf3  mov     rcx, [rcx+10h]
0x18000bcf7  call    WPP_SF_sd
0x18000bcfc  mov     ebx, [rsp+0A8h+var_78]
0x18000bd00  lea     rcx, [rsp+0A8h+pv]
0x18000bd05  call    ?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::shared_ptr<CSession>>::_Delete(void)
0x18000bd0a  nop
0x18000bd0b  lea     rcx, [rsp+0A8h+var_60]
0x18000bd10  call    WppTraceUnwinder__lambda_9ccba3754627b32900d511621c8157e3_______WppTraceUnwinder__lambda_9ccba3754627b32900d511621c8157e3____
0x18000bd15  mov     eax, ebx
0x18000bd17  jmp     short loc_18000BD47
0x18000bd19  mov     [rsp+0A8h+pv], 0
0x18000bd22  mov     rcx, rax; pwk
0x18000bd25  call    cs:__imp_SubmitThreadpoolWork
0x18000bd2b  jmp     short loc_18000BCFC
0x18000bd2d  lea     rcx, [rsp+0A8h+pv]
0x18000bd32  call    ?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::shared_ptr<CSession>>::_Delete(void)
0x18000bd37  nop
0x18000bd38  lea     rcx, [rsp+0A8h+var_60]
0x18000bd3d  call    WppTraceUnwinder__lambda_9ccba3754627b32900d511621c8157e3_______WppTraceUnwinder__lambda_9ccba3754627b32900d511621c8157e3____
0x18000bd42  mov     eax, 8007000Eh
0x18000bd47  mov     rcx, [rsp+0A8h+var_18]
0x18000bd4f  xor     rcx, rsp; StackCookie
0x18000bd52  call    __security_check_cookie
0x18000bd57  lea     r11, [rsp+0A8h+var_8]
0x18000bd5f  mov     rbx, [r11+18h]
0x18000bd63  mov     rsi, [r11+20h]
0x18000bd67  mov     rsp, r11
0x18000bd6a  pop     rdi
0x18000bd6b  retn
```
