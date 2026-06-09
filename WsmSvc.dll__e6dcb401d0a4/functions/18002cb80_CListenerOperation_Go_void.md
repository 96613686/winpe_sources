# CListenerOperation::Go(void)

- ea: `0x18002cb80`
- end: `0x18002cf71`
- name: `?Go@CListenerOperation@@QEAAXXZ`
- size: `1009`
- prototype: `void __fastcall(CListenerOperation *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c610`
- `0x180144f30`

## callees

- `0x180005d10`
- `0x18002aee0`
- `0x18002cb80`
- `0x18002dd20`
- `0x1800567e0`
- `0x180057de0`
- `0x18005a5b0`
- `0x1800831c0`
- `0x180097248`
- `0x1800976c4`
- `0x1800cb43c`
- `0x1800dfaf8`
- `0x180112380`
- `0x18011a6d4`
- `0x18017203c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cbf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cbf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccc5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002cca5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002cca5`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002cc23`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002cc23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cdff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cdff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002cf42`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002cf42`

## string_xrefs

- `0x18002cd3b`: `@Complete`
- `0x18002cd74`: `@Complete`
- `0x18002ce6d`: `@Configure`
- `0x18002cf4a`: `@Configure`
- `0x18002cccb`: `ImpersonateLoggedOnUser`
- `0x18002cc49`: `ImpersonateSelf`

## pseudocode

```c
void __fastcall CListenerOperation::Go(CListenerOperation *this)
{
  DWORD *v2; // r15
  __int64 v3; // rcx
  char v4; // di
  __int64 v5; // rsi
  void (__fastcall *v6)(__int64, _QWORD, __int64, const wchar_t *, DWORD); // rdi
  DWORD LastError; // ebx
  DWORD v8; // eax
  const wchar_t *v9; // r9
  PVOID *v10; // rax
  unsigned int Value; // eax
  const wchar_t *v12; // rsi
  int v13; // ebx
  bool IsInitialized; // al
  const wchar_t *v15; // rcx
  signed __int32 v16; // eax
  struct _TP_WORK *v17; // rcx
  signed __int32 v18; // eax
  int v19; // [rsp+30h] [rbp-48h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids, this);
  v2 = (DWORD *)((char *)this + 1136);
  CWSManCriticalSection::Acquire((CListenerOperation *)((char *)this + 1136));
  *((_DWORD *)this + 280) = 1;
  if ( *((_DWORD *)this + 284) )
    SetLastError(*((_DWORD *)this + 284));
  else
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1144));
  v3 = *((_QWORD *)this + 264);
  if ( !*(_QWORD *)(v3 + 672) )
  {
    v4 = 0;
    goto LABEL_18;
  }
  v4 = 1;
  if ( !(unsigned int)CSecurity::IsAnonymousLimitedAccessUser(*(const unsigned __int16 **)(v3 + 16)) )
  {
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)(*((_QWORD *)this + 264) + 672LL)) )
    {
      v5 = *((_QWORD *)this + 263);
      v6 = *(void (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *, DWORD))(*(_QWORD *)v5 + 64LL);
      LastError = GetLastError();
      v8 = GetLastError();
      v9 = L"ImpersonateLoggedOnUser";
      goto LABEL_11;
    }
    goto LABEL_18;
  }
  if ( ImpersonateSelf(SecurityImpersonation) )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
LABEL_19:
      if ( *((_DWORD *)this + 67) )
      {
        if ( (unsigned int)PacketParser::PacketElement<unsigned long>::GetValue(*((_QWORD *)this + 32) + 3768LL) )
        {
          Value = PacketParser::PacketElement<unsigned long>::GetValue(*((_QWORD *)this + 32) + 3768LL);
          if ( !Timer::StartTimer((char *)this + 32, *((struct IRequestContext **)this + 263), Value) )
            goto LABEL_46;
        }
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      v12 = L"true";
      if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x1000) != 0 )
      {
        v13 = *((_DWORD *)this + 2) & 0x7FFFFFFF;
        IsInitialized = IOperation::IsInitialized(this);
        v15 = L"true";
        if ( !IsInitialized )
          v15 = L"false";
        WPP_SF_qsSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"@Complete", (__int64)v15, v13);
      }
      do
      {
        v16 = *((_DWORD *)this + 2);
        if ( v16 >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 263) + 72LL))(*((_QWORD *)this + 263), 1115);
          goto LABEL_46;
        }
      }
      while ( v16 != _InterlockedCompareExchange((volatile signed __int32 *)this + 2, v16 + 1, v16) );
      if ( !(*(unsigned __int8 (__fastcall **)(CListenerOperation *))(*(_QWORD *)this + 200LL))(this) )
      {
        IOperation::Release(this, "@Complete");
        goto LABEL_46;
      }
      CWSManCriticalSection::Acquire((CListenerOperation *)((char *)this + 1136));
      *((_DWORD *)this + 280) = 0;
      if ( *v2 )
        SetLastError(*v2);
      else
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1144));
      v17 = (struct _TP_WORK *)*((_QWORD *)this + 150);
      if ( v17 )
        goto LABEL_47;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        v19 = *((_DWORD *)this + 2) & 0x7FFFFFFF;
        if ( !IOperation::IsInitialized(this) )
          v12 = L"false";
        WPP_SF_qsSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"@Configure", (__int64)v12, v19);
      }
      v18 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
      if ( v18 == 0x80000000 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\operation.cpp", 174, L"174", 0x54Fu, 0);
      }
      else if ( !v18 )
      {
        (*(void (__fastcall **)(CListenerOperation *))(*(_QWORD *)this + 24LL))(this);
      }
      goto LABEL_49;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids);
LABEL_18:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  v5 = *((_QWORD *)this + 263);
  v6 = *(void (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *, DWORD))(*(_QWORD *)v5 + 64LL);
  LastError = GetLastError();
  v8 = GetLastError();
  v9 = L"ImpersonateSelf";
LABEL_11:
  v6(v5, v8, 1077134180, v9, LastError);
  v4 = 0;
LABEL_46:
  CWSManCriticalSection::Acquire((CListenerOperation *)((char *)this + 1136));
  *((_DWORD *)this + 280) = 0;
  CWSManCriticalSection::Release((CListenerOperation *)((char *)this + 1136));
  (*(void (__fastcall **)(CListenerOperation *, __int64, _QWORD))(*(_QWORD *)this + 80LL))(this, 1, 0);
  CListenerOperation::AcknowledgeIfNecessary(this);
  IOperation::Shutdown(this);
  v17 = (struct _TP_WORK *)*((_QWORD *)this + 150);
  if ( v17 )
  {
LABEL_47:
    SubmitThreadpoolWork(v17);
    goto LABEL_49;
  }
  IOperation::Release(this, "@Configure");
LABEL_49:
  if ( v4 )
    CSecurity::RevertToSelf();
}

```

## disassembly

```asm
0x18002cb80  push    rbx
0x18002cb82  push    rsi
0x18002cb83  push    rdi
0x18002cb84  push    r12
0x18002cb86  push    r14
0x18002cb88  push    r15
0x18002cb8a  sub     rsp, 48h
0x18002cb8e  mov     r14, rcx
0x18002cb91  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb98  lea     r12, WPP_GLOBAL_Control
0x18002cb9f  mov     ebx, 400h
0x18002cba4  cmp     rcx, r12
0x18002cba7  jz      short loc_18002CBC6
0x18002cba9  test    [rcx+1Ch], ebx
0x18002cbac  jz      short loc_18002CBC6
0x18002cbae  mov     rcx, [rcx+10h]
0x18002cbb2  lea     r8, WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids
0x18002cbb9  mov     edx, 15h
0x18002cbbe  mov     r9, r14
0x18002cbc1  call    WPP_SF_q
0x18002cbc6  lea     r15, [r14+470h]
0x18002cbcd  mov     rcx, r15; this
0x18002cbd0  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x18002cbd5  mov     dword ptr [r14+460h], 1
0x18002cbe0  mov     ecx, [r15]; dwErrCode
0x18002cbe3  test    ecx, ecx
0x18002cbe5  jnz     short loc_18002CBF3
0x18002cbe7  lea     rcx, [r15+8]; lpCriticalSection
0x18002cbeb  call    cs:__imp_LeaveCriticalSection
0x18002cbf1  jmp     short loc_18002CBF9
0x18002cbf3  call    cs:__imp_SetLastError
0x18002cbf9  mov     rcx, [r14+840h]
0x18002cc00  cmp     qword ptr [rcx+2A0h], 0
0x18002cc08  jz      loc_18002CCD7
0x18002cc0e  mov     rcx, [rcx+10h]; unsigned __int16 *
0x18002cc12  mov     dil, 1
0x18002cc15  call    ?IsAnonymousLimitedAccessUser@CSecurity@@SAHPEBG@Z; CSecurity::IsAnonymousLimitedAccessUser(ushort const *)
0x18002cc1a  test    eax, eax
0x18002cc1c  jz      short loc_18002CC97
0x18002cc1e  mov     ecx, 2; ImpersonationLevel
0x18002cc23  call    cs:__imp_ImpersonateSelf
0x18002cc29  test    eax, eax
0x18002cc2b  jnz     short loc_18002CC6F
0x18002cc2d  mov     rsi, [r14+838h]
0x18002cc34  mov     rax, [rsi]
0x18002cc37  mov     rdi, [rax+40h]
0x18002cc3b  call    cs:__imp_GetLastError
0x18002cc41  mov     ebx, eax
0x18002cc43  call    cs:__imp_GetLastError
0x18002cc49  lea     r9, aImpersonatesel; "ImpersonateSelf"
0x18002cc50  mov     edx, eax
0x18002cc52  mov     dword ptr [rsp+78h+var_58], ebx
0x18002cc56  mov     rax, rdi
0x18002cc59  mov     r8d, 4033C364h
0x18002cc5f  mov     rcx, rsi
0x18002cc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc67  xor     dil, dil
0x18002cc6a  jmp     loc_18002CEF2
0x18002cc6f  mov     rax, cs:WPP_GLOBAL_Control
0x18002cc76  cmp     rax, r12
0x18002cc79  jz      short loc_18002CCE1
0x18002cc7b  test    [rax+1Ch], ebx
0x18002cc7e  jz      short loc_18002CCE1
0x18002cc80  mov     rcx, [rax+10h]
0x18002cc84  lea     r8, WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids
0x18002cc8b  mov     edx, 16h
0x18002cc90  call    WPP_SF_
0x18002cc95  jmp     short loc_18002CCDA
0x18002cc97  mov     rcx, [r14+840h]
0x18002cc9e  mov     rcx, [rcx+2A0h]; hToken
0x18002cca5  call    cs:__imp_ImpersonateLoggedOnUser
0x18002ccab  test    eax, eax
0x18002ccad  jnz     short loc_18002CCDA
0x18002ccaf  mov     rsi, [r14+838h]
0x18002ccb6  mov     rax, [rsi]
0x18002ccb9  mov     rdi, [rax+40h]
0x18002ccbd  call    cs:__imp_GetLastError
0x18002ccc3  mov     ebx, eax
0x18002ccc5  call    cs:__imp_GetLastError
0x18002cccb  lea     r9, aImpersonatelog; "ImpersonateLoggedOnUser"
0x18002ccd2  jmp     loc_18002CC50
0x18002ccd7  xor     dil, dil
0x18002ccda  mov     rax, cs:WPP_GLOBAL_Control
0x18002cce1  cmp     dword ptr [r14+10Ch], 0
0x18002cce9  jz      short loc_18002CD34
0x18002cceb  mov     rcx, [r14+100h]
0x18002ccf2  mov     ebx, 0EB8h
0x18002ccf7  add     rcx, rbx
0x18002ccfa  call    ?GetValue@?$PacketElement@K@PacketParser@@QEBAKXZ; PacketParser::PacketElement<ulong>::GetValue(void)
0x18002ccff  test    eax, eax
0x18002cd01  jz      short loc_18002CD2D
0x18002cd03  mov     rcx, [r14+100h]
0x18002cd0a  add     rcx, rbx
0x18002cd0d  call    ?GetValue@?$PacketElement@K@PacketParser@@QEBAKXZ; PacketParser::PacketElement<ulong>::GetValue(void)
0x18002cd12  mov     rdx, [r14+838h]; struct IRequestContext *
0x18002cd19  lea     rcx, [r14+20h]; Parameter
0x18002cd1d  mov     r8d, eax; unsigned int
0x18002cd20  call    ?StartTimer@Timer@@QEAA_NAEAVIRequestContext@@I@Z; Timer::StartTimer(IRequestContext &,uint)
0x18002cd25  test    al, al
0x18002cd27  jz      loc_18002CEF2
0x18002cd2d  mov     rax, cs:WPP_GLOBAL_Control
0x18002cd34  lea     rsi, aTrue; "true"
0x18002cd3b  lea     rbx, aComplete; "@Complete"
0x18002cd42  cmp     rax, r12
0x18002cd45  jz      short loc_18002CDA4
0x18002cd47  test    dword ptr [rax+1Ch], 1000h
0x18002cd4e  jz      short loc_18002CDA4
0x18002cd50  mov     ebx, [r14+8]
0x18002cd54  mov     rcx, r14; this
0x18002cd57  btr     ebx, 1Fh
0x18002cd5b  call    ?IsInitialized@IOperation@@QEBA_NXZ; IOperation::IsInitialized(void)
0x18002cd60  test    al, al
0x18002cd62  mov     dword ptr [rsp+78h+var_48], ebx; char
0x18002cd66  lea     rax, aFalse; "false"
0x18002cd6d  mov     rcx, rsi
0x18002cd70  cmovz   rcx, rax
0x18002cd74  lea     rbx, aComplete; "@Complete"
0x18002cd7b  mov     [rsp+78h+var_50], rcx; __int64
0x18002cd80  lea     r8, WPP_e4968f4695e73c65848dbd42e49ea3da_Traceguids
0x18002cd87  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd8e  mov     edx, 0Eh
0x18002cd93  mov     r9, r14
0x18002cd96  mov     [rsp+78h+var_58], rbx; __int64
0x18002cd9b  mov     rcx, [rcx+10h]; LoggerHandle
0x18002cd9f  call    WPP_SF_qsSd
0x18002cda4  mov     eax, [r14+8]
0x18002cda8  test    eax, eax
0x18002cdaa  jns     loc_18002CEDA
0x18002cdb0  lea     ecx, [rax+1]
0x18002cdb3  lock cmpxchg [r14+8], ecx
0x18002cdb9  jnz     short loc_18002CDA4
0x18002cdbb  mov     rax, [r14]
0x18002cdbe  mov     rcx, r14
0x18002cdc1  mov     rax, [rax+0C8h]
0x18002cdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdcd  test    al, al
0x18002cdcf  jnz     short loc_18002CDE1
0x18002cdd1  mov     rdx, rbx; char *
0x18002cdd4  mov     rcx, r14; this
0x18002cdd7  call    ?Release@IOperation@@QEAAJPEBD@Z; IOperation::Release(char const *)
0x18002cddc  jmp     loc_18002CEF2
0x18002cde1  mov     rcx, r15; this
0x18002cde4  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x18002cde9  mov     dword ptr [r14+460h], 0
0x18002cdf4  mov     ecx, [r15]; dwErrCode
0x18002cdf7  test    ecx, ecx
0x18002cdf9  jnz     short loc_18002CE07
0x18002cdfb  lea     rcx, [r15+8]; lpCriticalSection
0x18002cdff  call    cs:__imp_LeaveCriticalSection
0x18002ce05  jmp     short loc_18002CE0D
0x18002ce07  call    cs:__imp_SetLastError
0x18002ce0d  mov     rcx, [r14+4B0h]
0x18002ce14  test    rcx, rcx
0x18002ce17  jnz     loc_18002CF42
0x18002ce1d  mov     rax, cs:WPP_GLOBAL_Control
0x18002ce24  cmp     rax, r12
0x18002ce27  jz      short loc_18002CE83
0x18002ce29  test    dword ptr [rax+1Ch], 1000h
0x18002ce30  jz      short loc_18002CE83
0x18002ce32  mov     ebx, [r14+8]
0x18002ce36  mov     rcx, r14; this
0x18002ce39  btr     ebx, 1Fh
0x18002ce3d  call    ?IsInitialized@IOperation@@QEBA_NXZ; IOperation::IsInitialized(void)
0x18002ce42  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce49  lea     r8, WPP_e4968f4695e73c65848dbd42e49ea3da_Traceguids
0x18002ce50  test    al, al
0x18002ce52  mov     dword ptr [rsp+78h+var_48], ebx; char
0x18002ce56  lea     rax, aFalse; "false"
0x18002ce5d  mov     edx, 0Fh
0x18002ce62  cmovz   rsi, rax
0x18002ce66  mov     r9, r14
0x18002ce69  mov     rcx, [rcx+10h]; LoggerHandle
0x18002ce6d  lea     rax, aConfigure; "@Configure"
0x18002ce74  mov     [rsp+78h+var_50], rsi; __int64
0x18002ce79  mov     [rsp+78h+var_58], rax; __int64
0x18002ce7e  call    WPP_SF_qsSd
0x18002ce83  or      eax, 0FFFFFFFFh
0x18002ce86  lock xadd [r14+8], eax
0x18002ce8c  dec     eax
0x18002ce8e  cmp     eax, 80000000h
0x18002ce93  jnz     short loc_18002CEC1
0x18002ce95  mov     r9d, 54Fh; unsigned int
0x18002ce9b  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x18002cea4  lea     r8, a174; "174"
0x18002ceab  mov     edx, 0AEh; unsigned int
0x18002ceb0  lea     rcx, aOnecoreAdminWm_137; "onecore\\admin\\wmi\\wmx\\stdlib\\opera"...
0x18002ceb7  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002cebc  jmp     loc_18002CF59
0x18002cec1  test    eax, eax
0x18002cec3  jnz     loc_18002CF59
0x18002cec9  mov     rax, [r14]
0x18002cecc  mov     rcx, r14
0x18002cecf  mov     rax, [rax+18h]
0x18002ced3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ced8  jmp     short loc_18002CF59
0x18002ceda  mov     rcx, [r14+838h]
0x18002cee1  mov     edx, 45Bh
0x18002cee6  mov     rax, [rcx]
0x18002cee9  mov     rax, [rax+48h]
0x18002ceed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cef2  mov     rcx, r15; this
0x18002cef5  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x18002cefa  mov     rcx, r15; this
0x18002cefd  mov     dword ptr [r14+460h], 0
0x18002cf08  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x18002cf0d  mov     rax, [r14]
0x18002cf10  xor     r9d, r9d
0x18002cf13  xor     r8d, r8d
0x18002cf16  mov     rcx, r14
0x18002cf19  mov     rax, [rax+50h]
0x18002cf1d  lea     edx, [r9+1]
0x18002cf21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf26  mov     rcx, r14; this
0x18002cf29  call    ?AcknowledgeIfNecessary@CListenerOperation@@IEAAXXZ; CListenerOperation::AcknowledgeIfNecessary(void)
0x18002cf2e  mov     rcx, r14; this
0x18002cf31  call    ?Shutdown@IOperation@@QEAA_NXZ; IOperation::Shutdown(void)
0x18002cf36  mov     rcx, [r14+4B0h]; pwk
0x18002cf3d  test    rcx, rcx
0x18002cf40  jz      short loc_18002CF4A
0x18002cf42  call    cs:__imp_SubmitThreadpoolWork
0x18002cf48  jmp     short loc_18002CF59
0x18002cf4a  lea     rdx, aConfigure; "@Configure"
0x18002cf51  mov     rcx, r14; this
0x18002cf54  call    ?Release@IOperation@@QEAAJPEBD@Z; IOperation::Release(char const *)
0x18002cf59  test    dil, dil
0x18002cf5c  jz      short loc_18002CF63
0x18002cf5e  call    ?RevertToSelf@CSecurity@@SAHXZ; CSecurity::RevertToSelf(void)
0x18002cf63  add     rsp, 48h
0x18002cf67  pop     r15
0x18002cf69  pop     r14
0x18002cf6b  pop     r12
0x18002cf6d  pop     rdi
0x18002cf6e  pop     rsi
0x18002cf6f  pop     rbx
0x18002cf70  retn
```
