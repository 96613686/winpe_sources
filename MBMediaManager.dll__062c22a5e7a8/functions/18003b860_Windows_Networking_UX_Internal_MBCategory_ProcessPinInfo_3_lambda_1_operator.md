# _Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo_::_3_::_lambda_1_::operator()

- ea: `0x18003b860`
- end: `0x18003bc80`
- name: `_Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo_::_3_::_lambda_1_::operator()`
- size: `1056`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009d30`
- `0x180043ff0`

## callees

- `0x180009f60`
- `0x18000ad20`
- `0x18000cc50`
- `0x18000ccb0`
- `0x18000efa4`
- `0x180015430`
- `0x180017e08`
- `0x18001a6e8`
- `0x18001bd80`
- `0x18001bdb8`
- `0x18001c268`
- `0x1800242fc`
- `0x180024378`
- `0x18002d20c`
- `0x18003b860`
- `0x180044550`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bacb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bacb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bc74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bc74`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003b8cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003b8cc`

## string_xrefs

- `0x18003b985`: `Update _pin1PreviousState. old _pin1PreviousState=%d, new _pin1PreviousState=%d`
- `0x18003ba3a`: `PIN1 has never been sent to UX. Query for updated Pin State and send default PIN1 info to UX`
- `0x18003ba6d`: `PIN1 already sent to UX`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo_::_3_::_lambda_1_::operator()(
        __int64 a1)
{
  int WwanInterfaceObject; // edi
  Windows::Networking::UX::Internal::MBCategory *v3; // rcx
  unsigned int v4; // edx
  unsigned int v5; // eax
  int v6; // eax
  int v7; // edi
  Windows::Networking::UX::Internal::MBCategory *v8; // rcx
  Windows::Networking::UX::Internal::MBCategory *v9; // rcx
  char v10; // r8
  const struct Windows::Networking::UX::MbPinInfo *v11; // rdx
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  Windows::Networking::UX::Internal::MBCategory *v13; // rcx
  char *v14; // rdi
  int v15; // eax
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  char *v19; // rax
  __int64 (__fastcall ***v20)(_QWORD, __int64); // rdx
  __int64 *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  int v24; // [rsp+20h] [rbp-50h]
  int v25; // [rsp+20h] [rbp-50h]
  Windows::Networking::UX::Internal::MBCategory **v26; // [rsp+30h] [rbp-40h] BYREF
  struct WWAN_INTERFACE_OBJECT *v27; // [rsp+38h] [rbp-38h] BYREF
  __int64 v28; // [rsp+40h] [rbp-30h]
  int v29; // [rsp+48h] [rbp-28h]
  _OWORD v30[2]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  Windows::Networking::UX::Internal::MBCategory *v32; // [rsp+B0h] [rbp+40h] BYREF
  char *v33; // [rsp+B8h] [rbp+48h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, __int64); // [rsp+C0h] [rbp+50h] BYREF
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+C8h] [rbp+58h]

  v32 = 0;
  v26 = &v32;
  v27 = 0;
  LOBYTE(v28) = 1;
  WwanInterfaceObject = Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(
                          *(Windows::Networking::UX::Internal::MBCategory **)a1,
                          &v27);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>((__int64 **)&v26);
  if ( WwanInterfaceObject < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x15A0,
      (int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)WwanInterfaceObject);
    v3 = v32;
    goto LABEL_3;
  }
  v3 = v32;
  if ( v32 )
  {
    v4 = *((_DWORD *)v32 + 304);
    if ( v4 )
    {
      v5 = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(v32, v4);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x15A6,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
        (const char *)v5,
        v24);
LABEL_9:
      v3 = v32;
      goto LABEL_3;
    }
    memset(v30, 0, 28);
    v6 = Windows::Networking::UX::Internal::MBCategory::_FillPinState(
           v32,
           (Windows::Networking::UX::Internal::MBCategory *)((char *)v32 + 1056),
           (const struct _WWAN_PIN_INFO *)(a1 + 8),
           (const unsigned int *)(a1 + 20),
           (const bool *)(a1 + 25),
           (struct Windows::Networking::UX::MbPinInfo *)v30);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15AC,
        (int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
        (const char *)(unsigned int)v6);
      goto LABEL_9;
    }
    if ( *(_DWORD *)(a1 + 8) == 2 )
    {
      MBSettingUXLogging::Verbose(
        "Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo::<lambda_1>::operator ()",
        5559,
        "Update _pin1PreviousState. old _pin1PreviousState=%d, new _pin1PreviousState=%d",
        *(_DWORD *)(*(_QWORD *)a1 + 596LL),
        *(_DWORD *)(a1 + 12));
      *(_DWORD *)(*(_QWORD *)a1 + 596LL) = *(_DWORD *)(a1 + 12);
    }
    v7 = v30[0];
    if ( LODWORD(v30[0]) == 1 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo::<lambda_1>::operator ()",
        5625,
        "pinType is Pin1");
      v10 = *(_BYTE *)(a1 + 26);
      v11 = (const struct Windows::Networking::UX::MbPinInfo *)v30;
      v9 = *(Windows::Networking::UX::Internal::MBCategory **)a1;
    }
    else
    {
      if ( LODWORD(v30[0]) )
      {
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo::<lambda_1>::operator ()",
          5576,
          "pinType is not Pin1. pinType=%d",
          LODWORD(v30[0]));
        if ( v7 >= 3 )
        {
          *(_WORD *)(*(_QWORD *)a1 + 298LL) = 257;
          if ( (unsigned __int8)Windows::Networking::UX::Internal::MBCategory::_CalculateConnectivity(*(Windows::Networking::UX::Internal::MBCategory **)a1) )
            Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange(*(Windows::Networking::UX::Internal::MBCategory **)a1);
        }
      }
      else
      {
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo::<lambda_1>::operator ()",
          5572,
          "pinType is None - PIN is not set");
      }
      LODWORD(v27) = 0;
      v28 = 0;
      v29 = 0;
      LODWORD(v26) = 1;
      Windows::Networking::UX::Internal::MBCategory::_FillPinStateBasic(
        v8,
        (Windows::Networking::UX::Internal::MBCategory *)((char *)v32 + 1056),
        (struct Windows::Networking::UX::MbPinInfo *)&v26);
      if ( *(_DWORD *)(*(_QWORD *)a1 + 476LL) )
      {
        MBSettingUXLogging::Verbose(
          "Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo::<lambda_1>::operator ()",
          5615,
          "PIN1 already sent to UX");
        v9 = *(Windows::Networking::UX::Internal::MBCategory **)a1;
        HIDWORD(v27) = *(_DWORD *)(*(_QWORD *)a1 + 488LL);
        HIDWORD(v26) = *((_DWORD *)v9 + 120);
        v10 = *(_BYTE *)(a1 + 26);
      }
      else
      {
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::_ProcessPinInfo::<lambda_1>::operator ()",
          5601,
          "PIN1 has never been sent to UX. Query for updated Pin State and send default PIN1 info to UX");
        Windows::Networking::UX::Internal::MBCategory::tp_GetPinState(*(Windows::Networking::UX::Internal::MBCategory **)a1);
        HIDWORD(v27) = 0;
        HIDWORD(v26) = 0;
        *(_DWORD *)(*(_QWORD *)a1 + 596LL) = 0;
        v9 = *(Windows::Networking::UX::Internal::MBCategory **)a1;
        v10 = 1;
      }
      v11 = (const struct Windows::Networking::UX::MbPinInfo *)&v26;
    }
    Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo(v9, v11, v10);
    v12 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)a1 + 312LL);
    EnterCriticalSection(v12);
    v35 = v12;
    if ( *(_QWORD *)(*(_QWORD *)a1 + 352LL) )
    {
      if ( *(_BYTE *)(a1 + 24) )
      {
        v14 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v33 = v14;
        if ( v14 )
        {
          v15 = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(v13, *(_DWORD *)(a1 + 20));
          *((_DWORD *)v14 + 2) = 1;
          *(_QWORD *)v14 = &Windows::Networking::UX::Internal::MBPinEnterCompleteEvent::`vftable';
          *((_OWORD *)v14 + 1) = v30[0];
          *(_OWORD *)(v14 + 28) = *(_OWORD *)((char *)v30 + 12);
          *((_DWORD *)v14 + 11) = v15;
        }
        else
        {
          v14 = 0;
        }
        v34 = (__int64 (__fastcall ***)(_QWORD, __int64))v14;
        if ( v14 )
        {
          v16 = *(__int64 **)(*(_QWORD *)a1 + 352LL);
          v17 = *v16;
          v34 = 0;
          v33 = v14;
          v18 = (*(__int64 (__fastcall **)(__int64 *, char **))(v17 + 72))(v16, &v33);
          if ( v18 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1608,
              (int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
              (const char *)(unsigned int)v18);
        }
        else
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x160C,
            (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
            (const char *)0x8007000ELL,
            v25);
        }
      }
      else
      {
        if ( !*(_BYTE *)(a1 + 25) )
          goto LABEL_44;
        v19 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v20 = (__int64 (__fastcall ***)(_QWORD, __int64))v19;
        v33 = v19;
        if ( v19 )
        {
          *((_DWORD *)v19 + 2) = 0;
          *(_QWORD *)v19 = &Windows::Networking::UX::Internal::MBPinEnterCompleteEvent::`vftable';
          *((_OWORD *)v19 + 1) = v30[0];
          *(_OWORD *)(v19 + 28) = *(_OWORD *)((char *)v30 + 12);
        }
        else
        {
          v20 = 0;
        }
        v34 = v20;
        if ( v20 )
        {
          v21 = *(__int64 **)(*(_QWORD *)a1 + 352LL);
          v22 = *v21;
          v34 = 0;
          v33 = (char *)v20;
          v23 = (*(__int64 (__fastcall **)(__int64 *, char **))(v22 + 72))(v21, &v33);
          if ( v23 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1615,
              (int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
              (const char *)(unsigned int)v23);
        }
        else
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x1619,
            (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
            (const char *)0x8007000ELL,
            v25);
        }
      }
      std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(&v34);
    }
LABEL_44:
    if ( v12 )
      LeaveCriticalSection(v12);
    goto LABEL_9;
  }
LABEL_3:
  v32 = 0;
  if ( v3 )
    WwanFreeMemory(v3);
}

```

## disassembly

```asm
0x18003b860  push    rbp
0x18003b862  push    rbx
0x18003b863  push    rsi
0x18003b864  push    rdi
0x18003b865  push    r12
0x18003b867  push    r14
0x18003b869  push    r15
0x18003b86b  mov     rbp, rsp
0x18003b86e  sub     rsp, 70h
0x18003b872  mov     rbx, rcx
0x18003b875  xor     r12d, r12d
0x18003b878  mov     [rbp+arg_0], r12
0x18003b87c  lea     rax, [rbp+arg_0]
0x18003b880  mov     [rbp+var_40], rax
0x18003b884  mov     [rbp+var_38], r12
0x18003b888  mov     byte ptr [rbp+var_30], 1
0x18003b88c  lea     rdx, [rbp+var_38]; struct WWAN_INTERFACE_OBJECT **
0x18003b890  mov     rcx, [rcx]; this
0x18003b893  call    ?_GetWwanInterfaceObject@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEAPEAUWWAN_INTERFACE_OBJECT@@@Z; Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(WWAN_INTERFACE_OBJECT * *)
0x18003b898  mov     edi, eax
0x18003b89a  lea     rcx, [rbp+var_40]
0x18003b89e  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18003b8a3  mov     rcx, [rbp+38h]; this
0x18003b8a7  test    edi, edi
0x18003b8a9  jns     short loc_18003B8E1
0x18003b8ab  mov     r9d, edi; char *
0x18003b8ae  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18003b8b5  mov     edx, 15A0h; void *
0x18003b8ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b8bf  mov     rcx, [rbp+arg_0]
0x18003b8c3  test    rcx, rcx
0x18003b8c6  mov     [rbp+arg_0], r12
0x18003b8ca  jz      short loc_18003B8D2
0x18003b8cc  call    cs:__imp_WwanFreeMemory
0x18003b8d2  add     rsp, 70h
0x18003b8d6  pop     r15
0x18003b8d8  pop     r14
0x18003b8da  pop     r12
0x18003b8dc  pop     rdi
0x18003b8dd  pop     rsi
0x18003b8de  pop     rbx
0x18003b8df  pop     rbp
0x18003b8e0  retn
0x18003b8e1  mov     rcx, [rbp+arg_0]; this
0x18003b8e5  test    rcx, rcx
0x18003b8e8  jz      short loc_18003B8C3
0x18003b8ea  mov     edx, [rcx+4C0h]; unsigned int
0x18003b8f0  test    edx, edx
0x18003b8f2  jz      short loc_18003B918
0x18003b8f4  call    ?_HResultFromWwanStatus@MBCategory@Internal@UX@Networking@Windows@@AEAAJK@Z; Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(ulong)
0x18003b8f9  mov     rcx, [rbp+38h]; this
0x18003b8fd  mov     r9d, eax; char *
0x18003b900  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18003b907  mov     edx, 15A6h; void *
0x18003b90c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003b911  nop
0x18003b912  mov     rcx, [rbp+arg_0]
0x18003b916  jmp     short loc_18003B8C3
0x18003b918  xorps   xmm0, xmm0
0x18003b91b  movups  [rbp+var_20], xmm0
0x18003b91f  movups  [rbp+var_20+0Ch], xmm0
0x18003b923  lea     r14, [rbx+19h]
0x18003b927  lea     rdx, [rcx+420h]; struct _WWAN_PIN_LIST *
0x18003b92e  lea     rax, [rbp+var_20]
0x18003b932  mov     [rsp+70h+var_48], rax; struct Windows::Networking::UX::MbPinInfo *
0x18003b937  mov     [rsp+70h+var_50], r14; int
0x18003b93c  lea     r9, [rbx+14h]; unsigned int *
0x18003b940  lea     r8, [rbx+8]; struct _WWAN_PIN_INFO *
0x18003b944  call    ?_FillPinState@MBCategory@Internal@UX@Networking@Windows@@AEAAJAEBU_WWAN_PIN_LIST@@AEBU_WWAN_PIN_INFO@@AEBKAEB_NAEAUMbPinInfo@345@@Z; Windows::Networking::UX::Internal::MBCategory::_FillPinState(_WWAN_PIN_LIST const &,_WWAN_PIN_INFO const &,ulong const &,bool const &,Windows::Networking::UX::MbPinInfo &)
0x18003b949  mov     rcx, [rbp+38h]; this
0x18003b94d  test    eax, eax
0x18003b94f  jns     short loc_18003B967
0x18003b951  mov     r9d, eax; char *
0x18003b954  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18003b95b  mov     edx, 15ACh; void *
0x18003b960  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b965  jmp     short loc_18003B912
0x18003b967  lea     rsi, aWindowsNetwork_265; "Windows::Networking::UX::Internal::MBCa"...
0x18003b96e  cmp     dword ptr [rbx+8], 2
0x18003b972  jnz     short loc_18003B9A5
0x18003b974  mov     r9, [rbx]
0x18003b977  mov     eax, [rbx+0Ch]
0x18003b97a  mov     dword ptr [rsp+70h+var_50], eax; int
0x18003b97e  mov     r9d, [r9+254h]
0x18003b985  lea     r8, aUpdatePin1prev; "Update _pin1PreviousState. old _pin1Pre"...
0x18003b98c  mov     edx, 15B7h; unsigned int
0x18003b991  mov     rcx, rsi; char *
0x18003b994  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18003b999  mov     rcx, [rbx]
0x18003b99c  mov     eax, [rbx+0Ch]
0x18003b99f  mov     [rcx+254h], eax
0x18003b9a5  mov     edi, dword ptr [rbp+var_20]
0x18003b9a8  mov     rcx, rsi; char *
0x18003b9ab  cmp     edi, 1
0x18003b9ae  jz      loc_18003BA9D
0x18003b9b4  test    edi, edi
0x18003b9b6  jnz     short loc_18003B9CB
0x18003b9b8  lea     r8, aPintypeIsNoneP; "pinType is None - PIN is not set"
0x18003b9bf  mov     edx, 15C4h; unsigned int
0x18003b9c4  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18003b9c9  jmp     short loc_18003BA04
0x18003b9cb  mov     r9d, edi
0x18003b9ce  lea     r8, aPintypeIsNotPi; "pinType is not Pin1. pinType=%d"
0x18003b9d5  mov     edx, 15C8h; unsigned int
0x18003b9da  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18003b9df  cmp     edi, 3
0x18003b9e2  jl      short loc_18003BA04
0x18003b9e4  mov     rax, [rbx]
0x18003b9e7  mov     word ptr [rax+12Ah], 101h
0x18003b9f0  mov     rcx, [rbx]; this
0x18003b9f3  call    ?_CalculateConnectivity@MBCategory@Internal@UX@Networking@Windows@@AEAA_N_N@Z; Windows::Networking::UX::Internal::MBCategory::_CalculateConnectivity(bool)
0x18003b9f8  test    al, al
0x18003b9fa  jz      short loc_18003BA04
0x18003b9fc  mov     rcx, [rbx]; this
0x18003b9ff  call    ?_SubmitThreadpoolInvokeCategoryChange@MBCategory@Internal@UX@Networking@Windows@@AEAAJXZ; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange(void)
0x18003ba04  mov     dword ptr [rbp+var_38], r12d
0x18003ba08  mov     [rbp+var_30], r12
0x18003ba0c  mov     [rbp+var_28], r12d
0x18003ba10  mov     dword ptr [rbp+var_40], 1
0x18003ba17  mov     rdx, [rbp+arg_0]
0x18003ba1b  add     rdx, 420h; struct _WWAN_PIN_DESC *
0x18003ba22  lea     r8, [rbp+var_40]; struct Windows::Networking::UX::MbPinInfo *
0x18003ba26  call    ?_FillPinStateBasic@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEBU_WWAN_PIN_DESC@@AEAUMbPinInfo@345@@Z; Windows::Networking::UX::Internal::MBCategory::_FillPinStateBasic(_WWAN_PIN_DESC const &,Windows::Networking::UX::MbPinInfo &)
0x18003ba2b  mov     rdx, [rbx]
0x18003ba2e  mov     rcx, rsi; char *
0x18003ba31  cmp     [rdx+1DCh], r12d
0x18003ba38  jnz     short loc_18003BA6D
0x18003ba3a  lea     r8, aPin1HasNeverBe; "PIN1 has never been sent to UX. Query f"...
0x18003ba41  mov     edx, 15E1h; unsigned int
0x18003ba46  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18003ba4b  mov     rcx, [rbx]; this
0x18003ba4e  call    ?tp_GetPinState@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetPinState(void)
0x18003ba53  mov     dword ptr [rbp+var_38+4], r12d
0x18003ba57  mov     dword ptr [rbp+var_40+4], r12d
0x18003ba5b  mov     rax, [rbx]
0x18003ba5e  mov     [rax+254h], r12d
0x18003ba65  mov     rcx, [rbx]
0x18003ba68  mov     r8b, 1
0x18003ba6b  jmp     short loc_18003BA97
0x18003ba6d  lea     r8, aPin1AlreadySen; "PIN1 already sent to UX"
0x18003ba74  mov     edx, 15EFh; unsigned int
0x18003ba79  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18003ba7e  mov     rcx, [rbx]
0x18003ba81  mov     eax, [rcx+1E8h]
0x18003ba87  mov     dword ptr [rbp+var_38+4], eax
0x18003ba8a  mov     eax, [rcx+1E0h]
0x18003ba90  mov     dword ptr [rbp+var_40+4], eax
0x18003ba93  mov     r8b, [rbx+1Ah]
0x18003ba97  lea     rdx, [rbp+var_40]
0x18003ba9b  jmp     short loc_18003BAB9
0x18003ba9d  lea     r8, aPintypeIsPin1; "pinType is Pin1"
0x18003baa4  mov     edx, 15F9h; unsigned int
0x18003baa9  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18003baae  mov     r8b, [rbx+1Ah]; bool
0x18003bab2  lea     rdx, [rbp+var_20]; struct Windows::Networking::UX::MbPinInfo *
0x18003bab6  mov     rcx, [rbx]; this
0x18003bab9  call    ?tp_UpdatePinInfo@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEBUMbPinInfo@345@_N@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo(Windows::Networking::UX::MbPinInfo const &,bool)
0x18003babe  mov     rsi, [rbx]
0x18003bac1  add     rsi, 138h
0x18003bac8  mov     rcx, rsi; lpCriticalSection
0x18003bacb  call    cs:__imp_EnterCriticalSection
0x18003bad1  mov     [rbp+arg_18], rsi
0x18003bad5  mov     rax, [rbx]
0x18003bad8  cmp     [rax+160h], r12
0x18003badf  jz      loc_18003BC68
0x18003bae5  cmp     [rbx+18h], r12b
0x18003bae9  jz      loc_18003BBB0
0x18003baef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003baf6  mov     ecx, 30h ; '0'; unsigned __int64
0x18003bafb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003bb00  mov     rdi, rax
0x18003bb03  mov     [rbp+arg_8], rax
0x18003bb07  test    rax, rax
0x18003bb0a  jz      short loc_18003BB3A
0x18003bb0c  mov     edx, [rbx+14h]; unsigned int
0x18003bb0f  call    ?_HResultFromWwanStatus@MBCategory@Internal@UX@Networking@Windows@@AEAAJK@Z; Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(ulong)
0x18003bb14  mov     dword ptr [rdi+8], 1
0x18003bb1b  lea     rcx, ??_7MBPinEnterCompleteEvent@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::MBPinEnterCompleteEvent::`vftable'
0x18003bb22  mov     [rdi], rcx
0x18003bb25  movups  xmm0, [rbp+var_20]
0x18003bb29  movups  xmmword ptr [rdi+10h], xmm0
0x18003bb2d  movups  xmm1, [rbp+var_20+0Ch]
0x18003bb31  movups  xmmword ptr [rdi+1Ch], xmm1
0x18003bb35  mov     [rdi+2Ch], eax
0x18003bb38  jmp     short loc_18003BB3D
0x18003bb3a  mov     rdi, r12
0x18003bb3d  mov     [rbp+arg_10], rdi
0x18003bb41  test    rdi, rdi
0x18003bb44  jz      short loc_18003BB86
0x18003bb46  mov     rax, [rbx]
0x18003bb49  mov     rcx, [rax+160h]
0x18003bb50  mov     rax, [rcx]
0x18003bb53  mov     [rbp+arg_10], r12
0x18003bb57  mov     [rbp+arg_8], rdi
0x18003bb5b  lea     rdx, [rbp+arg_8]
0x18003bb5f  mov     rax, [rax+48h]
0x18003bb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb68  mov     rcx, [rbp+38h]; this
0x18003bb6c  test    eax, eax
0x18003bb6e  jns     short loc_18003BBA2
0x18003bb70  mov     r9d, eax; char *
0x18003bb73  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18003bb7a  mov     edx, 1608h; void *
0x18003bb7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003bb84  jmp     short loc_18003BBA2
0x18003bb86  mov     rcx, [rbp+38h]; this
0x18003bb8a  mov     r9d, 8007000Eh; char *
0x18003bb90  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18003bb97  mov     edx, 160Ch; void *
0x18003bb9c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003bba1  nop
0x18003bba2  lea     rcx, [rbp+arg_10]
0x18003bba6  call    ??1?$unique_ptr@UMBStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UMBStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(void)
0x18003bbab  jmp     loc_18003BC68
0x18003bbb0  cmp     [r14], r12b
0x18003bbb3  jz      loc_18003BC68
0x18003bbb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003bbc0  mov     ecx, 30h ; '0'; unsigned __int64
0x18003bbc5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003bbca  mov     rdx, rax
0x18003bbcd  mov     [rbp+arg_8], rax
0x18003bbd1  test    rax, rax
0x18003bbd4  jz      short loc_18003BBF6
0x18003bbd6  mov     [rax+8], r12d
0x18003bbda  lea     rax, ??_7MBPinEnterCompleteEvent@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::MBPinEnterCompleteEvent::`vftable'
0x18003bbe1  mov     [rdx], rax
0x18003bbe4  movups  xmm0, [rbp+var_20]
0x18003bbe8  movups  xmmword ptr [rdx+10h], xmm0
0x18003bbec  movups  xmm1, [rbp+var_20+0Ch]
0x18003bbf0  movups  xmmword ptr [rdx+1Ch], xmm1
0x18003bbf4  jmp     short loc_18003BBF9
0x18003bbf6  mov     rdx, r12
0x18003bbf9  mov     [rbp+arg_10], rdx
0x18003bbfd  test    rdx, rdx
0x18003bc00  jz      short loc_18003BC42
0x18003bc02  mov     rax, [rbx]
0x18003bc05  mov     rcx, [rax+160h]
0x18003bc0c  mov     rax, [rcx]
0x18003bc0f  mov     [rbp+arg_10], r12
0x18003bc13  mov     [rbp+arg_8], rdx
0x18003bc17  lea     rdx, [rbp+arg_8]
0x18003bc1b  mov     rax, [rax+48h]
0x18003bc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc24  mov     rcx, [rbp+38h]; this
0x18003bc28  test    eax, eax
0x18003bc2a  jns     short loc_18003BC5E
0x18003bc2c  mov     r9d, eax; char *
0x18003bc2f  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18003bc36  mov     edx, 1615h; void *
0x18003bc3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003bc40  jmp     short loc_18003BC5E
0x18003bc42  mov     rcx, [rbp+38h]; this
0x18003bc46  mov     r9d, 8007000Eh; char *
0x18003bc4c  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18003bc53  mov     edx, 1619h; void *
0x18003bc58  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003bc5d  nop
0x18003bc5e  lea     rcx, [rbp+arg_10]
0x18003bc62  call    ??1?$unique_ptr@UMBStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UMBStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(void)
0x18003bc67  nop
0x18003bc68  test    rsi, rsi
0x18003bc6b  jz      loc_18003B912
0x18003bc71  mov     rcx, rsi; lpCriticalSection
0x18003bc74  call    cs:__imp_LeaveCriticalSection
0x18003bc7a  jmp     loc_18003B912
```
