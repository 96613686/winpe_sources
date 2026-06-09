# sqlite3_keyword_name

- ea: `0x18009cd80`
- end: `0x18009cdbd`
- name: `sqlite3_keyword_name`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18009cd80`

## string_xrefs

- `0x18009cd92`: `REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXPLAINSTEADDATABASELECTABLEFTHENDEFERRABLELSEXCLUDELETEMPORARYISNULLSAVEPOINTERSECTIESNOTNULLIKEXCEPTRANSACTIONATURALTERAISEXCLUSIVEXISTSCONSTRAINTOFFSETRIGGERANGENERATEDETACHAVINGLOBEGINNEREFERENCESUNIQUERYWITHOUTERELEASEATTACHBETWEENOTHINGROUPSCASCADEFAULTCASECOLLATECREATECURRENT_DATEIMMEDIATEJOINSERTMATCHPLANALYZEPRAGMATERIALIZEDEFERREDISTINCTUPDATEVALUESVIRTUALWAYSWHENWHERECURSIVEABORTAFTERENAMEANDROPARTITIONAUTOINCREMENTCASTCOLUMNCOMMITCONFLICTCROSSCURRE`

## pseudocode

```c
__int64 __fastcall sqlite3_keyword_name(unsigned int a1, _QWORD *a2, _DWORD *a3)
{
  if ( a1 > 0x92 )
    return 1;
  *a2 = &aReindexedescap[(unsigned __int16)word_1800BDCE2[a1]];
  *a3 = *((unsigned __int8 *)qword_1800BD5F0 + (int)a1 + 1);
  return 0;
}

```

## disassembly

```asm
0x18009cd80  cmp     ecx, 92h
0x18009cd86  ja      short loc_18009CDB7
0x18009cd88  movsxd  rcx, ecx
0x18009cd8b  lea     r10, __ImageBase
0x18009cd92  lea     r9, aReindexedescap; "REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXP"...
0x18009cd99  movzx   eax, ds:rva word_1800BDCE2[r10+rcx*2]
0x18009cda2  add     rax, r9
0x18009cda5  mov     [rdx], rax
0x18009cda8  movzx   eax, byte ptr [rcx+r10+0BD5F1h]
0x18009cdb1  mov     [r8], eax
0x18009cdb4  xor     eax, eax
0x18009cdb6  retn
0x18009cdb7  mov     eax, 1
0x18009cdbc  retn
```
