# SdbCreateMsiTransformFile

- ea: `0x180048930`
- end: `0x180048a7d`
- name: `SdbCreateMsiTransformFile`
- size: `333`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ae70`
- `0x18000f114`
- `0x180018f20`
- `0x180048930`
- `0x180049914`
- `0x18004c3a0`
- `0x18004c404`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800489d9`
- `ntdll!RtlAllocateHeap` at `0x1800489d9`

## string_xrefs

- `0x180048963`: `SdbCreateMsiTransformFile`
- `0x180048a1e`: `SdbCreateMsiTransformFile`
- `0x180048a11`: `Can't read transform bits`
- `0x180048a43`: `Can't write transform bits to disk`

## pseudocode

```c
__int64 __fastcall SdbCreateMsiTransformFile(__int64 a1, const WCHAR *a2, __int64 a3)
{
  unsigned int v4; // r14d
  __int64 v5; // rdx
  unsigned int FirstTagRef; // eax
  unsigned int v8; // edi
  ULONG TagRefDataSize; // eax
  ULONG v10; // ebx
  PVOID Heap; // rax
  void *v12; // rsi

  v4 = 0;
  v5 = *(unsigned int *)(a3 + 12);
  if ( (_DWORD)v5 )
  {
    FirstTagRef = SdbFindFirstTagRef(a1, v5, 36867);
    v8 = FirstTagRef;
    if ( FirstTagRef )
    {
      TagRefDataSize = SdbpGetTagRefDataSize(a1, FirstTagRef);
      v10 = TagRefDataSize;
      if ( TagRefDataSize == 0x20000000 )
      {
        AslLogCallPrintf(1, "SdbCreateMsiTransformFile", 1347, "File bits found invalid sized tag 0x%x", v8);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TagRefDataSize);
        v12 = Heap;
        if ( Heap )
        {
          if ( (unsigned int)SdbpReadBinaryTagRef(a1, v8, Heap, v10) )
          {
            if ( SdbpWriteBufferToFile(a2, v12, v10) )
              v4 = 1;
            else
              AslLogCallPrintf(1, "SdbCreateMsiTransformFile", 1367, "Can't write transform bits to disk");
          }
          else
          {
            AslLogCallPrintf(1, "SdbCreateMsiTransformFile", 1362, "Can't read transform bits");
          }
          AslFree(NtCurrentPeb()->ProcessHeap, v12);
        }
        else
        {
          AslLogCallPrintf(1, "SdbCreateMsiTransformFile", 1354, "Failed to allocate %d bytes", v10);
        }
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbCreateMsiTransformFile", 1340, "File bits not found tag 0x%x", 0);
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbCreateMsiTransformFile", 1333, "File for transform \"%ws\" was not found", *(_QWORD *)a3);
  }
  return v4;
}

```

## disassembly

```asm
0x180048930  push    rbx
0x180048932  push    rbp
0x180048933  push    rsi
0x180048934  push    rdi
0x180048935  push    r14
0x180048937  push    r15
0x180048939  sub     rsp, 38h
0x18004893d  mov     r15, rdx
0x180048940  xor     r14d, r14d
0x180048943  mov     edx, [r8+0Ch]
0x180048947  mov     rbp, rcx
0x18004894a  test    edx, edx
0x18004894c  jnz     short loc_180048979
0x18004894e  mov     rax, [r8]
0x180048951  lea     r9, aFileForTransfo; "File for transform \"%ws\" was not foun"...
0x180048958  mov     [rsp+68h+var_48], rax
0x18004895d  mov     r8d, 535h
0x180048963  lea     rdx, aSdbcreatemsitr_0; "SdbCreateMsiTransformFile"
0x18004896a  mov     ecx, 1
0x18004896f  call    AslLogCallPrintf
0x180048974  jmp     loc_180048A6D
0x180048979  mov     r8d, 9003h
0x18004897f  call    SdbFindFirstTagRef
0x180048984  mov     edi, eax
0x180048986  test    eax, eax
0x180048988  jnz     short loc_18004899E
0x18004898a  mov     dword ptr [rsp+68h+var_48], r14d
0x18004898f  lea     r9, aFileBitsNotFou; "File bits not found tag 0x%x"
0x180048996  mov     r8d, 53Ch
0x18004899c  jmp     short loc_180048963
0x18004899e  mov     edx, edi
0x1800489a0  mov     rcx, rbp
0x1800489a3  call    SdbpGetTagRefDataSize
0x1800489a8  mov     ebx, eax
0x1800489aa  cmp     eax, 20000000h
0x1800489af  jnz     short loc_1800489C4
0x1800489b1  mov     dword ptr [rsp+68h+var_48], edi
0x1800489b5  lea     r9, aFileBitsFoundI; "File bits found invalid sized tag 0x%x"
0x1800489bc  mov     r8d, 543h
0x1800489c2  jmp     short loc_180048963
0x1800489c4  mov     rcx, gs:60h
0x1800489cd  mov     r8, rbx; Size
0x1800489d0  mov     edx, 8; Flags
0x1800489d5  mov     rcx, [rcx+30h]; HeapHandle
0x1800489d9  call    cs:__imp_RtlAllocateHeap
0x1800489df  mov     rsi, rax
0x1800489e2  test    rax, rax
0x1800489e5  jnz     short loc_1800489FD
0x1800489e7  mov     dword ptr [rsp+68h+var_48], ebx
0x1800489eb  lea     r9, aFailedToAlloca_34; "Failed to allocate %d bytes"
0x1800489f2  mov     r8d, 54Ah
0x1800489f8  jmp     loc_180048963
0x1800489fd  mov     r9d, ebx
0x180048a00  mov     r8, rsi
0x180048a03  mov     edx, edi
0x180048a05  mov     rcx, rbp
0x180048a08  call    SdbpReadBinaryTagRef
0x180048a0d  test    eax, eax
0x180048a0f  jnz     short loc_180048A31
0x180048a11  lea     r9, aCanTReadTransf; "Can't read transform bits"
0x180048a18  mov     r8d, 552h
0x180048a1e  lea     rdx, aSdbcreatemsitr_0; "SdbCreateMsiTransformFile"
0x180048a25  mov     ecx, 1
0x180048a2a  call    AslLogCallPrintf
0x180048a2f  jmp     short loc_180048A58
0x180048a31  mov     r8d, ebx; Length
0x180048a34  mov     rdx, rsi; Buffer
0x180048a37  mov     rcx, r15; SourceString
0x180048a3a  call    SdbpWriteBufferToFile
0x180048a3f  test    eax, eax
0x180048a41  jnz     short loc_180048A52
0x180048a43  lea     r9, aCanTWriteTrans; "Can't write transform bits to disk"
0x180048a4a  mov     r8d, 557h
0x180048a50  jmp     short loc_180048A1E
0x180048a52  mov     r14d, 1
0x180048a58  mov     rcx, gs:60h
0x180048a61  mov     rdx, rsi
0x180048a64  mov     rcx, [rcx+30h]
0x180048a68  call    AslFree
0x180048a6d  mov     eax, r14d
0x180048a70  add     rsp, 38h
0x180048a74  pop     r15
0x180048a76  pop     r14
0x180048a78  pop     rdi
0x180048a79  pop     rsi
0x180048a7a  pop     rbp
0x180048a7b  pop     rbx
0x180048a7c  retn
```
