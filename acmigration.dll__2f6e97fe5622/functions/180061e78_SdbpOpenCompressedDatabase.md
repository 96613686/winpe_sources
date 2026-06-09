# SdbpOpenCompressedDatabase

- ea: `0x180061e78`
- end: `0x180062005`
- name: `SdbpOpenCompressedDatabase`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005ec7c`

## callees

- `0x1800543c0`
- `0x18005e41c`
- `0x1800601c0`
- `0x180061e78`
- `0x18006a010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180061f2f`
- `ntdll!RtlAllocateHeap` at `0x180061f2f`
- `ntdll!RtlFreeHeap` at `0x180061fa5`
- `ntdll!RtlFreeHeap` at `0x180061fa5`

## string_xrefs

- `0x180061eaf`: `SdbpOpenCompressedDatabase`
- `0x180061f84`: `SdbpOpenCompressedDatabase`
- `0x180061f3d`: `SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory`
- `0x180061eea`: `SDB is not compressed`
- `0x180061f04`: `SDB compression algorithm does not match callback algorithm.`

## pseudocode

```c
__int64 __fastcall SdbpOpenCompressedDatabase(_QWORD *a1)
{
  unsigned int v1; // edi
  _DWORD *v2; // rbx
  __int64 v4; // rbp
  _DWORD *v5; // rcx
  PVOID Heap; // r14
  __int64 result; // rax
  _DWORD *v8; // rax
  unsigned int v9; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  v2 = 0;
  v9 = 0;
  if ( !g_ExpandCallback )
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 175, "No expand callback method set. Cannot expand ZDB file.");
    goto LABEL_16;
  }
  v4 = *a1;
  if ( *(_DWORD *)(*a1 + 20LL) >= 0x14u )
  {
    v5 = *(_DWORD **)(v4 + 8);
    if ( v5[2] == 1717724282 )
    {
      if ( v5[3] == g_ExpectedAlgorithm )
      {
        v9 = v5[4];
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v9);
        if ( Heap )
        {
          if ( (unsigned int)((__int64 (__fastcall *)(PVOID, unsigned int *, __int64, _QWORD))g_ExpandCallback)(
                               Heap,
                               &v9,
                               *(_QWORD *)(v4 + 8) + 20LL,
                               (unsigned int)(*(_DWORD *)(v4 + 20) - 20)) )
          {
            v8 = SdbpOpenDatabaseInMemory((__int64)Heap, v9);
            v2 = v8;
            if ( v8 )
            {
              v8[6] |= 0xCu;
              v1 = 1;
              v9 = 0;
              goto LABEL_16;
            }
          }
          else
          {
            AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 221, "Expand callback failed to expand SDB");
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          v9 = 0;
          if ( v2 )
          {
            SdbCloseDatabaseRead(v2);
            v2 = 0;
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
  result = v1;
  *a1 = v2;
  return result;
}

```

## disassembly

```asm
0x180061e78  mov     rax, rsp
0x180061e7b  mov     [rax+8], rbx
0x180061e7f  mov     [rax+10h], rbp
0x180061e83  mov     [rax+18h], r8d
0x180061e87  push    rsi
0x180061e88  push    rdi
0x180061e89  push    r14
0x180061e8b  sub     rsp, 30h
0x180061e8f  xor     edi, edi
0x180061e91  xor     ebx, ebx
0x180061e93  cmp     cs:g_ExpandCallback, rbx
0x180061e9a  mov     rsi, rcx
0x180061e9d  mov     [rax+18h], edi
0x180061ea0  jnz     short loc_180061EC5
0x180061ea2  lea     r9, aNoExpandCallba; "No expand callback method set. Cannot e"...
0x180061ea9  mov     r8d, 0AFh
0x180061eaf  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x180061eb6  mov     ecx, 1
0x180061ebb  call    AslLogCallPrintf
0x180061ec0  jmp     loc_180061FBE
0x180061ec5  mov     rbp, [rcx]
0x180061ec8  cmp     dword ptr [rbp+14h], 14h
0x180061ecc  jnb     short loc_180061EDD
0x180061ece  lea     r9, aSdbFileTooSmal; "SDB file too small to be valid"
0x180061ed5  mov     r8d, 0B4h
0x180061edb  jmp     short loc_180061EAF
0x180061edd  mov     rcx, [rbp+8]
0x180061ee1  cmp     dword ptr [rcx+8], 6662647Ah
0x180061ee8  jz      short loc_180061EF9
0x180061eea  lea     r9, aSdbIsNotCompre; "SDB is not compressed"
0x180061ef1  mov     r8d, 0BBh
0x180061ef7  jmp     short loc_180061EAF
0x180061ef9  mov     eax, cs:g_ExpectedAlgorithm
0x180061eff  cmp     [rcx+0Ch], eax
0x180061f02  jz      short loc_180061F13
0x180061f04  lea     r9, aSdbCompression; "SDB compression algorithm does not matc"...
0x180061f0b  mov     r8d, 0C0h
0x180061f11  jmp     short loc_180061EAF
0x180061f13  mov     eax, [rcx+10h]
0x180061f16  mov     edx, 8; Flags
0x180061f1b  mov     [rsp+48h+arg_10], eax
0x180061f1f  mov     r8d, eax; Size
0x180061f22  mov     rcx, gs:60h
0x180061f2b  mov     rcx, [rcx+30h]; HeapHandle
0x180061f2f  call    cs:__imp_RtlAllocateHeap
0x180061f35  mov     r14, rax
0x180061f38  test    rax, rax
0x180061f3b  jnz     short loc_180061F4F
0x180061f3d  lea     r9, aSdbpopencompre_1; "SdbpOpenCompressedDatabase failed to al"...
0x180061f44  mov     r8d, 0D3h
0x180061f4a  jmp     loc_180061EAF
0x180061f4f  mov     r9d, [rbp+14h]
0x180061f53  lea     rdx, [rsp+48h+arg_10]
0x180061f58  mov     r8, [rbp+8]
0x180061f5c  sub     r9d, 14h
0x180061f60  mov     rax, cs:g_ExpandCallback
0x180061f67  add     r8, 14h
0x180061f6b  mov     rcx, r14
0x180061f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f73  test    eax, eax
0x180061f75  jnz     short loc_180061FDE
0x180061f77  lea     r9, aExpandCallback; "Expand callback failed to expand SDB"
0x180061f7e  mov     r8d, 0DDh
0x180061f84  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x180061f8b  lea     ecx, [rax+1]
0x180061f8e  call    AslLogCallPrintf
0x180061f93  mov     rcx, gs:60h
0x180061f9c  mov     r8, r14; P
0x180061f9f  xor     edx, edx; Flags
0x180061fa1  mov     rcx, [rcx+30h]; HeapHandle
0x180061fa5  call    cs:__imp_RtlFreeHeap
0x180061fab  mov     [rsp+48h+arg_10], edi
0x180061faf  test    rbx, rbx
0x180061fb2  jz      short loc_180061FBE
0x180061fb4  mov     rcx, rbx
0x180061fb7  call    SdbCloseDatabaseRead
0x180061fbc  xor     ebx, ebx
0x180061fbe  mov     rcx, [rsi]
0x180061fc1  call    SdbCloseDatabaseRead
0x180061fc6  mov     rbp, [rsp+48h+arg_8]
0x180061fcb  mov     eax, edi
0x180061fcd  mov     [rsi], rbx
0x180061fd0  mov     rbx, [rsp+48h+arg_0]
0x180061fd5  add     rsp, 30h
0x180061fd9  pop     r14
0x180061fdb  pop     rdi
0x180061fdc  pop     rsi
0x180061fdd  retn
0x180061fde  mov     edx, [rsp+48h+arg_10]
0x180061fe2  mov     rcx, r14
0x180061fe5  call    SdbpOpenDatabaseInMemory
0x180061fea  mov     rbx, rax
0x180061fed  test    rax, rax
0x180061ff0  jz      short loc_180061F93
0x180061ff2  or      dword ptr [rax+18h], 0Ch
0x180061ff6  mov     edi, 1
0x180061ffb  mov     [rsp+48h+arg_10], 0
0x180062003  jmp     short loc_180061FBE
```
