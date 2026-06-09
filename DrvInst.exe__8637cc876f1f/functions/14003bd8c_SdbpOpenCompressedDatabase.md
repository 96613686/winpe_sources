# SdbpOpenCompressedDatabase

- ea: `0x14003bd8c`
- end: `0x14003bf11`
- name: `SdbpOpenCompressedDatabase`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140037870`

## callees

- `0x1400371e4`
- `0x140038fd8`
- `0x14003bd8c`
- `0x14003bf18`
- `0x14003c368`
- `0x140047010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14003be41`
- `ntdll!RtlAllocateHeap` at `0x14003be41`

## string_xrefs

- `0x14003bdc1`: `SdbpOpenCompressedDatabase`
- `0x14003be96`: `SdbpOpenCompressedDatabase`
- `0x14003be16`: `SDB compression algorithm does not match callback algorithm.`
- `0x14003bdfc`: `SDB is not compressed`
- `0x14003be4f`: `SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory`

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
0x14003bd8c  mov     [rsp+arg_8], rdx
0x14003bd91  push    rbx
0x14003bd92  push    rbp
0x14003bd93  push    rsi
0x14003bd94  push    rdi
0x14003bd95  push    r14
0x14003bd97  push    r15
0x14003bd99  sub     rsp, 38h
0x14003bd9d  xor     edi, edi
0x14003bd9f  xor     ebx, ebx
0x14003bda1  cmp     cs:g_ExpandCallback, rbx
0x14003bda8  mov     r15d, r8d
0x14003bdab  mov     rsi, rcx
0x14003bdae  mov     dword ptr [rsp+68h+arg_8], edi
0x14003bdb2  jnz     short loc_14003BDD7
0x14003bdb4  lea     r9, aNoExpandCallba; "No expand callback method set. Cannot e"...
0x14003bdbb  mov     r8d, 0AFh
0x14003bdc1  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x14003bdc8  mov     ecx, 1
0x14003bdcd  call    AslLogCallPrintf
0x14003bdd2  jmp     loc_14003BECD
0x14003bdd7  mov     rbp, [rcx]
0x14003bdda  cmp     dword ptr [rbp+14h], 14h
0x14003bdde  jnb     short loc_14003BDEF
0x14003bde0  lea     r9, aSdbFileTooSmal; "SDB file too small to be valid"
0x14003bde7  mov     r8d, 0B4h
0x14003bded  jmp     short loc_14003BDC1
0x14003bdef  mov     rcx, [rbp+8]
0x14003bdf3  cmp     dword ptr [rcx+8], 6662647Ah
0x14003bdfa  jz      short loc_14003BE0B
0x14003bdfc  lea     r9, aSdbIsNotCompre; "SDB is not compressed"
0x14003be03  mov     r8d, 0BBh
0x14003be09  jmp     short loc_14003BDC1
0x14003be0b  mov     eax, cs:g_ExpectedAlgorithm
0x14003be11  cmp     [rcx+0Ch], eax
0x14003be14  jz      short loc_14003BE25
0x14003be16  lea     r9, aSdbCompression; "SDB compression algorithm does not matc"...
0x14003be1d  mov     r8d, 0C0h
0x14003be23  jmp     short loc_14003BDC1
0x14003be25  mov     eax, [rcx+10h]
0x14003be28  mov     edx, 8; Flags
0x14003be2d  mov     dword ptr [rsp+68h+arg_8], eax
0x14003be31  mov     r8d, eax; Size
0x14003be34  mov     rcx, gs:60h
0x14003be3d  mov     rcx, [rcx+30h]; HeapHandle
0x14003be41  call    cs:__imp_RtlAllocateHeap
0x14003be47  mov     r14, rax
0x14003be4a  test    rax, rax
0x14003be4d  jnz     short loc_14003BE61
0x14003be4f  lea     r9, aSdbpopencompre_1; "SdbpOpenCompressedDatabase failed to al"...
0x14003be56  mov     r8d, 0D3h
0x14003be5c  jmp     loc_14003BDC1
0x14003be61  mov     r9d, [rbp+14h]
0x14003be65  lea     rdx, [rsp+68h+arg_8]
0x14003be6a  mov     r8, [rbp+8]
0x14003be6e  sub     r9d, 14h
0x14003be72  mov     rax, cs:g_ExpandCallback
0x14003be79  add     r8, 14h
0x14003be7d  mov     rcx, r14
0x14003be80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003be85  test    eax, eax
0x14003be87  jnz     short loc_14003BEE7
0x14003be89  lea     r9, aExpandCallback; "Expand callback failed to expand SDB"
0x14003be90  mov     r8d, 0DDh
0x14003be96  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x14003be9d  lea     ecx, [rax+1]
0x14003bea0  call    AslLogCallPrintf
0x14003bea5  mov     rcx, gs:60h
0x14003beae  mov     rdx, r14
0x14003beb1  mov     rcx, [rcx+30h]
0x14003beb5  call    AslFree
0x14003beba  mov     dword ptr [rsp+68h+arg_8], edi
0x14003bebe  test    rbx, rbx
0x14003bec1  jz      short loc_14003BECD
0x14003bec3  mov     rcx, rbx
0x14003bec6  call    SdbCloseDatabaseRead
0x14003becb  xor     ebx, ebx
0x14003becd  mov     rcx, [rsi]
0x14003bed0  call    SdbCloseDatabaseRead
0x14003bed5  mov     eax, edi
0x14003bed7  mov     [rsi], rbx
0x14003beda  add     rsp, 38h
0x14003bede  pop     r15
0x14003bee0  pop     r14
0x14003bee2  pop     rdi
0x14003bee3  pop     rsi
0x14003bee4  pop     rbp
0x14003bee5  pop     rbx
0x14003bee6  retn
0x14003bee7  mov     edx, dword ptr [rsp+68h+arg_8]
0x14003beeb  mov     r8d, r15d
0x14003beee  mov     rcx, r14
0x14003bef1  call    SdbpOpenDatabaseInMemory
0x14003bef6  mov     rbx, rax
0x14003bef9  test    rax, rax
0x14003befc  jz      short loc_14003BEA5
0x14003befe  or      dword ptr [rax+18h], 0Ch
0x14003bf02  mov     edi, 1
0x14003bf07  mov     dword ptr [rsp+68h+arg_8], 0
0x14003bf0f  jmp     short loc_14003BECD
```
