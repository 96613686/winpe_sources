# Streaming::StreamFault::StreamFault(_FLT_CALLBACK_DATA &,_FLT_INSTANCE *,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,_FILE_OBJECT &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,long &)

- ea: `0x14000be10`
- end: `0x14000bfdc`
- name: `??0StreamFault@Streaming@@QEAA@AEAU_FLT_CALLBACK_DATA@@PEAU_FLT_INSTANCE@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@AEAU_FILE_OBJECT@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@567@AEAJ@Z`
- size: `460`
- prototype: `__int64 __fastcall(__int64, struct _FLT_CALLBACK_DATA *, struct _FLT_INSTANCE *, PFLT_CONTEXT *, PVOID Object, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000db88`

## callees

- `0x140003650`
- `0x140005e3c`
- `0x14000a1ac`
- `0x14000be10`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14000be57`
- `ntoskrnl!EtwActivityIdControl` at `0x14000be57`
- `ntoskrnl!ObfReferenceObject` at `0x14000bf7b`
- `ntoskrnl!ObfReferenceObject` at `0x14000bf7b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bf90`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bf90`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000be99`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000be99`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000beec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000beec`
- `ntoskrnl!ExAllocatePool2` at `0x14000bed2`
- `ntoskrnl!ExAllocatePool2` at `0x14000bed2`
- `FLTMGR!FltCbdqInsertIo` at `0x14000bf31`
- `FLTMGR!FltCbdqInsertIo` at `0x14000bf31`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x14000bf0f`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x14000bf0f`
- `FLTMGR!FltReferenceContext` at `0x14000bf4a`
- `FLTMGR!FltReferenceContext` at `0x14000bf4a`
- `FLTMGR!FltReleaseContext` at `0x14000bf61`
- `FLTMGR!FltReleaseContext` at `0x14000bf61`

## pseudocode

```c
__int64 __fastcall Streaming::StreamFault::StreamFault(
        __int64 a1,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_INSTANCE *a3,
        PFLT_CONTEXT *a4,
        PVOID Object,
        __int64 a6,
        int *a7)
{
  struct Streaming::InstanceContext *v7; // rbp
  Streaming::InstanceContextFactory *v12; // rcx
  int Context; // eax
  __int64 Pool2; // rax
  void *v15; // rcx
  __int64 v16; // rsi
  HANDLE RequestorProcessId; // rax
  IO_CSQ_IRP_CONTEXT *v18; // r8
  struct _FLT_CALLBACK_DATA_QUEUE *v19; // rcx
  NTSTATUS inserted; // eax
  PFLT_CONTEXT v21; // rsi
  void *v22; // rcx

  v7 = (struct Streaming::InstanceContext *)(a1 + 8);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  EtwActivityIdControl(3u, (LPGUID)(a1 + 48));
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      StrmFlt_STREAM_FAULT_START,
      a1 + 48);
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 80), 0);
  Context = Streaming::InstanceContextFactory::GetContext(v12, a3, v7);
  *a7 = Context;
  if ( Context >= 0 )
  {
    Pool2 = ExAllocatePool2(256, 24, 1668376179);
    v15 = *(void **)(a1 + 40);
    v16 = Pool2;
    if ( v15 )
      ExFreePoolWithTag(v15, 0);
    *(_QWORD *)(a1 + 40) = v16;
    if ( v16 )
    {
      RequestorProcessId = FltGetRequestorProcessIdEx(a2);
      v18 = *(IO_CSQ_IRP_CONTEXT **)(a1 + 40);
      v19 = (struct _FLT_CALLBACK_DATA_QUEUE *)(*(_QWORD *)v7 + 104LL);
      *(_QWORD *)(a1 + 96) = RequestorProcessId;
      inserted = FltCbdqInsertIo(v19, a2, v18, v18);
      *a7 = inserted;
      if ( inserted >= 0 )
      {
        FltReferenceContext(*a4);
        v21 = *a4;
        if ( *(_QWORD *)a1 )
          FltReleaseContext(*(PFLT_CONTEXT *)a1);
        *(_QWORD *)a1 = v21;
        ObfReferenceObject(Object);
        v22 = *(void **)(a1 + 16);
        if ( v22 )
          ObfDereferenceObject(v22);
        *(_QWORD *)(a1 + 16) = Object;
        *(_QWORD *)(a1 + 24) = a2->Iopb->Parameters.Read.ByteOffset.QuadPart;
        *(_DWORD *)(a1 + 32) = a2->Iopb->Parameters.Read.Length;
        *a7 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
                a1 + 64,
                a6);
      }
    }
    else
    {
      *a7 = -1073741670;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14000be10  push    rbx
0x14000be12  push    rbp
0x14000be13  push    rsi
0x14000be14  push    rdi
0x14000be15  push    r13
0x14000be17  push    r14
0x14000be19  push    r15
0x14000be1b  sub     rsp, 20h
0x14000be1f  lea     rbp, [rcx+8]
0x14000be23  mov     qword ptr [rcx], 0
0x14000be2a  mov     r13, rdx
0x14000be2d  mov     qword ptr [rcx+10h], 0
0x14000be35  lea     rdx, [rcx+30h]; ActivityId
0x14000be39  mov     qword ptr [rcx+28h], 0
0x14000be41  mov     rbx, rcx
0x14000be44  mov     qword ptr [rbp+0], 0
0x14000be4c  mov     ecx, 3; ControlCode
0x14000be51  mov     r15, r9
0x14000be54  mov     rsi, r8
0x14000be57  call    cs:__imp_EtwActivityIdControl
0x14000be5e  nop     dword ptr [rax+rax+00h]
0x14000be63  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14000be6a  jz      short loc_14000BE83
0x14000be6c  lea     r8, [rbx+30h]
0x14000be70  lea     rdx, StrmFlt_STREAM_FAULT_START
0x14000be77  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14000be7e  call    McTemplateK0_EtwWriteTransfer
0x14000be83  lea     rcx, [rbx+50h]; DestinationString
0x14000be87  mov     qword ptr [rbx+40h], 0
0x14000be8f  xor     edx, edx; SourceString
0x14000be91  mov     qword ptr [rbx+48h], 0
0x14000be99  call    cs:__imp_RtlInitUnicodeString
0x14000bea0  nop     dword ptr [rax+rax+00h]
0x14000bea5  mov     r8, rbp; struct Streaming::InstanceContext *
0x14000bea8  mov     rdx, rsi; struct _FLT_INSTANCE *
0x14000beab  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x14000beb0  mov     rdi, [rsp+58h+arg_30]
0x14000beb8  mov     [rdi], eax
0x14000beba  test    eax, eax
0x14000bebc  js      loc_14000BFC9
0x14000bec2  mov     edx, 18h
0x14000bec7  mov     ecx, 100h
0x14000becc  mov     r8d, 63716673h
0x14000bed2  call    cs:__imp_ExAllocatePool2
0x14000bed9  nop     dword ptr [rax+rax+00h]
0x14000bede  mov     rcx, [rbx+28h]; P
0x14000bee2  mov     rsi, rax
0x14000bee5  test    rcx, rcx
0x14000bee8  jz      short loc_14000BEF8
0x14000beea  xor     edx, edx; Tag
0x14000beec  call    cs:__imp_ExFreePoolWithTag
0x14000bef3  nop     dword ptr [rax+rax+00h]
0x14000bef8  mov     [rbx+28h], rsi
0x14000befc  test    rsi, rsi
0x14000beff  jnz     short loc_14000BF0C
0x14000bf01  mov     dword ptr [rdi], 0C000009Ah
0x14000bf07  jmp     loc_14000BFC9
0x14000bf0c  mov     rcx, r13; CallbackData
0x14000bf0f  call    cs:__imp_FltGetRequestorProcessIdEx
0x14000bf16  nop     dword ptr [rax+rax+00h]
0x14000bf1b  mov     r8, [rbx+28h]; Context
0x14000bf1f  mov     rdx, r13; Cbd
0x14000bf22  mov     rcx, [rbp+0]
0x14000bf26  mov     r9, r8; InsertContext
0x14000bf29  add     rcx, 68h ; 'h'; Cbdq
0x14000bf2d  mov     [rbx+60h], rax
0x14000bf31  call    cs:__imp_FltCbdqInsertIo
0x14000bf38  nop     dword ptr [rax+rax+00h]
0x14000bf3d  mov     [rdi], eax
0x14000bf3f  test    eax, eax
0x14000bf41  js      loc_14000BFC9
0x14000bf47  mov     rcx, [r15]; Context
0x14000bf4a  call    cs:__imp_FltReferenceContext
0x14000bf51  nop     dword ptr [rax+rax+00h]
0x14000bf56  mov     rcx, [rbx]; Context
0x14000bf59  mov     rsi, [r15]
0x14000bf5c  test    rcx, rcx
0x14000bf5f  jz      short loc_14000BF6D
0x14000bf61  call    cs:__imp_FltReleaseContext
0x14000bf68  nop     dword ptr [rax+rax+00h]
0x14000bf6d  mov     [rbx], rsi
0x14000bf70  mov     rsi, [rsp+58h+Object]
0x14000bf78  mov     rcx, rsi; Object
0x14000bf7b  call    cs:__imp_ObfReferenceObject
0x14000bf82  nop     dword ptr [rax+rax+00h]
0x14000bf87  mov     rcx, [rbx+10h]; Object
0x14000bf8b  test    rcx, rcx
0x14000bf8e  jz      short loc_14000BF9C
0x14000bf90  call    cs:__imp_ObfDereferenceObject
0x14000bf97  nop     dword ptr [rax+rax+00h]
0x14000bf9c  mov     [rbx+10h], rsi
0x14000bfa0  lea     rcx, [rbx+40h]
0x14000bfa4  mov     rax, [r13+10h]
0x14000bfa8  mov     rdx, [rax+28h]
0x14000bfac  mov     [rbx+18h], rdx
0x14000bfb0  mov     rax, [r13+10h]
0x14000bfb4  mov     edx, [rax+18h]
0x14000bfb7  mov     [rbx+20h], edx
0x14000bfba  mov     rdx, [rsp+58h+arg_28]
0x14000bfc2  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &)
0x14000bfc7  mov     [rdi], eax
0x14000bfc9  mov     rax, rbx
0x14000bfcc  add     rsp, 20h
0x14000bfd0  pop     r15
0x14000bfd2  pop     r14
0x14000bfd4  pop     r13
0x14000bfd6  pop     rdi
0x14000bfd7  pop     rsi
0x14000bfd8  pop     rbp
0x14000bfd9  pop     rbx
0x14000bfda  retn
```
