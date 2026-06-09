# MapsStoreManager::DeleteData(int,int)

- ea: `0x180018730`
- end: `0x1800188d6`
- name: `?DeleteData@MapsStoreManager@@QEAAJHH@Z`
- size: `422`
- prototype: `__int64 __fastcall(MapsStoreManager *this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180011920`

## callees

- `0x1800162bc`
- `0x180016d58`
- `0x180017aa8`
- `0x180018730`
- `0x180019f68`
- `0x18001b9e0`
- `0x18001d424`
- `0x18001d8f4`
- `0x1800499d0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800187bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800187bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001887b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001887b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800188a8`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800188a8`

## string_xrefs

- `0x1800188a1`: `MapsStoreManager::DeleteData`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::DeleteData(MapsStoreManager *this, unsigned int a2, unsigned int a3)
{
  int v6; // r8d
  int v7; // ecx
  __int64 v8; // rax
  HANDLE Event; // rdi
  std::_Ref_count_base *v10; // rsi
  std::_Ref_count_base *v11; // rax
  wil **v12; // rdi
  unsigned int v13; // r8d
  int v14; // r9d
  wil *v15; // rcx
  unsigned int v16; // ebx
  signed int LastError; // eax
  __int128 v19; // [rsp+30h] [rbp-39h] BYREF
  __int64 v20; // [rsp+40h] [rbp-29h] BYREF
  std::_Ref_count_base *v21; // [rsp+48h] [rbp-21h]
  std::_Ref_count_base *v22[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 (__fastcall **v23)(); // [rsp+60h] [rbp-9h] BYREF
  _BYTE v24[48]; // [rsp+68h] [rbp-1h] BYREF
  __int64 (__fastcall ***v25)(); // [rsp+98h] [rbp+2Fh]

  *(_OWORD *)v22 = 0;
  v19 = 0;
  if ( MapControl::RegionSet::getIsLoaded((LPCRITICAL_SECTION)this) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, _QWORD, _DWORD))(**((_QWORD **)this + 40) + 24LL))(
           *((_QWORD *)this + 40),
           &v20,
           a2,
           a3,
           0);
    std::shared_ptr<MapControl::LocalIndex>::operator=(v22, v8);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
        &v19,
        Event);
      v10 = v22[0];
      v11 = (std::_Ref_count_base *)*((_QWORD *)&v19 + 1);
      if ( *((_QWORD *)&v19 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL));
      v12 = (wil **)v19;
      v20 = v19;
      v21 = v11;
      v25 = 0;
      v23 = off_1800991A0;
      lambda_c9b97e345bbdc8a72cff7d0e9edce9b7_::_lambda_c9b97e345bbdc8a72cff7d0e9edce9b7_(v24, &v20);
      v25 = &v23;
      MapControl::PersistedDataLoaderAsyncOperation::setCallback(v10, &v23);
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&v20);
      if ( v12 )
        v15 = *v12;
      else
        v15 = 0;
      if ( wil::handle_wait(v15, (void *)0xFFFFFFFFLL, v13, v14) )
      {
        if ( *((_BYTE *)v10 + 150) )
        {
          v16 = 0;
          goto LABEL_22;
        }
        v6 = 441;
        v7 = -2080309238;
      }
      else
      {
        v6 = 439;
        v7 = -1;
      }
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
      v6 = 432;
      v7 = LastError;
    }
  }
  else
  {
    v6 = 428;
    v7 = -2147024875;
  }
  v16 = ZTraceReportOrigination(v7, "MapsStoreManager::DeleteData", v6, this);
LABEL_22:
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&v19);
  if ( v22[1] )
    std::_Ref_count_base::_Decref(v22[1]);
  return v16;
}

```

## disassembly

```asm
0x180018730  push    rbp
0x180018732  push    rbx
0x180018733  push    rsi
0x180018734  push    rdi
0x180018735  lea     rbp, [rsp-3Fh]
0x18001873a  sub     rsp, 0A8h
0x180018741  mov     edi, r8d
0x180018744  mov     esi, edx
0x180018746  mov     rbx, rcx
0x180018749  xorps   xmm0, xmm0
0x18001874c  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180018751  xorps   xmm1, xmm1
0x180018754  movdqu  [rbp+57h+var_90], xmm1
0x180018759  call    ?getIsLoaded@RegionSet@MapControl@@QEAA_NXZ; MapControl::RegionSet::getIsLoaded(void)
0x18001875e  test    al, al
0x180018760  jnz     short loc_180018772
0x180018762  mov     r8d, 1ACh
0x180018768  mov     ecx, 80070015h
0x18001876d  jmp     loc_18001889E
0x180018772  mov     rcx, [rbx+140h]
0x180018779  mov     rax, [rcx]
0x18001877c  mov     [rsp+0C0h+var_A0], 0
0x180018784  mov     r9d, edi
0x180018787  mov     r8d, esi
0x18001878a  lea     rdx, [rbp+57h+var_80]
0x18001878e  mov     rax, [rax+18h]
0x180018792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018797  mov     rdx, rax
0x18001879a  lea     rcx, [rbp+57h+var_70]
0x18001879e  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x1800187a3  mov     rcx, [rbp+57h+var_78]; this
0x1800187a7  test    rcx, rcx
0x1800187aa  jz      short loc_1800187B1
0x1800187ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800187b1  xor     edx, edx; lpName
0x1800187b3  xor     ecx, ecx; lpEventAttributes
0x1800187b5  mov     r9d, 1F0003h; dwDesiredAccess
0x1800187bb  lea     r8d, [rdx+1]; dwFlags
0x1800187bf  call    cs:__imp_CreateEventExW
0x1800187c5  mov     rdi, rax
0x1800187c8  test    rax, rax
0x1800187cb  jz      loc_18001887B
0x1800187d1  call    cs:__imp_GetLastError
0x1800187d7  mov     rdx, rdi
0x1800187da  lea     rcx, [rbp+57h+var_90]
0x1800187de  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x1800187e3  mov     rsi, [rbp+57h+var_70]
0x1800187e7  mov     rax, qword ptr [rbp+57h+var_90+8]
0x1800187eb  test    rax, rax
0x1800187ee  jz      short loc_1800187F4
0x1800187f0  lock inc dword ptr [rax+8]
0x1800187f4  mov     rdi, qword ptr [rbp+57h+var_90]
0x1800187f8  mov     [rbp+57h+var_80], rdi
0x1800187fc  mov     [rbp+57h+var_78], rax
0x180018800  mov     [rbp+57h+var_28], 0
0x180018808  lea     rax, off_1800991A0
0x18001880f  mov     [rbp+57h+var_60], rax
0x180018813  lea     rdx, [rbp+57h+var_80]
0x180018817  lea     rcx, [rbp+57h+var_58]
0x18001881b  call    _lambda_c9b97e345bbdc8a72cff7d0e9edce9b7____lambda_c9b97e345bbdc8a72cff7d0e9edce9b7_
0x180018820  lea     rcx, [rbp+57h+var_60]
0x180018824  mov     [rbp+57h+var_28], rcx
0x180018828  lea     rdx, [rbp+57h+var_60]
0x18001882c  mov     rcx, rsi
0x18001882f  call    ?setCallback@PersistedDataLoaderAsyncOperation@MapControl@@QEAAXV?$function@$$A6AXAEBVPersistedDataLoaderAsyncOperation@MapControl@@@Z@std@@@Z; MapControl::PersistedDataLoaderAsyncOperation::setCallback(std::function<void (MapControl::PersistedDataLoaderAsyncOperation const &)>)
0x180018834  nop
0x180018835  lea     rcx, [rbp+57h+var_80]
0x180018839  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18001883e  test    rdi, rdi
0x180018841  jz      short loc_180018848
0x180018843  mov     rcx, [rdi]
0x180018846  jmp     short loc_18001884A
0x180018848  xor     ecx, ecx; this
0x18001884a  or      edx, 0FFFFFFFFh; void *
0x18001884d  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180018852  test    al, al
0x180018854  jnz     short loc_180018861
0x180018856  mov     r8d, 1B7h
0x18001885c  or      ecx, 0FFFFFFFFh
0x18001885f  jmp     short loc_18001889E
0x180018861  cmp     byte ptr [rsi+96h], 0
0x180018868  jnz     short loc_180018877
0x18001886a  mov     r8d, 1B9h
0x180018870  mov     ecx, 8401000Ah
0x180018875  jmp     short loc_18001889E
0x180018877  xor     ebx, ebx
0x180018879  jmp     short loc_1800188B0
0x18001887b  call    cs:__imp_GetLastError
0x180018881  test    eax, eax
0x180018883  jz      short loc_180018891
0x180018885  jle     short loc_180018896
0x180018887  movzx   eax, ax
0x18001888a  or      eax, 80070000h
0x18001888f  jmp     short loc_180018896
0x180018891  mov     eax, 80390004h
0x180018896  mov     r8d, 1B0h
0x18001889c  mov     ecx, eax
0x18001889e  mov     r9, rbx
0x1800188a1  lea     rdx, aMapsstoremanag_8; "MapsStoreManager::DeleteData"
0x1800188a8  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800188ae  mov     ebx, eax
0x1800188b0  lea     rcx, [rbp+57h+var_90]
0x1800188b4  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x1800188b9  nop
0x1800188ba  mov     rcx, [rbp+57h+var_70+8]; this
0x1800188be  test    rcx, rcx
0x1800188c1  jz      short loc_1800188C8
0x1800188c3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800188c8  mov     eax, ebx
0x1800188ca  add     rsp, 0A8h
0x1800188d1  pop     rdi
0x1800188d2  pop     rsi
0x1800188d3  pop     rbx
0x1800188d4  pop     rbp
0x1800188d5  retn
```
