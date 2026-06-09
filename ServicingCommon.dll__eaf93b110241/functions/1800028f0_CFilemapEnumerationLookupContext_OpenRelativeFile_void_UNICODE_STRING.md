# CFilemapEnumerationLookupContext::OpenRelativeFile(void *,_UNICODE_STRING *)

- ea: `0x1800028f0`
- end: `0x180002bf2`
- name: `?OpenRelativeFile@CFilemapEnumerationLookupContext@@QEAAJPEAXPEAU_UNICODE_STRING@@@Z`
- size: `770`
- prototype: `__int64 __fastcall(CFilemapEnumerationLookupContext *__hidden this, void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002748`

## callees

- `0x1800028f0`
- `0x1800031e0`
- `0x18000327c`
- `0x180003358`
- `0x18001f554`
- `0x1800293a0`

## import_xrefs

- `ntdll!NtReadFile` at `0x180002a82`
- `ntdll!NtReadFile` at `0x180002a82`
- `ntdll!NtOpenFile` at `0x18000296b`
- `ntdll!NtOpenFile` at `0x18000296b`
- `ntdll!NtQueryInformationFile` at `0x18000299e`
- `ntdll!NtQueryInformationFile` at `0x18000299e`
- `ntdll!NtClose` at `0x1800029b4`
- `ntdll!NtClose` at `0x180002aa0`
- `ntdll!NtClose` at `0x1800029b4`
- `ntdll!NtClose` at `0x180002aa0`

## string_xrefs

- `0x180002bc1`: `Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)`
- `0x180002b08`: `Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))`

## pseudocode

```c
NTSTATUS __fastcall CFilemapEnumerationLookupContext::OpenRelativeFile(
        CFilemapEnumerationLookupContext *this,
        void *a2,
        struct _UNICODE_STRING *a3)
{
  NTSTATUS result; // eax
  unsigned __int64 v5; // rax
  ULONG Length; // esi
  unsigned __int64 v7; // rbx
  unsigned __int64 *v8; // r14
  __int64 v9; // rdx
  __int64 StringRoutine; // rax
  NTSTATUS v11; // ebx
  const char *v12; // rax
  const char *v13; // [rsp+50h] [rbp-59h] BYREF
  const char *v14; // [rsp+58h] [rbp-51h]
  __int64 v15; // [rsp+60h] [rbp-49h]
  const char *v16; // [rsp+68h] [rbp-41h]
  void *FileHandle; // [rsp+70h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-31h] BYREF
  int v19; // [rsp+A8h] [rbp-1h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp+7h] BYREF
  __int128 FileInformation; // [rsp+C0h] [rbp+17h] BYREF
  __int64 v22; // [rsp+D0h] [rbp+27h]

  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.ObjectName = a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v22 = 0;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  FileInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 1u, 0x20u);
  if ( result >= 0 )
  {
    if ( !FileHandle )
      return -1073741595;
    NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( HIDWORD(FileInformation) )
    {
      NtClose(FileHandle);
      return -1073741675;
    }
    v5 = *((_QWORD *)this + 2);
    Length = DWORD2(FileInformation);
    v7 = DWORD2(FileInformation);
    if ( v5 >= DWORD2(FileInformation) )
      goto LABEL_14;
    v8 = (unsigned __int64 *)((char *)this + 8);
    v19 = 0;
    if ( this == (CFilemapEnumerationLookupContext *)-8LL )
    {
      v15 = 130;
      v13 = "onecore\\base\\lstring\\lblob.cpp";
      v14 = "RtlReallocateLBlob";
      v12 = "Not-null check failed: Blob";
    }
    else
    {
      v9 = *((_QWORD *)this + 3);
      if ( (v9 || !*v8) && *v8 <= v5 )
      {
        if ( v9 )
        {
          StringRoutine = anonymous_namespace_::OurRtlReallocateStringRoutine(DWORD2(FileInformation));
          if ( StringRoutine )
            goto LABEL_12;
          v15 = 148;
          v13 = "onecore\\base\\lstring\\lblob.cpp";
          v14 = "RtlReallocateLBlob";
          v16 = "Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)";
          v11 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
                  &v19,
                  &v13);
          if ( v11 >= 0 )
          {
LABEL_14:
            v11 = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, *((PVOID *)this + 3), Length, 0, 0);
            if ( v11 >= 0 )
              *((_QWORD *)this + 1) = IoStatusBlock.Information;
          }
        }
        else
        {
          StringRoutine = anonymous_namespace_::OurRtlAllocateStringRoutine(DWORD2(FileInformation));
          if ( StringRoutine )
          {
LABEL_12:
            *((_QWORD *)this + 3) = StringRoutine;
            *((_QWORD *)this + 2) = v7;
            if ( *v8 > v7 )
              *v8 = v7;
            goto LABEL_14;
          }
          v15 = 153;
          v13 = "onecore\\base\\lstring\\lblob.cpp";
          v14 = "RtlReallocateLBlob";
          v16 = "Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))";
          RtlReportErrorOrigination(&v13, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
          v11 = -1073741801;
        }
LABEL_16:
        NtClose(FileHandle);
        return v11;
      }
      v15 = 131;
      v13 = "onecore\\base\\lstring\\lblob.cpp";
      v14 = "RtlReallocateLBlob";
      v12 = "::RtlIsLBlobValid(Blob)";
    }
    v16 = v12;
    RtlReportErrorOrigination(&v13, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    v11 = -1073741811;
    goto LABEL_16;
  }
  return result;
}

```

## disassembly

```asm
0x1800028f0  push    rbp
0x1800028f2  push    rdi
0x1800028f3  push    r15
0x1800028f5  lea     rbp, [rsp-47h]
0x1800028fa  sub     rsp, 0F0h
0x180002901  mov     rax, cs:__security_cookie
0x180002908  xor     rax, rsp
0x18000290b  mov     [rbp+57h+var_28], rax
0x18000290f  xorps   xmm0, xmm0
0x180002912  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdx
0x180002916  mov     rdi, rcx
0x180002919  mov     [rbp+57h+ObjectAttributes.ObjectName], r8
0x18000291d  xorps   xmm1, xmm1
0x180002920  mov     [rsp+100h+OpenOptions], 20h ; ' '; OpenOptions
0x180002928  xor     eax, eax
0x18000292a  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180002932  xor     r15d, r15d
0x180002935  mov     [rbp+57h+var_30], rax
0x180002939  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000293d  mov     [rbp+57h+FileHandle], r15
0x180002941  mov     edx, 120089h; DesiredAccess
0x180002946  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000294e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180002952  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x18000295a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000295e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180002962  movups  [rbp+57h+FileInformation], xmm1
0x180002966  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000296b  call    cs:__imp_NtOpenFile
0x180002972  nop     dword ptr [rax+rax+00h]
0x180002977  test    eax, eax
0x180002979  js      short loc_1800029C5
0x18000297b  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000297f  test    rcx, rcx
0x180002982  jz      loc_180002BE0
0x180002988  mov     r9d, 18h; Length
0x18000298e  mov     [rsp+100h+ShareAccess], 5; FileInformationClass
0x180002996  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000299a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000299e  call    cs:__imp_NtQueryInformationFile
0x1800029a5  nop     dword ptr [rax+rax+00h]
0x1800029aa  cmp     dword ptr [rbp+57h+FileInformation+0Ch], r15d
0x1800029ae  jz      short loc_1800029DE
0x1800029b0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800029b4  call    cs:__imp_NtClose
0x1800029bb  nop     dword ptr [rax+rax+00h]
0x1800029c0  mov     eax, 0C0000095h
0x1800029c5  mov     rcx, [rbp+57h+var_28]
0x1800029c9  xor     rcx, rsp; StackCookie
0x1800029cc  call    __security_check_cookie
0x1800029d1  add     rsp, 0F0h
0x1800029d8  pop     r15
0x1800029da  pop     rdi
0x1800029db  pop     rbp
0x1800029dc  retn
0x1800029de  mov     rax, [rdi+10h]
0x1800029e2  mov     [rsp+100h+arg_18], rbx
0x1800029ea  mov     [rsp+100h+var_18], rsi
0x1800029f2  mov     esi, dword ptr [rbp+57h+FileInformation+8]
0x1800029f5  mov     [rsp+100h+var_20], r14
0x1800029fd  mov     ebx, esi
0x1800029ff  cmp     rax, rsi
0x180002a02  jnb     short loc_180002A56
0x180002a04  lea     r14, [rdi+8]
0x180002a08  mov     [rbp+57h+var_58], r15d
0x180002a0c  test    r14, r14
0x180002a0f  jz      loc_180002B22
0x180002a15  mov     rdx, [r14+10h]
0x180002a19  test    rdx, rdx
0x180002a1c  jz      loc_180002B6B
0x180002a22  cmp     [r14], rax
0x180002a25  ja      loc_180002B74
0x180002a2b  mov     rcx, rbx
0x180002a2e  test    rdx, rdx
0x180002a31  jz      loc_180002ACB
0x180002a37  call    _anonymous_namespace___OurRtlReallocateStringRoutine
0x180002a3c  test    rax, rax
0x180002a3f  jz      loc_180002B9B
0x180002a45  mov     [r14+10h], rax
0x180002a49  mov     [r14+8], rbx
0x180002a4d  cmp     [r14], rbx
0x180002a50  ja      loc_180002BEA
0x180002a56  mov     rax, [rdi+18h]
0x180002a5a  xor     r9d, r9d; ApcContext
0x180002a5d  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180002a61  xor     r8d, r8d; ApcRoutine
0x180002a64  mov     [rsp+100h+Key], r15; Key
0x180002a69  xor     edx, edx; Event
0x180002a6b  mov     [rsp+100h+ByteOffset], r15; ByteOffset
0x180002a70  mov     [rsp+100h+Length], esi; Length
0x180002a74  mov     qword ptr [rsp+100h+OpenOptions], rax; Buffer
0x180002a79  lea     rax, [rbp+57h+IoStatusBlock]
0x180002a7d  mov     qword ptr [rsp+100h+ShareAccess], rax; IoStatusBlock
0x180002a82  call    cs:__imp_NtReadFile
0x180002a89  nop     dword ptr [rax+rax+00h]
0x180002a8e  mov     ebx, eax
0x180002a90  test    eax, eax
0x180002a92  js      short loc_180002A9C
0x180002a94  mov     rcx, [rbp+57h+IoStatusBlock.Information]
0x180002a98  mov     [rdi+8], rcx
0x180002a9c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180002aa0  call    cs:__imp_NtClose
0x180002aa7  nop     dword ptr [rax+rax+00h]
0x180002aac  mov     rsi, [rsp+100h+var_18]
0x180002ab4  mov     eax, ebx
0x180002ab6  mov     rbx, [rsp+100h+arg_18]
0x180002abe  mov     r14, [rsp+100h+var_20]
0x180002ac6  jmp     loc_1800029C5
0x180002acb  call    _anonymous_namespace___OurRtlAllocateStringRoutine
0x180002ad0  test    rax, rax
0x180002ad3  jnz     loc_180002A45
0x180002ad9  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180002ae0  mov     [rbp+57h+var_A0], 99h
0x180002ae8  mov     [rbp+57h+var_B0], rax
0x180002aec  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180002af3  lea     rax, aRtlreallocatel_4; "RtlReallocateLBlob"
0x180002afa  mov     r8d, 0C0000017h
0x180002b00  mov     [rbp+57h+var_A8], rax
0x180002b04  lea     rcx, [rbp+57h+var_B0]
0x180002b08  lea     rax, aTempPucharRtla; "Temp = (PUCHAR)((*RtlAllocateStringRout"...
0x180002b0f  mov     [rbp+57h+var_98], rax
0x180002b13  call    RtlReportErrorOrigination
0x180002b18  mov     ebx, 0C0000017h
0x180002b1d  jmp     loc_180002A9C
0x180002b22  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180002b29  mov     [rbp+57h+var_A0], 82h
0x180002b31  mov     [rbp+57h+var_B0], rax
0x180002b35  lea     rax, aRtlreallocatel_4; "RtlReallocateLBlob"
0x180002b3c  mov     [rbp+57h+var_A8], rax
0x180002b40  lea     rax, aNotNullCheckFa_117; "Not-null check failed: Blob"
0x180002b47  mov     r8d, 0C000000Dh
0x180002b4d  mov     [rbp+57h+var_98], rax
0x180002b51  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180002b58  lea     rcx, [rbp+57h+var_B0]
0x180002b5c  call    RtlReportErrorOrigination
0x180002b61  mov     ebx, 0C000000Dh
0x180002b66  jmp     loc_180002A9C
0x180002b6b  cmp     [r14], r15
0x180002b6e  jz      loc_180002A22
0x180002b74  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180002b7b  mov     [rbp+57h+var_A0], 83h
0x180002b83  mov     [rbp+57h+var_B0], rax
0x180002b87  lea     rax, aRtlreallocatel_4; "RtlReallocateLBlob"
0x180002b8e  mov     [rbp+57h+var_A8], rax
0x180002b92  lea     rax, aRtlislblobvali_5; "::RtlIsLBlobValid(Blob)"
0x180002b99  jmp     short loc_180002B47
0x180002b9b  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180002ba2  mov     [rbp+57h+var_A0], 94h
0x180002baa  mov     [rbp+57h+var_B0], rax
0x180002bae  lea     rdx, [rbp+57h+var_B0]
0x180002bb2  lea     rax, aRtlreallocatel_4; "RtlReallocateLBlob"
0x180002bb9  mov     [rbp+57h+var_A8], rax
0x180002bbd  lea     rcx, [rbp+57h+var_58]
0x180002bc1  lea     rax, aTempRtlrealloc; "Temp = (*RtlReallocateStringRoutine)(By"...
0x180002bc8  mov     [rbp+57h+var_98], rax
0x180002bcc  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180002bd1  mov     ebx, eax
0x180002bd3  test    eax, eax
0x180002bd5  jns     loc_180002A56
0x180002bdb  jmp     loc_180002A9C
0x180002be0  mov     eax, 0C00000E5h
0x180002be5  jmp     loc_1800029C5
0x180002bea  mov     [r14], rbx
0x180002bed  jmp     loc_180002A56
```
