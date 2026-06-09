# Streaming::FileOperations::GetParentDirOpenNameFromCallback(_FLT_CALLBACK_DATA &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)

- ea: `0x140002de4`
- end: `0x140002ed5`
- name: `?GetParentDirOpenNameFromCallback@FileOperations@Streaming@@YAJAEAU_FLT_CALLBACK_DATA@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013030`

## callees

- `0x140002de4`
- `0x140003408`
- `0x1400034fc`
- `0x1400037fc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140002e1a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002e1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ea1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002eb6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002eb6`
- `FLTMGR!FltGetFileNameInformation` at `0x140002e32`
- `FLTMGR!FltGetFileNameInformation` at `0x140002e32`
- `FLTMGR!FltParseFileNameInformation` at `0x140002e48`
- `FLTMGR!FltParseFileNameInformation` at `0x140002e48`

## pseudocode

```c
__int64 __fastcall Streaming::FileOperations::GetParentDirOpenNameFromCallback(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2)
{
  int v4; // ebx
  struct _UNICODE_STRING v6; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp+20h] BYREF

  FileNameInformation = 0;
  *(_QWORD *)&v6.Length = 0;
  v6.Buffer = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v4 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
  if ( v4 >= 0 )
  {
    v4 = FltParseFileNameInformation(FileNameInformation);
    if ( v4 >= 0 )
    {
      v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
             (__int64)&v6,
             &FileNameInformation->Volume.Length);
      if ( v4 >= 0 )
      {
        v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(
               &v6,
               (const void **)&FileNameInformation->ParentDir);
        if ( v4 >= 0 )
          v4 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::swap(
                 a2,
                 &v6);
      }
    }
  }
  if ( v6.Buffer )
    ExFreePoolWithTag(v6.Buffer, 0);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140002de4  mov     [rsp-8+arg_0], rbx
0x140002de9  mov     [rsp-8+arg_8], rdi
0x140002dee  push    rbp
0x140002def  mov     rbp, rsp
0x140002df2  sub     rsp, 40h
0x140002df6  mov     rdi, rdx
0x140002df9  mov     [rbp+FileNameInformation], 0
0x140002e01  mov     rbx, rcx
0x140002e04  mov     [rbp+var_20], 0
0x140002e0c  xor     edx, edx; SourceString
0x140002e0e  mov     [rbp+P], 0
0x140002e16  lea     rcx, [rbp+DestinationString]; DestinationString
0x140002e1a  call    cs:__imp_RtlInitUnicodeString
0x140002e21  nop     dword ptr [rax+rax+00h]
0x140002e26  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x140002e2a  mov     edx, 102h; NameOptions
0x140002e2f  mov     rcx, rbx; CallbackData
0x140002e32  call    cs:__imp_FltGetFileNameInformation
0x140002e39  nop     dword ptr [rax+rax+00h]
0x140002e3e  mov     ebx, eax
0x140002e40  test    eax, eax
0x140002e42  js      short loc_140002E96
0x140002e44  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140002e48  call    cs:__imp_FltParseFileNameInformation
0x140002e4f  nop     dword ptr [rax+rax+00h]
0x140002e54  mov     ebx, eax
0x140002e56  test    eax, eax
0x140002e58  js      short loc_140002E96
0x140002e5a  mov     rdx, [rbp+FileNameInformation]
0x140002e5e  lea     rcx, [rbp+var_20]
0x140002e62  add     rdx, 18h
0x140002e66  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x140002e6b  mov     ebx, eax
0x140002e6d  test    eax, eax
0x140002e6f  js      short loc_140002E96
0x140002e71  mov     rdx, [rbp+FileNameInformation]
0x140002e75  lea     rcx, [rbp+var_20]
0x140002e79  add     rdx, 68h ; 'h'
0x140002e7d  call    ?append@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(_UNICODE_STRING const &)
0x140002e82  mov     ebx, eax
0x140002e84  test    eax, eax
0x140002e86  js      short loc_140002E96
0x140002e88  lea     rdx, [rbp+var_20]
0x140002e8c  mov     rcx, rdi
0x140002e8f  call    ?swap@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEAV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::swap(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140002e94  mov     ebx, eax
0x140002e96  mov     rcx, [rbp+P]; P
0x140002e9a  test    rcx, rcx
0x140002e9d  jz      short loc_140002EAD
0x140002e9f  xor     edx, edx; Tag
0x140002ea1  call    cs:__imp_ExFreePoolWithTag
0x140002ea8  nop     dword ptr [rax+rax+00h]
0x140002ead  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140002eb1  test    rcx, rcx
0x140002eb4  jz      short loc_140002EC2
0x140002eb6  call    cs:__imp_FltReleaseFileNameInformation
0x140002ebd  nop     dword ptr [rax+rax+00h]
0x140002ec2  mov     rdi, [rsp+40h+arg_8]
0x140002ec7  mov     eax, ebx
0x140002ec9  mov     rbx, [rsp+40h+arg_0]
0x140002ece  add     rsp, 40h
0x140002ed2  pop     rbp
0x140002ed3  retn
```
