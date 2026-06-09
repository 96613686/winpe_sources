# xml_parse_file_ext2

- ea: `0x1800e6848`
- end: `0x1800e6b91`
- name: `xml_parse_file_ext2`
- size: `841`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800e6d78`

## callees

- `0x18000a2d0`
- `0x180014ab4`
- `0x1800e6848`
- `0x180119956`

## string_xrefs

- `0x1800e687e`: `Undelete`
- `0x1800e68a4`: `Compress`
- `0x1800e6988`: `CompDirty`
- `0x1800e69ae`: `CompBlock`
- `0x1800e69d4`: `NoCompBlock`
- `0x1800e69fa`: `CompError`
- `0x1800e6898`: `nouunlink`
- `0x1800e68be`: `compress`
- `0x1800e69a2`: `compdirty`
- `0x1800e69c8`: `comprblk`
- `0x1800e69ee`: `nocomprblk`
- `0x1800e6a14`: `comperr`

## pseudocode

```c
__int64 __fastcall xml_parse_file_ext2(__int64 a1, const char *a2)
{
  __int64 v4; // rdx
  const char *v5; // rbx
  __int64 v6; // rcx

  if ( !strcmp_0(a2, "SecureDeletion") )
  {
    *(_DWORD *)(a1 + 40) = 57;
    v5 = "securedeletion";
  }
  else if ( !strcmp_0(a2, "Undelete") )
  {
    *(_DWORD *)(a1 + 40) = 58;
    v5 = "nouunlink";
  }
  else if ( !strcmp_0(a2, "Compress") )
  {
    *(_DWORD *)(a1 + 40) = 59;
    v5 = "compress";
  }
  else if ( !strcmp_0(a2, "Synchronous") )
  {
    *(_DWORD *)(a1 + 40) = 60;
    v5 = "sync";
  }
  else if ( !strcmp_0(a2, "Immutable") )
  {
    *(_DWORD *)(a1 + 40) = 61;
    v5 = "simmutable";
  }
  else if ( !strcmp_0(a2, "AppendOnly") )
  {
    *(_DWORD *)(a1 + 40) = 62;
    v5 = "sappend";
  }
  else if ( !strcmp_0(a2, "NoDump") )
  {
    *(_DWORD *)(a1 + 40) = 63;
    v5 = "nodump";
  }
  else if ( !strcmp_0(a2, "NoAtime") )
  {
    *(_DWORD *)(a1 + 40) = 64;
    v5 = "noatime";
  }
  else if ( !strcmp_0(a2, "CompDirty") )
  {
    *(_DWORD *)(a1 + 40) = 65;
    v5 = "compdirty";
  }
  else if ( !strcmp_0(a2, "CompBlock") )
  {
    *(_DWORD *)(a1 + 40) = 66;
    v5 = "comprblk";
  }
  else if ( !strcmp_0(a2, "NoCompBlock") )
  {
    *(_DWORD *)(a1 + 40) = 67;
    v5 = "nocomprblk";
  }
  else if ( !strcmp_0(a2, "CompError") )
  {
    *(_DWORD *)(a1 + 40) = 68;
    v5 = "comperr";
  }
  else if ( !strcmp_0(a2, "BTree") )
  {
    *(_DWORD *)(a1 + 40) = 69;
    v5 = "btree";
  }
  else if ( !strcmp_0(a2, "HashIndexed") )
  {
    *(_DWORD *)(a1 + 40) = 70;
    v5 = "hashidx";
  }
  else if ( !strcmp_0(a2, "iMagic") )
  {
    *(_DWORD *)(a1 + 40) = 71;
    v5 = "imagic";
  }
  else if ( !strcmp_0(a2, "Journaled") )
  {
    *(_DWORD *)(a1 + 40) = 72;
    v5 = "journal";
  }
  else if ( !strcmp_0(a2, "NoTail") )
  {
    *(_DWORD *)(a1 + 40) = 73;
    v5 = "notail";
  }
  else if ( !strcmp_0(a2, "DirSync") )
  {
    *(_DWORD *)(a1 + 40) = 74;
    v5 = "dirsync";
  }
  else if ( !strcmp_0(a2, "TopDir") )
  {
    *(_DWORD *)(a1 + 40) = 75;
    v5 = "topdir";
  }
  else
  {
    if ( strcmp_0(a2, "Reserved") )
      return 0;
    *(_DWORD *)(a1 + 40) = 76;
    v5 = "reserved";
  }
  v6 = *(_QWORD *)(a1 + 544);
  if ( *(_QWORD *)(v6 + 320) )
  {
    LOBYTE(v4) = 44;
    archive_strappend_char(v6 + 312, v4);
  }
  archive_strncat(*(_QWORD *)(a1 + 544) + 312LL, v5, 0x1000000);
  return 1;
}

```

## disassembly

```asm
0x1800e6848  mov     [rsp+arg_0], rbx
0x1800e684d  push    rdi
0x1800e684e  sub     rsp, 20h
0x1800e6852  mov     rbx, rdx
0x1800e6855  mov     rdi, rcx
0x1800e6858  mov     rcx, rbx; Str1
0x1800e685b  lea     rdx, aSecuredeletion_0; "SecureDeletion"
0x1800e6862  call    strcmp_0
0x1800e6867  test    eax, eax
0x1800e6869  jnz     short loc_1800E687E
0x1800e686b  mov     dword ptr [rdi+28h], 39h ; '9'
0x1800e6872  lea     rbx, aSecuredeletion; "securedeletion"
0x1800e6879  jmp     loc_1800E6B42
0x1800e687e  lea     rdx, aUndelete; "Undelete"
0x1800e6885  mov     rcx, rbx; Str1
0x1800e6888  call    strcmp_0
0x1800e688d  test    eax, eax
0x1800e688f  jnz     short loc_1800E68A4
0x1800e6891  mov     dword ptr [rdi+28h], 3Ah ; ':'
0x1800e6898  lea     rbx, aNouunlink; "nouunlink"
0x1800e689f  jmp     loc_1800E6B42
0x1800e68a4  lea     rdx, aCompress; "Compress"
0x1800e68ab  mov     rcx, rbx; Str1
0x1800e68ae  call    strcmp_0
0x1800e68b3  test    eax, eax
0x1800e68b5  jnz     short loc_1800E68CA
0x1800e68b7  mov     dword ptr [rdi+28h], 3Bh ; ';'
0x1800e68be  lea     rbx, aCompress_0; "compress"
0x1800e68c5  jmp     loc_1800E6B42
0x1800e68ca  lea     rdx, aSynchronous; "Synchronous"
0x1800e68d1  mov     rcx, rbx; Str1
0x1800e68d4  call    strcmp_0
0x1800e68d9  test    eax, eax
0x1800e68db  jnz     short loc_1800E68F0
0x1800e68dd  mov     dword ptr [rdi+28h], 3Ch ; '<'
0x1800e68e4  lea     rbx, aSync; "sync"
0x1800e68eb  jmp     loc_1800E6B42
0x1800e68f0  lea     rdx, aImmutable; "Immutable"
0x1800e68f7  mov     rcx, rbx; Str1
0x1800e68fa  call    strcmp_0
0x1800e68ff  test    eax, eax
0x1800e6901  jnz     short loc_1800E6916
0x1800e6903  mov     dword ptr [rdi+28h], 3Dh ; '='
0x1800e690a  lea     rbx, aSimmutable; "simmutable"
0x1800e6911  jmp     loc_1800E6B42
0x1800e6916  lea     rdx, aAppendonly; "AppendOnly"
0x1800e691d  mov     rcx, rbx; Str1
0x1800e6920  call    strcmp_0
0x1800e6925  test    eax, eax
0x1800e6927  jnz     short loc_1800E693C
0x1800e6929  mov     dword ptr [rdi+28h], 3Eh ; '>'
0x1800e6930  lea     rbx, aSappend; "sappend"
0x1800e6937  jmp     loc_1800E6B42
0x1800e693c  lea     rdx, aNodump; "NoDump"
0x1800e6943  mov     rcx, rbx; Str1
0x1800e6946  call    strcmp_0
0x1800e694b  test    eax, eax
0x1800e694d  jnz     short loc_1800E6962
0x1800e694f  mov     dword ptr [rdi+28h], 3Fh ; '?'
0x1800e6956  lea     rbx, aNodump_0; "nodump"
0x1800e695d  jmp     loc_1800E6B42
0x1800e6962  lea     rdx, aNoatime_0; "NoAtime"
0x1800e6969  mov     rcx, rbx; Str1
0x1800e696c  call    strcmp_0
0x1800e6971  test    eax, eax
0x1800e6973  jnz     short loc_1800E6988
0x1800e6975  mov     dword ptr [rdi+28h], 40h ; '@'
0x1800e697c  lea     rbx, aNoatime; "noatime"
0x1800e6983  jmp     loc_1800E6B42
0x1800e6988  lea     rdx, aCompdirty_0; "CompDirty"
0x1800e698f  mov     rcx, rbx; Str1
0x1800e6992  call    strcmp_0
0x1800e6997  test    eax, eax
0x1800e6999  jnz     short loc_1800E69AE
0x1800e699b  mov     dword ptr [rdi+28h], 41h ; 'A'
0x1800e69a2  lea     rbx, aCompdirty; "compdirty"
0x1800e69a9  jmp     loc_1800E6B42
0x1800e69ae  lea     rdx, aCompblock; "CompBlock"
0x1800e69b5  mov     rcx, rbx; Str1
0x1800e69b8  call    strcmp_0
0x1800e69bd  test    eax, eax
0x1800e69bf  jnz     short loc_1800E69D4
0x1800e69c1  mov     dword ptr [rdi+28h], 42h ; 'B'
0x1800e69c8  lea     rbx, aComprblk; "comprblk"
0x1800e69cf  jmp     loc_1800E6B42
0x1800e69d4  lea     rdx, aNocompblock; "NoCompBlock"
0x1800e69db  mov     rcx, rbx; Str1
0x1800e69de  call    strcmp_0
0x1800e69e3  test    eax, eax
0x1800e69e5  jnz     short loc_1800E69FA
0x1800e69e7  mov     dword ptr [rdi+28h], 43h ; 'C'
0x1800e69ee  lea     rbx, aNocomprblk; "nocomprblk"
0x1800e69f5  jmp     loc_1800E6B42
0x1800e69fa  lea     rdx, aComperror; "CompError"
0x1800e6a01  mov     rcx, rbx; Str1
0x1800e6a04  call    strcmp_0
0x1800e6a09  test    eax, eax
0x1800e6a0b  jnz     short loc_1800E6A20
0x1800e6a0d  mov     dword ptr [rdi+28h], 44h ; 'D'
0x1800e6a14  lea     rbx, aComperr; "comperr"
0x1800e6a1b  jmp     loc_1800E6B42
0x1800e6a20  lea     rdx, aBtree; "BTree"
0x1800e6a27  mov     rcx, rbx; Str1
0x1800e6a2a  call    strcmp_0
0x1800e6a2f  test    eax, eax
0x1800e6a31  jnz     short loc_1800E6A46
0x1800e6a33  mov     dword ptr [rdi+28h], 45h ; 'E'
0x1800e6a3a  lea     rbx, aBtree_0; "btree"
0x1800e6a41  jmp     loc_1800E6B42
0x1800e6a46  lea     rdx, aHashindexed; "HashIndexed"
0x1800e6a4d  mov     rcx, rbx; Str1
0x1800e6a50  call    strcmp_0
0x1800e6a55  test    eax, eax
0x1800e6a57  jnz     short loc_1800E6A6C
0x1800e6a59  mov     dword ptr [rdi+28h], 46h ; 'F'
0x1800e6a60  lea     rbx, aHashidx; "hashidx"
0x1800e6a67  jmp     loc_1800E6B42
0x1800e6a6c  lea     rdx, aImagic_0; "iMagic"
0x1800e6a73  mov     rcx, rbx; Str1
0x1800e6a76  call    strcmp_0
0x1800e6a7b  test    eax, eax
0x1800e6a7d  jnz     short loc_1800E6A92
0x1800e6a7f  mov     dword ptr [rdi+28h], 47h ; 'G'
0x1800e6a86  lea     rbx, aImagic; "imagic"
0x1800e6a8d  jmp     loc_1800E6B42
0x1800e6a92  lea     rdx, aJournaled; "Journaled"
0x1800e6a99  mov     rcx, rbx; Str1
0x1800e6a9c  call    strcmp_0
0x1800e6aa1  test    eax, eax
0x1800e6aa3  jnz     short loc_1800E6AB8
0x1800e6aa5  mov     dword ptr [rdi+28h], 48h ; 'H'
0x1800e6aac  lea     rbx, aJournal; "journal"
0x1800e6ab3  jmp     loc_1800E6B42
0x1800e6ab8  lea     rdx, aNotail_0; "NoTail"
0x1800e6abf  mov     rcx, rbx; Str1
0x1800e6ac2  call    strcmp_0
0x1800e6ac7  test    eax, eax
0x1800e6ac9  jnz     short loc_1800E6ADB
0x1800e6acb  mov     dword ptr [rdi+28h], 49h ; 'I'
0x1800e6ad2  lea     rbx, aNotail; "notail"
0x1800e6ad9  jmp     short loc_1800E6B42
0x1800e6adb  lea     rdx, aDirsync; "DirSync"
0x1800e6ae2  mov     rcx, rbx; Str1
0x1800e6ae5  call    strcmp_0
0x1800e6aea  test    eax, eax
0x1800e6aec  jnz     short loc_1800E6AFE
0x1800e6aee  mov     dword ptr [rdi+28h], 4Ah ; 'J'
0x1800e6af5  lea     rbx, aDirsync_0; "dirsync"
0x1800e6afc  jmp     short loc_1800E6B42
0x1800e6afe  lea     rdx, aTopdir_0; "TopDir"
0x1800e6b05  mov     rcx, rbx; Str1
0x1800e6b08  call    strcmp_0
0x1800e6b0d  test    eax, eax
0x1800e6b0f  jnz     short loc_1800E6B21
0x1800e6b11  mov     dword ptr [rdi+28h], 4Bh ; 'K'
0x1800e6b18  lea     rbx, aTopdir; "topdir"
0x1800e6b1f  jmp     short loc_1800E6B42
0x1800e6b21  lea     rdx, aReserved_0; "Reserved"
0x1800e6b28  mov     rcx, rbx; Str1
0x1800e6b2b  call    strcmp_0
0x1800e6b30  test    eax, eax
0x1800e6b32  jnz     short loc_1800E6B84
0x1800e6b34  mov     dword ptr [rdi+28h], 4Ch ; 'L'
0x1800e6b3b  lea     rbx, aReserved; "reserved"
0x1800e6b42  mov     rcx, [rdi+220h]
0x1800e6b49  cmp     qword ptr [rcx+140h], 0
0x1800e6b51  jbe     short loc_1800E6B61
0x1800e6b53  add     rcx, 138h
0x1800e6b5a  mov     dl, 2Ch ; ','
0x1800e6b5c  call    archive_strappend_char
0x1800e6b61  mov     rcx, [rdi+220h]
0x1800e6b68  mov     r8d, 1000000h
0x1800e6b6e  add     rcx, 138h
0x1800e6b75  mov     rdx, rbx
0x1800e6b78  call    archive_strncat
0x1800e6b7d  mov     eax, 1
0x1800e6b82  jmp     short loc_1800E6B86
0x1800e6b84  xor     eax, eax
0x1800e6b86  mov     rbx, [rsp+28h+arg_0]
0x1800e6b8b  add     rsp, 20h
0x1800e6b8f  pop     rdi
0x1800e6b90  retn
```
