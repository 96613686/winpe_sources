# InterceptInterface(_GUID const &,void *,void * *)

- ea: `0x1800070b8`
- end: `0x1800074f5`
- name: `?InterceptInterface@@YAJAEBU_GUID@@PEAXPEAPEAX@Z`
- size: `1085`
- prototype: `__int64 __fastcall(IID *rclsid, void *, void **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007520`
- `0x1800076b0`

## callees

- `0x1800070b8`
- `0x180007da8`
- `0x180007e04`
- `0x180007e5c`
- `0x180007f80`
- `0x180007fdc`
- `0x18000866c`
- `0x180008958`
- `0x1800089b0`
- `0x180008af0`
- `0x180009f74`
- `0x18000a010`
- `0x18000ab0c`
- `0x1800266e0`
- `0x18002b3c0`
- `0x18002b400`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007223`
- `KERNEL32!EnterCriticalSection` at `0x180007223`
- `KERNEL32!LeaveCriticalSection` at `0x18000723d`
- `KERNEL32!LeaveCriticalSection` at `0x180007250`
- `KERNEL32!LeaveCriticalSection` at `0x18000723d`
- `KERNEL32!LeaveCriticalSection` at `0x180007250`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180007163`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000728a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800072c6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180007302`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000733b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180007374`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180007163`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000728a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800072c6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180007302`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000733b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180007374`
- `ADVAPI32!RegCloseKey` at `0x180007486`
- `ADVAPI32!RegCloseKey` at `0x180007486`
- `ADVAPI32!RegOpenKeyExW` at `0x18000742a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000742a`
- `ole32!StringFromGUID2` at `0x180007123`
- `ole32!StringFromGUID2` at `0x180007123`
- `ole32!CoTaskMemFree` at `0x180007478`
- `ole32!CoTaskMemFree` at `0x180007478`
- `ole32!StringFromIID` at `0x1800073b0`
- `ole32!StringFromIID` at `0x1800073b0`
- `ole32!CoGetInterceptor` at `0x180007149`
- `ole32!CoGetInterceptor` at `0x180007149`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InterceptInterface(IID *rclsid, void *a2, void **a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  HRESULT Interceptor; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // r14
  __int64 v11; // rdx
  void **v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 **v15; // rdi
  __int64 *v16; // rdi
  __int64 v17; // r15
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  LSTATUS v21; // eax
  HKEY v22; // rbx
  __int64 v23; // rcx
  const wchar_t *v24; // rdx
  unsigned int v26; // [rsp+30h] [rbp-D0h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  OLECHAR sz[64]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v34[256]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t Buffer[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  if ( olog == 100 )
  {
    memset(sz, 0, sizeof(sz));
    StringFromGUID2(rclsid, sz, 64);
    LogLineFormat<27,wchar_t [64]>(v7, v6, sz);
  }
  ppv = 0;
  Interceptor = CoGetInterceptor(rclsid, 0, &GUID_60c7ca75_896d_11d2_b8b6_00c04fb9618a, &ppv);
  v26 = Interceptor;
  if ( Interceptor >= 0 )
  {
    v9 = malloc(0x18u);
    v10 = v9;
    if ( v9 )
    {
      *v9 = &CCallFrameEvents::`vftable';
      v9[1] = a2;
      (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 8LL))(a2);
      ++g_cInterceptors;
      *((_DWORD *)v10 + 4) = 0;
      Interceptor = (*(__int64 (__fastcall **)(void *, _QWORD *))(*(_QWORD *)ppv + 56LL))(ppv, v10);
      v26 = Interceptor;
      if ( Interceptor >= 0 )
      {
        _mm_lfence();
        Interceptor = (**(__int64 (__fastcall ***)(void *, IID *, void **))ppv)(ppv, rclsid, a3);
        v26 = Interceptor;
      }
      goto LABEL_43;
    }
LABEL_49:
    std::_Xbad_alloc();
  }
  _mm_lfence();
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&IID_IUnknown.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = a2;
    v13 = Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance();
    v14 = v13;
    v15 = (__int64 **)*a3;
    if ( v15 )
    {
      v16 = *v15;
      v17 = *v16;
      v18 = (struct _RTL_CRITICAL_SECTION *)(v13 + 64);
      EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 64));
      if ( (unsigned __int8)SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>::VtblMethodSwap(
                              v19,
                              v16) )
      {
        LeaveCriticalSection(v18);
        TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::insert(v14, v16, v17);
        goto LABEL_43;
      }
      LogLineFormat<48>();
      LeaveCriticalSection(v18);
    }
    LogLineFormat<49>();
    goto LABEL_43;
  }
  _mm_lfence();
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&IID_IPersistPropertyBag.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)IID_IPersistPropertyBag.Data4 )
  {
    v20 = malloc(0x10u);
    if ( !v20 )
      goto LABEL_49;
    v12 = &CInterceptorPersistPropertyBag::`vftable';
    goto LABEL_34;
  }
  _mm_lfence();
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&GUID_c73106ba_ac80_11d1_8df3_00c04fb6ef4f.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)GUID_c73106ba_ac80_11d1_8df3_00c04fb6ef4f.Data4 )
  {
    v20 = malloc(0x10u);
    if ( !v20 )
      goto LABEL_49;
    v12 = &CInterceptorSearchProtocol::`vftable';
    goto LABEL_34;
  }
  _mm_lfence();
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&GUID_7789f0b2_b5b2_4722_8b65_5dbd150697a9.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)GUID_7789f0b2_b5b2_4722_8b65_5dbd150697a9.Data4 )
  {
    v20 = malloc(0x10u);
    if ( !v20 )
      goto LABEL_49;
    v12 = &CInterceptorSearchProtocol2::`vftable';
    goto LABEL_34;
  }
  _mm_lfence();
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&GUID_1c2056cc_5ef4_101b_8bc8_00aa003e3b29.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)GUID_1c2056cc_5ef4_101b_8bc8_00aa003e3b29.Data4 )
  {
    v20 = malloc(0x10u);
    if ( !v20 )
      goto LABEL_49;
    v12 = &CInterceptorOleInPlaceObjectWindowless::`vftable';
    goto LABEL_34;
  }
  _mm_lfence();
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&GUID_3050f425_98b5_11cf_bb82_00aa00bdce0b.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)GUID_3050f425_98b5_11cf_bb82_00aa00bdce0b.Data4 )
  {
    v20 = malloc(0x10u);
    if ( !v20 )
      goto LABEL_49;
    v12 = &CIElementBehavior::`vftable';
LABEL_34:
    *v20 = v12;
    v20[1] = a2;
    _InterlockedIncrement((volatile signed __int32 *)&g_cInterceptors);
    *a3 = v20;
    goto LABEL_43;
  }
  _mm_lfence();
  lpsz = 0;
  if ( !StringFromIID(rclsid, &lpsz) )
  {
    snwprintf_s(Buffer, 0x104u, 0xFFFFFFFFFFFFFFFFuLL, L"Interface\\%s", lpsz);
    memset(v34, 0, sizeof(v34));
    v31 = 0;
    v32 = 0;
    hKey = 0;
    v21 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Buffer, 0, 0x20019u, &hKey);
    v22 = 0;
    if ( !v21 )
      v22 = hKey;
    v30 = v22;
    v23 = (unsigned int)-v21;
    v24 = (const wchar_t *)(unsigned int)-(v21 != 0);
    if ( ((unsigned int)v24 & v21) == 0 )
    {
      LODWORD(hKey) = 256;
      ATL::CRegKey::QueryStringValue((ATL::CRegKey *)&v30, v24, v34, (unsigned int *)&hKey);
    }
    LogLineFormat<67,wchar_t *,wchar_t [256]>(v23, v24, &lpsz, v34);
    CoTaskMemFree(lpsz);
    if ( v22 )
      RegCloseKey(v22);
  }
  *a3 = a2;
LABEL_43:
  if ( Interceptor < 0 )
    LogLineFormat<63,long>(v12, v11, &v26);
  else
    LogLineFormat<48,long>(v12, v11, &v26);
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return v26;
}

```

## disassembly

```asm
0x1800070b8  mov     [rsp-8+arg_8], rbx
0x1800070bd  mov     [rsp-8+arg_18], rsi
0x1800070c2  push    rbp
0x1800070c3  push    rdi
0x1800070c4  push    r12
0x1800070c6  push    r14
0x1800070c8  push    r15
0x1800070ca  lea     rbp, [rsp-410h]
0x1800070d2  sub     rsp, 510h
0x1800070d9  mov     rax, cs:__security_cookie
0x1800070e0  xor     rax, rsp
0x1800070e3  mov     [rbp+430h+var_30], rax
0x1800070ea  mov     rdi, r8
0x1800070ed  mov     rsi, rdx
0x1800070f0  mov     rbx, rcx
0x1800070f3  xor     r12d, r12d
0x1800070f6  cmp     cs:?olog@@3VOLog@@A, 64h ; 'd'; OLog olog
0x1800070fd  jnz     short loc_180007133
0x1800070ff  mov     [rsp+530h+sz], r12w
0x180007105  xor     edx, edx; Val
0x180007107  lea     r8d, [r12+7Eh]; Size
0x18000710c  lea     rcx, [rsp+530h+var_4BE]; void *
0x180007111  call    memset
0x180007116  lea     r8d, [r12+40h]; cchMax
0x18000711b  lea     rdx, [rsp+530h+sz]; lpsz
0x180007120  mov     rcx, rbx; rguid
0x180007123  call    cs:__imp_StringFromGUID2
0x180007129  lea     r8, [rsp+530h+sz]
0x18000712e  call    ??$LogLineFormat@$0BL@$$BY0EA@_W@@YAXW4Severity@Logging@Mso@@AEAY0BL@$$CB_WAEAY0EA@$$CB_W@Z; LogLineFormat<27,wchar_t [64]>(Mso::Logging::Severity,wchar_t const (&)[27],wchar_t const (&)[64])
0x180007133  mov     [rsp+530h+ppv], r12
0x180007138  lea     r9, [rsp+530h+ppv]; ppv
0x18000713d  lea     r8, _GUID_60c7ca75_896d_11d2_b8b6_00c04fb9618a; iid
0x180007144  xor     edx, edx; punkOuter
0x180007146  mov     rcx, rbx; iidIntercepted
0x180007149  call    cs:__imp_CoGetInterceptor
0x18000714f  mov     r14d, eax
0x180007152  mov     [rsp+530h+var_500], eax
0x180007156  test    eax, eax
0x180007158  js      loc_1800071E7
0x18000715e  mov     ecx, 18h; Size
0x180007163  call    cs:__imp_malloc
0x180007169  mov     r14, rax
0x18000716c  test    rax, rax
0x18000716f  jz      loc_1800074EC
0x180007175  lea     rax, ??_7CCallFrameEvents@@6B@; const CCallFrameEvents::`vftable'
0x18000717c  mov     [r14], rax
0x18000717f  mov     [r14+8], rsi
0x180007183  mov     rax, [rsi]
0x180007186  mov     rcx, rsi
0x180007189  mov     rax, [rax+8]
0x18000718d  call    cs:__guard_dispatch_icall_fptr
0x180007193  inc     cs:?g_cInterceptors@@3KA; ulong g_cInterceptors
0x180007199  mov     [r14+10h], r12d
0x18000719d  mov     rcx, [rsp+530h+ppv]
0x1800071a2  mov     rax, [rcx]
0x1800071a5  mov     rdx, r14
0x1800071a8  mov     rax, [rax+38h]
0x1800071ac  call    cs:__guard_dispatch_icall_fptr
0x1800071b2  mov     r14d, eax
0x1800071b5  mov     [rsp+530h+var_500], eax
0x1800071b9  test    eax, eax
0x1800071bb  js      loc_18000748F
0x1800071c1  lfence
0x1800071c4  mov     rcx, [rsp+530h+ppv]
0x1800071c9  mov     rax, [rcx]
0x1800071cc  mov     r8, rdi
0x1800071cf  mov     rdx, rbx
0x1800071d2  mov     rax, [rax]
0x1800071d5  call    cs:__guard_dispatch_icall_fptr
0x1800071db  mov     r14d, eax
0x1800071de  mov     [rsp+530h+var_500], eax
0x1800071e2  jmp     loc_18000748F
0x1800071e7  lfence
0x1800071ea  mov     rax, [rbx]
0x1800071ed  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800071f4  jnz     short loc_180007269
0x1800071f6  mov     rax, [rbx+8]
0x1800071fa  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180007201  jnz     short loc_180007269
0x180007203  mov     [rdi], rsi
0x180007206  call    ?Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ; Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)
0x18000720b  mov     rsi, rax
0x18000720e  mov     rdi, [rdi]
0x180007211  test    rdi, rdi
0x180007214  jz      short loc_180007243
0x180007216  mov     rdi, [rdi]
0x180007219  mov     r15, [rdi]
0x18000721c  lea     rbx, [rax+40h]
0x180007220  mov     rcx, rbx; lpCriticalSection
0x180007223  call    cs:__imp_EnterCriticalSection
0x180007229  mov     rdx, rdi
0x18000722c  call    ?VtblMethodSwap@?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@IEAA_NPEA_KP6AJPEAXAEBU_GUID@@PEAPEAX@Z@Z; SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>::VtblMethodSwap(unsigned __int64 *,long (*)(void *,_GUID const &,void * *))
0x180007231  test    al, al
0x180007233  jnz     short loc_18000724D
0x180007235  call    ??$LogLineFormat@$0DA@@@YAXW4Severity@Logging@Mso@@AEAY0DA@$$CB_W@Z; LogLineFormat<48>(Mso::Logging::Severity,wchar_t const (&)[48])
0x18000723a  mov     rcx, rbx; lpCriticalSection
0x18000723d  call    cs:__imp_LeaveCriticalSection
0x180007243  call    ??$LogLineFormat@$0DB@@@YAXW4Severity@Logging@Mso@@AEAY0DB@$$CB_W@Z; LogLineFormat<49>(Mso::Logging::Severity,wchar_t const (&)[49])
0x180007248  jmp     loc_18000748F
0x18000724d  mov     rcx, rbx; lpCriticalSection
0x180007250  call    cs:__imp_LeaveCriticalSection
0x180007256  mov     r8, r15
0x180007259  mov     rdx, rdi
0x18000725c  mov     rcx, rsi
0x18000725f  call    ?insert@?$TSgMap@PEA_KP6AJPEAXAEBU_GUID@@PEAPEAX@Z@@QEAA_NPEA_KP6AJPEAXAEBU_GUID@@PEAPEAX@Z@Z; TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::insert(unsigned __int64 *,long (*)(void *,_GUID const &,void * *))
0x180007264  jmp     loc_18000748F
0x180007269  lfence
0x18000726c  mov     rax, [rbx]
0x18000726f  cmp     rax, qword ptr cs:IID_IPersistPropertyBag.Data1
0x180007276  jnz     short loc_1800072A5
0x180007278  mov     rax, [rbx+8]
0x18000727c  cmp     rax, qword ptr cs:IID_IPersistPropertyBag.Data4
0x180007283  jnz     short loc_1800072A5
0x180007285  mov     ecx, 10h; Size
0x18000728a  call    cs:__imp_malloc
0x180007290  test    rax, rax
0x180007293  jz      loc_1800074EC
0x180007299  lea     rcx, ??_7CInterceptorPersistPropertyBag@@6B@; const CInterceptorPersistPropertyBag::`vftable'
0x1800072a0  jmp     loc_18000738A
0x1800072a5  lfence
0x1800072a8  mov     rax, [rbx]
0x1800072ab  cmp     rax, qword ptr cs:_GUID_c73106ba_ac80_11d1_8df3_00c04fb6ef4f.Data1
0x1800072b2  jnz     short loc_1800072E1
0x1800072b4  mov     rax, [rbx+8]
0x1800072b8  cmp     rax, qword ptr cs:_GUID_c73106ba_ac80_11d1_8df3_00c04fb6ef4f.Data4
0x1800072bf  jnz     short loc_1800072E1
0x1800072c1  mov     ecx, 10h; Size
0x1800072c6  call    cs:__imp_malloc
0x1800072cc  test    rax, rax
0x1800072cf  jz      loc_1800074EC
0x1800072d5  lea     rcx, ??_7CInterceptorSearchProtocol@@6B@; const CInterceptorSearchProtocol::`vftable'
0x1800072dc  jmp     loc_18000738A
0x1800072e1  lfence
0x1800072e4  mov     rax, [rbx]
0x1800072e7  cmp     rax, qword ptr cs:_GUID_7789f0b2_b5b2_4722_8b65_5dbd150697a9.Data1
0x1800072ee  jnz     short loc_18000731A
0x1800072f0  mov     rax, [rbx+8]
0x1800072f4  cmp     rax, qword ptr cs:_GUID_7789f0b2_b5b2_4722_8b65_5dbd150697a9.Data4
0x1800072fb  jnz     short loc_18000731A
0x1800072fd  mov     ecx, 10h; Size
0x180007302  call    cs:__imp_malloc
0x180007308  test    rax, rax
0x18000730b  jz      loc_1800074EC
0x180007311  lea     rcx, ??_7CInterceptorSearchProtocol2@@6B@; const CInterceptorSearchProtocol2::`vftable'
0x180007318  jmp     short loc_18000738A
0x18000731a  lfence
0x18000731d  mov     rax, [rbx]
0x180007320  cmp     rax, qword ptr cs:_GUID_1c2056cc_5ef4_101b_8bc8_00aa003e3b29.Data1
0x180007327  jnz     short loc_180007353
0x180007329  mov     rax, [rbx+8]
0x18000732d  cmp     rax, qword ptr cs:_GUID_1c2056cc_5ef4_101b_8bc8_00aa003e3b29.Data4
0x180007334  jnz     short loc_180007353
0x180007336  mov     ecx, 10h; Size
0x18000733b  call    cs:__imp_malloc
0x180007341  test    rax, rax
0x180007344  jz      loc_1800074EC
0x18000734a  lea     rcx, ??_7CInterceptorOleInPlaceObjectWindowless@@6B@; const CInterceptorOleInPlaceObjectWindowless::`vftable'
0x180007351  jmp     short loc_18000738A
0x180007353  lfence
0x180007356  mov     rax, [rbx]
0x180007359  cmp     rax, qword ptr cs:_GUID_3050f425_98b5_11cf_bb82_00aa00bdce0b.Data1
0x180007360  jnz     short loc_1800073A0
0x180007362  mov     rax, [rbx+8]
0x180007366  cmp     rax, qword ptr cs:_GUID_3050f425_98b5_11cf_bb82_00aa00bdce0b.Data4
0x18000736d  jnz     short loc_1800073A0
0x18000736f  mov     ecx, 10h; Size
0x180007374  call    cs:__imp_malloc
0x18000737a  test    rax, rax
0x18000737d  jz      loc_1800074EC
0x180007383  lea     rcx, ??_7CIElementBehavior@@6B@; const CIElementBehavior::`vftable'
0x18000738a  mov     [rax], rcx
0x18000738d  mov     [rax+8], rsi
0x180007391  lock inc cs:?g_cInterceptors@@3KA; ulong g_cInterceptors
0x180007398  mov     [rdi], rax
0x18000739b  jmp     loc_18000748F
0x1800073a0  lfence
0x1800073a3  mov     [rsp+530h+lpsz], r12
0x1800073a8  lea     rdx, [rsp+530h+lpsz]; lplpsz
0x1800073ad  mov     rcx, rbx; rclsid
0x1800073b0  call    cs:__imp_StringFromIID
0x1800073b6  test    eax, eax
0x1800073b8  jnz     loc_18000748C
0x1800073be  mov     rax, [rsp+530h+lpsz]
0x1800073c3  mov     [rsp+530h+phkResult], rax
0x1800073c8  lea     r9, aInterfaceS; "Interface\\%s"
0x1800073cf  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800073d3  mov     edx, 104h; BufferCount
0x1800073d8  lea     rcx, [rbp+430h+Buffer]; Buffer
0x1800073df  call    _snwprintf_s
0x1800073e4  mov     [rbp+430h+var_440], r12w
0x1800073e9  xor     edx, edx; Val
0x1800073eb  mov     r8d, 1FEh; Size
0x1800073f1  lea     rcx, [rbp+430h+var_43E]; void *
0x1800073f5  call    memset
0x1800073fa  mov     [rsp+530h+var_4D8], r12d
0x1800073ff  mov     [rsp+530h+var_4D0], r12
0x180007404  mov     [rsp+530h+hKey], r12
0x180007409  lea     rax, [rsp+530h+hKey]
0x18000740e  mov     [rsp+530h+phkResult], rax; phkResult
0x180007413  mov     r9d, 20019h; samDesired
0x180007419  xor     r8d, r8d; ulOptions
0x18000741c  lea     rdx, [rbp+430h+Buffer]; lpSubKey
0x180007423  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000742a  call    cs:__imp_RegOpenKeyExW
0x180007430  mov     rbx, r12
0x180007433  test    eax, eax
0x180007435  cmovz   rbx, [rsp+530h+hKey]
0x18000743b  mov     [rsp+530h+var_4E0], rbx
0x180007440  mov     ecx, eax
0x180007442  neg     ecx
0x180007444  sbb     edx, edx; wchar_t *
0x180007446  test    eax, edx
0x180007448  jnz     short loc_180007465
0x18000744a  mov     dword ptr [rsp+530h+hKey], 100h
0x180007452  lea     r9, [rsp+530h+hKey]; unsigned int *
0x180007457  lea     r8, [rbp+430h+var_440]; wchar_t *
0x18000745b  lea     rcx, [rsp+530h+var_4E0]; this
0x180007460  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEB_WPEA_WPEAK@Z; ATL::CRegKey::QueryStringValue(wchar_t const *,wchar_t *,ulong *)
0x180007465  lea     r9, [rbp+430h+var_440]
0x180007469  lea     r8, [rsp+530h+lpsz]
0x18000746e  call    ??$LogLineFormat@$0ED@PEA_W$$BY0BAA@_W@@YAXW4Severity@Logging@Mso@@AEAY0ED@$$CB_WAEBQEA_WAEAY0BAA@$$CB_W@Z; LogLineFormat<67,wchar_t *,wchar_t [256]>(Mso::Logging::Severity,wchar_t const (&)[67],wchar_t * const &,wchar_t const (&)[256])
0x180007473  mov     rcx, [rsp+530h+lpsz]; pv
0x180007478  call    cs:__imp_CoTaskMemFree
0x18000747e  test    rbx, rbx
0x180007481  jz      short loc_18000748C
0x180007483  mov     rcx, rbx; hKey
0x180007486  call    cs:__imp_RegCloseKey
0x18000748c  mov     [rdi], rsi
0x18000748f  lea     r8, [rsp+530h+var_500]
0x180007494  test    r14d, r14d
0x180007497  js      short loc_1800074A0
0x180007499  call    ??$LogLineFormat@$0DA@J@@YAXW4Severity@Logging@Mso@@AEAY0DA@$$CB_WAEBJ@Z; LogLineFormat<48,long>(Mso::Logging::Severity,wchar_t const (&)[48],long const &)
0x18000749e  jmp     short loc_1800074A6
0x1800074a0  call    ??$LogLineFormat@$0DP@J@@YAXW4Severity@Logging@Mso@@AEAY0DP@$$CB_WAEBJ@Z; LogLineFormat<63,long>(Mso::Logging::Severity,wchar_t const (&)[63],long const &)
0x1800074a5  nop
0x1800074a6  mov     rcx, [rsp+530h+ppv]
0x1800074ab  test    rcx, rcx
0x1800074ae  jz      short loc_1800074BD
0x1800074b0  mov     rax, [rcx]
0x1800074b3  mov     rax, [rax+10h]
0x1800074b7  call    cs:__guard_dispatch_icall_fptr
0x1800074bd  mov     eax, [rsp+530h+var_500]
0x1800074c1  mov     rcx, [rbp+430h+var_30]
0x1800074c8  xor     rcx, rsp; StackCookie
0x1800074cb  call    __security_check_cookie
0x1800074d0  lea     r11, [rsp+530h+var_20]
0x1800074d8  mov     rbx, [r11+38h]
0x1800074dc  mov     rsi, [r11+48h]
0x1800074e0  mov     rsp, r11
0x1800074e3  pop     r15
0x1800074e5  pop     r14
0x1800074e7  pop     r12
0x1800074e9  pop     rdi
0x1800074ea  pop     rbp
0x1800074eb  retn
0x1800074ec  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800074f2  jmp     short $+2
0x1800074f4  nop
```
