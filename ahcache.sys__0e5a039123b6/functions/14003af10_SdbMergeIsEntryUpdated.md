# SdbMergeIsEntryUpdated

- ea: `0x14003af10`
- end: `0x14003b2dd`
- name: `SdbMergeIsEntryUpdated`
- size: `973`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x1400040e4`
- `0x14003a6ec`

## callees

- `0x140024994`
- `0x140026170`
- `0x140026550`
- `0x14003aa68`
- `0x14003ac28`
- `0x14003ada0`
- `0x14003af10`
- `0x14003c19c`
- `0x14003c444`
- `0x14003c62c`
- `0x14003d820`
- `0x14003e1f0`
- `0x14003e364`
- `0x14003ef10`
- `0x14003f570`
- `0x14003fcf8`
- `0x14004007c`

## string_xrefs

- `0x14003b01a`: `SdbMergeIsEntryUpdated`
- `0x14003b2c2`: `SdbMergeIsEntryUpdated`

## pseudocode

```c
__int64 __fastcall SdbMergeIsEntryUpdated(void *a1, __int64 a2, void *a3, unsigned int *a4)
{
  unsigned int v6; // esi
  unsigned __int16 TagFromTagID; // ax
  unsigned __int64 i; // rdx
  unsigned __int16 *v10; // rdi
  int v12; // r15d
  unsigned int FirstTag; // r12d
  unsigned int TagFromAncestors; // eax
  unsigned int j; // eax
  unsigned int v16; // esi
  unsigned int v17; // eax
  unsigned int ParentTagFromAncestors; // eax
  unsigned int v19; // esi
  unsigned int m; // eax
  unsigned int v21; // edi
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // eax
  __int64 IndexKeyFromGUID; // rax
  unsigned int k; // eax
  unsigned int v29; // eax
  __int64 v30; // [rsp+20h] [rbp-48h]
  __int128 v31; // [rsp+30h] [rbp-38h] BYREF
  __int128 v32; // [rsp+40h] [rbp-28h]
  PCWSTR MappedTagData; // [rsp+50h] [rbp-18h]
  unsigned __int16 v34; // [rsp+B0h] [rbp+48h]
  unsigned int v35; // [rsp+B0h] [rbp+48h]
  unsigned int v37; // [rsp+D0h] [rbp+68h]

  MappedTagData = 0;
  v6 = a2;
  v31 = 0;
  v32 = 0;
  if ( !a1 || !a3 )
    return a3 != 0 ? -1073741585 : -1073741583;
  if ( !(_DWORD)a2 )
    return 3221225712LL;
  if ( !a4 )
    return 3221225714LL;
  *a4 = 0;
  TagFromTagID = SdbGetTagFromTagID(a1, a2);
  v34 = TagFromTagID;
  for ( i = 0; i < 0x24; ++i )
  {
    v10 = (unsigned __int16 *)qword_14000ADB0 + 5 * i;
    if ( *v10 == TagFromTagID )
    {
      if ( v10 )
      {
        v12 = v10[1];
        if ( (_WORD)v12 )
        {
          if ( (TagFromTagID & 0xF000) == 0x7000 )
          {
            FirstTag = SdbFindFirstTag(a1, v6, (unsigned __int16)v12);
            if ( FirstTag )
            {
              TagFromAncestors = _SdbpFindTagFromAncestors(a3, 2, 28751, 30724);
              v37 = TagFromAncestors;
              if ( TagFromAncestors )
              {
                for ( j = SdbFindFirstTag(a3, TagFromAncestors, 30723); ; j = SdbFindNextTag(a3, v37, v16) )
                {
                  v16 = j;
                  if ( !j )
                    break;
                  v17 = SdbFindFirstTag(a3, j, 14338);
                  if ( !v17 )
                    return 3221225816LL;
                  if ( v34 == (unsigned __int16)SdbReadWORDTag(a3, v17, 0) )
                  {
                    v23 = SdbFindFirstTag(a3, v16, 14339);
                    if ( !v23 )
                      return 3221225816LL;
                    if ( (_WORD)v12 == (unsigned __int16)SdbReadWORDTag(a3, v23, 0) )
                    {
                      WORD6(v31) = v12;
                      v24 = SdbFindFirstTag(a3, v16, 16406);
                      DWORD1(v32) = SdbReadDWORDTag((__int64)a3, v24, 0);
                      v25 = SdbFindFirstTag(a3, v16, 38913);
                      v35 = v25;
                      if ( !v25 )
                      {
                        AslLogCallPrintf(
                          1,
                          "SdbMergeIsEntryUpdated",
                          3139,
                          "Encountered an index without a TAG_INDEX_BITS entry 0x%08X",
                          v16);
                        return 3221225816LL;
                      }
                      LODWORD(v31) = v25;
                      v26 = v12 & 0xF000;
                      if ( v26 == 36864 )
                      {
                        if ( (unsigned int)SdbGetTagDataSize((__int64)a1, FirstTag) != 16 )
                        {
                          LODWORD(v30) = v35;
                          AslLogCallPrintf(
                            3,
                            "SdbMergeIsEntryUpdated",
                            3147,
                            "Original entry 0x%08X has bad GUID size",
                            v30);
                          return 3221226021LL;
                        }
                        MappedTagData = (PCWSTR)SdbpGetMappedTagData(a1, FirstTag);
                        IndexKeyFromGUID = SdbMakeIndexKeyFromGUID(MappedTagData);
                      }
                      else
                      {
                        if ( v26 != 0x8000 && v26 != 24576 )
                        {
                          AslLogCallPrintf(
                            1,
                            "SdbMergeIsEntryUpdated",
                            3166,
                            "Encountered a merge entry key not a string or guid %x",
                            v12);
                          return 3221225701LL;
                        }
                        MappedTagData = (PCWSTR)SdbGetStringTagPtr(a1, FirstTag);
                        IndexKeyFromGUID = SdbMakeIndexKeyFromStringEx(MappedTagData, SBYTE4(v32));
                      }
                      *((_QWORD *)&v32 + 1) = IndexKeyFromGUID;
                      for ( k = SdbpGetFirstIndexedRecord(a3, v35, IndexKeyFromGUID, &v31);
                            ;
                            k = SdbpGetNextIndexedRecord(a3, (unsigned int)v31, &v31) )
                      {
                        v21 = k;
                        if ( !k )
                          break;
                        v29 = SdbFindFirstTag(a3, k, (unsigned __int16)v12);
                        if ( v29 && SdbpMergeAreTagValuesEqual(a1, FirstTag, a3, v29) )
                          goto LABEL_39;
                      }
                      return 3221226021LL;
                    }
                    AslLogCallPrintf(
                      1,
                      "SdbMergeIsEntryUpdated",
                      3128,
                      "Encountered an index with an unexpected key for tag %x",
                      v34);
                  }
                }
              }
              else
              {
                ParentTagFromAncestors = SdbFindParentTagFromAncestors(a3, v10 + 2);
                v19 = ParentTagFromAncestors;
                if ( ParentTagFromAncestors )
                {
                  for ( m = SdbFindFirstTag(a3, ParentTagFromAncestors, *v10); ; m = SdbFindNextTag(a3, v19, v21) )
                  {
                    v21 = m;
                    if ( !m )
                      break;
                    v22 = SdbFindFirstTag(a3, m, (unsigned __int16)v12);
                    if ( SdbpMergeAreTagValuesEqual(a1, FirstTag, a3, v22) )
                    {
LABEL_39:
                      *a4 = v21;
                      return 0;
                    }
                  }
                }
              }
            }
            else
            {
              AslLogCallPrintf(3, "SdbMergeIsEntryUpdated", 3094, "Original entry 0x%08X missing merge id key", v6);
            }
          }
        }
      }
      return 3221226021LL;
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x14003af10  push    rbp
0x14003af12  push    rbx
0x14003af13  push    rsi
0x14003af14  push    rdi
0x14003af15  push    r12
0x14003af17  push    r13
0x14003af19  push    r14
0x14003af1b  push    r15
0x14003af1d  mov     rbp, rsp
0x14003af20  sub     rsp, 68h
0x14003af24  xor     eax, eax
0x14003af26  xorps   xmm0, xmm0
0x14003af29  xor     r12d, r12d
0x14003af2c  mov     [rbp+var_18], rax
0x14003af30  mov     r13, r9
0x14003af33  mov     rbx, r8
0x14003af36  mov     esi, edx
0x14003af38  mov     r14, rcx
0x14003af3b  movups  [rbp+var_38], xmm0
0x14003af3f  movups  [rbp+var_28], xmm0
0x14003af43  test    rcx, rcx
0x14003af46  jz      loc_14003B2CB
0x14003af4c  test    rbx, rbx
0x14003af4f  jz      loc_14003B2CB
0x14003af55  test    edx, edx
0x14003af57  jz      loc_14003B29D
0x14003af5d  test    r9, r9
0x14003af60  jz      loc_14003B2A7
0x14003af66  mov     [r9], r12d
0x14003af69  call    SdbGetTagFromTagID
0x14003af6e  mov     word ptr [rbp+arg_0], ax
0x14003af72  mov     edx, r12d
0x14003af75  cmp     rdx, 24h ; '$'
0x14003af79  jnb     short loc_14003AF99
0x14003af7b  lea     rcx, [rdx+rdx*4]
0x14003af7f  lea     r8, qword_14000ADB0
0x14003af86  lea     rdi, [r8+rcx*2]
0x14003af8a  cmp     [rdi], ax
0x14003af8d  jz      short loc_14003AF94
0x14003af8f  inc     rdx
0x14003af92  jmp     short loc_14003AF75
0x14003af94  test    rdi, rdi
0x14003af97  jnz     short loc_14003AFB0
0x14003af99  mov     eax, 0C0000225h
0x14003af9e  add     rsp, 68h
0x14003afa2  pop     r15
0x14003afa4  pop     r14
0x14003afa6  pop     r13
0x14003afa8  pop     r12
0x14003afaa  pop     rdi
0x14003afab  pop     rsi
0x14003afac  pop     rbx
0x14003afad  pop     rbp
0x14003afae  retn
0x14003afb0  movzx   r15d, word ptr [rdi+2]
0x14003afb5  test    r15w, r15w
0x14003afb9  jz      short loc_14003AF99
0x14003afbb  mov     ecx, 0F000h
0x14003afc0  and     ax, cx
0x14003afc3  mov     ecx, 7000h
0x14003afc8  cmp     ax, cx
0x14003afcb  jnz     short loc_14003AF99
0x14003afcd  movzx   r8d, r15w
0x14003afd1  mov     edx, esi
0x14003afd3  mov     rcx, r14
0x14003afd6  call    SdbFindFirstTag
0x14003afdb  mov     r12d, eax
0x14003afde  test    eax, eax
0x14003afe0  jz      loc_14003B2B1
0x14003afe6  mov     edx, 2
0x14003afeb  mov     r9d, 7804h
0x14003aff1  mov     r8d, 704Fh
0x14003aff7  mov     rcx, rbx
0x14003affa  call    __SdbpFindTagFromAncestors
0x14003afff  mov     [rbp+arg_20], eax
0x14003b002  mov     rcx, rbx
0x14003b005  test    eax, eax
0x14003b007  jz      loc_14003B08E
0x14003b00d  mov     r8d, 7803h
0x14003b013  mov     edx, eax
0x14003b015  call    SdbFindFirstTag
0x14003b01a  lea     rdi, aSdbmergeisentr_0; "SdbMergeIsEntryUpdated"
0x14003b021  mov     esi, eax
0x14003b023  test    eax, eax
0x14003b025  jz      loc_14003AF99
0x14003b02b  mov     r8d, 3802h
0x14003b031  mov     edx, eax
0x14003b033  mov     rcx, rbx
0x14003b036  call    SdbFindFirstTag
0x14003b03b  test    eax, eax
0x14003b03d  jz      short loc_14003B084
0x14003b03f  xor     r8d, r8d
0x14003b042  mov     edx, eax
0x14003b044  mov     rcx, rbx
0x14003b047  call    SdbReadWORDTag
0x14003b04c  cmp     word ptr [rbp+arg_0], ax
0x14003b050  jz      loc_14003B0EF
0x14003b056  mov     edx, [rbp+arg_20]
0x14003b059  mov     r8d, esi
0x14003b05c  mov     rcx, rbx
0x14003b05f  call    SdbFindNextTag
0x14003b064  jmp     short loc_14003B021
0x14003b066  lea     r9, aEncounteredAnI; "Encountered an index without a TAG_INDE"...
0x14003b06d  mov     [rsp+68h+var_48], esi
0x14003b071  mov     r8d, 0C43h
0x14003b077  mov     rdx, rdi
0x14003b07a  mov     ecx, 1
0x14003b07f  call    AslLogCallPrintf
0x14003b084  mov     eax, 0C0000158h
0x14003b089  jmp     loc_14003AF9E
0x14003b08e  lea     rdx, [rdi+4]
0x14003b092  call    SdbFindParentTagFromAncestors
0x14003b097  mov     esi, eax
0x14003b099  test    eax, eax
0x14003b09b  jz      loc_14003AF99
0x14003b0a1  movzx   r8d, word ptr [rdi]
0x14003b0a5  mov     edx, eax
0x14003b0a7  mov     rcx, rbx
0x14003b0aa  call    SdbFindFirstTag
0x14003b0af  mov     edi, eax
0x14003b0b1  test    eax, eax
0x14003b0b3  jz      loc_14003AF99
0x14003b0b9  movzx   r8d, r15w
0x14003b0bd  mov     edx, eax
0x14003b0bf  mov     rcx, rbx
0x14003b0c2  call    SdbFindFirstTag
0x14003b0c7  mov     r9d, eax
0x14003b0ca  mov     r8, rbx
0x14003b0cd  mov     edx, r12d
0x14003b0d0  mov     rcx, r14
0x14003b0d3  call    SdbpMergeAreTagValuesEqual
0x14003b0d8  test    eax, eax
0x14003b0da  jnz     loc_14003B216
0x14003b0e0  mov     r8d, edi
0x14003b0e3  mov     edx, esi
0x14003b0e5  mov     rcx, rbx
0x14003b0e8  call    SdbFindNextTag
0x14003b0ed  jmp     short loc_14003B0AF
0x14003b0ef  mov     r8d, 3803h
0x14003b0f5  mov     edx, esi
0x14003b0f7  mov     rcx, rbx
0x14003b0fa  call    SdbFindFirstTag
0x14003b0ff  test    eax, eax
0x14003b101  jz      short loc_14003B084
0x14003b103  xor     r8d, r8d
0x14003b106  mov     edx, eax
0x14003b108  mov     rcx, rbx
0x14003b10b  call    SdbReadWORDTag
0x14003b110  cmp     r15w, ax
0x14003b114  jz      short loc_14003B13D
0x14003b116  movzx   eax, word ptr [rbp+arg_0]
0x14003b11a  lea     r9, aEncounteredAnI_0; "Encountered an index with an unexpected"...
0x14003b121  mov     r8d, 0C38h
0x14003b127  mov     [rsp+68h+var_48], eax
0x14003b12b  mov     rdx, rdi
0x14003b12e  mov     ecx, 1
0x14003b133  call    AslLogCallPrintf
0x14003b138  jmp     loc_14003B056
0x14003b13d  mov     r8d, 4016h
0x14003b143  mov     word ptr [rbp+var_38+0Ch], r15w
0x14003b148  mov     edx, esi
0x14003b14a  mov     rcx, rbx
0x14003b14d  call    SdbFindFirstTag
0x14003b152  xor     r8d, r8d
0x14003b155  mov     edx, eax
0x14003b157  mov     rcx, rbx
0x14003b15a  call    SdbReadDWORDTag
0x14003b15f  mov     r8d, 9801h
0x14003b165  mov     dword ptr [rbp+var_28+4], eax
0x14003b168  mov     edx, esi
0x14003b16a  mov     rcx, rbx
0x14003b16d  call    SdbFindFirstTag
0x14003b172  mov     [rbp+arg_0], eax
0x14003b175  test    eax, eax
0x14003b177  jz      loc_14003B066
0x14003b17d  mov     dword ptr [rbp+var_38], eax
0x14003b180  mov     eax, r15d
0x14003b183  and     eax, 0F000h
0x14003b188  cmp     eax, 9000h
0x14003b18d  jnz     loc_14003B221
0x14003b193  mov     edx, r12d
0x14003b196  mov     rcx, r14
0x14003b199  call    SdbGetTagDataSize
0x14003b19e  cmp     eax, 10h
0x14003b1a1  jnz     loc_14003B258
0x14003b1a7  mov     edx, r12d
0x14003b1aa  mov     rcx, r14
0x14003b1ad  call    SdbpGetMappedTagData
0x14003b1b2  mov     rcx, rax
0x14003b1b5  mov     [rbp+var_18], rax
0x14003b1b9  call    SdbMakeIndexKeyFromGUID
0x14003b1be  mov     edx, [rbp+arg_0]
0x14003b1c1  lea     r9, [rbp+var_38]
0x14003b1c5  mov     r8, rax
0x14003b1c8  mov     qword ptr [rbp+var_28+8], rax
0x14003b1cc  mov     rcx, rbx
0x14003b1cf  call    SdbpGetFirstIndexedRecord
0x14003b1d4  mov     edi, eax
0x14003b1d6  test    eax, eax
0x14003b1d8  jz      loc_14003AF99
0x14003b1de  movzx   r8d, r15w
0x14003b1e2  mov     edx, eax
0x14003b1e4  mov     rcx, rbx
0x14003b1e7  call    SdbFindFirstTag
0x14003b1ec  test    eax, eax
0x14003b1ee  jz      short loc_14003B205
0x14003b1f0  mov     r9d, eax
0x14003b1f3  mov     r8, rbx
0x14003b1f6  mov     edx, r12d
0x14003b1f9  mov     rcx, r14
0x14003b1fc  call    SdbpMergeAreTagValuesEqual
0x14003b201  test    eax, eax
0x14003b203  jnz     short loc_14003B216
0x14003b205  mov     edx, dword ptr [rbp+var_38]
0x14003b208  lea     r8, [rbp+var_38]
0x14003b20c  mov     rcx, rbx
0x14003b20f  call    SdbpGetNextIndexedRecord
0x14003b214  jmp     short loc_14003B1D4
0x14003b216  mov     [r13+0], edi
0x14003b21a  xor     eax, eax
0x14003b21c  jmp     loc_14003AF9E
0x14003b221  cmp     eax, 8000h
0x14003b226  jz      short loc_14003B27E
0x14003b228  cmp     eax, 6000h
0x14003b22d  jz      short loc_14003B27E
0x14003b22f  lea     r9, aEncounteredAMe; "Encountered a merge entry key not a str"...
0x14003b236  mov     [rsp+68h+var_48], r15d
0x14003b23b  mov     r8d, 0C5Eh
0x14003b241  mov     rdx, rdi
0x14003b244  mov     ecx, 1
0x14003b249  call    AslLogCallPrintf
0x14003b24e  mov     eax, 0C00000E5h
0x14003b253  jmp     loc_14003AF9E
0x14003b258  mov     edx, [rbp+arg_0]
0x14003b25b  lea     r9, aOriginalEntry0; "Original entry 0x%08X has bad GUID size"
0x14003b262  mov     [rsp+68h+var_48], edx
0x14003b266  mov     r8d, 0C4Bh
0x14003b26c  mov     rdx, rdi
0x14003b26f  mov     ecx, 3
0x14003b274  call    AslLogCallPrintf
0x14003b279  jmp     loc_14003AF99
0x14003b27e  mov     edx, r12d
0x14003b281  mov     rcx, r14
0x14003b284  call    SdbGetStringTagPtr
0x14003b289  mov     edx, dword ptr [rbp+var_28+4]
0x14003b28c  mov     rcx, rax; SourceString
0x14003b28f  mov     [rbp+var_18], rax
0x14003b293  call    SdbMakeIndexKeyFromStringEx
0x14003b298  jmp     loc_14003B1BE
0x14003b29d  mov     eax, 0C00000F0h
0x14003b2a2  jmp     loc_14003AF9E
0x14003b2a7  mov     eax, 0C00000F2h
0x14003b2ac  jmp     loc_14003AF9E
0x14003b2b1  mov     [rsp+68h+var_48], esi
0x14003b2b5  lea     r9, aOriginalEntry0_0; "Original entry 0x%08X missing merge id "...
0x14003b2bc  mov     r8d, 0C16h
0x14003b2c2  lea     rdx, aSdbmergeisentr_0; "SdbMergeIsEntryUpdated"
0x14003b2c9  jmp     short loc_14003B26F
0x14003b2cb  neg     rbx
0x14003b2ce  sbb     eax, eax
0x14003b2d0  and     eax, 0FFFFFFFEh
0x14003b2d3  add     eax, 0C00000F1h
0x14003b2d8  jmp     loc_14003AF9E
```
