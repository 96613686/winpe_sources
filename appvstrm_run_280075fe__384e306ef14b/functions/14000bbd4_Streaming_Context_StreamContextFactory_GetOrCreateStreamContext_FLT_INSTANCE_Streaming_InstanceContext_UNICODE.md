# Streaming::Context::StreamContextFactory::GetOrCreateStreamContext(_FLT_INSTANCE *,Streaming::InstanceContext &,_UNICODE_STRING const &,_UNICODE_STRING const &,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)

- ea: `0x14000bbd4`
- end: `0x14000bcaa`
- name: `?GetOrCreateStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@3@AEBU_UNICODE_STRING@@2AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z`
- size: `214`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, Streaming::InstanceContext *this@<rdx>, PFILE_OBJECT FileObject, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140008dc4`
- `0x140011f30`

## callees

- `0x140003408`
- `0x1400034fc`
- `0x140005fb8`
- `0x14000b748`
- `0x14000bbd4`
- `0x14000bcb0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000bc04`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bc04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bc90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bc90`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamContextFactory::GetOrCreateStreamContext(
        PFLT_INSTANCE Instance,
        Streaming::InstanceContext *this,
        __int64 a3,
        struct _UNICODE_STRING *a4,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT *a6)
{
  int DosName; // ebx
  struct _UNICODE_STRING *v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  PVOID P; // [rsp+40h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF

  v13 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v12 = 0;
  DosName = Streaming::InstanceContext::GetDosName(this, (const struct _UNICODE_STRING **)&v12);
  if ( DosName >= 0 )
  {
    DosName = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
                &v13,
                v12);
    if ( DosName >= 0 )
    {
      DosName = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(
                  &v13,
                  a3);
      if ( DosName >= 0 )
      {
        DosName = Streaming::Context::StreamContextFactory::GetStreamContext(Instance, FileObject, a6);
        if ( DosName == -1073741275 )
          DosName = Streaming::Context::StreamContextFactory::CreateStreamContext(
                      Instance,
                      a4,
                      &DestinationString,
                      FileObject,
                      a6);
      }
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)DosName;
}

```

## disassembly

```asm
0x14000bbd4  push    rbp
0x14000bbd6  push    rbx
0x14000bbd7  push    rsi
0x14000bbd8  push    rdi
0x14000bbd9  push    r14
0x14000bbdb  mov     rbp, rsp
0x14000bbde  sub     rsp, 60h
0x14000bbe2  mov     rbx, rdx
0x14000bbe5  mov     [rbp+var_28], 0
0x14000bbed  mov     rsi, rcx
0x14000bbf0  mov     [rbp+P], 0
0x14000bbf8  xor     edx, edx; SourceString
0x14000bbfa  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000bbfe  mov     r14, r9
0x14000bc01  mov     rdi, r8
0x14000bc04  call    cs:__imp_RtlInitUnicodeString
0x14000bc0b  nop     dword ptr [rax+rax+00h]
0x14000bc10  lea     rdx, [rbp+var_30]; struct _UNICODE_STRING **
0x14000bc14  mov     [rbp+var_30], 0
0x14000bc1c  mov     rcx, rbx; this
0x14000bc1f  call    ?GetDosName@InstanceContext@Streaming@@QEAAJAEAPEBU_UNICODE_STRING@@@Z; Streaming::InstanceContext::GetDosName(_UNICODE_STRING const * &)
0x14000bc24  mov     ebx, eax
0x14000bc26  test    eax, eax
0x14000bc28  js      short loc_14000BC85
0x14000bc2a  mov     rdx, [rbp+var_30]
0x14000bc2e  lea     rcx, [rbp+var_28]
0x14000bc32  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x14000bc37  mov     ebx, eax
0x14000bc39  test    eax, eax
0x14000bc3b  js      short loc_14000BC85
0x14000bc3d  mov     rdx, rdi
0x14000bc40  lea     rcx, [rbp+var_28]
0x14000bc44  call    ?append@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(_UNICODE_STRING const &)
0x14000bc49  mov     ebx, eax
0x14000bc4b  test    eax, eax
0x14000bc4d  js      short loc_14000BC85
0x14000bc4f  mov     rdi, [rbp+arg_28]
0x14000bc53  mov     rcx, rsi
0x14000bc56  mov     rdx, [rbp+FileObject]
0x14000bc5a  mov     r8, rdi
0x14000bc5d  call    ?GetStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::GetStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x14000bc62  mov     ebx, eax
0x14000bc64  cmp     eax, 0C0000225h
0x14000bc69  jnz     short loc_14000BC85
0x14000bc6b  mov     r9, [rbp+FileObject]; FileObject
0x14000bc6f  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x14000bc73  mov     rdx, r14; struct _UNICODE_STRING *
0x14000bc76  mov     [rsp+60h+var_40], rdi; __int64
0x14000bc7b  mov     rcx, rsi; Instance
0x14000bc7e  call    ?CreateStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@1AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::CreateStreamContext(_FLT_INSTANCE *,_UNICODE_STRING const &,_UNICODE_STRING const &,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x14000bc83  mov     ebx, eax
0x14000bc85  mov     rcx, [rbp+P]; P
0x14000bc89  test    rcx, rcx
0x14000bc8c  jz      short loc_14000BC9C
0x14000bc8e  xor     edx, edx; Tag
0x14000bc90  call    cs:__imp_ExFreePoolWithTag
0x14000bc97  nop     dword ptr [rax+rax+00h]
0x14000bc9c  mov     eax, ebx
0x14000bc9e  add     rsp, 60h
0x14000bca2  pop     r14
0x14000bca4  pop     rdi
0x14000bca5  pop     rsi
0x14000bca6  pop     rbx
0x14000bca7  pop     rbp
0x14000bca8  retn
```
