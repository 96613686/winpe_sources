# SdbWriteBinaryTagFromFile

- ea: `0x18003ff20`
- end: `0x1800400f2`
- name: `SdbWriteBinaryTagFromFile`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x18001a900`
- `0x18001b024`
- `0x18003c9c0`
- `0x18003fee0`
- `0x18003ff20`

## import_xrefs

- `ntdll!NtReadFile` at `0x180040054`
- `ntdll!NtReadFile` at `0x180040054`
- `ntdll!RtlAllocateHeap` at `0x18004000e`
- `ntdll!RtlAllocateHeap` at `0x18004000e`

## string_xrefs

- `0x18003ff64`: `AslFileOpen failed [%x]`
- `0x18003ff75`: `SdbWriteBinaryTagFromFile`
- `0x18003ffb7`: `SdbWriteBinaryTagFromFile`
- `0x18003ffe2`: `SdbWriteBinaryTagFromFile`
- `0x180040071`: `SdbWriteBinaryTagFromFile`
- `0x1800400c9`: `SdbWriteBinaryTagFromFile`
- `0x180040064`: `Failed to read data [%x]`

## pseudocode

```c
__int64 __fastcall SdbWriteBinaryTagFromFile(__int64 a1, unsigned __int16 a2, WCHAR *a3)
{
  int v5; // eax
  int v7; // eax
  unsigned int v8; // ebx
  ULONG Length; // ebx
  PVOID Buffer; // r14
  NTSTATUS v11; // eax
  int v12; // eax
  SIZE_T Size; // [rsp+50h] [rbp-20h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-10h] BYREF
  HANDLE FileHandle; // [rsp+A8h] [rbp+38h] BYREF

  FileHandle = 0;
  ByteOffset.QuadPart = 0;
  IoStatusBlock = 0;
  v5 = AslFileOpen(&FileHandle, a3);
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "SdbWriteBinaryTagFromFile", 660, "AslFileOpen failed [%x]", v5);
    return 0;
  }
  Size = 0;
  v7 = AslFileGetSize(&Size, FileHandle);
  if ( v7 >= 0 )
  {
    if ( HIDWORD(Size) )
    {
      AslLogCallPrintf(1, "SdbWriteBinaryTagFromFile", 674, "File is too large to add.");
    }
    else
    {
      Length = Size;
      Buffer = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Size);
      if ( Buffer )
      {
        ByteOffset.QuadPart = 0;
        v11 = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
        if ( v11 >= 0 )
        {
          v8 = SdbWriteBinaryTag(a1, a2, Buffer, Length);
        }
        else
        {
          v8 = 0;
          AslLogCallPrintf(1, "SdbWriteBinaryTagFromFile", 699, "Failed to read data [%x]", v11);
        }
        AslFree(NtCurrentPeb()->ProcessHeap, Buffer);
        goto LABEL_13;
      }
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbWriteBinaryTagFromFile", 668, "AslFileGetSize failed [%x]", v7);
  }
  v8 = 0;
LABEL_13:
  v12 = AslFileClose(FileHandle);
  if ( v12 < 0 )
    AslLogCallPrintf(1, "SdbWriteBinaryTagFromFile", 711, "AslFileClose failed [%x]", v12);
  return v8;
}

```

## disassembly

```asm
0x18003ff20  mov     [rsp-18h+arg_0], rbx
0x18003ff25  mov     [rsp-18h+arg_8], r12
0x18003ff2a  push    rbp
0x18003ff2b  push    r14
0x18003ff2d  push    r15
0x18003ff2f  mov     rbp, rsp
0x18003ff32  sub     rsp, 70h
0x18003ff36  movzx   r15d, dx
0x18003ff3a  mov     [rbp+FileHandle], 0
0x18003ff42  mov     r12, rcx
0x18003ff45  mov     qword ptr [rbp+var_18], 0
0x18003ff4d  xorps   xmm0, xmm0
0x18003ff50  lea     rcx, [rbp+FileHandle]; FileHandle
0x18003ff54  mov     rdx, r8; FileName
0x18003ff57  movups  xmmword ptr [rbp+var_10], xmm0
0x18003ff5b  call    AslFileOpen
0x18003ff60  test    eax, eax
0x18003ff62  jns     short loc_18003FF8D
0x18003ff64  lea     r9, aAslfileopenFai; "AslFileOpen failed [%x]"
0x18003ff6b  mov     dword ptr [rsp+70h+IoStatusBlock], eax
0x18003ff6f  mov     r8d, 294h
0x18003ff75  lea     rdx, aSdbwritebinary_1; "SdbWriteBinaryTagFromFile"
0x18003ff7c  mov     ecx, 1
0x18003ff81  call    AslLogCallPrintf
0x18003ff86  xor     eax, eax
0x18003ff88  jmp     loc_1800400DC
0x18003ff8d  mov     rdx, [rbp+FileHandle]
0x18003ff91  lea     rcx, [rbp+Size]
0x18003ff95  mov     [rbp+Size], 0
0x18003ff9d  call    AslFileGetSize
0x18003ffa2  test    eax, eax
0x18003ffa4  jns     short loc_18003FFCF
0x18003ffa6  lea     r9, aAslfilegetsize; "AslFileGetSize failed [%x]"
0x18003ffad  mov     dword ptr [rsp+70h+IoStatusBlock], eax
0x18003ffb1  mov     r8d, 29Ch
0x18003ffb7  lea     rdx, aSdbwritebinary_1; "SdbWriteBinaryTagFromFile"
0x18003ffbe  mov     ecx, 1
0x18003ffc3  call    AslLogCallPrintf
0x18003ffc8  xor     ebx, ebx
0x18003ffca  jmp     loc_1800400AB
0x18003ffcf  cmp     dword ptr [rbp+Size+4], 0
0x18003ffd3  jz      short loc_18003FFF5
0x18003ffd5  lea     r9, aFileIsTooLarge; "File is too large to add."
0x18003ffdc  mov     r8d, 2A2h
0x18003ffe2  lea     rdx, aSdbwritebinary_1; "SdbWriteBinaryTagFromFile"
0x18003ffe9  mov     ecx, 1
0x18003ffee  call    AslLogCallPrintf
0x18003fff3  jmp     short loc_18003FFC8
0x18003fff5  mov     rcx, gs:60h
0x18003fffe  mov     edx, 8; Flags
0x180040003  mov     rbx, [rbp+Size]
0x180040007  mov     r8d, ebx; Size
0x18004000a  mov     rcx, [rcx+30h]; HeapHandle
0x18004000e  call    cs:__imp_RtlAllocateHeap
0x180040014  mov     r14, rax
0x180040017  test    rax, rax
0x18004001a  jz      short loc_18003FFC8
0x18004001c  mov     rcx, [rbp+FileHandle]; FileHandle
0x180040020  lea     rax, [rbp+var_18]
0x180040024  mov     [rsp+70h+Key], 0; Key
0x18004002d  xor     r9d, r9d; ApcContext
0x180040030  mov     [rsp+70h+ByteOffset], rax; ByteOffset
0x180040035  xor     r8d, r8d; ApcRoutine
0x180040038  mov     [rsp+70h+Length], ebx; Length
0x18004003c  lea     rax, [rbp+var_10]
0x180040040  mov     [rsp+70h+Buffer], r14; Buffer
0x180040045  xor     edx, edx; Event
0x180040047  mov     [rsp+70h+IoStatusBlock], rax; IoStatusBlock
0x18004004c  mov     qword ptr [rbp+var_18], 0
0x180040054  call    cs:__imp_NtReadFile
0x18004005a  test    eax, eax
0x18004005c  jns     short loc_180040082
0x18004005e  xor     ebx, ebx
0x180040060  mov     dword ptr [rsp+70h+IoStatusBlock], eax
0x180040064  lea     r9, aFailedToReadDa; "Failed to read data [%x]"
0x18004006b  mov     r8d, 2BBh
0x180040071  lea     rdx, aSdbwritebinary_1; "SdbWriteBinaryTagFromFile"
0x180040078  lea     ecx, [rbx+1]
0x18004007b  call    AslLogCallPrintf
0x180040080  jmp     short loc_180040096
0x180040082  mov     r9d, ebx
0x180040085  mov     r8, r14
0x180040088  movzx   edx, r15w
0x18004008c  mov     rcx, r12
0x18004008f  call    SdbWriteBinaryTag
0x180040094  mov     ebx, eax
0x180040096  mov     rcx, gs:60h
0x18004009f  mov     rdx, r14
0x1800400a2  mov     rcx, [rcx+30h]
0x1800400a6  call    AslFree
0x1800400ab  mov     rcx, [rbp+FileHandle]
0x1800400af  call    AslFileClose
0x1800400b4  test    eax, eax
0x1800400b6  jns     short loc_1800400DA
0x1800400b8  lea     r9, aAslfilecloseFa; "AslFileClose failed [%x]"
0x1800400bf  mov     dword ptr [rsp+70h+IoStatusBlock], eax
0x1800400c3  mov     r8d, 2C7h
0x1800400c9  lea     rdx, aSdbwritebinary_1; "SdbWriteBinaryTagFromFile"
0x1800400d0  mov     ecx, 1
0x1800400d5  call    AslLogCallPrintf
0x1800400da  mov     eax, ebx
0x1800400dc  lea     r11, [rsp+70h+var_s0]
0x1800400e1  mov     rbx, [r11+20h]
0x1800400e5  mov     r12, [r11+28h]
0x1800400e9  mov     rsp, r11
0x1800400ec  pop     r15
0x1800400ee  pop     r14
0x1800400f0  pop     rbp
0x1800400f1  retn
```
