# appv::vemgr::path_normalizer::normalize<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool)

- ea: `0x180003750`
- end: `0x1800038f3`
- name: `??$normalize@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@path_normalizer@vemgr@appv@@CAJAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@_N@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800038fc`

## callees

- `0x180003750`
- `0x18000a9e4`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x180003802`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18000382a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18000382a`
- `ntoskrnl!IoCreateFile` at `0x1800037ee`
- `ntoskrnl!IoCreateFile` at `0x1800037ee`
- `ntoskrnl!ZwClose` at `0x180003844`
- `ntoskrnl!ZwClose` at `0x1800038cd`
- `ntoskrnl!ZwClose` at `0x180003844`
- `ntoskrnl!ZwClose` at `0x1800038cd`
- `ntoskrnl!ObfDereferenceObject` at `0x1800038b9`
- `ntoskrnl!ObfDereferenceObject` at `0x1800038b9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1800038aa`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1800038aa`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x18000387a`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x18000387a`

## pseudocode

```c
NTSTATUS __fastcall appv::vemgr::path_normalizer::normalize<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        struct _UNICODE_STRING *a1,
        unsigned __int8 a2)
{
  NTSTATUS result; // eax
  void *v4; // rbx
  NTSTATUS v5; // edi
  PVOID v6; // rdi
  NTSTATUS FileNameInformationUnsafe; // esi
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp+7h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+E8h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+77h] BYREF
  PVOID Object; // [rsp+100h] [rbp+7Fh] BYREF

  ObjectAttributes.ObjectName = a1 + 1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  result = IoCreateFile(
             &FileHandle,
             0x100000u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0,
             7u,
             1u,
             a2 + 16416,
             0,
             0,
             CreateFileTypeNone,
             0,
             0x900u);
  if ( result >= 0 )
  {
    v4 = FileHandle;
    Object = 0;
    v5 = ObReferenceObjectByHandle(FileHandle, 0x100000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    if ( v5 >= 0 )
    {
      v6 = Object;
      if ( Object )
      {
        FileNameInformation = 0;
        FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                      (PFILE_OBJECT)Object,
                                      0,
                                      0x101u,
                                      &FileNameInformation);
        if ( FileNameInformationUnsafe >= 0 )
        {
          FileNameInformationUnsafe = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
                                        a1,
                                        FileNameInformation->Name.Buffer,
                                        (unsigned __int64)FileNameInformation->Name.Length >> 1);
          FltReleaseFileNameInformation(FileNameInformation);
        }
        ObfDereferenceObject(v6);
      }
      else
      {
        FileNameInformationUnsafe = -1073741811;
      }
      if ( v4 )
        ZwClose(v4);
      return FileNameInformationUnsafe;
    }
    else
    {
      if ( v4 )
        ZwClose(v4);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003750  mov     r11, rsp
0x180003753  mov     [r11+10h], rbx
0x180003757  push    rbp
0x180003758  push    rsi
0x180003759  push    rdi
0x18000375a  push    r14
0x18000375c  push    r15
0x18000375e  lea     rbp, [r11-5Fh]
0x180003762  sub     rsp, 0B0h
0x180003769  mov     dword ptr [rsp+68h], 900h; Options
0x180003771  lea     rax, [rcx+10h]
0x180003775  xor     r15d, r15d
0x180003778  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000377c  mov     [r11-78h], r15
0x180003780  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180003784  mov     [r11-80h], r15d
0x180003788  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000378c  mov     [rsp+50h], r15d; EaLength
0x180003791  xorps   xmm0, xmm0
0x180003794  mov     [rsp+0D0h+EaBuffer], r15; EaBuffer
0x180003799  mov     r14, rcx
0x18000379c  movzx   eax, dl
0x18000379f  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800037a3  add     eax, 4020h
0x1800037a8  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800037b0  mov     [rsp+0D0h+CreateOptions], eax; CreateOptions
0x1800037b4  mov     edi, 100000h
0x1800037b9  mov     [rsp+0D0h+Disposition], 1; Disposition
0x1800037c1  mov     edx, edi; DesiredAccess
0x1800037c3  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x1800037cb  mov     [rsp+0D0h+FileAttributes], r15d; FileAttributes
0x1800037d0  mov     [rsp+0D0h+AllocationSize], r15; AllocationSize
0x1800037d5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800037dd  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800037e1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800037e6  mov     [rbp+57h+FileHandle], r15
0x1800037ea  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800037ee  call    cs:__imp_IoCreateFile
0x1800037f5  nop     dword ptr [rax+rax+00h]
0x1800037fa  test    eax, eax
0x1800037fc  js      loc_1800038DB
0x180003802  mov     r8, cs:__imp_IoFileObjectType
0x180003809  lea     rax, [rbp+57h+Object]
0x18000380d  mov     rbx, [rbp+57h+FileHandle]
0x180003811  xor     r9d, r9d; AccessMode
0x180003814  mov     [rbp+57h+Object], r15
0x180003818  mov     edx, edi; DesiredAccess
0x18000381a  mov     qword ptr [rsp+0D0h+FileAttributes], r15; HandleInformation
0x18000381f  mov     rcx, rbx; Handle
0x180003822  mov     r8, [r8]; ObjectType
0x180003825  mov     [rsp+0D0h+AllocationSize], rax; Object
0x18000382a  call    cs:__imp_ObReferenceObjectByHandle
0x180003831  nop     dword ptr [rax+rax+00h]
0x180003836  mov     edi, eax
0x180003838  test    eax, eax
0x18000383a  jns     short loc_180003857
0x18000383c  test    rbx, rbx
0x18000383f  jz      short loc_180003850
0x180003841  mov     rcx, rbx; Handle
0x180003844  call    cs:__imp_ZwClose
0x18000384b  nop     dword ptr [rax+rax+00h]
0x180003850  mov     eax, edi
0x180003852  jmp     loc_1800038DB
0x180003857  mov     rdi, [rbp+57h+Object]
0x18000385b  test    rdi, rdi
0x18000385e  jnz     short loc_180003867
0x180003860  mov     esi, 0C000000Dh
0x180003865  jmp     short loc_1800038C5
0x180003867  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x18000386b  mov     [rbp+57h+FileNameInformation], r15
0x18000386f  xor     edx, edx; Instance
0x180003871  mov     r8d, 101h; NameOptions
0x180003877  mov     rcx, rdi; FileObject
0x18000387a  call    cs:__imp_FltGetFileNameInformationUnsafe
0x180003881  nop     dword ptr [rax+rax+00h]
0x180003886  mov     esi, eax
0x180003888  test    eax, eax
0x18000388a  js      short loc_1800038B6
0x18000388c  mov     rdx, [rbp+57h+FileNameInformation]
0x180003890  mov     rcx, r14
0x180003893  movzx   r8d, word ptr [rdx+8]
0x180003898  mov     rdx, [rdx+10h]
0x18000389c  shr     r8, 1
0x18000389f  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x1800038a4  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1800038a8  mov     esi, eax
0x1800038aa  call    cs:__imp_FltReleaseFileNameInformation
0x1800038b1  nop     dword ptr [rax+rax+00h]
0x1800038b6  mov     rcx, rdi; Object
0x1800038b9  call    cs:__imp_ObfDereferenceObject
0x1800038c0  nop     dword ptr [rax+rax+00h]
0x1800038c5  test    rbx, rbx
0x1800038c8  jz      short loc_1800038D9
0x1800038ca  mov     rcx, rbx; Handle
0x1800038cd  call    cs:__imp_ZwClose
0x1800038d4  nop     dword ptr [rax+rax+00h]
0x1800038d9  mov     eax, esi
0x1800038db  mov     rbx, [rsp+0D0h+arg_8]
0x1800038e3  add     rsp, 0B0h
0x1800038ea  pop     r15
0x1800038ec  pop     r14
0x1800038ee  pop     rdi
0x1800038ef  pop     rsi
0x1800038f0  pop     rbp
0x1800038f1  retn
```
