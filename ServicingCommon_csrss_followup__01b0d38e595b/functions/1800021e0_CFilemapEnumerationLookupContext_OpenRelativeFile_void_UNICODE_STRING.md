# CFilemapEnumerationLookupContext::OpenRelativeFile(void *,_UNICODE_STRING *)

- ea: `0x1800021e0`
- end: `0x1800024e2`
- name: `?OpenRelativeFile@CFilemapEnumerationLookupContext@@QEAAJPEAXPEAU_UNICODE_STRING@@@Z`
- size: `770`
- prototype: `__int64 __fastcall(CFilemapEnumerationLookupContext *__hidden this, void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002034`

## callees

- `0x1800021e0`
- `0x180009820`
- `0x18000bef8`
- `0x18000c478`
- `0x1800217cc`
- `0x18002d2b0`

## import_xrefs

- `ntdll!NtReadFile` at `0x180002372`
- `ntdll!NtReadFile` at `0x180002372`
- `ntdll!NtQueryInformationFile` at `0x18000228e`
- `ntdll!NtQueryInformationFile` at `0x18000228e`
- `ntdll!NtClose` at `0x1800022a4`
- `ntdll!NtClose` at `0x180002390`
- `ntdll!NtClose` at `0x1800022a4`
- `ntdll!NtClose` at `0x180002390`
- `ntdll!NtOpenFile` at `0x18000225b`
- `ntdll!NtOpenFile` at `0x18000225b`

## string_xrefs

- `0x1800023f8`: `Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))`
- `0x1800024b1`: `Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)`

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
0x1800021e0  push    rbp
0x1800021e2  push    rdi
0x1800021e3  push    r15
0x1800021e5  lea     rbp, [rsp-47h]
0x1800021ea  sub     rsp, 0F0h
0x1800021f1  mov     rax, cs:__security_cookie
0x1800021f8  xor     rax, rsp
0x1800021fb  mov     [rbp+57h+var_28], rax
0x1800021ff  xorps   xmm0, xmm0
0x180002202  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdx
0x180002206  mov     rdi, rcx
0x180002209  mov     [rbp+57h+ObjectAttributes.ObjectName], r8
0x18000220d  xorps   xmm1, xmm1
0x180002210  mov     [rsp+100h+OpenOptions], 20h ; ' '; OpenOptions
0x180002218  xor     eax, eax
0x18000221a  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180002222  xor     r15d, r15d
0x180002225  mov     [rbp+57h+var_30], rax
0x180002229  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000222d  mov     [rbp+57h+FileHandle], r15
0x180002231  mov     edx, 120089h; DesiredAccess
0x180002236  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000223e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180002242  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x18000224a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000224e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180002252  movups  [rbp+57h+FileInformation], xmm1
0x180002256  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000225b  call    cs:__imp_NtOpenFile
0x180002262  nop     dword ptr [rax+rax+00h]
0x180002267  test    eax, eax
0x180002269  js      short loc_1800022B5
0x18000226b  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000226f  test    rcx, rcx
0x180002272  jz      loc_1800024D0
0x180002278  mov     r9d, 18h; Length
0x18000227e  mov     [rsp+100h+ShareAccess], 5; FileInformationClass
0x180002286  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000228a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000228e  call    cs:__imp_NtQueryInformationFile
0x180002295  nop     dword ptr [rax+rax+00h]
0x18000229a  cmp     dword ptr [rbp+57h+FileInformation+0Ch], r15d
0x18000229e  jz      short loc_1800022CE
0x1800022a0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800022a4  call    cs:__imp_NtClose
0x1800022ab  nop     dword ptr [rax+rax+00h]
0x1800022b0  mov     eax, 0C0000095h
0x1800022b5  mov     rcx, [rbp+57h+var_28]
0x1800022b9  xor     rcx, rsp; StackCookie
0x1800022bc  call    __security_check_cookie
0x1800022c1  add     rsp, 0F0h
0x1800022c8  pop     r15
0x1800022ca  pop     rdi
0x1800022cb  pop     rbp
0x1800022cc  retn
0x1800022ce  mov     rax, [rdi+10h]
0x1800022d2  mov     [rsp+100h+arg_18], rbx
0x1800022da  mov     [rsp+100h+var_18], rsi
0x1800022e2  mov     esi, dword ptr [rbp+57h+FileInformation+8]
0x1800022e5  mov     [rsp+100h+var_20], r14
0x1800022ed  mov     ebx, esi
0x1800022ef  cmp     rax, rsi
0x1800022f2  jnb     short loc_180002346
0x1800022f4  lea     r14, [rdi+8]
0x1800022f8  mov     [rbp+57h+var_58], r15d
0x1800022fc  test    r14, r14
0x1800022ff  jz      loc_180002412
0x180002305  mov     rdx, [r14+10h]
0x180002309  test    rdx, rdx
0x18000230c  jz      loc_18000245B
0x180002312  cmp     [r14], rax
0x180002315  ja      loc_180002464
0x18000231b  mov     rcx, rbx
0x18000231e  test    rdx, rdx
0x180002321  jz      loc_1800023BB
0x180002327  call    _anonymous_namespace___OurRtlReallocateStringRoutine
0x18000232c  test    rax, rax
0x18000232f  jz      loc_18000248B
0x180002335  mov     [r14+10h], rax
0x180002339  mov     [r14+8], rbx
0x18000233d  cmp     [r14], rbx
0x180002340  ja      loc_1800024DA
0x180002346  mov     rax, [rdi+18h]
0x18000234a  xor     r9d, r9d; ApcContext
0x18000234d  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180002351  xor     r8d, r8d; ApcRoutine
0x180002354  mov     [rsp+100h+Key], r15; Key
0x180002359  xor     edx, edx; Event
0x18000235b  mov     [rsp+100h+ByteOffset], r15; ByteOffset
0x180002360  mov     [rsp+100h+Length], esi; Length
0x180002364  mov     qword ptr [rsp+100h+OpenOptions], rax; Buffer
0x180002369  lea     rax, [rbp+57h+IoStatusBlock]
0x18000236d  mov     qword ptr [rsp+100h+ShareAccess], rax; IoStatusBlock
0x180002372  call    cs:__imp_NtReadFile
0x180002379  nop     dword ptr [rax+rax+00h]
0x18000237e  mov     ebx, eax
0x180002380  test    eax, eax
0x180002382  js      short loc_18000238C
0x180002384  mov     rcx, [rbp+57h+IoStatusBlock.Information]
0x180002388  mov     [rdi+8], rcx
0x18000238c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180002390  call    cs:__imp_NtClose
0x180002397  nop     dword ptr [rax+rax+00h]
0x18000239c  mov     rsi, [rsp+100h+var_18]
0x1800023a4  mov     eax, ebx
0x1800023a6  mov     rbx, [rsp+100h+arg_18]
0x1800023ae  mov     r14, [rsp+100h+var_20]
0x1800023b6  jmp     loc_1800022B5
0x1800023bb  call    _anonymous_namespace___OurRtlAllocateStringRoutine
0x1800023c0  test    rax, rax
0x1800023c3  jnz     loc_180002335
0x1800023c9  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x1800023d0  mov     [rbp+57h+var_A0], 99h
0x1800023d8  mov     [rbp+57h+var_B0], rax
0x1800023dc  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800023e3  lea     rax, aRtlreallocatel_4; "RtlReallocateLBlob"
0x1800023ea  mov     r8d, 0C0000017h
0x1800023f0  mov     [rbp+57h+var_A8], rax
0x1800023f4  lea     rcx, [rbp+57h+var_B0]
0x1800023f8  lea     rax, aTempPucharRtla; "Temp = (PUCHAR)((*RtlAllocateStringRout"...
0x1800023ff  mov     [rbp+57h+var_98], rax
0x180002403  call    RtlReportErrorOrigination
0x180002408  mov     ebx, 0C0000017h
0x18000240d  jmp     loc_18000238C
0x180002412  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180002419  mov     [rbp+57h+var_A0], 82h
0x180002421  mov     [rbp+57h+var_B0], rax
0x180002425  lea     rax, aRtlreallocatel_4; "RtlReallocateLBlob"
0x18000242c  mov     [rbp+57h+var_A8], rax
0x180002430  lea     rax, aNotNullCheckFa_117; "Not-null check failed: Blob"
0x180002437  mov     r8d, 0C000000Dh
0x18000243d  mov     [rbp+57h+var_98], rax
0x180002441  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180002448  lea     rcx, [rbp+57h+var_B0]
0x18000244c  call    RtlReportErrorOrigination
0x180002451  mov     ebx, 0C000000Dh
0x180002456  jmp     loc_18000238C
0x18000245b  cmp     [r14], r15
0x18000245e  jz      loc_180002312
0x180002464  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18000246b  mov     [rbp+57h+var_A0], 83h
0x180002473  mov     [rbp+57h+var_B0], rax
0x180002477  lea     rax, aRtlreallocatel_4; "RtlReallocateLBlob"
0x18000247e  mov     [rbp+57h+var_A8], rax
0x180002482  lea     rax, aRtlislblobvali_5; "::RtlIsLBlobValid(Blob)"
0x180002489  jmp     short loc_180002437
0x18000248b  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180002492  mov     [rbp+57h+var_A0], 94h
0x18000249a  mov     [rbp+57h+var_B0], rax
0x18000249e  lea     rdx, [rbp+57h+var_B0]
0x1800024a2  lea     rax, aRtlreallocatel_4; "RtlReallocateLBlob"
0x1800024a9  mov     [rbp+57h+var_A8], rax
0x1800024ad  lea     rcx, [rbp+57h+var_58]
0x1800024b1  lea     rax, aTempRtlrealloc; "Temp = (*RtlReallocateStringRoutine)(By"...
0x1800024b8  mov     [rbp+57h+var_98], rax
0x1800024bc  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800024c1  mov     ebx, eax
0x1800024c3  test    eax, eax
0x1800024c5  jns     loc_180002346
0x1800024cb  jmp     loc_18000238C
0x1800024d0  mov     eax, 0C00000E5h
0x1800024d5  jmp     loc_1800022B5
0x1800024da  mov     [r14], rbx
0x1800024dd  jmp     loc_180002346
```
