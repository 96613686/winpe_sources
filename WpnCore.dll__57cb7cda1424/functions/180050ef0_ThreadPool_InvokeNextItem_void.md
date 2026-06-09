# ThreadPool::InvokeNextItem(void)

- ea: `0x180050ef0`
- end: `0x180051228`
- name: `?InvokeNextItem@ThreadPool@@AEAAJXZ`
- size: `824`
- prototype: `__int64 __fastcall(ThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800919f0`

## callees

- `0x180011e6c`
- `0x180013360`
- `0x1800140e0`
- `0x180020f48`
- `0x1800275b0`
- `0x18002da64`
- `0x18002de9c`
- `0x18002ee38`
- `0x18004c9e4`
- `0x18004ca20`
- `0x18004cb00`
- `0x18004cd10`
- `0x180050ef0`
- `0x180051230`
- `0x180051470`
- `0x1800b99f0`
- `0x1800be924`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050f30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050f68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050fc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800510c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800511bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050f30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050f68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050fc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800510c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800511bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050f5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050fb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050fda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800511b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800511ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050f5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050fb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050fda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800511b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800511ea`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180050ffd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180050ffd`

## string_xrefs

- `0x18005100e`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\threadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ThreadPool::InvokeNextItem(ThreadPool *this)
{
  __int64 v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v4; // ecx
  __int64 v5; // rcx
  char *v6; // r8
  __int64 v7; // rdx
  const unsigned __int16 *v8; // r14
  HRESULT v9; // eax
  unsigned __int64 v10; // rdx
  unsigned __int8 v11; // cl
  __int64 v12; // rdx
  __int64 v13; // rcx
  WpncoreTelemetry *v14; // rax
  int v15; // eax
  unsigned __int64 v16; // rdx
  int v17; // ecx
  int v18; // r15d
  __int64 v19; // rcx
  WpncoreTelemetry *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned __int64 v23; // rcx
  const unsigned __int8 *v24; // rdx
  __int64 appended; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned int v29; // r8d
  int v31; // [rsp+20h] [rbp-49h]
  struct _GUID v32; // [rsp+30h] [rbp-39h] BYREF
  __int64 v33; // [rsp+40h] [rbp-29h]
  unsigned __int8 *v34[3]; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int8 *v35[2]; // [rsp+60h] [rbp-9h] BYREF
  __m128i si128; // [rsp+70h] [rbp+7h]
  GUID pguid; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v2 = 0;
  v33 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v4 = ++*((_DWORD *)this + 38);
  if ( v4 <= *((_DWORD *)this + 36) )
    v4 = *((_DWORD *)this + 36);
  *((_DWORD *)this + 36) = v4;
  if ( v3 )
    LeaveCriticalSection(v3);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_QWORD *)this + 3) )
  {
    v5 = **((_QWORD **)this + 2);
    v2 = *(_QWORD *)(v5 + 16);
    *(_QWORD *)(v5 + 16) = 0;
    v33 = v2;
    v6 = (char *)**((_QWORD **)this + 2);
    v7 = *(_QWORD *)v6;
    --*((_QWORD *)this + 3);
    **((_QWORD **)v6 + 1) = v7;
    *(_QWORD *)(v7 + 8) = *((_QWORD *)v6 + 1);
    std::_List_node<std::unique_ptr<WorkItem>,void *>::_Freenode<std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>>>(
      v5,
      v6);
  }
  if ( this != (ThreadPool *)-32LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( v2 )
  {
    EnterCriticalSection(v3);
    ++*((_DWORD *)this + 35);
    if ( v3 )
      LeaveCriticalSection(v3);
    v8 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
    pguid = 0;
    v9 = CoCreateGuid(&pguid);
    v11 = (unsigned __int8)retaddr;
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\threadpool\\threadpool.cpp",
        (const char *)(unsigned int)v9,
        v31);
    v34[2] = 0;
    if ( WpncoreTelemetry::IsEnabled(v11, v10) )
    {
      v14 = (WpncoreTelemetry *)wil::details::static_lazy<WpncoreTelemetry>::get(
                                  v13,
                                  _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_);
      v32 = pguid;
      WpncoreTelemetry::StartThreadpoolWork_(v14, &v32, v8);
    }
    if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x40) != 0 )
      McTemplateU0zp_EventWriteTransfer(v13, v12, v8, 0);
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    v18 = v15;
    if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x40) != 0 )
      McTemplateU0zpd_EventWriteTransfer(v17, v16, (_DWORD)v8, 0, v15);
    if ( WpncoreTelemetry::IsEnabled(v17, v16) )
    {
      v20 = (WpncoreTelemetry *)wil::details::static_lazy<WpncoreTelemetry>::get(
                                  v19,
                                  _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_);
      v32 = pguid;
      WpncoreTelemetry::StopThreadpoolWork_(v20, &v32, v8, v18);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)this + 4);
    *(_QWORD *)&v32.Data1 = (char *)this + 160;
    *(_OWORD *)v35 = 0;
    si128 = 0;
    std::wstring::_Construct_empty(v35, v21);
    v22 = -1;
    do
      ++v22;
    while ( v8[v22] );
    std::wstring::_Assign<unsigned short>(v35, v8, v22);
    v24 = (const unsigned __int8 *)v35;
    if ( si128.m128i_i64[1] > 7uLL )
      v24 = v35[0];
    appended = std::_Fnv1a_append_bytes(v23, v24, 2 * si128.m128i_i64[0]);
    v26 = std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Find_last<std::wstring>(
            (_QWORD *)this + 26,
            v34,
            (__int64)v35,
            appended)[1];
    if ( !v26 )
      v26 = *((_QWORD *)this + 27);
    if ( v26 == *((_QWORD *)this + 27) )
      *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Try_emplace<std::wstring const &,>(
                               (_QWORD *)this + 26,
                               (__int64)v34,
                               (__int64)v35)
                + 48LL) = 0;
    v27 = std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Try_emplace<std::wstring const &,>(
            (_QWORD *)this + 26,
            (__int64)v34,
            (__int64)v35);
    ++*(_DWORD *)(*(_QWORD *)v27 + 48LL);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v35[0], 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v35[0]) = 0;
    if ( this != (ThreadPool *)-160LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 4);
  }
  EnterCriticalSection(v3);
  v29 = --*((_DWORD *)this + 38);
  if ( v29 >= *((_DWORD *)this + 37) )
    v29 = *((_DWORD *)this + 37);
  *((_DWORD *)this + 37) = v29;
  if ( v3 )
    LeaveCriticalSection(v3);
  if ( v2 )
    std::default_delete<NotificationPlatform>::operator()(v28, v2);
  return 0;
}

```

## disassembly

```asm
0x180050ef0  mov     [rsp-8+arg_8], rbx
0x180050ef5  mov     [rsp-8+arg_10], rsi
0x180050efa  push    rbp
0x180050efb  push    rdi
0x180050efc  push    r12
0x180050efe  push    r14
0x180050f00  push    r15
0x180050f02  lea     rbp, [rsp-37h]
0x180050f07  sub     rsp, 0A0h
0x180050f0e  mov     rax, cs:__security_cookie
0x180050f15  xor     rax, rsp
0x180050f18  mov     [rbp+57h+var_30], rax
0x180050f1c  mov     rdi, rcx
0x180050f1f  xor     r12d, r12d
0x180050f22  mov     ebx, r12d
0x180050f25  mov     [rbp+57h+var_80], rbx
0x180050f29  lea     rsi, [rcx+58h]
0x180050f2d  mov     rcx, rsi; lpCriticalSection
0x180050f30  call    cs:__imp_EnterCriticalSection
0x180050f36  inc     dword ptr [rdi+98h]
0x180050f3c  mov     ecx, [rdi+98h]
0x180050f42  mov     eax, [rdi+90h]
0x180050f48  cmp     ecx, eax
0x180050f4a  cmovbe  ecx, eax
0x180050f4d  mov     [rdi+90h], ecx
0x180050f53  test    rsi, rsi
0x180050f56  jz      short loc_180050F61
0x180050f58  mov     rcx, rsi; lpCriticalSection
0x180050f5b  call    cs:__imp_LeaveCriticalSection
0x180050f61  lea     r14, [rdi+20h]
0x180050f65  mov     rcx, r14; lpCriticalSection
0x180050f68  call    cs:__imp_EnterCriticalSection
0x180050f6e  cmp     [rdi+18h], r12
0x180050f72  jz      short loc_180050FAC
0x180050f74  mov     rax, [rdi+10h]
0x180050f78  mov     rcx, [rax]
0x180050f7b  mov     rbx, [rcx+10h]
0x180050f7f  mov     [rcx+10h], r12
0x180050f83  mov     [rbp+57h+var_80], rbx
0x180050f87  mov     rax, [rdi+10h]
0x180050f8b  mov     r8, [rax]
0x180050f8e  mov     rdx, [r8]
0x180050f91  dec     qword ptr [rdi+18h]
0x180050f95  mov     rax, [r8+8]
0x180050f99  mov     [rax], rdx
0x180050f9c  mov     rax, [r8+8]
0x180050fa0  mov     [rdx+8], rax
0x180050fa4  mov     rdx, r8
0x180050fa7  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::unique_ptr<WorkItem>,void *>::_Freenode<std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>>>(std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>> &,std::_List_node<std::unique_ptr<WorkItem>,void *> *)
0x180050fac  test    r14, r14
0x180050faf  jz      short loc_180050FBA
0x180050fb1  mov     rcx, r14; lpCriticalSection
0x180050fb4  call    cs:__imp_LeaveCriticalSection
0x180050fba  test    rbx, rbx
0x180050fbd  jz      loc_1800511B8
0x180050fc3  mov     rcx, rsi; lpCriticalSection
0x180050fc6  call    cs:__imp_EnterCriticalSection
0x180050fcc  inc     dword ptr [rdi+8Ch]
0x180050fd2  test    rsi, rsi
0x180050fd5  jz      short loc_180050FE0
0x180050fd7  mov     rcx, rsi; lpCriticalSection
0x180050fda  call    cs:__imp_LeaveCriticalSection
0x180050fe0  mov     rax, [rbx]
0x180050fe3  mov     rcx, rbx
0x180050fe6  mov     rax, [rax+18h]
0x180050fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fef  mov     r14, rax
0x180050ff2  xorps   xmm0, xmm0
0x180050ff5  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180050ff9  lea     rcx, [rbp+57h+pguid]; pguid
0x180050ffd  call    cs:__imp_CoCreateGuid
0x180051003  mov     rcx, [rbp+5Fh]; this
0x180051007  test    eax, eax
0x180051009  jns     short loc_18005101F
0x18005100b  mov     r9d, eax; char *
0x18005100e  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180051015  mov     edx, 0A4h; void *
0x18005101a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005101f  mov     [rbp+57h+var_68], r12
0x180051023  call    ?IsEnabled@WpncoreTelemetry@@SA_NE_K@Z; WpncoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x180051028  test    al, al
0x18005102a  jz      short loc_180051050
0x18005102c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c91d295e9756ec26c89460bbd269b90b_@@CA@XZ; _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_(void)
0x180051033  call    ?get@?$static_lazy@VWpncoreTelemetry@@@details@wil@@QEAAPEAVWpncoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpncoreTelemetry>::get(void (*)(void))
0x180051038  movaps  xmm0, xmmword ptr [rbp+57h+pguid.Data1]
0x18005103c  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180051041  mov     r8, r14; unsigned __int16 *
0x180051044  lea     rdx, [rbp+57h+var_90]; struct _GUID
0x180051048  mov     rcx, rax; this
0x18005104b  call    ?StartThreadpoolWork_@WpncoreTelemetry@@QEAAXU_GUID@@PEBG@Z; WpncoreTelemetry::StartThreadpoolWork_(_GUID,ushort const *)
0x180051050  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 40h
0x180051057  jz      short loc_180051064
0x180051059  xor     r9d, r9d
0x18005105c  mov     r8, r14
0x18005105f  call    McTemplateU0zp_EventWriteTransfer
0x180051064  mov     rax, [rbx]
0x180051067  mov     rcx, rbx
0x18005106a  mov     rax, [rax+8]
0x18005106e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051073  mov     r15d, eax
0x180051076  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 40h
0x18005107d  jz      short loc_18005108E
0x18005107f  mov     [rsp+0C0h+var_A0], eax
0x180051083  xor     r9d, r9d
0x180051086  mov     r8, r14
0x180051089  call    McTemplateU0zpd_EventWriteTransfer
0x18005108e  call    ?IsEnabled@WpncoreTelemetry@@SA_NE_K@Z; WpncoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x180051093  test    al, al
0x180051095  jz      short loc_1800510BE
0x180051097  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c91d295e9756ec26c89460bbd269b90b_@@CA@XZ; _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_(void)
0x18005109e  call    ?get@?$static_lazy@VWpncoreTelemetry@@@details@wil@@QEAAPEAVWpncoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpncoreTelemetry>::get(void (*)(void))
0x1800510a3  movaps  xmm0, xmmword ptr [rbp+57h+pguid.Data1]
0x1800510a7  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800510ac  mov     r9d, r15d; int
0x1800510af  mov     r8, r14; unsigned __int16 *
0x1800510b2  lea     rdx, [rbp+57h+var_90]; struct _GUID
0x1800510b6  mov     rcx, rax; this
0x1800510b9  call    ?StopThreadpoolWork_@WpncoreTelemetry@@QEAAXU_GUID@@PEBGJ@Z; WpncoreTelemetry::StopThreadpoolWork_(_GUID,ushort const *,long)
0x1800510be  lea     r15, [rdi+0A0h]
0x1800510c5  mov     rcx, r15; lpCriticalSection
0x1800510c8  call    cs:__imp_EnterCriticalSection
0x1800510ce  mov     qword ptr [rbp+57h+var_90.Data1], r15
0x1800510d2  xorps   xmm0, xmm0
0x1800510d5  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800510d9  xorps   xmm1, xmm1
0x1800510dc  movdqu  [rbp+57h+var_50], xmm1
0x1800510e1  lea     rcx, [rbp+57h+var_60]
0x1800510e5  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800510ea  nop
0x1800510eb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800510ef  inc     r8
0x1800510f2  cmp     [r14+r8*2], r12w
0x1800510f7  jnz     short loc_1800510EF
0x1800510f9  mov     rdx, r14
0x1800510fc  lea     rcx, [rbp+57h+var_60]
0x180051100  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180051105  lea     r14, [rdi+0D0h]
0x18005110c  mov     r8, qword ptr [rbp+57h+var_50]
0x180051110  lea     rdx, [rbp+57h+var_60]
0x180051114  cmp     qword ptr [rbp+57h+var_50+8], 7
0x180051119  cmova   rdx, [rbp+57h+var_60]; unsigned __int8 *
0x18005111e  add     r8, r8; unsigned __int64
0x180051121  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180051126  mov     r9, rax
0x180051129  lea     r8, [rbp+57h+var_60]
0x18005112d  lea     rdx, [rbp+57h+var_78]
0x180051131  mov     rcx, r14
0x180051134  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180051139  mov     rcx, [rax+8]
0x18005113d  test    rcx, rcx
0x180051140  jnz     short loc_180051146
0x180051142  mov     rcx, [r14+8]
0x180051146  cmp     rcx, [rdi+0D8h]
0x18005114d  jnz     short loc_180051166
0x18005114f  lea     r8, [rbp+57h+var_60]
0x180051153  lea     rdx, [rbp+57h+var_78]
0x180051157  mov     rcx, r14
0x18005115a  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18005115f  mov     rdx, [rax]
0x180051162  mov     [rdx+30h], r12d
0x180051166  lea     r8, [rbp+57h+var_60]
0x18005116a  lea     rdx, [rbp+57h+var_78]
0x18005116e  mov     rcx, r14
0x180051171  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180051176  mov     rcx, [rax]
0x180051179  inc     dword ptr [rcx+30h]
0x18005117c  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x180051180  cmp     rdx, 7
0x180051184  jbe     short loc_180051197
0x180051186  lea     rdx, ds:2[rdx*2]
0x18005118e  mov     rcx, [rbp+57h+var_60]
0x180051192  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180051197  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005119f  movdqu  [rbp+57h+var_50], xmm0
0x1800511a4  mov     word ptr [rbp+57h+var_60], r12w
0x1800511a9  test    r15, r15
0x1800511ac  jz      short loc_1800511B8
0x1800511ae  mov     rcx, r15; lpCriticalSection
0x1800511b1  call    cs:__imp_LeaveCriticalSection
0x1800511b7  nop
0x1800511b8  mov     rcx, rsi; lpCriticalSection
0x1800511bb  call    cs:__imp_EnterCriticalSection
0x1800511c1  dec     dword ptr [rdi+98h]
0x1800511c7  mov     r8d, [rdi+98h]
0x1800511ce  mov     eax, [rdi+94h]
0x1800511d4  cmp     r8d, eax
0x1800511d7  cmovnb  r8d, eax
0x1800511db  mov     [rdi+94h], r8d
0x1800511e2  test    rsi, rsi
0x1800511e5  jz      short loc_1800511F1
0x1800511e7  mov     rcx, rsi; lpCriticalSection
0x1800511ea  call    cs:__imp_LeaveCriticalSection
0x1800511f0  nop
0x1800511f1  test    rbx, rbx
0x1800511f4  jz      short loc_1800511FE
0x1800511f6  mov     rdx, rbx
0x1800511f9  call    ??R?$default_delete@VNotificationPlatform@@@std@@QEBAXPEAVNotificationPlatform@@@Z; std::default_delete<NotificationPlatform>::operator()(NotificationPlatform *)
0x1800511fe  xor     eax, eax
0x180051200  mov     rcx, [rbp+57h+var_30]
0x180051204  xor     rcx, rsp; StackCookie
0x180051207  call    __security_check_cookie
0x18005120c  lea     r11, [rsp+0C0h+var_20]
0x180051214  mov     rbx, [r11+38h]
0x180051218  mov     rsi, [r11+40h]
0x18005121c  mov     rsp, r11
0x18005121f  pop     r15
0x180051221  pop     r14
0x180051223  pop     r12
0x180051225  pop     rdi
0x180051226  pop     rbp
0x180051227  retn
```
