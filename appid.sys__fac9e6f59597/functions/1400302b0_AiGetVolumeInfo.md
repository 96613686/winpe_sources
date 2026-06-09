# AiGetVolumeInfo

- ea: `0x1400302b0`
- end: `0x14003060e`
- name: `AiGetVolumeInfo`
- size: `862`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, struct _UNICODE_STRING *, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002fe20`
- `0x1400333b0`

## callees

- `0x140001970`
- `0x140006a20`
- `0x140006c40`
- `0x1400302b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x1400303e9`
- `ntoskrnl!ZwOpenFile` at `0x1400303e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400305af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400305df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400305af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400305df`
- `ntoskrnl!ExAllocatePool2` at `0x140030356`
- `ntoskrnl!ExAllocatePool2` at `0x140030356`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140030318`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140030318`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140030479`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140030503`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140030579`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140030479`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140030503`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140030579`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x140030394`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x140030394`
- `ntoskrnl!ZwClose` at `0x1400305c4`
- `ntoskrnl!ZwClose` at `0x1400305c4`

## pseudocode

```c
__int64 __fastcall AiGetVolumeInfo(struct _UNICODE_STRING *a1, void *a2, struct _UNICODE_STRING *a3, _DWORD *a4)
{
  __int64 v8; // rdx
  WCHAR *Pool2; // rax
  NTSTATUS v10; // ebx
  void *v11; // rcx
  NTSTATUS v12; // eax
  void *v13; // rcx
  ULONG v14; // eax
  _DWORD *v15; // rax
  _DWORD *v16; // rsi
  PWSTR Buffer; // rcx
  void *FileHandle; // [rsp+50h] [rbp-49h] BYREF
  ULONG OutputBufferLength[2]; // [rsp+58h] [rbp-41h] BYREF
  __int64 OutputBuffer; // [rsp+60h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  __int64 InputBuffer; // [rsp+A8h] [rbp+Fh] BYREF
  int v25; // [rsp+B0h] [rbp+17h]

  a3->Buffer = 0;
  FileHandle = 0;
  OutputBuffer = 0;
  InputBuffer = 0;
  v25 = 0;
  *(_QWORD *)OutputBufferLength = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( RtlEqualUnicodeString(a1, &String2, 1u) )
  {
    *(_QWORD *)&a3->Length = xmmword_140019588;
    v8 = WORD1(xmmword_140019588);
    a3->Buffer = (PWSTR)*((_QWORD *)&xmmword_140019588 + 1);
    Pool2 = (WCHAR *)ExAllocatePool2(258, v8, 1145663553);
    a3->Buffer = Pool2;
    if ( Pool2 )
    {
      v10 = 0;
      memmove(Pool2, *((const void **)&xmmword_140019588 + 1), a3->MaximumLength);
      *a4 = 0;
      goto LABEL_27;
    }
    goto LABEL_18;
  }
  v10 = IoVolumeDeviceToDosName(a2, a3);
  if ( v10 < 0 )
    goto LABEL_27;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = ZwOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v10 >= 0 )
  {
    v11 = FileHandle;
    *a4 = 0;
    v12 = ZwDeviceIoControlFile(v11, 0, 0, 0, &IoStatusBlock, 0x2D0C14u, 0, 0, &OutputBuffer, 8u);
    v10 = v12;
    if ( v12 < 0 )
      goto LABEL_11;
    if ( !*(_WORD *)((char *)&OutputBuffer + 5) )
      goto LABEL_27;
    v13 = FileHandle;
    *a4 = 1;
    InputBuffer = 0;
    v12 = ZwDeviceIoControlFile(v13, 0, 0, 0, &IoStatusBlock, 0x2D1400u, &InputBuffer, 0xCu, OutputBufferLength, 8u);
    v10 = v12;
    if ( v12 < 0 )
    {
LABEL_11:
      if ( v12 != -1073741801 && v12 != -1073741670 )
        v10 = 0;
    }
    else
    {
      v14 = OutputBufferLength[1];
      if ( OutputBufferLength[1] < 0x28 )
        v14 = 40;
      OutputBufferLength[1] = v14;
      v15 = (_DWORD *)AiAlloc(v14);
      v16 = v15;
      if ( !v15 )
      {
LABEL_18:
        v10 = -1073741801;
        goto LABEL_27;
      }
      v10 = ZwDeviceIoControlFile(
              FileHandle,
              0,
              0,
              0,
              &IoStatusBlock,
              0x2D1400u,
              &InputBuffer,
              0xCu,
              v15,
              OutputBufferLength[1]);
      if ( v10 >= 0 && (v16[7] == 1 || v16[7] == 3 || v16[7] == 6 || v16[7] == 8 || v16[7] == 11) )
        *a4 = 0;
      ExFreePoolWithTag(v16, 0);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_ZD(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_4affb847aa64312eeff433e6518e017d_Traceguids,
      (_DWORD)a1,
      v10);
  }
LABEL_27:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v10 < 0 )
  {
    Buffer = a3->Buffer;
    if ( Buffer )
    {
      ExFreePoolWithTag(Buffer, 0);
      a3->Buffer = 0;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400302b0  push    rbp
0x1400302b2  push    rbx
0x1400302b3  push    rsi
0x1400302b4  push    rdi
0x1400302b5  push    r14
0x1400302b7  push    r15
0x1400302b9  lea     rbp, [rsp-2Fh]
0x1400302be  sub     rsp, 0C8h
0x1400302c5  mov     rax, cs:__security_cookie
0x1400302cc  xor     rax, rsp
0x1400302cf  mov     [rbp+57h+var_38], rax
0x1400302d3  xorps   xmm0, xmm0
0x1400302d6  xor     r15d, r15d
0x1400302d9  xor     eax, eax
0x1400302db  mov     [r8+8], r15
0x1400302df  mov     rdi, r8
0x1400302e2  mov     [rbp+57h+FileHandle], r15
0x1400302e6  mov     rbx, rdx
0x1400302e9  mov     [rbp+57h+var_90], r15
0x1400302ed  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400302f1  mov     r8b, 1; CaseInSensitive
0x1400302f4  mov     [rbp+57h+var_48], rax
0x1400302f8  lea     rdx, String2; String2
0x1400302ff  mov     [rbp+57h+var_40], eax
0x140030302  mov     r14, r9
0x140030305  mov     qword ptr [rbp+57h+var_98], r15
0x140030309  mov     rsi, rcx
0x14003030c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140030310  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140030314  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140030318  call    cs:__imp_RtlEqualUnicodeString
0x14003031f  nop     dword ptr [rax+rax+00h]
0x140030324  test    al, al
0x140030326  jz      short loc_14003038E
0x140030328  mov     rax, qword ptr cs:xmmword_140019588
0x14003032f  mov     ecx, 102h
0x140030334  mov     [rdi], rax
0x140030337  mov     r8d, 44497041h
0x14003033d  mov     rax, qword ptr cs:xmmword_140019588
0x140030344  shr     rax, 10h
0x140030348  movzx   edx, ax
0x14003034b  mov     rax, qword ptr cs:xmmword_140019588+8
0x140030352  mov     [rdi+8], rax
0x140030356  call    cs:__imp_ExAllocatePool2
0x14003035d  nop     dword ptr [rax+rax+00h]
0x140030362  mov     [rdi+8], rax
0x140030366  test    rax, rax
0x140030369  jz      loc_140030538
0x14003036f  movzx   r8d, word ptr [rdi+2]; Size
0x140030374  mov     rcx, rax; void *
0x140030377  mov     rdx, qword ptr cs:xmmword_140019588+8; Src
0x14003037e  mov     ebx, r15d
0x140030381  call    memmove
0x140030386  mov     [r14], r15d
0x140030389  jmp     loc_1400305BB
0x14003038e  mov     rdx, rdi; DosName
0x140030391  mov     rcx, rbx; VolumeDeviceObject
0x140030394  call    cs:__imp_IoVolumeDeviceToDosName
0x14003039b  nop     dword ptr [rax+rax+00h]
0x1400303a0  mov     ebx, eax
0x1400303a2  test    eax, eax
0x1400303a4  js      loc_1400305BB
0x1400303aa  xorps   xmm0, xmm0
0x1400303ad  mov     [rsp+0F0h+OpenOptions], 20h ; ' '; OpenOptions
0x1400303b5  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400303b9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400303c0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400303c4  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1400303c8  mov     edx, 100000h; DesiredAccess
0x1400303cd  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400303d4  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400303d8  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x1400303dc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400303e1  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1400303e9  call    cs:__imp_ZwOpenFile
0x1400303f0  nop     dword ptr [rax+rax+00h]
0x1400303f5  mov     ebx, eax
0x1400303f7  test    eax, eax
0x1400303f9  jns     short loc_14003043E
0x1400303fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140030402  lea     rax, WPP_GLOBAL_Control
0x140030409  cmp     rcx, rax
0x14003040c  jz      loc_1400305BB
0x140030412  mov     eax, [rcx+2Ch]
0x140030415  test    al, 10h
0x140030417  jz      loc_1400305BB
0x14003041d  mov     rcx, [rcx+18h]
0x140030421  lea     r8, WPP_4affb847aa64312eeff433e6518e017d_Traceguids
0x140030428  mov     edx, 0Bh
0x14003042d  mov     [rsp+0F0h+ShareAccess], ebx
0x140030431  mov     r9, rsi
0x140030434  call    WPP_SF_ZD
0x140030439  jmp     loc_1400305BB
0x14003043e  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140030442  lea     rax, [rbp+57h+var_90]
0x140030446  mov     [rsp+0F0h+OutputBufferLength], 8; OutputBufferLength
0x14003044e  xor     r9d, r9d; ApcContext
0x140030451  mov     [rsp+0F0h+OutputBuffer], rax; OutputBuffer
0x140030456  xor     r8d, r8d; ApcRoutine
0x140030459  mov     [rsp+0F0h+InputBufferLength], r15d; InputBufferLength
0x14003045e  lea     rax, [rbp+57h+IoStatusBlock]
0x140030462  mov     [rsp+0F0h+InputBuffer], r15; InputBuffer
0x140030467  xor     edx, edx; Event
0x140030469  mov     [rsp+0F0h+OpenOptions], 2D0C14h; IoControlCode
0x140030471  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x140030476  mov     [r14], r15d
0x140030479  call    cs:__imp_ZwDeviceIoControlFile
0x140030480  nop     dword ptr [rax+rax+00h]
0x140030485  mov     ebx, eax
0x140030487  test    eax, eax
0x140030489  jns     short loc_1400304A9
0x14003048b  cmp     eax, 0C0000017h
0x140030490  jz      loc_1400305BB
0x140030496  cmp     eax, 0C000009Ah
0x14003049b  jz      loc_1400305BB
0x1400304a1  mov     ebx, r15d
0x1400304a4  jmp     loc_1400305BB
0x1400304a9  cmp     byte ptr [rbp+57h+var_90+5], r15b
0x1400304ad  jnz     short loc_1400304B9
0x1400304af  cmp     byte ptr [rbp+57h+var_90+6], r15b
0x1400304b3  jz      loc_1400305BB
0x1400304b9  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400304bd  lea     rax, [rbp+57h+var_98]
0x1400304c1  mov     [rsp+0F0h+OutputBufferLength], 8; OutputBufferLength
0x1400304c9  xor     r9d, r9d; ApcContext
0x1400304cc  mov     [rsp+0F0h+OutputBuffer], rax; OutputBuffer
0x1400304d1  xor     r8d, r8d; ApcRoutine
0x1400304d4  mov     [rsp+0F0h+InputBufferLength], 0Ch; InputBufferLength
0x1400304dc  lea     rax, [rbp+57h+var_48]
0x1400304e0  mov     [rsp+0F0h+InputBuffer], rax; InputBuffer
0x1400304e5  xor     edx, edx; Event
0x1400304e7  lea     rax, [rbp+57h+IoStatusBlock]
0x1400304eb  mov     [rsp+0F0h+OpenOptions], 2D1400h; IoControlCode
0x1400304f3  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x1400304f8  mov     dword ptr [r14], 1
0x1400304ff  mov     [rbp+57h+var_48], r15
0x140030503  call    cs:__imp_ZwDeviceIoControlFile
0x14003050a  nop     dword ptr [rax+rax+00h]
0x14003050f  mov     ebx, eax
0x140030511  test    eax, eax
0x140030513  js      loc_14003048B
0x140030519  mov     eax, [rbp+57h+var_98+4]
0x14003051c  mov     ecx, 28h ; '('
0x140030521  cmp     eax, ecx
0x140030523  cmovb   eax, ecx
0x140030526  mov     ecx, eax
0x140030528  mov     [rbp+57h+var_98+4], eax
0x14003052b  call    AiAlloc
0x140030530  mov     rsi, rax
0x140030533  test    rax, rax
0x140030536  jnz     short loc_14003053F
0x140030538  mov     ebx, 0C0000017h
0x14003053d  jmp     short loc_1400305BB
0x14003053f  mov     eax, [rbp+57h+var_98+4]
0x140030542  xor     r9d, r9d; ApcContext
0x140030545  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140030549  xor     r8d, r8d; ApcRoutine
0x14003054c  mov     [rsp+0F0h+OutputBufferLength], eax; OutputBufferLength
0x140030550  xor     edx, edx; Event
0x140030552  mov     [rsp+0F0h+OutputBuffer], rsi; OutputBuffer
0x140030557  lea     rax, [rbp+57h+var_48]
0x14003055b  mov     [rsp+0F0h+InputBufferLength], 0Ch; InputBufferLength
0x140030563  mov     [rsp+0F0h+InputBuffer], rax; InputBuffer
0x140030568  lea     rax, [rbp+57h+IoStatusBlock]
0x14003056c  mov     [rsp+0F0h+OpenOptions], 2D1400h; IoControlCode
0x140030574  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x140030579  call    cs:__imp_ZwDeviceIoControlFile
0x140030580  nop     dword ptr [rax+rax+00h]
0x140030585  mov     ebx, eax
0x140030587  test    eax, eax
0x140030589  js      short loc_1400305AA
0x14003058b  mov     ecx, [rsi+1Ch]
0x14003058e  sub     ecx, 1
0x140030591  jz      short loc_1400305A7
0x140030593  sub     ecx, 2
0x140030596  jz      short loc_1400305A7
0x140030598  sub     ecx, 3
0x14003059b  jz      short loc_1400305A7
0x14003059d  sub     ecx, 2
0x1400305a0  jz      short loc_1400305A7
0x1400305a2  cmp     ecx, 3
0x1400305a5  jnz     short loc_1400305AA
0x1400305a7  mov     [r14], r15d
0x1400305aa  xor     edx, edx; Tag
0x1400305ac  mov     rcx, rsi; P
0x1400305af  call    cs:__imp_ExFreePoolWithTag
0x1400305b6  nop     dword ptr [rax+rax+00h]
0x1400305bb  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400305bf  test    rcx, rcx
0x1400305c2  jz      short loc_1400305D0
0x1400305c4  call    cs:__imp_ZwClose
0x1400305cb  nop     dword ptr [rax+rax+00h]
0x1400305d0  test    ebx, ebx
0x1400305d2  jns     short loc_1400305EF
0x1400305d4  mov     rcx, [rdi+8]; P
0x1400305d8  test    rcx, rcx
0x1400305db  jz      short loc_1400305EF
0x1400305dd  xor     edx, edx; Tag
0x1400305df  call    cs:__imp_ExFreePoolWithTag
0x1400305e6  nop     dword ptr [rax+rax+00h]
0x1400305eb  mov     [rdi+8], r15
0x1400305ef  mov     eax, ebx
0x1400305f1  mov     rcx, [rbp+57h+var_38]
0x1400305f5  xor     rcx, rsp; StackCookie
0x1400305f8  call    __security_check_cookie
0x1400305fd  add     rsp, 0C8h
0x140030604  pop     r15
0x140030606  pop     r14
0x140030608  pop     rdi
0x140030609  pop     rsi
0x14003060a  pop     rbx
0x14003060b  pop     rbp
0x14003060c  retn
```
