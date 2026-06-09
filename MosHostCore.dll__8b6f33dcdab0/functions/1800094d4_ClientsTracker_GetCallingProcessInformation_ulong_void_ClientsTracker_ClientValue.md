# ClientsTracker::GetCallingProcessInformation(ulong,void *,ClientsTracker::ClientValue *)

- ea: `0x1800094d4`
- end: `0x18000989c`
- name: `?GetCallingProcessInformation@ClientsTracker@@AEAAJKPEAXPEAUClientValue@1@@Z`
- size: `968`
- prototype: `__int64 __fastcall(ClientsTracker *this, unsigned int, void *, struct ClientsTracker::ClientValue *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009128`

## callees

- `0x180003410`
- `0x18000381c`
- `0x180003f7c`
- `0x180004d3c`
- `0x180004fc0`
- `0x180007a88`
- `0x1800080b4`
- `0x180008e24`
- `0x180009064`
- `0x1800093bc`
- `0x1800094d4`
- `0x18000b0b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000967c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000981f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000967c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000981f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000965e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000965e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009672`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009672`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009815`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009815`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000976e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000976e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800097bd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800097bd`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800095e6`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180009751`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800095e6`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180009751`
- `RPCRT4!RpcImpersonateClient` at `0x180009539`
- `RPCRT4!RpcImpersonateClient` at `0x180009539`
- `RPCRT4!RpcRevertToSelf` at `0x1800095af`
- `RPCRT4!RpcRevertToSelf` at `0x1800096bc`
- `RPCRT4!RpcRevertToSelf` at `0x180009721`
- `RPCRT4!RpcRevertToSelf` at `0x1800095af`
- `RPCRT4!RpcRevertToSelf` at `0x1800096bc`
- `RPCRT4!RpcRevertToSelf` at `0x180009721`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180009713`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180009713`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000959c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000959c`
- `ZTrace_Maps!ZTraceHelper` at `0x180009573`
- `ZTrace_Maps!ZTraceHelper` at `0x180009573`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800096a9`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800097f4`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800096a9`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800097f4`

## string_xrefs

- `0x180009553`: `Can't impersonate. Error: 0x%08X`
- `0x18000956a`: `Impersonator<struct ImpersonatorRpcClientTraits>::Impersonator`

## pseudocode

```c
__int64 __fastcall ClientsTracker::GetCallingProcessInformation(
        ClientsTracker *this,
        unsigned int a2,
        void *a3,
        struct ClientsTracker::ClientValue *a4)
{
  RPC_STATUS v7; // eax
  int v8; // ecx
  unsigned int v9; // ebx
  RPC_STATUS v10; // eax
  signed int v11; // edi
  PHANDLE v12; // rbx
  _DWORD *v13; // rax
  HANDLE CurrentThread; // rax
  signed int v15; // eax
  RPC_STATUS v16; // eax
  signed int v17; // esi
  int CallerPackageFamilyName; // eax
  RPC_STATUS v19; // eax
  signed int v20; // esi
  PSID v21; // rdi
  signed int LastError; // eax
  int v23; // r8d
  void *v24; // rcx
  signed int v26; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-98h] BYREF
  PSID pSid; // [rsp+70h] [rbp-90h] BYREF
  PHANDLE TokenHandle[2]; // [rsp+78h] [rbp-88h] BYREF
  char *v30; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v31; // [rsp+90h] [rbp-70h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  struct _EXCEPTION_RECORD pExceptionRecord; // [rsp+A0h] [rbp-60h] BYREF

  *(_OWORD *)TokenHandle = 0;
  pSid = 0;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v26 = -2147024875;
  if ( a3 )
  {
    v7 = RpcImpersonateClient(a3);
    if ( v7 )
    {
      v26 = v7 | 0x80010000;
      ZTraceHelper(
        0,
        "Impersonator<struct ImpersonatorRpcClientTraits>::Impersonator",
        21,
        &v26,
        "Can't impersonate. Error: 0x%08X",
        v7 | 0x80010000);
      v8 = v26;
      goto LABEL_7;
    }
    v8 = 0;
  }
  else
  {
    v8 = -2147023888;
  }
  v26 = v8;
LABEL_7:
  if ( v8 >= 0 )
  {
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
      TokenHandle,
      0);
    v12 = TokenHandle[0];
    if ( !TokenHandle[0] )
    {
      v13 = operator new(0x18u);
      *(_OWORD *)v13 = 0;
      v13[2] = 1;
      v13[3] = 1;
      *(_QWORD *)v13 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::`vftable';
      *((_QWORD *)v13 + 2) = 0;
      v30 = (char *)(v13 + 4);
      v31 = (std::_Ref_count_base *)v13;
      std::shared_ptr<OdmlMapDataPackage>::operator=(TokenHandle, &v30);
      if ( v31 )
        std::_Ref_count_base::_Decref(v31);
      v12 = TokenHandle[0];
    }
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, v12) )
    {
      CallerPackageFamilyName = ClientsTracker::GetCallerPackageFamilyName(this, a2, (char *)a4 + 16);
      if ( CallerPackageFamilyName < 0 )
        ZTraceReportIgnore(CallerPackageFamilyName, "ClientsTracker::GetCallingProcessInformation", 561, this);
      if ( v26 >= 0 )
      {
        v19 = RpcRevertToSelf();
        v20 = v19 != 0 ? v19 | 0x80010000 : 0;
        if ( v20 < 0 )
        {
          memset_0(&pExceptionRecord.ExceptionFlags, 0, 0x94u);
          pExceptionRecord.ExceptionCode = v20;
          RaiseFailFastException(&pExceptionRecord, 0, 1u);
        }
      }
      v21 = pSid;
      if ( pSid )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
        FreeSid(v21);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
      }
      pSid = 0;
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        if ( v12 )
          v24 = *v12;
        else
          v24 = 0;
        if ( CheckTokenMembership(v24, pSid, &IsMember) )
        {
          v9 = 0;
          if ( !IsMember && (PHANDLE *)((char *)a4 + 48) != TokenHandle )
            std::shared_ptr<OdmlMapDataPackage>::operator=((char *)a4 + 48, TokenHandle);
          goto LABEL_50;
        }
        LastError = GetLastError();
        if ( LastError )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          LastError = -2143748092;
        }
        v23 = 572;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          LastError = -2143748092;
        }
        v23 = 569;
      }
      v9 = ZTraceReportOrigination(LastError, "ClientsTracker::GetCallingProcessInformation", v23, this);
      goto LABEL_50;
    }
    v15 = GetLastError();
    if ( v15 )
    {
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
    }
    else
    {
      v15 = -2143748092;
    }
    v9 = ZTraceReportOrigination(v15, "ClientsTracker::GetCallingProcessInformation", 559, this);
    if ( v26 >= 0 )
    {
      v16 = RpcRevertToSelf();
      v17 = v16 != 0 ? v16 | 0x80010000 : 0;
      if ( v17 < 0 )
      {
        memset_0(&pExceptionRecord.ExceptionFlags, 0, 0x94u);
        pExceptionRecord.ExceptionCode = v17;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v9 = ZTraceReportPropagation(v8, "ClientsTracker::GetCallingProcessInformation", 553, this);
    if ( v26 >= 0 )
    {
      v10 = RpcRevertToSelf();
      v11 = v10 != 0 ? v10 | 0x80010000 : 0;
      if ( v11 < 0 )
      {
        memset_0(&pExceptionRecord.ExceptionFlags, 0, 0x94u);
        pExceptionRecord.ExceptionCode = v11;
LABEL_11:
        RaiseFailFastException(&pExceptionRecord, 0, 1u);
      }
    }
  }
LABEL_50:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
  std::shared_ptr<OdmlMapDataPackage>::~shared_ptr<OdmlMapDataPackage>(TokenHandle);
  return v9;
}

```

## disassembly

```asm
0x1800094d4  push    rbp
0x1800094d6  push    rbx
0x1800094d7  push    rsi
0x1800094d8  push    rdi
0x1800094d9  push    r12
0x1800094db  push    r13
0x1800094dd  push    r14
0x1800094df  push    r15
0x1800094e1  lea     rbp, [rsp-58h]
0x1800094e6  sub     rsp, 158h
0x1800094ed  mov     rax, cs:__security_cookie
0x1800094f4  xor     rax, rsp
0x1800094f7  mov     [rbp+90h+var_50], rax
0x1800094fb  mov     r15, r9
0x1800094fe  mov     esi, edx
0x180009500  mov     r14, rcx
0x180009503  xor     r12d, r12d
0x180009506  xorps   xmm1, xmm1
0x180009509  movdqu  xmmword ptr [rsp+190h+TokenHandle], xmm1
0x18000950f  mov     [rsp+190h+pSid], r12
0x180009514  mov     [rsp+190h+IsMember], r12d
0x180009519  mov     dword ptr [rbp+90h+pIdentifierAuthority.Value], r12d
0x18000951d  mov     word ptr [rbp+90h+pIdentifierAuthority.Value+4], 500h
0x180009523  mov     [rsp+190h+var_130], 80070015h
0x18000952b  mov     r13d, 80010000h
0x180009531  test    r8, r8
0x180009534  jz      short loc_18000957F
0x180009536  mov     rcx, r8; BindingHandle
0x180009539  call    cs:__imp_RpcImpersonateClient
0x18000953f  test    eax, eax
0x180009541  jnz     short loc_180009548
0x180009543  mov     ecx, r12d
0x180009546  jmp     short loc_180009584
0x180009548  or      eax, r13d
0x18000954b  mov     [rsp+190h+var_130], eax
0x18000954f  mov     [rsp+190h+nSubAuthority3], eax
0x180009553  lea     rax, aCanTImpersonat; "Can't impersonate. Error: 0x%08X"
0x18000955a  mov     qword ptr [rsp+190h+nSubAuthority2], rax
0x18000955f  lea     r9, [rsp+190h+var_130]
0x180009564  mov     r8d, 15h
0x18000956a  lea     rdx, aImpersonatorSt; "Impersonator<struct ImpersonatorRpcClie"...
0x180009571  xor     ecx, ecx
0x180009573  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180009579  mov     ecx, [rsp+190h+var_130]
0x18000957d  jmp     short loc_180009588
0x18000957f  mov     ecx, 800703F0h
0x180009584  mov     [rsp+190h+var_130], ecx
0x180009588  test    ecx, ecx
0x18000958a  jns     short loc_1800095F1
0x18000958c  mov     r9, r14
0x18000958f  mov     r8d, 229h
0x180009595  lea     rdx, aClientstracker_3; "ClientsTracker::GetCallingProcessInform"...
0x18000959c  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800095a2  mov     ebx, eax
0x1800095a4  cmp     [rsp+190h+var_130], r12d
0x1800095a9  jl      loc_180009865
0x1800095af  call    cs:__imp_RpcRevertToSelf
0x1800095b5  mov     ecx, eax
0x1800095b7  or      ecx, r13d
0x1800095ba  neg     eax
0x1800095bc  sbb     edi, edi
0x1800095be  and     edi, ecx
0x1800095c0  jge     loc_180009865
0x1800095c6  xor     edx, edx; Val
0x1800095c8  mov     r8d, 94h; Size
0x1800095ce  lea     rcx, [rbp+90h+pExceptionRecord.ExceptionFlags]; void *
0x1800095d2  call    memset_0
0x1800095d7  mov     [rbp+90h+pExceptionRecord.ExceptionCode], edi
0x1800095da  mov     r8d, 1; dwFlags
0x1800095e0  xor     edx, edx; pContextRecord
0x1800095e2  lea     rcx, [rbp+90h+pExceptionRecord]; pExceptionRecord
0x1800095e6  call    cs:__imp_RaiseFailFastException
0x1800095ec  jmp     loc_180009865
0x1800095f1  xor     edx, edx
0x1800095f3  lea     rcx, [rsp+190h+TokenHandle]
0x1800095f8  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x1800095fd  mov     edi, 1
0x180009602  mov     rbx, [rsp+190h+TokenHandle]
0x180009607  test    rbx, rbx
0x18000960a  jnz     short loc_18000965E
0x18000960c  lea     ecx, [rdi+17h]; Size
0x18000960f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009614  mov     [rbp+90h+var_108], rax
0x180009618  xorps   xmm0, xmm0
0x18000961b  movups  xmmword ptr [rax], xmm0
0x18000961e  mov     [rax+8], edi
0x180009621  mov     [rax+0Ch], edi
0x180009624  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x18000962b  mov     [rax], rcx
0x18000962e  lea     rcx, [rax+10h]
0x180009632  mov     [rcx], r12
0x180009635  mov     [rbp+90h+var_108], rcx
0x180009639  mov     [rbp+90h+var_100], rax
0x18000963d  lea     rdx, [rbp+90h+var_108]
0x180009641  lea     rcx, [rsp+190h+TokenHandle]
0x180009646  call    ??4?$shared_ptr@VOdmlMapDataPackage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<OdmlMapDataPackage>::operator=(std::shared_ptr<OdmlMapDataPackage> &&)
0x18000964b  mov     rcx, [rbp+90h+var_100]; this
0x18000964f  test    rcx, rcx
0x180009652  jz      short loc_180009659
0x180009654  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009659  mov     rbx, [rsp+190h+TokenHandle]
0x18000965e  call    cs:__imp_GetCurrentThread
0x180009664  mov     r9, rbx; TokenHandle
0x180009667  mov     r8d, edi; OpenAsSelf
0x18000966a  mov     edx, 0Ch; DesiredAccess
0x18000966f  mov     rcx, rax; ThreadHandle
0x180009672  call    cs:__imp_OpenThreadToken
0x180009678  test    eax, eax
0x18000967a  jnz     short loc_1800096EF
0x18000967c  call    cs:__imp_GetLastError
0x180009682  test    eax, eax
0x180009684  jz      short loc_180009692
0x180009686  jle     short loc_180009697
0x180009688  movzx   eax, ax
0x18000968b  or      eax, 80070000h
0x180009690  jmp     short loc_180009697
0x180009692  mov     eax, 80390004h
0x180009697  mov     r9, r14
0x18000969a  mov     r8d, 22Fh
0x1800096a0  lea     rdx, aClientstracker_3; "ClientsTracker::GetCallingProcessInform"...
0x1800096a7  mov     ecx, eax
0x1800096a9  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800096af  mov     ebx, eax
0x1800096b1  cmp     [rsp+190h+var_130], r12d
0x1800096b6  jl      loc_180009865
0x1800096bc  call    cs:__imp_RpcRevertToSelf
0x1800096c2  mov     ecx, eax
0x1800096c4  or      ecx, r13d
0x1800096c7  neg     eax
0x1800096c9  sbb     esi, esi
0x1800096cb  and     esi, ecx
0x1800096cd  jge     loc_180009865
0x1800096d3  xor     edx, edx; Val
0x1800096d5  mov     r8d, 94h; Size
0x1800096db  lea     rcx, [rbp+90h+pExceptionRecord.ExceptionFlags]; void *
0x1800096df  call    memset_0
0x1800096e4  mov     [rbp+90h+pExceptionRecord.ExceptionCode], esi
0x1800096e7  mov     r8d, edi
0x1800096ea  jmp     loc_1800095E0
0x1800096ef  lea     r8, [r15+10h]
0x1800096f3  mov     edx, esi
0x1800096f5  mov     rcx, r14
0x1800096f8  call    ?GetCallerPackageFamilyName@ClientsTracker@@AEAAJKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ClientsTracker::GetCallerPackageFamilyName(ulong,std::wstring *)
0x1800096fd  test    eax, eax
0x1800096ff  jns     short loc_18000971A
0x180009701  mov     r9, r14
0x180009704  mov     r8d, 231h
0x18000970a  lea     rdx, aClientstracker_3; "ClientsTracker::GetCallingProcessInform"...
0x180009711  mov     ecx, eax
0x180009713  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180009719  nop
0x18000971a  cmp     [rsp+190h+var_130], r12d
0x18000971f  jl      short loc_180009757
0x180009721  call    cs:__imp_RpcRevertToSelf
0x180009727  mov     ecx, eax
0x180009729  or      ecx, r13d
0x18000972c  neg     eax
0x18000972e  sbb     esi, esi
0x180009730  and     esi, ecx
0x180009732  jge     short loc_180009757
0x180009734  xor     edx, edx; Val
0x180009736  mov     r8d, 94h; Size
0x18000973c  lea     rcx, [rbp+90h+pExceptionRecord.ExceptionFlags]; void *
0x180009740  call    memset_0
0x180009745  mov     [rbp+90h+pExceptionRecord.ExceptionCode], esi
0x180009748  mov     r8d, edi; dwFlags
0x18000974b  xor     edx, edx; pContextRecord
0x18000974d  lea     rcx, [rbp+90h+pExceptionRecord]; pExceptionRecord
0x180009751  call    cs:__imp_RaiseFailFastException
0x180009757  mov     rdi, [rsp+190h+pSid]
0x18000975c  test    rdi, rdi
0x18000975f  jz      short loc_18000977E
0x180009761  lea     rcx, [rsp+190h+var_130]; this
0x180009766  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000976b  mov     rcx, rdi; pSid
0x18000976e  call    cs:__imp_FreeSid
0x180009774  lea     rcx, [rsp+190h+var_130]; this
0x180009779  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000977e  mov     [rsp+190h+pSid], r12
0x180009783  lea     rax, [rsp+190h+pSid]
0x180009788  mov     [rsp+190h+var_140], rax; pSid
0x18000978d  mov     [rsp+190h+nSubAuthority7], r12d; nSubAuthority7
0x180009792  mov     [rsp+190h+nSubAuthority6], r12d; nSubAuthority6
0x180009797  mov     [rsp+190h+nSubAuthority5], r12d; nSubAuthority5
0x18000979c  mov     [rsp+190h+nSubAuthority4], r12d; nSubAuthority4
0x1800097a1  mov     [rsp+190h+nSubAuthority3], r12d; nSubAuthority3
0x1800097a6  mov     [rsp+190h+nSubAuthority2], r12d; nSubAuthority2
0x1800097ab  mov     r9d, 220h; nSubAuthority1
0x1800097b1  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800097b7  mov     dl, 2; nSubAuthorityCount
0x1800097b9  lea     rcx, [rbp+90h+pIdentifierAuthority]; pIdentifierAuthority
0x1800097bd  call    cs:__imp_AllocateAndInitializeSid
0x1800097c3  test    eax, eax
0x1800097c5  jnz     short loc_1800097FE
0x1800097c7  call    cs:__imp_GetLastError
0x1800097cd  test    eax, eax
0x1800097cf  jz      short loc_1800097DD
0x1800097d1  jle     short loc_1800097E2
0x1800097d3  movzx   eax, ax
0x1800097d6  or      eax, 80070000h
0x1800097db  jmp     short loc_1800097E2
0x1800097dd  mov     eax, 80390004h
0x1800097e2  mov     r8d, 239h
0x1800097e8  mov     r9, r14
0x1800097eb  lea     rdx, aClientstracker_3; "ClientsTracker::GetCallingProcessInform"...
0x1800097f2  mov     ecx, eax
0x1800097f4  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800097fa  mov     ebx, eax
0x1800097fc  jmp     short loc_180009865
0x1800097fe  test    rbx, rbx
0x180009801  jz      short loc_180009808
0x180009803  mov     rcx, [rbx]
0x180009806  jmp     short loc_18000980B
0x180009808  mov     rcx, r12; TokenHandle
0x18000980b  lea     r8, [rsp+190h+IsMember]; IsMember
0x180009810  mov     rdx, [rsp+190h+pSid]; SidToCheck
0x180009815  call    cs:__imp_CheckTokenMembership
0x18000981b  test    eax, eax
0x18000981d  jnz     short loc_180009842
0x18000981f  call    cs:__imp_GetLastError
0x180009825  test    eax, eax
0x180009827  jz      short loc_180009835
0x180009829  jle     short loc_18000983A
0x18000982b  movzx   eax, ax
0x18000982e  or      eax, 80070000h
0x180009833  jmp     short loc_18000983A
0x180009835  mov     eax, 80390004h
0x18000983a  mov     r8d, 23Ch
0x180009840  jmp     short loc_1800097E8
0x180009842  mov     ebx, r12d
0x180009845  cmp     [rsp+190h+IsMember], r12d
0x18000984a  jnz     short loc_180009865
0x18000984c  lea     rcx, [r15+30h]
0x180009850  lea     rax, [rsp+190h+TokenHandle]
0x180009855  cmp     rcx, rax
0x180009858  jz      short loc_180009865
0x18000985a  lea     rdx, [rsp+190h+TokenHandle]
0x18000985f  call    ??4?$shared_ptr@VOdmlMapDataPackage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<OdmlMapDataPackage>::operator=(std::shared_ptr<OdmlMapDataPackage> &&)
0x180009864  nop
0x180009865  lea     rcx, [rsp+190h+pSid]
0x18000986a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000986f  nop
0x180009870  lea     rcx, [rsp+190h+TokenHandle]
0x180009875  call    ??1?$shared_ptr@VOdmlMapDataPackage@@@std@@QEAA@XZ; std::shared_ptr<OdmlMapDataPackage>::~shared_ptr<OdmlMapDataPackage>(void)
0x18000987a  mov     eax, ebx
0x18000987c  mov     rcx, [rbp+90h+var_50]
0x180009880  xor     rcx, rsp; StackCookie
0x180009883  call    __security_check_cookie
0x180009888  add     rsp, 158h
0x18000988f  pop     r15
0x180009891  pop     r14
0x180009893  pop     r13
0x180009895  pop     r12
0x180009897  pop     rdi
0x180009898  pop     rsi
0x180009899  pop     rbx
0x18000989a  pop     rbp
0x18000989b  retn
```
