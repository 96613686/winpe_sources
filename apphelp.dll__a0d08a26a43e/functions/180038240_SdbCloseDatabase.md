# SdbCloseDatabase

- ea: `0x180038240`
- end: `0x180038472`
- name: `SdbCloseDatabase`
- size: `562`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180001730`
- `0x180037b2c`
- `0x180038240`
- `0x18003f690`
- `0x180040650`

## callees

- `0x18000b510`
- `0x18000ecc0`
- `0x18000f114`
- `0x18000f150`
- `0x180015e8c`
- `0x180018f20`
- `0x180038240`
- `0x18003cbb8`
- `0x18003cf80`
- `0x18003f610`
- `0x18003fc80`
- `0x1800402a0`
- `0x1800407e0`
- `0x1800408c4`

## import_xrefs

- `ntdll!NtClose` at `0x1800383e1`
- `ntdll!NtClose` at `0x1800383e1`

## string_xrefs

- `0x1800382eb`: `Failed to read a string`
- `0x1800382dc`: `Failed to write stringtable item`
- `0x180038311`: `Failed to write end list tag for the string table`
- `0x1800383be`: `SdbpWriteDatabase failed`

## pseudocode

```c
__int64 __fastcall SdbCloseDatabase(_QWORD *a1)
{
  __int64 v2; // rcx
  unsigned int FirstTag; // edi
  unsigned int v4; // esi
  __int64 StringTagPtr; // rax
  __int64 i; // rdi
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  void *FileHandle; // rax
  NTSTATUS v11; // eax

  if ( !*((_DWORD *)a1 + 4) )
    goto LABEL_37;
  v2 = a1[330];
  if ( !v2 )
    goto LABEL_37;
  FirstTag = SdbFindFirstTag(v2, 0, 34817);
  if ( !FirstTag )
    goto LABEL_37;
  v4 = SdbBeginWriteListTag(a1, 30721);
  while ( FirstTag )
  {
    StringTagPtr = SdbGetStringTagPtr(a1[330], FirstTag);
    if ( !StringTagPtr )
    {
      AslLogCallPrintf(1, "SdbCloseDatabase", 1589, "Failed to read a string");
      break;
    }
    if ( !(unsigned int)SdbWriteStringTagDirect(a1, 34817, StringTagPtr) )
    {
      AslLogCallPrintf(1, "SdbCloseDatabase", 1594, "Failed to write stringtable item");
      break;
    }
    FirstTag = SdbFindNextTag(a1[330], 0, FirstTag);
  }
  if ( !(unsigned int)SdbEndWriteListTag(a1, v4) )
  {
    AslLogCallPrintf(1, "SdbCloseDatabase", 1602, "Failed to write end list tag for the string table");
  }
  else
  {
LABEL_37:
    if ( *((_DWORD *)a1 + 4) )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 659); i = (unsigned int)(i + 1) )
      {
        if ( !(unsigned int)SdbpSortIndex(a1, LODWORD(a1[5 * i + 6])) )
        {
          AslLogCallPrintf(1, "SdbCloseDatabase", 1616, "Failed to sort index");
          break;
        }
      }
    }
  }
  v7 = a1[330];
  if ( v7 )
  {
    SdbCloseDatabase(v7);
    a1[330] = 0;
  }
  if ( a1[331] )
  {
    AslHashFree();
    a1[331] = 0;
  }
  v8 = a1[1];
  if ( v8 )
  {
    if ( *((_DWORD *)a1 + 4) && *a1 )
    {
      if ( !(unsigned int)SdbpWriteDatabase(a1) )
        AslLogCallPrintf(1, "SdbCloseDatabase", 1642, "SdbpWriteDatabase failed");
      FileHandle = (void *)AslFileMappingGetFileHandle(*a1, v9);
      v11 = NtClose(FileHandle);
      if ( v11 < 0 )
        AslLogCallPrintf(1, "SdbCloseDatabase", 1650, "Failed to close sdb file handle [%x]", v11);
      AslFree(NtCurrentPeb()->ProcessHeap, a1[1]);
      goto LABEL_33;
    }
    if ( (a1[3] & 9) == 9 )
    {
      AslFree(NtCurrentPeb()->ProcessHeap, v8);
      *((_DWORD *)a1 + 5) = 0;
LABEL_33:
      a1[1] = 0;
    }
  }
  AslFileMappingDelete(*a1);
  return AslFree(NtCurrentPeb()->ProcessHeap, a1);
}

```

## disassembly

```asm
0x180038240  push    rbx
0x180038242  push    rsi
0x180038243  push    rdi
0x180038244  push    r14
0x180038246  push    r15
0x180038248  sub     rsp, 30h
0x18003824c  cmp     dword ptr [rcx+10h], 0
0x180038250  lea     r15, aSdbclosedataba_1; "SdbCloseDatabase"
0x180038257  mov     rbx, rcx
0x18003825a  mov     r14d, 1
0x180038260  jz      loc_180038320
0x180038266  mov     rcx, [rcx+0A50h]
0x18003826d  test    rcx, rcx
0x180038270  jz      loc_180038320
0x180038276  xor     edx, edx
0x180038278  mov     r8d, 8801h
0x18003827e  call    SdbFindFirstTag
0x180038283  mov     edi, eax
0x180038285  test    eax, eax
0x180038287  jz      loc_180038320
0x18003828d  mov     edx, 7801h
0x180038292  mov     rcx, rbx
0x180038295  call    SdbBeginWriteListTag
0x18003829a  mov     esi, eax
0x18003829c  test    edi, edi
0x18003829e  jz      short loc_180038303
0x1800382a0  mov     rcx, [rbx+0A50h]
0x1800382a7  mov     edx, edi
0x1800382a9  call    SdbGetStringTagPtr
0x1800382ae  test    rax, rax
0x1800382b1  jz      short loc_1800382EB
0x1800382b3  mov     edx, 8801h
0x1800382b8  mov     r8, rax
0x1800382bb  mov     rcx, rbx
0x1800382be  call    SdbWriteStringTagDirect
0x1800382c3  test    eax, eax
0x1800382c5  jz      short loc_1800382DC
0x1800382c7  mov     rcx, [rbx+0A50h]
0x1800382ce  mov     r8d, edi
0x1800382d1  xor     edx, edx
0x1800382d3  call    SdbFindNextTag
0x1800382d8  mov     edi, eax
0x1800382da  jmp     short loc_18003829C
0x1800382dc  lea     r9, aFailedToWriteS_0; "Failed to write stringtable item"
0x1800382e3  mov     r8d, 63Ah
0x1800382e9  jmp     short loc_1800382F8
0x1800382eb  lea     r9, aFailedToReadAS; "Failed to read a string"
0x1800382f2  mov     r8d, 635h
0x1800382f8  mov     rdx, r15
0x1800382fb  mov     ecx, r14d
0x1800382fe  call    AslLogCallPrintf
0x180038303  mov     edx, esi
0x180038305  mov     rcx, rbx
0x180038308  call    SdbEndWriteListTag
0x18003830d  test    eax, eax
0x18003830f  jnz     short loc_180038320
0x180038311  lea     r9, aFailedToWriteE; "Failed to write end list tag for the st"...
0x180038318  mov     r8d, 642h
0x18003831e  jmp     short loc_180038356
0x180038320  cmp     dword ptr [rbx+10h], 0
0x180038324  jz      short loc_180038361
0x180038326  xor     edi, edi
0x180038328  cmp     edi, [rbx+0A4Ch]
0x18003832e  jnb     short loc_180038361
0x180038330  lea     rdx, [rdi+rdi*4]
0x180038334  mov     rcx, rbx
0x180038337  mov     edx, [rbx+rdx*8+30h]
0x18003833b  call    SdbpSortIndex
0x180038340  test    eax, eax
0x180038342  jz      short loc_180038349
0x180038344  add     edi, r14d
0x180038347  jmp     short loc_180038328
0x180038349  lea     r9, aFailedToSortIn; "Failed to sort index"
0x180038350  mov     r8d, 650h
0x180038356  mov     rdx, r15
0x180038359  mov     ecx, r14d
0x18003835c  call    AslLogCallPrintf
0x180038361  mov     rcx, [rbx+0A50h]
0x180038368  test    rcx, rcx
0x18003836b  jz      short loc_18003837D
0x18003836d  call    SdbCloseDatabase
0x180038372  mov     qword ptr [rbx+0A50h], 0
0x18003837d  mov     rcx, [rbx+0A58h]
0x180038384  test    rcx, rcx
0x180038387  jz      short loc_180038399
0x180038389  call    AslHashFree
0x18003838e  mov     qword ptr [rbx+0A58h], 0
0x180038399  mov     rdx, [rbx+8]
0x18003839d  test    rdx, rdx
0x1800383a0  jz      loc_18003844A
0x1800383a6  cmp     dword ptr [rbx+10h], 0
0x1800383aa  jz      short loc_18003841F
0x1800383ac  cmp     qword ptr [rbx], 0
0x1800383b0  jz      short loc_18003841F
0x1800383b2  mov     rcx, rbx
0x1800383b5  call    SdbpWriteDatabase
0x1800383ba  test    eax, eax
0x1800383bc  jnz     short loc_1800383D6
0x1800383be  lea     r9, aSdbpwritedatab_0; "SdbpWriteDatabase failed"
0x1800383c5  mov     r8d, 66Ah
0x1800383cb  mov     rdx, r15
0x1800383ce  mov     ecx, r14d
0x1800383d1  call    AslLogCallPrintf
0x1800383d6  mov     rcx, [rbx]
0x1800383d9  call    AslFileMappingGetFileHandle
0x1800383de  mov     rcx, rax; Handle
0x1800383e1  call    cs:__imp_NtClose
0x1800383e7  test    eax, eax
0x1800383e9  jns     short loc_180038407
0x1800383eb  lea     r9, aFailedToCloseS; "Failed to close sdb file handle [%x]"
0x1800383f2  mov     [rsp+58h+var_38], eax
0x1800383f6  mov     r8d, 672h
0x1800383fc  mov     rdx, r15
0x1800383ff  mov     ecx, r14d
0x180038402  call    AslLogCallPrintf
0x180038407  mov     rcx, gs:60h
0x180038410  mov     rdx, [rbx+8]
0x180038414  mov     rcx, [rcx+30h]
0x180038418  call    AslFree
0x18003841d  jmp     short loc_180038442
0x18003841f  mov     eax, [rbx+18h]
0x180038422  and     eax, 9
0x180038425  cmp     al, 9
0x180038427  jnz     short loc_18003844A
0x180038429  mov     rcx, gs:60h
0x180038432  mov     rcx, [rcx+30h]
0x180038436  call    AslFree
0x18003843b  mov     dword ptr [rbx+14h], 0
0x180038442  mov     qword ptr [rbx+8], 0
0x18003844a  mov     rcx, [rbx]
0x18003844d  call    AslFileMappingDelete
0x180038452  mov     rcx, gs:60h
0x18003845b  mov     rdx, rbx
0x18003845e  mov     rcx, [rcx+30h]
0x180038462  add     rsp, 30h
0x180038466  pop     r15
0x180038468  pop     r14
0x18003846a  pop     rdi
0x18003846b  pop     rsi
0x18003846c  pop     rbx
0x18003846d  jmp     AslFree
```
