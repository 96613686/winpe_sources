# CSrvDllModuleT<CEmptyType>::DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x180012af4`
- end: `0x180012e9d`
- name: `?DllMain@?$CSrvDllModuleT@VCEmptyType@@@@SAJPEAUHINSTANCE__@@KPEAX@Z`
- size: `937`
- prototype: `__int64 __fastcall(HMODULE hLibModule, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180017c78`

## callees

- `0x180001008`
- `0x1800010a8`
- `0x180001ac0`
- `0x180001e90`
- `0x180001ed8`
- `0x1800090dc`
- `0x180009480`
- `0x18000ee34`
- `0x18000ef08`
- `0x180012af4`
- `0x180012ea4`
- `0x180014800`
- `0x180014e14`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012bbb`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012bbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012bf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012bf5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012cfe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012cfe`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180012e51`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180012e6c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180012e51`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180012e6c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180012c76`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180012c85`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180012c76`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180012c85`

## pseudocode

```c
__int64 __fastcall CSrvDllModuleT<CEmptyType>::DllMain(HMODULE hLibModule, int a2)
{
  int v4; // ebx
  _QWORD *v5; // rdi
  int v6; // eax
  _QWORD *v7; // rdi
  void *v8; // rcx
  __int64 i; // rdi
  __int64 (*v10)(void); // rax
  int v11; // eax
  int *v12; // r9
  REGHANDLE v13; // rcx
  REGHANDLE v14; // rcx
  _QWORD *v16; // [rsp+30h] [rbp-58h] BYREF
  _QWORD *v17; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-48h] BYREF

  v16 = 0;
  v4 = 0;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v5 = operator new((unsigned int)(a2 + 71));
      *v5 = 1;
      v5[5] = 0;
      v5[6] = 0;
      v5[7] = 0;
      v5[1] = 0;
      v5[2] = 0;
      v5[3] = 0;
      v5[4] = 0;
      v5[8] = 0;
      v17 = v5;
      v6 = CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::Init(v5);
      v4 = v6;
      if ( v6 >= 0 )
      {
        v17 = 0;
        v16 = v5;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
        v5 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
      SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(&v17);
      if ( v4 >= 0 )
      {
        DisableThreadLibraryCalls(hLibModule);
        v16 = 0;
        CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState = v5;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
      }
    }
  }
  else
  {
    v7 = CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState;
    if ( CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
      && _InterlockedExchangeAdd(
           (volatile signed __int32 *)CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState,
           0xFFFFFFFF) == 1
      && v7 )
    {
      v8 = (void *)v7[8];
      if ( v8 )
      {
        CloseHandle(v8);
        v7[8] = 0;
      }
      CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>((__int64)(v7 + 3));
      CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>((__int64)(v7 + 1));
      operator delete(v7);
    }
    CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(&v16);
  if ( v4 < 0 )
    goto LABEL_17;
  if ( a2 )
  {
    if ( a2 != 1 )
      goto LABEL_52;
    g_hInstance = hLibModule;
    COverriddenOperatorsSafeGuardT<CEmptyType>::OperatorsSafeGuardFunc();
    for ( i = CGlobalList<CGlobalInitializer<1>>::g_pFirst; ; i = *(_QWORD *)i )
    {
      if ( !i )
      {
        v4 = 0;
        goto LABEL_28;
      }
      if ( !*(_DWORD *)(i + 24) )
      {
        if ( DecodePointer(*(PVOID *)(i + 8)) )
        {
          v10 = (__int64 (*)(void))DecodePointer(*(PVOID *)(i + 8));
          v11 = v10();
          v4 = v11;
          if ( v11 < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
            CGlobalInitializer<1>::Done();
LABEL_28:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
            if ( v4 >= 0 )
            {
              TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18002F1D0);
              if ( (unsigned int)dword_18002F1D0 > 5
                && (qword_18002F1E0 & 0x400000000000LL) != 0
                && (qword_18002F1E8 & 0x400000000000LL) == qword_18002F1E8 )
              {
                EventActivityIdControl(3u, &stru_18002FC00);
              }
              else
              {
                stru_18002FC00 = 0;
              }
              g_activity = 1;
              if ( (unsigned int)dword_18002F1D0 > 5
                && (qword_18002F1E0 & 0x400000000000LL) != 0
                && (qword_18002F1E8 & 0x400000000000LL) == qword_18002F1E8 )
              {
                if ( byte_18002FBFC && (dword_18002FC10 || dword_18002FC14 || dword_18002FC18 || dword_18002FC1C) )
                  v12 = &dword_18002FC10;
                else
                  v12 = 0;
                tlgWriteTransfer_EventWriteTransfer(&dword_18002F1D0, word_18002B0EA, &stru_18002FC00, v12, 2, v18);
              }
              TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18002F208);
              goto LABEL_52;
            }
LABEL_17:
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
            goto LABEL_52;
          }
        }
        *(_DWORD *)(i + 24) = 1;
      }
    }
  }
  CGlobalInitializer<1>::Done();
  g_activity = 2;
  if ( (unsigned int)dword_18002F1D0 > 5
    && (qword_18002F1E0 & 0x400000000000LL) != 0
    && (qword_18002F1E8 & 0x400000000000LL) == qword_18002F1E8 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_18002F1D0, &byte_18002B0C7, &stru_18002FC00, 0, 2, v18);
  }
  v13 = RegHandle;
  dword_18002F1D0 = 0;
  RegHandle = 0;
  EventUnregister(v13);
  v14 = qword_18002F228;
  dword_18002F208 = 0;
  qword_18002F228 = 0;
  EventUnregister(v14);
LABEL_52:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012af4  mov     [rsp+arg_8], rbx
0x180012af9  mov     [rsp+arg_10], rbp
0x180012afe  push    rsi
0x180012aff  push    rdi
0x180012b00  push    r14
0x180012b02  sub     rsp, 70h
0x180012b06  mov     rax, cs:__security_cookie
0x180012b0d  xor     rax, rsp
0x180012b10  mov     [rsp+88h+var_28], rax
0x180012b15  xor     r14d, r14d
0x180012b18  mov     esi, edx
0x180012b1a  mov     [rsp+88h+var_58], r14
0x180012b1f  mov     rbp, rcx
0x180012b22  mov     ebx, r14d
0x180012b25  mov     eax, edx
0x180012b27  test    edx, edx
0x180012b29  jz      loc_180012BCF
0x180012b2f  cmp     eax, 1
0x180012b32  jnz     loc_180012C25
0x180012b38  xor     ecx, ecx
0x180012b3a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012b3f  lea     ecx, [rsi+47h]; Size
0x180012b42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012b47  mov     rcx, rax
0x180012b4a  mov     rdi, rax
0x180012b4d  mov     qword ptr [rax], 1
0x180012b54  mov     [rax+28h], r14
0x180012b58  mov     [rax+30h], r14
0x180012b5c  mov     [rax+38h], r14
0x180012b60  mov     [rax+8], r14
0x180012b64  mov     [rax+10h], r14
0x180012b68  mov     [rax+18h], r14
0x180012b6c  mov     [rax+20h], r14
0x180012b70  mov     [rax+40h], r14
0x180012b74  mov     [rsp+88h+var_50], rax
0x180012b79  call    ?Init@?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@AEAAJXZ; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::Init(void)
0x180012b7e  mov     ebx, eax
0x180012b80  test    eax, eax
0x180012b82  jns     short loc_180012B90
0x180012b84  mov     ecx, eax
0x180012b86  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012b8b  mov     edi, r14d
0x180012b8e  jmp     short loc_180012B9A
0x180012b90  mov     [rsp+88h+var_50], r14
0x180012b95  mov     [rsp+88h+var_58], rdi
0x180012b9a  mov     ecx, ebx
0x180012b9c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012ba1  lea     rcx, [rsp+88h+var_50]
0x180012ba6  call    ??1?$SP@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@V?$SP_COM@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@@@QEAA@XZ; SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(void)
0x180012bab  test    ebx, ebx
0x180012bad  jns     short loc_180012BB8
0x180012baf  mov     ecx, ebx
0x180012bb1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012bb6  jmp     short loc_180012C25
0x180012bb8  mov     rcx, rbp; hLibModule
0x180012bbb  call    cs:__imp_DisableThreadLibraryCalls
0x180012bc1  mov     [rsp+88h+var_58], r14
0x180012bc6  mov     cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA, rdi; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x180012bcd  jmp     short loc_180012C25
0x180012bcf  mov     rdi, cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x180012bd6  test    rdi, rdi
0x180012bd9  jz      short loc_180012C1E
0x180012bdb  or      eax, 0FFFFFFFFh
0x180012bde  lock xadd [rdi], eax
0x180012be2  cmp     eax, 1
0x180012be5  jnz     short loc_180012C1E
0x180012be7  test    rdi, rdi
0x180012bea  jz      short loc_180012C1E
0x180012bec  mov     rcx, [rdi+40h]; hObject
0x180012bf0  test    rcx, rcx
0x180012bf3  jz      short loc_180012BFF
0x180012bf5  call    cs:__imp_CloseHandle
0x180012bfb  mov     [rdi+40h], r14
0x180012bff  lea     rcx, [rdi+18h]
0x180012c03  call    ??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)
0x180012c08  lea     rcx, [rdi+8]
0x180012c0c  call    ??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)
0x180012c11  mov     edx, 48h ; 'H'; unsigned __int64
0x180012c16  mov     rcx, rdi; void *
0x180012c19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012c1e  mov     cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA, r14; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x180012c25  mov     ecx, ebx
0x180012c27  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012c2c  lea     rcx, [rsp+88h+var_58]
0x180012c31  call    ??1?$SP@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@V?$SP_COM@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@@@QEAA@XZ; SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(void)
0x180012c36  test    ebx, ebx
0x180012c38  jns     short loc_180012C46
0x180012c3a  mov     ecx, ebx
0x180012c3c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012c41  jmp     loc_180012E72
0x180012c46  test    esi, esi
0x180012c48  jz      loc_180012DCB
0x180012c4e  cmp     esi, 1
0x180012c51  jnz     loc_180012E72
0x180012c57  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * g_hInstance
0x180012c5e  call    ?OperatorsSafeGuardFunc@?$COverriddenOperatorsSafeGuardT@VCEmptyType@@@@SAJXZ; COverriddenOperatorsSafeGuardT<CEmptyType>::OperatorsSafeGuardFunc(void)
0x180012c63  mov     rdi, cs:?g_pFirst@?$CGlobalList@V?$CGlobalInitializer@$00@@@@2PEAV?$CGlobalInitializer@$00@@EA; CGlobalInitializer<1> * CGlobalList<CGlobalInitializer<1>>::g_pFirst
0x180012c6a  jmp     short loc_180012CA0
0x180012c6c  cmp     [rdi+18h], r14d
0x180012c70  jnz     short loc_180012C9D
0x180012c72  mov     rcx, [rdi+8]; Ptr
0x180012c76  call    cs:__imp_DecodePointer
0x180012c7c  test    rax, rax
0x180012c7f  jz      short loc_180012C96
0x180012c81  mov     rcx, [rdi+8]; Ptr
0x180012c85  call    cs:__imp_DecodePointer
0x180012c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c90  mov     ebx, eax
0x180012c92  test    eax, eax
0x180012c94  js      short loc_180012D06
0x180012c96  mov     dword ptr [rdi+18h], 1
0x180012c9d  mov     rdi, [rdi]
0x180012ca0  test    rdi, rdi
0x180012ca3  jnz     short loc_180012C6C
0x180012ca5  mov     ebx, r14d
0x180012ca8  mov     ecx, ebx
0x180012caa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012caf  test    ebx, ebx
0x180012cb1  js      short loc_180012C3A
0x180012cb3  lea     rcx, dword_18002F1D0; CallbackContext
0x180012cba  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180012cbf  mov     eax, cs:dword_18002F1D0
0x180012cc5  mov     rdi, 400000000000h
0x180012ccf  cmp     eax, 5
0x180012cd2  jbe     short loc_180012D14
0x180012cd4  mov     rcx, cs:qword_18002F1E8
0x180012cdb  mov     rax, cs:qword_18002F1E0
0x180012ce2  test    rdi, rax
0x180012ce5  jz      short loc_180012D14
0x180012ce7  mov     rax, rcx
0x180012cea  and     rax, rdi
0x180012ced  cmp     rax, rcx
0x180012cf0  jnz     short loc_180012D14
0x180012cf2  lea     rdx, stru_18002FC00; ActivityId
0x180012cf9  mov     ecx, 3; ControlCode
0x180012cfe  call    cs:__imp_EventActivityIdControl
0x180012d04  jmp     short loc_180012D1E
0x180012d06  mov     ecx, eax
0x180012d08  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012d0d  call    ?Done@?$CGlobalInitializer@$00@@SAJXZ; CGlobalInitializer<1>::Done(void)
0x180012d12  jmp     short loc_180012CA8
0x180012d14  xorps   xmm0, xmm0
0x180012d17  movups  xmmword ptr cs:stru_18002FC00.Data1, xmm0
0x180012d1e  mov     eax, cs:dword_18002F1D0
0x180012d24  mov     cs:?g_activity@@3V?$TraceLoggingActivity@$1?g_ChangePKTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 1; TraceLoggingActivity<&_tlgProvider_t const * const g_ChangePKTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> g_activity
0x180012d2e  cmp     eax, 5
0x180012d31  jbe     loc_180012DBA
0x180012d37  mov     rcx, cs:qword_18002F1E8
0x180012d3e  mov     rax, cs:qword_18002F1E0
0x180012d45  test    rdi, rax
0x180012d48  jz      short loc_180012DBA
0x180012d4a  mov     rax, rcx
0x180012d4d  and     rax, rdi
0x180012d50  cmp     rax, rcx
0x180012d53  jnz     short loc_180012DBA
0x180012d55  cmp     cs:byte_18002FBFC, r14b
0x180012d5c  jz      short loc_180012D8B
0x180012d5e  cmp     cs:dword_18002FC10, r14d
0x180012d65  jnz     short loc_180012D82
0x180012d67  cmp     cs:dword_18002FC14, r14d
0x180012d6e  jnz     short loc_180012D82
0x180012d70  cmp     cs:dword_18002FC18, r14d
0x180012d77  jnz     short loc_180012D82
0x180012d79  cmp     cs:dword_18002FC1C, r14d
0x180012d80  jz      short loc_180012D8B
0x180012d82  lea     r9, dword_18002FC10
0x180012d89  jmp     short loc_180012D8E
0x180012d8b  mov     r9, r14
0x180012d8e  lea     rax, [rsp+88h+var_48]
0x180012d93  mov     [rsp+88h+var_60], rax
0x180012d98  lea     r8, stru_18002FC00
0x180012d9f  lea     rdx, word_18002B0EA
0x180012da6  mov     [rsp+88h+var_68], 2
0x180012dae  lea     rcx, dword_18002F1D0
0x180012db5  call    _tlgWriteTransfer_EventWriteTransfer
0x180012dba  lea     rcx, dword_18002F208; CallbackContext
0x180012dc1  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180012dc6  jmp     loc_180012E72
0x180012dcb  call    ?Done@?$CGlobalInitializer@$00@@SAJXZ; CGlobalInitializer<1>::Done(void)
0x180012dd0  mov     eax, cs:dword_18002F1D0
0x180012dd6  mov     cs:?g_activity@@3V?$TraceLoggingActivity@$1?g_ChangePKTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 2; TraceLoggingActivity<&_tlgProvider_t const * const g_ChangePKTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> g_activity
0x180012de0  cmp     eax, 5
0x180012de3  jbe     short loc_180012E3C
0x180012de5  mov     rcx, cs:qword_18002F1E8
0x180012dec  mov     rdi, 400000000000h
0x180012df6  mov     rax, cs:qword_18002F1E0
0x180012dfd  test    rdi, rax
0x180012e00  jz      short loc_180012E3C
0x180012e02  mov     rax, rcx
0x180012e05  and     rax, rdi
0x180012e08  cmp     rax, rcx
0x180012e0b  jnz     short loc_180012E3C
0x180012e0d  lea     rax, [rsp+88h+var_48]
0x180012e12  xor     r9d, r9d
0x180012e15  mov     [rsp+88h+var_60], rax
0x180012e1a  lea     r8, stru_18002FC00
0x180012e21  lea     rdx, byte_18002B0C7
0x180012e28  mov     [rsp+88h+var_68], 2
0x180012e30  lea     rcx, dword_18002F1D0
0x180012e37  call    _tlgWriteTransfer_EventWriteTransfer
0x180012e3c  mov     rcx, cs:RegHandle; RegHandle
0x180012e43  mov     cs:dword_18002F1D0, r14d
0x180012e4a  mov     cs:RegHandle, r14
0x180012e51  call    cs:__imp_EventUnregister
0x180012e57  mov     rcx, cs:qword_18002F228; RegHandle
0x180012e5e  mov     cs:dword_18002F208, r14d
0x180012e65  mov     cs:qword_18002F228, r14
0x180012e6c  call    cs:__imp_EventUnregister
0x180012e72  mov     ecx, ebx
0x180012e74  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012e79  mov     eax, ebx
0x180012e7b  mov     rcx, [rsp+88h+var_28]
0x180012e80  xor     rcx, rsp; StackCookie
0x180012e83  call    __security_check_cookie
0x180012e88  lea     r11, [rsp+88h+var_18]
0x180012e8d  mov     rbx, [r11+28h]
0x180012e91  mov     rbp, [r11+30h]
0x180012e95  mov     rsp, r11
0x180012e98  pop     r14
0x180012e9a  pop     rdi
0x180012e9b  pop     rsi
0x180012e9c  retn
```
