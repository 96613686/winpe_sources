# Streaming::Context::StreamContextFactory::GetOrCreateStreamContext(_FLT_INSTANCE *,_FLT_CALLBACK_DATA &,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)

- ea: `0x14000ba94`
- end: `0x14000bbce`
- name: `?GetOrCreateStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FLT_CALLBACK_DATA@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _FLT_CALLBACK_DATA *, struct _FILE_OBJECT *, PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140012b18`

## callees

- `0x140002cb8`
- `0x140005e3c`
- `0x140005fb8`
- `0x14000b748`
- `0x14000ba94`
- `0x14000bcb0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000bae1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bb03`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bae1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bb03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bb98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bb98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbaf`
- `FLTMGR!FltReleaseContext` at `0x14000bb81`
- `FLTMGR!FltReleaseContext` at `0x14000bb81`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamContextFactory::GetOrCreateStreamContext(
        PFLT_INSTANCE Instance,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FILE_OBJECT *a3,
        PFLT_CONTEXT *a4)
{
  __int64 result; // rax
  Streaming::InstanceContextFactory *v9; // rcx
  int DosName; // ebx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING *v12; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING v13; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING v14; // [rsp+50h] [rbp-9h] BYREF
  __int64 v15; // [rsp+60h] [rbp+7h] BYREF
  PVOID v16; // [rsp+68h] [rbp+Fh]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF

  result = Streaming::Context::StreamContextFactory::GetStreamContext(Instance, a3, a4);
  if ( (_DWORD)result == -1073741275 )
  {
    v15 = 0;
    v16 = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    *(_QWORD *)&v13.Length = 0;
    v13.Buffer = 0;
    RtlInitUnicodeString(&v14, 0);
    Context = 0;
    v12 = 0;
    DosName = Streaming::InstanceContextFactory::GetContext(v9, Instance, &Context);
    if ( DosName >= 0 )
    {
      DosName = Streaming::InstanceContext::GetDosName(
                  (Streaming::InstanceContext *)&Context,
                  (const struct _UNICODE_STRING **)&v12);
      if ( DosName >= 0 )
      {
        DosName = Streaming::FileOperations::GetFilePathFromCallback(a2, (const void **)v12, &v13, (__int64)&v15);
        if ( DosName >= 0 )
          DosName = Streaming::Context::StreamContextFactory::CreateStreamContext(
                      Instance,
                      &DestinationString,
                      &v14,
                      a3,
                      a4);
      }
    }
    if ( Context )
      FltReleaseContext(Context);
    if ( v13.Buffer )
      ExFreePoolWithTag(v13.Buffer, 0);
    if ( v16 )
      ExFreePoolWithTag(v16, 0);
    return (unsigned int)DosName;
  }
  return result;
}

```

## disassembly

```asm
0x14000ba94  push    rbp
0x14000ba96  push    rbx
0x14000ba97  push    rsi
0x14000ba98  push    rdi
0x14000ba99  push    r14
0x14000ba9b  push    r15
0x14000ba9d  lea     rbp, [rsp-2Fh]
0x14000baa2  sub     rsp, 88h
0x14000baa9  mov     r14, r8
0x14000baac  mov     r15, rdx
0x14000baaf  mov     rdx, r14
0x14000bab2  mov     r8, r9
0x14000bab5  mov     rsi, r9
0x14000bab8  mov     rdi, rcx
0x14000babb  call    ?GetStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::GetStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x14000bac0  cmp     eax, 0C0000225h
0x14000bac5  jnz     loc_14000BBBD
0x14000bacb  xor     edx, edx; SourceString
0x14000bacd  mov     [rbp+57h+var_50], 0
0x14000bad5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000bad9  mov     [rbp+57h+var_48], 0
0x14000bae1  call    cs:__imp_RtlInitUnicodeString
0x14000bae8  nop     dword ptr [rax+rax+00h]
0x14000baed  xor     edx, edx; SourceString
0x14000baef  mov     [rbp+57h+var_70], 0
0x14000baf7  lea     rcx, [rbp+57h+var_60]; DestinationString
0x14000bafb  mov     [rbp+57h+P], 0
0x14000bb03  call    cs:__imp_RtlInitUnicodeString
0x14000bb0a  nop     dword ptr [rax+rax+00h]
0x14000bb0f  lea     r8, [rbp+57h+Context]; struct Streaming::InstanceContext *
0x14000bb13  mov     [rbp+57h+Context], 0
0x14000bb1b  mov     rdx, rdi; struct _FLT_INSTANCE *
0x14000bb1e  mov     [rbp+57h+var_78], 0
0x14000bb26  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x14000bb2b  mov     ebx, eax
0x14000bb2d  test    eax, eax
0x14000bb2f  js      short loc_14000BB78
0x14000bb31  lea     rdx, [rbp+57h+var_78]; struct _UNICODE_STRING **
0x14000bb35  lea     rcx, [rbp+57h+Context]; this
0x14000bb39  call    ?GetDosName@InstanceContext@Streaming@@QEAAJAEAPEBU_UNICODE_STRING@@@Z; Streaming::InstanceContext::GetDosName(_UNICODE_STRING const * &)
0x14000bb3e  mov     ebx, eax
0x14000bb40  test    eax, eax
0x14000bb42  js      short loc_14000BB78
0x14000bb44  mov     rdx, [rbp+57h+var_78]
0x14000bb48  lea     r9, [rbp+57h+var_50]
0x14000bb4c  lea     r8, [rbp+57h+var_70]
0x14000bb50  mov     rcx, r15
0x14000bb53  call    ?GetFilePathFromCallback@FileOperations@Streaming@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@2@Z; Streaming::FileOperations::GetFilePathFromCallback(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x14000bb58  mov     ebx, eax
0x14000bb5a  test    eax, eax
0x14000bb5c  js      short loc_14000BB78
0x14000bb5e  mov     r9, r14; FileObject
0x14000bb61  mov     [rsp+0B0h+var_90], rsi; __int64
0x14000bb66  lea     r8, [rbp+57h+var_60]; struct _UNICODE_STRING *
0x14000bb6a  mov     rcx, rdi; Instance
0x14000bb6d  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x14000bb71  call    ?CreateStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@1AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::CreateStreamContext(_FLT_INSTANCE *,_UNICODE_STRING const &,_UNICODE_STRING const &,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x14000bb76  mov     ebx, eax
0x14000bb78  mov     rcx, [rbp+57h+Context]; Context
0x14000bb7c  test    rcx, rcx
0x14000bb7f  jz      short loc_14000BB8D
0x14000bb81  call    cs:__imp_FltReleaseContext
0x14000bb88  nop     dword ptr [rax+rax+00h]
0x14000bb8d  mov     rcx, [rbp+57h+P]; P
0x14000bb91  test    rcx, rcx
0x14000bb94  jz      short loc_14000BBA4
0x14000bb96  xor     edx, edx; Tag
0x14000bb98  call    cs:__imp_ExFreePoolWithTag
0x14000bb9f  nop     dword ptr [rax+rax+00h]
0x14000bba4  mov     rcx, [rbp+57h+var_48]; P
0x14000bba8  test    rcx, rcx
0x14000bbab  jz      short loc_14000BBBB
0x14000bbad  xor     edx, edx; Tag
0x14000bbaf  call    cs:__imp_ExFreePoolWithTag
0x14000bbb6  nop     dword ptr [rax+rax+00h]
0x14000bbbb  mov     eax, ebx
0x14000bbbd  add     rsp, 88h
0x14000bbc4  pop     r15
0x14000bbc6  pop     r14
0x14000bbc8  pop     rdi
0x14000bbc9  pop     rsi
0x14000bbca  pop     rbx
0x14000bbcb  pop     rbp
0x14000bbcc  retn
```
