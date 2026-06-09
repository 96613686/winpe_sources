# Streaming::PackageWriter::QueryAllocationRanges(_UNICODE_STRING const &,_UNICODE_STRING &,_FILE_ALLOCATED_RANGE_BUFFER const &,_FILE_ALLOCATED_RANGE_BUFFER * const,ulong,ulong &)

- ea: `0x140008dc4`
- end: `0x140009353`
- name: `?QueryAllocationRanges@PackageWriter@Streaming@@SAJAEBU_UNICODE_STRING@@AEAU3@AEBU_FILE_ALLOCATED_RANGE_BUFFER@@QEAU4@KAEAK@Z`
- size: `1423`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, struct _UNICODE_STRING *, const struct _FILE_ALLOCATED_RANGE_BUFFER *, struct _FILE_ALLOCATED_RANGE_BUFFER *const, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14001104c`

## callees

- `0x1400030b8`
- `0x140005ed8`
- `0x140008dc4`
- `0x14000ad80`
- `0x14000af6c`
- `0x14000bbd4`
- `0x1400147fc`
- `0x140014a50`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140008e51`
- `ntoskrnl!ObfDereferenceObject` at `0x140008ecb`
- `ntoskrnl!ObfDereferenceObject` at `0x140008f62`
- `ntoskrnl!ObfDereferenceObject` at `0x1400090a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000928a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400092fd`
- `ntoskrnl!ObfDereferenceObject` at `0x140008e51`
- `ntoskrnl!ObfDereferenceObject` at `0x140008ecb`
- `ntoskrnl!ObfDereferenceObject` at `0x140008f62`
- `ntoskrnl!ObfDereferenceObject` at `0x1400090a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000928a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400092fd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008dfa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008dfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000932d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400090d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000932d`
- `FLTMGR!FltClose` at `0x140008e38`
- `FLTMGR!FltClose` at `0x140008eb2`
- `FLTMGR!FltClose` at `0x140008f49`
- `FLTMGR!FltClose` at `0x14000908d`
- `FLTMGR!FltClose` at `0x140009271`
- `FLTMGR!FltClose` at `0x1400092e4`
- `FLTMGR!FltClose` at `0x140008e38`
- `FLTMGR!FltClose` at `0x140008eb2`
- `FLTMGR!FltClose` at `0x140008f49`
- `FLTMGR!FltClose` at `0x14000908d`
- `FLTMGR!FltClose` at `0x140009271`
- `FLTMGR!FltClose` at `0x1400092e4`
- `FLTMGR!FltReleaseContext` at `0x140008ee8`
- `FLTMGR!FltReleaseContext` at `0x140008f7b`
- `FLTMGR!FltReleaseContext` at `0x1400090bf`
- `FLTMGR!FltReleaseContext` at `0x1400091e8`
- `FLTMGR!FltReleaseContext` at `0x140009225`
- `FLTMGR!FltReleaseContext` at `0x14000925c`
- `FLTMGR!FltReleaseContext` at `0x1400092a3`
- `FLTMGR!FltReleaseContext` at `0x1400092cf`
- `FLTMGR!FltReleaseContext` at `0x140009316`
- `FLTMGR!FltReleaseContext` at `0x140008ee8`
- `FLTMGR!FltReleaseContext` at `0x140008f7b`
- `FLTMGR!FltReleaseContext` at `0x1400090bf`
- `FLTMGR!FltReleaseContext` at `0x1400091e8`
- `FLTMGR!FltReleaseContext` at `0x140009225`
- `FLTMGR!FltReleaseContext` at `0x14000925c`
- `FLTMGR!FltReleaseContext` at `0x1400092a3`
- `FLTMGR!FltReleaseContext` at `0x1400092cf`
- `FLTMGR!FltReleaseContext` at `0x140009316`

## string_xrefs

- `0x140008ff3`: `PackageWriter::QueryAllocationRanges() - Streaming Filter could not open file for streaming file %s. Failure status 0x%08X.`
- `0x14000914a`: `PackageWriter::QueryAllocationRanges() - Streaming filter could not track the streamable file '%s'. This can cause I/O failures. Please try to pre-stream the application. Failure status = 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::PackageWriter::QueryAllocationRanges(
        const struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        const struct _FILE_ALLOCATED_RANGE_BUFFER *a3,
        struct _FILE_ALLOCATED_RANGE_BUFFER *const a4,
        unsigned int a5,
        unsigned int *a6)
{
  int FileFullName; // ebx
  PERESOURCE *v12; // rcx
  struct _FLT_INSTANCE *v13; // rbx
  unsigned int AllocationRanges; // edi
  NTSTATUS v15; // esi
  __int64 v16; // rbx
  GUID **CurrentActivityID; // rax
  volatile signed __int32 *Buffer; // rdi
  volatile signed __int32 *v19; // rdi
  int v20; // eax
  __int64 v21; // rbx
  GUID **v22; // rax
  volatile signed __int32 *v23; // rdi
  volatile signed __int32 *v24; // rdi
  PFLT_CONTEXT v25; // rbx
  PFLT_CONTEXT v26; // rcx
  PHANDLE v27; // [rsp+20h] [rbp-69h]
  PHANDLE v28; // [rsp+20h] [rbp-69h]
  PVOID Object; // [rsp+30h] [rbp-59h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-51h] BYREF
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-49h] BYREF
  PFLT_CONTEXT v32; // [rsp+48h] [rbp-41h] BYREF
  __int64 v33; // [rsp+50h] [rbp-39h] BYREF
  PVOID P; // [rsp+58h] [rbp-31h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-29h] BYREF
  PFLT_INSTANCE Instance; // [rsp+70h] [rbp-19h] BYREF
  volatile signed __int32 *v37; // [rsp+78h] [rbp-11h]
  struct _UNICODE_STRING v38; // [rsp+80h] [rbp-9h] BYREF

  v33 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  Context = 0;
  Instance = 0;
  Object = 0;
  FileHandle = 0;
  v32 = 0;
  FileFullName = Streaming::Utils::GetFileFullName((__int64)a1, (__int64)a2, (__int64)&v33);
  if ( FileFullName < 0 )
  {
LABEL_2:
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)FileFullName;
  }
  v12 = (PERESOURCE *)*((_QWORD *)Streaming::gStrmFltData + 3);
  v38 = *a1;
  FileFullName = Streaming::InstanceContextFactory::GetContextByVolumeName(
                   v12,
                   &v38,
                   (POWNER_ENTRY *)&Instance,
                   (struct Streaming::InstanceContext *)&Context);
  if ( FileFullName < 0 )
  {
    if ( Context )
      FltReleaseContext(Context);
    goto LABEL_2;
  }
  v13 = Instance;
  AllocationRanges = -1073741772;
  v15 = Streaming::FileOperations::OpenFileForStreaming(
          *((struct _FLT_FILTER **)Streaming::gStrmFltData + 1),
          Instance,
          &DestinationString,
          (PFILE_OBJECT *)&Object,
          &FileHandle);
  if ( v15 == -1073741772 )
  {
    if ( (int)Streaming::StagingManager::StageFileUnsafe(v13, &DestinationString) < 0 )
    {
LABEL_10:
      if ( FileHandle )
      {
        FltClose(FileHandle);
        FileHandle = 0;
      }
      if ( Object )
      {
        ObfDereferenceObject(Object);
        Object = 0;
      }
      if ( Context )
        FltReleaseContext(Context);
      if ( P )
        ExFreePoolWithTag(P, 0);
      return AllocationRanges;
    }
    v15 = Streaming::FileOperations::OpenFileForStreaming(
            *((struct _FLT_FILTER **)Streaming::gStrmFltData + 1),
            v13,
            &DestinationString,
            (PFILE_OBJECT *)&Object,
            &FileHandle);
  }
  if ( v15 < 0 )
  {
    v16 = *Streaming::Utils::GetNullTerminated(&Instance, &DestinationString.Length);
    CurrentActivityID = Streaming::Utils::GetCurrentActivityID((GUID **)&v38);
    LODWORD(v27) = v15;
    LogWrite(
      1,
      *CurrentActivityID,
      L"PackageWriter::QueryAllocationRanges() - Streaming Filter could not open file for streaming file %s. Failure status 0x%08X.",
      v16,
      v27);
    Buffer = (volatile signed __int32 *)v38.Buffer;
    if ( v38.Buffer )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v38.Buffer + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 8LL))(Buffer);
        if ( _InterlockedExchangeAdd(Buffer + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 16LL))(Buffer);
      }
    }
    v19 = v37;
    if ( v37 )
    {
      if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
LABEL_29:
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    if ( Object )
    {
      ObfDereferenceObject(Object);
      Object = 0;
    }
    if ( Context )
      FltReleaseContext(Context);
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)v15;
  }
  v20 = Streaming::Context::StreamContextFactory::GetOrCreateStreamContext(
          v13,
          (Streaming::InstanceContext *)&Context,
          (const void **)a2,
          &DestinationString,
          (PFILE_OBJECT)Object,
          &v32);
  v15 = v20;
  if ( ((v20 + 1073741195) & 0xFFFFFFFD) != 0 )
  {
    if ( v20 >= 0 )
    {
      v25 = v32;
      AllocationRanges = Streaming::Context::StreamingBitmapBuilder::QueryAllocationRanges(
                           (PRTL_BITMAP *)v32 + 11,
                           *((_QWORD *)v32 + 10),
                           &a3->FileOffset,
                           (__int64)a4,
                           a5,
                           a6);
      FltReleaseContext(v25);
      goto LABEL_10;
    }
    v21 = *Streaming::Utils::GetNullTerminated(&Instance, &DestinationString.Length);
    v22 = Streaming::Utils::GetCurrentActivityID((GUID **)&v38);
    LODWORD(v28) = v15;
    LogWrite(
      1,
      *v22,
      L"PackageWriter::QueryAllocationRanges() - Streaming filter could not track the streamable file '%s'. This can cause"
       " I/O failures. Please try to pre-stream the application. Failure status = 0x%08X.",
      v21,
      v28);
    v23 = (volatile signed __int32 *)v38.Buffer;
    if ( v38.Buffer )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v38.Buffer + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    v24 = v37;
    if ( v37 )
    {
      if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
    if ( v32 )
      FltReleaseContext(v32);
    goto LABEL_29;
  }
  v26 = v32;
  if ( a5 )
  {
    *a6 = 1;
    *a4 = *a3;
    if ( v26 )
      FltReleaseContext(v26);
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    if ( Object )
    {
      ObfDereferenceObject(Object);
      Object = 0;
    }
    if ( Context )
      FltReleaseContext(Context);
    if ( P )
      ExFreePoolWithTag(P, 0);
    return 0;
  }
  else
  {
    if ( v32 )
      FltReleaseContext(v32);
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    if ( Object )
    {
      ObfDereferenceObject(Object);
      Object = 0;
    }
    if ( Context )
      FltReleaseContext(Context);
    if ( P )
      ExFreePoolWithTag(P, 0);
    return 261;
  }
}

```

## disassembly

```asm
0x140008dc4  push    rbp
0x140008dc6  push    rbx
0x140008dc7  push    rsi
0x140008dc8  push    rdi
0x140008dc9  push    r12
0x140008dcb  push    r13
0x140008dcd  push    r14
0x140008dcf  push    r15
0x140008dd1  lea     rbp, [rsp-0Fh]
0x140008dd6  sub     rsp, 98h
0x140008ddd  mov     r12, rdx
0x140008de0  mov     rdi, rcx
0x140008de3  xor     r13d, r13d
0x140008de6  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x140008dea  xor     edx, edx; SourceString
0x140008dec  mov     [rbp+47h+var_80], r13
0x140008df0  mov     [rbp+47h+P], r13
0x140008df4  mov     r14, r9
0x140008df7  mov     r15, r8
0x140008dfa  call    cs:__imp_RtlInitUnicodeString
0x140008e01  nop     dword ptr [rax+rax+00h]
0x140008e06  lea     r8, [rbp+47h+var_80]
0x140008e0a  mov     [rbp+47h+Context], r13
0x140008e0e  mov     rdx, r12
0x140008e11  mov     [rbp+47h+Instance], r13
0x140008e15  mov     rcx, rdi
0x140008e18  mov     [rbp+47h+Object], r13
0x140008e1c  mov     [rbp+47h+FileHandle], r13
0x140008e20  mov     [rbp+47h+var_88], r13
0x140008e24  call    ?GetFileFullName@Utils@Streaming@@YAJAEBU_UNICODE_STRING@@0AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Utils::GetFileFullName(_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140008e29  mov     ebx, eax
0x140008e2b  test    eax, eax
0x140008e2d  jns     short loc_140008E7F
0x140008e2f  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x140008e33  test    rcx, rcx
0x140008e36  jz      short loc_140008E48
0x140008e38  call    cs:__imp_FltClose
0x140008e3f  nop     dword ptr [rax+rax+00h]
0x140008e44  mov     [rbp+47h+FileHandle], r13
0x140008e48  mov     rcx, [rbp+47h+Object]; Object
0x140008e4c  test    rcx, rcx
0x140008e4f  jz      short loc_140008E61
0x140008e51  call    cs:__imp_ObfDereferenceObject
0x140008e58  nop     dword ptr [rax+rax+00h]
0x140008e5d  mov     [rbp+47h+Object], r13
0x140008e61  mov     rcx, [rbp+47h+P]; P
0x140008e65  test    rcx, rcx
0x140008e68  jz      short loc_140008E78
0x140008e6a  xor     edx, edx; Tag
0x140008e6c  call    cs:__imp_ExFreePoolWithTag
0x140008e73  nop     dword ptr [rax+rax+00h]
0x140008e78  mov     eax, ebx
0x140008e7a  jmp     loc_14000933E
0x140008e7f  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140008e86  lea     r9, [rbp+47h+Context]; struct Streaming::InstanceContext *
0x140008e8a  movups  xmm0, xmmword ptr [rdi]
0x140008e8d  lea     r8, [rbp+47h+Instance]; struct _FLT_INSTANCE **
0x140008e91  lea     rdx, [rbp+47h+var_50]; struct _UNICODE_STRING
0x140008e95  mov     rcx, [rcx+18h]; this
0x140008e99  movdqu  xmmword ptr [rbp+47h+var_50.Length], xmm0
0x140008e9e  call    ?GetContextByVolumeName@InstanceContextFactory@Streaming@@QEAAJU_UNICODE_STRING@@AEAPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContextByVolumeName(_UNICODE_STRING,_FLT_INSTANCE * &,Streaming::InstanceContext &)
0x140008ea3  mov     ebx, eax
0x140008ea5  test    eax, eax
0x140008ea7  jns     short loc_140008EF9
0x140008ea9  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x140008ead  test    rcx, rcx
0x140008eb0  jz      short loc_140008EC2
0x140008eb2  call    cs:__imp_FltClose
0x140008eb9  nop     dword ptr [rax+rax+00h]
0x140008ebe  mov     [rbp+47h+FileHandle], r13
0x140008ec2  mov     rcx, [rbp+47h+Object]; Object
0x140008ec6  test    rcx, rcx
0x140008ec9  jz      short loc_140008EDB
0x140008ecb  call    cs:__imp_ObfDereferenceObject
0x140008ed2  nop     dword ptr [rax+rax+00h]
0x140008ed7  mov     [rbp+47h+Object], r13
0x140008edb  mov     rcx, [rbp+47h+Context]; Context
0x140008edf  test    rcx, rcx
0x140008ee2  jz      loc_140008E61
0x140008ee8  call    cs:__imp_FltReleaseContext
0x140008eef  nop     dword ptr [rax+rax+00h]
0x140008ef4  jmp     loc_140008E61
0x140008ef9  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140008f00  lea     rax, [rbp+47h+FileHandle]
0x140008f04  mov     rbx, [rbp+47h+Instance]
0x140008f08  lea     r9, [rbp+47h+Object]; int
0x140008f0c  lea     r8, [rbp+47h+DestinationString]; int
0x140008f10  mov     [rsp+0D0h+var_B0], rax; FileHandle
0x140008f15  mov     rdx, rbx; int
0x140008f18  mov     rcx, [rcx+8]; int
0x140008f1c  call    ?OpenFileForStreaming@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEBU_UNICODE_STRING@@AEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z; Streaming::FileOperations::OpenFileForStreaming(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)
0x140008f21  mov     edi, 0C0000034h
0x140008f26  mov     esi, eax
0x140008f28  cmp     eax, edi
0x140008f2a  jnz     loc_140008FCB
0x140008f30  lea     rdx, [rbp+47h+DestinationString]; struct _UNICODE_STRING *
0x140008f34  mov     rcx, rbx; Instance
0x140008f37  call    ?StageFileUnsafe@StagingManager@Streaming@@SAJPEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@@Z; Streaming::StagingManager::StageFileUnsafe(_FLT_INSTANCE *,_UNICODE_STRING const &)
0x140008f3c  test    eax, eax
0x140008f3e  jns     short loc_140008FA5
0x140008f40  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x140008f44  test    rcx, rcx
0x140008f47  jz      short loc_140008F59
0x140008f49  call    cs:__imp_FltClose
0x140008f50  nop     dword ptr [rax+rax+00h]
0x140008f55  mov     [rbp+47h+FileHandle], r13
0x140008f59  mov     rcx, [rbp+47h+Object]; Object
0x140008f5d  test    rcx, rcx
0x140008f60  jz      short loc_140008F72
0x140008f62  call    cs:__imp_ObfDereferenceObject
0x140008f69  nop     dword ptr [rax+rax+00h]
0x140008f6e  mov     [rbp+47h+Object], r13
0x140008f72  mov     rcx, [rbp+47h+Context]; Context
0x140008f76  test    rcx, rcx
0x140008f79  jz      short loc_140008F87
0x140008f7b  call    cs:__imp_FltReleaseContext
0x140008f82  nop     dword ptr [rax+rax+00h]
0x140008f87  mov     rcx, [rbp+47h+P]; P
0x140008f8b  test    rcx, rcx
0x140008f8e  jz      short loc_140008F9E
0x140008f90  xor     edx, edx; Tag
0x140008f92  call    cs:__imp_ExFreePoolWithTag
0x140008f99  nop     dword ptr [rax+rax+00h]
0x140008f9e  mov     eax, edi
0x140008fa0  jmp     loc_14000933E
0x140008fa5  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140008fac  lea     rax, [rbp+47h+FileHandle]
0x140008fb0  lea     r9, [rbp+47h+Object]; int
0x140008fb4  mov     [rsp+0D0h+var_B0], rax; FileHandle
0x140008fb9  lea     r8, [rbp+47h+DestinationString]; int
0x140008fbd  mov     rdx, rbx; int
0x140008fc0  mov     rcx, [rcx+8]; int
0x140008fc4  call    ?OpenFileForStreaming@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEBU_UNICODE_STRING@@AEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z; Streaming::FileOperations::OpenFileForStreaming(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)
0x140008fc9  mov     esi, eax
0x140008fcb  test    esi, esi
0x140008fcd  jns     loc_1400090E9
0x140008fd3  lea     rdx, [rbp+47h+DestinationString]
0x140008fd7  lea     rcx, [rbp+47h+Instance]
0x140008fdb  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008fe0  lea     rcx, [rbp+47h+var_50]
0x140008fe4  mov     rbx, [rax]
0x140008fe7  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140008fec  mov     r9, rbx
0x140008fef  mov     dword ptr [rsp+0D0h+var_B0], esi
0x140008ff3  lea     r8, aPackagewriterQ; "PackageWriter::QueryAllocationRanges() "...
0x140008ffa  mov     ecx, 1
0x140008fff  mov     rdx, [rax]
0x140009002  call    LogWrite
0x140009007  mov     rdi, [rbp+47h+var_50.Buffer]
0x14000900b  or      ebx, 0FFFFFFFFh
0x14000900e  test    rdi, rdi
0x140009011  jz      short loc_140009047
0x140009013  mov     eax, ebx
0x140009015  lock xadd [rdi+8], eax
0x14000901a  add     eax, ebx
0x14000901c  jnz     short loc_140009047
0x14000901e  mov     rax, [rdi]
0x140009021  mov     rcx, rdi
0x140009024  mov     rax, [rax+8]
0x140009028  call    _guard_dispatch_icall
0x14000902d  mov     eax, ebx
0x14000902f  lock xadd [rdi+0Ch], eax
0x140009034  add     eax, ebx
0x140009036  jnz     short loc_140009047
0x140009038  mov     rax, [rdi]
0x14000903b  mov     rcx, rdi
0x14000903e  mov     rax, [rax+10h]
0x140009042  call    _guard_dispatch_icall
0x140009047  mov     rdi, [rbp+47h+var_58]
0x14000904b  test    rdi, rdi
0x14000904e  jz      short loc_140009084
0x140009050  mov     eax, ebx
0x140009052  lock xadd [rdi+8], eax
0x140009057  add     eax, ebx
0x140009059  jnz     short loc_140009084
0x14000905b  mov     rax, [rdi]
0x14000905e  mov     rcx, rdi
0x140009061  mov     rax, [rax+8]
0x140009065  call    _guard_dispatch_icall
0x14000906a  mov     eax, ebx
0x14000906c  lock xadd [rdi+0Ch], eax
0x140009071  add     eax, ebx
0x140009073  jnz     short loc_140009084
0x140009075  mov     rax, [rdi]
0x140009078  mov     rcx, rdi
0x14000907b  mov     rax, [rax+10h]
0x14000907f  call    _guard_dispatch_icall
0x140009084  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x140009088  test    rcx, rcx
0x14000908b  jz      short loc_14000909D
0x14000908d  call    cs:__imp_FltClose
0x140009094  nop     dword ptr [rax+rax+00h]
0x140009099  mov     [rbp+47h+FileHandle], r13
0x14000909d  mov     rcx, [rbp+47h+Object]; Object
0x1400090a1  test    rcx, rcx
0x1400090a4  jz      short loc_1400090B6
0x1400090a6  call    cs:__imp_ObfDereferenceObject
0x1400090ad  nop     dword ptr [rax+rax+00h]
0x1400090b2  mov     [rbp+47h+Object], r13
0x1400090b6  mov     rcx, [rbp+47h+Context]; Context
0x1400090ba  test    rcx, rcx
0x1400090bd  jz      short loc_1400090CB
0x1400090bf  call    cs:__imp_FltReleaseContext
0x1400090c6  nop     dword ptr [rax+rax+00h]
0x1400090cb  mov     rcx, [rbp+47h+P]; P
0x1400090cf  test    rcx, rcx
0x1400090d2  jz      short loc_1400090E2
0x1400090d4  xor     edx, edx; Tag
0x1400090d6  call    cs:__imp_ExFreePoolWithTag
0x1400090dd  nop     dword ptr [rax+rax+00h]
0x1400090e2  mov     eax, esi
0x1400090e4  jmp     loc_14000933E
0x1400090e9  mov     rax, [rbp+47h+Object]
0x1400090ed  lea     rcx, [rbp+47h+var_88]
0x1400090f1  mov     [rsp+0D0h+var_A8], rcx; __int64
0x1400090f6  lea     r9, [rbp+47h+DestinationString]
0x1400090fa  mov     rcx, rbx; Instance
0x1400090fd  mov     [rsp+0D0h+var_B0], rax; FileObject
0x140009102  mov     r8, r12
0x140009105  lea     rdx, [rbp+47h+Context]; this
0x140009109  call    ?GetOrCreateStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@3@AEBU_UNICODE_STRING@@2AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::GetOrCreateStreamContext(_FLT_INSTANCE *,Streaming::InstanceContext &,_UNICODE_STRING const &,_UNICODE_STRING const &,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x14000910e  mov     esi, eax
0x140009110  lea     ecx, [rax+3FFFFD8Bh]
0x140009116  test    ecx, 0FFFFFFFDh
0x14000911c  jz      loc_140009236
0x140009122  test    eax, eax
0x140009124  jns     loc_1400091F9
0x14000912a  lea     rdx, [rbp+47h+DestinationString]
0x14000912e  lea     rcx, [rbp+47h+Instance]
0x140009132  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140009137  lea     rcx, [rbp+47h+var_50]
0x14000913b  mov     rbx, [rax]
0x14000913e  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140009143  mov     r9, rbx
0x140009146  mov     dword ptr [rsp+0D0h+var_B0], esi
0x14000914a  lea     r8, aPackagewriterQ_0; "PackageWriter::QueryAllocationRanges() "...
0x140009151  mov     ecx, 1
0x140009156  mov     rdx, [rax]
0x140009159  call    LogWrite
0x14000915e  mov     rdi, [rbp+47h+var_50.Buffer]
0x140009162  or      ebx, 0FFFFFFFFh
0x140009165  test    rdi, rdi
0x140009168  jz      short loc_14000919E
0x14000916a  mov     eax, ebx
0x14000916c  lock xadd [rdi+8], eax
0x140009171  add     eax, ebx
0x140009173  jnz     short loc_14000919E
0x140009175  mov     rax, [rdi]
0x140009178  mov     rcx, rdi
0x14000917b  mov     rax, [rax+8]
0x14000917f  call    _guard_dispatch_icall
0x140009184  mov     eax, ebx
0x140009186  lock xadd [rdi+0Ch], eax
0x14000918b  add     eax, ebx
0x14000918d  jnz     short loc_14000919E
0x14000918f  mov     rax, [rdi]
0x140009192  mov     rcx, rdi
0x140009195  mov     rax, [rax+10h]
0x140009199  call    _guard_dispatch_icall
0x14000919e  mov     rdi, [rbp+47h+var_58]
0x1400091a2  test    rdi, rdi
0x1400091a5  jz      short loc_1400091DB
0x1400091a7  mov     eax, ebx
0x1400091a9  lock xadd [rdi+8], eax
0x1400091ae  add     eax, ebx
0x1400091b0  jnz     short loc_1400091DB
0x1400091b2  mov     rax, [rdi]
0x1400091b5  mov     rcx, rdi
0x1400091b8  mov     rax, [rax+8]
0x1400091bc  call    _guard_dispatch_icall
0x1400091c1  mov     eax, ebx
0x1400091c3  lock xadd [rdi+0Ch], eax
0x1400091c8  add     eax, ebx
0x1400091ca  jnz     short loc_1400091DB
0x1400091cc  mov     rax, [rdi]
0x1400091cf  mov     rcx, rdi
0x1400091d2  mov     rax, [rax+10h]
0x1400091d6  call    _guard_dispatch_icall
0x1400091db  mov     rcx, [rbp+47h+var_88]; Context
0x1400091df  test    rcx, rcx
0x1400091e2  jz      loc_140009084
0x1400091e8  call    cs:__imp_FltReleaseContext
0x1400091ef  nop     dword ptr [rax+rax+00h]
0x1400091f4  jmp     loc_140009084
0x1400091f9  mov     rax, [rbp+47h+arg_28]
0x1400091fd  mov     r9, r14
0x140009200  mov     rbx, [rbp+47h+var_88]
0x140009204  mov     r8, r15
0x140009207  mov     [rsp+0D0h+var_A8], rax
0x14000920c  mov     eax, [rbp+47h+arg_20]
0x14000920f  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140009213  mov     rdx, [rbx+50h]
0x140009217  lea     rcx, [rbx+58h]
0x14000921b  call    ?QueryAllocationRanges@StreamingBitmapBuilder@Context@Streaming@@SAJAEAV?$auto_ptr@VStreamingBitMap@Context@Streaming@@U?$AllocDelete@VStreamingBitMap@Context@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@_JAEBU_FILE_ALLOCATED_RANGE_BUFFER@@QEAU8@KAEAK@Z; Streaming::Context::StreamingBitmapBuilder::QueryAllocationRanges(appv::shared::kernel::auto_ptr<Streaming::Context::StreamingBitMap,appv::shared::kernel::AllocDelete<Streaming::Context::StreamingBitMap>> &,__int64,_FILE_ALLOCATED_RANGE_BUFFER const &,_FILE_ALLOCATED_RANGE_BUFFER * const,ulong,ulong &)
0x140009220  mov     rcx, rbx; Context
0x140009223  mov     edi, eax
0x140009225  call    cs:__imp_FltReleaseContext
0x14000922c  nop     dword ptr [rax+rax+00h]
0x140009231  jmp     loc_140008F40
0x140009236  mov     rcx, [rbp+47h+var_88]; Context
  ... truncated ...
```
