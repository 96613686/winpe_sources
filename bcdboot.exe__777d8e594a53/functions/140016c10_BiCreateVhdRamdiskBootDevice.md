# BiCreateVhdRamdiskBootDevice

- ea: `0x140016c10`
- end: `0x140016dff`
- name: `BiCreateVhdRamdiskBootDevice`
- size: `495`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x140016784`

## callees

- `0x140016c10`
- `0x1400265e2`
- `0x1400265fa`

## import_xrefs

- `ntdll!ZwDeviceIoControlFile` at `0x140016cfb`
- `ntdll!ZwDeviceIoControlFile` at `0x140016cfb`
- `ntdll!ZwClose` at `0x140016d07`
- `ntdll!ZwClose` at `0x140016d07`
- `ntdll!RtlAllocateHeap` at `0x140016d55`
- `ntdll!RtlAllocateHeap` at `0x140016d55`
- `ntdll!RtlInitUnicodeString` at `0x140016c6e`
- `ntdll!RtlInitUnicodeString` at `0x140016c6e`
- `ntdll!ZwOpenFile` at `0x140016cb7`
- `ntdll!ZwOpenFile` at `0x140016cb7`

## pseudocode

```c
__int64 __fastcall BiCreateVhdRamdiskBootDevice(__int64 a1, _QWORD *a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rax
  size_t v6; // rsi
  unsigned int v7; // r14d
  char *Heap; // rax
  char *v9; // rbx
  int v10; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-39h] BYREF
  _BYTE OutputBuffer[20]; // [rsp+A0h] [rbp-29h] BYREF
  int v16; // [rsp+B4h] [rbp-15h]
  __int64 v17; // [rsp+C0h] [rbp-9h]
  int v18; // [rsp+C8h] [rbp-1h]
  __int64 v19; // [rsp+D0h] [rbp+7h]
  void *FileHandle; // [rsp+140h] [rbp+77h] BYREF

  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  memset_0(OutputBuffer, 0, 0x40u);
  DestinationString = 0;
  FileHandle = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v4 = ZwOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v4 >= 0 )
  {
    v4 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x240008u, 0, 0, OutputBuffer, 0x40u);
    ZwClose(FileHandle);
    if ( v4 >= 0 )
    {
      if ( v16 == 3 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)(a1 + 2 * v5 + 106) );
        v6 = 2 * v5 + 2;
        v7 = 2 * v5 + 106;
        Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        v9 = Heap;
        if ( Heap )
        {
          memset_0(Heap, 0, v7);
          *(_DWORD *)v9 = 0;
          *((_DWORD *)v9 + 4) = 5;
          *(_QWORD *)(v9 + 28) = 5;
          *((_DWORD *)v9 + 6) = v6 + 84;
          *((_DWORD *)v9 + 2) = v7;
          *((_DWORD *)v9 + 5) = 1;
          *((_DWORD *)v9 + 10) = 72;
          *((_DWORD *)v9 + 9) = 16;
          *((_DWORD *)v9 + 12) = 3;
          *(_QWORD *)(v9 + 52) = v19 << 12;
          *(_QWORD *)(v9 + 60) = v17;
          v10 = v18;
          *((_DWORD *)v9 + 18) = 1;
          *((_DWORD *)v9 + 20) = 5;
          *((_DWORD *)v9 + 17) = v10;
          *((_DWORD *)v9 + 19) = 12;
          memcpy_0(v9 + 104, (const void *)(a1 + 106), v6);
          *a2 = v9;
          return 0;
        }
        else
        {
          return (unsigned int)-1073741670;
        }
      }
      else
      {
        return (unsigned int)-1073741808;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140016c10  push    rbp
0x140016c12  push    rbx
0x140016c13  push    rsi
0x140016c14  push    rdi
0x140016c15  push    r12
0x140016c17  push    r13
0x140016c19  push    r14
0x140016c1b  push    r15
0x140016c1d  lea     rbp, [rsp-1Fh]
0x140016c22  sub     rsp, 0E8h
0x140016c29  xorps   xmm0, xmm0
0x140016c2c  xor     eax, eax
0x140016c2e  mov     r12, rdx
0x140016c31  mov     rdi, rcx
0x140016c34  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140016c38  xor     edx, edx; Val
0x140016c3a  lea     rcx, [rbp+57h+var_80]; void *
0x140016c3e  lea     esi, [rax+40h]
0x140016c41  mov     r8d, esi; Size
0x140016c44  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140016c48  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140016c4c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140016c50  call    memset_0
0x140016c55  xorps   xmm0, xmm0
0x140016c58  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x140016c5f  xor     r13d, r13d
0x140016c62  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140016c66  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140016c6a  mov     [rbp+57h+FileHandle], r13
0x140016c6e  call    cs:__imp_RtlInitUnicodeString
0x140016c74  lea     rax, [rbp+57h+DestinationString]
0x140016c78  mov     [rsp+120h+OpenOptions], 20h ; ' '; OpenOptions
0x140016c80  xorps   xmm0, xmm0
0x140016c83  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016c87  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140016c8b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016c92  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140016c96  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x140016c9a  mov     edx, 0C0000000h; DesiredAccess
0x140016c9f  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140016ca6  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140016caa  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x140016cb2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016cb7  call    cs:__imp_ZwOpenFile
0x140016cbd  mov     ebx, eax
0x140016cbf  test    eax, eax
0x140016cc1  js      loc_140016DE9
0x140016cc7  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140016ccb  lea     rax, [rbp+57h+var_80]
0x140016ccf  mov     [rsp+120h+OutputBufferLength], esi; OutputBufferLength
0x140016cd3  xor     r9d, r9d; ApcContext
0x140016cd6  mov     [rsp+120h+OutputBuffer], rax; OutputBuffer
0x140016cdb  xor     r8d, r8d; ApcRoutine
0x140016cde  mov     [rsp+120h+InputBufferLength], r13d; InputBufferLength
0x140016ce3  lea     rax, [rbp+57h+IoStatusBlock]
0x140016ce7  mov     [rsp+120h+InputBuffer], r13; InputBuffer
0x140016cec  xor     edx, edx; Event
0x140016cee  mov     [rsp+120h+OpenOptions], 240008h; IoControlCode
0x140016cf6  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x140016cfb  call    cs:__imp_ZwDeviceIoControlFile
0x140016d01  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140016d05  mov     ebx, eax
0x140016d07  call    cs:__imp_ZwClose
0x140016d0d  test    ebx, ebx
0x140016d0f  js      loc_140016DE9
0x140016d15  cmp     [rbp+57h+var_6C], 3
0x140016d19  jz      short loc_140016D25
0x140016d1b  mov     ebx, 0C0000010h
0x140016d20  jmp     loc_140016DE9
0x140016d25  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016d29  inc     rax
0x140016d2c  cmp     [rdi+rax*2+6Ah], r13w
0x140016d32  jnz     short loc_140016D29
0x140016d34  mov     rcx, gs:60h
0x140016d3d  lea     rsi, ds:2[rax*2]
0x140016d45  lea     r14d, [rsi+68h]
0x140016d49  xor     edx, edx; Flags
0x140016d4b  mov     r8d, r14d; Size
0x140016d4e  mov     r15d, r14d
0x140016d51  mov     rcx, [rcx+30h]; HeapHandle
0x140016d55  call    cs:__imp_RtlAllocateHeap
0x140016d5b  mov     rbx, rax
0x140016d5e  test    rax, rax
0x140016d61  jnz     short loc_140016D6A
0x140016d63  mov     ebx, 0C000009Ah
0x140016d68  jmp     short loc_140016DE9
0x140016d6a  mov     r8, r15; Size
0x140016d6d  xor     edx, edx; Val
0x140016d6f  mov     rcx, rbx; void *
0x140016d72  call    memset_0
0x140016d77  mov     edx, 5
0x140016d7c  mov     [rbx], r13d
0x140016d7f  mov     [rbx+10h], edx
0x140016d82  lea     eax, [rsi+54h]
0x140016d85  mov     [rbx+1Ch], rdx
0x140016d89  mov     r8, rsi; Size
0x140016d8c  mov     [rbx+18h], eax
0x140016d8f  lea     ecx, [rdx-4]
0x140016d92  mov     [rbx+8], r14d
0x140016d96  mov     [rbx+14h], ecx
0x140016d99  mov     dword ptr [rbx+28h], 48h ; 'H'
0x140016da0  mov     dword ptr [rbx+24h], 10h
0x140016da7  mov     dword ptr [rbx+30h], 3
0x140016dae  mov     rax, [rbp+57h+var_50]
0x140016db2  shl     rax, 0Ch
0x140016db6  mov     [rbx+34h], rax
0x140016dba  mov     rax, [rbp+57h+var_60]
0x140016dbe  mov     [rbx+3Ch], rax
0x140016dc2  mov     eax, [rbp+57h+var_58]
0x140016dc5  mov     [rbx+48h], ecx
0x140016dc8  lea     rcx, [rbx+68h]; void *
0x140016dcc  mov     [rbx+50h], edx
0x140016dcf  lea     rdx, [rdi+6Ah]; Src
0x140016dd3  mov     [rbx+44h], eax
0x140016dd6  mov     dword ptr [rbx+4Ch], 0Ch
0x140016ddd  call    memcpy_0
0x140016de2  mov     [r12], rbx
0x140016de6  mov     ebx, r13d
0x140016de9  mov     eax, ebx
0x140016deb  add     rsp, 0E8h
0x140016df2  pop     r15
0x140016df4  pop     r14
0x140016df6  pop     r13
0x140016df8  pop     r12
0x140016dfa  pop     rdi
0x140016dfb  pop     rsi
0x140016dfc  pop     rbx
0x140016dfd  pop     rbp
0x140016dfe  retn
```
