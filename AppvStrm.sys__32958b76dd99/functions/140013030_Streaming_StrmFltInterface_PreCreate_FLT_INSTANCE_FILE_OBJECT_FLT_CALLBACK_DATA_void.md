# Streaming::StrmFltInterface::PreCreate(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,void * &)

- ea: `0x140013030`
- end: `0x14001315a`
- name: `?PreCreate@StrmFltInterface@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAPEAX@Z`
- size: `298`
- prototype: `__int64 __fastcall(Streaming::StrmFltInterface *this, struct _FLT_INSTANCE *, struct _FILE_OBJECT *, struct _FLT_CALLBACK_DATA *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140001aa0`

## callees

- `0x140002de4`
- `0x1400034fc`
- `0x1400037fc`
- `0x140013030`
- `0x140015f00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140013079`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001309b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400130f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013079`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001309b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400130f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001312d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001312d`
- `ntoskrnl!ExAllocatePool2` at `0x14001304d`
- `ntoskrnl!ExAllocatePool2` at `0x14001304d`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400130c9`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400130c9`

## pseudocode

```c
__int64 __fastcall Streaming::StrmFltInterface::PreCreate(
        Streaming::StrmFltInterface *this,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        struct _FLT_CALLBACK_DATA *a4,
        void **a5)
{
  _BYTE *Pool2; // rax
  _BYTE *v7; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  ULONG Options; // eax
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF
  PVOID P; // [rsp+28h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  Pool2 = (_BYTE *)ExAllocatePool2(256, 72, 1667458675);
  v7 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, 0x48u);
  RtlInitUnicodeString((PUNICODE_STRING)(v7 + 24), 0);
  *((_QWORD *)v7 + 5) = 0;
  *((_QWORD *)v7 + 6) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(v7 + 56), 0);
  *a5 = v7;
  *v7 = 0;
  Iopb = a4->Iopb;
  Options = Iopb->Parameters.Create.Options;
  if ( (Options & 0x200000) != 0 )
  {
    Iopb->Parameters.Create.Options = Options & 0xFFDFFFFF;
    FltSetCallbackDataDirty(a4);
    *v7 = 1;
    v11 = 0;
    P = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
      &v11,
      &a4->Iopb->TargetFileObject->FileName);
    appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::swap(v7 + 40, &v11);
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
  Streaming::FileOperations::GetParentDirOpenNameFromCallback(a4);
  return 0;
}

```

## disassembly

```asm
0x140013030  mov     [rsp+arg_0], rbx
0x140013035  push    rdi
0x140013036  sub     rsp, 40h
0x14001303a  mov     edx, 48h ; 'H'
0x14001303f  mov     ecx, 100h
0x140013044  mov     r8d, 63636673h
0x14001304a  mov     rdi, r9
0x14001304d  call    cs:__imp_ExAllocatePool2
0x140013054  nop     dword ptr [rax+rax+00h]
0x140013059  mov     rbx, rax
0x14001305c  test    rax, rax
0x14001305f  jz      loc_140013149
0x140013065  xor     edx, edx; Val
0x140013067  mov     rcx, rax; void *
0x14001306a  lea     r8d, [rdx+48h]; Size
0x14001306e  call    memset
0x140013073  lea     rcx, [rbx+18h]; DestinationString
0x140013077  xor     edx, edx; SourceString
0x140013079  call    cs:__imp_RtlInitUnicodeString
0x140013080  nop     dword ptr [rax+rax+00h]
0x140013085  lea     rcx, [rbx+38h]; DestinationString
0x140013089  mov     qword ptr [rbx+28h], 0
0x140013091  xor     edx, edx; SourceString
0x140013093  mov     qword ptr [rbx+30h], 0
0x14001309b  call    cs:__imp_RtlInitUnicodeString
0x1400130a2  nop     dword ptr [rax+rax+00h]
0x1400130a7  mov     rax, [rsp+48h+arg_20]
0x1400130ac  mov     [rax], rbx
0x1400130af  mov     byte ptr [rbx], 0
0x1400130b2  mov     rcx, [rdi+10h]
0x1400130b6  mov     eax, [rcx+20h]
0x1400130b9  bt      eax, 15h
0x1400130bd  jnb     short loc_140013139
0x1400130bf  btr     eax, 15h
0x1400130c3  mov     [rcx+20h], eax
0x1400130c6  mov     rcx, rdi; Data
0x1400130c9  call    cs:__imp_FltSetCallbackDataDirty
0x1400130d0  nop     dword ptr [rax+rax+00h]
0x1400130d5  xor     edx, edx; SourceString
0x1400130d7  mov     byte ptr [rbx], 1
0x1400130da  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1400130df  mov     [rsp+48h+var_28], 0
0x1400130e8  mov     [rsp+48h+P], 0
0x1400130f1  call    cs:__imp_RtlInitUnicodeString
0x1400130f8  nop     dword ptr [rax+rax+00h]
0x1400130fd  mov     rax, [rdi+10h]
0x140013101  lea     rcx, [rsp+48h+var_28]
0x140013106  mov     rdx, [rax+8]
0x14001310a  add     rdx, 58h ; 'X'
0x14001310e  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x140013113  lea     rcx, [rbx+28h]
0x140013117  lea     rdx, [rsp+48h+var_28]
0x14001311c  call    ?swap@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEAV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::swap(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140013121  mov     rcx, [rsp+48h+P]; P
0x140013126  test    rcx, rcx
0x140013129  jz      short loc_140013139
0x14001312b  xor     edx, edx; Tag
0x14001312d  call    cs:__imp_ExFreePoolWithTag
0x140013134  nop     dword ptr [rax+rax+00h]
0x140013139  lea     rdx, [rbx+8]
0x14001313d  mov     rcx, rdi; CallbackData
0x140013140  call    ?GetParentDirOpenNameFromCallback@FileOperations@Streaming@@YAJAEAU_FLT_CALLBACK_DATA@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::FileOperations::GetParentDirOpenNameFromCallback(_FLT_CALLBACK_DATA &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140013145  xor     eax, eax
0x140013147  jmp     short loc_14001314E
0x140013149  mov     eax, 0C000009Ah
0x14001314e  mov     rbx, [rsp+48h+arg_0]
0x140013153  add     rsp, 40h
0x140013157  pop     rdi
0x140013158  retn
```
