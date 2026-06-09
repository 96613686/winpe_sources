# AipGetImageId

- ea: `0x140032a90`
- end: `0x140032d20`
- name: `AipGetImageId`
- size: `656`
- prototype: `__int64 __fastcall(HANDLE FileHandle, PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002ff50`

## callees

- `0x140001970`
- `0x140006a20`
- `0x140032a90`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x140032b89`
- `ntoskrnl!ZwOpenFile` at `0x140032b89`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032b1b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032b1b`
- `ntoskrnl!ZwFsControlFile` at `0x140032c18`
- `ntoskrnl!ZwFsControlFile` at `0x140032ca5`
- `ntoskrnl!ZwFsControlFile` at `0x140032c18`
- `ntoskrnl!ZwFsControlFile` at `0x140032ca5`
- `ntoskrnl!ZwClose` at `0x140032cf8`
- `ntoskrnl!ZwClose` at `0x140032cf8`

## pseudocode

```c
__int64 __fastcall AipGetImageId(HANDLE FileHandle, UNICODE_STRING *String1, _QWORD *a3)
{
  int v6; // esi
  NTSTATUS v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  int v9; // edx
  __int64 v10; // rax
  __int64 InputBuffer; // [rsp+58h] [rbp-B0h] BYREF
  void *FileHandlea; // [rsp+60h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK FileHandle_8; // [rsp+68h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes_8; // [rsp+78h] [rbp-90h] BYREF
  _OWORD OutputBuffer[4]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v17[8]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v18; // [rsp+F0h] [rbp-18h]
  __int64 v19; // [rsp+100h] [rbp-8h]

  FileHandlea = 0;
  LODWORD(InputBuffer) = 131074;
  v6 = 0;
  memset(&ObjectAttributes_8, 0, 44);
  FileHandle_8 = 0;
  memset(OutputBuffer, 0, sizeof(OutputBuffer));
  if ( !RtlEqualUnicodeString(String1, &String2, 1u) || (v6 = 1, !qword_1400195A8) )
  {
    ObjectAttributes_8.Length = 48;
    ObjectAttributes_8.RootDirectory = 0;
    ObjectAttributes_8.Attributes = 576;
    ObjectAttributes_8.ObjectName = String1;
    *(_OWORD *)&ObjectAttributes_8.SecurityDescriptor = 0;
    v7 = ZwOpenFile(&FileHandlea, 0x80100000, &ObjectAttributes_8, &FileHandle_8, 7u, 0x20u);
    if ( v7 >= 0 )
    {
      v7 = ZwFsControlFile(FileHandlea, 0, 0, 0, &FileHandle_8, 0x900F4u, 0, 0, OutputBuffer, 0x40u);
      if ( v7 >= 0 )
      {
        v10 = *(_QWORD *)&OutputBuffer[0];
        a3[2] = *(_QWORD *)&OutputBuffer[0];
        if ( v6 )
          qword_1400195A8 = v10;
        goto LABEL_15;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
        goto LABEL_17;
      v9 = 13;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
        goto LABEL_17;
      v9 = 12;
    }
    WPP_SF_ZD(
      v8->AttachedDevice,
      v9,
      (unsigned int)WPP_4affb847aa64312eeff433e6518e017d_Traceguids,
      (_DWORD)String1,
      v7);
    goto LABEL_17;
  }
  a3[2] = qword_1400195A8;
LABEL_15:
  v7 = ZwFsControlFile(FileHandle, 0, 0, 0, &FileHandle_8, 0x900EBu, &InputBuffer, 4u, v17, 0x252u);
  if ( v7 >= 0 )
  {
    a3[1] = v19;
    *a3 = v18;
  }
LABEL_17:
  if ( FileHandlea )
    ZwClose(FileHandlea);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140032a90  mov     r11, rsp
0x140032a93  push    rbp
0x140032a94  push    rbx
0x140032a95  lea     rbp, [r11-278h]
0x140032a9c  sub     rsp, 368h
0x140032aa3  mov     rax, cs:__security_cookie
0x140032aaa  xor     rax, rsp
0x140032aad  mov     [rbp+270h+var_38], rax
0x140032ab4  mov     [r11-18h], rsi
0x140032ab8  xorps   xmm0, xmm0
0x140032abb  mov     [r11-20h], rdi
0x140032abf  xorps   xmm1, xmm1
0x140032ac2  mov     [r11-28h], r12
0x140032ac6  mov     rdi, r8
0x140032ac9  mov     [r11-30h], r14
0x140032acd  xor     r12d, r12d
0x140032ad0  mov     [r11-38h], r15
0x140032ad4  mov     r14, rcx
0x140032ad7  mov     r15, rdx
0x140032ada  mov     [rsp+370h+FileHandle], r12
0x140032adf  movups  xmmword ptr [rbp+270h+ObjectAttributes+18h], xmm0
0x140032ae3  mov     rcx, r15; String1
0x140032ae6  mov     dword ptr [rsp+370h+var_320], 20002h
0x140032aee  xor     eax, eax
0x140032af0  lea     rdx, String2; String2
0x140032af7  mov     r8b, 1; CaseInSensitive
0x140032afa  mov     esi, r12d
0x140032afd  movups  xmmword ptr [rsp+370h+ObjectAttributes+8], xmm0
0x140032b02  movups  xmmword ptr [rbp+270h+ObjectAttributes+24h], xmm0
0x140032b06  movups  xmmword ptr [rsp+370h+FileHandle+8], xmm0
0x140032b0b  movups  [rbp+270h+var_2D0], xmm1
0x140032b0f  movups  [rbp+270h+var_2C0], xmm1
0x140032b13  movups  [rbp+270h+var_2B0], xmm1
0x140032b17  movups  [rbp+270h+var_2A0], xmm1
0x140032b1b  call    cs:__imp_RtlEqualUnicodeString
0x140032b22  nop     dword ptr [rax+rax+00h]
0x140032b27  test    al, al
0x140032b29  jz      short loc_140032B45
0x140032b2b  mov     rax, cs:qword_1400195A8
0x140032b32  mov     esi, 1
0x140032b37  test    rax, rax
0x140032b3a  jz      short loc_140032B45
0x140032b3c  mov     [rdi+10h], rax
0x140032b40  jmp     loc_140032C65
0x140032b45  xorps   xmm0, xmm0
0x140032b48  mov     [rsp+370h+OpenOptions], 20h ; ' '; OpenOptions
0x140032b50  lea     r9, [rsp+370h+FileHandle+8]; IoStatusBlock
0x140032b55  mov     dword ptr [rsp+370h+ObjectAttributes+8], 30h ; '0'
0x140032b5d  lea     r8, [rsp+370h+ObjectAttributes+8]; ObjectAttributes
0x140032b62  mov     qword ptr [rsp+370h+ObjectAttributes+10h], r12
0x140032b67  mov     edx, 80100000h; DesiredAccess
0x140032b6c  mov     dword ptr [rbp+270h+ObjectAttributes+20h], 240h
0x140032b73  lea     rcx, [rsp+370h+FileHandle]; FileHandle
0x140032b78  mov     qword ptr [rbp+270h+ObjectAttributes+18h], r15
0x140032b7c  movdqu  xmmword ptr [rbp+270h+ObjectAttributes+28h], xmm0
0x140032b81  mov     [rsp+370h+ShareAccess], 7; ShareAccess
0x140032b89  call    cs:__imp_ZwOpenFile
0x140032b90  nop     dword ptr [rax+rax+00h]
0x140032b95  mov     ebx, eax
0x140032b97  test    eax, eax
0x140032b99  jns     short loc_140032BDE
0x140032b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ba2  lea     rax, WPP_GLOBAL_Control
0x140032ba9  cmp     rcx, rax
0x140032bac  jz      loc_140032CC6
0x140032bb2  mov     eax, [rcx+2Ch]
0x140032bb5  test    al, 10h
0x140032bb7  jz      loc_140032CC6
0x140032bbd  mov     edx, 0Ch
0x140032bc2  mov     rcx, [rcx+18h]
0x140032bc6  lea     r8, WPP_4affb847aa64312eeff433e6518e017d_Traceguids
0x140032bcd  mov     r9, r15
0x140032bd0  mov     [rsp+370h+ShareAccess], ebx
0x140032bd4  call    WPP_SF_ZD
0x140032bd9  jmp     loc_140032CC6
0x140032bde  mov     rcx, [rsp+370h+FileHandle]; FileHandle
0x140032be3  lea     rax, [rbp+270h+var_2D0]
0x140032be7  mov     [rsp+370h+OutputBufferLength], 40h ; '@'; OutputBufferLength
0x140032bef  xor     r9d, r9d; ApcContext
0x140032bf2  mov     [rsp+370h+OutputBuffer], rax; OutputBuffer
0x140032bf7  xor     r8d, r8d; ApcRoutine
0x140032bfa  mov     [rsp+370h+InputBufferLength], r12d; InputBufferLength
0x140032bff  lea     rax, [rsp+370h+FileHandle+8]
0x140032c04  mov     [rsp+370h+InputBuffer], r12; InputBuffer
0x140032c09  xor     edx, edx; Event
0x140032c0b  mov     [rsp+370h+OpenOptions], 900F4h; FsControlCode
0x140032c13  mov     qword ptr [rsp+370h+ShareAccess], rax; IoStatusBlock
0x140032c18  call    cs:__imp_ZwFsControlFile
0x140032c1f  nop     dword ptr [rax+rax+00h]
0x140032c24  mov     ebx, eax
0x140032c26  test    eax, eax
0x140032c28  jns     short loc_140032C52
0x140032c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032c31  lea     rax, WPP_GLOBAL_Control
0x140032c38  cmp     rcx, rax
0x140032c3b  jz      loc_140032CC6
0x140032c41  mov     eax, [rcx+2Ch]
0x140032c44  test    al, 10h
0x140032c46  jz      short loc_140032CC6
0x140032c48  mov     edx, 0Dh
0x140032c4d  jmp     loc_140032BC2
0x140032c52  mov     rax, qword ptr [rbp+270h+var_2D0]
0x140032c56  mov     [rdi+10h], rax
0x140032c5a  test    esi, esi
0x140032c5c  jz      short loc_140032C65
0x140032c5e  mov     cs:qword_1400195A8, rax
0x140032c65  mov     [rsp+370h+OutputBufferLength], 252h; OutputBufferLength
0x140032c6d  lea     rax, [rbp+270h+var_290]
0x140032c71  mov     [rsp+370h+OutputBuffer], rax; OutputBuffer
0x140032c76  xor     r9d, r9d; ApcContext
0x140032c79  mov     [rsp+370h+InputBufferLength], 4; InputBufferLength
0x140032c81  lea     rax, [rsp+370h+var_320]
0x140032c86  mov     [rsp+370h+InputBuffer], rax; InputBuffer
0x140032c8b  xor     r8d, r8d; ApcRoutine
0x140032c8e  lea     rax, [rsp+370h+FileHandle+8]
0x140032c93  mov     [rsp+370h+OpenOptions], 900EBh; FsControlCode
0x140032c9b  xor     edx, edx; Event
0x140032c9d  mov     qword ptr [rsp+370h+ShareAccess], rax; IoStatusBlock
0x140032ca2  mov     rcx, r14; FileHandle
0x140032ca5  call    cs:__imp_ZwFsControlFile
0x140032cac  nop     dword ptr [rax+rax+00h]
0x140032cb1  mov     ebx, eax
0x140032cb3  test    eax, eax
0x140032cb5  js      short loc_140032CC6
0x140032cb7  mov     rax, [rbp+270h+var_278]
0x140032cbb  mov     [rdi+8], rax
0x140032cbf  mov     rax, [rbp+270h+var_288]
0x140032cc3  mov     [rdi], rax
0x140032cc6  mov     rcx, [rsp+370h+FileHandle]; Handle
0x140032ccb  mov     r15, [rsp+370h+var_30]
0x140032cd3  mov     r14, [rsp+370h+var_28]
0x140032cdb  mov     r12, [rsp+370h+var_20]
0x140032ce3  mov     rdi, [rsp+370h+var_18]
0x140032ceb  mov     rsi, [rsp+360h]
0x140032cf3  test    rcx, rcx
0x140032cf6  jz      short loc_140032D04
0x140032cf8  call    cs:__imp_ZwClose
0x140032cff  nop     dword ptr [rax+rax+00h]
0x140032d04  mov     eax, ebx
0x140032d06  mov     rcx, [rbp+270h+var_38]
0x140032d0d  xor     rcx, rsp; StackCookie
0x140032d10  call    __security_check_cookie
0x140032d15  add     rsp, 368h
0x140032d1c  pop     rbx
0x140032d1d  pop     rbp
0x140032d1e  retn
```
