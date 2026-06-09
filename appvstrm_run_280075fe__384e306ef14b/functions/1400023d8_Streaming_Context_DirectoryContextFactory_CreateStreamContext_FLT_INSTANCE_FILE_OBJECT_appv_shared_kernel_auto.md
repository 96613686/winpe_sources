# Streaming::Context::DirectoryContextFactory::CreateStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::DirectoryContext,Streaming::Context::ContextDelete> &)

- ea: `0x1400023d8`
- end: `0x140002702`
- name: `?CreateStreamContext@DirectoryContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UDirectoryContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z`
- size: `810`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a310`

## callees

- `0x140002298`
- `0x1400023d8`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`
- `0x140015f00`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140002556`
- `ntoskrnl!ExInitializeResourceLite` at `0x140002556`
- `ntoskrnl!ExAllocatePool2` at `0x14000250a`
- `ntoskrnl!ExAllocatePool2` at `0x140002537`
- `ntoskrnl!ExAllocatePool2` at `0x14000250a`
- `ntoskrnl!ExAllocatePool2` at `0x140002537`
- `FLTMGR!FltSetStreamContext` at `0x1400025a0`
- `FLTMGR!FltSetStreamContext` at `0x1400025a0`
- `FLTMGR!FltReleaseContext` at `0x1400024a9`
- `FLTMGR!FltReleaseContext` at `0x1400024c6`
- `FLTMGR!FltReleaseContext` at `0x1400025c8`
- `FLTMGR!FltReleaseContext` at `0x1400025e5`
- `FLTMGR!FltReleaseContext` at `0x140002605`
- `FLTMGR!FltReleaseContext` at `0x140002622`
- `FLTMGR!FltReleaseContext` at `0x1400026ba`
- `FLTMGR!FltReleaseContext` at `0x1400026d7`
- `FLTMGR!FltReleaseContext` at `0x1400024a9`
- `FLTMGR!FltReleaseContext` at `0x1400024c6`
- `FLTMGR!FltReleaseContext` at `0x1400025c8`
- `FLTMGR!FltReleaseContext` at `0x1400025e5`
- `FLTMGR!FltReleaseContext` at `0x140002605`
- `FLTMGR!FltReleaseContext` at `0x140002622`
- `FLTMGR!FltReleaseContext` at `0x1400026ba`
- `FLTMGR!FltReleaseContext` at `0x1400026d7`
- `FLTMGR!FltAllocateContext` at `0x140002430`
- `FLTMGR!FltAllocateContext` at `0x140002430`

## string_xrefs

- `0x14000244f`: `DirectoryContextFactory::CreateStreamContext() - Low memory error.`
- `0x14000265d`: `DirectoryContextFactory::CreateStreamContext() - Low memory error.`

## pseudocode

```c
__int64 __fastcall Streaming::Context::DirectoryContextFactory::CreateStreamContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT *a3)
{
  NTSTATUS v6; // esi
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v8; // rdi
  __int64 *v10; // r14
  __int64 Pool2; // rax
  _QWORD *v12; // rdi
  struct _ERESOURCE *v13; // rax
  NTSTATUS v14; // edi
  PFLT_CONTEXT v15; // rcx
  PFLT_CONTEXT v16; // rax
  PFLT_CONTEXT v17; // rcx
  __int64 *v18; // rax
  volatile signed __int32 *v19; // rdi
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-18h] BYREF
  volatile signed __int32 *v22; // [rsp+40h] [rbp-10h]
  PFLT_CONTEXT NewContext; // [rsp+98h] [rbp+48h] BYREF

  NewContext = 0;
  Context = 0;
  v6 = FltAllocateContext(*((PFLT_FILTER *)Streaming::gStrmFltData + 1), 8u, 0x70u, PagedPool, &NewContext);
  if ( v6 < 0 )
  {
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v21);
    LogWrite(1, *CurrentActivityID, L"DirectoryContextFactory::CreateStreamContext() - Low memory error.");
    v8 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    if ( NewContext )
      FltReleaseContext(NewContext);
    return (unsigned int)v6;
  }
  memset(NewContext, 0, 0x70u);
  *(_BYTE *)NewContext = 1;
  *((_BYTE *)NewContext + 24) = 0;
  v10 = (__int64 *)NewContext;
  Pool2 = ExAllocatePool2(256, 16, 1667524211);
  v12 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_DWORD *)Pool2 = 1818453619;
    v13 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1818453619);
    v12[1] = v13;
    if ( v13 )
      v6 = ExInitializeResourceLite(v13);
    else
      v6 = -1073741670;
  }
  else
  {
    v12 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::shared_read_lock>::reset<appv::shared::kernel::shared_read_lock>(
    v10 + 1,
    v12);
  if ( v6 >= 0 && *((_QWORD *)NewContext + 1) )
  {
    v14 = FltSetStreamContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, &Context);
    if ( v14 == -1071906814 )
    {
      v16 = Context;
      Context = *a3;
      v15 = Context;
      *a3 = v16;
      if ( !v15 )
      {
LABEL_19:
        v17 = NewContext;
LABEL_20:
        if ( v17 )
          FltReleaseContext(v17);
        return 0;
      }
LABEL_18:
      FltReleaseContext(v15);
      Context = 0;
      goto LABEL_19;
    }
    if ( v14 >= 0 )
    {
      v17 = *a3;
      *a3 = NewContext;
      NewContext = v17;
      if ( !Context )
        goto LABEL_20;
      v15 = Context;
      goto LABEL_18;
    }
    if ( Context )
    {
      FltReleaseContext(Context);
      Context = 0;
    }
    if ( NewContext )
      FltReleaseContext(NewContext);
    return (unsigned int)v14;
  }
  else
  {
    v18 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v21);
    LogWrite(1, *v18, L"DirectoryContextFactory::CreateStreamContext() - Low memory error.");
    v19 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    if ( Context )
    {
      FltReleaseContext(Context);
      Context = 0;
    }
    if ( NewContext )
      FltReleaseContext(NewContext);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400023d8  mov     [rsp-28h+arg_0], rbx
0x1400023dd  mov     [rsp-28h+arg_8], rsi
0x1400023e2  push    rbp
0x1400023e3  push    rdi
0x1400023e4  push    r12
0x1400023e6  push    r14
0x1400023e8  push    r15
0x1400023ea  mov     rbp, rsp
0x1400023ed  sub     rsp, 50h
0x1400023f1  mov     r12, rcx
0x1400023f4  mov     [rbp+NewContext], 0
0x1400023fc  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140002403  lea     rax, [rbp+NewContext]
0x140002407  mov     r15, rdx
0x14000240a  mov     [rbp+Context], 0
0x140002412  mov     edx, 8; ContextType
0x140002417  mov     [rsp+50h+ReturnedContext], rax; ReturnedContext
0x14000241c  mov     rbx, r8
0x14000241f  mov     rcx, [rcx+8]; Filter
0x140002423  lea     edi, [rdx-7]
0x140002426  lea     r14d, [rdx+68h]
0x14000242a  mov     r9d, edi; PoolType
0x14000242d  mov     r8d, r14d; ContextSize
0x140002430  call    cs:__imp_FltAllocateContext
0x140002437  nop     dword ptr [rax+rax+00h]
0x14000243c  mov     esi, eax
0x14000243e  test    eax, eax
0x140002440  jns     loc_1400024D9
0x140002446  lea     rcx, [rbp+var_18]
0x14000244a  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000244f  lea     r8, aDirectoryconte; "DirectoryContextFactory::CreateStreamCo"...
0x140002456  mov     ecx, edi
0x140002458  mov     rdx, [rax]
0x14000245b  call    LogWrite
0x140002460  mov     rdi, [rbp+var_10]
0x140002464  test    rdi, rdi
0x140002467  jz      short loc_1400024A0
0x140002469  or      ebx, 0FFFFFFFFh
0x14000246c  mov     eax, ebx
0x14000246e  lock xadd [rdi+8], eax
0x140002473  add     eax, ebx
0x140002475  jnz     short loc_1400024A0
0x140002477  mov     rax, [rdi]
0x14000247a  mov     rcx, rdi
0x14000247d  mov     rax, [rax+8]
0x140002481  call    _guard_dispatch_icall
0x140002486  mov     eax, ebx
0x140002488  lock xadd [rdi+0Ch], eax
0x14000248d  add     eax, ebx
0x14000248f  jnz     short loc_1400024A0
0x140002491  mov     rax, [rdi]
0x140002494  mov     rcx, rdi
0x140002497  mov     rax, [rax+10h]
0x14000249b  call    _guard_dispatch_icall
0x1400024a0  mov     rcx, [rbp+Context]; Context
0x1400024a4  test    rcx, rcx
0x1400024a7  jz      short loc_1400024BD
0x1400024a9  call    cs:__imp_FltReleaseContext
0x1400024b0  nop     dword ptr [rax+rax+00h]
0x1400024b5  mov     [rbp+Context], 0
0x1400024bd  mov     rcx, [rbp+NewContext]; Context
0x1400024c1  test    rcx, rcx
0x1400024c4  jz      short loc_1400024D2
0x1400024c6  call    cs:__imp_FltReleaseContext
0x1400024cd  nop     dword ptr [rax+rax+00h]
0x1400024d2  mov     eax, esi
0x1400024d4  jmp     loc_1400026E8
0x1400024d9  mov     rcx, [rbp+NewContext]; void *
0x1400024dd  mov     r8, r14; Size
0x1400024e0  xor     edx, edx; Val
0x1400024e2  call    memset
0x1400024e7  mov     rax, [rbp+NewContext]
0x1400024eb  mov     edx, 10h
0x1400024f0  mov     ecx, 100h
0x1400024f5  mov     r8d, 63646673h
0x1400024fb  mov     [rax], dil
0x1400024fe  mov     rax, [rbp+NewContext]
0x140002502  mov     byte ptr [rax+18h], 0
0x140002506  mov     r14, [rbp+NewContext]
0x14000250a  call    cs:__imp_ExAllocatePool2
0x140002511  nop     dword ptr [rax+rax+00h]
0x140002516  mov     rdi, rax
0x140002519  test    rax, rax
0x14000251c  jz      short loc_140002566
0x14000251e  mov     edx, 68h ; 'h'
0x140002523  mov     qword ptr [rax+8], 0
0x14000252b  mov     r8d, 6C636673h
0x140002531  mov     [rax], r8d
0x140002534  lea     ecx, [rdx-28h]
0x140002537  call    cs:__imp_ExAllocatePool2
0x14000253e  nop     dword ptr [rax+rax+00h]
0x140002543  mov     [rdi+8], rax
0x140002547  test    rax, rax
0x14000254a  jnz     short loc_140002553
0x14000254c  mov     esi, 0C000009Ah
0x140002551  jmp     short loc_140002568
0x140002553  mov     rcx, rax; Resource
0x140002556  call    cs:__imp_ExInitializeResourceLite
0x14000255d  nop     dword ptr [rax+rax+00h]
0x140002562  mov     esi, eax
0x140002564  jmp     short loc_140002568
0x140002566  xor     edi, edi
0x140002568  mov     rdx, rdi
0x14000256b  lea     rcx, [r14+8]
0x14000256f  call    ??$reset@Vshared_read_lock@kernel@shared@appv@@@?$shared_ptr@Vshared_read_lock@kernel@shared@appv@@@kernel_std@@QEAAXPEAVshared_read_lock@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::shared_read_lock>::reset<appv::shared::kernel::shared_read_lock>(appv::shared::kernel::shared_read_lock *)
0x140002574  test    esi, esi
0x140002576  js      loc_140002654
0x14000257c  mov     r9, [rbp+NewContext]; NewContext
0x140002580  cmp     qword ptr [r9+8], 0
0x140002585  jz      loc_140002654
0x14000258b  lea     rax, [rbp+Context]
0x14000258f  mov     r8d, 1; Operation
0x140002595  mov     rdx, r15; FileObject
0x140002598  mov     [rsp+50h+ReturnedContext], rax; OldContext
0x14000259d  mov     rcx, r12; Instance
0x1400025a0  call    cs:__imp_FltSetStreamContext
0x1400025a7  nop     dword ptr [rax+rax+00h]
0x1400025ac  mov     edi, eax
0x1400025ae  cmp     eax, 0C01C0002h
0x1400025b3  jnz     short loc_1400025F8
0x1400025b5  mov     rcx, [rbx]; Context
0x1400025b8  mov     rax, [rbp+Context]
0x1400025bc  mov     [rbp+Context], rcx
0x1400025c0  mov     [rbx], rax
0x1400025c3  test    rcx, rcx
0x1400025c6  jz      short loc_1400025DC
0x1400025c8  call    cs:__imp_FltReleaseContext
0x1400025cf  nop     dword ptr [rax+rax+00h]
0x1400025d4  mov     [rbp+Context], 0
0x1400025dc  mov     rcx, [rbp+NewContext]; Context
0x1400025e0  test    rcx, rcx
0x1400025e3  jz      short loc_1400025F1
0x1400025e5  call    cs:__imp_FltReleaseContext
0x1400025ec  nop     dword ptr [rax+rax+00h]
0x1400025f1  xor     eax, eax
0x1400025f3  jmp     loc_1400026E8
0x1400025f8  test    edi, edi
0x1400025fa  jns     short loc_140002635
0x1400025fc  mov     rcx, [rbp+Context]; Context
0x140002600  test    rcx, rcx
0x140002603  jz      short loc_140002619
0x140002605  call    cs:__imp_FltReleaseContext
0x14000260c  nop     dword ptr [rax+rax+00h]
0x140002611  mov     [rbp+Context], 0
0x140002619  mov     rcx, [rbp+NewContext]; Context
0x14000261d  test    rcx, rcx
0x140002620  jz      short loc_14000262E
0x140002622  call    cs:__imp_FltReleaseContext
0x140002629  nop     dword ptr [rax+rax+00h]
0x14000262e  mov     eax, edi
0x140002630  jmp     loc_1400026E8
0x140002635  mov     rax, [rbp+NewContext]
0x140002639  mov     rcx, [rbx]
0x14000263c  mov     [rbx], rax
0x14000263f  mov     rax, [rbp+Context]
0x140002643  mov     [rbp+NewContext], rcx
0x140002647  test    rax, rax
0x14000264a  jz      short loc_1400025E0
0x14000264c  mov     rcx, rax
0x14000264f  jmp     loc_1400025C8
0x140002654  lea     rcx, [rbp+var_18]
0x140002658  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000265d  lea     r8, aDirectoryconte; "DirectoryContextFactory::CreateStreamCo"...
0x140002664  mov     ecx, 1
0x140002669  mov     rdx, [rax]
0x14000266c  call    LogWrite
0x140002671  mov     rdi, [rbp+var_10]
0x140002675  test    rdi, rdi
0x140002678  jz      short loc_1400026B1
0x14000267a  or      ebx, 0FFFFFFFFh
0x14000267d  mov     eax, ebx
0x14000267f  lock xadd [rdi+8], eax
0x140002684  add     eax, ebx
0x140002686  jnz     short loc_1400026B1
0x140002688  mov     rax, [rdi]
0x14000268b  mov     rcx, rdi
0x14000268e  mov     rax, [rax+8]
0x140002692  call    _guard_dispatch_icall
0x140002697  mov     eax, ebx
0x140002699  lock xadd [rdi+0Ch], eax
0x14000269e  add     eax, ebx
0x1400026a0  jnz     short loc_1400026B1
0x1400026a2  mov     rax, [rdi]
0x1400026a5  mov     rcx, rdi
0x1400026a8  mov     rax, [rax+10h]
0x1400026ac  call    _guard_dispatch_icall
0x1400026b1  mov     rcx, [rbp+Context]; Context
0x1400026b5  test    rcx, rcx
0x1400026b8  jz      short loc_1400026CE
0x1400026ba  call    cs:__imp_FltReleaseContext
0x1400026c1  nop     dword ptr [rax+rax+00h]
0x1400026c6  mov     [rbp+Context], 0
0x1400026ce  mov     rcx, [rbp+NewContext]; Context
0x1400026d2  test    rcx, rcx
0x1400026d5  jz      short loc_1400026E3
0x1400026d7  call    cs:__imp_FltReleaseContext
0x1400026de  nop     dword ptr [rax+rax+00h]
0x1400026e3  mov     eax, 0C000009Ah
0x1400026e8  lea     r11, [rsp+50h+var_s0]
0x1400026ed  mov     rbx, [r11+30h]
0x1400026f1  mov     rsi, [r11+38h]
0x1400026f5  mov     rsp, r11
0x1400026f8  pop     r15
0x1400026fa  pop     r14
0x1400026fc  pop     r12
0x1400026fe  pop     rdi
0x1400026ff  pop     rbp
0x140002700  retn
```
