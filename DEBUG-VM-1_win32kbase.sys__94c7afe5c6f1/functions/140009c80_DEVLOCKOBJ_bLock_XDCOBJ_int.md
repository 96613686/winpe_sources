# DEVLOCKOBJ::bLock(XDCOBJ &,int)

- ea: `0x140009c80`
- end: `0x14000a347`
- name: `?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z`
- size: `1735`
- prototype: `__int64 __fastcall(DEVLOCKOBJ *__hidden this, struct XDCOBJ *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400098f0`

## callees

- `0x140009c80`
- `0x14000fe44`
- `0x140013c60`
- `0x140013d3c`
- `0x140013ff0`
- `0x14001c648`
- `0x14001c970`
- `0x14001cb70`
- `0x14001d3b4`
- `0x14001d48c`
- `0x14001f570`
- `0x14002ae90`
- `0x14003ecb0`
- `0x140093cf0`
- `0x1400af6a0`
- `0x1400af714`
- `0x1400efc40`
- `0x14010f2b0`
- `0x140190650`
- `0x1401e2720`
- `0x1401e5f34`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140009ddb`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140009ddb`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009da1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009ea2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009ed9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009f0e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009f84`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009fbb`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009da1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009ea2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009ed9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009f0e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009f84`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140009fbb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140009cd0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140009cf5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140009cd0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140009cf5`

## pseudocode

```c
__int64 __fastcall DEVLOCKOBJ::bLock(DEVLOCKOBJ *this, struct XDCOBJ *a2, int a3)
{
  int (*v6)(void); // rax
  __int64 (__fastcall *v7)(struct XDCOBJ *, char *, char *, char *); // rax
  int v8; // eax
  __int64 result; // rax
  __int64 v10; // rdi
  int v11; // r12d
  _QWORD *v12; // rax
  __int64 v13; // rdx
  bool v14; // zf
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // edx
  _QWORD *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // edx
  struct _GRETHREAD *CurrentThread; // rax
  struct _GRETHREAD *v39; // rbp
  HSEMAPHORE v40; // r15
  struct _GRETHREAD *v41; // rax
  int v42; // ecx
  __int64 v43; // r8
  struct _GRETHREAD *v44; // r14
  int v45; // edx
  unsigned __int64 i; // rcx
  int v47; // eax
  struct _GRETHREAD *v48; // rax
  int v49; // ecx
  bool v50; // cc
  __int64 v51; // rcx
  SURFACE *v52; // rcx
  __int64 v53; // [rsp+70h] [rbp+8h] BYREF

  *((_DWORD *)this + 6) = 1;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = **(_QWORD **)a2;
  if ( a3 )
  {
    DEVLOCKOBJ::bPrepareTrgDco(this, 0);
    if ( a3 == 1 )
      *((_DWORD *)this + 6) |= 0x20000u;
  }
  else
  {
    v6 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2032LL);
    if ( !v6
      || v6() < 0
      || ((v7 = *(__int64 (__fastcall **)(struct XDCOBJ *, char *, char *, char *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable()
                                                                                              + 24)
                                                                                  + 2040LL)) == 0
        ? (v8 = 0)
        : (v8 = v7(a2, (char *)this + 144, (char *)this + 136, (char *)this + 28)),
          v8 != 1) )
    {
      *((_DWORD *)this + 6) &= ~1u;
      return 0;
    }
    DEVLOCKOBJ::bPrepareTrgDco(this, 0);
  }
  v10 = *((_QWORD *)a2 + 2);
  v11 = 0;
  if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) == 0 )
  {
    CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
    if ( !CurrentThreadWin32Thread )
      goto LABEL_59;
    v29 = 0;
    v14 = *CurrentThreadWin32Thread == 0;
    v30 = *CurrentThreadWin32Thread + 8LL;
    if ( !v14 )
      v29 = v30;
    if ( !v29 || !*(_DWORD *)(v29 + 340) )
    {
LABEL_59:
      *((_DWORD *)this + 6) |= 0x80000u;
      v31 = (_QWORD *)PsGetCurrentThreadWin32Thread();
      if ( v31 )
      {
        v32 = 0;
        v14 = *v31 == 0;
        v33 = *v31 + 8LL;
        if ( !v14 )
          v32 = v33;
        if ( v32 )
          ++*(_DWORD *)(v32 + 340);
      }
    }
    goto LABEL_64;
  }
  *((_QWORD *)this + 1) = *(_QWORD *)v10 + 624LL;
  GreAcquireSemaphoreShared<1,>(v10);
  *((_DWORD *)this + 6) |= 8u;
  v12 = (_QWORD *)PsGetCurrentThreadWin32Thread();
  if ( !v12 )
    goto LABEL_141;
  v13 = 0;
  v14 = *v12 == 0;
  v15 = *v12 + 8LL;
  if ( !v14 )
    v13 = v15;
  if ( !v13 || !*(_DWORD *)(v13 + 340) )
  {
LABEL_141:
    if ( !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)v10 + 1144LL)) )
    {
      GreAcquireSemaphoreShared<2,>(v10);
      v11 = 1;
    }
  }
  v16 = *(_QWORD *)a2;
  v53 = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
  if ( (**(_DWORD **)(v16 + 976) & 1) != 0 || (*(_DWORD *)(v16 + 36) & 0x8000) != 0 )
  {
    if ( (unsigned int)PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v53) )
      goto LABEL_33;
    v16 = *(_QWORD *)a2;
  }
  v17 = *(_QWORD *)(v16 + 64);
  *(_QWORD *)this = v17;
  *((_QWORD *)this + 2) = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
  if ( v11 == 1 && v17 == *(_QWORD *)v10 + 1144LL )
  {
    GreReleaseSemaphoreShared<2,>(v10);
    v11 = 0;
  }
  if ( *(_QWORD *)this == *(_QWORD *)v10 + 1144LL )
  {
    *((_DWORD *)this + 6) |= 0x100000u;
    GreAcquireSemaphore<2,>(v10);
  }
  else
  {
    GreAcquireSemaphore<8,PDEVOBJ>(*((_QWORD *)this + 2));
  }
  v18 = *((_DWORD *)this + 6);
  if ( (v18 & 0x200) == 0 && (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x4000) != 0 )
    *((_DWORD *)this + 6) = v18 | 0x200;
LABEL_33:
  v19 = (_QWORD *)PsGetCurrentThreadWin32Thread();
  if ( !v19 )
    goto LABEL_38;
  v20 = 0;
  v14 = *v19 == 0;
  v21 = *v19 + 8LL;
  if ( !v14 )
    v20 = v21;
  if ( !v20 || !*(_DWORD *)(v20 + 340) )
  {
LABEL_38:
    *((_DWORD *)this + 6) |= 0x1000u;
    v22 = (_QWORD *)PsGetCurrentThreadWin32Thread();
    if ( v22 )
    {
      v23 = 0;
      v14 = *v22 == 0;
      v24 = *v22 + 8LL;
      if ( !v14 )
        v23 = v24;
      if ( v23 )
      {
        *(_QWORD *)(v23 + 304) = 0;
        *(_QWORD *)(v23 + 296) = 0;
      }
    }
    v25 = (_QWORD *)PsGetCurrentThreadWin32Thread();
    if ( v25 )
    {
      v26 = 0;
      v14 = *v25 == 0;
      v27 = *v25 + 8LL;
      if ( !v14 )
        v26 = v27;
      if ( v26 )
        ++*(_DWORD *)(v26 + 340);
    }
    GreAcquireSemaphoreShared<3,>(v10);
  }
  if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x5000) == 0x1000 )
  {
    if ( (*((_DWORD *)this + 6) & 0x1000) != 0 )
      GreReleaseSemaphoreShared<3,>(v10);
    if ( v11 )
    {
LABEL_76:
      GreReleaseSemaphoreShared<2,>(v10);
      *((_DWORD *)this + 6) &= ~1u;
      return 0;
    }
    goto LABEL_138;
  }
LABEL_64:
  if ( (*((_DWORD *)this + 6) & 0x1000) != 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x80000) != 0 )
    {
      if ( *((_QWORD *)this + 1) )
        GreReleaseSemaphoreShared<3,>(v10);
      if ( v11 )
        goto LABEL_76;
      goto LABEL_138;
    }
  }
  else if ( *((_QWORD *)this + 1) )
  {
    goto LABEL_77;
  }
  if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x10) != 0 && !(unsigned int)DC::bCompute(*(DC **)a2) )
  {
    if ( *((_QWORD *)this + 1) )
      GreReleaseSemaphoreShared<3,>(v10);
    if ( v11 )
      goto LABEL_76;
    goto LABEL_138;
  }
LABEL_77:
  v34 = *(_QWORD *)a2;
  if ( *(_QWORD *)(*(_QWORD *)a2 + 1168LL)
    && (*(_DWORD *)(v34 + 40) & 2) != 0
    && (v35 = *(_QWORD *)(v34 + 496)) != 0
    && (*(_DWORD *)(v35 + 164) & 0x800) != 0
    || *(_QWORD *)(v34 + 1152)
    || *(_QWORD *)(v34 + 1160)
    && (*(_DWORD *)(v34 + 40) & 2) != 0
    && (v36 = *(_QWORD *)(v34 + 496)) != 0
    && (*(_DWORD *)(v36 + 164) & 0x800) != 0
    || *(_QWORD *)(v34 + 1144) )
  {
    v37 = *((_DWORD *)this + 6);
    if ( (v37 & 0x20000) == 0 && (*(_DWORD *)(v34 + 36) & 0x200) != 0 && (v37 & 0x1000) != 0 )
    {
      if ( !*((_QWORD *)this + 17) )
        DC::vSetRendering((DC *)v34);
      CurrentThread = GreGetCurrentThread();
      v39 = CurrentThread;
      if ( CurrentThread )
      {
        *((_QWORD *)CurrentThread + 37) = *(_QWORD *)a2;
        if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x4000) == 0 )
        {
          *((_DWORD *)CurrentThread + 84) |= 1u;
          *(_QWORD *)(*(_QWORD *)a2 + 1976LL) = 0;
          v40 = (HSEMAPHORE)(*(_QWORD *)v10 + 832LL);
          EngAcquireSemaphoreShared(v40);
          v41 = GreGetCurrentThreadCrossSessionCheck();
          v44 = v41;
          if ( v41 )
          {
            v43 = *(_QWORD *)v41;
            if ( (*(_QWORD *)v41 & 0xFFFFFFDFFFFFC000uLL) != 0 && (v43 & 0x4000) == 0 )
            {
              v45 = 38;
              for ( i = 0; i < 0x40; ++i )
              {
                v47 = i;
                if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v43) == 0 )
                  v47 = v45;
                v45 = v47;
              }
              if ( v47 > 14 && v47 != 38 )
                MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v47);
            }
            v42 = *((unsigned __int8 *)v44 + 22);
            *((_BYTE *)v44 + 22) = v42 + 1;
            if ( !(_BYTE)v42 )
              *(_QWORD *)v44 |= 0x4000uLL;
          }
          v14 = LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) == 0;
          *((_DWORD *)v39 + 87) = *(_DWORD *)(v10 + 4392);
          if ( !v14 && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
            McTemplateK0pz_EtwWriteTransfer(
              v42,
              (unsigned int)&LockRelease,
              v43,
              (_DWORD)v40,
              (__int64)L"VisRgnUniqueness");
          v48 = GreGetCurrentThreadCrossSessionCheck();
          if ( v48 )
          {
            v14 = (*((_BYTE *)v48 + 22))-- == 1;
            if ( v14 )
              *(_QWORD *)v48 &= ~0x4000uLL;
          }
          GreReleaseSemaphoreSharedInternal(v40);
        }
      }
    }
    if ( *((_QWORD *)this + 1) && (*((_DWORD *)this + 6) & 0x1000) != 0 )
      GreReleaseSemaphoreShared<3,>(v10);
    if ( v11 )
      GreReleaseSemaphoreShared<2,>(v10);
    if ( (*((_DWORD *)this + 6) & 0x20000) == 0 )
    {
      result = DEVLOCKOBJ::bPrepareTrgDco(this, a2);
      v49 = *((_DWORD *)this + 6);
      if ( !(_DWORD)result )
      {
        *((_DWORD *)this + 6) = v49 & 0xFFFFFFFE;
        return result;
      }
      if ( (v49 & 0x81000) != 0 )
        DLODCOBJ::vLockForDPIScaledClipping((DEVLOCKOBJ *)((char *)this + 32), **(HDC **)a2);
    }
    v50 = dword_140295318 <= 0;
    if ( dword_140295318 < 0 )
    {
      _InterlockedCompareExchange(
        &dword_140295318,
        Feature_Servicing_SurfaceMapping_devlock__private_IsEnabledDeviceUsageNoInline() != 0,
        -1);
      v50 = dword_140295318 <= 0;
    }
    if ( v50 )
      return 1;
    v51 = *((_QWORD *)this + 4);
    if ( v51 && *((_BYTE *)this + 129) )
      v52 = *(SURFACE **)(v51 + 496);
    else
      v52 = *(_QWORD *)a2 ? *(SURFACE **)(*(_QWORD *)a2 + 496LL) : 0LL;
    v14 = *((_DWORD *)this + 40) == 2;
    *((_QWORD *)this + 21) = v52;
    if ( !v14 || !v52 )
      return 1;
    if ( (int)SURFACE::MapUserVAToKernel(v52, IoWriteAccess, 0) >= 0 )
    {
      *((_DWORD *)this + 40) = 0;
      return 1;
    }
    *((_DWORD *)this + 40) = 1;
  }
LABEL_138:
  *((_DWORD *)this + 6) &= ~1u;
  return 0;
}

```

## disassembly

```asm
0x140009c80  push    rbx
0x140009c82  push    rsi
0x140009c83  push    rdi
0x140009c84  push    r13
0x140009c86  push    r14
0x140009c88  push    r15
0x140009c8a  sub     rsp, 38h
0x140009c8e  xor     r13d, r13d
0x140009c91  mov     dword ptr [rcx+18h], 1
0x140009c98  mov     [rcx], r13
0x140009c9b  mov     rbx, rcx
0x140009c9e  mov     [rcx+8], r13
0x140009ca2  mov     edi, r8d
0x140009ca5  mov     [rcx+10h], r13
0x140009ca9  mov     rsi, rdx
0x140009cac  mov     [rcx+90h], r13
0x140009cb3  mov     [rcx+88h], r13
0x140009cba  mov     rax, [rdx]
0x140009cbd  mov     rcx, [rax]
0x140009cc0  mov     [rbx+98h], rcx
0x140009cc7  test    r8d, r8d
0x140009cca  jnz     loc_140009D56
0x140009cd0  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140009cd7  nop     dword ptr [rax+rax+00h]
0x140009cdc  mov     rcx, [rax+18h]
0x140009ce0  mov     rax, [rcx+7F0h]
0x140009ce7  test    rax, rax
0x140009cea  jz      short loc_140009D41
0x140009cec  call    _guard_dispatch_icall
0x140009cf1  test    eax, eax
0x140009cf3  js      short loc_140009D41
0x140009cf5  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140009cfc  nop     dword ptr [rax+rax+00h]
0x140009d01  mov     rcx, [rax+18h]
0x140009d05  mov     rax, [rcx+7F8h]
0x140009d0c  test    rax, rax
0x140009d0f  jz      short loc_140009D2D
0x140009d11  lea     r9, [rbx+1Ch]
0x140009d15  mov     rcx, rsi
0x140009d18  lea     r8, [rbx+88h]
0x140009d1f  lea     rdx, [rbx+90h]
0x140009d26  call    _guard_dispatch_icall
0x140009d2b  jmp     short loc_140009D30
0x140009d2d  mov     eax, r13d
0x140009d30  cmp     eax, 1
0x140009d33  jnz     short loc_140009D41
0x140009d35  xor     edx, edx; struct XDCOBJ *
0x140009d37  mov     rcx, rbx; this
0x140009d3a  call    ?bPrepareTrgDco@DEVLOCKOBJ@@QEAAHPEAVXDCOBJ@@@Z; DEVLOCKOBJ::bPrepareTrgDco(XDCOBJ *)
0x140009d3f  jmp     short loc_140009D6C
0x140009d41  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x140009d45  xor     eax, eax
0x140009d47  add     rsp, 38h
0x140009d4b  pop     r15
0x140009d4d  pop     r14
0x140009d4f  pop     r13
0x140009d51  pop     rdi
0x140009d52  pop     rsi
0x140009d53  pop     rbx
0x140009d54  retn
0x140009d56  xor     edx, edx; struct XDCOBJ *
0x140009d58  mov     rcx, rbx; this
0x140009d5b  call    ?bPrepareTrgDco@DEVLOCKOBJ@@QEAAHPEAVXDCOBJ@@@Z; DEVLOCKOBJ::bPrepareTrgDco(XDCOBJ *)
0x140009d60  cmp     edi, 1
0x140009d63  jnz     short loc_140009D6C
0x140009d65  or      dword ptr [rbx+18h], 20000h
0x140009d6c  mov     rax, [rsi]
0x140009d6f  mov     rdi, [rsi+10h]
0x140009d73  mov     [rsp+68h+var_38], r12
0x140009d78  mov     r12d, r13d
0x140009d7b  test    dword ptr [rax+24h], 200h
0x140009d82  jz      loc_140009F84
0x140009d88  mov     rax, [rdi]
0x140009d8b  mov     rcx, rdi
0x140009d8e  add     rax, 270h
0x140009d94  mov     [rbx+8], rax
0x140009d98  call    ??$GreAcquireSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x140009d9d  or      dword ptr [rbx+18h], 8
0x140009da1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140009da8  nop     dword ptr [rax+rax+00h]
0x140009dad  test    rax, rax
0x140009db0  jz      short loc_140009DD1
0x140009db2  mov     rcx, [rax]
0x140009db5  mov     rdx, r13
0x140009db8  test    rcx, rcx
0x140009dbb  lea     rax, [rcx+8]
0x140009dbf  cmovnz  rdx, rax
0x140009dc3  test    rdx, rdx
0x140009dc6  jz      short loc_140009DD1
0x140009dc8  cmp     [rdx+154h], r13d
0x140009dcf  jnz     short loc_140009DF9
0x140009dd1  mov     rcx, [rdi]
0x140009dd4  add     rcx, 478h; Resource
0x140009ddb  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140009de2  nop     dword ptr [rax+rax+00h]
0x140009de7  test    eax, eax
0x140009de9  jnz     short loc_140009DF9
0x140009deb  mov     rcx, rdi
0x140009dee  call    ??$GreAcquireSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140009df3  mov     r12d, 1
0x140009df9  mov     rdx, [rsi]
0x140009dfc  mov     rax, [rdx+30h]
0x140009e00  mov     [rsp+68h+arg_0], rax
0x140009e05  mov     rax, [rdx+3D0h]
0x140009e0c  mov     ecx, [rax]
0x140009e0e  test    cl, 1
0x140009e11  jnz     short loc_140009E1C
0x140009e13  test    dword ptr [rdx+24h], 8000h
0x140009e1a  jz      short loc_140009E2D
0x140009e1c  lea     rcx, [rsp+68h+arg_0]; this
0x140009e21  call    ?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x140009e26  test    eax, eax
0x140009e28  jnz     short loc_140009EA2
0x140009e2a  mov     rdx, [rsi]
0x140009e2d  mov     r8, [rdx+40h]
0x140009e31  mov     [rbx], r8
0x140009e34  mov     rax, [rsi]
0x140009e37  mov     rcx, [rax+30h]
0x140009e3b  mov     [rbx+10h], rcx
0x140009e3f  cmp     r12d, 1
0x140009e43  jnz     short loc_140009E5E
0x140009e45  mov     rax, [rdi]
0x140009e48  add     rax, 478h
0x140009e4e  cmp     r8, rax
0x140009e51  jnz     short loc_140009E5E
0x140009e53  mov     rcx, rdi
0x140009e56  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140009e5b  mov     r12d, r13d
0x140009e5e  mov     rax, [rdi]
0x140009e61  add     rax, 478h
0x140009e67  cmp     [rbx], rax
0x140009e6a  jnz     short loc_140009E7D
0x140009e6c  or      dword ptr [rbx+18h], 100000h
0x140009e73  mov     rcx, rdi
0x140009e76  call    ??$GreAcquireSemaphore@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphore<2,>(Gre::Base::SESSION_GLOBALS &)
0x140009e7b  jmp     short loc_140009E86
0x140009e7d  mov     rcx, [rbx+10h]
0x140009e81  call    ??$GreAcquireSemaphore@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreAcquireSemaphore<8,PDEVOBJ>(PDEVOBJ)
0x140009e86  mov     edx, [rbx+18h]
0x140009e89  bt      edx, 9
0x140009e8d  jb      short loc_140009EA2
0x140009e8f  mov     rax, [rsi]
0x140009e92  test    dword ptr [rax+24h], 4000h
0x140009e99  jz      short loc_140009EA2
0x140009e9b  bts     edx, 9
0x140009e9f  mov     [rbx+18h], edx
0x140009ea2  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140009ea9  nop     dword ptr [rax+rax+00h]
0x140009eae  test    rax, rax
0x140009eb1  jz      short loc_140009ED2
0x140009eb3  mov     rcx, [rax]
0x140009eb6  mov     rdx, r13
0x140009eb9  test    rcx, rcx
0x140009ebc  lea     rax, [rcx+8]
0x140009ec0  cmovnz  rdx, rax
0x140009ec4  test    rdx, rdx
0x140009ec7  jz      short loc_140009ED2
0x140009ec9  cmp     [rdx+154h], r13d
0x140009ed0  jnz     short loc_140009F43
0x140009ed2  or      dword ptr [rbx+18h], 1000h
0x140009ed9  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140009ee0  nop     dword ptr [rax+rax+00h]
0x140009ee5  test    rax, rax
0x140009ee8  jz      short loc_140009F0E
0x140009eea  mov     rcx, [rax]
0x140009eed  mov     rdx, r13
0x140009ef0  test    rcx, rcx
0x140009ef3  lea     rax, [rcx+8]
0x140009ef7  cmovnz  rdx, rax
0x140009efb  test    rdx, rdx
0x140009efe  jz      short loc_140009F0E
0x140009f00  mov     [rdx+130h], r13
0x140009f07  mov     [rdx+128h], r13
0x140009f0e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140009f15  nop     dword ptr [rax+rax+00h]
0x140009f1a  test    rax, rax
0x140009f1d  jz      short loc_140009F3B
0x140009f1f  mov     rcx, [rax]
0x140009f22  mov     rdx, r13
0x140009f25  test    rcx, rcx
0x140009f28  lea     rax, [rcx+8]
0x140009f2c  cmovnz  rdx, rax
0x140009f30  test    rdx, rdx
0x140009f33  jz      short loc_140009F3B
0x140009f35  inc     dword ptr [rdx+154h]
0x140009f3b  mov     rcx, rdi
0x140009f3e  call    ??$GreAcquireSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x140009f43  mov     rax, [rsi]
0x140009f46  mov     ecx, [rax+24h]
0x140009f49  and     ecx, 5000h
0x140009f4f  cmp     ecx, 1000h
0x140009f55  jnz     loc_140009FE8
0x140009f5b  test    [rbx+18h], ecx
0x140009f5e  jz      short loc_140009F68
0x140009f60  mov     rcx, rdi
0x140009f63  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x140009f68  test    r12d, r12d
0x140009f6b  jz      loc_14000A33F
0x140009f71  mov     rcx, rdi
0x140009f74  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140009f79  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x140009f7d  xor     eax, eax
0x140009f7f  jmp     loc_14000A321
0x140009f84  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140009f8b  nop     dword ptr [rax+rax+00h]
0x140009f90  test    rax, rax
0x140009f93  jz      short loc_140009FB4
0x140009f95  mov     rcx, [rax]
0x140009f98  mov     rdx, r13
0x140009f9b  test    rcx, rcx
0x140009f9e  lea     rax, [rcx+8]
0x140009fa2  cmovnz  rdx, rax
0x140009fa6  test    rdx, rdx
0x140009fa9  jz      short loc_140009FB4
0x140009fab  cmp     [rdx+154h], r13d
0x140009fb2  jnz     short loc_140009FE8
0x140009fb4  or      dword ptr [rbx+18h], 80000h
0x140009fbb  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140009fc2  nop     dword ptr [rax+rax+00h]
0x140009fc7  test    rax, rax
0x140009fca  jz      short loc_140009FE8
0x140009fcc  mov     rcx, [rax]
0x140009fcf  mov     rdx, r13
0x140009fd2  test    rcx, rcx
0x140009fd5  lea     rax, [rcx+8]
0x140009fd9  cmovnz  rdx, rax
0x140009fdd  test    rdx, rdx
0x140009fe0  jz      short loc_140009FE8
0x140009fe2  inc     dword ptr [rdx+154h]
0x140009fe8  test    dword ptr [rbx+18h], 1000h
0x140009fef  jz      short loc_14000A027
0x140009ff1  mov     rax, [rsi]
0x140009ff4  test    dword ptr [rax+24h], 80000h
0x140009ffb  jz      short loc_14000A02D
0x140009ffd  cmp     [rbx+8], r13
0x14000a001  jz      short loc_14000A00B
0x14000a003  mov     rcx, rdi
0x14000a006  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x14000a00b  test    r12d, r12d
0x14000a00e  jz      loc_14000A33F
0x14000a014  mov     rcx, rdi
0x14000a017  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14000a01c  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x14000a020  xor     eax, eax
0x14000a022  jmp     loc_14000A321
0x14000a027  cmp     [rbx+8], r13
0x14000a02b  jnz     short loc_14000A06A
0x14000a02d  mov     rcx, [rsi]; this
0x14000a030  mov     eax, [rcx+24h]
0x14000a033  test    al, 10h
0x14000a035  jz      short loc_14000A06A
0x14000a037  call    ?bCompute@DC@@QEAAHXZ; DC::bCompute(void)
0x14000a03c  test    eax, eax
0x14000a03e  jnz     short loc_14000A06A
0x14000a040  cmp     [rbx+8], r13
0x14000a044  jz      short loc_14000A04E
0x14000a046  mov     rcx, rdi
0x14000a049  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x14000a04e  test    r12d, r12d
0x14000a051  jz      loc_14000A33F
0x14000a057  mov     rcx, rdi
0x14000a05a  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14000a05f  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x14000a063  xor     eax, eax
0x14000a065  jmp     loc_14000A321
0x14000a06a  mov     rcx, [rsi]; this
0x14000a06d  cmp     [rcx+490h], r13
0x14000a074  jz      short loc_14000A095
0x14000a076  mov     eax, [rcx+28h]
0x14000a079  test    al, 2
0x14000a07b  jz      short loc_14000A095
0x14000a07d  mov     rax, [rcx+1F0h]
0x14000a084  test    rax, rax
0x14000a087  jz      short loc_14000A095
0x14000a089  test    dword ptr [rax+0A4h], 800h
0x14000a093  jnz     short loc_14000A0D3
0x14000a095  cmp     [rcx+480h], r13
0x14000a09c  jnz     short loc_14000A0D3
0x14000a09e  cmp     [rcx+488h], r13
0x14000a0a5  jz      short loc_14000A0C6
0x14000a0a7  mov     eax, [rcx+28h]
0x14000a0aa  test    al, 2
0x14000a0ac  jz      short loc_14000A0C6
0x14000a0ae  mov     rax, [rcx+1F0h]
0x14000a0b5  test    rax, rax
0x14000a0b8  jz      short loc_14000A0C6
0x14000a0ba  test    dword ptr [rax+0A4h], 800h
0x14000a0c4  jnz     short loc_14000A0D3
0x14000a0c6  cmp     [rcx+478h], r13
0x14000a0cd  jz      loc_14000A33F
0x14000a0d3  mov     edx, [rbx+18h]
0x14000a0d6  bt      edx, 11h
0x14000a0da  jb      loc_14000A231
0x14000a0e0  test    dword ptr [rcx+24h], 200h
0x14000a0e7  jz      loc_14000A231
0x14000a0ed  bt      edx, 0Ch
0x14000a0f1  jnb     loc_14000A231
0x14000a0f7  mov     [rsp+68h+arg_8], rbp
0x14000a0fc  cmp     [rbx+88h], r13
0x14000a103  jnz     short loc_14000A10A
  ... truncated ...
```
