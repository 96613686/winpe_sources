# UaspFreeResources

- ea: `0x140003618`
- end: `0x140003b83`
- name: `UaspFreeResources`
- size: `1387`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140003600`
- `0x140003b90`

## callees

- `0x140002964`
- `0x140003618`
- `0x140004bf8`
- `0x140005238`
- `0x14000d560`
- `0x14000d830`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003755`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003781`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400037a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003975`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003990`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003aa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ae9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003b02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003b17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003755`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003781`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400037a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003975`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003990`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003aa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ae9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003b02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003b17`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000395e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000395e`
- `ntoskrnl!IoFreeIrp` at `0x1400037c1`
- `ntoskrnl!IoFreeIrp` at `0x1400037e0`
- `ntoskrnl!IoFreeIrp` at `0x14000382f`
- `ntoskrnl!IoFreeIrp` at `0x14000387b`
- `ntoskrnl!IoFreeIrp` at `0x1400038c3`
- `ntoskrnl!IoFreeIrp` at `0x14000390b`
- `ntoskrnl!IoFreeIrp` at `0x1400037c1`
- `ntoskrnl!IoFreeIrp` at `0x1400037e0`
- `ntoskrnl!IoFreeIrp` at `0x14000382f`
- `ntoskrnl!IoFreeIrp` at `0x14000387b`
- `ntoskrnl!IoFreeIrp` at `0x1400038c3`
- `ntoskrnl!IoFreeIrp` at `0x14000390b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140003693`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140003693`
- `ntoskrnl!IoFreeWorkItem` at `0x140003b5d`
- `ntoskrnl!IoFreeWorkItem` at `0x140003b5d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000370f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000370f`
- `ntoskrnl!IoFreeMdl` at `0x140003b36`
- `ntoskrnl!IoFreeMdl` at `0x140003b36`
- `ntoskrnl!DbgPrintEx` at `0x140003a1a`
- `ntoskrnl!DbgPrintEx` at `0x140003a1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400036bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400036bc`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000366b`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000366b`

## string_xrefs

- `0x140003a0d`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`

## pseudocode

```c
void __fastcall UaspFreeResources(__int64 a1, char a2)
{
  int Default; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  unsigned int i; // ebx
  __int64 v9; // rdi
  void *v10; // rcx
  void *v11; // rcx
  IRP *v12; // rcx
  IRP *v13; // rcx
  unsigned __int16 v14; // bp
  USBD_HANDLE *v15; // rdi
  __int64 v16; // rbx
  IRP *v17; // rcx
  struct _URB *v18; // rdx
  IRP *v19; // rcx
  struct _URB *v20; // rdx
  IRP *v21; // rcx
  struct _URB *v22; // rdx
  IRP *v23; // rcx
  struct _URB *v24; // rdx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  __int64 v29; // rbx
  void (__fastcall *v30)(_QWORD); // rax
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  __int64 v35; // rcx
  struct _MDL *v36; // rcx
  struct _IO_WORKITEM *v37; // rcx
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-58h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    WPP_RECORDER_SF_qDD(Default, v5, v6, v7);
  }
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 1288));
  if ( (*(_BYTE *)a1 & 2) != 0 )
  {
    KeWaitForSingleObject((PVOID)(a1 + 1408), Executive, 0, 0, 0);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        3,
        21,
        (__int64)WPP_5439ef5302de3287b9b5be8f6c06671c_Traceguids);
    *(_BYTE *)a1 |= 4u;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 1240), &LockHandle);
    *(_DWORD *)(a1 + 1248) = 1;
    if ( a2 && *(_QWORD *)(a1 + 1128) )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 1000); ++i )
      {
        v9 = 32LL * i;
        v10 = *(void **)(v9 + *(_QWORD *)(a1 + 1128) + 16);
        if ( v10 )
        {
          ExFreePoolWithTag(v10, 0);
          *(_QWORD *)(v9 + *(_QWORD *)(a1 + 1128) + 16) = 0;
        }
      }
      ExFreePoolWithTag(*(PVOID *)(a1 + 1128), 0);
      *(_QWORD *)(a1 + 1128) = 0;
    }
    v11 = *(void **)(a1 + 1112);
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0);
      *(_QWORD *)(a1 + 1112) = 0;
    }
    v12 = *(IRP **)(a1 + 144);
    if ( v12 )
    {
      IoFreeIrp(v12);
      *(_QWORD *)(a1 + 144) = 0;
    }
    v13 = *(IRP **)(a1 + 168);
    if ( v13 )
      IoFreeIrp(v13);
    if ( *(_QWORD *)(a1 + 1176) )
    {
      v14 = 0;
      if ( *(_WORD *)(a1 + 1280) )
      {
        v15 = (USBD_HANDLE *)(a1 + 1272);
        do
        {
          v16 = 224LL * v14;
          v17 = *(IRP **)(v16 + *(_QWORD *)(a1 + 1176) + 112);
          if ( v17 )
          {
            IoFreeIrp(v17);
            v15 = (USBD_HANDLE *)(a1 + 1272);
            *(_QWORD *)(v16 + *(_QWORD *)(a1 + 1176) + 112) = 0;
          }
          v18 = *(struct _URB **)(v16 + *(_QWORD *)(a1 + 1176) + 80);
          if ( v18 )
          {
            v15 = (USBD_HANDLE *)(a1 + 1272);
            USBD_UrbFree(*(USBD_HANDLE *)(a1 + 1272), v18);
          }
          v19 = *(IRP **)(v16 + *(_QWORD *)(a1 + 1176) + 120);
          if ( v19 )
          {
            IoFreeIrp(v19);
            v15 = (USBD_HANDLE *)(a1 + 1272);
            *(_QWORD *)(v16 + *(_QWORD *)(a1 + 1176) + 120) = 0;
          }
          v20 = *(struct _URB **)(v16 + *(_QWORD *)(a1 + 1176) + 88);
          if ( v20 )
            USBD_UrbFree(*v15, v20);
          v21 = *(IRP **)(v16 + *(_QWORD *)(a1 + 1176) + 128);
          if ( v21 )
          {
            IoFreeIrp(v21);
            *(_QWORD *)(v16 + *(_QWORD *)(a1 + 1176) + 128) = 0;
          }
          v22 = *(struct _URB **)(v16 + *(_QWORD *)(a1 + 1176) + 96);
          if ( v22 )
            USBD_UrbFree(*v15, v22);
          v23 = *(IRP **)(v16 + *(_QWORD *)(a1 + 1176) + 136);
          if ( v23 )
          {
            IoFreeIrp(v23);
            *(_QWORD *)(v16 + *(_QWORD *)(a1 + 1176) + 136) = 0;
          }
          v24 = *(struct _URB **)(v16 + *(_QWORD *)(a1 + 1176) + 104);
          if ( v24 )
            USBD_UrbFree(*v15, v24);
          else
            v15 = (USBD_HANDLE *)(a1 + 1272);
          ++v14;
        }
        while ( v14 < *(_WORD *)(a1 + 1280) );
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v25 = *(void **)(a1 + 32);
    if ( v25 )
    {
      ExFreePoolWithTag(v25, 0);
      *(_QWORD *)(a1 + 32) = 0;
    }
    v26 = *(void **)(a1 + 40);
    if ( v26 )
    {
      ExFreePoolWithTag(v26, 0);
      *(_QWORD *)(a1 + 40) = 0;
    }
    v27 = *(void **)(a1 + 56);
    if ( v27 )
    {
      ExFreePoolWithTag(v27, 0);
      *(_QWORD *)(a1 + 56) = 0;
    }
    v28 = *(void **)(a1 + 72);
    if ( v28 )
    {
      ExFreePoolWithTag(v28, 0);
      *(_QWORD *)(a1 + 72) = 0;
    }
    v29 = *(_QWORD *)(a1 + 1272);
    if ( v29 )
    {
      *(_BYTE *)(v29 + 225) = 1;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v29 + 220), 0xFFFFFFFF) <= 1 )
      {
        if ( *(_BYTE *)(v29 + 225) )
        {
          v30 = *(void (__fastcall **)(_QWORD))(v29 + 112);
          if ( v30 )
            v30(*(_QWORD *)(v29 + 48));
          ExFreePoolWithTag((PVOID)v29, *(_DWORD *)(v29 + 64));
        }
        else if ( g_EnableDbgPrints )
        {
          DbgPrintEx(
            0x4Du,
            0,
            "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n",
            (const void *)v29);
        }
      }
      *(_QWORD *)(a1 + 1272) = 0;
    }
    v31 = *(void **)(a1 + 1152);
    if ( v31 )
    {
      ExFreePoolWithTag(v31, 0);
      *(_QWORD *)(a1 + 1152) = 0;
    }
    v32 = *(void **)(a1 + 1184);
    if ( v32 )
    {
      ExFreePoolWithTag(v32, 0);
      *(_QWORD *)(a1 + 1184) = 0;
    }
    v33 = *(void **)(a1 + 1176);
    if ( v33 )
    {
      ExFreePoolWithTag(v33, 0);
      *(_QWORD *)(a1 + 1176) = 0;
    }
    v34 = *(void **)(a1 + 1224);
    if ( v34 )
    {
      ExFreePoolWithTag(v34, 0);
      *(_QWORD *)(a1 + 1224) = 0;
    }
    v35 = *(_QWORD *)(a1 + 1400);
    if ( v35 )
    {
      ExFreePoolWithTag(*(PVOID *)(v35 + 24), 0);
      ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(a1 + 1400) + 32LL), 0);
      ExFreePoolWithTag(*(PVOID *)(a1 + 1400), 0);
      *(_QWORD *)(a1 + 1400) = 0;
    }
    v36 = *(struct _MDL **)(a1 + 1432);
    if ( v36 )
    {
      IoFreeMdl(v36);
      *(_QWORD *)(a1 + 1432) = 0;
    }
    FreeReservedMDLs(a1);
    v37 = *(struct _IO_WORKITEM **)(a1 + 200);
    if ( v37 )
    {
      IoFreeWorkItem(v37);
      *(_QWORD *)(a1 + 200) = 0;
    }
    *(_BYTE *)a1 &= ~2u;
  }
}

```

## disassembly

```asm
0x140003618  push    rbx
0x14000361a  push    rbp
0x14000361b  push    rsi
0x14000361c  push    rdi
0x14000361d  push    r12
0x14000361f  push    r14
0x140003621  push    r15
0x140003623  sub     rsp, 60h
0x140003627  xor     eax, eax
0x140003629  movzx   ebp, dl
0x14000362c  xor     r15d, r15d
0x14000362f  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x140003634  cmp     cs:gTracingEnabled, r15b
0x14000363b  lea     r14, WPP_RECORDER_INITIALIZED
0x140003642  xorps   xmm0, xmm0
0x140003645  mov     rsi, rcx
0x140003648  lea     r12d, [rax+1]
0x14000364c  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140003651  jz      short loc_14000368C
0x140003653  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000365a  jz      short loc_14000368C
0x14000365c  movzx   edi, byte ptr [rcx]
0x14000365f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003666  shr     edi, 1
0x140003668  and     edi, r12d
0x14000366b  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140003672  nop     dword ptr [rax+rax+00h]
0x140003677  mov     [rsp+98h+var_60], edi
0x14000367b  mov     rcx, rax
0x14000367e  mov     [rsp+98h+var_68], ebp
0x140003682  mov     [rsp+98h+var_70], rsi
0x140003687  call    WPP_RECORDER_SF_qDD
0x14000368c  lea     rcx, [rsi+508h]; RunRef
0x140003693  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14000369a  nop     dword ptr [rax+rax+00h]
0x14000369f  test    byte ptr [rsi], 2
0x1400036a2  jz      loc_140003B73
0x1400036a8  lea     rcx, [rsi+580h]; Object
0x1400036af  mov     [rsp+98h+Timeout], r15; Timeout
0x1400036b4  xor     r9d, r9d; Alertable
0x1400036b7  xor     r8d, r8d; WaitMode
0x1400036ba  xor     edx, edx; WaitReason
0x1400036bc  call    cs:__imp_KeWaitForSingleObject
0x1400036c3  nop     dword ptr [rax+rax+00h]
0x1400036c8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400036cf  jz      short loc_140003700
0x1400036d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036d8  cmp     [rcx+48h], r15w
0x1400036dd  jz      short loc_140003700
0x1400036df  mov     rcx, [rcx+40h]
0x1400036e3  lea     rax, WPP_5439ef5302de3287b9b5be8f6c06671c_Traceguids
0x1400036ea  mov     r9d, 15h
0x1400036f0  mov     [rsp+98h+Timeout], rax
0x1400036f5  xor     edx, edx
0x1400036f7  lea     r8d, [r9-12h]
0x1400036fb  call    WPP_RECORDER_SF_
0x140003700  or      byte ptr [rsi], 4
0x140003703  lea     rcx, [rsi+4D8h]; SpinLock
0x14000370a  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x14000370f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003716  nop     dword ptr [rax+rax+00h]
0x14000371b  mov     [rsi+4E0h], r12d
0x140003722  test    bpl, bpl
0x140003725  jz      short loc_140003794
0x140003727  cmp     [rsi+468h], r15
0x14000372e  jz      short loc_140003794
0x140003730  mov     ebx, r15d
0x140003733  cmp     [rsi+3E8h], r15d
0x14000373a  jbe     short loc_140003778
0x14000373c  mov     rax, [rsi+468h]
0x140003743  mov     edi, ebx
0x140003745  shl     rdi, 5
0x140003749  mov     rcx, [rdi+rax+10h]; P
0x14000374e  test    rcx, rcx
0x140003751  jz      short loc_14000376D
0x140003753  xor     edx, edx; Tag
0x140003755  call    cs:__imp_ExFreePoolWithTag
0x14000375c  nop     dword ptr [rax+rax+00h]
0x140003761  mov     rax, [rsi+468h]
0x140003768  mov     [rdi+rax+10h], r15
0x14000376d  add     ebx, r12d
0x140003770  cmp     ebx, [rsi+3E8h]
0x140003776  jb      short loc_14000373C
0x140003778  mov     rcx, [rsi+468h]; P
0x14000377f  xor     edx, edx; Tag
0x140003781  call    cs:__imp_ExFreePoolWithTag
0x140003788  nop     dword ptr [rax+rax+00h]
0x14000378d  mov     [rsi+468h], r15
0x140003794  mov     rcx, [rsi+458h]; P
0x14000379b  test    rcx, rcx
0x14000379e  jz      short loc_1400037B5
0x1400037a0  xor     edx, edx; Tag
0x1400037a2  call    cs:__imp_ExFreePoolWithTag
0x1400037a9  nop     dword ptr [rax+rax+00h]
0x1400037ae  mov     [rsi+458h], r15
0x1400037b5  mov     rcx, [rsi+90h]; Irp
0x1400037bc  test    rcx, rcx
0x1400037bf  jz      short loc_1400037D4
0x1400037c1  call    cs:__imp_IoFreeIrp
0x1400037c8  nop     dword ptr [rax+rax+00h]
0x1400037cd  mov     [rsi+90h], r15
0x1400037d4  mov     rcx, [rsi+0A8h]; Irp
0x1400037db  test    rcx, rcx
0x1400037de  jz      short loc_1400037EC
0x1400037e0  call    cs:__imp_IoFreeIrp
0x1400037e7  nop     dword ptr [rax+rax+00h]
0x1400037ec  cmp     [rsi+498h], r15
0x1400037f3  jz      loc_140003959
0x1400037f9  mov     ebp, r15d
0x1400037fc  cmp     r15w, [rsi+500h]
0x140003804  jnb     loc_140003959
0x14000380a  lea     r14, [rsi+4F8h]
0x140003811  mov     rdi, r14
0x140003814  movzx   eax, bp
0x140003817  imul    rbx, rax, 0E0h
0x14000381e  mov     rax, [rsi+498h]
0x140003825  mov     rcx, [rbx+rax+70h]; Irp
0x14000382a  test    rcx, rcx
0x14000382d  jz      short loc_14000384A
0x14000382f  call    cs:__imp_IoFreeIrp
0x140003836  nop     dword ptr [rax+rax+00h]
0x14000383b  mov     rax, [rsi+498h]
0x140003842  mov     rdi, r14
0x140003845  mov     [rbx+rax+70h], r15
0x14000384a  mov     rax, [rsi+498h]
0x140003851  mov     rdx, [rbx+rax+50h]; Urb
0x140003856  test    rdx, rdx
0x140003859  jz      short loc_14000386A
0x14000385b  lea     rdi, [rsi+4F8h]
0x140003862  mov     rcx, [rdi]; USBDHandle
0x140003865  call    USBD_UrbFree
0x14000386a  mov     rax, [rsi+498h]
0x140003871  mov     rcx, [rbx+rax+78h]; Irp
0x140003876  test    rcx, rcx
0x140003879  jz      short loc_140003896
0x14000387b  call    cs:__imp_IoFreeIrp
0x140003882  nop     dword ptr [rax+rax+00h]
0x140003887  mov     rax, [rsi+498h]
0x14000388e  mov     rdi, r14
0x140003891  mov     [rbx+rax+78h], r15
0x140003896  mov     rax, [rsi+498h]
0x14000389d  mov     rdx, [rbx+rax+58h]; Urb
0x1400038a2  test    rdx, rdx
0x1400038a5  jz      short loc_1400038AF
0x1400038a7  mov     rcx, [rdi]; USBDHandle
0x1400038aa  call    USBD_UrbFree
0x1400038af  mov     rax, [rsi+498h]
0x1400038b6  mov     rcx, [rbx+rax+80h]; Irp
0x1400038be  test    rcx, rcx
0x1400038c1  jz      short loc_1400038DE
0x1400038c3  call    cs:__imp_IoFreeIrp
0x1400038ca  nop     dword ptr [rax+rax+00h]
0x1400038cf  mov     rax, [rsi+498h]
0x1400038d6  mov     [rbx+rax+80h], r15
0x1400038de  mov     rax, [rsi+498h]
0x1400038e5  mov     rdx, [rbx+rax+60h]; Urb
0x1400038ea  test    rdx, rdx
0x1400038ed  jz      short loc_1400038F7
0x1400038ef  mov     rcx, [rdi]; USBDHandle
0x1400038f2  call    USBD_UrbFree
0x1400038f7  mov     rax, [rsi+498h]
0x1400038fe  mov     rcx, [rbx+rax+88h]; Irp
0x140003906  test    rcx, rcx
0x140003909  jz      short loc_140003926
0x14000390b  call    cs:__imp_IoFreeIrp
0x140003912  nop     dword ptr [rax+rax+00h]
0x140003917  mov     rax, [rsi+498h]
0x14000391e  mov     [rbx+rax+88h], r15
0x140003926  mov     rax, [rsi+498h]
0x14000392d  mov     rdx, [rbx+rax+68h]; Urb
0x140003932  test    rdx, rdx
0x140003935  jz      short loc_140003941
0x140003937  mov     rcx, [rdi]; USBDHandle
0x14000393a  call    USBD_UrbFree
0x14000393f  jmp     short loc_140003948
0x140003941  lea     rdi, [rsi+4F8h]
0x140003948  add     bp, r12w
0x14000394c  cmp     bp, [rsi+500h]
0x140003953  jb      loc_140003814
0x140003959  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x14000395e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003965  nop     dword ptr [rax+rax+00h]
0x14000396a  mov     rcx, [rsi+20h]; P
0x14000396e  test    rcx, rcx
0x140003971  jz      short loc_140003985
0x140003973  xor     edx, edx; Tag
0x140003975  call    cs:__imp_ExFreePoolWithTag
0x14000397c  nop     dword ptr [rax+rax+00h]
0x140003981  mov     [rsi+20h], r15
0x140003985  mov     rcx, [rsi+28h]; P
0x140003989  test    rcx, rcx
0x14000398c  jz      short loc_1400039A0
0x14000398e  xor     edx, edx; Tag
0x140003990  call    cs:__imp_ExFreePoolWithTag
0x140003997  nop     dword ptr [rax+rax+00h]
0x14000399c  mov     [rsi+28h], r15
0x1400039a0  mov     rcx, [rsi+38h]; P
0x1400039a4  test    rcx, rcx
0x1400039a7  jz      short loc_1400039BB
0x1400039a9  xor     edx, edx; Tag
0x1400039ab  call    cs:__imp_ExFreePoolWithTag
0x1400039b2  nop     dword ptr [rax+rax+00h]
0x1400039b7  mov     [rsi+38h], r15
0x1400039bb  mov     rcx, [rsi+48h]; P
0x1400039bf  test    rcx, rcx
0x1400039c2  jz      short loc_1400039D6
0x1400039c4  xor     edx, edx; Tag
0x1400039c6  call    cs:__imp_ExFreePoolWithTag
0x1400039cd  nop     dword ptr [rax+rax+00h]
0x1400039d2  mov     [rsi+48h], r15
0x1400039d6  mov     rbx, [rsi+4F8h]
0x1400039dd  test    rbx, rbx
0x1400039e0  jz      short loc_140003A53
0x1400039e2  mov     [rbx+0E1h], r12b
0x1400039e9  or      eax, 0FFFFFFFFh
0x1400039ec  lock xadd [rbx+0DCh], eax
0x1400039f4  sub     eax, r12d
0x1400039f7  jg      short loc_140003A4C
0x1400039f9  cmp     [rbx+0E1h], r15b
0x140003a00  jnz     short loc_140003A28
0x140003a02  cmp     cs:g_EnableDbgPrints, r15b
0x140003a09  jz      short loc_140003A4C
0x140003a0b  xor     edx, edx; Level
0x140003a0d  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x140003a14  mov     r9, rbx
0x140003a17  lea     ecx, [rdx+4Dh]; ComponentId
0x140003a1a  call    cs:__imp_DbgPrintEx
0x140003a21  nop     dword ptr [rax+rax+00h]
0x140003a26  jmp     short loc_140003A4C
0x140003a28  mov     rax, [rbx+70h]
0x140003a2c  test    rax, rax
0x140003a2f  jz      short loc_140003A3A
0x140003a31  mov     rcx, [rbx+30h]
0x140003a35  call    _guard_dispatch_icall
0x140003a3a  mov     edx, [rbx+40h]; Tag
0x140003a3d  mov     rcx, rbx; P
0x140003a40  call    cs:__imp_ExFreePoolWithTag
0x140003a47  nop     dword ptr [rax+rax+00h]
0x140003a4c  mov     [rsi+4F8h], r15
0x140003a53  mov     rcx, [rsi+480h]; P
0x140003a5a  test    rcx, rcx
0x140003a5d  jz      short loc_140003A74
0x140003a5f  xor     edx, edx; Tag
0x140003a61  call    cs:__imp_ExFreePoolWithTag
0x140003a68  nop     dword ptr [rax+rax+00h]
0x140003a6d  mov     [rsi+480h], r15
0x140003a74  mov     rcx, [rsi+4A0h]; P
0x140003a7b  test    rcx, rcx
0x140003a7e  jz      short loc_140003A95
0x140003a80  xor     edx, edx; Tag
0x140003a82  call    cs:__imp_ExFreePoolWithTag
0x140003a89  nop     dword ptr [rax+rax+00h]
0x140003a8e  mov     [rsi+4A0h], r15
0x140003a95  mov     rcx, [rsi+498h]; P
0x140003a9c  test    rcx, rcx
0x140003a9f  jz      short loc_140003AB6
0x140003aa1  xor     edx, edx; Tag
0x140003aa3  call    cs:__imp_ExFreePoolWithTag
0x140003aaa  nop     dword ptr [rax+rax+00h]
0x140003aaf  mov     [rsi+498h], r15
0x140003ab6  mov     rcx, [rsi+4C8h]; P
0x140003abd  test    rcx, rcx
0x140003ac0  jz      short loc_140003AD7
0x140003ac2  xor     edx, edx; Tag
0x140003ac4  call    cs:__imp_ExFreePoolWithTag
0x140003acb  nop     dword ptr [rax+rax+00h]
0x140003ad0  mov     [rsi+4C8h], r15
0x140003ad7  mov     rcx, [rsi+578h]
0x140003ade  test    rcx, rcx
0x140003ae1  jz      short loc_140003B2A
0x140003ae3  mov     rcx, [rcx+18h]; P
0x140003ae7  xor     edx, edx; Tag
0x140003ae9  call    cs:__imp_ExFreePoolWithTag
0x140003af0  nop     dword ptr [rax+rax+00h]
0x140003af5  mov     rcx, [rsi+578h]
0x140003afc  xor     edx, edx; Tag
0x140003afe  mov     rcx, [rcx+20h]; P
0x140003b02  call    cs:__imp_ExFreePoolWithTag
0x140003b09  nop     dword ptr [rax+rax+00h]
0x140003b0e  mov     rcx, [rsi+578h]; P
0x140003b15  xor     edx, edx; Tag
0x140003b17  call    cs:__imp_ExFreePoolWithTag
0x140003b1e  nop     dword ptr [rax+rax+00h]
0x140003b23  mov     [rsi+578h], r15
0x140003b2a  mov     rcx, [rsi+598h]; Mdl
0x140003b31  test    rcx, rcx
0x140003b34  jz      short loc_140003B49
0x140003b36  call    cs:__imp_IoFreeMdl
0x140003b3d  nop     dword ptr [rax+rax+00h]
0x140003b42  mov     [rsi+598h], r15
0x140003b49  mov     rcx, rsi
0x140003b4c  call    FreeReservedMDLs
0x140003b51  mov     rcx, [rsi+0C8h]; IoWorkItem
0x140003b58  test    rcx, rcx
0x140003b5b  jz      short loc_140003B70
0x140003b5d  call    cs:__imp_IoFreeWorkItem
0x140003b64  nop     dword ptr [rax+rax+00h]
0x140003b69  mov     [rsi+0C8h], r15
0x140003b70  and     byte ptr [rsi], 0FDh
0x140003b73  add     rsp, 60h
  ... truncated ...
```
