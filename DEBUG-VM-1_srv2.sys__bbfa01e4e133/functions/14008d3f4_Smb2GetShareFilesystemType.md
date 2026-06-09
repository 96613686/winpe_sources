# Smb2GetShareFilesystemType

- ea: `0x14008d3f4`
- end: `0x14008d638`
- name: `Smb2GetShareFilesystemType`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140081d90`

## callees

- `0x140022958`
- `0x140028ab8`
- `0x140038490`
- `0x14008d3f4`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x14008d48e`
- `ntoskrnl!ZwCreateEvent` at `0x14008d48e`
- `ntoskrnl!NtFsControlFile` at `0x14008d4e5`
- `ntoskrnl!NtFsControlFile` at `0x14008d4e5`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14008d5b3`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14008d5b3`
- `ntoskrnl!NtClose` at `0x14008d502`
- `ntoskrnl!NtClose` at `0x14008d502`

## pseudocode

```c
__int64 __fastcall Smb2GetShareFilesystemType(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 result; // rax
  unsigned int Status; // ebx
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  void *EventHandle; // [rsp+50h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-51h] BYREF
  _WORD OutputBuffer[32]; // [rsp+A0h] [rbp-19h] BYREF

  result = 0;
  EventHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  if ( !a1 || !a2 || !a3 )
    return 3221225485LL;
  *a3 = 0;
  if ( !*(_DWORD *)(a1 + 284) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
    if ( (Status & 0x80000000) == 0 )
    {
      Status = NtFsControlFile(
                 *(HANDLE *)(a2 + 88),
                 EventHandle,
                 0,
                 0,
                 &IoStatusBlock,
                 0x90060u,
                 0,
                 0,
                 OutputBuffer,
                 0x40u);
      if ( Status == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        Status = IoStatusBlock.Status;
      }
      NtClose(EventHandle);
      EventHandle = 0;
      if ( (int)(Status + 0x80000000) < 0 || Status == -2147483643 )
      {
        v10 = OutputBuffer[0];
        Status = 0;
      }
      else
      {
        if ( Status != -1073741808 && Status != -1073741811 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            return Status;
          }
          v12 = 17;
LABEL_29:
          WPP_SF_qD(v11->AttachedDevice, v12, &WPP_4e8015138ece3414973dc97451d118ee_Traceguids, a1, Status);
          return Status;
        }
        Status = 0;
        v10 = 0;
      }
      *a3 = v10;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DqZd(WPP_GLOBAL_Control->AttachedDevice, v8, v9, v10, a1, a1 + 120);
      }
      return Status;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return Status;
    }
    v12 = 16;
    goto LABEL_29;
  }
  return result;
}

```

## disassembly

```asm
0x14008d3f4  push    rbp
0x14008d3f6  push    rbx
0x14008d3f7  push    rsi
0x14008d3f8  push    rdi
0x14008d3f9  push    r14
0x14008d3fb  lea     rbp, [rsp-37h]
0x14008d400  sub     rsp, 0F0h
0x14008d407  mov     rax, cs:__security_cookie
0x14008d40e  xor     rax, rsp
0x14008d411  mov     [rbp+57h+var_30], rax
0x14008d415  xor     eax, eax
0x14008d417  mov     [rbp+57h+EventHandle], 0
0x14008d41f  mov     dword ptr [rbp+57h+ObjectAttributes+4], eax
0x14008d422  xorps   xmm0, xmm0
0x14008d425  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], eax
0x14008d428  mov     rsi, r8
0x14008d42b  mov     r14, rdx
0x14008d42e  mov     rdi, rcx
0x14008d431  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14008d435  test    rcx, rcx
0x14008d438  jz      loc_14008D62E
0x14008d43e  test    rdx, rdx
0x14008d441  jz      loc_14008D62E
0x14008d447  test    r8, r8
0x14008d44a  jz      loc_14008D62E
0x14008d450  mov     [r8], eax
0x14008d453  cmp     [rcx+11Ch], eax
0x14008d459  jnz     loc_14008D545
0x14008d45f  xor     r9d, r9d; EventType
0x14008d462  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14008d469  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14008d46d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14008d471  mov     edx, 1F0003h; DesiredAccess
0x14008d476  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14008d47d  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x14008d481  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14008d485  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008d48a  mov     [rsp+110h+InitialState], al; InitialState
0x14008d48e  call    cs:__imp_ZwCreateEvent
0x14008d495  nop     dword ptr [rax+rax+00h]
0x14008d49a  mov     ebx, eax
0x14008d49c  test    eax, eax
0x14008d49e  js      loc_14008D5F8
0x14008d4a4  mov     rdx, [rbp+57h+EventHandle]; Event
0x14008d4a8  lea     rax, [rbp+57h+var_70]
0x14008d4ac  mov     rcx, [r14+58h]; FileHandle
0x14008d4b0  xor     r9d, r9d; ApcContext
0x14008d4b3  mov     [rsp+110h+OutputBufferLength], 40h ; '@'; OutputBufferLength
0x14008d4bb  xor     r8d, r8d; ApcRoutine
0x14008d4be  mov     [rsp+110h+OutputBuffer], rax; OutputBuffer
0x14008d4c3  lea     rax, [rbp+57h+IoStatusBlock]
0x14008d4c7  mov     [rsp+110h+InputBufferLength], 0; InputBufferLength
0x14008d4cf  mov     [rsp+110h+InputBuffer], 0; InputBuffer
0x14008d4d8  mov     [rsp+110h+FsControlCode], 90060h; FsControlCode
0x14008d4e0  mov     qword ptr [rsp+110h+InitialState], rax; IoStatusBlock
0x14008d4e5  call    cs:__imp_NtFsControlFile
0x14008d4ec  nop     dword ptr [rax+rax+00h]
0x14008d4f1  mov     ebx, eax
0x14008d4f3  cmp     eax, 103h
0x14008d4f8  jz      loc_14008D5AA
0x14008d4fe  mov     rcx, [rbp+57h+EventHandle]; Handle
0x14008d502  call    cs:__imp_NtClose
0x14008d509  nop     dword ptr [rax+rax+00h]
0x14008d50e  mov     ecx, 80000000h
0x14008d513  mov     [rbp+57h+EventHandle], 0
0x14008d51b  lea     eax, [rbx+rcx]
0x14008d51e  test    ecx, eax
0x14008d520  jz      short loc_14008D560
0x14008d522  movzx   r9d, [rbp+57h+var_70]
0x14008d527  xor     ebx, ebx
0x14008d529  mov     [rsi], r9d
0x14008d52c  lea     rax, WPP_GLOBAL_Control
0x14008d533  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d53a  cmp     rcx, rax
0x14008d53d  jnz     loc_14008D5C7
0x14008d543  mov     eax, ebx
0x14008d545  mov     rcx, [rbp+57h+var_30]
0x14008d549  xor     rcx, rsp; StackCookie
0x14008d54c  call    __security_check_cookie
0x14008d551  add     rsp, 0F0h
0x14008d558  pop     r14
0x14008d55a  pop     rdi
0x14008d55b  pop     rsi
0x14008d55c  pop     rbx
0x14008d55d  pop     rbp
0x14008d55e  retn
0x14008d560  cmp     ebx, 80000005h
0x14008d566  jz      short loc_14008D522
0x14008d568  cmp     ebx, 0C0000010h
0x14008d56e  jz      loc_14009B926
0x14008d574  cmp     ebx, 0C000000Dh
0x14008d57a  jz      loc_14009B926
0x14008d580  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d587  lea     rax, WPP_GLOBAL_Control
0x14008d58e  cmp     rcx, rax
0x14008d591  jz      short loc_14008D543
0x14008d593  mov     eax, [rcx+2Ch]
0x14008d596  test    al, 1
0x14008d598  jz      short loc_14008D543
0x14008d59a  cmp     byte ptr [rcx+29h], 1
0x14008d59e  jb      short loc_14008D543
0x14008d5a0  mov     edx, 11h
0x14008d5a5  jmp     loc_14009B930
0x14008d5aa  mov     rcx, [rbp+57h+EventHandle]; Handle
0x14008d5ae  xor     r8d, r8d; Timeout
0x14008d5b1  xor     edx, edx; Alertable
0x14008d5b3  call    cs:__imp_ZwWaitForSingleObject
0x14008d5ba  nop     dword ptr [rax+rax+00h]
0x14008d5bf  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x14008d5c2  jmp     loc_14008D4FE
0x14008d5c7  mov     eax, [rcx+2Ch]
0x14008d5ca  test    al, 1
0x14008d5cc  jz      loc_14008D543
0x14008d5d2  cmp     byte ptr [rcx+29h], 2
0x14008d5d6  jb      loc_14008D543
0x14008d5dc  mov     rcx, [rcx+18h]
0x14008d5e0  lea     rax, [rdi+78h]
0x14008d5e4  mov     qword ptr [rsp+110h+FsControlCode], rax
0x14008d5e9  mov     qword ptr [rsp+110h+InitialState], rdi
0x14008d5ee  call    WPP_SF_DqZd
0x14008d5f3  jmp     loc_14008D543
0x14008d5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d5ff  lea     rax, WPP_GLOBAL_Control
0x14008d606  cmp     rcx, rax
0x14008d609  jz      loc_14008D543
0x14008d60f  mov     eax, [rcx+2Ch]
0x14008d612  test    al, 1
0x14008d614  jz      loc_14008D543
0x14008d61a  cmp     byte ptr [rcx+29h], 1
0x14008d61e  jb      loc_14008D543
0x14008d624  mov     edx, 10h
0x14008d629  jmp     loc_14009B930
0x14008d62e  mov     eax, 0C000000Dh
0x14008d633  jmp     loc_14008D545
0x14009b926  xor     ebx, ebx
0x14009b928  xor     r9d, r9d
0x14009b92b  jmp     loc_14008D529
0x14009b930  mov     rcx, [rcx+18h]
0x14009b934  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x14009b93b  mov     r9, rdi
0x14009b93e  mov     dword ptr [rsp+110h+InitialState], ebx
0x14009b942  call    WPP_SF_qD
0x14009b947  nop
0x14009b948  jmp     loc_14008D543
```
