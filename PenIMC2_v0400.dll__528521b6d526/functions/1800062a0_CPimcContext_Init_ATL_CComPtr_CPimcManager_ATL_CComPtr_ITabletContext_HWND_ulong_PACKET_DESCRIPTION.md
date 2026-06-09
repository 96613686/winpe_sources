# CPimcContext::Init(ATL::CComPtr<CPimcManager>,ATL::CComPtr<ITabletContext>,HWND__ *,ulong,_PACKET_DESCRIPTION *)

- ea: `0x1800062a0`
- end: `0x1800066b6`
- name: `?Init@CPimcContext@@QEAAJV?$CComPtr@VCPimcManager@@@ATL@@V?$CComPtr@UITabletContext@@@3@PEAUHWND__@@KPEAU_PACKET_DESCRIPTION@@@Z`
- size: `1046`
- prototype: `__int64 __usercall@<rax>(struct CPimcContext *@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800082f0`

## callees

- `0x180001360`
- `0x1800062a0`
- `0x1800066dc`
- `0x180006a28`
- `0x180007b24`
- `0x180007e24`
- `0x18000a8f0`
- `0x18000ada8`
- `0x18000b39c`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800065bc`
- `KERNEL32!DeleteCriticalSection` at `0x1800065bc`
- `KERNEL32!InitializeCriticalSection` at `0x180006418`
- `KERNEL32!InitializeCriticalSection` at `0x180006418`
- `KERNEL32!CreateEventW` at `0x180006428`
- `KERNEL32!CreateEventW` at `0x180006428`
- `KERNEL32!GetCurrentProcessId` at `0x1800064ee`
- `KERNEL32!GetCurrentProcessId` at `0x1800064ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CPimcContext::Init(struct CPimcContext *a1, _QWORD *a2, _QWORD *a3, HWND a4, int a5, __int64 a6)
{
  _QWORD *v7; // rdi
  char v9; // r15
  __int64 v10; // rbx
  CPimcManager *v11; // rcx
  _QWORD *v12; // rsi
  signed int inited; // ebx
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  struct _RTL_CRITICAL_SECTION *v17; // rsi
  HANDLE EventW; // rax
  CPimcManager *v19; // rbx
  __int64 v20; // r12
  DWORD CurrentProcessId; // eax
  CPimcManager *v22; // rcx
  __int64 v23; // rcx
  CPimcManager *v25; // [rsp+40h] [rbp-40h] BYREF
  CPimcManager *v26; // [rsp+48h] [rbp-38h] BYREF
  CPimcManager **v27; // [rsp+50h] [rbp-30h] BYREF
  int v28; // [rsp+58h] [rbp-28h]
  char v29; // [rsp+5Ch] [rbp-24h]
  char v30[32]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v31; // [rsp+C0h] [rbp+40h] BYREF
  _QWORD *v32; // [rsp+C8h] [rbp+48h]
  _QWORD *v33; // [rsp+D0h] [rbp+50h]

  v33 = a3;
  v32 = a2;
  v7 = a3;
  v9 = 0;
  LOBYTE(v31) = 0;
  v10 = *a2;
  if ( *((_QWORD *)a1 + 3) != *a2 )
  {
    v26 = (CPimcManager *)*a2;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v26 = (CPimcManager *)*((_QWORD *)a1 + 3);
    v11 = v26;
    *((_QWORD *)a1 + 3) = v10;
    if ( v11 )
      (*(void (__fastcall **)(CPimcManager *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( *v7 )
  {
    v12 = (_QWORD *)((char *)a1 + 32);
    inited = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v7)(*v7, &IID_ITabletContextP, (char *)a1 + 32);
    if ( inited < 0 )
      goto LABEL_35;
    v26 = (CPimcManager *)&v31;
    LODWORD(v27) = 1;
    BYTE4(v27) = 0;
    v28 = 0;
    v29 = 1;
    v14 = *v12;
    v31 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v15 = ComUtils::GitComLockableWrapper<ITabletContextP>::GitComLockableWrapper<ITabletContextP>(v30, &v31, &v27);
    *(_OWORD *)((char *)a1 + 296) = *(_OWORD *)v15;
    *((_DWORD *)a1 + 78) = *(_DWORD *)(v15 + 16);
    inited = *((_DWORD *)a1 + 74) == 0 ? 0x80004005 : 0;
    if ( !*((_DWORD *)a1 + 74) )
      goto LABEL_35;
    LOBYTE(v31) = 1;
    v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 256LL))(*v12);
    *((_DWORD *)a1 + 60) &= ~2u;
    *((_DWORD *)a1 + 60) |= v16 == 0 ? 2 : 0;
  }
  *((_DWORD *)a1 + 10) = a5;
  *((_QWORD *)a1 + 6) = a6;
  *((_DWORD *)a1 + 48) = 0;
  v17 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 200);
  InitializeCriticalSection((LPCRITICAL_SECTION)a1 + 5);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a1 + 23) = EventW;
  inited = EventW == 0 ? 0x80000301 : 0;
  if ( !EventW || (inited = CPimcManager::InstallWindowHook(*((CPimcManager **)a1 + 3), a4, a1), inited < 0) )
  {
LABEL_34:
    DeleteCriticalSection(v17);
    v9 = v31;
LABEL_35:
    SafeCloseHandle((void **)a1 + 23);
    if ( v9 && *((_DWORD *)a1 + 74) )
    {
      LODWORD(v31) = *((_DWORD *)a1 + 74);
      ATL::CComGITPtr<ITabletContextP>::Revoke(&v31);
      ATL::CComGITPtr<ITabletContextP>::Revoke(&v31);
    }
    if ( *((_QWORD *)a1 + 3) )
    {
      v31 = 0;
      v31 = *((_QWORD *)a1 + 3);
      v23 = v31;
      *((_QWORD *)a1 + 3) = 0;
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    *((_QWORD *)a1 + 6) = 0;
    if ( *v32 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 16LL))(*v32);
    goto LABEL_43;
  }
  if ( *v7 )
  {
    v25 = 0;
    inited = (***((__int64 (__fastcall ****)(_QWORD, GUID *, CPimcManager **))a1 + 4))(
               *((_QWORD *)a1 + 4),
               &IID_ITabletContextP,
               &v25);
    if ( inited < 0 )
    {
      if ( v25 )
        (*(void (__fastcall **)(CPimcManager *))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_33:
      CPimcManager::UninstallWindowHook(*((CPimcManager **)a1 + 3), a1);
      goto LABEL_34;
    }
    v27 = &v26;
    v26 = v25;
    if ( v25 )
      (*(void (__fastcall **)(CPimcManager *))(*(_QWORD *)v25 + 8LL))(v25);
    v27 = &v26;
    v19 = v26;
    v20 = *(_QWORD *)v26;
    CurrentProcessId = GetCurrentProcessId();
    inited = (*(__int64 (__fastcall **)(CPimcManager *, _QWORD, char *, char *, char *, char *))(v20 + 272))(
               v19,
               CurrentProcessId,
               (char *)a1 + 56,
               (char *)a1 + 64,
               (char *)a1 + 72,
               (char *)a1 + 80);
    if ( inited >= 0 )
      inited = CPimcContext::InitCommunicationsCore(a1);
    v22 = v26;
    if ( v26 )
      (*(void (__fastcall **)(CPimcManager *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( inited == -2147024891 )
    {
      if ( !(unsigned int)CPimcManager::IsVistaOrGreater(v22) )
      {
LABEL_30:
        if ( v25 )
          (*(void (__fastcall **)(CPimcManager *))(*(_QWORD *)v25 + 16LL))(v25);
        v17 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 200);
        v7 = v33;
        goto LABEL_33;
      }
      v27 = &v26;
      v26 = v25;
      if ( v25 )
        (*(void (__fastcall **)(CPimcManager *))(*(_QWORD *)v25 + 8LL))(v25);
      inited = CPimcContext::InitNamedCommunications(a1, (WCHAR *)&v26);
    }
    if ( inited < 0 )
      goto LABEL_30;
    if ( v25 )
      (*(void (__fastcall **)(CPimcManager *))(*(_QWORD *)v25 + 16LL))(v25);
    v7 = v33;
  }
  *((_DWORD *)a1 + 60) &= ~1u;
  *((_DWORD *)a1 + 61) = -1;
  if ( *v32 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 16LL))(*v32);
LABEL_43:
  if ( *v7 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800062a0  mov     [rsp-38h+arg_18], rbx
0x1800062a5  mov     [rsp-38h+arg_10], r8
0x1800062aa  mov     [rsp-38h+arg_8], rdx
0x1800062af  push    rbp
0x1800062b0  push    rsi
0x1800062b1  push    rdi
0x1800062b2  push    r12
0x1800062b4  push    r13
0x1800062b6  push    r14
0x1800062b8  push    r15
0x1800062ba  mov     rbp, rsp
0x1800062bd  sub     rsp, 80h
0x1800062c4  mov     r14, r9
0x1800062c7  mov     rdi, r8
0x1800062ca  mov     r13, rcx
0x1800062cd  xor     r12d, r12d
0x1800062d0  mov     r15b, r12b
0x1800062d3  mov     byte ptr [rbp+arg_0], r12b
0x1800062d7  mov     rbx, [rdx]
0x1800062da  cmp     [rcx+18h], rbx
0x1800062de  jz      short loc_180006318
0x1800062e0  mov     [rbp+var_38], rbx
0x1800062e4  test    rbx, rbx
0x1800062e7  jz      short loc_1800062FA
0x1800062e9  mov     rax, [rbx]
0x1800062ec  mov     rcx, rbx
0x1800062ef  mov     rax, [rax+8]
0x1800062f3  call    cs:__guard_dispatch_icall_fptr
0x1800062f9  nop
0x1800062fa  mov     rcx, [r13+18h]
0x1800062fe  mov     [rbp+var_38], rcx
0x180006302  mov     [r13+18h], rbx
0x180006306  test    rcx, rcx
0x180006309  jz      short loc_180006318
0x18000630b  mov     rax, [rcx]
0x18000630e  mov     rax, [rax+10h]
0x180006312  call    cs:__guard_dispatch_icall_fptr
0x180006318  mov     rcx, [rdi]
0x18000631b  test    rcx, rcx
0x18000631e  jz      loc_1800063F8
0x180006324  lea     rsi, [r13+20h]
0x180006328  mov     rax, [rcx]
0x18000632b  mov     r8, rsi
0x18000632e  lea     rdx, IID_ITabletContextP
0x180006335  mov     rax, [rax]
0x180006338  call    cs:__guard_dispatch_icall_fptr
0x18000633e  mov     ebx, eax
0x180006340  test    eax, eax
0x180006342  js      loc_1800065C6
0x180006348  lea     rax, [rbp+arg_0]
0x18000634c  mov     [rbp+var_38], rax
0x180006350  mov     dword ptr [rbp+var_30], 1
0x180006357  mov     byte ptr [rbp+var_30+4], r12b
0x18000635b  mov     dword ptr [rbp+var_30+8], r12d
0x18000635f  mov     byte ptr [rbp+var_30+0Ch], 1
0x180006363  movaps  xmm0, [rbp+var_30]
0x180006367  movdqa  [rbp+var_30], xmm0
0x18000636c  mov     rcx, [rsi]
0x18000636f  mov     [rbp+arg_0], rcx
0x180006373  test    rcx, rcx
0x180006376  jz      short loc_180006386
0x180006378  mov     rax, [rcx]
0x18000637b  mov     rax, [rax+8]
0x18000637f  call    cs:__guard_dispatch_icall_fptr
0x180006385  nop
0x180006386  lea     r8, [rbp+var_30]
0x18000638a  lea     rdx, [rbp+arg_0]
0x18000638e  lea     rcx, [rbp+var_20]
0x180006392  call    ??0?$GitComLockableWrapper@UITabletContextP@@@ComUtils@@QEAA@V?$CComPtr@UITabletContextP@@@ATL@@VComApartmentVerifier@1@@Z; ComUtils::GitComLockableWrapper<ITabletContextP>::GitComLockableWrapper<ITabletContextP>(ATL::CComPtr<ITabletContextP>,ComUtils::ComApartmentVerifier)
0x180006397  movups  xmm0, xmmword ptr [rax]
0x18000639a  movups  xmmword ptr [r13+128h], xmm0
0x1800063a2  mov     eax, [rax+10h]
0x1800063a5  mov     [r13+138h], eax
0x1800063ac  mov     ecx, [r13+128h]
0x1800063b3  mov     eax, ecx
0x1800063b5  neg     eax
0x1800063b7  sbb     ebx, ebx
0x1800063b9  not     ebx
0x1800063bb  and     ebx, 80004005h
0x1800063c1  test    ecx, ecx
0x1800063c3  jz      loc_1800065C6
0x1800063c9  mov     byte ptr [rbp+arg_0], 1
0x1800063cd  mov     rcx, [rsi]
0x1800063d0  mov     rax, [rcx]
0x1800063d3  mov     rax, [rax+100h]
0x1800063da  call    cs:__guard_dispatch_icall_fptr
0x1800063e0  and     dword ptr [r13+0F0h], 0FFFFFFFDh
0x1800063e8  neg     eax
0x1800063ea  sbb     eax, eax
0x1800063ec  not     eax
0x1800063ee  and     eax, 2
0x1800063f1  or      [r13+0F0h], eax
0x1800063f8  mov     eax, [rbp+arg_20]
0x1800063fb  mov     [r13+28h], eax
0x1800063ff  mov     rax, [rbp+arg_28]
0x180006403  mov     [r13+30h], rax
0x180006407  mov     [r13+0C0h], r12d
0x18000640e  lea     rsi, [r13+0C8h]
0x180006415  mov     rcx, rsi; lpCriticalSection
0x180006418  call    cs:__imp_InitializeCriticalSection
0x18000641e  xor     r9d, r9d; lpName
0x180006421  xor     r8d, r8d; bInitialState
0x180006424  xor     edx, edx; bManualReset
0x180006426  xor     ecx, ecx; lpEventAttributes
0x180006428  call    cs:__imp_CreateEventW
0x18000642e  mov     [r13+0B8h], rax
0x180006435  mov     rcx, rax
0x180006438  neg     rcx
0x18000643b  sbb     ebx, ebx
0x18000643d  not     ebx
0x18000643f  and     ebx, 80000301h
0x180006445  test    rax, rax
0x180006448  jz      loc_1800065B9
0x18000644e  mov     r8, r13; struct CPimcContext *
0x180006451  mov     rdx, r14; HWND
0x180006454  mov     rcx, [r13+18h]; this
0x180006458  call    ?InstallWindowHook@CPimcManager@@QEAAJPEAUHWND__@@PEAVCPimcContext@@@Z; CPimcManager::InstallWindowHook(HWND__ *,CPimcContext *)
0x18000645d  mov     ebx, eax
0x18000645f  test    eax, eax
0x180006461  js      loc_1800065B9
0x180006467  cmp     [rdi], r12
0x18000646a  jz      loc_18000668A
0x180006470  mov     [rbp+var_40], r12
0x180006474  mov     rcx, [r13+20h]
0x180006478  mov     rax, [rcx]
0x18000647b  lea     r8, [rbp+var_40]
0x18000647f  lea     rdx, IID_ITabletContextP
0x180006486  mov     rax, [rax]
0x180006489  call    cs:__guard_dispatch_icall_fptr
0x18000648f  mov     ebx, eax
0x180006491  test    eax, eax
0x180006493  jns     short loc_1800064B4
0x180006495  mov     rcx, [rbp+var_40]
0x180006499  test    rcx, rcx
0x18000649c  jz      loc_1800065AD
0x1800064a2  mov     rax, [rcx]
0x1800064a5  mov     rax, [rax+10h]
0x1800064a9  call    cs:__guard_dispatch_icall_fptr
0x1800064af  jmp     loc_1800065AD
0x1800064b4  lea     rax, [rbp+var_38]
0x1800064b8  mov     qword ptr [rbp+var_30], rax
0x1800064bc  mov     rcx, [rbp+var_40]
0x1800064c0  mov     [rbp+var_38], rcx
0x1800064c4  test    rcx, rcx
0x1800064c7  jz      short loc_1800064D7
0x1800064c9  mov     rax, [rcx]
0x1800064cc  mov     rax, [rax+8]
0x1800064d0  call    cs:__guard_dispatch_icall_fptr
0x1800064d6  nop
0x1800064d7  lea     rax, [rbp+var_38]
0x1800064db  mov     qword ptr [rbp+var_30], rax
0x1800064df  mov     rbx, [rbp+var_38]
0x1800064e3  mov     r12, [rbx]
0x1800064e6  lea     rdi, [r13+50h]
0x1800064ea  lea     rsi, [r13+48h]
0x1800064ee  call    cs:__imp_GetCurrentProcessId
0x1800064f4  mov     edx, eax
0x1800064f6  mov     [rsp+80h+var_58], rdi
0x1800064fb  mov     [rsp+80h+var_60], rsi
0x180006500  lea     r9, [r13+40h]
0x180006504  lea     r8, [r13+38h]
0x180006508  mov     rcx, rbx
0x18000650b  mov     rax, [r12+110h]
0x180006513  call    cs:__guard_dispatch_icall_fptr
0x180006519  mov     ebx, eax
0x18000651b  xor     r12d, r12d
0x18000651e  test    eax, eax
0x180006520  js      short loc_18000652C
0x180006522  mov     rcx, r13; this
0x180006525  call    ?InitCommunicationsCore@CPimcContext@@QEAAJXZ; CPimcContext::InitCommunicationsCore(void)
0x18000652a  mov     ebx, eax
0x18000652c  mov     rcx, [rbp+var_38]
0x180006530  test    rcx, rcx
0x180006533  jz      short loc_180006542
0x180006535  mov     rax, [rcx]
0x180006538  mov     rax, [rax+10h]
0x18000653c  call    cs:__guard_dispatch_icall_fptr
0x180006542  cmp     ebx, 80070005h
0x180006548  jnz     short loc_180006584
0x18000654a  call    ?IsVistaOrGreater@CPimcManager@@QEAAHXZ; CPimcManager::IsVistaOrGreater(void)
0x18000654f  test    eax, eax
0x180006551  jz      short loc_18000658C
0x180006553  lea     rax, [rbp+var_38]
0x180006557  mov     qword ptr [rbp+var_30], rax
0x18000655b  mov     rcx, [rbp+var_40]
0x18000655f  mov     [rbp+var_38], rcx
0x180006563  test    rcx, rcx
0x180006566  jz      short loc_180006576
0x180006568  mov     rax, [rcx]
0x18000656b  mov     rax, [rax+8]
0x18000656f  call    cs:__guard_dispatch_icall_fptr
0x180006575  nop
0x180006576  lea     rdx, [rbp+var_38]
0x18000657a  mov     rcx, r13; this
0x18000657d  call    ?InitNamedCommunications@CPimcContext@@QEAAJV?$CComPtr@UITabletContextP@@@ATL@@@Z; CPimcContext::InitNamedCommunications(ATL::CComPtr<ITabletContextP>)
0x180006582  mov     ebx, eax
0x180006584  test    ebx, ebx
0x180006586  jns     loc_180006670
0x18000658c  mov     rcx, [rbp+var_40]
0x180006590  test    rcx, rcx
0x180006593  jz      short loc_1800065A2
0x180006595  mov     rax, [rcx]
0x180006598  mov     rax, [rax+10h]
0x18000659c  call    cs:__guard_dispatch_icall_fptr
0x1800065a2  lea     rsi, [r13+0C8h]
0x1800065a9  mov     rdi, [rbp+arg_10]
0x1800065ad  mov     rdx, r13; struct CPimcContext *
0x1800065b0  mov     rcx, [r13+18h]; this
0x1800065b4  call    ?UninstallWindowHook@CPimcManager@@QEAAJPEAVCPimcContext@@@Z; CPimcManager::UninstallWindowHook(CPimcContext *)
0x1800065b9  mov     rcx, rsi; lpCriticalSection
0x1800065bc  call    cs:__imp_DeleteCriticalSection
0x1800065c2  mov     r15b, byte ptr [rbp+arg_0]
0x1800065c6  lea     rcx, [r13+0B8h]; void **
0x1800065cd  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x1800065d2  test    r15b, r15b
0x1800065d5  jz      short loc_1800065F8
0x1800065d7  mov     eax, [r13+128h]
0x1800065de  test    eax, eax
0x1800065e0  jz      short loc_1800065F8
0x1800065e2  mov     dword ptr [rbp+arg_0], eax
0x1800065e5  lea     rcx, [rbp+arg_0]
0x1800065e9  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x1800065ee  nop
0x1800065ef  lea     rcx, [rbp+arg_0]
0x1800065f3  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x1800065f8  cmp     [r13+18h], r12
0x1800065fc  jz      short loc_180006620
0x1800065fe  mov     [rbp+arg_0], r12
0x180006602  mov     rcx, [r13+18h]
0x180006606  mov     [rbp+arg_0], rcx
0x18000660a  mov     [r13+18h], r12
0x18000660e  test    rcx, rcx
0x180006611  jz      short loc_180006620
0x180006613  mov     rax, [rcx]
0x180006616  mov     rax, [rax+10h]
0x18000661a  call    cs:__guard_dispatch_icall_fptr
0x180006620  mov     [r13+30h], r12
0x180006624  mov     rcx, [rbp+arg_8]
0x180006628  mov     rcx, [rcx]
0x18000662b  test    rcx, rcx
0x18000662e  jz      short loc_18000663E
0x180006630  mov     rax, [rcx]
0x180006633  mov     rax, [rax+10h]
0x180006637  call    cs:__guard_dispatch_icall_fptr
0x18000663d  nop
0x18000663e  mov     rcx, [rdi]
0x180006641  test    rcx, rcx
0x180006644  jz      short loc_180006653
0x180006646  mov     rax, [rcx]
0x180006649  mov     rax, [rax+10h]
0x18000664d  call    cs:__guard_dispatch_icall_fptr
0x180006653  mov     eax, ebx
0x180006655  mov     rbx, [rsp+80h+arg_18]
0x18000665d  add     rsp, 80h
0x180006664  pop     r15
0x180006666  pop     r14
0x180006668  pop     r13
0x18000666a  pop     r12
0x18000666c  pop     rdi
0x18000666d  pop     rsi
0x18000666e  pop     rbp
0x18000666f  retn
0x180006670  mov     rcx, [rbp+var_40]
0x180006674  test    rcx, rcx
0x180006677  jz      short loc_180006686
0x180006679  mov     rax, [rcx]
0x18000667c  mov     rax, [rax+10h]
0x180006680  call    cs:__guard_dispatch_icall_fptr
0x180006686  mov     rdi, [rbp+arg_10]
0x18000668a  and     dword ptr [r13+0F0h], 0FFFFFFFEh
0x180006692  or      dword ptr [r13+0F4h], 0FFFFFFFFh
0x18000669a  mov     rcx, [rbp+arg_8]
0x18000669e  mov     rcx, [rcx]
0x1800066a1  test    rcx, rcx
0x1800066a4  jz      short loc_1800066B4
0x1800066a6  mov     rax, [rcx]
0x1800066a9  mov     rax, [rax+10h]
0x1800066ad  call    cs:__guard_dispatch_icall_fptr
0x1800066b3  nop
0x1800066b4  jmp     short loc_18000663E
```
