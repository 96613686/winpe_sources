# SdbpOpenCompressedDatabase

- ea: `0x1801234f4`
- end: `0x180123679`
- name: `SdbpOpenCompressedDatabase`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180119160`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x180118ad4`
- `0x18011a8b8`
- `0x1801234f4`
- `0x180130010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1801235a9`
- `ntdll!RtlAllocateHeap` at `0x1801235a9`

## string_xrefs

- `0x180123564`: `SDB is not compressed`
- `0x180123529`: `SdbpOpenCompressedDatabase`
- `0x1801235fe`: `SdbpOpenCompressedDatabase`
- `0x1801235b7`: `SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory`
- `0x18012357e`: `SDB compression algorithm does not match callback algorithm.`

## pseudocode

```c
__int64 __fastcall SdbpOpenCompressedDatabase(_QWORD *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // edi
  _DWORD *v4; // rbx
  const char *v7; // r9
  int v8; // r8d
  __int64 v9; // rbp
  _DWORD *v10; // rcx
  PVOID Heap; // r14
  __int64 result; // rax
  _DWORD *v13; // rax
  unsigned int v14; // [rsp+78h] [rbp+10h] BYREF
  int v15; // [rsp+7Ch] [rbp+14h]

  v15 = HIDWORD(a2);
  v3 = 0;
  v4 = 0;
  v14 = 0;
  if ( !g_ExpandCallback )
  {
    v7 = "No expand callback method set. Cannot expand ZDB file.";
    v8 = 175;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenCompressedDatabase", v8, (_DWORD)v7);
    goto LABEL_16;
  }
  v9 = *a1;
  if ( *(_DWORD *)(*a1 + 20LL) < 0x14u )
  {
    v7 = "SDB file too small to be valid";
    v8 = 180;
    goto LABEL_3;
  }
  v10 = *(_DWORD **)(v9 + 8);
  if ( v10[2] != 1717724282 )
  {
    v7 = "SDB is not compressed";
    v8 = 187;
    goto LABEL_3;
  }
  if ( v10[3] != g_ExpectedAlgorithm )
  {
    v7 = "SDB compression algorithm does not match callback algorithm.";
    v8 = 192;
    goto LABEL_3;
  }
  v14 = v10[4];
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v14);
  if ( !Heap )
  {
    v7 = "SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory";
    v8 = 211;
    goto LABEL_3;
  }
  if ( (unsigned int)((__int64 (__fastcall *)(PVOID, unsigned int *, __int64, _QWORD))g_ExpandCallback)(
                       Heap,
                       &v14,
                       *(_QWORD *)(v9 + 8) + 20LL,
                       (unsigned int)(*(_DWORD *)(v9 + 20) - 20)) )
  {
    v13 = SdbpOpenDatabaseInMemory((__int64)Heap, v14, a3);
    v4 = v13;
    if ( v13 )
    {
      v13[6] |= 0xCu;
      v3 = 1;
      v14 = 0;
      goto LABEL_16;
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpOpenCompressedDatabase",
      221,
      (unsigned int)"Expand callback failed to expand SDB");
  }
  AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  v14 = 0;
  if ( v4 )
  {
    SdbCloseDatabaseRead(v4);
    v4 = 0;
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
0x1801234f4  mov     [rsp+arg_8], rdx
0x1801234f9  push    rbx
0x1801234fa  push    rbp
0x1801234fb  push    rsi
0x1801234fc  push    rdi
0x1801234fd  push    r14
0x1801234ff  push    r15
0x180123501  sub     rsp, 38h
0x180123505  xor     edi, edi
0x180123507  xor     ebx, ebx
0x180123509  cmp     cs:g_ExpandCallback, rbx
0x180123510  mov     r15d, r8d
0x180123513  mov     rsi, rcx
0x180123516  mov     dword ptr [rsp+68h+arg_8], edi
0x18012351a  jnz     short loc_18012353F
0x18012351c  lea     r9, aNoExpandCallba; "No expand callback method set. Cannot e"...
0x180123523  mov     r8d, 0AFh
0x180123529  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x180123530  mov     ecx, 1
0x180123535  call    AslLogCallPrintf
0x18012353a  jmp     loc_180123635
0x18012353f  mov     rbp, [rcx]
0x180123542  cmp     dword ptr [rbp+14h], 14h
0x180123546  jnb     short loc_180123557
0x180123548  lea     r9, aSdbFileTooSmal; "SDB file too small to be valid"
0x18012354f  mov     r8d, 0B4h
0x180123555  jmp     short loc_180123529
0x180123557  mov     rcx, [rbp+8]
0x18012355b  cmp     dword ptr [rcx+8], 6662647Ah
0x180123562  jz      short loc_180123573
0x180123564  lea     r9, aSdbIsNotCompre; "SDB is not compressed"
0x18012356b  mov     r8d, 0BBh
0x180123571  jmp     short loc_180123529
0x180123573  mov     eax, cs:g_ExpectedAlgorithm
0x180123579  cmp     [rcx+0Ch], eax
0x18012357c  jz      short loc_18012358D
0x18012357e  lea     r9, aSdbCompression; "SDB compression algorithm does not matc"...
0x180123585  mov     r8d, 0C0h
0x18012358b  jmp     short loc_180123529
0x18012358d  mov     eax, [rcx+10h]
0x180123590  mov     edx, 8; Flags
0x180123595  mov     dword ptr [rsp+68h+arg_8], eax
0x180123599  mov     r8d, eax; Size
0x18012359c  mov     rcx, gs:60h
0x1801235a5  mov     rcx, [rcx+30h]; HeapHandle
0x1801235a9  call    cs:__imp_RtlAllocateHeap
0x1801235af  mov     r14, rax
0x1801235b2  test    rax, rax
0x1801235b5  jnz     short loc_1801235C9
0x1801235b7  lea     r9, aSdbpopencompre_1; "SdbpOpenCompressedDatabase failed to al"...
0x1801235be  mov     r8d, 0D3h
0x1801235c4  jmp     loc_180123529
0x1801235c9  mov     r9d, [rbp+14h]
0x1801235cd  lea     rdx, [rsp+68h+arg_8]
0x1801235d2  mov     r8, [rbp+8]
0x1801235d6  sub     r9d, 14h
0x1801235da  mov     rax, cs:g_ExpandCallback
0x1801235e1  add     r8, 14h
0x1801235e5  mov     rcx, r14
0x1801235e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801235ed  test    eax, eax
0x1801235ef  jnz     short loc_18012364F
0x1801235f1  lea     r9, aExpandCallback; "Expand callback failed to expand SDB"
0x1801235f8  mov     r8d, 0DDh
0x1801235fe  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x180123605  lea     ecx, [rax+1]
0x180123608  call    AslLogCallPrintf
0x18012360d  mov     rcx, gs:60h
0x180123616  mov     rdx, r14
0x180123619  mov     rcx, [rcx+30h]
0x18012361d  call    AslFree
0x180123622  mov     dword ptr [rsp+68h+arg_8], edi
0x180123626  test    rbx, rbx
0x180123629  jz      short loc_180123635
0x18012362b  mov     rcx, rbx
0x18012362e  call    SdbCloseDatabaseRead
0x180123633  xor     ebx, ebx
0x180123635  mov     rcx, [rsi]
0x180123638  call    SdbCloseDatabaseRead
0x18012363d  mov     eax, edi
0x18012363f  mov     [rsi], rbx
0x180123642  add     rsp, 38h
0x180123646  pop     r15
0x180123648  pop     r14
0x18012364a  pop     rdi
0x18012364b  pop     rsi
0x18012364c  pop     rbp
0x18012364d  pop     rbx
0x18012364e  retn
0x18012364f  mov     edx, dword ptr [rsp+68h+arg_8]
0x180123653  mov     r8d, r15d
0x180123656  mov     rcx, r14
0x180123659  call    SdbpOpenDatabaseInMemory
0x18012365e  mov     rbx, rax
0x180123661  test    rax, rax
0x180123664  jz      short loc_18012360D
0x180123666  or      dword ptr [rax+18h], 0Ch
0x18012366a  mov     edi, 1
0x18012366f  mov     dword ptr [rsp+68h+arg_8], 0
0x180123677  jmp     short loc_180123635
```
