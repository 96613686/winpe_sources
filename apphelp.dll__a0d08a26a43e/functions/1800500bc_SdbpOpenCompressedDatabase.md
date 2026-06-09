# SdbpOpenCompressedDatabase

- ea: `0x1800500bc`
- end: `0x180050241`
- name: `SdbpOpenCompressedDatabase`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002f60`

## callees

- `0x18000f114`
- `0x1800160c0`
- `0x180018f20`
- `0x180047d58`
- `0x1800500bc`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180050171`
- `ntdll!RtlAllocateHeap` at `0x180050171`

## string_xrefs

- `0x1800500f1`: `SdbpOpenCompressedDatabase`
- `0x1800501c6`: `SdbpOpenCompressedDatabase`
- `0x180050146`: `SDB compression algorithm does not match callback algorithm.`
- `0x18005012c`: `SDB is not compressed`
- `0x18005017f`: `SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory`

## pseudocode

```c
__int64 __fastcall SdbpOpenCompressedDatabase(_QWORD *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // edi
  _DWORD *v4; // rbx
  __int64 v7; // rbp
  _DWORD *v8; // rcx
  PVOID Heap; // r14
  __int64 result; // rax
  _DWORD *v11; // rax
  unsigned int v12; // [rsp+78h] [rbp+10h] BYREF
  int v13; // [rsp+7Ch] [rbp+14h]

  v13 = HIDWORD(a2);
  v3 = 0;
  v4 = 0;
  v12 = 0;
  if ( !g_ExpandCallback )
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 175, "No expand callback method set. Cannot expand ZDB file.");
    goto LABEL_16;
  }
  v7 = *a1;
  if ( *(_DWORD *)(*a1 + 20LL) >= 0x14u )
  {
    v8 = *(_DWORD **)(v7 + 8);
    if ( v8[2] == 1717724282 )
    {
      if ( v8[3] == g_ExpectedAlgorithm )
      {
        v12 = v8[4];
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
        if ( Heap )
        {
          if ( (unsigned int)((__int64 (__fastcall *)(PVOID, unsigned int *, __int64, _QWORD))g_ExpandCallback)(
                               Heap,
                               &v12,
                               *(_QWORD *)(v7 + 8) + 20LL,
                               (unsigned int)(*(_DWORD *)(v7 + 20) - 20)) )
          {
            v11 = SdbpOpenDatabaseInMemory((__int64)Heap, v12, a3);
            v4 = v11;
            if ( v11 )
            {
              v11[6] |= 0xCu;
              v3 = 1;
              v12 = 0;
              goto LABEL_16;
            }
          }
          else
          {
            AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 221, "Expand callback failed to expand SDB");
          }
          AslFree(NtCurrentPeb()->ProcessHeap, Heap);
          v12 = 0;
          if ( v4 )
          {
            SdbCloseDatabaseRead(v4);
            v4 = 0;
          }
        }
        else
        {
          AslLogCallPrintf(
            1,
            "SdbpOpenCompressedDatabase",
            211,
            "SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory");
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          "SdbpOpenCompressedDatabase",
          192,
          "SDB compression algorithm does not match callback algorithm.");
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 187, "SDB is not compressed");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 180, "SDB file too small to be valid");
  }
LABEL_16:
  SdbCloseDatabaseRead(*a1);
  result = v3;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x1800500bc  mov     [rsp+arg_8], rdx
0x1800500c1  push    rbx
0x1800500c2  push    rbp
0x1800500c3  push    rsi
0x1800500c4  push    rdi
0x1800500c5  push    r14
0x1800500c7  push    r15
0x1800500c9  sub     rsp, 38h
0x1800500cd  xor     edi, edi
0x1800500cf  xor     ebx, ebx
0x1800500d1  cmp     cs:g_ExpandCallback, rbx
0x1800500d8  mov     r15d, r8d
0x1800500db  mov     rsi, rcx
0x1800500de  mov     dword ptr [rsp+68h+arg_8], edi
0x1800500e2  jnz     short loc_180050107
0x1800500e4  lea     r9, aNoExpandCallba; "No expand callback method set. Cannot e"...
0x1800500eb  mov     r8d, 0AFh
0x1800500f1  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x1800500f8  mov     ecx, 1
0x1800500fd  call    AslLogCallPrintf
0x180050102  jmp     loc_1800501FD
0x180050107  mov     rbp, [rcx]
0x18005010a  cmp     dword ptr [rbp+14h], 14h
0x18005010e  jnb     short loc_18005011F
0x180050110  lea     r9, aSdbFileTooSmal; "SDB file too small to be valid"
0x180050117  mov     r8d, 0B4h
0x18005011d  jmp     short loc_1800500F1
0x18005011f  mov     rcx, [rbp+8]
0x180050123  cmp     dword ptr [rcx+8], 6662647Ah
0x18005012a  jz      short loc_18005013B
0x18005012c  lea     r9, aSdbIsNotCompre; "SDB is not compressed"
0x180050133  mov     r8d, 0BBh
0x180050139  jmp     short loc_1800500F1
0x18005013b  mov     eax, cs:g_ExpectedAlgorithm
0x180050141  cmp     [rcx+0Ch], eax
0x180050144  jz      short loc_180050155
0x180050146  lea     r9, aSdbCompression; "SDB compression algorithm does not matc"...
0x18005014d  mov     r8d, 0C0h
0x180050153  jmp     short loc_1800500F1
0x180050155  mov     eax, [rcx+10h]
0x180050158  mov     edx, 8; Flags
0x18005015d  mov     dword ptr [rsp+68h+arg_8], eax
0x180050161  mov     r8d, eax; Size
0x180050164  mov     rcx, gs:60h
0x18005016d  mov     rcx, [rcx+30h]; HeapHandle
0x180050171  call    cs:__imp_RtlAllocateHeap
0x180050177  mov     r14, rax
0x18005017a  test    rax, rax
0x18005017d  jnz     short loc_180050191
0x18005017f  lea     r9, aSdbpopencompre_1; "SdbpOpenCompressedDatabase failed to al"...
0x180050186  mov     r8d, 0D3h
0x18005018c  jmp     loc_1800500F1
0x180050191  mov     r9d, [rbp+14h]
0x180050195  lea     rdx, [rsp+68h+arg_8]
0x18005019a  mov     r8, [rbp+8]
0x18005019e  sub     r9d, 14h
0x1800501a2  mov     rax, cs:g_ExpandCallback
0x1800501a9  add     r8, 14h
0x1800501ad  mov     rcx, r14
0x1800501b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501b5  test    eax, eax
0x1800501b7  jnz     short loc_180050217
0x1800501b9  lea     r9, aExpandCallback; "Expand callback failed to expand SDB"
0x1800501c0  mov     r8d, 0DDh
0x1800501c6  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x1800501cd  lea     ecx, [rax+1]
0x1800501d0  call    AslLogCallPrintf
0x1800501d5  mov     rcx, gs:60h
0x1800501de  mov     rdx, r14
0x1800501e1  mov     rcx, [rcx+30h]
0x1800501e5  call    AslFree
0x1800501ea  mov     dword ptr [rsp+68h+arg_8], edi
0x1800501ee  test    rbx, rbx
0x1800501f1  jz      short loc_1800501FD
0x1800501f3  mov     rcx, rbx
0x1800501f6  call    SdbCloseDatabaseRead
0x1800501fb  xor     ebx, ebx
0x1800501fd  mov     rcx, [rsi]
0x180050200  call    SdbCloseDatabaseRead
0x180050205  mov     eax, edi
0x180050207  mov     [rsi], rbx
0x18005020a  add     rsp, 38h
0x18005020e  pop     r15
0x180050210  pop     r14
0x180050212  pop     rdi
0x180050213  pop     rsi
0x180050214  pop     rbp
0x180050215  pop     rbx
0x180050216  retn
0x180050217  mov     edx, dword ptr [rsp+68h+arg_8]
0x18005021b  mov     r8d, r15d
0x18005021e  mov     rcx, r14
0x180050221  call    SdbpOpenDatabaseInMemory
0x180050226  mov     rbx, rax
0x180050229  test    rax, rax
0x18005022c  jz      short loc_1800501D5
0x18005022e  or      dword ptr [rax+18h], 0Ch
0x180050232  mov     edi, 1
0x180050237  mov     dword ptr [rsp+68h+arg_8], 0
0x18005023f  jmp     short loc_1800501FD
```
