# Streaming::StreamingTargetFileObject::StreamingTargetFileObject(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,long &)

- ea: `0x140011a90`
- end: `0x140011b6b`
- name: `??0StreamingTargetFileObject@Streaming@@QEAA@AEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@345@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@345@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@345@AEAJ@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, __int64 *, PFLT_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011f30`

## callees

- `0x140003650`
- `0x140011a90`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140011ad5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011ad5`
- `FLTMGR!FltReferenceContext` at `0x140011b2d`
- `FLTMGR!FltReferenceContext` at `0x140011b2d`
- `FLTMGR!FltReleaseContext` at `0x140011b44`
- `FLTMGR!FltReleaseContext` at `0x140011b44`

## pseudocode

```c
__int64 __fastcall Streaming::StreamingTargetFileObject::StreamingTargetFileObject(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4,
        PFLT_CONTEXT *a5,
        int *a6)
{
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  PFLT_CONTEXT v14; // rbx

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 40), 0);
  v10 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
          a1 + 24,
          a2);
  *a6 = v10;
  if ( v10 >= 0 )
  {
    v11 = *a3;
    if ( *a3 && *a4 && *a5 )
    {
      *a3 = *(_QWORD *)(a1 + 8);
      v12 = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 8) = v11;
      v13 = *a4;
      *a4 = v12;
      *(_QWORD *)(a1 + 16) = v13;
      FltReferenceContext(*a5);
      v14 = *a5;
      if ( *(_QWORD *)a1 )
        FltReleaseContext(*(PFLT_CONTEXT *)a1);
      *(_QWORD *)a1 = v14;
    }
    else
    {
      *a6 = -1073741811;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140011a90  push    rbx
0x140011a92  push    rsi
0x140011a93  push    rdi
0x140011a94  push    r14
0x140011a96  push    r15
0x140011a98  sub     rsp, 20h
0x140011a9c  mov     rdi, rdx
0x140011a9f  mov     qword ptr [rcx], 0
0x140011aa6  mov     rsi, rcx
0x140011aa9  mov     qword ptr [rcx+8], 0
0x140011ab1  mov     qword ptr [rcx+10h], 0
0x140011ab9  xor     edx, edx; SourceString
0x140011abb  mov     qword ptr [rcx+18h], 0
0x140011ac3  mov     r14, r9
0x140011ac6  mov     qword ptr [rcx+20h], 0
0x140011ace  mov     r15, r8
0x140011ad1  add     rcx, 28h ; '('; DestinationString
0x140011ad5  call    cs:__imp_RtlInitUnicodeString
0x140011adc  nop     dword ptr [rax+rax+00h]
0x140011ae1  mov     rdx, rdi
0x140011ae4  lea     rcx, [rsi+18h]
0x140011ae8  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &)
0x140011aed  mov     rdx, [rsp+48h+arg_28]
0x140011af2  mov     [rdx], eax
0x140011af4  test    eax, eax
0x140011af6  js      short loc_140011B5B
0x140011af8  mov     rcx, [r15]
0x140011afb  test    rcx, rcx
0x140011afe  jz      short loc_140011B55
0x140011b00  cmp     qword ptr [r14], 0
0x140011b04  jz      short loc_140011B55
0x140011b06  mov     rbx, [rsp+48h+arg_20]
0x140011b0b  cmp     qword ptr [rbx], 0
0x140011b0f  jz      short loc_140011B55
0x140011b11  mov     rax, [rsi+8]
0x140011b15  mov     [r15], rax
0x140011b18  mov     rax, [rsi+10h]
0x140011b1c  mov     [rsi+8], rcx
0x140011b20  mov     rcx, [r14]
0x140011b23  mov     [r14], rax
0x140011b26  mov     [rsi+10h], rcx
0x140011b2a  mov     rcx, [rbx]; Context
0x140011b2d  call    cs:__imp_FltReferenceContext
0x140011b34  nop     dword ptr [rax+rax+00h]
0x140011b39  mov     rcx, [rsi]; Context
0x140011b3c  mov     rbx, [rbx]
0x140011b3f  test    rcx, rcx
0x140011b42  jz      short loc_140011B50
0x140011b44  call    cs:__imp_FltReleaseContext
0x140011b4b  nop     dword ptr [rax+rax+00h]
0x140011b50  mov     [rsi], rbx
0x140011b53  jmp     short loc_140011B5B
0x140011b55  mov     dword ptr [rdx], 0C000000Dh
0x140011b5b  mov     rax, rsi
0x140011b5e  add     rsp, 20h
0x140011b62  pop     r15
0x140011b64  pop     r14
0x140011b66  pop     rdi
0x140011b67  pop     rsi
0x140011b68  pop     rbx
0x140011b69  retn
```
