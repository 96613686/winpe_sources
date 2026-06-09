# Streaming::Messaging::PackageLoader::CreateStagingDirectory(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING *,uchar)

- ea: `0x1400084b0`
- end: `0x14000869f`
- name: `?CreateStagingDirectory@PackageLoader@Messaging@Streaming@@SAJAEBU_UNICODE_STRING@@0PEAU4@E@Z`
- size: `495`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140010c64`

## callees

- `0x140005ed8`
- `0x140007fe4`
- `0x1400084b0`
- `0x1400147fc`
- `0x140014a50`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400084f7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400084f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008527`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008621`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000866b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008527`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008621`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000866b`
- `FLTMGR!FltReleaseContext` at `0x140008636`
- `FLTMGR!FltReleaseContext` at `0x140008680`
- `FLTMGR!FltReleaseContext` at `0x140008636`
- `FLTMGR!FltReleaseContext` at `0x140008680`

## string_xrefs

- `0x140008585`: `PackageLoader::CreateStagingDirectory() - Filter might not be attached to the volume. Couldn't find instance for volume %s. Failure Status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::PackageLoader::CreateStagingDirectory(
        const struct _UNICODE_STRING *a1,
        const struct _UNICODE_STRING *a2,
        struct _FILE_OBJECT *a3,
        char a4)
{
  int FileFullName; // ebx
  Streaming::InstanceContextFactory *v9; // rcx
  int ContextByVolumeName; // esi
  __int64 v11; // rbx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *Buffer; // rbx
  volatile signed __int32 *v14; // rbx
  char v16[4]; // [rsp+20h] [rbp-39h]
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-29h] BYREF
  PFLT_INSTANCE Instance; // [rsp+38h] [rbp-21h] BYREF
  volatile signed __int32 *v19; // [rsp+40h] [rbp-19h]
  struct _UNICODE_STRING v20; // [rsp+50h] [rbp-9h] BYREF
  __int64 v21; // [rsp+60h] [rbp+7h] BYREF
  PVOID P; // [rsp+68h] [rbp+Fh]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF

  Context = 0;
  Instance = 0;
  v21 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  FileFullName = Streaming::Utils::GetFileFullName(a1, a2, &v21);
  if ( FileFullName < 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)FileFullName;
  }
  v9 = (Streaming::InstanceContextFactory *)*((_QWORD *)Streaming::gStrmFltData + 3);
  v20 = *a1;
  ContextByVolumeName = Streaming::InstanceContextFactory::GetContextByVolumeName(
                          v9,
                          &v20,
                          &Instance,
                          (struct Streaming::InstanceContext *)&Context);
  if ( ContextByVolumeName >= 0 )
  {
    FileFullName = Streaming::Messaging::PackageLoader::CreateStagingDirectory(&DestinationString, Instance, a3, a1, a4);
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( Context )
      FltReleaseContext(Context);
    return (unsigned int)FileFullName;
  }
  v11 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&Instance, a1);
  CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v20);
  *(_DWORD *)v16 = ContextByVolumeName;
  LogWrite(
    1,
    *CurrentActivityID,
    L"PackageLoader::CreateStagingDirectory() - Filter might not be attached to the volume. Couldn't find instance for vol"
     "ume %s. Failure Status 0x%08X.",
    v11,
    *(_DWORD *)v16);
  Buffer = (volatile signed __int32 *)v20.Buffer;
  if ( v20.Buffer )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20.Buffer + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 8LL))(Buffer);
      if ( _InterlockedExchangeAdd(Buffer + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 16LL))(Buffer);
    }
  }
  v14 = v19;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)ContextByVolumeName;
}

```

## disassembly

```asm
0x1400084b0  push    rbp
0x1400084b2  push    rbx
0x1400084b3  push    rsi
0x1400084b4  push    rdi
0x1400084b5  push    r14
0x1400084b7  push    r15
0x1400084b9  lea     rbp, [rsp-2Fh]
0x1400084be  sub     rsp, 88h
0x1400084c5  mov     rbx, rdx
0x1400084c8  mov     [rbp+57h+Context], 0
0x1400084d0  mov     rdi, rcx
0x1400084d3  mov     [rbp+57h+Instance], 0
0x1400084db  xor     edx, edx; SourceString
0x1400084dd  mov     [rbp+57h+var_50], 0
0x1400084e5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400084e9  mov     [rbp+57h+P], 0
0x1400084f1  mov     r14b, r9b
0x1400084f4  mov     r15, r8
0x1400084f7  call    cs:__imp_RtlInitUnicodeString
0x1400084fe  nop     dword ptr [rax+rax+00h]
0x140008503  lea     r8, [rbp+57h+var_50]
0x140008507  mov     rdx, rbx
0x14000850a  mov     rcx, rdi
0x14000850d  call    ?GetFileFullName@Utils@Streaming@@YAJAEBU_UNICODE_STRING@@0AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Utils::GetFileFullName(_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140008512  mov     ebx, eax
0x140008514  test    eax, eax
0x140008516  jns     short loc_140008538
0x140008518  mov     rcx, [rbp+57h+P]; P
0x14000851c  test    rcx, rcx
0x14000851f  jz      loc_14000868C
0x140008525  xor     edx, edx; Tag
0x140008527  call    cs:__imp_ExFreePoolWithTag
0x14000852e  nop     dword ptr [rax+rax+00h]
0x140008533  jmp     loc_14000868C
0x140008538  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x14000853f  lea     r9, [rbp+57h+Context]; struct Streaming::InstanceContext *
0x140008543  movups  xmm0, xmmword ptr [rdi]
0x140008546  lea     r8, [rbp+57h+Instance]; struct _FLT_INSTANCE **
0x14000854a  lea     rdx, [rbp+57h+var_60]; struct _UNICODE_STRING
0x14000854e  mov     rcx, [rcx+18h]; this
0x140008552  movdqu  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140008557  call    ?GetContextByVolumeName@InstanceContextFactory@Streaming@@QEAAJU_UNICODE_STRING@@AEAPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContextByVolumeName(_UNICODE_STRING,_FLT_INSTANCE * &,Streaming::InstanceContext &)
0x14000855c  mov     esi, eax
0x14000855e  test    eax, eax
0x140008560  jns     loc_140008646
0x140008566  mov     rdx, rdi
0x140008569  lea     rcx, [rbp+57h+Instance]
0x14000856d  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008572  lea     rcx, [rbp+57h+var_60]
0x140008576  mov     rbx, [rax]
0x140008579  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000857e  mov     r9, rbx
0x140008581  mov     dword ptr [rsp+0B0h+var_90], esi
0x140008585  lea     r8, aPackageloaderC_5; "PackageLoader::CreateStagingDirectory()"...
0x14000858c  mov     ecx, 1
0x140008591  mov     rdx, [rax]
0x140008594  call    LogWrite
0x140008599  mov     rbx, [rbp+57h+var_60.Buffer]
0x14000859d  or      edi, 0FFFFFFFFh
0x1400085a0  test    rbx, rbx
0x1400085a3  jz      short loc_1400085D9
0x1400085a5  mov     eax, edi
0x1400085a7  lock xadd [rbx+8], eax
0x1400085ac  add     eax, edi
0x1400085ae  jnz     short loc_1400085D9
0x1400085b0  mov     rax, [rbx]
0x1400085b3  mov     rcx, rbx
0x1400085b6  mov     rax, [rax+8]
0x1400085ba  call    _guard_dispatch_icall
0x1400085bf  mov     eax, edi
0x1400085c1  lock xadd [rbx+0Ch], eax
0x1400085c6  add     eax, edi
0x1400085c8  jnz     short loc_1400085D9
0x1400085ca  mov     rax, [rbx]
0x1400085cd  mov     rcx, rbx
0x1400085d0  mov     rax, [rax+10h]
0x1400085d4  call    _guard_dispatch_icall
0x1400085d9  mov     rbx, [rbp+57h+var_70]
0x1400085dd  test    rbx, rbx
0x1400085e0  jz      short loc_140008616
0x1400085e2  mov     eax, edi
0x1400085e4  lock xadd [rbx+8], eax
0x1400085e9  add     eax, edi
0x1400085eb  jnz     short loc_140008616
0x1400085ed  mov     rax, [rbx]
0x1400085f0  mov     rcx, rbx
0x1400085f3  mov     rax, [rax+8]
0x1400085f7  call    _guard_dispatch_icall
0x1400085fc  mov     eax, edi
0x1400085fe  lock xadd [rbx+0Ch], eax
0x140008603  add     eax, edi
0x140008605  jnz     short loc_140008616
0x140008607  mov     rax, [rbx]
0x14000860a  mov     rcx, rbx
0x14000860d  mov     rax, [rax+10h]
0x140008611  call    _guard_dispatch_icall
0x140008616  mov     rcx, [rbp+57h+P]; P
0x14000861a  test    rcx, rcx
0x14000861d  jz      short loc_14000862D
0x14000861f  xor     edx, edx; Tag
0x140008621  call    cs:__imp_ExFreePoolWithTag
0x140008628  nop     dword ptr [rax+rax+00h]
0x14000862d  mov     rcx, [rbp+57h+Context]; Context
0x140008631  test    rcx, rcx
0x140008634  jz      short loc_140008642
0x140008636  call    cs:__imp_FltReleaseContext
0x14000863d  nop     dword ptr [rax+rax+00h]
0x140008642  mov     eax, esi
0x140008644  jmp     short loc_14000868E
0x140008646  mov     rdx, [rbp+57h+Instance]; Instance
0x14000864a  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x14000864e  mov     r9, rdi; struct _UNICODE_STRING *
0x140008651  mov     [rsp+0B0h+var_90], r14b; char
0x140008656  mov     r8, r15; struct _UNICODE_STRING *
0x140008659  call    ?CreateStagingDirectory@PackageLoader@Messaging@Streaming@@CAJAEBU_UNICODE_STRING@@PEAU_FLT_INSTANCE@@PEAU4@0E@Z; Streaming::Messaging::PackageLoader::CreateStagingDirectory(_UNICODE_STRING const &,_FLT_INSTANCE *,_UNICODE_STRING *,_UNICODE_STRING const &,uchar)
0x14000865e  mov     rcx, [rbp+57h+P]; P
0x140008662  mov     ebx, eax
0x140008664  test    rcx, rcx
0x140008667  jz      short loc_140008677
0x140008669  xor     edx, edx; Tag
0x14000866b  call    cs:__imp_ExFreePoolWithTag
0x140008672  nop     dword ptr [rax+rax+00h]
0x140008677  mov     rcx, [rbp+57h+Context]; Context
0x14000867b  test    rcx, rcx
0x14000867e  jz      short loc_14000868C
0x140008680  call    cs:__imp_FltReleaseContext
0x140008687  nop     dword ptr [rax+rax+00h]
0x14000868c  mov     eax, ebx
0x14000868e  add     rsp, 88h
0x140008695  pop     r15
0x140008697  pop     r14
0x140008699  pop     rdi
0x14000869a  pop     rsi
0x14000869b  pop     rbx
0x14000869c  pop     rbp
0x14000869d  retn
```
