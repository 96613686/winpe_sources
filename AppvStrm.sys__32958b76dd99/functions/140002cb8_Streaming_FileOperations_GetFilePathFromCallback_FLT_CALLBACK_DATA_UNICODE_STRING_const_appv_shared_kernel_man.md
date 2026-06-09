# Streaming::FileOperations::GetFilePathFromCallback(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)

- ea: `0x140002cb8`
- end: `0x140002ddc`
- name: `?GetFilePathFromCallback@FileOperations@Streaming@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@2@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, const void **, struct _UNICODE_STRING *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a310`
- `0x14000ba94`

## callees

- `0x140002cb8`
- `0x140003408`
- `0x1400034fc`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x140002dc2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002dc2`
- `FLTMGR!FltGetFileNameInformation` at `0x140002ce0`
- `FLTMGR!FltGetFileNameInformation` at `0x140002ce0`
- `FLTMGR!FltParseFileNameInformation` at `0x140002cfa`
- `FLTMGR!FltParseFileNameInformation` at `0x140002cfa`

## pseudocode

```c
__int64 __fastcall Streaming::FileOperations::GetFilePathFromCallback(
        struct _FLT_CALLBACK_DATA *a1,
        const void **a2,
        struct _UNICODE_STRING *a3,
        __int64 a4)
{
  NTSTATUS v7; // eax
  struct _FLT_FILE_NAME_INFORMATION *v8; // rcx
  signed int v9; // ebx
  PFLT_FILE_NAME_INFORMATION v10; // rdx
  __int64 Length; // rcx
  char *v12; // r9
  unsigned int v13; // ecx
  __int16 v14; // r8
  signed int v15; // eax
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+20h] [rbp-20h] BYREF
  __int128 v18; // [rsp+28h] [rbp-18h] BYREF

  FileNameInformation = 0;
  v7 = FltGetFileNameInformation(a1, 0x101u, &FileNameInformation);
  v8 = FileNameInformation;
  v9 = v7;
  if ( v7 < 0 )
  {
LABEL_16:
    if ( v8 )
      goto LABEL_17;
    return (unsigned int)v9;
  }
  v9 = FltParseFileNameInformation(FileNameInformation);
  if ( v9 < 0
    || (v9 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(a3, a2),
        v9 < 0) )
  {
LABEL_15:
    v8 = FileNameInformation;
    goto LABEL_16;
  }
  v10 = FileNameInformation;
  Length = FileNameInformation->Volume.Length;
  v12 = (char *)FileNameInformation->Name.Buffer + Length;
  if ( !v12 )
  {
    v9 = -1073741811;
    goto LABEL_12;
  }
  v13 = 2 * (unsigned __int16)(((unsigned __int64)FileNameInformation->Name.Length - Length) >> 1);
  v18 = 0;
  if ( v13 > 0xFFFF )
    v14 = -1;
  else
    v14 = v13;
  v9 = v13 > 0xFFFF ? 0xC0000095 : 0;
  if ( (v13 > 0xFFFF ? 0xC0000000 : 0) != 0xC0000000 )
  {
    *((_QWORD *)&v18 + 1) = v12;
    WORD1(v18) = v14;
    LOWORD(v18) = v14;
    v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(
            a3,
            (const void **)&v18);
    v10 = FileNameInformation;
    v9 = v15;
  }
  if ( v9 >= 0 )
  {
    v9 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
           a4,
           &v10->Name.Length);
    goto LABEL_15;
  }
LABEL_12:
  if ( v10 )
  {
    v8 = v10;
LABEL_17:
    FltReleaseFileNameInformation(v8);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140002cb8  push    rbp
0x140002cba  push    rbx
0x140002cbb  push    rsi
0x140002cbc  push    rdi
0x140002cbd  push    r14
0x140002cbf  mov     rbp, rsp
0x140002cc2  sub     rsp, 40h
0x140002cc6  mov     rdi, r8
0x140002cc9  mov     [rbp+FileNameInformation], 0
0x140002cd1  mov     rsi, rdx
0x140002cd4  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x140002cd8  mov     edx, 101h; NameOptions
0x140002cdd  mov     r14, r9
0x140002ce0  call    cs:__imp_FltGetFileNameInformation
0x140002ce7  nop     dword ptr [rax+rax+00h]
0x140002cec  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140002cf0  mov     ebx, eax
0x140002cf2  test    eax, eax
0x140002cf4  js      loc_140002DBD
0x140002cfa  call    cs:__imp_FltParseFileNameInformation
0x140002d01  nop     dword ptr [rax+rax+00h]
0x140002d06  mov     ebx, eax
0x140002d08  test    eax, eax
0x140002d0a  js      loc_140002DB9
0x140002d10  mov     rdx, rsi
0x140002d13  mov     rcx, rdi
0x140002d16  call    ?append@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(_UNICODE_STRING const &)
0x140002d1b  mov     ebx, eax
0x140002d1d  test    eax, eax
0x140002d1f  js      loc_140002DB9
0x140002d25  mov     rdx, [rbp+FileNameInformation]
0x140002d29  movzx   ecx, word ptr [rdx+18h]
0x140002d2d  mov     r9, [rdx+10h]
0x140002d31  add     r9, rcx
0x140002d34  jnz     short loc_140002D3D
0x140002d36  mov     ebx, 0C000000Dh
0x140002d3b  jmp     short loc_140002DA1
0x140002d3d  movzx   eax, word ptr [rdx+8]
0x140002d41  xorps   xmm0, xmm0
0x140002d44  sub     rax, rcx
0x140002d47  shr     rax, 1
0x140002d4a  movzx   ecx, ax
0x140002d4d  mov     eax, 0FFFFh
0x140002d52  add     rcx, rcx
0x140002d55  movups  [rbp+var_18], xmm0
0x140002d59  cmp     ecx, eax
0x140002d5b  ja      short loc_140002D63
0x140002d5d  movzx   r8d, cx
0x140002d61  jmp     short loc_140002D66
0x140002d63  mov     r8d, eax
0x140002d66  cmp     eax, ecx
0x140002d68  mov     ecx, 0C0000000h
0x140002d6d  sbb     ebx, ebx
0x140002d6f  and     ebx, 0C0000095h
0x140002d75  mov     eax, ebx
0x140002d77  and     eax, ecx
0x140002d79  cmp     eax, ecx
0x140002d7b  jz      short loc_140002D9D
0x140002d7d  lea     rdx, [rbp+var_18]
0x140002d81  mov     qword ptr [rbp+var_18+8], r9
0x140002d85  mov     rcx, rdi
0x140002d88  mov     word ptr [rbp+var_18+2], r8w
0x140002d8d  mov     word ptr [rbp+var_18], r8w
0x140002d92  call    ?append@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(_UNICODE_STRING const &)
0x140002d97  mov     rdx, [rbp+FileNameInformation]
0x140002d9b  mov     ebx, eax
0x140002d9d  test    ebx, ebx
0x140002d9f  jns     short loc_140002DAB
0x140002da1  test    rdx, rdx
0x140002da4  jz      short loc_140002DCE
0x140002da6  mov     rcx, rdx
0x140002da9  jmp     short loc_140002DC2
0x140002dab  add     rdx, 8
0x140002daf  mov     rcx, r14
0x140002db2  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x140002db7  mov     ebx, eax
0x140002db9  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140002dbd  test    rcx, rcx
0x140002dc0  jz      short loc_140002DCE
0x140002dc2  call    cs:__imp_FltReleaseFileNameInformation
0x140002dc9  nop     dword ptr [rax+rax+00h]
0x140002dce  mov     eax, ebx
0x140002dd0  add     rsp, 40h
0x140002dd4  pop     r14
0x140002dd6  pop     rdi
0x140002dd7  pop     rsi
0x140002dd8  pop     rbx
0x140002dd9  pop     rbp
0x140002dda  retn
```
