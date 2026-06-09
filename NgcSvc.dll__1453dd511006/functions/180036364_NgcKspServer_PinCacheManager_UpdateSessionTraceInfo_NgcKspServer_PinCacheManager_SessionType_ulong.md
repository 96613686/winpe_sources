# NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(NgcKspServer::PinCacheManager::SessionType,ulong)

- ea: `0x180036364`
- end: `0x180036557`
- name: `?UpdateSessionTraceInfo@PinCacheManager@NgcKspServer@@QEAAXW4SessionType@12@K@Z`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007307c`
- `0x18007faac`

## callees

- `0x180010d1c`
- `0x180036364`
- `0x180047228`
- `0x180048394`
- `0x18005f8e8`
- `0x18007f408`
- `0x18007f438`
- `0x18007f5fc`
- `0x180081098`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003652b`
- `RPCRT4!UuidCreate` at `0x18003651b`
- `RPCRT4!UuidCreate` at `0x18003651b`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetCandidateUserSessionIds` at `0x1800363ca`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetCandidateUserSessionIds` at `0x1800363ca`

## string_xrefs

- `0x180036498`: `onecore\ds\security\ngc\kspsvc\svc\pincachemanager.cpp`
- `0x18003653d`: `onecore\ds\security\ngc\kspsvc\svc\pincachemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(__int64 a1, int a2, int a3)
{
  char i; // al
  _QWORD *v6; // rax
  int v7; // edi
  int v8; // edi
  int v9; // edi
  int v10; // [rsp+20h] [rbp-58h]
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  char v12; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v13[8]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v14; // [rsp+48h] [rbp-30h] BYREF
  __int64 v15; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v17; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v18; // [rsp+98h] [rbp+20h] BYREF

  v17 = a3;
  if ( a3 && (unsigned __int8)IsCamIsCandidateUserPresent() )
  {
    for ( i = 0; !i; i = 1 )
    {
      v18 = 0;
      v11 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::reset(
        &v11,
        0);
      if ( (int)CamGetCandidateUserSessionIds(&v18, &v11) < 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>(&v11);
        break;
      }
      v14 = 0;
      v15 = 0;
      std::vector<unsigned long>::insert<unsigned long *,0>(
        (unsigned int)&v14,
        (unsigned int)&v12,
        0,
        v11,
        v11 + 4LL * v18);
      v6 = (_QWORD *)std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned long>>>,unsigned long>(
                       v13,
                       v14,
                       *((_QWORD *)&v14 + 1),
                       &v17);
      if ( *v6 != *((_QWORD *)&v14 + 1) )
      {
        if ( (unsigned int)(a2 - 3) <= 1 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x304,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\pincachemanager.cpp",
            (const char *)0x8000FFFFLL,
            v10);
        if ( (_QWORD)v14 )
        {
          std::_Deallocate<16>((void *)v14, (v15 - v14) & 0xFFFFFFFFFFFFFFFCuLL);
          v14 = 0;
          v15 = 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>(&v11);
        return;
      }
      if ( (_QWORD)v14 )
      {
        std::_Deallocate<16>((void *)v14, (v15 - v14) & 0xFFFFFFFFFFFFFFFCuLL);
        v14 = 0;
        v15 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>(&v11);
    }
  }
  *(_DWORD *)(a1 + 80) = a2;
  if ( a2 )
  {
    v7 = a2 - 1;
    if ( !v7 )
      goto LABEL_22;
    v8 = v7 - 1;
    if ( !v8 )
    {
LABEL_21:
      *(_QWORD *)(a1 + 72) = 0;
      UuidCreate((UUID *)(a1 + 48));
      goto LABEL_22;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
LABEL_22:
      GetSystemTimeAsFileTime((LPFILETIME)(a1 + 64));
      return;
    }
    if ( v9 == 1 )
      goto LABEL_21;
  }
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x321,
    (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\pincachemanager.cpp",
    (const char *)0x8000FFFFLL,
    v10);
}

```

## disassembly

```asm
0x180036364  mov     [rsp+arg_10], r8d
0x180036369  mov     [rsp+arg_8], edx
0x18003636d  mov     [rsp+arg_0], rcx
0x180036372  push    rsi
0x180036373  push    rdi
0x180036374  sub     rsp, 68h
0x180036378  mov     edi, edx
0x18003637a  mov     rsi, rcx
0x18003637d  test    r8d, r8d
0x180036380  jz      loc_1800364F4
0x180036386  call    IsCamIsCandidateUserPresent
0x18003638b  test    al, al
0x18003638d  jz      loc_1800364E3
0x180036393  xor     al, al
0x180036395  test    al, al
0x180036397  jnz     loc_1800364E3
0x18003639d  mov     [rsp+78h+arg_18], 0
0x1800363a8  mov     [rsp+78h+var_48], 0
0x1800363b1  xor     edx, edx
0x1800363b3  lea     rcx, [rsp+78h+var_48]
0x1800363b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAKP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAKPEAK$0A@$$T@details@wil@@@details@wil@@QEAAXPEAK@Z
0x1800363bd  lea     rdx, [rsp+78h+var_48]
0x1800363c2  lea     rcx, [rsp+78h+arg_18]
0x1800363ca  call    cs:__imp_CamGetCandidateUserSessionIds
0x1800363d0  test    eax, eax
0x1800363d2  jns     short loc_1800363E3
0x1800363d4  lea     rcx, [rsp+78h+var_48]
0x1800363d9  call    ??1?$unique_storage@U?$resource_policy@PEAKP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAKPEAK$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800363de  jmp     loc_1800364E3
0x1800363e3  xorps   xmm0, xmm0
0x1800363e6  movdqu  [rsp+78h+var_30], xmm0
0x1800363ec  mov     [rsp+78h+var_20], 0
0x1800363f5  mov     eax, [rsp+78h+arg_18]
0x1800363fc  mov     r9, [rsp+78h+var_48]
0x180036401  lea     rax, [r9+rax*4]
0x180036405  mov     qword ptr [rsp+78h+var_58], rax; int
0x18003640a  xor     r8d, r8d
0x18003640d  lea     rdx, [rsp+78h+var_40]
0x180036412  lea     rcx, [rsp+78h+var_30]
0x180036417  call    ??$insert@PEAK$0A@@?$vector@KV?$allocator@K@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@1@PEAK1@Z
0x18003641c  lea     r9, [rsp+78h+arg_10]
0x180036424  mov     r8, qword ptr [rsp+78h+var_30+8]
0x180036429  mov     rdx, qword ptr [rsp+78h+var_30]
0x18003642e  lea     rcx, [rsp+78h+var_38]
0x180036433  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@std@@K@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@0@V10@V10@AEBK@Z
0x180036438  mov     rcx, qword ptr [rsp+78h+var_30+8]
0x18003643d  cmp     [rax], rcx
0x180036440  jnz     short loc_180036480
0x180036442  mov     rcx, qword ptr [rsp+78h+var_30]
0x180036447  test    rcx, rcx
0x18003644a  jz      short loc_18003646F
0x18003644c  mov     rdx, [rsp+78h+var_20]
0x180036451  sub     rdx, rcx
0x180036454  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180036458  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z
0x18003645d  xorps   xmm0, xmm0
0x180036460  movdqu  [rsp+78h+var_30], xmm0
0x180036466  mov     [rsp+78h+var_20], 0
0x18003646f  lea     rcx, [rsp+78h+var_48]
0x180036474  call    ??1?$unique_storage@U?$resource_policy@PEAKP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAKPEAK$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036479  mov     al, 1
0x18003647b  jmp     loc_180036395
0x180036480  lea     eax, [rdi-3]
0x180036483  cmp     eax, 1
0x180036486  setbe   al
0x180036489  mov     rcx, [rsp+78h]; this
0x18003648e  test    al, al
0x180036490  jz      short loc_1800364AA
0x180036492  mov     r9d, 8000FFFFh; char *
0x180036498  lea     r8, aOnecoreDsSecur_24
0x18003649f  mov     edx, 304h; void *
0x1800364a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800364a9  nop
0x1800364aa  mov     rcx, qword ptr [rsp+78h+var_30]
0x1800364af  test    rcx, rcx
0x1800364b2  jz      short loc_1800364D7
0x1800364b4  mov     rdx, [rsp+78h+var_20]
0x1800364b9  sub     rdx, rcx
0x1800364bc  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800364c0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z
0x1800364c5  xorps   xmm0, xmm0
0x1800364c8  movdqu  [rsp+78h+var_30], xmm0
0x1800364ce  mov     [rsp+78h+var_20], 0
0x1800364d7  lea     rcx, [rsp+78h+var_48]
0x1800364dc  call    ??1?$unique_storage@U?$resource_policy@PEAKP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAKPEAK$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800364e1  jmp     short loc_18003654F
0x1800364e3  jmp     short loc_1800364F4
0x1800364e5  mov     rsi, [rsp+78h+arg_0]
0x1800364ed  mov     edi, [rsp+78h+arg_8]
0x1800364f4  mov     [rsi+50h], edi
0x1800364f7  test    edi, edi
0x1800364f9  jz      short loc_180036532
0x1800364fb  sub     edi, 1
0x1800364fe  jz      short loc_180036521
0x180036500  sub     edi, 1
0x180036503  jz      short loc_18003650F
0x180036505  sub     edi, 1
0x180036508  jz      short loc_180036521
0x18003650a  cmp     edi, 1
0x18003650d  jnz     short loc_180036532
0x18003650f  mov     qword ptr [rsi+48h], 0
0x180036517  lea     rcx, [rsi+30h]; Uuid
0x18003651b  call    cs:__imp_UuidCreate
0x180036521  lea     rcx, [rsi+40h]
0x180036525  add     rsp, 68h
0x180036529  pop     rdi
0x18003652a  pop     rsi
0x18003652b  jmp     cs:__imp_GetSystemTimeAsFileTime
0x180036532  mov     rcx, [rsp+78h]; this
0x180036537  mov     r9d, 8000FFFFh; char *
0x18003653d  lea     r8, aOnecoreDsSecur_24
0x180036544  mov     edx, 321h; void *
0x180036549  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z
0x18003654e  nop
0x18003654f  add     rsp, 68h
0x180036553  pop     rdi
0x180036554  pop     rsi
0x180036555  retn
```
