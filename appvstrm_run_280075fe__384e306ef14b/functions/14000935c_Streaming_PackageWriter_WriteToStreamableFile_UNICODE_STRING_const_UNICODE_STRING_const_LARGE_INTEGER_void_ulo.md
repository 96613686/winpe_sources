# Streaming::PackageWriter::WriteToStreamableFile(_UNICODE_STRING const &,_UNICODE_STRING const &,_LARGE_INTEGER,void *,ulong,uint,ulong &)

- ea: `0x14000935c`
- end: `0x140009846`
- name: `?WriteToStreamableFile@PackageWriter@Streaming@@SAJAEBU_UNICODE_STRING@@0T_LARGE_INTEGER@@PEAXKIAEAK@Z`
- size: `1258`
- prototype: `static int(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, union _LARGE_INTEGER, void *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140011928`

## callees

- `0x1400034fc`
- `0x140005ed8`
- `0x14000935c`
- `0x14000984c`
- `0x140011cb0`
- `0x140011f30`
- `0x1400147fc`
- `0x140014a50`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140009392`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000943d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009457`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009392`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000943d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009457`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009480`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000949b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009508`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000951f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009585`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400095ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400095c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009629`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009743`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000975a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400097a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400097bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009822`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009480`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000949b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009508`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000951f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009585`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400095ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400095c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009629`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009743`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000975a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400097a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400097bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009822`
- `FLTMGR!FltReleaseContext` at `0x140009418`
- `FLTMGR!FltReleaseContext` at `0x14000956e`
- `FLTMGR!FltReleaseContext` at `0x140009612`
- `FLTMGR!FltReleaseContext` at `0x14000980b`
- `FLTMGR!FltReleaseContext` at `0x140009418`
- `FLTMGR!FltReleaseContext` at `0x14000956e`
- `FLTMGR!FltReleaseContext` at `0x140009612`
- `FLTMGR!FltReleaseContext` at `0x14000980b`

## string_xrefs

- `0x140009699`: `PackageWriter::WriteToStreamableFile() - Streaming Filter failed in writing to the file %s from offset %lld with data size %ld. Failure status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::PackageWriter::WriteToStreamableFile(
        const struct _UNICODE_STRING *a1,
        const struct _UNICODE_STRING *a2,
        union _LARGE_INTEGER a3,
        void *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7)
{
  int FileFullName; // ebx
  Streaming::InstanceContextFactory *v13; // rcx
  PFLT_CONTEXT v14; // rbx
  int v15; // r14d
  volatile signed __int32 *Buffer; // rsi
  volatile signed __int32 *v17; // rsi
  __int64 v18; // rsi
  int v19; // r15d
  __int64 v20; // rsi
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v22; // rsi
  volatile signed __int32 *v23; // rsi
  volatile signed __int32 *v24; // rsi
  unsigned int v25[2]; // [rsp+28h] [rbp-B9h]
  unsigned int v26[2]; // [rsp+28h] [rbp-B9h]
  __int64 v27; // [rsp+30h] [rbp-B1h]
  ULONG v28; // [rsp+38h] [rbp-A9h]
  PFLT_CONTEXT Context; // [rsp+50h] [rbp-91h] BYREF
  volatile signed __int32 *v30; // [rsp+58h] [rbp-89h]
  struct _UNICODE_STRING v31; // [rsp+60h] [rbp-81h] BYREF
  __int64 v32; // [rsp+70h] [rbp-71h] BYREF
  PVOID P; // [rsp+78h] [rbp-69h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-61h] BYREF
  UNICODE_STRING v35; // [rsp+90h] [rbp-51h] BYREF
  struct _UNICODE_STRING v36; // [rsp+A0h] [rbp-41h] BYREF
  struct _FLT_INSTANCE *v37; // [rsp+B0h] [rbp-31h] BYREF
  volatile signed __int32 *v38; // [rsp+B8h] [rbp-29h]
  __int64 v39; // [rsp+C0h] [rbp-21h] BYREF
  PVOID v40; // [rsp+C8h] [rbp-19h]
  struct _UNICODE_STRING v41; // [rsp+D0h] [rbp-11h] BYREF

  v32 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  Context = 0;
  v37 = 0;
  *a7 = 0;
  FileFullName = Streaming::Utils::GetFileFullName(a1, a2, &v32);
  if ( FileFullName < 0 )
  {
LABEL_2:
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)FileFullName;
  }
  v13 = (Streaming::InstanceContextFactory *)*((_QWORD *)Streaming::gStrmFltData + 3);
  v31 = *a1;
  FileFullName = Streaming::InstanceContextFactory::GetContextByVolumeName(
                   v13,
                   &v31,
                   &v37,
                   (struct Streaming::InstanceContext *)&Context);
  if ( FileFullName < 0 )
  {
LABEL_6:
    if ( Context )
      FltReleaseContext(Context);
    goto LABEL_2;
  }
  v39 = 0;
  v40 = 0;
  v31 = 0;
  RtlInitUnicodeString(&v41, 0);
  *(_QWORD *)&v35.Length = 0;
  v35.Buffer = 0;
  RtlInitUnicodeString(&v36, 0);
  FileFullName = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
                   &v39,
                   a1);
  if ( FileFullName < 0
    || (FileFullName = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
                         &v35,
                         a2),
        FileFullName < 0) )
  {
    if ( v35.Buffer )
      ExFreePoolWithTag(v35.Buffer, 0);
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    goto LABEL_6;
  }
  v14 = Context;
  v15 = Streaming::StreamingTargetFileCache::Open(
          *((_QWORD *)Context + 34),
          (__int64)&v39,
          &v35,
          v37,
          (Streaming::InstanceContext *)&Context,
          (Streaming::StreamingTargetFileObject **)&v31);
  if ( v15 == -1073741195 )
  {
    if ( v35.Buffer )
      ExFreePoolWithTag(v35.Buffer, 0);
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    Buffer = (volatile signed __int32 *)v31.Buffer;
    if ( v31.Buffer )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v31.Buffer + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 8LL))(Buffer);
        if ( _InterlockedExchangeAdd(Buffer + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 16LL))(Buffer);
      }
    }
    FltReleaseContext(v14);
    if ( P )
      ExFreePoolWithTag(P, 0);
    return 0;
  }
  if ( v15 < 0 )
  {
    if ( v35.Buffer )
      ExFreePoolWithTag(v35.Buffer, 0);
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    v17 = (volatile signed __int32 *)v31.Buffer;
    if ( v31.Buffer )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v31.Buffer + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    FltReleaseContext(v14);
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)v15;
  }
  v18 = *(_QWORD *)&v31.Length;
  v25[0] = a5;
  v19 = Streaming::PackageWriter::WriteToStreamableFile(
          v37,
          **(struct Streaming::Context::StrmStreamContext ***)&v31.Length,
          *(struct _FILE_OBJECT **)(*(_QWORD *)&v31.Length + 8LL),
          a3,
          a4,
          *(size_t *)v25,
          *((_DWORD *)v14 + 24),
          v28,
          a7);
  if ( v19 >= 0 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v18 + 88LL) + 56LL) )
      Streaming::StreamingTargetFileCache::Close(*((_QWORD *)v14 + 34), (__int64)&Context, &v35, 1);
    if ( v35.Buffer )
      ExFreePoolWithTag(v35.Buffer, 0);
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    v24 = (volatile signed __int32 *)v31.Buffer;
    if ( !v31.Buffer )
      goto LABEL_63;
  }
  else
  {
    v20 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&Context, &DestinationString);
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v37);
    LODWORD(v27) = v19;
    v26[0] = a5;
    LogWrite(
      1,
      *CurrentActivityID,
      L"PackageWriter::WriteToStreamableFile() - Streaming Filter failed in writing to the file %s from offset %lld with d"
       "ata size %ld. Failure status 0x%08X.",
      v20,
      a3.QuadPart,
      *(_QWORD *)v26,
      v27);
    v22 = v38;
    if ( v38 )
    {
      if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    v23 = v30;
    if ( v30 )
    {
      if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    if ( v35.Buffer )
      ExFreePoolWithTag(v35.Buffer, 0);
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    v24 = (volatile signed __int32 *)v31.Buffer;
    if ( !v31.Buffer )
      goto LABEL_63;
  }
  if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 16LL))(v24);
  }
LABEL_63:
  FltReleaseContext(v14);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14000935c  push    rbp
0x14000935e  push    rbx
0x14000935f  push    rsi
0x140009360  push    rdi
0x140009361  push    r12
0x140009363  push    r13
0x140009365  push    r14
0x140009367  push    r15
0x140009369  lea     rbp, [rsp-7]
0x14000936e  sub     rsp, 0E8h
0x140009375  mov     r14, rdx
0x140009378  mov     rsi, rcx
0x14000937b  xor     r13d, r13d
0x14000937e  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140009382  xor     edx, edx; SourceString
0x140009384  mov     [rbp+3Fh+var_B0], r13
0x140009388  mov     [rbp+3Fh+P], r13
0x14000938c  mov     r12, r9
0x14000938f  mov     rdi, r8
0x140009392  call    cs:__imp_RtlInitUnicodeString
0x140009399  nop     dword ptr [rax+rax+00h]
0x14000939e  mov     r15, [rbp+3Fh+arg_30]
0x1400093a2  lea     r8, [rbp+3Fh+var_B0]
0x1400093a6  mov     rdx, r14
0x1400093a9  mov     [rsp+120h+Context], r13
0x1400093ae  mov     rcx, rsi
0x1400093b1  mov     [rbp+3Fh+var_70], r13
0x1400093b5  mov     [r15], r13d
0x1400093b8  call    ?GetFileFullName@Utils@Streaming@@YAJAEBU_UNICODE_STRING@@0AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Utils::GetFileFullName(_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x1400093bd  mov     ebx, eax
0x1400093bf  test    eax, eax
0x1400093c1  jns     short loc_1400093E1
0x1400093c3  mov     rcx, [rbp+3Fh+P]; P
0x1400093c7  test    rcx, rcx
0x1400093ca  jz      short loc_1400093DA
0x1400093cc  xor     edx, edx; Tag
0x1400093ce  call    cs:__imp_ExFreePoolWithTag
0x1400093d5  nop     dword ptr [rax+rax+00h]
0x1400093da  mov     eax, ebx
0x1400093dc  jmp     loc_140009831
0x1400093e1  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x1400093e8  lea     r9, [rsp+120h+Context]; struct Streaming::InstanceContext *
0x1400093ed  movups  xmm0, xmmword ptr [rsi]
0x1400093f0  lea     r8, [rbp+3Fh+var_70]; struct _FLT_INSTANCE **
0x1400093f4  lea     rdx, [rsp+120h+var_C0]; struct _UNICODE_STRING
0x1400093f9  mov     rcx, [rcx+18h]; this
0x1400093fd  movdqu  xmmword ptr [rsp+120h+var_C0.Length], xmm0
0x140009403  call    ?GetContextByVolumeName@InstanceContextFactory@Streaming@@QEAAJU_UNICODE_STRING@@AEAPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContextByVolumeName(_UNICODE_STRING,_FLT_INSTANCE * &,Streaming::InstanceContext &)
0x140009408  mov     ebx, eax
0x14000940a  test    eax, eax
0x14000940c  jns     short loc_140009426
0x14000940e  mov     rcx, [rsp+120h+Context]; Context
0x140009413  test    rcx, rcx
0x140009416  jz      short loc_1400093C3
0x140009418  call    cs:__imp_FltReleaseContext
0x14000941f  nop     dword ptr [rax+rax+00h]
0x140009424  jmp     short loc_1400093C3
0x140009426  xorps   xmm0, xmm0
0x140009429  mov     [rbp+3Fh+var_60], r13
0x14000942d  xor     edx, edx; SourceString
0x14000942f  mov     [rbp+3Fh+var_58], r13
0x140009433  lea     rcx, [rbp+3Fh+var_50]; DestinationString
0x140009437  movdqu  xmmword ptr [rsp+120h+var_C0.Length], xmm0
0x14000943d  call    cs:__imp_RtlInitUnicodeString
0x140009444  nop     dword ptr [rax+rax+00h]
0x140009449  xor     edx, edx; SourceString
0x14000944b  mov     [rbp+3Fh+var_90], r13
0x14000944f  lea     rcx, [rbp+3Fh+var_80]; DestinationString
0x140009453  mov     [rbp+3Fh+var_88], r13
0x140009457  call    cs:__imp_RtlInitUnicodeString
0x14000945e  nop     dword ptr [rax+rax+00h]
0x140009463  mov     rdx, rsi
0x140009466  lea     rcx, [rbp+3Fh+var_60]
0x14000946a  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x14000946f  mov     ebx, eax
0x140009471  test    eax, eax
0x140009473  jns     short loc_1400094AC
0x140009475  mov     rcx, [rbp+3Fh+var_88]; P
0x140009479  test    rcx, rcx
0x14000947c  jz      short loc_14000948C
0x14000947e  xor     edx, edx; Tag
0x140009480  call    cs:__imp_ExFreePoolWithTag
0x140009487  nop     dword ptr [rax+rax+00h]
0x14000948c  mov     rcx, [rbp+3Fh+var_58]; P
0x140009490  test    rcx, rcx
0x140009493  jz      loc_14000940E
0x140009499  xor     edx, edx; Tag
0x14000949b  call    cs:__imp_ExFreePoolWithTag
0x1400094a2  nop     dword ptr [rax+rax+00h]
0x1400094a7  jmp     loc_14000940E
0x1400094ac  mov     rdx, r14
0x1400094af  lea     rcx, [rbp+3Fh+var_90]
0x1400094b3  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x1400094b8  mov     ebx, eax
0x1400094ba  test    eax, eax
0x1400094bc  js      short loc_140009475
0x1400094be  mov     rbx, [rsp+120h+Context]
0x1400094c3  lea     rax, [rsp+120h+var_C0]
0x1400094c8  mov     r9, [rbp+3Fh+var_70]
0x1400094cc  lea     r8, [rbp+3Fh+var_90]
0x1400094d0  mov     qword ptr [rsp+120h+var_F8], rax
0x1400094d5  lea     rdx, [rbp+3Fh+var_60]
0x1400094d9  lea     rax, [rsp+120h+Context]
0x1400094de  mov     rcx, [rbx+110h]
0x1400094e5  mov     [rsp+120h+var_100], rax
0x1400094ea  call    ?Open@StreamingTargetFileCache@Streaming@@QEAAJAEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@0PEAU_FLT_INSTANCE@@AEAVInstanceContext@2@AEAV?$shared_ptr@VStreamingTargetFileObject@Streaming@@@kernel_std@@@Z; Streaming::StreamingTargetFileCache::Open(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &,_FLT_INSTANCE *,Streaming::InstanceContext &,kernel_std::shared_ptr<Streaming::StreamingTargetFileObject> &)
0x1400094ef  mov     r14d, eax
0x1400094f2  cmp     eax, 0C0000275h
0x1400094f7  jnz     loc_140009598
0x1400094fd  mov     rcx, [rbp+3Fh+var_88]; P
0x140009501  test    rcx, rcx
0x140009504  jz      short loc_140009514
0x140009506  xor     edx, edx; Tag
0x140009508  call    cs:__imp_ExFreePoolWithTag
0x14000950f  nop     dword ptr [rax+rax+00h]
0x140009514  mov     rcx, [rbp+3Fh+var_58]; P
0x140009518  test    rcx, rcx
0x14000951b  jz      short loc_14000952B
0x14000951d  xor     edx, edx; Tag
0x14000951f  call    cs:__imp_ExFreePoolWithTag
0x140009526  nop     dword ptr [rax+rax+00h]
0x14000952b  mov     rsi, [rbp+3Fh+var_C0.Buffer]
0x14000952f  test    rsi, rsi
0x140009532  jz      short loc_14000956B
0x140009534  or      edi, 0FFFFFFFFh
0x140009537  mov     eax, edi
0x140009539  lock xadd [rsi+8], eax
0x14000953e  add     eax, edi
0x140009540  jnz     short loc_14000956B
0x140009542  mov     rax, [rsi]
0x140009545  mov     rcx, rsi
0x140009548  mov     rax, [rax+8]
0x14000954c  call    _guard_dispatch_icall
0x140009551  mov     eax, edi
0x140009553  lock xadd [rsi+0Ch], eax
0x140009558  add     eax, edi
0x14000955a  jnz     short loc_14000956B
0x14000955c  mov     rax, [rsi]
0x14000955f  mov     rcx, rsi
0x140009562  mov     rax, [rax+10h]
0x140009566  call    _guard_dispatch_icall
0x14000956b  mov     rcx, rbx; Context
0x14000956e  call    cs:__imp_FltReleaseContext
0x140009575  nop     dword ptr [rax+rax+00h]
0x14000957a  mov     rcx, [rbp+3Fh+P]; P
0x14000957e  test    rcx, rcx
0x140009581  jz      short loc_140009591
0x140009583  xor     edx, edx; Tag
0x140009585  call    cs:__imp_ExFreePoolWithTag
0x14000958c  nop     dword ptr [rax+rax+00h]
0x140009591  xor     eax, eax
0x140009593  jmp     loc_140009831
0x140009598  test    r14d, r14d
0x14000959b  jns     loc_14000963D
0x1400095a1  mov     rcx, [rbp+3Fh+var_88]; P
0x1400095a5  test    rcx, rcx
0x1400095a8  jz      short loc_1400095B8
0x1400095aa  xor     edx, edx; Tag
0x1400095ac  call    cs:__imp_ExFreePoolWithTag
0x1400095b3  nop     dword ptr [rax+rax+00h]
0x1400095b8  mov     rcx, [rbp+3Fh+var_58]; P
0x1400095bc  test    rcx, rcx
0x1400095bf  jz      short loc_1400095CF
0x1400095c1  xor     edx, edx; Tag
0x1400095c3  call    cs:__imp_ExFreePoolWithTag
0x1400095ca  nop     dword ptr [rax+rax+00h]
0x1400095cf  mov     rsi, [rbp+3Fh+var_C0.Buffer]
0x1400095d3  test    rsi, rsi
0x1400095d6  jz      short loc_14000960F
0x1400095d8  or      edi, 0FFFFFFFFh
0x1400095db  mov     eax, edi
0x1400095dd  lock xadd [rsi+8], eax
0x1400095e2  add     eax, edi
0x1400095e4  jnz     short loc_14000960F
0x1400095e6  mov     rax, [rsi]
0x1400095e9  mov     rcx, rsi
0x1400095ec  mov     rax, [rax+8]
0x1400095f0  call    _guard_dispatch_icall
0x1400095f5  mov     eax, edi
0x1400095f7  lock xadd [rsi+0Ch], eax
0x1400095fc  add     eax, edi
0x1400095fe  jnz     short loc_14000960F
0x140009600  mov     rax, [rsi]
0x140009603  mov     rcx, rsi
0x140009606  mov     rax, [rax+10h]
0x14000960a  call    _guard_dispatch_icall
0x14000960f  mov     rcx, rbx; Context
0x140009612  call    cs:__imp_FltReleaseContext
0x140009619  nop     dword ptr [rax+rax+00h]
0x14000961e  mov     rcx, [rbp+3Fh+P]; P
0x140009622  test    rcx, rcx
0x140009625  jz      short loc_140009635
0x140009627  xor     edx, edx; Tag
0x140009629  call    cs:__imp_ExFreePoolWithTag
0x140009630  nop     dword ptr [rax+rax+00h]
0x140009635  mov     eax, r14d
0x140009638  jmp     loc_140009831
0x14000963d  mov     rsi, qword ptr [rsp+120h+var_C0.Length]
0x140009642  mov     r9, rdi; union _LARGE_INTEGER
0x140009645  mov     eax, [rbx+60h]
0x140009648  mov     r14d, [rbp+3Fh+arg_20]
0x14000964c  mov     rcx, [rbp+3Fh+var_70]; struct _FLT_INSTANCE *
0x140009650  mov     r8, [rsi+8]; struct _FILE_OBJECT *
0x140009654  mov     rdx, [rsi]; struct Streaming::Context::StrmStreamContext *
0x140009657  mov     [rsp+120h+var_E0], r15; unsigned int *
0x14000965c  mov     dword ptr [rsp+120h+var_F0], eax; unsigned int
0x140009660  mov     [rsp+120h+var_F8], r14d; unsigned int
0x140009665  mov     [rsp+120h+var_100], r12; void *
0x14000966a  call    ?WriteToStreamableFile@PackageWriter@Streaming@@SAJPEAU_FLT_INSTANCE@@PEAUStrmStreamContext@Context@2@AEAU_FILE_OBJECT@@T_LARGE_INTEGER@@PEAXKK_NAEAK@Z; Streaming::PackageWriter::WriteToStreamableFile(_FLT_INSTANCE *,Streaming::Context::StrmStreamContext *,_FILE_OBJECT &,_LARGE_INTEGER,void *,ulong,ulong,bool,ulong &)
0x14000966f  mov     r15d, eax
0x140009672  test    eax, eax
0x140009674  jns     loc_140009775
0x14000967a  lea     rdx, [rbp+3Fh+DestinationString]
0x14000967e  lea     rcx, [rsp+120h+Context]
0x140009683  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140009688  lea     rcx, [rbp+3Fh+var_70]
0x14000968c  mov     rsi, [rax]
0x14000968f  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140009694  mov     dword ptr [rsp+120h+var_F0], r15d
0x140009699  lea     r8, aPackagewriterW_1; "PackageWriter::WriteToStreamableFile() "...
0x1400096a0  mov     [rsp+120h+var_F8], r14d
0x1400096a5  mov     r9, rsi
0x1400096a8  mov     ecx, 1
0x1400096ad  mov     [rsp+120h+var_100], rdi
0x1400096b2  mov     rdx, [rax]
0x1400096b5  call    LogWrite
0x1400096ba  mov     rsi, [rbp+3Fh+var_68]
0x1400096be  or      edi, 0FFFFFFFFh
0x1400096c1  test    rsi, rsi
0x1400096c4  jz      short loc_1400096FA
0x1400096c6  mov     eax, edi
0x1400096c8  lock xadd [rsi+8], eax
0x1400096cd  add     eax, edi
0x1400096cf  jnz     short loc_1400096FA
0x1400096d1  mov     rax, [rsi]
0x1400096d4  mov     rcx, rsi
0x1400096d7  mov     rax, [rax+8]
0x1400096db  call    _guard_dispatch_icall
0x1400096e0  mov     eax, edi
0x1400096e2  lock xadd [rsi+0Ch], eax
0x1400096e7  add     eax, edi
0x1400096e9  jnz     short loc_1400096FA
0x1400096eb  mov     rax, [rsi]
0x1400096ee  mov     rcx, rsi
0x1400096f1  mov     rax, [rax+10h]
0x1400096f5  call    _guard_dispatch_icall
0x1400096fa  mov     rsi, [rsp+120h+var_C8]
0x1400096ff  test    rsi, rsi
0x140009702  jz      short loc_140009738
0x140009704  mov     eax, edi
0x140009706  lock xadd [rsi+8], eax
0x14000970b  add     eax, edi
0x14000970d  jnz     short loc_140009738
0x14000970f  mov     rax, [rsi]
0x140009712  mov     rcx, rsi
0x140009715  mov     rax, [rax+8]
0x140009719  call    _guard_dispatch_icall
0x14000971e  mov     eax, edi
0x140009720  lock xadd [rsi+0Ch], eax
0x140009725  add     eax, edi
0x140009727  jnz     short loc_140009738
0x140009729  mov     rax, [rsi]
0x14000972c  mov     rcx, rsi
0x14000972f  mov     rax, [rax+10h]
0x140009733  call    _guard_dispatch_icall
0x140009738  mov     rcx, [rbp+3Fh+var_88]; P
0x14000973c  test    rcx, rcx
0x14000973f  jz      short loc_14000974F
0x140009741  xor     edx, edx; Tag
0x140009743  call    cs:__imp_ExFreePoolWithTag
0x14000974a  nop     dword ptr [rax+rax+00h]
0x14000974f  mov     rcx, [rbp+3Fh+var_58]; P
0x140009753  test    rcx, rcx
0x140009756  jz      short loc_140009766
0x140009758  xor     edx, edx; Tag
0x14000975a  call    cs:__imp_ExFreePoolWithTag
0x140009761  nop     dword ptr [rax+rax+00h]
0x140009766  mov     rsi, [rbp+3Fh+var_C0.Buffer]
0x14000976a  test    rsi, rsi
0x14000976d  jz      loc_140009808
0x140009773  jmp     short loc_1400097D4
0x140009775  mov     rax, [rsi]
0x140009778  mov     rcx, [rax+58h]
0x14000977c  cmp     [rcx+38h], r13b
0x140009780  jz      short loc_14000979A
0x140009782  mov     rcx, [rbx+110h]
0x140009789  lea     r8, [rbp+3Fh+var_90]
0x14000978d  mov     r9b, 1
0x140009790  lea     rdx, [rsp+120h+Context]
0x140009795  call    ?Close@StreamingTargetFileCache@Streaming@@QEAAJAEAVInstanceContext@2@AEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@_N@Z; Streaming::StreamingTargetFileCache::Close(Streaming::InstanceContext &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &,bool)
0x14000979a  mov     rcx, [rbp+3Fh+var_88]; P
0x14000979e  test    rcx, rcx
0x1400097a1  jz      short loc_1400097B1
0x1400097a3  xor     edx, edx; Tag
0x1400097a5  call    cs:__imp_ExFreePoolWithTag
0x1400097ac  nop     dword ptr [rax+rax+00h]
0x1400097b1  mov     rcx, [rbp+3Fh+var_58]; P
0x1400097b5  test    rcx, rcx
0x1400097b8  jz      short loc_1400097C8
0x1400097ba  xor     edx, edx; Tag
  ... truncated ...
```
