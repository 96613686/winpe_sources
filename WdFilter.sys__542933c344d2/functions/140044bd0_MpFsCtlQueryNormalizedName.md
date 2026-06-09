# MpFsCtlQueryNormalizedName

- ea: `0x140044bd0`
- end: `0x140044e6c`
- name: `MpFsCtlQueryNormalizedName`
- size: `668`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400448f0`

## callees

- `0x1400018a4`
- `0x1400118d0`
- `0x140011900`
- `0x140044bd0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140044c5b`
- `ntoskrnl!ProbeForRead` at `0x140044c5b`
- `ntoskrnl!ProbeForWrite` at `0x140044ce5`
- `ntoskrnl!ProbeForWrite` at `0x140044ce5`
- `ntoskrnl!IoThreadToProcess` at `0x140044c33`
- `ntoskrnl!IoThreadToProcess` at `0x140044e08`
- `ntoskrnl!IoThreadToProcess` at `0x140044c33`
- `ntoskrnl!IoThreadToProcess` at `0x140044e08`
- `FLTMGR!FltGetFileNameInformation` at `0x140044c9e`
- `FLTMGR!FltGetFileNameInformation` at `0x140044c9e`
- `FLTMGR!FltGetFileSystemType` at `0x140044c77`
- `FLTMGR!FltGetFileSystemType` at `0x140044c77`
- `FLTMGR!FltQueryInformationFile` at `0x140044dc0`
- `FLTMGR!FltQueryInformationFile` at `0x140044dc0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140044d5f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140044d5f`

## pseudocode

```c
NTSTATUS __fastcall MpFsCtlQueryNormalizedName(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  FLT_FILE_NAME_OPTIONS v4; // r14d
  struct _KPROCESS *v5; // rdi
  int v6; // edi
  NTSTATUS result; // eax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  _DWORD *EaBuffer; // rsi
  SIZE_T Length; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v11; // rcx
  PFLT_FILE_NAME_INFORMATION v12; // rdx
  unsigned __int64 v13; // rcx
  NTSTATUS v14; // eax
  struct _KPROCESS *v15; // rdi
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+38h] [rbp-40h] BYREF
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+40h] [rbp-38h] BYREF
  ULONG LengthReturned; // [rsp+44h] [rbp-34h] BYREF
  __int64 FileInformation; // [rsp+48h] [rbp-30h] BYREF

  FileNameInformation = 0;
  v4 = 257;
  FileSystemType = FLT_FSTYPE_UNKNOWN;
  if ( *(int *)(MpData + 868) < 0
    || (v5 = *(struct _KPROCESS **)(MpData + 232), IoThreadToProcess(KeGetCurrentThread()) == v5)
    || (v15 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v15) )
  {
    ProbeForRead(CallbackData->Iopb->Parameters.CreatePipe.Parameters, 8u, 4u);
    FltGetFileSystemType(*(PVOID *)(a2 + 24), &FileSystemType);
    if ( FileSystemType == FLT_FSTYPE_MUP
      && (LengthReturned = 0,
          FileInformation = 0,
          v14 = FltQueryInformationFile(
                  *(PFLT_INSTANCE *)(a2 + 24),
                  *(PFILE_OBJECT *)(a2 + 32),
                  &FileInformation,
                  8u,
                  FileNormalizedNameInformation,
                  &LengthReturned),
          (int)(v14 + 0x80000000) >= 0) )
    {
      v6 = -2147483643;
      if ( v14 != -2147483643 )
        v4 = 258;
    }
    else
    {
      v6 = -2147483643;
    }
    result = FltGetFileNameInformation(CallbackData, v4, &FileNameInformation);
    if ( result < 0 )
    {
      _mm_lfence();
    }
    else
    {
      _mm_lfence();
      Iopb = CallbackData->Iopb;
      EaBuffer = Iopb->Parameters.Create.EaBuffer;
      Length = Iopb->Parameters.Read.Length;
      v11 = FileNameInformation;
      if ( (unsigned int)FileNameInformation->Name.Length + 4 <= (unsigned int)Length )
      {
        _mm_lfence();
        ProbeForWrite(EaBuffer, Length, 2u);
        *EaBuffer = 0;
        v12 = FileNameInformation;
        v13 = FileNameInformation->Name.Length;
        if ( (_DWORD)v13 == FileNameInformation->Volume.Length + 2
          && FileNameInformation->Name.Buffer[(v13 >> 1) - 1] == 92 )
        {
          *EaBuffer = 1;
          v12 = FileNameInformation;
        }
        memmove(EaBuffer + 1, v12->Name.Buffer, v12->Name.Length);
        v11 = FileNameInformation;
        CallbackData->IoStatus.Information = FileNameInformation->Name.Length + 4LL;
        v6 = 0;
      }
      if ( v11 )
        FltReleaseFileNameInformation(v11);
      return v6;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
        *(unsigned int *)(MpData + 868));
    return -1073741790;
  }
  return result;
}

```

## disassembly

```asm
0x140044bd0  mov     [rsp+arg_10], rbx
0x140044bd5  mov     [rsp+arg_18], rsi
0x140044bda  push    rdi
0x140044bdb  push    r14
0x140044bdd  push    r15
0x140044bdf  sub     rsp, 60h
0x140044be3  mov     rax, cs:__security_cookie
0x140044bea  xor     rax, rsp
0x140044bed  mov     [rsp+78h+var_28], rax
0x140044bf2  mov     rsi, rdx
0x140044bf5  mov     rbx, rcx
0x140044bf8  xor     r15d, r15d
0x140044bfb  mov     [rsp+78h+FileNameInformation], r15
0x140044c00  mov     r14d, 101h
0x140044c06  mov     [rsp+78h+FileSystemType], r15d
0x140044c0b  mov     rax, cs:MpData
0x140044c12  mov     ecx, [rax+364h]
0x140044c18  test    ecx, ecx
0x140044c1a  js      short loc_140044C48
0x140044c1c  mov     rcx, gs:188h; Thread
0x140044c25  mov     rax, cs:MpData
0x140044c2c  mov     rdi, [rax+0E8h]
0x140044c33  call    cs:__imp_IoThreadToProcess
0x140044c3a  nop     dword ptr [rax+rax+00h]
0x140044c3f  cmp     rax, rdi
0x140044c42  jnz     loc_140044DF1
0x140044c48  mov     rcx, [rbx+10h]
0x140044c4c  mov     edx, 8; Length
0x140044c51  mov     r8d, 4; Alignment
0x140044c57  mov     rcx, [rcx+30h]; Address
0x140044c5b  call    cs:__imp_ProbeForRead
0x140044c62  nop     dword ptr [rax+rax+00h]
0x140044c67  jmp     short loc_140044C6E
0x140044c69  jmp     loc_140044D6D
0x140044c6e  lea     rdx, [rsp+78h+FileSystemType]; FileSystemType
0x140044c73  mov     rcx, [rsi+18h]; FltObject
0x140044c77  call    cs:__imp_FltGetFileSystemType
0x140044c7e  nop     dword ptr [rax+rax+00h]
0x140044c83  cmp     [rsp+78h+FileSystemType], 0Dh
0x140044c88  jz      loc_140044D91
0x140044c8e  mov     edi, 80000005h
0x140044c93  lea     r8, [rsp+78h+FileNameInformation]; FileNameInformation
0x140044c98  mov     edx, r14d; NameOptions
0x140044c9b  mov     rcx, rbx; CallbackData
0x140044c9e  call    cs:__imp_FltGetFileNameInformation
0x140044ca5  nop     dword ptr [rax+rax+00h]
0x140044caa  test    eax, eax
0x140044cac  js      loc_140044E64
0x140044cb2  lfence
0x140044cb5  mov     rax, [rbx+10h]
0x140044cb9  mov     rsi, [rax+38h]
0x140044cbd  mov     edx, [rax+18h]; Length
0x140044cc0  mov     rcx, [rsp+78h+FileNameInformation]
0x140044cc5  movzx   eax, word ptr [rcx+8]
0x140044cc9  add     eax, 4
0x140044ccc  cmp     eax, edx
0x140044cce  jbe     short loc_140044CD9
0x140044cd0  mov     [rsp+78h+var_48], edi
0x140044cd4  jmp     loc_140044D5A
0x140044cd9  lfence
0x140044cdc  mov     r8d, 2; Alignment
0x140044ce2  mov     rcx, rsi; Address
0x140044ce5  call    cs:__imp_ProbeForWrite
0x140044cec  nop     dword ptr [rax+rax+00h]
0x140044cf1  mov     [rsi], r15d
0x140044cf4  mov     rdx, [rsp+78h+FileNameInformation]
0x140044cf9  movzx   ecx, word ptr [rdx+8]
0x140044cfd  movzx   eax, word ptr [rdx+18h]
0x140044d01  add     eax, 2
0x140044d04  cmp     ecx, eax
0x140044d06  jnz     short loc_140044D22
0x140044d08  shr     rcx, 1
0x140044d0b  mov     rax, [rdx+10h]
0x140044d0f  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140044d15  jnz     short loc_140044D22
0x140044d17  mov     dword ptr [rsi], 1
0x140044d1d  mov     rdx, [rsp+78h+FileNameInformation]
0x140044d22  movzx   r8d, word ptr [rdx+8]; Size
0x140044d27  lea     rcx, [rsi+4]; void *
0x140044d2b  mov     rdx, [rdx+10h]; Src
0x140044d2f  call    memmove
0x140044d34  mov     rcx, [rsp+78h+FileNameInformation]
0x140044d39  movzx   eax, word ptr [rcx+8]
0x140044d3d  add     rax, 4
0x140044d41  mov     [rbx+20h], rax
0x140044d45  mov     edi, r15d
0x140044d48  mov     [rsp+78h+var_48], r15d
0x140044d4d  jmp     short loc_140044D5A
0x140044d4f  mov     edi, eax
0x140044d51  mov     [rsp+78h+var_48], eax
0x140044d55  mov     rcx, [rsp+78h+FileNameInformation]; FileNameInformation
0x140044d5a  test    rcx, rcx
0x140044d5d  jz      short loc_140044D6B
0x140044d5f  call    cs:__imp_FltReleaseFileNameInformation
0x140044d66  nop     dword ptr [rax+rax+00h]
0x140044d6b  mov     eax, edi
0x140044d6d  mov     rcx, [rsp+78h+var_28]
0x140044d72  xor     rcx, rsp; StackCookie
0x140044d75  call    __security_check_cookie
0x140044d7a  lea     r11, [rsp+78h+var_18]
0x140044d7f  mov     rbx, [r11+30h]
0x140044d83  mov     rsi, [r11+38h]
0x140044d87  mov     rsp, r11
0x140044d8a  pop     r15
0x140044d8c  pop     r14
0x140044d8e  pop     rdi
0x140044d8f  retn
0x140044d91  mov     [rsp+78h+var_34], r15d
0x140044d96  mov     [rsp+78h+FileInformation], r15
0x140044d9b  lea     rax, [rsp+78h+var_34]
0x140044da0  mov     [rsp+78h+LengthReturned], rax; LengthReturned
0x140044da5  mov     [rsp+78h+FileInformationClass], 30h ; '0'; FileInformationClass
0x140044dad  mov     r9d, 8; Length
0x140044db3  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x140044db8  mov     rdx, [rsi+20h]; FileObject
0x140044dbc  mov     rcx, [rsi+18h]; Instance
0x140044dc0  call    cs:__imp_FltQueryInformationFile
0x140044dc7  nop     dword ptr [rax+rax+00h]
0x140044dcc  mov     edx, 80000000h
0x140044dd1  lea     ecx, [rax+rdx]
0x140044dd4  test    edx, ecx
0x140044dd6  jnz     loc_140044C8E
0x140044ddc  mov     ecx, 102h
0x140044de1  mov     edi, 80000005h
0x140044de6  cmp     eax, edi
0x140044de8  cmovnz  r14d, ecx
0x140044dec  jmp     loc_140044C93
0x140044df1  mov     rcx, gs:188h; Thread
0x140044dfa  mov     rax, cs:MpData
0x140044e01  mov     rdi, [rax+100h]
0x140044e08  call    cs:__imp_IoThreadToProcess
0x140044e0f  nop     dword ptr [rax+rax+00h]
0x140044e14  cmp     rax, rdi
0x140044e17  jz      loc_140044C48
0x140044e1d  lea     rax, WPP_GLOBAL_Control
0x140044e24  mov     rcx, cs:WPP_GLOBAL_Control
0x140044e2b  cmp     rcx, rax
0x140044e2e  jz      short loc_140044E5A
0x140044e30  mov     eax, [rcx+2Ch]
0x140044e33  test    al, 1
0x140044e35  jz      short loc_140044E5A
0x140044e37  mov     rcx, [rcx+18h]
0x140044e3b  mov     edx, 14h
0x140044e40  mov     r9, cs:MpData
0x140044e47  mov     r9d, [r9+364h]
0x140044e4e  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140044e55  call    WPP_SF_d
0x140044e5a  mov     eax, 0C0000022h
0x140044e5f  jmp     loc_140044D6D
0x140044e64  lfence
0x140044e67  jmp     loc_140044D6D
```
