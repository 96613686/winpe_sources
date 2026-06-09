# CInterceptor_IWbemSyncProvider::Helper_GetObjectAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x14000bcb0`
- end: `0x14000c188`
- name: `?Helper_GetObjectAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `1240`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncProvider *__hidden this@<rcx>, int@<edx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000b7d0`

## callees

- `0x14000bcb0`
- `0x14000c190`
- `0x14000d1e0`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c11c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c11c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bd80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bd80`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000be7d`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000be7d`
- `wbemcomn!GetMemLogObject` at `0x14000c088`
- `wbemcomn!GetMemLogObject` at `0x14000c088`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000c093`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000c093`
- `OLEAUT32!__imp_SysAllocString` at `0x14000bd4b`
- `OLEAUT32!__imp_SysAllocString` at `0x14000bd4b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c025`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c025`
- `OLEAUT32!__imp_VariantInit` at `0x14000bd14`
- `OLEAUT32!__imp_VariantInit` at `0x14000bd14`
- `OLEAUT32!__imp_VariantClear` at `0x14000c037`
- `OLEAUT32!__imp_VariantClear` at `0x14000c064`
- `OLEAUT32!__imp_VariantClear` at `0x14000c037`
- `OLEAUT32!__imp_VariantClear` at `0x14000c064`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000c104`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000c148`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000c104`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000c148`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000bf6f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000c17d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000bf6f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000c17d`

## string_xrefs

- `0x14000bd29`: `__GET_EXTENSIONS`
- `0x14000c0b3`: `__GET_EXTENSIONS`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_GetObjectAsync(
        CInterceptor_IWbemSyncProvider *this,
        int a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6,
        struct IWbemServices *a7)
{
  int v11; // ebp
  __int64 v12; // rbx
  OLECHAR *v13; // r15
  LPVOID v14; // rdx
  void *v15; // rcx
  struct IWbemContext *v16; // rbx
  char *v17; // r14
  char *v18; // rcx
  HRESULT v19; // edi
  int v20; // eax
  char *v21; // rcx
  bool v22; // zf
  void (__fastcall *v23)(char *); // rax
  int v24; // ebp
  unsigned int v25; // ebp
  struct IWbemServices *v26; // r14
  struct IWbemClassObject *v27; // r8
  unsigned __int16 *v28; // r9
  const wchar_t *v30; // rdx
  CMemoryLog *MemLogObject; // rax
  __int64 v32; // [rsp+50h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-60h] BYREF

  v32 = 0;
  if ( a5 )
  {
    v11 = ((__int64 (__fastcall *)(struct IWbemContext *, __int64 *))a5->lpVtbl->Clone)(a5, &v32);
    v12 = v32;
    if ( v32 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v12 + 72LL))(
             v12,
             L"__GET_EXTENSIONS",
             0,
             &pvarg) >= 0 )
      {
        VariantClear(&pvarg);
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v12 + 72LL))(
               v12,
               L"__GET_EXT_CLIENT_REQUEST",
               0,
               &pvarg) < 0 )
        {
          (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v12 + 80LL))(
            v12,
            L"__GET_EXTENSIONS",
            0);
          (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v12 + 80LL))(
            v12,
            L"__GET_EXT_CLIENT_REQUEST",
            0);
          (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v12 + 80LL))(
            v12,
            L"__GET_EXT_KEYS_ONLY",
            0);
          v30 = L"__GET_EXT_PROPERTIES";
        }
        else
        {
          VariantClear(&pvarg);
          v30 = L"__GET_EXT_CLIENT_REQUEST";
        }
        (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v12 + 80LL))(v12, v30, 0);
      }
    }
    if ( v11 < 0 )
      goto LABEL_36;
  }
  v13 = SysAllocString(a3);
  if ( !v13 )
    goto LABEL_36;
  v14 = ProviderSubSystem_Globals::s_Allocator;
  v15 = (void *)*((_QWORD *)ProviderSubSystem_Globals::s_Allocator + 1);
  if ( !v15 )
    goto LABEL_45;
  v16 = (struct IWbemContext *)HeapAlloc(v15, *((_DWORD *)ProviderSubSystem_Globals::s_Allocator + 4) & 5 | 8u, 0xB0u);
  if ( !v16 )
  {
    GetLastError();
LABEL_45:
    v16 = 0;
  }
  a5 = v16;
  v17 = (char *)this + 232;
  if ( v16 )
  {
    v18 = (char *)this + 232;
    if ( !this )
      v18 = 0;
    CCommon_IWbemSyncObjectSink::CCommon_IWbemSyncObjectSink(
      (__int64)v16,
      (__int64)v14,
      (__int64)a6,
      (__int64)this,
      (__int64)v18);
    v16->lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_GetObjectAsync::`vftable'{for `IWbemObjectSinkEx'};
    v16[1].lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_GetObjectAsync::`vftable'{for `IWbemShutdown'};
    v16[2].lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_GetObjectAsync::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'};
    LODWORD(v16[19].lpVtbl) = a4 & 0xFFFFFDFF;
    v16[20].lpVtbl = (struct IWbemContextVtbl *)v13;
    v16[21].lpVtbl = (struct IWbemContextVtbl *)this;
    if ( this )
    {
      (*(void (__fastcall **)(CInterceptor_IWbemSyncProvider *))(*(_QWORD *)this + 8LL))(this);
      WmiSetAndCommitObject(
        qword_140061398,
        1,
        v16[21].lpVtbl[6].Next,
        *((_QWORD *)v16[21].lpVtbl[6].Clone + 8),
        v16[21].lpVtbl[6].BeginEnumeration,
        v16[21].lpVtbl[6].GetNames,
        v16[21].lpVtbl[6].EndEnumeration,
        v16[19].lpVtbl);
    }
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IWbemContext *))v16->lpVtbl->AddRef)(v16);
    v19 = ((__int64 (__fastcall *)(struct IWbemContext *))v16->lpVtbl->DeleteValue)(v16);
    if ( v19 >= 0 )
    {
      a5 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 48LL))((char *)this + 232);
      v20 = (*(__int64 (__fastcall **)(char *, struct IWbemContext *, struct IWbemContext **))(*(_QWORD *)v17 + 64LL))(
              (char *)this + 232,
              v16 + 2,
              &a5);
      v21 = (char *)this + 232;
      v22 = v20 == 0;
      v23 = *(void (__fastcall **)(char *))(*(_QWORD *)v17 + 56LL);
      if ( !v22 )
      {
        v23(v21);
        v19 = -2147217402;
        goto LABEL_24;
      }
      v23(v21);
      v24 = -641;
      if ( *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) )
        v24 = -513;
      if ( a2 && CoImpersonateClient() < 0 )
      {
        v19 = -2147217405;
        goto LABEL_24;
      }
      v25 = a4 & v24;
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 16);
      ++*((_QWORD *)this + 80);
      v26 = a7;
      v19 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, __int64, struct IWbemContext *))a7->lpVtbl->GetObjectAsync)(
              a7,
              v13,
              v25,
              v32,
              v16);
      CoRevertToSelf();
      if ( v19 == -2147217355 || v19 == -2147217400 )
      {
        if ( ProviderSubSystem_Globals::s_SharedCounters )
          ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 16);
        ++*((_QWORD *)this + 80);
        if ( a2 )
        {
          v19 = CoImpersonateClient();
          if ( v19 < 0 )
            goto LABEL_24;
        }
        v19 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, __int64, struct IWbemContext *))v26->lpVtbl->GetObjectAsync)(
                v26,
                v13,
                v25 & 0xFFFFFF7F,
                v32,
                v16);
        CoRevertToSelf();
      }
      if ( v19 < 0 )
LABEL_24:
        CInterceptor_IWbemSyncProvider::SetStatus(this, L"GetObjectAsync", v27, v28, v19, (struct IWbemObjectSink *)v16);
    }
    ((void (__fastcall *)(struct IWbemContext *))v16->lpVtbl->Release)(v16);
    goto LABEL_26;
  }
  SysFreeString(v13);
LABEL_36:
  v19 = -2147217402;
LABEL_26:
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v19 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v19);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14000bcb0  push    rbx
0x14000bcb2  push    rbp
0x14000bcb3  push    rsi
0x14000bcb4  push    rdi
0x14000bcb5  push    r12
0x14000bcb7  push    r13
0x14000bcb9  push    r14
0x14000bcbb  push    r15
0x14000bcbd  sub     rsp, 78h
0x14000bcc1  mov     r12d, r9d
0x14000bcc4  mov     rdi, r8
0x14000bcc7  mov     r13d, edx
0x14000bcca  mov     rsi, rcx
0x14000bccd  mov     [rsp+0B8h+var_68], 0
0x14000bcd6  mov     rcx, [rsp+0B8h+arg_20]
0x14000bcde  test    rcx, rcx
0x14000bce1  jz      short loc_14000BD48
0x14000bce3  mov     rax, [rcx]
0x14000bce6  lea     rdx, [rsp+0B8h+var_68]
0x14000bceb  mov     rax, [rax+18h]
0x14000bcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bcf4  mov     ebp, eax
0x14000bcf6  mov     rbx, [rsp+0B8h+var_68]
0x14000bcfb  test    rbx, rbx
0x14000bcfe  jz      short loc_14000BD40
0x14000bd00  xorps   xmm0, xmm0
0x14000bd03  xor     eax, eax
0x14000bd05  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x14000bd0a  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x14000bd0f  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x14000bd14  call    cs:__imp_VariantInit
0x14000bd1a  mov     rcx, [rbx]
0x14000bd1d  mov     rax, [rcx+48h]
0x14000bd21  lea     r9, [rsp+0B8h+pvarg]
0x14000bd26  xor     r8d, r8d
0x14000bd29  lea     rdx, aGetExtensions; "__GET_EXTENSIONS"
0x14000bd30  mov     rcx, rbx
0x14000bd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd38  test    eax, eax
0x14000bd3a  jns     loc_14000C032
0x14000bd40  test    ebp, ebp
0x14000bd42  js      loc_14000C02B
0x14000bd48  mov     rcx, rdi; psz
0x14000bd4b  call    cs:__imp_SysAllocString
0x14000bd51  mov     r15, rax
0x14000bd54  test    rax, rax
0x14000bd57  jz      loc_14000C02B
0x14000bd5d  mov     rdx, cs:?s_Allocator@ProviderSubSystem_Globals@@2PEAVWmiAllocator@@EA; WmiAllocator * ProviderSubSystem_Globals::s_Allocator
0x14000bd64  mov     rcx, [rdx+8]; hHeap
0x14000bd68  test    rcx, rcx
0x14000bd6b  jz      loc_14000C122
0x14000bd71  mov     edx, [rdx+10h]
0x14000bd74  and     edx, 5
0x14000bd77  or      edx, 8; dwFlags
0x14000bd7a  mov     r8d, 0B0h; dwBytes
0x14000bd80  call    cs:__imp_HeapAlloc
0x14000bd86  mov     rbx, rax
0x14000bd89  test    rax, rax
0x14000bd8c  jz      loc_14000C11C
0x14000bd92  mov     [rsp+0B8h+arg_20], rbx
0x14000bd9a  lea     r14, [rsi+0E8h]
0x14000bda1  test    rbx, rbx
0x14000bda4  jz      loc_14000BE84
0x14000bdaa  mov     edi, r12d
0x14000bdad  btr     edi, 9
0x14000bdb1  mov     rcx, r14
0x14000bdb4  xor     eax, eax
0x14000bdb6  test    rsi, rsi
0x14000bdb9  cmovz   rcx, rax
0x14000bdbd  mov     qword ptr [rsp+0B8h+var_98], rcx
0x14000bdc2  mov     r9, rsi
0x14000bdc5  mov     r8, [rsp+0B8h+arg_28]
0x14000bdcd  mov     rcx, rbx
0x14000bdd0  call    ??0CCommon_IWbemSyncObjectSink@@QEAA@AEAVWmiAllocator@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K@Z; CCommon_IWbemSyncObjectSink::CCommon_IWbemSyncObjectSink(WmiAllocator &,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong)
0x14000bdd5  nop
0x14000bdd6  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_GetObjectAsync@@6BIWbemObjectSinkEx@@@; const CInterceptor_IWbemSyncObjectSink_GetObjectAsync::`vftable'{for `IWbemObjectSinkEx'}
0x14000bddd  mov     [rbx], rax
0x14000bde0  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_GetObjectAsync@@6BIWbemShutdown@@@; const CInterceptor_IWbemSyncObjectSink_GetObjectAsync::`vftable'{for `IWbemShutdown'}
0x14000bde7  mov     [rbx+8], rax
0x14000bdeb  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_GetObjectAsync@@6BWmiContainerElement@?$WmiContainerController@PEAX@@@; const CInterceptor_IWbemSyncObjectSink_GetObjectAsync::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'}
0x14000bdf2  mov     [rbx+10h], rax
0x14000bdf6  mov     [rbx+98h], edi
0x14000bdfc  mov     [rbx+0A0h], r15
0x14000be03  mov     [rbx+0A8h], rsi
0x14000be0a  test    rsi, rsi
0x14000be0d  jz      short loc_14000BE84
0x14000be0f  mov     rax, [rsi]
0x14000be12  mov     rcx, rsi
0x14000be15  mov     rax, [rax+8]
0x14000be19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be1e  mov     r8, [rbx+0A8h]
0x14000be25  mov     r9, [r8+258h]
0x14000be2c  mov     rax, [rbx+0A0h]
0x14000be33  mov     [rsp+0B8h+var_78], rax
0x14000be38  mov     eax, [rbx+98h]
0x14000be3e  mov     [rsp+0B8h+var_80], eax
0x14000be42  mov     rax, [r8+278h]
0x14000be49  mov     [rsp+0B8h+var_88], rax
0x14000be4e  mov     rax, [r8+260h]
0x14000be55  mov     [rsp+0B8h+var_90], rax
0x14000be5a  mov     rax, [r8+268h]
0x14000be61  mov     qword ptr [rsp+0B8h+var_98], rax
0x14000be66  mov     r9, [r9+40h]
0x14000be6a  mov     r8, [r8+270h]
0x14000be71  mov     edx, 1
0x14000be76  mov     rcx, cs:qword_140061398
0x14000be7d  call    cs:__imp_WmiSetAndCommitObject
0x14000be83  nop
0x14000be84  test    rbx, rbx
0x14000be87  jz      loc_14000C022
0x14000be8d  mov     rax, [rbx]
0x14000be90  mov     rcx, rbx
0x14000be93  mov     rax, [rax+8]
0x14000be97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be9c  mov     rax, [rbx]
0x14000be9f  mov     rcx, rbx
0x14000bea2  mov     rax, [rax+50h]
0x14000bea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000beab  mov     edi, eax
0x14000bead  test    eax, eax
0x14000beaf  js      loc_14000BFA9
0x14000beb5  mov     [rsp+0B8h+arg_20], 0
0x14000bec1  mov     rax, [r14]
0x14000bec4  mov     rcx, r14
0x14000bec7  mov     rax, [rax+30h]
0x14000becb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bed0  mov     rax, [r14]
0x14000bed3  lea     rdx, [rbx+10h]
0x14000bed7  lea     r8, [rsp+0B8h+arg_20]
0x14000bedf  mov     rcx, r14
0x14000bee2  mov     rax, [rax+40h]
0x14000bee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000beeb  mov     rdx, [r14]
0x14000beee  mov     r8, [rdx+38h]
0x14000bef2  mov     rcx, r14
0x14000bef5  test    eax, eax
0x14000bef7  mov     rax, r8
0x14000befa  jnz     loc_14000C09E
0x14000bf00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf05  mov     rax, [rsi+258h]
0x14000bf0c  mov     ebp, 0FFFFFD7Fh
0x14000bf11  cmp     dword ptr [rax+6CCh], 0
0x14000bf18  mov     eax, 0FFFFFDFFh
0x14000bf1d  cmovnz  ebp, eax
0x14000bf20  test    r13d, r13d
0x14000bf23  jnz     loc_14000C104
0x14000bf29  and     ebp, r12d
0x14000bf2c  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000bf33  test    rax, rax
0x14000bf36  jz      short loc_14000BF3F
0x14000bf38  inc     qword ptr [rax+80h]
0x14000bf3f  inc     qword ptr [rsi+280h]
0x14000bf46  mov     r14, [rsp+0B8h+arg_30]
0x14000bf4e  mov     rax, [r14]
0x14000bf51  mov     qword ptr [rsp+0B8h+var_98], rbx
0x14000bf56  mov     r9, [rsp+0B8h+var_68]
0x14000bf5b  mov     r8d, ebp
0x14000bf5e  mov     rdx, r15
0x14000bf61  mov     rcx, r14
0x14000bf64  mov     rax, [rax+38h]
0x14000bf68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf6d  mov     edi, eax
0x14000bf6f  call    cs:__imp_CoRevertToSelf
0x14000bf75  cmp     edi, 80041035h
0x14000bf7b  jz      loc_14000C129
0x14000bf81  cmp     edi, 80041008h
0x14000bf87  jz      loc_14000C129
0x14000bf8d  test    edi, edi
0x14000bf8f  jns     short loc_14000BFA9
0x14000bf91  mov     [rsp+0B8h+var_90], rbx; struct IWbemObjectSink *
0x14000bf96  mov     [rsp+0B8h+var_98], edi; int
0x14000bf9a  lea     rdx, aGetobjectasync; "GetObjectAsync"
0x14000bfa1  mov     rcx, rsi; this
0x14000bfa4  call    ?SetStatus@CInterceptor_IWbemSyncProvider@@AEAAJPEAG00JPEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::SetStatus(ushort *,ushort *,ushort *,long,IWbemObjectSink *)
0x14000bfa9  mov     rax, [rbx]
0x14000bfac  mov     rcx, rbx
0x14000bfaf  mov     rax, [rax+10h]
0x14000bfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bfb8  mov     rcx, [rsp+0B8h+var_68]
0x14000bfbd  test    rcx, rcx
0x14000bfc0  jz      short loc_14000BFCE
0x14000bfc2  mov     rax, [rcx]
0x14000bfc5  mov     rax, [rax+10h]
0x14000bfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bfce  test    edi, edi
0x14000bfd0  js      loc_14000C088
0x14000bfd6  lea     rax, WPP_GLOBAL_Control
0x14000bfdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bfe4  cmp     rcx, rax
0x14000bfe7  jnz     short loc_14000BFFC
0x14000bfe9  mov     eax, edi
0x14000bfeb  add     rsp, 78h
0x14000bfef  pop     r15
0x14000bff1  pop     r14
0x14000bff3  pop     r13
0x14000bff5  pop     r12
0x14000bff7  pop     rdi
0x14000bff8  pop     rsi
0x14000bff9  pop     rbp
0x14000bffa  pop     rbx
0x14000bffb  retn
0x14000bffc  test    byte ptr [rcx+1Ch], 4
0x14000c000  jz      short loc_14000BFE9
0x14000c002  cmp     byte ptr [rcx+19h], 2
0x14000c006  jb      short loc_14000BFE9
0x14000c008  mov     edx, 4Fh ; 'O'
0x14000c00d  mov     r9d, edi
0x14000c010  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000c017  mov     rcx, [rcx+10h]
0x14000c01b  call    WPP_SF_d
0x14000c020  jmp     short loc_14000BFE9
0x14000c022  mov     rcx, r15; bstrString
0x14000c025  call    cs:__imp_SysFreeString
0x14000c02b  mov     edi, 80041006h
0x14000c030  jmp     short loc_14000BFB8
0x14000c032  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x14000c037  call    cs:__imp_VariantClear
0x14000c03d  mov     rax, [rbx]
0x14000c040  lea     r9, [rsp+0B8h+pvarg]
0x14000c045  xor     r8d, r8d
0x14000c048  lea     rdx, aGetExtClientRe; "__GET_EXT_CLIENT_REQUEST"
0x14000c04f  mov     rcx, rbx
0x14000c052  mov     rax, [rax+48h]
0x14000c056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c05b  test    eax, eax
0x14000c05d  js      short loc_14000C0AD
0x14000c05f  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x14000c064  call    cs:__imp_VariantClear
0x14000c06a  lea     rdx, aGetExtClientRe; "__GET_EXT_CLIENT_REQUEST"
0x14000c071  mov     rax, [rbx]
0x14000c074  xor     r8d, r8d
0x14000c077  mov     rcx, rbx
0x14000c07a  mov     rax, [rax+50h]
0x14000c07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c083  jmp     loc_14000BD40
0x14000c088  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000c08e  mov     edx, edi
0x14000c090  mov     rcx, rax
0x14000c093  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000c099  jmp     loc_14000BFD6
0x14000c09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0a3  mov     edi, 80041006h
0x14000c0a8  jmp     loc_14000BF91
0x14000c0ad  mov     rax, [rbx]
0x14000c0b0  xor     r8d, r8d
0x14000c0b3  lea     rdx, aGetExtensions; "__GET_EXTENSIONS"
0x14000c0ba  mov     rcx, rbx
0x14000c0bd  mov     rax, [rax+50h]
0x14000c0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0c6  mov     rax, [rbx]
0x14000c0c9  xor     r8d, r8d
0x14000c0cc  lea     rdx, aGetExtClientRe; "__GET_EXT_CLIENT_REQUEST"
0x14000c0d3  mov     rcx, rbx
0x14000c0d6  mov     rax, [rax+50h]
0x14000c0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0df  mov     rax, [rbx]
0x14000c0e2  xor     r8d, r8d
0x14000c0e5  lea     rdx, aGetExtKeysOnly; "__GET_EXT_KEYS_ONLY"
0x14000c0ec  mov     rcx, rbx
0x14000c0ef  mov     rax, [rax+50h]
0x14000c0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0f8  lea     rdx, aGetExtProperti; "__GET_EXT_PROPERTIES"
0x14000c0ff  jmp     loc_14000C071
0x14000c104  call    cs:__imp_CoImpersonateClient
0x14000c10a  test    eax, eax
0x14000c10c  jns     loc_14000BF29
0x14000c112  mov     edi, 80041003h
0x14000c117  jmp     loc_14000BF91
0x14000c11c  call    cs:__imp_GetLastError
0x14000c122  xor     ebx, ebx
0x14000c124  jmp     loc_14000BD92
0x14000c129  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000c130  test    rax, rax
0x14000c133  jz      short loc_14000C13C
0x14000c135  inc     qword ptr [rax+80h]
0x14000c13c  inc     qword ptr [rsi+280h]
0x14000c143  test    r13d, r13d
0x14000c146  jz      short loc_14000C158
0x14000c148  call    cs:__imp_CoImpersonateClient
0x14000c14e  mov     edi, eax
0x14000c150  test    eax, eax
0x14000c152  js      loc_14000BF91
0x14000c158  mov     rax, [r14]
0x14000c15b  btr     ebp, 7
0x14000c15f  mov     qword ptr [rsp+0B8h+var_98], rbx
0x14000c164  mov     r9, [rsp+0B8h+var_68]
0x14000c169  mov     r8d, ebp
0x14000c16c  mov     rdx, r15
0x14000c16f  mov     rcx, r14
0x14000c172  mov     rax, [rax+38h]
0x14000c176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c17b  mov     edi, eax
0x14000c17d  call    cs:__imp_CoRevertToSelf
0x14000c183  jmp     loc_14000BF8D
```
