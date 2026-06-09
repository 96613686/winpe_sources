# OpenCompartment

- ea: `0x140055fa0`
- end: `0x14005614c`
- name: `OpenCompartment`
- size: `428`
- prototype: `NTSTATUS __fastcall(__int128 *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x140055fa0`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140056115`
- `ntoskrnl!ZwClose` at `0x140056115`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400560ff`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400560ff`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400560e2`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400560e2`
- `ntoskrnl!ZwCreateFile` at `0x140056079`
- `ntoskrnl!ZwCreateFile` at `0x140056079`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055ffd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055ffd`

## pseudocode

```c
NTSTATUS __fastcall OpenCompartment(__int128 *a1, void **a2)
{
  NTSTATUS result; // eax
  __int128 v5; // xmm0
  void *v6; // rcx
  NTSTATUS Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp+27h] BYREF
  _BYTE InputBuffer[24]; // [rsp+B0h] [rbp+37h] BYREF

  *a2 = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  IoStatusBlock = 0;
  memset(InputBuffer, 0, sizeof(InputBuffer));
  RtlInitUnicodeString(&DestinationString, L"\\Device\\NDIS");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  result = ZwCreateFile(a2, 0x2000000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
  if ( result >= 0 )
  {
    v5 = *a1;
    v6 = *a2;
    *(_DWORD *)InputBuffer = 1573248;
    *(_OWORD *)&InputBuffer[4] = v5;
    *(_DWORD *)&InputBuffer[20] = 0;
    Status = ZwDeviceIoControlFile(v6, 0, 0, 0, &IoStatusBlock, 0x1700ACu, InputBuffer, 0x18u, 0, 0);
    if ( Status == 259 )
    {
      ZwWaitForSingleObject(*a2, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status < 0 )
    {
      ZwClose(*a2);
      *a2 = 0;
    }
    return Status;
  }
  return result;
}

```

## disassembly

```asm
0x140055fa0  mov     [rsp-8+arg_10], rbx
0x140055fa5  mov     [rsp-8+arg_18], rdi
0x140055faa  push    rbp
0x140055fab  lea     rbp, [rsp-57h]
0x140055fb0  sub     rsp, 0D0h
0x140055fb7  mov     rax, cs:__security_cookie
0x140055fbe  xor     rax, rsp
0x140055fc1  mov     [rbp+57h+var_8], rax
0x140055fc5  xorps   xmm0, xmm0
0x140055fc8  xor     eax, eax
0x140055fca  mov     [rdx], rax
0x140055fcd  mov     rdi, rdx
0x140055fd0  mov     rbx, rcx
0x140055fd3  mov     [rbp+57h+var_10], rax
0x140055fd7  xorps   xmm1, xmm1
0x140055fda  lea     rdx, aDeviceNdis; "\\Device\\NDIS"
0x140055fe1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140055fe5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140055fe9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140055fed  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140055ff1  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140055ff5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140055ff9  movups  [rbp+57h+InputBuffer], xmm1
0x140055ffd  call    cs:__imp_RtlInitUnicodeString
0x140056004  nop     dword ptr [rax+rax+00h]
0x140056009  mov     [rsp+0D0h+EaLength], 0; EaLength
0x140056011  lea     rax, [rbp+57h+DestinationString]
0x140056015  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x14005601e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140056022  mov     [rsp+0D0h+CreateOptions], 0; CreateOptions
0x14005602a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005602e  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x140056036  xorps   xmm0, xmm0
0x140056039  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x140056041  mov     edx, 2000000h; DesiredAccess
0x140056046  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x14005604e  mov     rcx, rdi; FileHandle
0x140056051  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x14005605a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140056061  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140056069  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140056070  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140056074  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140056079  call    cs:__imp_ZwCreateFile
0x140056080  nop     dword ptr [rax+rax+00h]
0x140056085  test    eax, eax
0x140056087  js      loc_14005612A
0x14005608d  movups  xmm0, xmmword ptr [rbx]
0x140056090  mov     rcx, [rdi]; FileHandle
0x140056093  mov     eax, 18h
0x140056098  mov     dword ptr [rsp+0D0h+EaBuffer], 0; OutputBufferLength
0x1400560a0  xor     r9d, r9d; ApcContext
0x1400560a3  mov     qword ptr [rsp+0D0h+CreateOptions], 0; OutputBuffer
0x1400560ac  xor     r8d, r8d; ApcRoutine
0x1400560af  mov     [rsp+0D0h+CreateDisposition], eax; InputBufferLength
0x1400560b3  xor     edx, edx; Event
0x1400560b5  lea     rax, [rbp+57h+InputBuffer]
0x1400560b9  mov     dword ptr [rbp+57h+InputBuffer], 180180h
0x1400560c0  mov     qword ptr [rsp+0D0h+ShareAccess], rax; InputBuffer
0x1400560c5  lea     rax, [rbp+57h+IoStatusBlock]
0x1400560c9  mov     [rsp+0D0h+FileAttributes], 1700ACh; IoControlCode
0x1400560d1  mov     [rsp+0D0h+AllocationSize], rax; IoStatusBlock
0x1400560d6  movdqu  [rbp+57h+InputBuffer+4], xmm0
0x1400560db  mov     dword ptr [rbp+57h+var_10+4], 0
0x1400560e2  call    cs:__imp_ZwDeviceIoControlFile
0x1400560e9  nop     dword ptr [rax+rax+00h]
0x1400560ee  mov     ebx, eax
0x1400560f0  cmp     eax, 103h
0x1400560f5  jnz     short loc_14005610E
0x1400560f7  mov     rcx, [rdi]; Handle
0x1400560fa  xor     r8d, r8d; Timeout
0x1400560fd  xor     edx, edx; Alertable
0x1400560ff  call    cs:__imp_ZwWaitForSingleObject
0x140056106  nop     dword ptr [rax+rax+00h]
0x14005610b  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x14005610e  test    ebx, ebx
0x140056110  jns     short loc_140056128
0x140056112  mov     rcx, [rdi]; Handle
0x140056115  call    cs:__imp_ZwClose
0x14005611c  nop     dword ptr [rax+rax+00h]
0x140056121  mov     qword ptr [rdi], 0
0x140056128  mov     eax, ebx
0x14005612a  mov     rcx, [rbp+57h+var_8]
0x14005612e  xor     rcx, rsp; StackCookie
0x140056131  call    __security_check_cookie
0x140056136  lea     r11, [rsp+0D0h+var_s0]
0x14005613e  mov     rbx, [r11+20h]
0x140056142  mov     rdi, [r11+28h]
0x140056146  mov     rsp, r11
0x140056149  pop     rbp
0x14005614a  retn
```
