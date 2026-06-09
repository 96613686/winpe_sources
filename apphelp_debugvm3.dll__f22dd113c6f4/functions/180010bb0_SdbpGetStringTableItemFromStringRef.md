# SdbpGetStringTableItemFromStringRef

- ea: `0x180010bb0`
- end: `0x180010daa`
- name: `SdbpGetStringTableItemFromStringRef`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800111b0`

## callees

- `0x18000f114`
- `0x180010bb0`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180010bfa`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180010bfa`

## string_xrefs

- `0x180010c90`: `SdbpReadMappedData`
- `0x180010d8a`: `SdbpReadMappedData`
- `0x180010ca1`: `Error reading data`
- `0x180010d7b`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbpGetStringTableItemFromStringRef(__int64 a1, int a2, _DWORD *a3, _QWORD *a4)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  unsigned int v13; // ecx
  int v14; // eax
  __int64 v15; // rax
  bool v16; // sf
  unsigned int v17; // ebx
  int *v19; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  LODWORD(v5) = 0;
  v19 = 0;
  if ( *(_DWORD *)(a1 + 16) )
  {
    if ( *(_QWORD *)(a1 + 2640) )
    {
      v4 = *(_QWORD *)(a1 + 2640);
      v12 = 6;
LABEL_6:
      v5 = (unsigned int)(v12 + a2);
      if ( (unsigned int)v5 >= 0xFFFFFFFE )
      {
        AslLogCallPrintf(
          1,
          "SdbpReadMappedData",
          855,
          "Offset and region size add up to cause an integer overflow or underflow");
      }
      else
      {
        v13 = *(_DWORD *)(v4 + 20);
        if ( v13 >= (int)v5 + 2 )
        {
          if ( *(_WORD *)(v5 + *(_QWORD *)(v4 + 8)) == 0x8801 )
          {
            v11 = 0;
            goto LABEL_10;
          }
          goto LABEL_17;
        }
        AslLogCallPrintf(
          1,
          "SdbpReadMappedData",
          860,
          "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
          v5,
          2,
          v13);
      }
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
LABEL_17:
      AslLogCallPrintf(1, "SdbpGetStringTableItemFromStringRef", 888, "Pulled out a non-stringtable item");
      v11 = -1073741788;
      goto LABEL_10;
    }
    AslLogCallPrintf(1, "SdbpGetStringTableItemFromStringRef", 838, "No stringtable in DB");
    v11 = -1073741275;
  }
  else
  {
    v10 = RtlRunOnceExecuteOnce(a1 + 2624, InitOnceGetStringTableOffset, a1, &v19);
    v11 = v10;
    if ( v10 < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbpGetStringTableItemFromStringRef",
        858,
        "RtlRunOnceExecuteOnce failed for InitOnceGetStringTableOffset [%x]",
        v10);
    }
    else
    {
      if ( v19 )
      {
        v12 = *v19;
        if ( *v19 )
        {
          v4 = a1;
          goto LABEL_6;
        }
      }
      AslLogCallPrintf(
        1,
        "SdbpGetStringTableItemFromStringRef",
        874,
        "InitOnceGetStringTableOffset succeeded but failed to find string table");
      v11 = -1073741271;
    }
  }
LABEL_10:
  v14 = 0;
  if ( v11 >= 0 )
    v14 = v5;
  *a3 = v14;
  v15 = 0;
  v16 = v11 < 0;
  v17 = ~v11;
  if ( !v16 )
    v15 = v4;
  *a4 = v15;
  return v17 >> 31;
}

```

## disassembly

```asm
0x180010bb0  mov     [rsp+arg_8], rbx
0x180010bb5  mov     [rsp+arg_10], rbp
0x180010bba  push    rsi
0x180010bbb  push    rdi
0x180010bbc  push    r12
0x180010bbe  push    r14
0x180010bc0  push    r15
0x180010bc2  sub     rsp, 40h
0x180010bc6  xor     esi, esi
0x180010bc8  xor     edi, edi
0x180010bca  mov     r14, r9
0x180010bcd  mov     r15, r8
0x180010bd0  mov     r12d, edx
0x180010bd3  mov     rbp, rcx
0x180010bd6  mov     [rsp+68h+arg_0], rsi
0x180010bdb  cmp     [rcx+10h], esi
0x180010bde  jnz     loc_180010D36
0x180010be4  add     rcx, 0A40h
0x180010beb  lea     r9, [rsp+68h+arg_0]
0x180010bf0  mov     r8, rbp
0x180010bf3  lea     rdx, InitOnceGetStringTableOffset
0x180010bfa  call    cs:__imp_RtlRunOnceExecuteOnce
0x180010c00  mov     ebx, eax
0x180010c02  test    eax, eax
0x180010c04  js      loc_180010CE7
0x180010c0a  mov     rax, [rsp+68h+arg_0]
0x180010c0f  test    rax, rax
0x180010c12  jz      loc_180010D0E
0x180010c18  mov     eax, [rax]
0x180010c1a  test    eax, eax
0x180010c1c  jz      loc_180010D0E
0x180010c22  mov     rsi, rbp
0x180010c25  lea     edi, [rax+r12]
0x180010c29  lea     eax, [rdi+2]
0x180010c2c  cmp     eax, 2
0x180010c2f  jb      short loc_180010C83
0x180010c31  mov     ecx, [rsi+14h]
0x180010c34  cmp     ecx, eax
0x180010c36  jb      loc_180010D77
0x180010c3c  mov     rax, [rsi+8]
0x180010c40  mov     edx, 8801h
0x180010c45  cmp     [rdi+rax], dx
0x180010c49  jnz     short loc_180010CBF
0x180010c4b  xor     ebx, ebx
0x180010c4d  mov     rbp, [rsp+68h+arg_10]
0x180010c55  xor     eax, eax
0x180010c57  test    ebx, ebx
0x180010c59  cmovns  eax, edi
0x180010c5c  mov     [r15], eax
0x180010c5f  xor     eax, eax
0x180010c61  test    ebx, ebx
0x180010c63  not     ebx
0x180010c65  cmovns  rax, rsi
0x180010c69  shr     ebx, 1Fh
0x180010c6c  mov     [r14], rax
0x180010c6f  mov     eax, ebx
0x180010c71  mov     rbx, [rsp+68h+arg_8]
0x180010c76  add     rsp, 40h
0x180010c7a  pop     r15
0x180010c7c  pop     r14
0x180010c7e  pop     r12
0x180010c80  pop     rdi
0x180010c81  pop     rsi
0x180010c82  retn
0x180010c83  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x180010c8a  mov     r8d, 357h
0x180010c90  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180010c97  mov     ecx, 1
0x180010c9c  call    AslLogCallPrintf
0x180010ca1  lea     r9, aErrorReadingDa; "Error reading data"
0x180010ca8  mov     r8d, 0BDFh
0x180010cae  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x180010cb5  mov     ecx, 1
0x180010cba  call    AslLogCallPrintf
0x180010cbf  lea     r9, aPulledOutANonS; "Pulled out a non-stringtable item"
0x180010cc6  mov     r8d, 378h
0x180010ccc  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x180010cd3  mov     ecx, 1
0x180010cd8  call    AslLogCallPrintf
0x180010cdd  mov     ebx, 0C0000024h
0x180010ce2  jmp     loc_180010C4D
0x180010ce7  lea     r9, aRtlrunonceexec_0; "RtlRunOnceExecuteOnce failed for InitOn"...
0x180010cee  mov     [rsp+68h+var_48], eax
0x180010cf2  mov     r8d, 35Ah
0x180010cf8  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x180010cff  mov     ecx, 1
0x180010d04  call    AslLogCallPrintf
0x180010d09  jmp     loc_180010C4D
0x180010d0e  lea     r9, aInitoncegetstr_0; "InitOnceGetStringTableOffset succeeded "...
0x180010d15  mov     r8d, 36Ah
0x180010d1b  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x180010d22  mov     ecx, 1
0x180010d27  call    AslLogCallPrintf
0x180010d2c  mov     ebx, 0C0000229h
0x180010d31  jmp     loc_180010C4D
0x180010d36  mov     rax, [rcx+0A50h]
0x180010d3d  test    rax, rax
0x180010d40  jz      short loc_180010D4F
0x180010d42  mov     rsi, rax
0x180010d45  mov     eax, 6
0x180010d4a  jmp     loc_180010C25
0x180010d4f  lea     r9, aNoStringtableI; "No stringtable in DB"
0x180010d56  mov     r8d, 346h
0x180010d5c  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x180010d63  mov     ecx, 1
0x180010d68  call    AslLogCallPrintf
0x180010d6d  mov     ebx, 0C0000225h
0x180010d72  jmp     loc_180010C4D
0x180010d77  mov     [rsp+68h+var_38], ecx
0x180010d7b  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x180010d82  mov     [rsp+68h+var_40], 2
0x180010d8a  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180010d91  mov     ecx, 1
0x180010d96  mov     [rsp+68h+var_48], edi
0x180010d9a  mov     r8d, 35Ch
0x180010da0  call    AslLogCallPrintf
0x180010da5  jmp     loc_180010CA1
```
