# sqlite3_keyword_name

- ea: `0x18008edc0`
- end: `0x18008edfd`
- name: `sqlite3_keyword_name`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18008edc0`

## string_xrefs

- `0x18008edd2`: `REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXPLAINSTEADDATABASELECTABLEFTHENDEFERRABLELSEXCLUDELETEMPORARYISNULLSAVEPOINTERSECTIESNOTNULLIKEXCEPTRANSACTIONATURALTERAISEXCLUSIVEXISTSCONSTRAINTOFFSETRIGGERANGENERATEDETACHAVINGLOBEGINNEREFERENCESUNIQUERYWITHOUTERELEASEATTACHBETWEENOTHINGROUPSCASCADEFAULTCASECOLLATECREATECURRENT_DATEIMMEDIATEJOINSERTMATCHPLANALYZEPRAGMATERIALIZEDEFERREDISTINCTUPDATEVALUESVIRTUALWAYSWHENWHERECURSIVEABORTAFTERENAMEANDROPARTITIONAUTOINCREMENTCASTCOLUMNCOMMITCONFLICTCROSSCURRE`

## pseudocode

```c
__int64 __fastcall sqlite3_keyword_name(unsigned int a1, _QWORD *a2, _DWORD *a3)
{
  if ( a1 > 0x92 )
    return 1;
  *a2 = &aReindexedescap[(unsigned __int16)word_1800A6F72[a1]];
  *a3 = *((unsigned __int8 *)qword_1800A6880 + (int)a1 + 1);
  return 0;
}

```

## disassembly

```asm
0x18008edc0  cmp     ecx, 92h
0x18008edc6  ja      short loc_18008EDF7
0x18008edc8  movsxd  rcx, ecx
0x18008edcb  lea     r10, cs:180000000h
0x18008edd2  lea     r9, aReindexedescap; "REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXP"...
0x18008edd9  movzx   eax, ds:rva word_1800A6F72[r10+rcx*2]
0x18008ede2  add     rax, r9
0x18008ede5  mov     [rdx], rax
0x18008ede8  movzx   eax, byte ptr [rcx+r10+0A6881h]
0x18008edf1  mov     [r8], eax
0x18008edf4  xor     eax, eax
0x18008edf6  retn
0x18008edf7  mov     eax, 1
0x18008edfc  retn
```
