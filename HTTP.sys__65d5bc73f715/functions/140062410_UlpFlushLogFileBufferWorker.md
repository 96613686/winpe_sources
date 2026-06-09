# UlpFlushLogFileBufferWorker

- ea: `0x140062410`
- end: `0x140062556`
- name: `UlpFlushLogFileBufferWorker`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140037060`
- `0x140062410`
- `0x140062604`
- `0x14006293c`
- `0x1400b0154`
- `0x1401c4444`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x140177bbc`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140177bbc`
- `ntoskrnl!ZwWriteFile` at `0x1400624c9`
- `ntoskrnl!ZwWriteFile` at `0x140177b9e`
- `ntoskrnl!ZwWriteFile` at `0x1400624c9`
- `ntoskrnl!ZwWriteFile` at `0x140177b9e`
- `ntoskrnl!ZwCreateEvent` at `0x140177b53`
- `ntoskrnl!ZwCreateEvent` at `0x140177b53`
- `ntoskrnl!ZwClose` at `0x140177bd3`
- `ntoskrnl!ZwClose` at `0x140177bd3`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006245f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006245f`

## pseudocode

```c
__int64 __fastcall UlpFlushLogFileBufferWorker(__int64 *a1)
{
  __int64 v1; // rdi
  __int64 v2; // r15
  __int64 Current; // r14
  __int64 CurrentServerSilo; // rax
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+B0h] [rbp+30h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+B8h] [rbp+38h] BYREF

  v1 = a1[1];
  v2 = *a1;
  EventHandle = 0;
  ByteOffset.QuadPart = -1;
  memset(&ObjectAttributes, 0, 44);
  Current = UxPodGetCurrent();
  if ( *((_BYTE *)a1 + 16) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
    if ( v7 >= 0 )
    {
      v7 = ZwWriteFile(
             *(HANDLE *)(v2 + 64),
             EventHandle,
             0,
             0,
             (PIO_STATUS_BLOCK)(v1 + 24),
             *(PVOID *)(v1 + 64),
             *(_DWORD *)(v1 + 56),
             &ByteOffset,
             0);
      if ( v7 == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        v7 = *(_DWORD *)(a1[1] + 24);
      }
      ZwClose(EventHandle);
    }
    UlFreeLogFileBuffer(v1);
  }
  else
  {
    CurrentServerSilo = PsGetCurrentServerSilo();
    *(_QWORD *)(v1 + 48) = CurrentServerSilo;
    UxPodReferenceSilo(CurrentServerSilo, 1280076885, 36);
    *(_BYTE *)(v1 + 40) = 1;
    _InterlockedIncrement((volatile signed __int32 *)(Current + 2976));
    v6 = ZwWriteFile(
           *(HANDLE *)(v2 + 64),
           0,
           UlpBufferFlushAPC,
           (PVOID)v1,
           (PIO_STATUS_BLOCK)(v1 + 24),
           *(PVOID *)(v1 + 64),
           *(_DWORD *)(v1 + 56),
           &ByteOffset,
           0);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( (BYTE9(xmmword_1401A2C90) & 8) != 0 )
        WPP_SF_d(779, 21, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, (unsigned int)v6);
      UlpLogBufferWriteCompletion(v1, Current);
    }
  }
  if ( (BYTE9(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qqdd(1291, 22, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, v2, v1, *((unsigned __int8 *)a1 + 16), v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140062410  mov     [rsp-28h+arg_10], rbx
0x140062415  push    rbp
0x140062416  push    rsi
0x140062417  push    rdi
0x140062418  push    r14
0x14006241a  push    r15
0x14006241c  mov     rbp, rsp
0x14006241f  sub     rsp, 80h
0x140062426  mov     rdi, [rcx+8]
0x14006242a  xorps   xmm0, xmm0
0x14006242d  mov     r15, [rcx]
0x140062430  xor     eax, eax
0x140062432  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140062436  mov     rsi, rcx
0x140062439  mov     [rbp+EventHandle], rax
0x14006243d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140062441  mov     qword ptr [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x140062449  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14006244d  call    UxPodGetCurrent
0x140062452  cmp     byte ptr [rsi+10h], 0
0x140062456  mov     r14, rax
0x140062459  jnz     loc_140177B18
0x14006245f  call    cs:__imp_PsGetCurrentServerSilo
0x140062466  nop     dword ptr [rax+rax+00h]
0x14006246b  mov     edx, 4C4C6C55h
0x140062470  mov     r8d, 24h ; '$'
0x140062476  mov     rcx, rax
0x140062479  mov     [rdi+30h], rax
0x14006247d  call    UxPodReferenceSilo
0x140062482  mov     byte ptr [rdi+28h], 1
0x140062486  lock inc dword ptr [r14+0BA0h]
0x14006248e  mov     [rsp+80h+Key], 0; Key
0x140062497  lea     rax, [rbp+arg_8]
0x14006249b  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x1400624a0  lea     rcx, [rdi+18h]
0x1400624a4  mov     eax, [rdi+38h]
0x1400624a7  lea     r8, UlpBufferFlushAPC; ApcRoutine
0x1400624ae  mov     [rsp+80h+Length], eax; Length
0x1400624b2  mov     r9, rdi; ApcContext
0x1400624b5  mov     rax, [rdi+40h]
0x1400624b9  xor     edx, edx; Event
0x1400624bb  mov     [rsp+80h+Buffer], rax; Buffer
0x1400624c0  mov     [rsp+80h+IoStatusBlock], rcx; IoStatusBlock
0x1400624c5  mov     rcx, [r15+40h]; FileHandle
0x1400624c9  call    cs:__imp_ZwWriteFile
0x1400624d0  nop     dword ptr [rax+rax+00h]
0x1400624d5  mov     ebx, eax
0x1400624d7  test    eax, eax
0x1400624d9  js      short loc_1400624FE
0x1400624db  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x1400624e2  jnz     short loc_14006252A
0x1400624e4  mov     eax, ebx
0x1400624e6  mov     rbx, [rsp+80h+arg_10]
0x1400624ee  add     rsp, 80h
0x1400624f5  pop     r15
0x1400624f7  pop     r14
0x1400624f9  pop     rdi
0x1400624fa  pop     rsi
0x1400624fb  pop     rbp
0x1400624fc  retn
0x1400624fe  test    byte ptr cs:xmmword_1401A2C90+9, 8
0x140062505  jz      loc_140177BED
0x14006250b  mov     edx, 15h
0x140062510  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x140062517  mov     ecx, 30Bh
0x14006251c  mov     r9d, eax
0x14006251f  call    WPP_SF_d
0x140062524  nop
0x140062525  jmp     loc_140177BED
0x14006252a  movzx   eax, byte ptr [rsi+10h]
0x14006252e  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x140062535  mov     [rsp+80h+Length], ebx
0x140062539  mov     edx, 16h
0x14006253e  mov     dword ptr [rsp+80h+Buffer], eax
0x140062542  mov     ecx, 50Bh
0x140062547  mov     r9, r15
0x14006254a  mov     [rsp+80h+IoStatusBlock], rdi
0x14006254f  call    WPP_SF_qqdd
0x140062554  jmp     short loc_1400624E4
0x140177b18  xorps   xmm0, xmm0
0x140177b1b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140177b22  xor     r9d, r9d; EventType
0x140177b25  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140177b2d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140177b31  mov     [rbp+ObjectAttributes.Attributes], 200h
0x140177b38  mov     edx, 1F0003h; DesiredAccess
0x140177b3d  mov     [rbp+ObjectAttributes.ObjectName], 0
0x140177b45  lea     rcx, [rbp+EventHandle]; EventHandle
0x140177b49  mov     byte ptr [rsp+80h+IoStatusBlock], 0; InitialState
0x140177b4e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140177b53  call    cs:__imp_ZwCreateEvent
0x140177b5a  nop     dword ptr [rax+rax+00h]
0x140177b5f  mov     ebx, eax
0x140177b61  test    eax, eax
0x140177b63  js      short loc_140177BDF
0x140177b65  mov     rdx, [rbp+EventHandle]; Event
0x140177b69  lea     rax, [rbp+arg_8]
0x140177b6d  mov     [rsp+80h+Key], 0; Key
0x140177b76  lea     rcx, [rdi+18h]
0x140177b7a  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x140177b7f  xor     r9d, r9d; ApcContext
0x140177b82  mov     eax, [rdi+38h]
0x140177b85  xor     r8d, r8d; ApcRoutine
0x140177b88  mov     [rsp+80h+Length], eax; Length
0x140177b8c  mov     rax, [rdi+40h]
0x140177b90  mov     [rsp+80h+Buffer], rax; Buffer
0x140177b95  mov     [rsp+80h+IoStatusBlock], rcx; IoStatusBlock
0x140177b9a  mov     rcx, [r15+40h]; FileHandle
0x140177b9e  call    cs:__imp_ZwWriteFile
0x140177ba5  nop     dword ptr [rax+rax+00h]
0x140177baa  mov     ebx, eax
0x140177bac  cmp     eax, 103h
0x140177bb1  jnz     short loc_140177BCF
0x140177bb3  mov     rcx, [rbp+EventHandle]; Handle
0x140177bb7  xor     r8d, r8d; Timeout
0x140177bba  xor     edx, edx; Alertable
0x140177bbc  call    cs:__imp_ZwWaitForSingleObject
0x140177bc3  nop     dword ptr [rax+rax+00h]
0x140177bc8  mov     rax, [rsi+8]
0x140177bcc  mov     ebx, [rax+18h]
0x140177bcf  mov     rcx, [rbp+EventHandle]; Handle
0x140177bd3  call    cs:__imp_ZwClose
0x140177bda  nop     dword ptr [rax+rax+00h]
0x140177bdf  mov     rcx, rdi
0x140177be2  call    UlFreeLogFileBuffer
0x140177be7  nop
0x140177be8  jmp     loc_1400624DB
0x140177bed  mov     rdx, r14
0x140177bf0  mov     rcx, rdi
0x140177bf3  call    UlpLogBufferWriteCompletion
0x140177bf8  nop
0x140177bf9  jmp     loc_1400624DB
```
