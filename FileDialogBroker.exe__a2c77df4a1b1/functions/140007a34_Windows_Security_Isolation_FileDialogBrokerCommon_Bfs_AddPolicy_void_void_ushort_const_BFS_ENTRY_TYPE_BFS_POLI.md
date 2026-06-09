# Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::AddPolicy(void *,void *,ushort const *,_BFS_ENTRY_TYPE,_BFS_POLICY,ulong)

- ea: `0x140007a34`
- end: `0x140007b08`
- name: `?AddPolicy@Bfs@FileDialogBrokerCommon@Isolation@Security@Windows@@YAKPEAX0PEBGW4_BFS_ENTRY_TYPE@@W4_BFS_POLICY@@K@Z`
- size: `212`
- prototype: `__int64 __fastcall(void *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400105c4`

## callees

- `0x140007a34`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140007a93`
- `ntdll!RtlNtStatusToDosError` at `0x140007ae3`
- `ntdll!RtlNtStatusToDosError` at `0x140007a93`
- `ntdll!RtlNtStatusToDosError` at `0x140007ae3`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140007a87`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140007a87`
- `ntdll!RtlFreeUnicodeString` at `0x140007aef`
- `ntdll!RtlFreeUnicodeString` at `0x140007aef`
- `ntdll!NtDeviceIoControlFile` at `0x140007adb`
- `ntdll!NtDeviceIoControlFile` at `0x140007adb`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::AddPolicy(
        void *a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  NTSTATUS v5; // eax
  ULONG v6; // ebx
  NTSTATUS v7; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  __int64 InputBuffer; // [rsp+60h] [rbp+17h] BYREF
  int v11; // [rsp+68h] [rbp+1Fh]
  __int64 v12; // [rsp+6Ch] [rbp+23h]
  __int128 v13; // [rsp+74h] [rbp+2Bh] BYREF
  __int64 UnicodeString_12; // [rsp+84h] [rbp+3Bh]
  int v15; // [rsp+8Ch] [rbp+43h]

  InputBuffer = a2;
  v11 = a4;
  UnicodeString_12 = 0;
  v15 = 0;
  v12 = 1;
  IoStatusBlock = 0;
  v13 = 0;
  v5 = RtlDosPathNameToNtPathName_U_WithStatus(a3, (char *)&v13 + 4, 0, 0);
  if ( v5 >= 0 )
  {
    v7 = NtDeviceIoControlFile(a1, 0, 0, 0, &IoStatusBlock, 0x228004u, &InputBuffer, 0x30u, 0, 0);
    v6 = RtlNtStatusToDosError(v7);
    RtlFreeUnicodeString((PUNICODE_STRING)((char *)&v13 + 4));
  }
  else
  {
    return RtlNtStatusToDosError(v5);
  }
  return v6;
}

```

## disassembly

```asm
0x140007a34  mov     [rsp-8+arg_0], rbx
0x140007a39  push    rbp
0x140007a3a  lea     rbp, [rsp-47h]
0x140007a3f  sub     rsp, 90h
0x140007a46  mov     rax, r8
0x140007a49  mov     [rbp+47h+var_30], rdx
0x140007a4d  mov     rbx, rcx
0x140007a50  mov     [rbp+47h+var_28], r9d
0x140007a54  xorps   xmm0, xmm0
0x140007a57  mov     qword ptr [rbp+47h+UnicodeString+0Ch], 0
0x140007a5f  xorps   xmm1, xmm1
0x140007a62  mov     [rbp+47h+var_4], 0
0x140007a69  mov     rcx, rax
0x140007a6c  mov     [rbp+47h+var_24], 1
0x140007a74  xor     r9d, r9d
0x140007a77  lea     rdx, [rbp+47h+UnicodeString]
0x140007a7b  xor     r8d, r8d
0x140007a7e  movups  xmmword ptr [rbp+47h+var_40], xmm0
0x140007a82  movdqu  xmmword ptr [rbp+2Bh], xmm1
0x140007a87  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140007a8d  test    eax, eax
0x140007a8f  jns     short loc_140007A9D
0x140007a91  mov     ecx, eax; Status
0x140007a93  call    cs:__imp_RtlNtStatusToDosError
0x140007a99  mov     ebx, eax
0x140007a9b  jmp     short loc_140007AF5
0x140007a9d  mov     [rsp+90h+OutputBufferLength], 0; OutputBufferLength
0x140007aa5  lea     rax, [rbp+47h+var_30]
0x140007aa9  mov     [rsp+90h+OutputBuffer], 0; OutputBuffer
0x140007ab2  xor     r9d, r9d; ApcContext
0x140007ab5  mov     [rsp+90h+InputBufferLength], 30h ; '0'; InputBufferLength
0x140007abd  xor     r8d, r8d; ApcRoutine
0x140007ac0  mov     [rsp+90h+InputBuffer], rax; InputBuffer
0x140007ac5  xor     edx, edx; Event
0x140007ac7  lea     rax, [rbp+47h+var_40]
0x140007acb  mov     [rsp+90h+IoControlCode], 228004h; IoControlCode
0x140007ad3  mov     rcx, rbx; FileHandle
0x140007ad6  mov     [rsp+90h+IoStatusBlock], rax; IoStatusBlock
0x140007adb  call    cs:__imp_NtDeviceIoControlFile
0x140007ae1  mov     ecx, eax; Status
0x140007ae3  call    cs:__imp_RtlNtStatusToDosError
0x140007ae9  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x140007aed  mov     ebx, eax
0x140007aef  call    cs:__imp_RtlFreeUnicodeString
0x140007af5  mov     eax, ebx
0x140007af7  mov     rbx, [rsp+90h+arg_0]
0x140007aff  add     rsp, 90h
0x140007b06  pop     rbp
0x140007b07  retn
```
