# FiringAgent::CreateEventInterceptor(ITypeInfo * *)

- ea: `0x18000685c`
- end: `0x180006afe`
- name: `?CreateEventInterceptor@FiringAgent@@AEAAPEAVEventInterface@@PEAPEAUITypeInfo@@@Z`
- size: `674`
- prototype: `struct EventInterface *(FiringAgent *__hidden this, struct ITypeInfo **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001cdfc`

## callees

- `0x180003d54`
- `0x18000685c`
- `0x180006b10`
- `0x180007b90`
- `0x180008938`
- `0x180012654`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000690c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000690c`
- `ole32!CoGetInterceptorFromTypeInfo` at `0x1800068c2`
- `ole32!CoGetInterceptorFromTypeInfo` at `0x1800068c2`

## string_xrefs

- `0x1800068ce`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
struct EventInterface *__fastcall FiringAgent::CreateEventInterceptor(FiringAgent *this, struct ITypeInfo **a2)
{
  ITypeInfo *v4; // r8
  IUnknown *v5; // rdx
  HRESULT InterceptorFromTypeInfo; // eax
  int v7; // eax
  char *v8; // rax
  EventInterface *v9; // rdi
  struct ITypeInfo *v10; // rcx
  __int64 (__fastcall ***v11)(void *, IID *, __int64); // rbx
  _QWORD *v12; // r14
  IID v13; // xmm0
  int v14; // eax
  int v15; // eax
  struct ITypeInfo *v16; // rcx
  int v17; // eax
  void *ppv; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  struct tagTYPEATTR *v21; // [rsp+40h] [rbp-20h] BYREF
  IID iidIntercepted; // [rsp+48h] [rbp-18h] BYREF

  iidIntercepted = 0;
  ResolveTypeInfo(a2, &iidIntercepted);
  v4 = *a2;
  v5 = (IUnknown *)*((_QWORD *)this + 23);
  ppv = 0;
  InterceptorFromTypeInfo = CoGetInterceptorFromTypeInfo(&iidIntercepted, v5, v4, &IID_IUnknown, &ppv);
  if ( InterceptorFromTypeInfo < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1722u, 0x12u, InterceptorFromTypeInfo);
  v20 = 0;
  v7 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(ppv, &IID_ICallInterceptor, &v20);
  if ( v7 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1727u, 0x12u, v7);
  v8 = (char *)CoTaskMemAlloc(0x50u);
  v9 = (EventInterface *)v8;
  if ( v8 )
  {
    v10 = *a2;
    v11 = (__int64 (__fastcall ***)(void *, IID *, __int64))ppv;
    *(_QWORD *)v8 = &EventInterface::`vftable'{for `ICallFrameEvents'};
    *((_QWORD *)v8 + 2) = this;
    v12 = v8 + 24;
    *((_QWORD *)v8 + 1) = &EventInterface::`vftable'{for `IDispatch'};
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = v11;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v13 = iidIntercepted;
    *((_QWORD *)v8 + 9) = v10;
    *(IID *)(v8 + 56) = v13;
    ((void (__fastcall *)(struct ITypeInfo *))v10->lpVtbl->AddRef)(v10);
    v14 = (**v11)(v11, &iidIntercepted, (__int64)v9 + 24);
    if ( v14 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x5E6u, 0x12u, v14);
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 16LL))(*v12) )
      InternalAssert(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x5EAu, 0x12u, L"refs != 0");
  }
  else
  {
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x172Eu, 0xC0001204, 0x12u);
    v9 = 0;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, EventInterface *))(*(_QWORD *)v20 + 56LL))(v20, v9);
  if ( v15 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1732u, 0x12u, v15);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v16 = *a2;
  v21 = 0;
  v17 = ((__int64 (__fastcall *)(struct ITypeInfo *, struct tagTYPEATTR **))v16->lpVtbl->GetTypeAttr)(v16, &v21);
  if ( v17 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1738u, 0x12u, v17);
  EventInterface::GetMethodInfo(v9, *a2, v21, 0, 0);
  ((void (__fastcall *)(_QWORD, struct tagTYPEATTR *))(*a2)->lpVtbl->ReleaseTypeAttr)(*a2, v21);
  return v9;
}

```

## disassembly

```asm
0x18000685c  mov     [rsp-28h+arg_10], rbx
0x180006861  mov     [rsp-28h+arg_18], rsi
0x180006866  push    rbp
0x180006867  push    rdi
0x180006868  push    r12
0x18000686a  push    r13
0x18000686c  push    r14
0x18000686e  mov     rbp, rsp
0x180006871  sub     rsp, 60h
0x180006875  mov     rax, cs:__security_cookie
0x18000687c  xor     rax, rsp
0x18000687f  mov     [rbp+var_8], rax
0x180006883  mov     rsi, rdx
0x180006886  mov     r14, rcx
0x180006889  xorps   xmm0, xmm0
0x18000688c  lea     rdx, [rbp+iidIntercepted]; struct _GUID *
0x180006890  mov     rcx, rsi; struct ITypeInfo **
0x180006893  movups  xmmword ptr [rbp+iidIntercepted.Data1], xmm0
0x180006897  call    ?ResolveTypeInfo@@YAXPEAPEAUITypeInfo@@PEAU_GUID@@@Z; ResolveTypeInfo(ITypeInfo * *,_GUID *)
0x18000689c  mov     r8, [rsi]; typeInfo
0x18000689f  lea     rax, [rbp+var_30]
0x1800068a3  mov     rdx, [r14+0B8h]; punkOuter
0x1800068aa  lea     r9, IID_IUnknown; iid
0x1800068b1  lea     rcx, [rbp+iidIntercepted]; iidIntercepted
0x1800068b5  mov     [rsp+60h+ppv], rax; ppv
0x1800068ba  mov     [rbp+var_30], 0
0x1800068c2  call    cs:__imp_CoGetInterceptorFromTypeInfo
0x1800068c8  mov     r12d, 12h
0x1800068ce  lea     r13, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x1800068d5  test    eax, eax
0x1800068d7  js      loc_180006A9A
0x1800068dd  mov     rcx, [rbp+var_30]
0x1800068e1  lea     r8, [rbp+var_28]
0x1800068e5  mov     [rbp+var_28], 0
0x1800068ed  lea     rdx, IID_ICallInterceptor
0x1800068f4  mov     rax, [rcx]
0x1800068f7  mov     rax, [rax]
0x1800068fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ff  test    eax, eax
0x180006901  js      loc_180006AB2
0x180006907  mov     ecx, 50h ; 'P'; cb
0x18000690c  call    cs:__imp_CoTaskMemAlloc
0x180006912  mov     rdi, rax
0x180006915  test    rax, rax
0x180006918  jz      loc_180006A4D
0x18000691e  mov     rcx, [rsi]
0x180006921  lea     rax, ??_7EventInterface@@6BICallFrameEvents@@@; const EventInterface::`vftable'{for `ICallFrameEvents'}
0x180006928  mov     rbx, [rbp+var_30]
0x18000692c  mov     [rdi], rax
0x18000692f  lea     rax, ??_7EventInterface@@6BIDispatch@@@; const EventInterface::`vftable'{for `IDispatch'}
0x180006936  mov     [rdi+10h], r14
0x18000693a  lea     r14, [rdi+18h]
0x18000693e  mov     [rdi+8], rax
0x180006942  mov     qword ptr [r14], 0
0x180006949  mov     [rdi+20h], rbx
0x18000694d  mov     qword ptr [rdi+28h], 0
0x180006955  mov     qword ptr [rdi+30h], 0
0x18000695d  movups  xmm0, xmmword ptr [rbp+iidIntercepted.Data1]
0x180006961  mov     [rdi+48h], rcx
0x180006965  movdqu  xmmword ptr [rdi+38h], xmm0
0x18000696a  mov     rax, [rcx]
0x18000696d  mov     rax, [rax+8]
0x180006971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006976  mov     rax, [rbx]
0x180006979  lea     rdx, [rbp+iidIntercepted]
0x18000697d  mov     r8, r14
0x180006980  mov     rcx, rbx
0x180006983  mov     rax, [rax]
0x180006986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000698b  test    eax, eax
0x18000698d  js      loc_180006A6A
0x180006993  mov     rcx, [r14]
0x180006996  mov     rax, [rcx]
0x180006999  mov     rax, [rax+10h]
0x18000699d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069a2  test    eax, eax
0x1800069a4  jz      loc_180006AE2
0x1800069aa  mov     rcx, [rbp+var_28]
0x1800069ae  mov     rdx, rdi
0x1800069b1  mov     rax, [rcx]
0x1800069b4  mov     rax, [rax+38h]
0x1800069b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069bd  test    eax, eax
0x1800069bf  js      loc_180006A82
0x1800069c5  mov     rcx, [rbp+var_28]
0x1800069c9  mov     rax, [rcx]
0x1800069cc  mov     rax, [rax+10h]
0x1800069d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d5  mov     rcx, [rsi]
0x1800069d8  lea     rdx, [rbp+var_20]
0x1800069dc  mov     [rbp+var_20], 0
0x1800069e4  mov     rax, [rcx]
0x1800069e7  mov     rax, [rax+18h]
0x1800069eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f0  test    eax, eax
0x1800069f2  js      loc_180006ACA
0x1800069f8  mov     r8, [rbp+var_20]; struct tagTYPEATTR *
0x1800069fc  xor     r9d, r9d; unsigned __int16
0x1800069ff  mov     rdx, [rsi]; struct ITypeInfo *
0x180006a02  mov     rcx, rdi; this
0x180006a05  mov     [rsp+60h+ppv], r9; struct DescendentInterface *
0x180006a0a  call    ?GetMethodInfo@EventInterface@@QEAAGPEAUITypeInfo@@PEAUtagTYPEATTR@@GPEAVDescendentInterface@@@Z; EventInterface::GetMethodInfo(ITypeInfo *,tagTYPEATTR *,ushort,DescendentInterface *)
0x180006a0f  mov     rcx, [rsi]
0x180006a12  mov     rdx, [rcx]
0x180006a15  mov     rax, [rdx+98h]
0x180006a1c  mov     rdx, [rbp+var_20]
0x180006a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a25  mov     rax, rdi
0x180006a28  mov     rcx, [rbp+var_8]
0x180006a2c  xor     rcx, rsp; StackCookie
0x180006a2f  call    __security_check_cookie
0x180006a34  lea     r11, [rsp+60h+var_s0]
0x180006a39  mov     rbx, [r11+40h]
0x180006a3d  mov     rsi, [r11+48h]
0x180006a41  mov     rsp, r11
0x180006a44  pop     r14
0x180006a46  pop     r13
0x180006a48  pop     r12
0x180006a4a  pop     rdi
0x180006a4b  pop     rbp
0x180006a4c  retn
0x180006a4d  mov     r9d, r12d; unsigned __int16
0x180006a50  mov     edx, 172Eh; unsigned int
0x180006a55  mov     r8d, 0C0001204h; unsigned int
0x180006a5b  mov     rcx, r13; unsigned __int16 *
0x180006a5e  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180006a63  xor     edi, edi
0x180006a65  jmp     loc_1800069AA
0x180006a6a  mov     r8d, r12d; unsigned __int16
0x180006a6d  mov     r9d, eax; int
0x180006a70  mov     edx, 5E6h; unsigned int
0x180006a75  mov     rcx, r13; unsigned __int16 *
0x180006a78  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180006a7d  jmp     loc_180006993
0x180006a82  mov     r8d, r12d; unsigned __int16
0x180006a85  mov     r9d, eax; int
0x180006a88  mov     edx, 1732h; unsigned int
0x180006a8d  mov     rcx, r13; unsigned __int16 *
0x180006a90  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180006a95  jmp     loc_1800069C5
0x180006a9a  mov     r8d, r12d; unsigned __int16
0x180006a9d  mov     r9d, eax; int
0x180006aa0  mov     edx, 1722h; unsigned int
0x180006aa5  mov     rcx, r13; unsigned __int16 *
0x180006aa8  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180006aad  jmp     loc_1800068DD
0x180006ab2  mov     r8d, r12d; unsigned __int16
0x180006ab5  mov     r9d, eax; int
0x180006ab8  mov     edx, 1727h; unsigned int
0x180006abd  mov     rcx, r13; unsigned __int16 *
0x180006ac0  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180006ac5  jmp     loc_180006907
0x180006aca  mov     r8d, r12d; unsigned __int16
0x180006acd  mov     r9d, eax; int
0x180006ad0  mov     edx, 1738h; unsigned int
0x180006ad5  mov     rcx, r13; unsigned __int16 *
0x180006ad8  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180006add  jmp     loc_1800069F8
0x180006ae2  mov     r8d, r12d; unsigned __int16
0x180006ae5  lea     r9, aRefs0; "refs != 0"
0x180006aec  mov     edx, 5EAh; unsigned int
0x180006af1  mov     rcx, r13; unsigned __int16 *
0x180006af4  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180006af9  jmp     loc_1800069AA
```
