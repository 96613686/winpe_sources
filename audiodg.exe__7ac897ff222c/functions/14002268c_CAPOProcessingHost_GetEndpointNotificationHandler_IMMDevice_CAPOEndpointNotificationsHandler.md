# CAPOProcessingHost::GetEndpointNotificationHandler(IMMDevice *,CAPOEndpointNotificationsHandler * *)

- ea: `0x14002268c`
- end: `0x140022929`
- name: `?GetEndpointNotificationHandler@CAPOProcessingHost@@AEAAJPEAUIMMDevice@@PEAPEAVCAPOEndpointNotificationsHandler@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(CAPOProcessingHost *__hidden this, struct IMMDevice *, struct CAPOEndpointNotificationsHandler **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400223f8`
- `0x140032608`

## callees

- `0x14000c33c`
- `0x140016f68`
- `0x14002268c`
- `0x14002296c`
- `0x140022a24`
- `0x140022e54`
- `0x140023010`
- `0x140046dc0`
- `0x14004d2c4`
- `0x14005d0e0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400227f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002287e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400228c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400227f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002287e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400228c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400226c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400226c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400227e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002288b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400227e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002288b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAPOProcessingHost::GetEndpointNotificationHandler(
        CAPOProcessingHost *this,
        struct IMMDevice *a2,
        struct CAPOEndpointNotificationsHandler **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // r8
  unsigned __int64 v10; // rcx
  size_t v11; // r14
  wchar_t **v12; // rdx
  unsigned __int64 v13; // rax
  const char *v14; // r9
  unsigned __int64 v15; // r11
  __int64 v16; // rcx
  _QWORD *v17; // rdi
  _QWORD *v18; // r12
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  struct CAPOEndpointNotificationsHandler *v21; // rcx
  __int64 result; // rax
  int v23; // eax
  unsigned int v24; // edi
  int v25; // eax
  LPVOID pv; // [rsp+20h] [rbp-88h] BYREF
  struct IMMDevice *v27; // [rsp+28h] [rbp-80h] BYREF
  char *v28; // [rsp+30h] [rbp-78h]
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+38h] [rbp-70h]
  wchar_t *S1[2]; // [rsp+40h] [rbp-68h] BYREF
  size_t N; // [rsp+50h] [rbp-58h]
  unsigned __int64 v32; // [rsp+58h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v27 = a2;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v29 = v6;
  pv = 0;
  try
  {
    v7 = ((__int64 (*)(void))a2->lpVtbl->GetId)();
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)(unsigned int)v7,
        (int)pv);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v6 )
        LeaveCriticalSection(v6);
      result = v8;
    }
    else
    {
      *(_OWORD *)S1 = 0;
      N = 0;
      v32 = 0;
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)pv + v9) );
      std::wstring::_Construct<1,unsigned short const *>(S1, pv);
      v11 = N;
      v28 = (char *)this + 80;
      v12 = (wchar_t **)S1[0];
      if ( v32 <= 7 )
        v12 = S1;
      v13 = 2 * (*((_QWORD *)this + 16) & std::_Fnv1a_append_bytes(v10, (const unsigned __int8 *const)v12, 2 * N));
      v16 = *((_QWORD *)this + 13);
      v17 = *(_QWORD **)(v16 + 8 * v13 + 8);
      if ( v17 != *((_QWORD **)this + 11) )
      {
        v18 = *(_QWORD **)(v16 + 8 * v13);
        while ( 1 )
        {
          v19 = (const wchar_t *)(v17 + 2);
          if ( v17[5] > 7u )
            v19 = *(const wchar_t **)v19;
          v20 = (const wchar_t *)S1;
          if ( v15 > 7 )
            v20 = S1[0];
          if ( v11 == v17[4] )
          {
            if ( !v11 )
              goto LABEL_17;
            v25 = wmemcmp(v20, v19, v11);
            v15 = v32;
            if ( !v25 )
              goto LABEL_17;
            v11 = N;
          }
          if ( v17 == v18 )
            break;
          v17 = (_QWORD *)v17[1];
        }
      }
      v17 = 0;
LABEL_17:
      if ( !v17 )
        v17 = (_QWORD *)*((_QWORD *)this + 11);
      if ( v15 > 7 )
        std::_Deallocate<16>(S1[0], 2 * v15 + 2);
      if ( v17 != *((_QWORD **)this + 11) )
      {
        v21 = (struct CAPOEndpointNotificationsHandler *)v17[6];
        if ( v21 )
        {
          *a3 = v21;
          (*(void (__fastcall **)(struct CAPOEndpointNotificationsHandler *))(*(_QWORD *)v21 + 8LL))(v21);
        }
        else
        {
          *a3 = 0;
        }
        goto LABEL_24;
      }
      v23 = Microsoft::WRL::Details::MakeAndInitialize<CAPOEndpointNotificationsHandler,CAPOEndpointNotificationsHandler,IMMDevice * &>(
              a3,
              &v27);
      v24 = v23;
      if ( v23 >= 0 )
      {
        v27 = (struct IMMDevice *)pv;
        std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>::emplace<unsigned short *,CAPOEndpointNotificationsHandler * &>(
          v28,
          S1,
          &v27,
          a3);
LABEL_24:
        if ( pv )
          CoTaskMemFree(pv);
        if ( v6 )
          LeaveCriticalSection(v6);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)(unsigned int)v23,
        (int)pv);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
      if ( v6 )
        LeaveCriticalSection(v6);
      result = v24;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA6,
                           (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x14002268c  push    rbx
0x14002268e  push    rsi
0x14002268f  push    rdi
0x140022690  push    r12
0x140022692  push    r13
0x140022694  push    r14
0x140022696  push    r15
0x140022698  sub     rsp, 70h
0x14002269c  mov     rax, cs:__security_cookie
0x1400226a3  xor     rax, rsp
0x1400226a6  mov     [rsp+0A8h+var_48], rax
0x1400226ab  mov     r15, r8
0x1400226ae  mov     rdi, rdx
0x1400226b1  mov     r13, rcx
0x1400226b4  mov     [rsp+0A8h+var_80], rdx
0x1400226b9  lea     rbx, [rcx+20h]
0x1400226bd  mov     rcx, rbx; lpCriticalSection
0x1400226c0  call    cs:__imp_EnterCriticalSection
0x1400226c6  mov     [rsp+0A8h+var_70], rbx
0x1400226cb  xor     r12d, r12d
0x1400226ce  mov     [rsp+0A8h+pv], r12
0x1400226d3  mov     rax, [rdi]
0x1400226d6  mov     [rsp+0A8h+pv], r12; int
0x1400226db  lea     rdx, [rsp+0A8h+pv]
0x1400226e0  mov     rcx, rdi
0x1400226e3  mov     rax, [rax+28h]
0x1400226e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400226ec  mov     edi, eax
0x1400226ee  test    eax, eax
0x1400226f0  js      loc_14002284F
0x1400226f6  mov     rdx, [rsp+0A8h+pv]
0x1400226fb  xorps   xmm0, xmm0
0x1400226fe  movups  xmmword ptr [rsp+0A8h+S1], xmm0
0x140022703  mov     [rsp+0A8h+N], r12
0x140022708  mov     [rsp+0A8h+var_50], r12
0x14002270d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140022711  inc     r8
0x140022714  cmp     [rdx+r8*2], r12w
0x140022719  jnz     short loc_140022711
0x14002271b  lea     rcx, [rsp+0A8h+S1]
0x140022720  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140022725  mov     r14, [rsp+0A8h+N]
0x14002272a  mov     r11, [rsp+0A8h+var_50]
0x14002272f  lea     rsi, [r13+50h]
0x140022733  mov     [rsp+0A8h+var_78], rsi
0x140022738  cmp     r11, 7
0x14002273c  mov     rdx, [rsp+0A8h+S1]
0x140022741  ja      short loc_140022748
0x140022743  lea     rdx, [rsp+0A8h+S1]; unsigned __int8 *
0x140022748  lea     r8, [r14+r14]; unsigned __int64
0x14002274c  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x140022751  and     rax, [rsi+30h]
0x140022755  add     rax, rax
0x140022758  mov     rcx, [rsi+18h]
0x14002275c  mov     rdi, [rcx+rax*8+8]
0x140022761  cmp     rdi, [rsi+8]
0x140022765  jz      short loc_1400227A2
0x140022767  mov     r12, [rcx+rax*8]
0x14002276b  lea     rdx, [rdi+10h]; S2
0x14002276f  cmp     qword ptr [rdi+28h], 7
0x140022774  ja      short loc_14002279A
0x140022776  lea     rcx, [rsp+0A8h+S1]
0x14002277b  cmp     r11, 7
0x14002277f  cmova   rcx, [rsp+0A8h+S1]; S1
0x140022785  cmp     r14, [rdi+20h]
0x140022789  jz      loc_1400228D0
0x14002278f  cmp     rdi, r12
0x140022792  jz      short loc_14002279F
0x140022794  mov     rdi, [rdi+8]
0x140022798  jmp     short loc_14002276B
0x14002279a  mov     rdx, [rdx]
0x14002279d  jmp     short loc_140022776
0x14002279f  xor     r12d, r12d
0x1400227a2  mov     rdi, r12
0x1400227a5  test    rdi, rdi
0x1400227a8  jz      loc_1400228F8
0x1400227ae  cmp     r11, 7
0x1400227b2  ja      loc_140022901
0x1400227b8  cmp     rdi, [r13+58h]
0x1400227bc  jz      short loc_140022819
0x1400227be  mov     rcx, [rdi+30h]
0x1400227c2  test    rcx, rcx
0x1400227c5  jz      loc_140022918
0x1400227cb  mov     [r15], rcx
0x1400227ce  mov     rax, [rcx]
0x1400227d1  mov     rax, [rax+8]
0x1400227d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227da  nop
0x1400227db  mov     rcx, [rsp+0A8h+pv]; pv
0x1400227e0  test    rcx, rcx
0x1400227e3  jz      short loc_1400227EC
0x1400227e5  call    cs:__imp_CoTaskMemFree
0x1400227eb  nop
0x1400227ec  test    rbx, rbx
0x1400227ef  jz      short loc_1400227FA
0x1400227f1  mov     rcx, rbx; lpCriticalSection
0x1400227f4  call    cs:__imp_LeaveCriticalSection
0x1400227fa  xor     eax, eax
0x1400227fc  mov     rcx, [rsp+0A8h+var_48]
0x140022801  xor     rcx, rsp; StackCookie
0x140022804  call    __security_check_cookie
0x140022809  add     rsp, 70h
0x14002280d  pop     r15
0x14002280f  pop     r14
0x140022811  pop     r13
0x140022813  pop     r12
0x140022815  pop     rdi
0x140022816  pop     rsi
0x140022817  pop     rbx
0x140022818  retn
0x140022819  lea     rdx, [rsp+0A8h+var_80]
0x14002281e  mov     rcx, r15
0x140022821  call    ??$MakeAndInitialize@VCAPOEndpointNotificationsHandler@@V1@AEAPEAUIMMDevice@@@Details@WRL@Microsoft@@YAJPEAPEAVCAPOEndpointNotificationsHandler@@AEAPEAUIMMDevice@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAPOEndpointNotificationsHandler,CAPOEndpointNotificationsHandler,IMMDevice * &>(CAPOEndpointNotificationsHandler * *,IMMDevice * &)
0x140022826  mov     edi, eax
0x140022828  test    eax, eax
0x14002282a  js      short loc_140022893
0x14002282c  mov     rax, [rsp+0A8h+pv]
0x140022831  mov     [rsp+0A8h+var_80], rax
0x140022836  mov     r9, r15
0x140022839  lea     r8, [rsp+0A8h+var_80]
0x14002283e  lea     rdx, [rsp+0A8h+S1]
0x140022843  mov     rcx, [rsp+0A8h+var_78]
0x140022848  call    ??$emplace@PEAGAEAPEAVCAPOEndpointNotificationsHandler@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCAPOEndpointNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@$$QEAPEAGAEAPEAVCAPOEndpointNotificationsHandler@@@Z; std::_Hash<std::_Umap_traits<std::wstring,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CAPOEndpointNotificationsHandler,wil::err_returncode_policy>>>,0>>::emplace<ushort *,CAPOEndpointNotificationsHandler * &>(ushort * &&,CAPOEndpointNotificationsHandler * &)
0x14002284d  jmp     short loc_1400227DB
0x14002284f  mov     rcx, [rsp+0A8h]; this
0x140022857  mov     r9d, edi; char *
0x14002285a  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140022861  mov     edx, 97h; void *
0x140022866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002286b  nop
0x14002286c  mov     rcx, [rsp+0A8h+pv]; pv
0x140022871  test    rcx, rcx
0x140022874  jnz     short loc_14002288B
0x140022876  test    rbx, rbx
0x140022879  jz      short loc_140022884
0x14002287b  mov     rcx, rbx; lpCriticalSection
0x14002287e  call    cs:__imp_LeaveCriticalSection
0x140022884  mov     eax, edi
0x140022886  jmp     loc_1400227FC
0x14002288b  call    cs:__imp_CoTaskMemFree
0x140022891  jmp     short loc_140022876
0x140022893  mov     rcx, [rsp+0A8h]; this
0x14002289b  mov     r9d, edi; char *
0x14002289e  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400228a5  mov     edx, 9Ch; void *
0x1400228aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400228af  nop
0x1400228b0  lea     rcx, [rsp+0A8h+pv]
0x1400228b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400228ba  nop
0x1400228bb  test    rbx, rbx
0x1400228be  jz      short loc_1400228C9
0x1400228c0  mov     rcx, rbx; lpCriticalSection
0x1400228c3  call    cs:__imp_LeaveCriticalSection
0x1400228c9  mov     eax, edi
0x1400228cb  jmp     loc_1400227FC
0x1400228d0  test    r14, r14
0x1400228d3  jz      short loc_1400228F0
0x1400228d5  mov     r8, r14; N
0x1400228d8  call    wmemcmp
0x1400228dd  mov     r11, [rsp+0A8h+var_50]
0x1400228e2  test    eax, eax
0x1400228e4  jz      short loc_1400228F0
0x1400228e6  mov     r14, [rsp+0A8h+N]
0x1400228eb  jmp     loc_14002278F
0x1400228f0  xor     r12d, r12d
0x1400228f3  jmp     loc_1400227A5
0x1400228f8  mov     rdi, [rsi+8]
0x1400228fc  jmp     loc_1400227AE
0x140022901  lea     rdx, ds:2[r11*2]
0x140022909  mov     rcx, [rsp+0A8h+S1]
0x14002290e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140022913  jmp     loc_1400227B8
0x140022918  mov     [r15], r12
0x14002291b  jmp     loc_1400227DB
0x140022920  mov     eax, dword ptr [rsp+0A8h+pv]
0x140022924  jmp     loc_1400227FC
```
