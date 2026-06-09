# RefsNotifyChangeDirectory(_IRP_CONTEXT *,_IRP *,_VCB *,_SCB *,_CCB *)

- ea: `0x1402a1288`
- end: `0x1402a1655`
- name: `?RefsNotifyChangeDirectory@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_VCB@@PEAU_SCB@@PEAU_CCB@@@Z`
- size: `973`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct _IRP *@<rdx>, struct _VCB *@<r8>, struct _SCB *@<r9>, struct _CCB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1403162c0`

## callees

- `0x14000e0e0`
- `0x140076ad0`
- `0x140085570`
- `0x1400862c0`
- `0x140088990`
- `0x1400d0fd8`
- `0x1402a1288`
- `0x14031def0`
- `0x14031f9c0`

## import_xrefs

- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1402a15b7`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1402a15b7`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402a1427`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402a14c9`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402a1427`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402a14c9`
- `ntoskrnl!PsIsThreadImpersonating` at `0x1402a1473`
- `ntoskrnl!PsIsThreadImpersonating` at `0x1402a1473`
- `ntoskrnl!SeTokenIsAdmin` at `0x1402a14e6`
- `ntoskrnl!SeTokenIsAdmin` at `0x1402a14e6`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1402a151b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1402a151b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a152c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a152c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346d92`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a140b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a14ad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a140b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a14ad`

## pseudocode

```c
__int64 __fastcall RefsNotifyChangeDirectory(
        struct _IRP_CONTEXT *a1,
        struct _IRP *a2,
        struct _VCB *a3,
        struct _SCB *a4,
        struct _CCB *FsContext)
{
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // rbx
  BOOLEAN (__stdcall *TraverseCallback)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT); // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  BOOLEAN WatchTree; // r15
  unsigned int v13; // r8d
  __int64 v14; // rcx
  unsigned int v15; // r8d
  PACCESS_TOKEN ClientToken; // rcx
  int v17; // ecx
  ULONG CompletionFilter; // [rsp+C8h] [rbp+10h]

  SubjectContext = 0;
  TraverseCallback = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  CompletionFilter = CurrentStackLocation->Parameters.Create.Options;
  WatchTree = CurrentStackLocation->Flags & 1;
  *((_QWORD *)a1 + 1) |= 1uLL;
  RefsAcquireSharedVcb(a1, a3, 1u);
  v14 = *((_QWORD *)a4 + 17);
  if ( !*(_DWORD *)(v14 + 176) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids, 3221225558LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741738, a1, "DirCtrl.c", 0x64Du);
    RefsRaiseStatusInternal(a1, -1073741738, v13);
  }
  if ( !RefsIsFileOpen((const struct _FCB *)v14) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids, 3221225768LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528, a1, "DirCtrl.c", 0x657u);
    RefsRaiseStatusInternal(a1, -1073741528, v15);
  }
  if ( WatchTree )
  {
    if ( (*((_DWORD *)FsContext + 1) & 0x80u) != 0 )
    {
      SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                             (POOL_TYPE)(PoolType | 0x10),
                                                             0x20u,
                                                             0x64466552u);
      SeCaptureSubjectContext(SubjectContext);
      TraverseCallback = (BOOLEAN (__stdcall *)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT))RefsNotifyTraverseCheck;
    }
    if ( byte_1402688C8 )
    {
      if ( !_bittest16((const signed __int16 *)FsContext + 44, 9u)
        && ((unsigned __int8)PsIsThreadImpersonating(KeGetCurrentThread())
         || RefsEffectiveMode(a2, a2->Tail.Overlay.CurrentStackLocation) == 1) )
      {
        if ( !SubjectContext )
        {
          SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                                 (POOL_TYPE)(PoolType | 0x10),
                                                                 0x20u,
                                                                 0x64466552u);
          SeCaptureSubjectContext(SubjectContext);
        }
        ClientToken = SubjectContext->ClientToken;
        if ( !SubjectContext->ClientToken )
          ClientToken = SubjectContext->PrimaryToken;
        if ( !SeTokenIsAdmin(ClientToken) )
          TraverseCallback = (BOOLEAN (__stdcall *)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT))RefsNotifyTraverseCheckEx;
      }
      if ( !TraverseCallback && SubjectContext )
      {
        SeReleaseSubjectContext(SubjectContext);
        ExFreePoolWithTag(SubjectContext, 0);
        SubjectContext = 0;
      }
    }
  }
  v17 = *((_DWORD *)FsContext + 1);
  if ( (v17 & 0x800000) == 0 )
  {
    *((_DWORD *)FsContext + 1) = v17 | 0x800000;
    _InterlockedIncrement((volatile signed __int32 *)a3 + 354);
  }
  FsRtlNotifyFilterChangeDirectory(
    *((PNOTIFY_SYNC *)a3 + 108),
    (PLIST_ENTRY)a3 + 53,
    FsContext,
    (PSTRING)((char *)a4 + 392),
    WatchTree,
    0,
    CompletionFilter,
    a2,
    TraverseCallback,
    SubjectContext,
    0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids, 259);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(259, 0, "DirCtrl.c", 0x6BFu);
  RefsReleaseVcb(a1, a3);
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, 0, 0);
  return 259;
}

```

## disassembly

```asm
0x1402a1288  mov     rax, rsp
0x1402a128b  mov     [rax+18h], r8
0x1402a128f  mov     [rax+8], rcx
0x1402a1293  push    rbx
0x1402a1294  push    rsi
0x1402a1295  push    rdi
0x1402a1296  push    r12
0x1402a1298  push    r13
0x1402a129a  push    r14
0x1402a129c  push    r15
0x1402a129e  sub     rsp, 80h
0x1402a12a5  mov     r12, r9
0x1402a12a8  mov     r14, r8
0x1402a12ab  mov     r13, rdx
0x1402a12ae  mov     rdi, rcx
0x1402a12b1  xor     ebx, ebx
0x1402a12b3  mov     [rax-50h], rbx
0x1402a12b7  xor     esi, esi
0x1402a12b9  mov     [rax-58h], bl
0x1402a12bc  mov     [rax-57h], bl
0x1402a12bf  mov     rax, [rdx+0B8h]
0x1402a12c6  mov     ecx, [rax+10h]
0x1402a12c9  mov     [rsp+0B8h+arg_8], ecx
0x1402a12d0  mov     r15b, [rax+2]
0x1402a12d4  and     r15b, 1
0x1402a12d8  or      qword ptr [rdi+8], 1
0x1402a12dd  mov     r8b, 1; unsigned __int8
0x1402a12e0  mov     rdx, r14; struct _VCB *
0x1402a12e3  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1402a12e6  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x1402a12eb  nop
0x1402a12ec  mov     rcx, [r12+88h]
0x1402a12f4  cmp     [rcx+0B0h], esi
0x1402a12fa  jnz     short loc_1402A1368
0x1402a12fc  lea     rax, WPP_GLOBAL_Control
0x1402a1303  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a130a  cmp     rcx, rax
0x1402a130d  jz      short loc_1402A1337
0x1402a130f  test    dword ptr [rcx+2Ch], 100h
0x1402a1316  jz      short loc_1402A1337
0x1402a1318  cmp     byte ptr [rcx+29h], 4
0x1402a131c  jb      short loc_1402A1337
0x1402a131e  lea     edx, [rbx+1Ah]
0x1402a1321  mov     r9d, 0C0000056h
0x1402a1327  lea     r8, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids
0x1402a132e  mov     rcx, [rcx+18h]
0x1402a1332  call    WPP_SF_d
0x1402a1337  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a133d  test    al, al
0x1402a133f  jz      short loc_1402A135B
0x1402a1341  mov     r9d, 64Dh; unsigned int
0x1402a1347  lea     r8, aDirctrlC; "DirCtrl.c"
0x1402a134e  mov     rdx, rdi; struct _IRP_CONTEXT *
0x1402a1351  mov     ecx, 0C0000056h; Status
0x1402a1356  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402a135b  mov     edx, 0C0000056h; int
0x1402a1360  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1402a1363  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1402a1368  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x1402a136d  test    al, al
0x1402a136f  jnz     short loc_1402A13DF
0x1402a1371  lea     rax, WPP_GLOBAL_Control
0x1402a1378  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a137f  cmp     rcx, rax
0x1402a1382  jz      short loc_1402A13AE
0x1402a1384  test    dword ptr [rcx+2Ch], 100h
0x1402a138b  jz      short loc_1402A13AE
0x1402a138d  cmp     byte ptr [rcx+29h], 4
0x1402a1391  jb      short loc_1402A13AE
0x1402a1393  mov     edx, 1Bh
0x1402a1398  mov     r9d, 0C0000128h
0x1402a139e  lea     r8, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids
0x1402a13a5  mov     rcx, [rcx+18h]
0x1402a13a9  call    WPP_SF_d
0x1402a13ae  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a13b4  test    al, al
0x1402a13b6  jz      short loc_1402A13D2
0x1402a13b8  mov     r9d, 657h; unsigned int
0x1402a13be  lea     r8, aDirctrlC; "DirCtrl.c"
0x1402a13c5  mov     rdx, rdi; struct _IRP_CONTEXT *
0x1402a13c8  mov     ecx, 0C0000128h; Status
0x1402a13cd  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402a13d2  mov     edx, 0C0000128h; int
0x1402a13d7  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1402a13da  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1402a13df  test    r15b, r15b
0x1402a13e2  jz      loc_1402A1543
0x1402a13e8  mov     rax, [rsp+0B8h+FsContext]
0x1402a13f0  mov     ecx, [rax+4]
0x1402a13f3  test    cl, cl
0x1402a13f5  jns     short loc_1402A1444
0x1402a13f7  mov     ecx, cs:PoolType
0x1402a13fd  or      ecx, 10h; PoolType
0x1402a1400  mov     edx, 20h ; ' '; NumberOfBytes
0x1402a1405  mov     r8d, 64466552h; Tag
0x1402a140b  call    cs:__imp_ExAllocatePoolWithTag
0x1402a1412  nop     dword ptr [rax+rax+00h]
0x1402a1417  mov     rbx, rax
0x1402a141a  mov     [rsp+0B8h+var_50], rax
0x1402a141f  mov     [rsp+0B8h+var_58], 1
0x1402a1424  mov     rcx, rax; SubjectContext
0x1402a1427  call    cs:__imp_SeCaptureSubjectContext
0x1402a142e  nop     dword ptr [rax+rax+00h]
0x1402a1433  mov     [rsp+0B8h+var_58], 0
0x1402a1438  lea     rsi, ?RefsNotifyTraverseCheck@@YAEPEAX0PEAU_SECURITY_SUBJECT_CONTEXT@@@Z; RefsNotifyTraverseCheck(void *,void *,_SECURITY_SUBJECT_CONTEXT *)
0x1402a143f  mov     [rsp+0B8h+var_48], rsi
0x1402a1444  mov     [rsp+0B8h+var_58], 0
0x1402a1449  cmp     cs:byte_1402688C8, 0
0x1402a1450  jz      loc_1402A1543
0x1402a1456  mov     rax, [rsp+0B8h+FsContext]
0x1402a145e  bt      word ptr [rax+58h], 9
0x1402a1464  jb      loc_1402A1504
0x1402a146a  mov     rcx, gs:188h
0x1402a1473  call    cs:__imp_PsIsThreadImpersonating
0x1402a147a  nop     dword ptr [rax+rax+00h]
0x1402a147f  test    al, al
0x1402a1481  jnz     short loc_1402A1496
0x1402a1483  mov     rdx, [r13+0B8h]; struct _IO_STACK_LOCATION *
0x1402a148a  mov     rcx, r13; struct _IRP *
0x1402a148d  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402a1492  cmp     al, 1
0x1402a1494  jnz     short loc_1402A1504
0x1402a1496  test    rbx, rbx
0x1402a1499  jnz     short loc_1402A14DA
0x1402a149b  mov     ecx, cs:PoolType
0x1402a14a1  or      ecx, 10h; PoolType
0x1402a14a4  lea     edx, [rbx+20h]; NumberOfBytes
0x1402a14a7  mov     r8d, 64466552h; Tag
0x1402a14ad  call    cs:__imp_ExAllocatePoolWithTag
0x1402a14b4  nop     dword ptr [rax+rax+00h]
0x1402a14b9  mov     rbx, rax
0x1402a14bc  mov     [rsp+0B8h+var_50], rax
0x1402a14c1  mov     [rsp+0B8h+var_58], 1
0x1402a14c6  mov     rcx, rax; SubjectContext
0x1402a14c9  call    cs:__imp_SeCaptureSubjectContext
0x1402a14d0  nop     dword ptr [rax+rax+00h]
0x1402a14d5  mov     [rsp+0B8h+var_58], 0
0x1402a14da  mov     rcx, [rbx]
0x1402a14dd  test    rcx, rcx
0x1402a14e0  jnz     short loc_1402A14E6
0x1402a14e2  mov     rcx, [rbx+10h]; Token
0x1402a14e6  call    cs:__imp_SeTokenIsAdmin
0x1402a14ed  nop     dword ptr [rax+rax+00h]
0x1402a14f2  lea     rcx, ?RefsNotifyTraverseCheckEx@@YAEPEAX0PEAU_SECURITY_SUBJECT_CONTEXT@@@Z; RefsNotifyTraverseCheckEx(void *,void *,_SECURITY_SUBJECT_CONTEXT *)
0x1402a14f9  test    al, al
0x1402a14fb  cmovz   rsi, rcx
0x1402a14ff  mov     [rsp+0B8h+var_48], rsi
0x1402a1504  mov     [rsp+0B8h+var_58], 0
0x1402a1509  test    rsi, rsi
0x1402a150c  jnz     short loc_1402A1543
0x1402a150e  mov     [rsp+0B8h+var_58], sil
0x1402a1513  test    rbx, rbx
0x1402a1516  jz      short loc_1402A1543
0x1402a1518  mov     rcx, rbx; SubjectContext
0x1402a151b  call    cs:__imp_SeReleaseSubjectContext
0x1402a1522  nop     dword ptr [rax+rax+00h]
0x1402a1527  xor     edx, edx; Tag
0x1402a1529  mov     rcx, rbx; P
0x1402a152c  call    cs:__imp_ExFreePoolWithTag
0x1402a1533  nop     dword ptr [rax+rax+00h]
0x1402a1538  xor     ebx, ebx
0x1402a153a  mov     [rsp+0B8h+var_50], rbx
0x1402a153f  mov     [rsp+0B8h+var_58], bl
0x1402a1543  mov     rdx, [rsp+0B8h+FsContext]
0x1402a154b  mov     ecx, [rdx+4]
0x1402a154e  mov     r8d, 800000h
0x1402a1554  test    r8d, ecx
0x1402a1557  jnz     short loc_1402A156C
0x1402a1559  or      ecx, r8d
0x1402a155c  mov     [rdx+4], ecx
0x1402a155f  lock inc dword ptr [r14+588h]
0x1402a1567  mov     [rsp+0B8h+var_57], 1
0x1402a156c  lea     r9, [r12+188h]; FullDirectoryName
0x1402a1574  lea     rdx, [r14+350h]; NotifyList
0x1402a157b  mov     [rsp+0B8h+FilterCallback], 0; FilterCallback
0x1402a1584  mov     [rsp+0B8h+SubjectContext], rbx; SubjectContext
0x1402a1589  mov     [rsp+0B8h+TraverseCallback], rsi; TraverseCallback
0x1402a158e  mov     [rsp+0B8h+NotifyIrp], r13; NotifyIrp
0x1402a1593  mov     eax, [rsp+0B8h+arg_8]
0x1402a159a  mov     [rsp+0B8h+CompletionFilter], eax; CompletionFilter
0x1402a159e  mov     [rsp+0B8h+IgnoreBuffer], 0; IgnoreBuffer
0x1402a15a3  mov     [rsp+0B8h+WatchTree], r15b; WatchTree
0x1402a15a8  mov     r8, [rsp+0B8h+FsContext]; FsContext
0x1402a15b0  mov     rcx, [r14+360h]; NotifySync
0x1402a15b7  call    cs:__imp_FsRtlNotifyFilterChangeDirectory
0x1402a15be  nop     dword ptr [rax+rax+00h]
0x1402a15c3  lea     rax, WPP_GLOBAL_Control
0x1402a15ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a15d1  cmp     rcx, rax
0x1402a15d4  jz      short loc_1402A1600
0x1402a15d6  test    dword ptr [rcx+2Ch], 100h
0x1402a15dd  jz      short loc_1402A1600
0x1402a15df  cmp     byte ptr [rcx+29h], 5
0x1402a15e3  jb      short loc_1402A1600
0x1402a15e5  mov     edx, 1Ch
0x1402a15ea  mov     r9d, 103h
0x1402a15f0  lea     r8, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids
0x1402a15f7  mov     rcx, [rcx+18h]
0x1402a15fb  call    WPP_SF_d
0x1402a1600  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a1606  test    al, al
0x1402a1608  jz      short loc_1402A1624
0x1402a160a  mov     r9d, 6BFh; unsigned int
0x1402a1610  lea     r8, aDirctrlC; "DirCtrl.c"
0x1402a1617  xor     edx, edx; struct _IRP_CONTEXT *
0x1402a1619  mov     ecx, 103h; Status
0x1402a161e  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402a1623  nop
0x1402a1624  mov     rdx, r14; struct _VCB *
0x1402a1627  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1402a162a  call    ?RefsReleaseVcb@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@@Z; RefsReleaseVcb(_IRP_CONTEXT *,_VCB *)
0x1402a162f  xor     r8d, r8d; Status
0x1402a1632  xor     edx, edx; Irp
0x1402a1634  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1402a1637  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402a163c  mov     eax, 103h
0x1402a1641  add     rsp, 80h
0x1402a1648  pop     r15
0x1402a164a  pop     r14
0x1402a164c  pop     r13
0x1402a164e  pop     r12
0x1402a1650  pop     rdi
0x1402a1651  pop     rsi
0x1402a1652  pop     rbx
0x1402a1653  retn
0x140346d43  push    rbx
0x140346d45  push    rbp
0x140346d46  push    rdi
0x140346d47  sub     rsp, 60h
0x140346d4b  mov     rbp, rdx
0x140346d4e  movzx   ebx, cl
0x140346d51  mov     rdi, [rbp+0D0h]
0x140346d58  mov     rdx, rdi; struct _VCB *
0x140346d5b  mov     rcx, [rbp+0C0h]; struct _IRP_CONTEXT *
0x140346d62  call    ?RefsReleaseVcb@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@@Z; RefsReleaseVcb(_IRP_CONTEXT *,_VCB *)
0x140346d67  mov     eax, ebx
0x140346d69  test    bl, bl
0x140346d6b  jz      short loc_140346D9F
0x140346d6d  cmp     byte ptr [rbp+61h], 0
0x140346d71  jz      short loc_140346D86
0x140346d73  mov     rax, [rbp+0E0h]
0x140346d7a  btr     dword ptr [rax+4], 17h
0x140346d7f  lock dec dword ptr [rdi+588h]
0x140346d86  cmp     byte ptr [rbp+60h], 0
0x140346d8a  jz      short loc_140346D9F
0x140346d8c  xor     edx, edx; Tag
0x140346d8e  mov     rcx, [rbp+68h]; P
0x140346d92  call    cs:__imp_ExFreePoolWithTag
0x140346d99  nop     dword ptr [rax+rax+00h]
0x140346d9e  nop
0x140346d9f  add     rsp, 60h
0x140346da3  pop     rdi
0x140346da4  pop     rbp
0x140346da5  pop     rbx
0x140346da6  retn
```
