# VfsCopyStreamData

- ea: `0x1400028d4`
- end: `0x1400029e7`
- name: `VfsCopyStreamData`
- size: `275`
- prototype: `__int64 __fastcall(PFLT_INSTANCE InitiatingInstance, PFILE_OBJECT FileObject, PFLT_INSTANCE, PFILE_OBJECT, __int64 FileInformation, PVOID Buffer, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400022b4`

## callees

- `0x1400028d4`

## import_xrefs

- `FLTMGR!FltWriteFile` at `0x14000297d`
- `FLTMGR!FltWriteFile` at `0x14000297d`
- `FLTMGR!FltSetInformationFile` at `0x140002920`
- `FLTMGR!FltSetInformationFile` at `0x140002920`
- `FLTMGR!FltReadFile` at `0x1400029bc`
- `FLTMGR!FltReadFile` at `0x1400029bc`

## pseudocode

```c
NTSTATUS __fastcall VfsCopyStreamData(
        PFLT_INSTANCE InitiatingInstance,
        PFILE_OBJECT FileObject,
        PFLT_INSTANCE a3,
        PFILE_OBJECT a4,
        __int64 *FileInformation,
        PVOID Buffer,
        ULONG a7)
{
  NTSTATUS result; // eax
  PVOID v12; // rbx
  __int64 v13; // rdi
  ULONG Length; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-10h] BYREF

  Length = 0;
  ByteOffset.QuadPart = 0;
  FileInformation = (__int64 *)*FileInformation;
  result = FltSetInformationFile(a3, a4, &FileInformation, 8u, FileEndOfFileInformation);
  if ( result >= 0 )
  {
    v12 = Buffer;
    for ( ByteOffset.QuadPart = 0; ; ByteOffset.QuadPart += v13 )
    {
      result = FltReadFile(InitiatingInstance, FileObject, &ByteOffset, a7, v12, 0, &Length, 0, 0);
      if ( result == -1073741807 )
        break;
      if ( result < 0 )
        return result;
      if ( !Length )
        break;
      v13 = Length;
      result = FltWriteFile(a3, a4, &ByteOffset, Length, v12, 0, &Length, 0, 0);
      if ( result < 0 )
        return result;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400028d4  push    rbp
0x1400028d6  push    rbx
0x1400028d7  push    rsi
0x1400028d8  push    rdi
0x1400028d9  push    r12
0x1400028db  push    r13
0x1400028dd  push    r14
0x1400028df  push    r15
0x1400028e1  mov     rbp, rsp
0x1400028e4  sub     rsp, 68h
0x1400028e8  mov     rax, [rbp+FileInformation]
0x1400028ec  xor     r13d, r13d
0x1400028ef  mov     r15, r9
0x1400028f2  mov     [rbp+Length], r13d
0x1400028f6  mov     r12, r8
0x1400028f9  mov     qword ptr [rbp+ByteOffset], r13
0x1400028fd  mov     rsi, rdx
0x140002900  mov     [rsp+68h+FileInformationClass], 14h; FileInformationClass
0x140002908  mov     r10, [rax]
0x14000290b  lea     r9d, [r13+8]; Length
0x14000290f  mov     r14, rcx
0x140002912  mov     [rbp+FileInformation], r10
0x140002916  lea     r8, [rbp+FileInformation]; FileInformation
0x14000291a  mov     rdx, r15; FileObject
0x14000291d  mov     rcx, r12; Instance
0x140002920  call    cs:__imp_FltSetInformationFile
0x140002927  nop     dword ptr [rax+rax+00h]
0x14000292c  test    eax, eax
0x14000292e  js      loc_1400029D5
0x140002934  mov     rbx, [rbp+Buffer]
0x140002938  mov     qword ptr [rbp+ByteOffset], r13
0x14000293c  jmp     short loc_140002991
0x14000293e  test    eax, eax
0x140002940  js      loc_1400029D5
0x140002946  mov     eax, [rbp+Length]
0x140002949  test    eax, eax
0x14000294b  jz      loc_1400029D3
0x140002951  mov     [rsp+68h+CallbackContext], r13; CallbackContext
0x140002956  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14000295a  mov     [rsp+68h+CallbackRoutine], r13; CallbackRoutine
0x14000295f  mov     edi, eax
0x140002961  mov     r9d, eax; Length
0x140002964  mov     rdx, r15; FileObject
0x140002967  lea     rax, [rbp+Length]
0x14000296b  mov     rcx, r12; InitiatingInstance
0x14000296e  mov     [rsp+68h+BytesWritten], rax; BytesWritten
0x140002973  mov     [rsp+68h+Flags], r13d; Flags
0x140002978  mov     qword ptr [rsp+68h+FileInformationClass], rbx; Buffer
0x14000297d  call    cs:__imp_FltWriteFile
0x140002984  nop     dword ptr [rax+rax+00h]
0x140002989  test    eax, eax
0x14000298b  js      short loc_1400029D5
0x14000298d  add     qword ptr [rbp+ByteOffset], rdi
0x140002991  mov     r9d, [rbp+arg_30]; Length
0x140002995  lea     rax, [rbp+Length]
0x140002999  mov     [rsp+68h+CallbackContext], r13; CallbackContext
0x14000299e  lea     r8, [rbp+ByteOffset]; ByteOffset
0x1400029a2  mov     [rsp+68h+CallbackRoutine], r13; CallbackRoutine
0x1400029a7  mov     rdx, rsi; FileObject
0x1400029aa  mov     [rsp+68h+BytesWritten], rax; BytesRead
0x1400029af  mov     rcx, r14; InitiatingInstance
0x1400029b2  mov     [rsp+68h+Flags], r13d; Flags
0x1400029b7  mov     qword ptr [rsp+68h+FileInformationClass], rbx; Buffer
0x1400029bc  call    cs:__imp_FltReadFile
0x1400029c3  nop     dword ptr [rax+rax+00h]
0x1400029c8  cmp     eax, 0C0000011h
0x1400029cd  jnz     loc_14000293E
0x1400029d3  xor     eax, eax
0x1400029d5  add     rsp, 68h
0x1400029d9  pop     r15
0x1400029db  pop     r14
0x1400029dd  pop     r13
0x1400029df  pop     r12
0x1400029e1  pop     rdi
0x1400029e2  pop     rsi
0x1400029e3  pop     rbx
0x1400029e4  pop     rbp
0x1400029e5  retn
```
