# SdbpWriteCompressedDatabase

- ea: `0x180050248`
- end: `0x18005049b`
- name: `SdbpWriteCompressedDatabase`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800408c4`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x18003cbb8`
- `0x180050248`
- `0x1800591b0`
- `0x18005a010`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180050328`
- `ntdll!NtWriteFile` at `0x18005040a`
- `ntdll!NtWriteFile` at `0x180050328`
- `ntdll!NtWriteFile` at `0x18005040a`
- `ntdll!RtlAllocateHeap` at `0x180050377`
- `ntdll!RtlAllocateHeap` at `0x180050377`

## string_xrefs

- `0x180050343`: `SdbpWriteCompressedDatabase`
- `0x1800503c3`: `SdbpWriteCompressedDatabase`
- `0x180050425`: `SdbpWriteCompressedDatabase`
- `0x180050470`: `SdbpWriteCompressedDatabase`
- `0x180050293`: `Compress callback was not set. Unable to compress SDB.`
- `0x180050332`: `Failed to write the zdb header [%x]`
- `0x180050414`: `Failed to write the zdb [%x]`
- `0x1800503b6`: `Compress callback failed to compress the sdb`

## pseudocode

```c
__int64 __fastcall SdbpWriteCompressedDatabase(__int64 a1)
{
  unsigned int v1; // esi
  _QWORD *v3; // rdx
  int v4; // r8d
  void *v5; // rax
  NTSTATUS v6; // eax
  PVOID Heap; // rax
  void *v8; // rdi
  void *FileHandle; // rax
  NTSTATUS v10; // eax
  ULONG Length; // [rsp+50h] [rbp-9h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-1h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+7h] BYREF
  __int128 Buffer; // [rsp+70h] [rbp+17h] BYREF
  int v16; // [rsp+80h] [rbp+27h]

  v1 = 0;
  Length = 0;
  ByteOffset.QuadPart = 0;
  v16 = 0;
  IoStatusBlock = 0;
  Buffer = 0;
  if ( g_CompressCallback )
  {
    v3 = *(_QWORD **)(a1 + 8);
    if ( v3 && *(_QWORD *)a1 )
    {
      v4 = *(_DWORD *)(a1 + 20);
      if ( (unsigned int)(v4 - 42) > 0xFFFFFD5 )
      {
        AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 343, "Input DB was either too large or too small.");
      }
      else
      {
        *(_QWORD *)&Buffer = *v3;
        HIDWORD(Buffer) = g_ExpectedAlgorithm;
        DWORD2(Buffer) = 1717724282;
        v16 = v4;
        v5 = (void *)((__int64 (*)(void))AslFileMappingGetFileHandle)();
        v6 = NtWriteFile(v5, 0, 0, 0, &IoStatusBlock, &Buffer, 0x14u, &ByteOffset, 0);
        if ( v6 >= 0 )
        {
          ByteOffset.LowPart += 20;
          Length = *(_DWORD *)(a1 + 20);
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
          v8 = Heap;
          if ( Heap )
          {
            if ( (unsigned int)((__int64 (__fastcall *)(PVOID, ULONG *, _QWORD, _QWORD))g_CompressCallback)(
                                 Heap,
                                 &Length,
                                 *(_QWORD *)(a1 + 8),
                                 *(unsigned int *)(a1 + 20)) )
            {
              FileHandle = (void *)AslFileMappingGetFileHandle(*(_QWORD *)a1);
              v10 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, v8, Length, &ByteOffset, 0);
              if ( v10 >= 0 )
                v1 = 1;
              else
                AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 405, "Failed to write the zdb [%x]", v10);
            }
            else
            {
              AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 386, "Compress callback failed to compress the sdb");
            }
            AslFree(NtCurrentPeb()->ProcessHeap, v8);
          }
          else
          {
            AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 376, "Failed to allocate zdb buffer.");
          }
        }
        else
        {
          AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 367, "Failed to write the zdb header [%x]", v6);
        }
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 337, "Input DB was not in a valid state.");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpWriteCompressedDatabase", 330, "Compress callback was not set. Unable to compress SDB.");
  }
  return v1;
}

```

## disassembly

```asm
0x180050248  push    rbp
0x18005024a  push    rbx
0x18005024b  push    rsi
0x18005024c  push    rdi
0x18005024d  lea     rbp, [rsp-3Fh]
0x180050252  sub     rsp, 98h
0x180050259  mov     rax, cs:__security_cookie
0x180050260  xor     rax, rsp
0x180050263  mov     [rbp+57h+var_28], rax
0x180050267  xor     esi, esi
0x180050269  mov     [rbp+57h+var_60], 0
0x180050270  xor     eax, eax
0x180050272  mov     qword ptr [rbp+57h+var_58], rsi
0x180050276  cmp     cs:g_CompressCallback, rax
0x18005027d  xorps   xmm0, xmm0
0x180050280  xorps   xmm1, xmm1
0x180050283  mov     [rbp+57h+var_30], eax
0x180050286  mov     rbx, rcx
0x180050289  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18005028d  movups  [rbp+57h+var_40], xmm1
0x180050291  jnz     short loc_1800502A5
0x180050293  lea     r9, aCompressCallba; "Compress callback was not set. Unable t"...
0x18005029a  mov     r8d, 14Ah
0x1800502a0  jmp     loc_180050470
0x1800502a5  mov     rdx, [rcx+8]
0x1800502a9  test    rdx, rdx
0x1800502ac  jz      loc_180050463
0x1800502b2  mov     rcx, [rcx]
0x1800502b5  test    rcx, rcx
0x1800502b8  jz      loc_180050463
0x1800502be  mov     r8d, [rbx+14h]
0x1800502c2  lea     eax, [r8-2Ah]
0x1800502c6  cmp     eax, 0FFFFFD5h
0x1800502cb  ja      loc_180050454
0x1800502d1  mov     eax, [rdx]
0x1800502d3  mov     dword ptr [rbp+57h+var_40], eax
0x1800502d6  mov     eax, [rdx+4]
0x1800502d9  mov     dword ptr [rbp+57h+var_40+4], eax
0x1800502dc  mov     eax, cs:g_ExpectedAlgorithm
0x1800502e2  mov     dword ptr [rbp+57h+var_40+0Ch], eax
0x1800502e5  mov     dword ptr [rbp+57h+var_40+8], 6662647Ah
0x1800502ec  mov     [rbp+57h+var_30], r8d
0x1800502f0  call    AslFileMappingGetFileHandle
0x1800502f5  mov     rcx, rax; FileHandle
0x1800502f8  mov     [rsp+0B0h+Key], rsi; Key
0x1800502fd  lea     rax, [rbp+57h+var_58]
0x180050301  xor     r9d, r9d; ApcContext
0x180050304  mov     [rsp+0B0h+ByteOffset], rax; ByteOffset
0x180050309  xor     r8d, r8d; ApcRoutine
0x18005030c  lea     rax, [rbp+57h+var_40]
0x180050310  mov     [rsp+0B0h+Length], 14h; Length
0x180050318  mov     [rsp+0B0h+Buffer], rax; Buffer
0x18005031d  xor     edx, edx; Event
0x18005031f  lea     rax, [rbp+57h+var_50]
0x180050323  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x180050328  call    cs:__imp_NtWriteFile
0x18005032e  test    eax, eax
0x180050330  jns     short loc_180050359
0x180050332  lea     r9, aFailedToWriteT; "Failed to write the zdb header [%x]"
0x180050339  mov     dword ptr [rsp+0B0h+IoStatusBlock], eax
0x18005033d  mov     r8d, 16Fh
0x180050343  lea     rdx, aSdbpwritecompr; "SdbpWriteCompressedDatabase"
0x18005034a  mov     ecx, 1
0x18005034f  call    AslLogCallPrintf
0x180050354  jmp     loc_180050481
0x180050359  add     dword ptr [rbp+57h+var_58], 14h
0x18005035d  mov     edx, 8; Flags
0x180050362  mov     r8d, [rbx+14h]; Size
0x180050366  mov     [rbp+57h+var_60], r8d
0x18005036a  mov     rcx, gs:60h
0x180050373  mov     rcx, [rcx+30h]; HeapHandle
0x180050377  call    cs:__imp_RtlAllocateHeap
0x18005037d  mov     rdi, rax
0x180050380  test    rax, rax
0x180050383  jnz     short loc_180050397
0x180050385  lea     r9, aFailedToAlloca_7; "Failed to allocate zdb buffer."
0x18005038c  mov     r8d, 178h
0x180050392  jmp     loc_180050470
0x180050397  mov     r9d, [rbx+14h]
0x18005039b  lea     rdx, [rbp+57h+var_60]
0x18005039f  mov     r8, [rbx+8]
0x1800503a3  mov     rcx, rdi
0x1800503a6  mov     rax, cs:g_CompressCallback
0x1800503ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503b2  test    eax, eax
0x1800503b4  jnz     short loc_1800503D4
0x1800503b6  lea     r9, aCompressCallba_0; "Compress callback failed to compress th"...
0x1800503bd  mov     r8d, 182h
0x1800503c3  lea     rdx, aSdbpwritecompr; "SdbpWriteCompressedDatabase"
0x1800503ca  lea     ecx, [rax+1]
0x1800503cd  call    AslLogCallPrintf
0x1800503d2  jmp     short loc_18005043D
0x1800503d4  mov     rcx, [rbx]
0x1800503d7  call    AslFileMappingGetFileHandle
0x1800503dc  mov     rcx, rax; FileHandle
0x1800503df  mov     [rsp+0B0h+Key], rsi; Key
0x1800503e4  lea     rax, [rbp+57h+var_58]
0x1800503e8  xor     r9d, r9d; ApcContext
0x1800503eb  mov     [rsp+0B0h+ByteOffset], rax; ByteOffset
0x1800503f0  xor     r8d, r8d; ApcRoutine
0x1800503f3  mov     eax, [rbp+57h+var_60]
0x1800503f6  xor     edx, edx; Event
0x1800503f8  mov     [rsp+0B0h+Length], eax; Length
0x1800503fc  lea     rax, [rbp+57h+var_50]
0x180050400  mov     [rsp+0B0h+Buffer], rdi; Buffer
0x180050405  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x18005040a  call    cs:__imp_NtWriteFile
0x180050410  test    eax, eax
0x180050412  jns     short loc_180050438
0x180050414  lea     r9, aFailedToWriteT_1; "Failed to write the zdb [%x]"
0x18005041b  mov     dword ptr [rsp+0B0h+IoStatusBlock], eax
0x18005041f  mov     r8d, 195h
0x180050425  lea     rdx, aSdbpwritecompr; "SdbpWriteCompressedDatabase"
0x18005042c  mov     ecx, 1
0x180050431  call    AslLogCallPrintf
0x180050436  jmp     short loc_18005043D
0x180050438  mov     esi, 1
0x18005043d  mov     rcx, gs:60h
0x180050446  mov     rdx, rdi
0x180050449  mov     rcx, [rcx+30h]
0x18005044d  call    AslFree
0x180050452  jmp     short loc_180050481
0x180050454  lea     r9, aInputDbWasEith; "Input DB was either too large or too sm"...
0x18005045b  mov     r8d, 157h
0x180050461  jmp     short loc_180050470
0x180050463  lea     r9, aInputDbWasNotI; "Input DB was not in a valid state."
0x18005046a  mov     r8d, 151h
0x180050470  lea     rdx, aSdbpwritecompr; "SdbpWriteCompressedDatabase"
0x180050477  mov     ecx, 1
0x18005047c  call    AslLogCallPrintf
0x180050481  mov     eax, esi
0x180050483  mov     rcx, [rbp+57h+var_28]
0x180050487  xor     rcx, rsp; StackCookie
0x18005048a  call    __security_check_cookie
0x18005048f  add     rsp, 98h
0x180050496  pop     rdi
0x180050497  pop     rsi
0x180050498  pop     rbx
0x180050499  pop     rbp
0x18005049a  retn
```
