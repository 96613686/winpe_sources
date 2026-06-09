# Streaming::FileOperations::GetDosFilePathUnsafe(_FLT_INSTANCE *,_FILE_OBJECT &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)

- ea: `0x140002a14`
- end: `0x140002b35`
- name: `?GetDosFilePathUnsafe@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEBU_UNICODE_STRING@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a310`

## callees

- `0x140002a14`
- `0x140003408`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x140002a5c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002b1d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002a5c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002b1d`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140002a41`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140002a41`
- `FLTMGR!FltParseFileNameInformation` at `0x140002a6f`
- `FLTMGR!FltParseFileNameInformation` at `0x140002a6f`

## pseudocode

```c
__int64 __fastcall Streaming::FileOperations::GetDosFilePathUnsafe(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        __int64 a4)
{
  NTSTATUS FileNameInformationUnsafe; // eax
  struct _FLT_FILE_NAME_INFORMATION *v7; // rcx
  NTSTATUS v8; // ebx
  int v10; // eax
  __int64 Length; // rdx
  char *v12; // r9
  unsigned int v13; // edx
  __int16 v14; // r8
  NTSTATUS v15; // eax
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+20h] [rbp-28h] BYREF
  __int128 v17; // [rsp+28h] [rbp-20h] BYREF

  FileNameInformation = 0;
  FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, Instance, 0x101u, &FileNameInformation);
  v7 = FileNameInformation;
  v8 = FileNameInformationUnsafe;
  if ( FileNameInformationUnsafe < 0 )
  {
LABEL_2:
    if ( v7 )
      FltReleaseFileNameInformation(v7);
    return (unsigned int)v8;
  }
  v8 = FltParseFileNameInformation(FileNameInformation);
  if ( v8 < 0 )
  {
    v7 = FileNameInformation;
    goto LABEL_2;
  }
  v10 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(a4, a3);
  v7 = FileNameInformation;
  v8 = v10;
  if ( v10 < 0 )
    goto LABEL_2;
  Length = FileNameInformation->Volume.Length;
  v12 = (char *)FileNameInformation->Name.Buffer + Length;
  if ( !v12 )
  {
    v8 = -1073741811;
    goto LABEL_2;
  }
  v13 = 2 * (unsigned __int16)(((unsigned __int64)FileNameInformation->Name.Length - Length) >> 1);
  v17 = 0;
  if ( v13 > 0xFFFF )
    v14 = -1;
  else
    v14 = v13;
  v8 = v13 > 0xFFFF ? 0xC0000095 : 0;
  if ( (v13 > 0xFFFF ? 0xC0000000 : 0) != 0xC0000000 )
  {
    *((_QWORD *)&v17 + 1) = v12;
    WORD1(v17) = v14;
    LOWORD(v17) = v14;
    v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(a4, &v17);
    v7 = FileNameInformation;
    v8 = v15;
  }
  if ( v8 < 0 )
    goto LABEL_2;
  if ( v7 )
    FltReleaseFileNameInformation(v7);
  return 0;
}

```

## disassembly

```asm
0x140002a14  push    rbp
0x140002a16  push    rbx
0x140002a17  push    rsi
0x140002a18  push    rdi
0x140002a19  mov     rbp, rsp
0x140002a1c  sub     rsp, 48h
0x140002a20  mov     rax, rdx
0x140002a23  mov     [rbp+FileNameInformation], 0
0x140002a2b  mov     rdx, rcx; Instance
0x140002a2e  mov     rdi, r9
0x140002a31  mov     rsi, r8
0x140002a34  lea     r9, [rbp+FileNameInformation]; FileNameInformation
0x140002a38  mov     rcx, rax; FileObject
0x140002a3b  mov     r8d, 101h; NameOptions
0x140002a41  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140002a48  nop     dword ptr [rax+rax+00h]
0x140002a4d  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140002a51  mov     ebx, eax
0x140002a53  test    eax, eax
0x140002a55  jns     short loc_140002A6F
0x140002a57  test    rcx, rcx
0x140002a5a  jz      short loc_140002A68
0x140002a5c  call    cs:__imp_FltReleaseFileNameInformation
0x140002a63  nop     dword ptr [rax+rax+00h]
0x140002a68  mov     eax, ebx
0x140002a6a  jmp     loc_140002B2B
0x140002a6f  call    cs:__imp_FltParseFileNameInformation
0x140002a76  nop     dword ptr [rax+rax+00h]
0x140002a7b  mov     ebx, eax
0x140002a7d  test    eax, eax
0x140002a7f  jns     short loc_140002A87
0x140002a81  mov     rcx, [rbp+FileNameInformation]
0x140002a85  jmp     short loc_140002A57
0x140002a87  mov     rdx, rsi
0x140002a8a  mov     rcx, rdi
0x140002a8d  call    ?append@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(_UNICODE_STRING const &)
0x140002a92  mov     rcx, [rbp+FileNameInformation]
0x140002a96  mov     ebx, eax
0x140002a98  test    eax, eax
0x140002a9a  js      short loc_140002A57
0x140002a9c  movzx   edx, word ptr [rcx+18h]
0x140002aa0  mov     r9, [rcx+10h]
0x140002aa4  add     r9, rdx
0x140002aa7  jnz     short loc_140002AB0
0x140002aa9  mov     ebx, 0C000000Dh
0x140002aae  jmp     short loc_140002A57
0x140002ab0  movzx   eax, word ptr [rcx+8]
0x140002ab4  xorps   xmm0, xmm0
0x140002ab7  sub     rax, rdx
0x140002aba  shr     rax, 1
0x140002abd  movzx   edx, ax
0x140002ac0  mov     eax, 0FFFFh
0x140002ac5  add     rdx, rdx
0x140002ac8  movups  [rbp+var_20], xmm0
0x140002acc  cmp     edx, eax
0x140002ace  ja      short loc_140002AD6
0x140002ad0  movzx   r8d, dx
0x140002ad4  jmp     short loc_140002AD9
0x140002ad6  mov     r8d, eax
0x140002ad9  cmp     eax, edx
0x140002adb  mov     edx, 0C0000000h
0x140002ae0  sbb     ebx, ebx
0x140002ae2  and     ebx, 0C0000095h
0x140002ae8  mov     eax, ebx
0x140002aea  and     eax, edx
0x140002aec  cmp     eax, edx
0x140002aee  jz      short loc_140002B10
0x140002af0  lea     rdx, [rbp+var_20]
0x140002af4  mov     qword ptr [rbp+var_20+8], r9
0x140002af8  mov     rcx, rdi
0x140002afb  mov     word ptr [rbp+var_20+2], r8w
0x140002b00  mov     word ptr [rbp+var_20], r8w
0x140002b05  call    ?append@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(_UNICODE_STRING const &)
0x140002b0a  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140002b0e  mov     ebx, eax
0x140002b10  test    ebx, ebx
0x140002b12  js      loc_140002A57
0x140002b18  test    rcx, rcx
0x140002b1b  jz      short loc_140002B29
0x140002b1d  call    cs:__imp_FltReleaseFileNameInformation
0x140002b24  nop     dword ptr [rax+rax+00h]
0x140002b29  xor     eax, eax
0x140002b2b  add     rsp, 48h
0x140002b2f  pop     rdi
0x140002b30  pop     rsi
0x140002b31  pop     rbx
0x140002b32  pop     rbp
0x140002b33  retn
```
