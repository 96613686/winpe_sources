# BiGetPhysicalDiskNumber

- ea: `0x140017aec`
- end: `0x140017bf8`
- name: `BiGetPhysicalDiskNumber`
- size: `268`
- prototype: `__int64 __fastcall(PCWSTR SourceString, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140017c00`
- `0x140020e68`

## callees

- `0x140017aec`
- `0x140017cac`

## import_xrefs

- `ntdll!ZwClose` at `0x140017bdb`
- `ntdll!ZwClose` at `0x140017bdb`
- `ntdll!RtlFreeHeap` at `0x140017bcc`
- `ntdll!RtlFreeHeap` at `0x140017bcc`
- `ntdll!RtlInitUnicodeString` at `0x140017b2f`
- `ntdll!RtlInitUnicodeString` at `0x140017b2f`
- `ntdll!ZwOpenFile` at `0x140017b80`
- `ntdll!ZwOpenFile` at `0x140017b80`

## pseudocode

```c
__int64 __fastcall BiGetPhysicalDiskNumber(PCWSTR SourceString, _DWORD *a2)
{
  NTSTATUS v3; // ebx
  int VolumeDiskExtentsInformation; // eax
  PVOID v5; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp+20h] BYREF
  PVOID P; // [rsp+A8h] [rbp+28h]

  FileHandle = 0;
  P = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v3 = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v3 >= 0 )
  {
    VolumeDiskExtentsInformation = BiGetVolumeDiskExtentsInformation(FileHandle);
    v5 = P;
    v3 = VolumeDiskExtentsInformation;
    if ( VolumeDiskExtentsInformation >= 0 )
    {
      if ( *(_DWORD *)P == 1 )
      {
        v3 = 0;
        *a2 = *((_DWORD *)P + 2);
      }
      else
      {
        v3 = -1073741637;
      }
    }
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140017aec  mov     [rsp-8+arg_0], rbx
0x140017af1  mov     [rsp-8+arg_8], rdi
0x140017af6  push    rbp
0x140017af7  mov     rbp, rsp
0x140017afa  sub     rsp, 80h
0x140017b01  xorps   xmm0, xmm0
0x140017b04  xor     eax, eax
0x140017b06  mov     rdi, rdx
0x140017b09  mov     [rbp+FileHandle], rax
0x140017b0d  mov     rdx, rcx; SourceString
0x140017b10  mov     [rbp+P], rax
0x140017b14  xorps   xmm1, xmm1
0x140017b17  lea     rcx, [rbp+DestinationString]; DestinationString
0x140017b1b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140017b1f  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140017b23  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140017b27  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140017b2b  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140017b2f  call    cs:__imp_RtlInitUnicodeString
0x140017b35  xorps   xmm0, xmm0
0x140017b38  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x140017b40  lea     rax, [rbp+DestinationString]
0x140017b44  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140017b4b  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140017b4f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140017b53  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140017b57  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140017b5f  mov     edx, 80100000h; DesiredAccess
0x140017b64  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140017b6b  lea     rcx, [rbp+FileHandle]; FileHandle
0x140017b6f  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x140017b77  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140017b7c  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140017b80  call    cs:__imp_ZwOpenFile
0x140017b86  mov     ebx, eax
0x140017b88  test    eax, eax
0x140017b8a  js      short loc_140017BD2
0x140017b8c  mov     rcx, [rbp+FileHandle]; FileHandle
0x140017b90  lea     rdx, [rbp+P]
0x140017b94  call    BiGetVolumeDiskExtentsInformation
0x140017b99  mov     r8, [rbp+P]; P
0x140017b9d  mov     ebx, eax
0x140017b9f  test    eax, eax
0x140017ba1  js      short loc_140017BB8
0x140017ba3  cmp     dword ptr [r8], 1
0x140017ba7  jz      short loc_140017BB0
0x140017ba9  mov     ebx, 0C00000BBh
0x140017bae  jmp     short loc_140017BB8
0x140017bb0  mov     eax, [r8+8]
0x140017bb4  xor     ebx, ebx
0x140017bb6  mov     [rdi], eax
0x140017bb8  test    r8, r8
0x140017bbb  jz      short loc_140017BD2
0x140017bbd  mov     rcx, gs:60h
0x140017bc6  xor     edx, edx; Flags
0x140017bc8  mov     rcx, [rcx+30h]; HeapHandle
0x140017bcc  call    cs:__imp_RtlFreeHeap
0x140017bd2  mov     rcx, [rbp+FileHandle]; Handle
0x140017bd6  test    rcx, rcx
0x140017bd9  jz      short loc_140017BE1
0x140017bdb  call    cs:__imp_ZwClose
0x140017be1  lea     r11, [rsp+80h+var_s0]
0x140017be9  mov     eax, ebx
0x140017beb  mov     rbx, [r11+10h]
0x140017bef  mov     rdi, [r11+18h]
0x140017bf3  mov     rsp, r11
0x140017bf6  pop     rbp
0x140017bf7  retn
```
