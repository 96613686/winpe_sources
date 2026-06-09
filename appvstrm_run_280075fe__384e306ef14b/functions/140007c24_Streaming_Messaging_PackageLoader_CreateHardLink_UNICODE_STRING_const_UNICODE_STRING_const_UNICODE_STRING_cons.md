# Streaming::Messaging::PackageLoader::CreateHardLink(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &)

- ea: `0x140007c24`
- end: `0x140007fde`
- name: `?CreateHardLink@PackageLoader@Messaging@Streaming@@SAJAEBU_UNICODE_STRING@@00@Z`
- size: `954`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x140010df4`

## callees

- `0x1400030b8`
- `0x140005ed8`
- `0x140007c24`
- `0x1400147fc`
- `0x140014a50`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140007cc5`
- `ntoskrnl!ObfDereferenceObject` at `0x140007e1f`
- `ntoskrnl!ObfDereferenceObject` at `0x140007f70`
- `ntoskrnl!ObfDereferenceObject` at `0x140007cc5`
- `ntoskrnl!ObfDereferenceObject` at `0x140007e1f`
- `ntoskrnl!ObfDereferenceObject` at `0x140007f70`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007c60`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007c7a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007c60`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007c7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007f8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007fa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007f8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007fa2`
- `ntoskrnl!ExAllocatePool2` at `0x140007ee1`
- `ntoskrnl!ExAllocatePool2` at `0x140007ee1`
- `FLTMGR!FltClose` at `0x140007cac`
- `FLTMGR!FltClose` at `0x140007e06`
- `FLTMGR!FltClose` at `0x140007f57`
- `FLTMGR!FltClose` at `0x140007cac`
- `FLTMGR!FltClose` at `0x140007e06`
- `FLTMGR!FltClose` at `0x140007f57`
- `FLTMGR!FltSetInformationFile` at `0x140007f2f`
- `FLTMGR!FltSetInformationFile` at `0x140007f2f`
- `FLTMGR!FltReleaseContext` at `0x140007e66`
- `FLTMGR!FltReleaseContext` at `0x140007fb7`
- `FLTMGR!FltReleaseContext` at `0x140007e66`
- `FLTMGR!FltReleaseContext` at `0x140007fb7`

## string_xrefs

- `0x140007d65`: `PackageLoader::CreateHardLink() - Filter might not be attached to the volume. Couldn't find instance for volume %s . Failure Status 0x%08X.`
- `0x140007ebd`: `PackageLoader::CreateHardLink() - Streaming Filter could not open file for streaming file %s .Failure status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::PackageLoader::CreateHardLink(
        const struct _UNICODE_STRING *a1,
        const struct _UNICODE_STRING *a2,
        const struct _UNICODE_STRING *a3)
{
  int FileFullName; // ebx
  Streaming::InstanceContextFactory *v8; // rcx
  NTSTATUS ContextByVolumeName; // esi
  __int64 v10; // rbx
  __int64 *CurrentActivityID; // rax
  const WCHAR *v12; // r8
  volatile signed __int32 *Buffer; // rdi
  volatile signed __int32 *v14; // rdi
  struct _FILE_OBJECT *v15; // rsi
  ULONG v16; // edi
  __int64 Pool2; // rax
  _DWORD *v18; // rbx
  unsigned int v19; // edi
  void *v20; // rcx
  unsigned int Length; // eax
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-39h]
  HANDLE FileHandle; // [rsp+30h] [rbp-29h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-21h] BYREF
  PFLT_INSTANCE Instance; // [rsp+40h] [rbp-19h] BYREF
  volatile signed __int32 *v26; // [rsp+48h] [rbp-11h]
  __int64 v27; // [rsp+50h] [rbp-9h] BYREF
  PVOID v28; // [rsp+58h] [rbp-1h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  struct _UNICODE_STRING v30; // [rsp+70h] [rbp+17h] BYREF
  __int64 v31; // [rsp+80h] [rbp+27h] BYREF
  PVOID P; // [rsp+88h] [rbp+2Fh]
  struct _UNICODE_STRING v33; // [rsp+90h] [rbp+37h] BYREF
  PVOID Object; // [rsp+D8h] [rbp+7Fh] BYREF

  Context = 0;
  Instance = 0;
  v27 = 0;
  v28 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v31 = 0;
  P = 0;
  RtlInitUnicodeString(&v33, 0);
  Object = 0;
  FileHandle = 0;
  FileFullName = Streaming::Utils::GetFileFullName(a1, a2, &v27);
  if ( FileFullName < 0 || (FileFullName = Streaming::Utils::GetFileFullName(a1, a3, &v31), FileFullName < 0) )
  {
    if ( Object )
    {
      ObfDereferenceObject(Object);
      Object = 0;
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    return (unsigned int)FileFullName;
  }
  else
  {
    v8 = (Streaming::InstanceContextFactory *)*((_QWORD *)Streaming::gStrmFltData + 3);
    v30 = *a1;
    ContextByVolumeName = Streaming::InstanceContextFactory::GetContextByVolumeName(
                            v8,
                            &v30,
                            &Instance,
                            (struct Streaming::InstanceContext *)&Context);
    if ( ContextByVolumeName < 0 )
    {
      v10 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&Instance, a1);
      CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v30);
      v12 = L"PackageLoader::CreateHardLink() - Filter might not be attached to the volume. Couldn't find instance for vol"
             "ume %s . Failure Status 0x%08X.";
      goto LABEL_12;
    }
    ContextByVolumeName = Streaming::FileOperations::OpenFileForStreaming(
                            *((struct _FLT_FILTER **)Streaming::gStrmFltData + 1),
                            Instance,
                            &v33,
                            (PFILE_OBJECT *)&Object,
                            &FileHandle);
    if ( ContextByVolumeName < 0 )
    {
      v10 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&Instance, &v33);
      CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v30);
      v12 = L"PackageLoader::CreateHardLink() - Streaming Filter could not open file for streaming file %s .Failure status 0x%08X.";
LABEL_12:
      FileInformationClass[0] = ContextByVolumeName;
      LogWrite(1, *CurrentActivityID, v12, v10, *(_QWORD *)FileInformationClass);
      Buffer = (volatile signed __int32 *)v30.Buffer;
      if ( v30.Buffer )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30.Buffer + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 8LL))(Buffer);
          if ( _InterlockedExchangeAdd(Buffer + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 16LL))(Buffer);
        }
      }
      v14 = v26;
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
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
      if ( P )
        ExFreePoolWithTag(P, 0);
      if ( v28 )
        ExFreePoolWithTag(v28, 0);
      if ( Context )
        FltReleaseContext(Context);
      return (unsigned int)ContextByVolumeName;
    }
    v15 = (struct _FILE_OBJECT *)Object;
    v16 = DestinationString.Length + 20;
    Pool2 = ExAllocatePool2(256, v16, 1818781299);
    v18 = (_DWORD *)Pool2;
    if ( Pool2 )
    {
      *(_BYTE *)Pool2 = 0;
      v20 = (void *)(Pool2 + 20);
      *(_QWORD *)(Pool2 + 8) = 0;
      Length = DestinationString.Length;
      v18[4] = DestinationString.Length;
      memmove(v20, DestinationString.Buffer, Length);
      v19 = FltSetInformationFile(Instance, v15, v18, v16, FileLinkInformation);
      ExFreePoolWithTag(v18, 0);
    }
    else
    {
      v19 = -1073741670;
    }
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
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    if ( Context )
      FltReleaseContext(Context);
    return v19;
  }
}

```

## disassembly

```asm
0x140007c24  mov     [rsp-8+arg_0], rbx
0x140007c29  mov     [rsp-8+arg_8], rsi
0x140007c2e  push    rbp
0x140007c2f  push    rdi
0x140007c30  push    r14
0x140007c32  lea     rbp, [rsp-47h]
0x140007c37  sub     rsp, 0A0h
0x140007c3e  xor     r14d, r14d
0x140007c41  mov     rbx, rdx
0x140007c44  mov     rdi, rcx
0x140007c47  mov     [rbp+57h+Context], r14
0x140007c4b  xor     edx, edx; SourceString
0x140007c4d  mov     [rbp+57h+Instance], r14
0x140007c51  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007c55  mov     [rbp+57h+var_60], r14
0x140007c59  mov     [rbp+57h+var_58], r14
0x140007c5d  mov     rsi, r8
0x140007c60  call    cs:__imp_RtlInitUnicodeString
0x140007c67  nop     dword ptr [rax+rax+00h]
0x140007c6c  xor     edx, edx; SourceString
0x140007c6e  mov     [rbp+57h+var_30], r14
0x140007c72  lea     rcx, [rbp+57h+var_20]; DestinationString
0x140007c76  mov     [rbp+57h+P], r14
0x140007c7a  call    cs:__imp_RtlInitUnicodeString
0x140007c81  nop     dword ptr [rax+rax+00h]
0x140007c86  lea     r8, [rbp+57h+var_60]
0x140007c8a  mov     [rbp+57h+Object], r14
0x140007c8e  mov     rdx, rbx
0x140007c91  mov     [rbp+57h+FileHandle], r14
0x140007c95  mov     rcx, rdi
0x140007c98  call    ?GetFileFullName@Utils@Streaming@@YAJAEBU_UNICODE_STRING@@0AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Utils::GetFileFullName(_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140007c9d  mov     ebx, eax
0x140007c9f  test    eax, eax
0x140007ca1  jns     short loc_140007D0A
0x140007ca3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140007ca7  test    rcx, rcx
0x140007caa  jz      short loc_140007CBC
0x140007cac  call    cs:__imp_FltClose
0x140007cb3  nop     dword ptr [rax+rax+00h]
0x140007cb8  mov     [rbp+57h+FileHandle], r14
0x140007cbc  mov     rcx, [rbp+57h+Object]; Object
0x140007cc0  test    rcx, rcx
0x140007cc3  jz      short loc_140007CD5
0x140007cc5  call    cs:__imp_ObfDereferenceObject
0x140007ccc  nop     dword ptr [rax+rax+00h]
0x140007cd1  mov     [rbp+57h+Object], r14
0x140007cd5  mov     rcx, [rbp+57h+P]; P
0x140007cd9  test    rcx, rcx
0x140007cdc  jz      short loc_140007CEC
0x140007cde  xor     edx, edx; Tag
0x140007ce0  call    cs:__imp_ExFreePoolWithTag
0x140007ce7  nop     dword ptr [rax+rax+00h]
0x140007cec  mov     rcx, [rbp+57h+var_58]; P
0x140007cf0  test    rcx, rcx
0x140007cf3  jz      short loc_140007D03
0x140007cf5  xor     edx, edx; Tag
0x140007cf7  call    cs:__imp_ExFreePoolWithTag
0x140007cfe  nop     dword ptr [rax+rax+00h]
0x140007d03  mov     eax, ebx
0x140007d05  jmp     loc_140007FC5
0x140007d0a  lea     r8, [rbp+57h+var_30]
0x140007d0e  mov     rdx, rsi
0x140007d11  mov     rcx, rdi
0x140007d14  call    ?GetFileFullName@Utils@Streaming@@YAJAEBU_UNICODE_STRING@@0AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Utils::GetFileFullName(_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x140007d19  mov     ebx, eax
0x140007d1b  test    eax, eax
0x140007d1d  js      short loc_140007CA3
0x140007d1f  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140007d26  lea     r9, [rbp+57h+Context]; struct Streaming::InstanceContext *
0x140007d2a  movups  xmm0, xmmword ptr [rdi]
0x140007d2d  lea     r8, [rbp+57h+Instance]; struct _FLT_INSTANCE **
0x140007d31  lea     rdx, [rbp+57h+var_40]; struct _UNICODE_STRING
0x140007d35  mov     rcx, [rcx+18h]; this
0x140007d39  movdqu  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x140007d3e  call    ?GetContextByVolumeName@InstanceContextFactory@Streaming@@QEAAJU_UNICODE_STRING@@AEAPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContextByVolumeName(_UNICODE_STRING,_FLT_INSTANCE * &,Streaming::InstanceContext &)
0x140007d43  mov     esi, eax
0x140007d45  test    eax, eax
0x140007d47  jns     loc_140007E79
0x140007d4d  mov     rdx, rdi
0x140007d50  lea     rcx, [rbp+57h+Instance]
0x140007d54  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140007d59  lea     rcx, [rbp+57h+var_40]
0x140007d5d  mov     rbx, [rax]
0x140007d60  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140007d65  lea     r8, aPackageloaderC_2; "PackageLoader::CreateHardLink() - Filte"...
0x140007d6c  mov     rdx, [rax]
0x140007d6f  mov     r9, rbx
0x140007d72  mov     ecx, 1
0x140007d77  mov     [rsp+0B0h+FileInformationClass], esi
0x140007d7b  call    LogWrite
0x140007d80  mov     rdi, [rbp+57h+var_40.Buffer]
0x140007d84  or      ebx, 0FFFFFFFFh
0x140007d87  test    rdi, rdi
0x140007d8a  jz      short loc_140007DC0
0x140007d8c  mov     eax, ebx
0x140007d8e  lock xadd [rdi+8], eax
0x140007d93  add     eax, ebx
0x140007d95  jnz     short loc_140007DC0
0x140007d97  mov     rax, [rdi]
0x140007d9a  mov     rcx, rdi
0x140007d9d  mov     rax, [rax+8]
0x140007da1  call    _guard_dispatch_icall
0x140007da6  mov     eax, ebx
0x140007da8  lock xadd [rdi+0Ch], eax
0x140007dad  add     eax, ebx
0x140007daf  jnz     short loc_140007DC0
0x140007db1  mov     rax, [rdi]
0x140007db4  mov     rcx, rdi
0x140007db7  mov     rax, [rax+10h]
0x140007dbb  call    _guard_dispatch_icall
0x140007dc0  mov     rdi, [rbp+57h+var_68]
0x140007dc4  test    rdi, rdi
0x140007dc7  jz      short loc_140007DFD
0x140007dc9  mov     eax, ebx
0x140007dcb  lock xadd [rdi+8], eax
0x140007dd0  add     eax, ebx
0x140007dd2  jnz     short loc_140007DFD
0x140007dd4  mov     rax, [rdi]
0x140007dd7  mov     rcx, rdi
0x140007dda  mov     rax, [rax+8]
0x140007dde  call    _guard_dispatch_icall
0x140007de3  mov     eax, ebx
0x140007de5  lock xadd [rdi+0Ch], eax
0x140007dea  add     eax, ebx
0x140007dec  jnz     short loc_140007DFD
0x140007dee  mov     rax, [rdi]
0x140007df1  mov     rcx, rdi
0x140007df4  mov     rax, [rax+10h]
0x140007df8  call    _guard_dispatch_icall
0x140007dfd  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140007e01  test    rcx, rcx
0x140007e04  jz      short loc_140007E16
0x140007e06  call    cs:__imp_FltClose
0x140007e0d  nop     dword ptr [rax+rax+00h]
0x140007e12  mov     [rbp+57h+FileHandle], r14
0x140007e16  mov     rcx, [rbp+57h+Object]; Object
0x140007e1a  test    rcx, rcx
0x140007e1d  jz      short loc_140007E2F
0x140007e1f  call    cs:__imp_ObfDereferenceObject
0x140007e26  nop     dword ptr [rax+rax+00h]
0x140007e2b  mov     [rbp+57h+Object], r14
0x140007e2f  mov     rcx, [rbp+57h+P]; P
0x140007e33  test    rcx, rcx
0x140007e36  jz      short loc_140007E46
0x140007e38  xor     edx, edx; Tag
0x140007e3a  call    cs:__imp_ExFreePoolWithTag
0x140007e41  nop     dword ptr [rax+rax+00h]
0x140007e46  mov     rcx, [rbp+57h+var_58]; P
0x140007e4a  test    rcx, rcx
0x140007e4d  jz      short loc_140007E5D
0x140007e4f  xor     edx, edx; Tag
0x140007e51  call    cs:__imp_ExFreePoolWithTag
0x140007e58  nop     dword ptr [rax+rax+00h]
0x140007e5d  mov     rcx, [rbp+57h+Context]; Context
0x140007e61  test    rcx, rcx
0x140007e64  jz      short loc_140007E72
0x140007e66  call    cs:__imp_FltReleaseContext
0x140007e6d  nop     dword ptr [rax+rax+00h]
0x140007e72  mov     eax, esi
0x140007e74  jmp     loc_140007FC5
0x140007e79  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140007e80  lea     rax, [rbp+57h+FileHandle]
0x140007e84  mov     rdx, [rbp+57h+Instance]; int
0x140007e88  lea     r9, [rbp+57h+Object]; int
0x140007e8c  lea     r8, [rbp+57h+var_20]; int
0x140007e90  mov     qword ptr [rsp+0B0h+FileInformationClass], rax; FileHandle
0x140007e95  mov     rcx, [rcx+8]; int
0x140007e99  call    ?OpenFileForStreaming@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEBU_UNICODE_STRING@@AEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z; Streaming::FileOperations::OpenFileForStreaming(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)
0x140007e9e  mov     esi, eax
0x140007ea0  test    eax, eax
0x140007ea2  jns     short loc_140007EC9
0x140007ea4  lea     rdx, [rbp+57h+var_20]
0x140007ea8  lea     rcx, [rbp+57h+Instance]
0x140007eac  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140007eb1  lea     rcx, [rbp+57h+var_40]
0x140007eb5  mov     rbx, [rax]
0x140007eb8  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140007ebd  lea     r8, aPackageloaderC_10; "PackageLoader::CreateHardLink() - Strea"...
0x140007ec4  jmp     loc_140007D6C
0x140007ec9  movzx   edi, [rbp+57h+DestinationString.Length]
0x140007ecd  mov     ecx, 100h
0x140007ed2  mov     rsi, [rbp+57h+Object]
0x140007ed6  add     edi, 14h
0x140007ed9  mov     edx, edi
0x140007edb  mov     r8d, 6C686673h
0x140007ee1  call    cs:__imp_ExAllocatePool2
0x140007ee8  nop     dword ptr [rax+rax+00h]
0x140007eed  mov     rbx, rax
0x140007ef0  test    rax, rax
0x140007ef3  jnz     short loc_140007EFC
0x140007ef5  mov     edi, 0C000009Ah
0x140007efa  jmp     short loc_140007F4E
0x140007efc  mov     [rax], r14b
0x140007eff  lea     rcx, [rbx+14h]; void *
0x140007f03  mov     [rax+8], r14
0x140007f07  movzx   eax, [rbp+57h+DestinationString.Length]
0x140007f0b  mov     [rbx+10h], eax
0x140007f0e  mov     r8d, eax; Size
0x140007f11  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x140007f15  call    memmove
0x140007f1a  mov     rcx, [rbp+57h+Instance]; Instance
0x140007f1e  mov     r9d, edi; Length
0x140007f21  mov     r8, rbx; FileInformation
0x140007f24  mov     [rsp+0B0h+FileInformationClass], 0Bh; FileInformationClass
0x140007f2c  mov     rdx, rsi; FileObject
0x140007f2f  call    cs:__imp_FltSetInformationFile
0x140007f36  nop     dword ptr [rax+rax+00h]
0x140007f3b  xor     edx, edx; Tag
0x140007f3d  mov     rcx, rbx; P
0x140007f40  mov     edi, eax
0x140007f42  call    cs:__imp_ExFreePoolWithTag
0x140007f49  nop     dword ptr [rax+rax+00h]
0x140007f4e  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140007f52  test    rcx, rcx
0x140007f55  jz      short loc_140007F67
0x140007f57  call    cs:__imp_FltClose
0x140007f5e  nop     dword ptr [rax+rax+00h]
0x140007f63  mov     [rbp+57h+FileHandle], r14
0x140007f67  mov     rcx, [rbp+57h+Object]; Object
0x140007f6b  test    rcx, rcx
0x140007f6e  jz      short loc_140007F80
0x140007f70  call    cs:__imp_ObfDereferenceObject
0x140007f77  nop     dword ptr [rax+rax+00h]
0x140007f7c  mov     [rbp+57h+Object], r14
0x140007f80  mov     rcx, [rbp+57h+P]; P
0x140007f84  test    rcx, rcx
0x140007f87  jz      short loc_140007F97
0x140007f89  xor     edx, edx; Tag
0x140007f8b  call    cs:__imp_ExFreePoolWithTag
0x140007f92  nop     dword ptr [rax+rax+00h]
0x140007f97  mov     rcx, [rbp+57h+var_58]; P
0x140007f9b  test    rcx, rcx
0x140007f9e  jz      short loc_140007FAE
0x140007fa0  xor     edx, edx; Tag
0x140007fa2  call    cs:__imp_ExFreePoolWithTag
0x140007fa9  nop     dword ptr [rax+rax+00h]
0x140007fae  mov     rcx, [rbp+57h+Context]; Context
0x140007fb2  test    rcx, rcx
0x140007fb5  jz      short loc_140007FC3
0x140007fb7  call    cs:__imp_FltReleaseContext
0x140007fbe  nop     dword ptr [rax+rax+00h]
0x140007fc3  mov     eax, edi
0x140007fc5  lea     r11, [rsp+0B0h+var_10]
0x140007fcd  mov     rbx, [r11+20h]
0x140007fd1  mov     rsi, [r11+28h]
0x140007fd5  mov     rsp, r11
0x140007fd8  pop     r14
0x140007fda  pop     rdi
0x140007fdb  pop     rbp
0x140007fdc  retn
```
