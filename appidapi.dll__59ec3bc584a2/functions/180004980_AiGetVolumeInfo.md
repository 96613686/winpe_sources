# AiGetVolumeInfo

- ea: `0x180004980`
- end: `0x180004c9a`
- name: `AiGetVolumeInfo`
- size: `794`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800061c8`

## callees

- `0x180003fd4`
- `0x180004980`
- `0x18000533c`
- `0x1800055f0`
- `0x180009562`
- `0x1800095c0`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800049ea`
- `ntdll!RtlEqualUnicodeString` at `0x1800049ea`
- `ntdll!NtOpenFile` at `0x180004a95`
- `ntdll!NtOpenFile` at `0x180004a95`
- `ntdll!NtClose` at `0x180004c4e`
- `ntdll!NtClose` at `0x180004c4e`
- `ntdll!NtDeviceIoControlFile` at `0x180004b15`
- `ntdll!NtDeviceIoControlFile` at `0x180004b99`
- `ntdll!NtDeviceIoControlFile` at `0x180004c02`
- `ntdll!NtDeviceIoControlFile` at `0x180004b15`
- `ntdll!NtDeviceIoControlFile` at `0x180004b99`
- `ntdll!NtDeviceIoControlFile` at `0x180004c02`
- `ntdll!RtlFreeHeap` at `0x180004c3f`
- `ntdll!RtlFreeHeap` at `0x180004c70`
- `ntdll!RtlFreeHeap` at `0x180004c3f`
- `ntdll!RtlFreeHeap` at `0x180004c70`

## pseudocode

```c
__int64 __fastcall AiGetVolumeInfo(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, _DWORD *a3)
{
  _DWORD *v6; // rsi
  __int64 MaximumLength; // rcx
  WCHAR *v8; // rax
  int DeviceDosName; // ebx
  int v10; // edx
  int v11; // r8d
  void *v12; // rcx
  NTSTATUS v13; // eax
  void *v14; // rcx
  ULONG v15; // eax
  _DWORD *v16; // rax
  PWSTR Buffer; // r8
  void *FileHandle; // [rsp+50h] [rbp-49h] BYREF
  ULONG OutputBufferLength[2]; // [rsp+58h] [rbp-41h] BYREF
  __int64 OutputBuffer; // [rsp+60h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-31h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  __int64 InputBuffer; // [rsp+A8h] [rbp+Fh] BYREF
  int v25; // [rsp+B0h] [rbp+17h]

  a2->Buffer = 0;
  FileHandle = 0;
  OutputBuffer = 0;
  InputBuffer = 0;
  v25 = 0;
  *(_QWORD *)OutputBufferLength = 0;
  memset(&ObjectAttributes, 0, 44);
  v6 = 0;
  IoStatusBlock = 0;
  if ( RtlEqualUnicodeString(a1, &String2, 1u) )
  {
    *(_QWORD *)&a2->Length = xmmword_180010808;
    MaximumLength = a2->MaximumLength;
    a2->Buffer = (PWSTR)*((_QWORD *)&xmmword_180010808 + 1);
    v8 = (WCHAR *)AiAlloc(MaximumLength);
    a2->Buffer = v8;
    if ( v8 )
    {
      DeviceDosName = 0;
      memcpy_0(v8, *((const void **)&xmmword_180010808 + 1), a2->MaximumLength);
LABEL_25:
      *a3 = 0;
      goto LABEL_26;
    }
LABEL_4:
    DeviceDosName = -1073741801;
    goto LABEL_26;
  }
  DeviceDosName = AipGetDeviceDosName((const void **)a1, a2);
  if ( DeviceDosName < 0 )
    goto LABEL_26;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DeviceDosName = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( DeviceDosName >= 0 )
  {
    v12 = FileHandle;
    *a3 = 0;
    v13 = NtDeviceIoControlFile(v12, 0, 0, 0, &IoStatusBlock, 0x2D0C14u, 0, 0, &OutputBuffer, 8u);
    DeviceDosName = v13;
    if ( v13 < 0 )
      goto LABEL_12;
    if ( !*(_WORD *)((char *)&OutputBuffer + 5) )
      goto LABEL_26;
    v14 = FileHandle;
    *a3 = 1;
    InputBuffer = 0;
    v13 = NtDeviceIoControlFile(v14, 0, 0, 0, &IoStatusBlock, 0x2D1400u, &InputBuffer, 0xCu, OutputBufferLength, 8u);
    DeviceDosName = v13;
    if ( v13 < 0 )
    {
LABEL_12:
      if ( v13 != -1073741801 && v13 != -1073741670 )
        DeviceDosName = 0;
    }
    else
    {
      v15 = OutputBufferLength[1];
      if ( OutputBufferLength[1] < 0x28 )
        v15 = 40;
      OutputBufferLength[1] = v15;
      v16 = (_DWORD *)AiAlloc(v15);
      v6 = v16;
      if ( !v16 )
        goto LABEL_4;
      DeviceDosName = NtDeviceIoControlFile(
                        FileHandle,
                        0,
                        0,
                        0,
                        &IoStatusBlock,
                        0x2D1400u,
                        &InputBuffer,
                        0xCu,
                        v16,
                        OutputBufferLength[1]);
      if ( DeviceDosName >= 0 && (v6[7] == 1 || v6[7] == 3 || v6[7] == 6 || v6[7] == 8 || v6[7] == 11) )
        goto LABEL_25;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (_DWORD)a1, DeviceDosName);
  }
LABEL_26:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( FileHandle )
    NtClose(FileHandle);
  if ( DeviceDosName < 0 )
  {
    Buffer = a2->Buffer;
    if ( Buffer )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      a2->Buffer = 0;
    }
  }
  return (unsigned int)DeviceDosName;
}

```

## disassembly

```asm
0x180004980  push    rbp
0x180004982  push    rbx
0x180004983  push    rsi
0x180004984  push    rdi
0x180004985  push    r12
0x180004987  push    r14
0x180004989  push    r15
0x18000498b  lea     rbp, [rsp-27h]
0x180004990  sub     rsp, 0C0h
0x180004997  mov     rax, cs:__security_cookie
0x18000499e  xor     rax, rsp
0x1800049a1  mov     [rbp+57h+var_38], rax
0x1800049a5  xor     r12d, r12d
0x1800049a8  xorps   xmm0, xmm0
0x1800049ab  xor     eax, eax
0x1800049ad  mov     [rdx+8], r12
0x1800049b1  mov     r15, r8
0x1800049b4  mov     [rbp+57h+FileHandle], r12
0x1800049b8  mov     rdi, rdx
0x1800049bb  mov     [rbp+57h+var_90], r12
0x1800049bf  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800049c3  lea     rdx, String2; String2
0x1800049ca  mov     [rbp+57h+var_48], rax
0x1800049ce  mov     r8b, 1; CaseInsensitive
0x1800049d1  mov     [rbp+57h+var_40], eax
0x1800049d4  mov     r14, rcx
0x1800049d7  mov     qword ptr [rbp+57h+var_98], r12
0x1800049db  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800049df  mov     esi, r12d
0x1800049e2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800049e6  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800049ea  call    cs:__imp_RtlEqualUnicodeString
0x1800049f0  test    al, al
0x1800049f2  jz      short loc_180004A41
0x1800049f4  mov     rax, qword ptr cs:xmmword_180010808
0x1800049fb  mov     [rdi], rax
0x1800049fe  mov     rax, qword ptr cs:xmmword_180010808+8
0x180004a05  movzx   ecx, word ptr [rdi+2]
0x180004a09  mov     [rdi+8], rax
0x180004a0d  call    AiAlloc
0x180004a12  mov     [rdi+8], rax
0x180004a16  test    rax, rax
0x180004a19  jz      short loc_180004A37
0x180004a1b  movzx   r8d, word ptr [rdi+2]; Size
0x180004a20  mov     rcx, rax; void *
0x180004a23  mov     rdx, qword ptr cs:xmmword_180010808+8; Src
0x180004a2a  mov     ebx, r12d
0x180004a2d  call    memcpy_0
0x180004a32  jmp     loc_180004C2A
0x180004a37  mov     ebx, 0C0000017h
0x180004a3c  jmp     loc_180004C2D
0x180004a41  mov     rdx, rdi
0x180004a44  mov     rcx, r14
0x180004a47  call    AipGetDeviceDosName
0x180004a4c  mov     ebx, eax
0x180004a4e  test    eax, eax
0x180004a50  js      loc_180004C2D
0x180004a56  xorps   xmm0, xmm0
0x180004a59  mov     [rsp+0F0h+OpenOptions], 20h ; ' '; OpenOptions
0x180004a61  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180004a65  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180004a6c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180004a70  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180004a74  mov     edx, 100000h; DesiredAccess
0x180004a79  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180004a80  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180004a84  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x180004a88  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004a8d  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x180004a95  call    cs:__imp_NtOpenFile
0x180004a9b  mov     ebx, eax
0x180004a9d  test    eax, eax
0x180004a9f  jns     short loc_180004AD7
0x180004aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004aa8  lea     rax, WPP_GLOBAL_Control
0x180004aaf  cmp     rcx, rax
0x180004ab2  jz      loc_180004C2D
0x180004ab8  test    byte ptr [rcx+1Ch], 10h
0x180004abc  jz      loc_180004C2D
0x180004ac2  mov     rcx, [rcx+10h]
0x180004ac6  mov     r9, r14
0x180004ac9  mov     [rsp+0F0h+ShareAccess], ebx
0x180004acd  call    WPP_SF_ZD
0x180004ad2  jmp     loc_180004C2D
0x180004ad7  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180004adb  lea     rax, [rbp+57h+var_90]
0x180004adf  mov     r14d, 8
0x180004ae5  mov     [r15], r12d
0x180004ae8  mov     [rsp+0F0h+OutputBufferLength], r14d; OutputBufferLength
0x180004aed  xor     r9d, r9d; ApcContext
0x180004af0  mov     [rsp+0F0h+OutputBuffer], rax; OutputBuffer
0x180004af5  xor     r8d, r8d; ApcRoutine
0x180004af8  mov     [rsp+0F0h+InputBufferLength], r12d; InputBufferLength
0x180004afd  lea     rax, [rbp+57h+IoStatusBlock]
0x180004b01  mov     [rsp+0F0h+InputBuffer], r12; InputBuffer
0x180004b06  xor     edx, edx; Event
0x180004b08  mov     [rsp+0F0h+OpenOptions], 2D0C14h; IoControlCode
0x180004b10  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x180004b15  call    cs:__imp_NtDeviceIoControlFile
0x180004b1b  mov     ebx, eax
0x180004b1d  test    eax, eax
0x180004b1f  jns     short loc_180004B3F
0x180004b21  cmp     eax, 0C0000017h
0x180004b26  jz      loc_180004C2D
0x180004b2c  cmp     eax, 0C000009Ah
0x180004b31  jz      loc_180004C2D
0x180004b37  mov     ebx, r12d
0x180004b3a  jmp     loc_180004C2D
0x180004b3f  cmp     byte ptr [rbp+57h+var_90+5], r12b
0x180004b43  jnz     short loc_180004B4F
0x180004b45  cmp     byte ptr [rbp+57h+var_90+6], r12b
0x180004b49  jz      loc_180004C2D
0x180004b4f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180004b53  lea     rax, [rbp+57h+var_98]
0x180004b57  mov     [rsp+0F0h+OutputBufferLength], r14d; OutputBufferLength
0x180004b5c  xor     r9d, r9d; ApcContext
0x180004b5f  mov     [rsp+0F0h+OutputBuffer], rax; OutputBuffer
0x180004b64  mov     r14d, 0Ch
0x180004b6a  mov     [rsp+0F0h+InputBufferLength], r14d; InputBufferLength
0x180004b6f  lea     rax, [rbp+57h+var_48]
0x180004b73  mov     [rsp+0F0h+InputBuffer], rax; InputBuffer
0x180004b78  xor     r8d, r8d; ApcRoutine
0x180004b7b  lea     rax, [rbp+57h+IoStatusBlock]
0x180004b7f  mov     [rsp+0F0h+OpenOptions], 2D1400h; IoControlCode
0x180004b87  xor     edx, edx; Event
0x180004b89  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x180004b8e  mov     dword ptr [r15], 1
0x180004b95  mov     [rbp+57h+var_48], r12
0x180004b99  call    cs:__imp_NtDeviceIoControlFile
0x180004b9f  mov     ebx, eax
0x180004ba1  test    eax, eax
0x180004ba3  js      loc_180004B21
0x180004ba9  mov     eax, [rbp+57h+var_98+4]
0x180004bac  lea     ecx, [r14+1Ch]
0x180004bb0  cmp     eax, ecx
0x180004bb2  cmovb   eax, ecx
0x180004bb5  mov     ecx, eax
0x180004bb7  mov     [rbp+57h+var_98+4], eax
0x180004bba  call    AiAlloc
0x180004bbf  mov     rsi, rax
0x180004bc2  test    rax, rax
0x180004bc5  jz      loc_180004A37
0x180004bcb  mov     eax, [rbp+57h+var_98+4]
0x180004bce  xor     r9d, r9d; ApcContext
0x180004bd1  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180004bd5  xor     r8d, r8d; ApcRoutine
0x180004bd8  mov     [rsp+0F0h+OutputBufferLength], eax; OutputBufferLength
0x180004bdc  xor     edx, edx; Event
0x180004bde  mov     [rsp+0F0h+OutputBuffer], rsi; OutputBuffer
0x180004be3  lea     rax, [rbp+57h+var_48]
0x180004be7  mov     [rsp+0F0h+InputBufferLength], r14d; InputBufferLength
0x180004bec  mov     [rsp+0F0h+InputBuffer], rax; InputBuffer
0x180004bf1  lea     rax, [rbp+57h+IoStatusBlock]
0x180004bf5  mov     [rsp+0F0h+OpenOptions], 2D1400h; IoControlCode
0x180004bfd  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x180004c02  call    cs:__imp_NtDeviceIoControlFile
0x180004c08  mov     ebx, eax
0x180004c0a  test    eax, eax
0x180004c0c  js      short loc_180004C2D
0x180004c0e  mov     ecx, [rsi+1Ch]
0x180004c11  sub     ecx, 1
0x180004c14  jz      short loc_180004C2A
0x180004c16  sub     ecx, 2
0x180004c19  jz      short loc_180004C2A
0x180004c1b  sub     ecx, 3
0x180004c1e  jz      short loc_180004C2A
0x180004c20  sub     ecx, 2
0x180004c23  jz      short loc_180004C2A
0x180004c25  cmp     ecx, 3
0x180004c28  jnz     short loc_180004C2D
0x180004c2a  mov     [r15], r12d
0x180004c2d  mov     rcx, gs:60h
0x180004c36  mov     r8, rsi; P
0x180004c39  xor     edx, edx; Flags
0x180004c3b  mov     rcx, [rcx+30h]; HeapHandle
0x180004c3f  call    cs:__imp_RtlFreeHeap
0x180004c45  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180004c49  test    rcx, rcx
0x180004c4c  jz      short loc_180004C54
0x180004c4e  call    cs:__imp_NtClose
0x180004c54  test    ebx, ebx
0x180004c56  jns     short loc_180004C7A
0x180004c58  mov     r8, [rdi+8]; P
0x180004c5c  test    r8, r8
0x180004c5f  jz      short loc_180004C7A
0x180004c61  mov     rcx, gs:60h
0x180004c6a  xor     edx, edx; Flags
0x180004c6c  mov     rcx, [rcx+30h]; HeapHandle
0x180004c70  call    cs:__imp_RtlFreeHeap
0x180004c76  mov     [rdi+8], r12
0x180004c7a  mov     eax, ebx
0x180004c7c  mov     rcx, [rbp+57h+var_38]
0x180004c80  xor     rcx, rsp; StackCookie
0x180004c83  call    __security_check_cookie
0x180004c88  add     rsp, 0C0h
0x180004c8f  pop     r15
0x180004c91  pop     r14
0x180004c93  pop     r12
0x180004c95  pop     rdi
0x180004c96  pop     rsi
0x180004c97  pop     rbx
0x180004c98  pop     rbp
0x180004c99  retn
```
