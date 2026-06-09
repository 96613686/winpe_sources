# Streaming::Messaging::PackageLoader::CreateStreamableFile(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING *,_LARGE_INTEGER &)

- ea: `0x140008bdc`
- end: `0x140008dbc`
- name: `?CreateStreamableFile@PackageLoader@Messaging@Streaming@@SAJAEBU_UNICODE_STRING@@0PEAU4@AEAT_LARGE_INTEGER@@@Z`
- size: `480`
- prototype: `static int(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, struct _UNICODE_STRING *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140010c64`

## callees

- `0x140005ed8`
- `0x1400086a8`
- `0x140008bdc`
- `0x1400147fc`
- `0x140014a50`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140008c23`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008c23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d88`
- `FLTMGR!FltReleaseContext` at `0x140008d9d`
- `FLTMGR!FltReleaseContext` at `0x140008d9d`

## string_xrefs

- `0x140008ca4`: `PackageLoader::CreateStreamableFile() - Filter might not be attached to the volume. Couldn't find instance for volume %s . Failure Status 0x%08X.`
- `0x140008ce5`: `PackageLoader::CreateStreamableFile() - Failed to create package file %s. Failure status = 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::PackageLoader::CreateStreamableFile(
        const struct _UNICODE_STRING *a1,
        const struct _UNICODE_STRING *a2,
        struct _FILE_OBJECT *a3,
        union _LARGE_INTEGER *a4)
{
  int FileFullName; // ebx
  Streaming::InstanceContextFactory *v10; // rcx
  int ContextByVolumeName; // esi
  const struct _UNICODE_STRING *v12; // r9
  __int64 v13; // rbx
  __int64 *CurrentActivityID; // rax
  const WCHAR *v15; // r8
  volatile signed __int32 *Buffer; // rdi
  volatile signed __int32 *v17; // rdi
  union _LARGE_INTEGER *v18; // [rsp+20h] [rbp-39h]
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-29h] BYREF
  struct _FLT_INSTANCE *v20; // [rsp+38h] [rbp-21h] BYREF
  volatile signed __int32 *v21; // [rsp+40h] [rbp-19h]
  struct _UNICODE_STRING v22; // [rsp+50h] [rbp-9h] BYREF
  __int64 v23; // [rsp+60h] [rbp+7h] BYREF
  PVOID P; // [rsp+68h] [rbp+Fh]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF

  Context = 0;
  v20 = 0;
  v23 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  FileFullName = Streaming::Utils::GetFileFullName(a1, a2, &v23);
  if ( FileFullName < 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)FileFullName;
  }
  v10 = (Streaming::InstanceContextFactory *)*((_QWORD *)Streaming::gStrmFltData + 3);
  v22 = *a1;
  ContextByVolumeName = Streaming::InstanceContextFactory::GetContextByVolumeName(
                          v10,
                          &v22,
                          &v20,
                          (struct Streaming::InstanceContext *)&Context);
  if ( ContextByVolumeName < 0 )
  {
    v13 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&v20, a1);
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v22);
    v15 = L"PackageLoader::CreateStreamableFile() - Filter might not be attached to the volume. Couldn't find instance for"
           " volume %s . Failure Status 0x%08X.";
    goto LABEL_9;
  }
  ContextByVolumeName = Streaming::Messaging::PackageLoader::CreateStreamableFile(&DestinationString, v20, a3, v12, a4);
  if ( ContextByVolumeName < 0 )
  {
    v13 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&v20, &DestinationString);
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v22);
    v15 = L"PackageLoader::CreateStreamableFile() - Failed to create package file %s. Failure status = 0x%08X.";
LABEL_9:
    LODWORD(v18) = ContextByVolumeName;
    LogWrite(1, *CurrentActivityID, v15, v13, v18);
    Buffer = (volatile signed __int32 *)v22.Buffer;
    if ( v22.Buffer )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22.Buffer + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 8LL))(Buffer);
        if ( _InterlockedExchangeAdd(Buffer + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 16LL))(Buffer);
      }
    }
    v17 = v21;
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
      }
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
0x140008bdc  push    rbp
0x140008bde  push    rbx
0x140008bdf  push    rsi
0x140008be0  push    rdi
0x140008be1  push    r14
0x140008be3  push    r15
0x140008be5  lea     rbp, [rsp-2Fh]
0x140008bea  sub     rsp, 88h
0x140008bf1  mov     rbx, rdx
0x140008bf4  mov     [rbp+57h+Context], 0
0x140008bfc  mov     rdi, rcx
0x140008bff  mov     [rbp+57h+var_78], 0
0x140008c07  xor     edx, edx; SourceString
0x140008c09  mov     [rbp+57h+var_50], 0
0x140008c11  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140008c15  mov     [rbp+57h+P], 0
0x140008c1d  mov     r14, r9
0x140008c20  mov     r15, r8
0x140008c23  call    cs:__imp_RtlInitUnicodeString
0x140008c2a  nop     dword ptr [rax+rax+00h]
0x140008c2f  lea     r8, [rbp+57h+var_50]
0x140008c33  mov     rdx, rbx
0x140008c36  mov     rcx, rdi
0x140008c39  call    ?GetFileFullName@Utils@Streaming@@YAJAEBU_UNICODE_STRING@@0AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Utils::GetFileFullName(_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140008c3e  mov     ebx, eax
0x140008c40  test    eax, eax
0x140008c42  jns     short loc_140008C62
0x140008c44  mov     rcx, [rbp+57h+P]; P
0x140008c48  test    rcx, rcx
0x140008c4b  jz      short loc_140008C5B
0x140008c4d  xor     edx, edx; Tag
0x140008c4f  call    cs:__imp_ExFreePoolWithTag
0x140008c56  nop     dword ptr [rax+rax+00h]
0x140008c5b  mov     eax, ebx
0x140008c5d  jmp     loc_140008DAB
0x140008c62  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140008c69  lea     r9, [rbp+57h+Context]; struct Streaming::InstanceContext *
0x140008c6d  movups  xmm0, xmmword ptr [rdi]
0x140008c70  lea     r8, [rbp+57h+var_78]; struct _FLT_INSTANCE **
0x140008c74  lea     rdx, [rbp+57h+var_60]; struct _UNICODE_STRING
0x140008c78  mov     rcx, [rcx+18h]; this
0x140008c7c  movdqu  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140008c81  call    ?GetContextByVolumeName@InstanceContextFactory@Streaming@@QEAAJU_UNICODE_STRING@@AEAPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContextByVolumeName(_UNICODE_STRING,_FLT_INSTANCE * &,Streaming::InstanceContext &)
0x140008c86  mov     esi, eax
0x140008c88  test    eax, eax
0x140008c8a  jns     short loc_140008CAD
0x140008c8c  mov     rdx, rdi
0x140008c8f  lea     rcx, [rbp+57h+var_78]
0x140008c93  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008c98  lea     rcx, [rbp+57h+var_60]
0x140008c9c  mov     rbx, [rax]
0x140008c9f  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140008ca4  lea     r8, aPackageloaderC_1; "PackageLoader::CreateStreamableFile() -"...
0x140008cab  jmp     short loc_140008CEC
0x140008cad  mov     rdx, [rbp+57h+var_78]; struct _FLT_INSTANCE *
0x140008cb1  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x140008cb5  mov     r8, r15; struct _UNICODE_STRING *
0x140008cb8  mov     [rsp+0B0h+var_90], r14; union _LARGE_INTEGER *
0x140008cbd  call    ?CreateStreamableFile@PackageLoader@Messaging@Streaming@@CAJAEBU_UNICODE_STRING@@PEAU_FLT_INSTANCE@@PEAU4@0AEAT_LARGE_INTEGER@@@Z; Streaming::Messaging::PackageLoader::CreateStreamableFile(_UNICODE_STRING const &,_FLT_INSTANCE *,_UNICODE_STRING *,_UNICODE_STRING const &,_LARGE_INTEGER &)
0x140008cc2  mov     esi, eax
0x140008cc4  test    eax, eax
0x140008cc6  jns     loc_140008D7D
0x140008ccc  lea     rdx, [rbp+57h+DestinationString]
0x140008cd0  lea     rcx, [rbp+57h+var_78]
0x140008cd4  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008cd9  lea     rcx, [rbp+57h+var_60]
0x140008cdd  mov     rbx, [rax]
0x140008ce0  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140008ce5  lea     r8, aPackageloaderC; "PackageLoader::CreateStreamableFile() -"...
0x140008cec  mov     rdx, [rax]
0x140008cef  mov     r9, rbx
0x140008cf2  mov     ecx, 1
0x140008cf7  mov     dword ptr [rsp+0B0h+var_90], esi
0x140008cfb  call    LogWrite
0x140008d00  mov     rdi, [rbp+57h+var_60.Buffer]
0x140008d04  or      ebx, 0FFFFFFFFh
0x140008d07  test    rdi, rdi
0x140008d0a  jz      short loc_140008D40
0x140008d0c  mov     eax, ebx
0x140008d0e  lock xadd [rdi+8], eax
0x140008d13  add     eax, ebx
0x140008d15  jnz     short loc_140008D40
0x140008d17  mov     rax, [rdi]
0x140008d1a  mov     rcx, rdi
0x140008d1d  mov     rax, [rax+8]
0x140008d21  call    _guard_dispatch_icall
0x140008d26  mov     eax, ebx
0x140008d28  lock xadd [rdi+0Ch], eax
0x140008d2d  add     eax, ebx
0x140008d2f  jnz     short loc_140008D40
0x140008d31  mov     rax, [rdi]
0x140008d34  mov     rcx, rdi
0x140008d37  mov     rax, [rax+10h]
0x140008d3b  call    _guard_dispatch_icall
0x140008d40  mov     rdi, [rbp+57h+var_70]
0x140008d44  test    rdi, rdi
0x140008d47  jz      short loc_140008D7D
0x140008d49  mov     eax, ebx
0x140008d4b  lock xadd [rdi+8], eax
0x140008d50  add     eax, ebx
0x140008d52  jnz     short loc_140008D7D
0x140008d54  mov     rax, [rdi]
0x140008d57  mov     rcx, rdi
0x140008d5a  mov     rax, [rax+8]
0x140008d5e  call    _guard_dispatch_icall
0x140008d63  mov     eax, ebx
0x140008d65  lock xadd [rdi+0Ch], eax
0x140008d6a  add     eax, ebx
0x140008d6c  jnz     short loc_140008D7D
0x140008d6e  mov     rax, [rdi]
0x140008d71  mov     rcx, rdi
0x140008d74  mov     rax, [rax+10h]
0x140008d78  call    _guard_dispatch_icall
0x140008d7d  mov     rcx, [rbp+57h+P]; P
0x140008d81  test    rcx, rcx
0x140008d84  jz      short loc_140008D94
0x140008d86  xor     edx, edx; Tag
0x140008d88  call    cs:__imp_ExFreePoolWithTag
0x140008d8f  nop     dword ptr [rax+rax+00h]
0x140008d94  mov     rcx, [rbp+57h+Context]; Context
0x140008d98  test    rcx, rcx
0x140008d9b  jz      short loc_140008DA9
0x140008d9d  call    cs:__imp_FltReleaseContext
0x140008da4  nop     dword ptr [rax+rax+00h]
0x140008da9  mov     eax, esi
0x140008dab  add     rsp, 88h
0x140008db2  pop     r15
0x140008db4  pop     r14
0x140008db6  pop     rdi
0x140008db7  pop     rsi
0x140008db8  pop     rbx
0x140008db9  pop     rbp
0x140008dba  retn
```
