# BZ2_bz__AssertH__fail

- ea: `0x180016320`
- end: `0x180016382`
- name: `BZ2_bz__AssertH__fail`
- size: `98`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018220`
- `0x18001c4e0`
- `0x18001ef30`
- `0x18001f0e0`
- `0x18001f460`
- `0x180020030`
- `0x180020750`
- `0x1800214d0`

## callees

- `0x1800158b8`
- `0x180016320`
- `0x180016390`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_exit` at `0x18001637b`
- `api-ms-win-crt-private-l1-1-0!_o_exit` at `0x18001637b`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180016339`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180016361`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180016339`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180016361`

## string_xrefs

- `0x180016342`: `\n\nbzip2/libbzip2: internal error number %d.\nThis is a bug in bzip2/libbzip2, %s.\nPlease report it to: bzip2-devel@sourceware.org.  If this happened\nwhen you were using some program which uses libbzip2 as a\ncomponent, you should also report this bug to the author(s)\nof that program.  Please make an effort to report this bug;\ntimely and accurate bug reports eventually lead to higher\nquality software.  Thanks.\n\n`
- `0x18001636a`: `\n*** A special note about internal error number 1007 ***\n\nExperience suggests that a common cause of i.e. 1007\nis unreliable memory or other hardware.  The 1007 assertion\njust happens to cross-check the results of huge numbers of\nmemory reads/writes, and so acts (unintendedly) as a stress\ntest of your memory system.\n\nI suggest the following: try compressing the file again,\npossibly monitoring progress in detail with the -vv flag.\n\n* If the error cannot be reproduced, and/or happens a`

## pseudocode

```c
void __fastcall __noreturn BZ2_bz__AssertH__fail(int a1)
{
  const char *v2; // rbx
  FILE *v3; // rax
  FILE *v4; // rax

  v2 = (const char *)BZ2_bzlibVersion();
  v3 = __acrt_iob_func(2u);
  fprintf(
    v3,
    "\n"
    "\n"
    "bzip2/libbzip2: internal error number %d.\n"
    "This is a bug in bzip2/libbzip2, %s.\n"
    "Please report it to: bzip2-devel@sourceware.org.  If this happened\n"
    "when you were using some program which uses libbzip2 as a\n"
    "component, you should also report this bug to the author(s)\n"
    "of that program.  Please make an effort to report this bug;\n"
    "timely and accurate bug reports eventually lead to higher\n"
    "quality software.  Thanks.\n"
    "\n",
    a1,
    v2);
  if ( a1 == 1007 )
  {
    v4 = __acrt_iob_func(2u);
    fprintf(
      v4,
      "\n"
      "*** A special note about internal error number 1007 ***\n"
      "\n"
      "Experience suggests that a common cause of i.e. 1007\n"
      "is unreliable memory or other hardware.  The 1007 assertion\n"
      "just happens to cross-check the results of huge numbers of\n"
      "memory reads/writes, and so acts (unintendedly) as a stress\n"
      "test of your memory system.\n"
      "\n"
      "I suggest the following: try compressing the file again,\n"
      "possibly monitoring progress in detail with the -vv flag.\n"
      "\n"
      "* If the error cannot be reproduced, and/or happens at different\n"
      "  points in compression, you may have a flaky memory system.\n"
      "  Try a memory-test program.  I have used Memtest86\n"
      "  (www.memtest86.com).  At the time of writing it is free (GPLd).\n"
      "  Memtest86 tests memory much more thorougly than your BIOSs\n"
      "  power-on test, and may find failures that the BIOS doesn't.\n"
      "\n"
      "* If the error can be repeatably reproduced, this is a bug in\n"
      "  bzip2, and I would very much like to hear about it.  Please\n"
      "  let me know, and, ideally, save a copy of the file causing the\n"
      "  problem -- without which I will be unable to investigate it.\n"
      "\n");
  }
  exit(3);
}

```

## disassembly

```asm
0x180016320  mov     [rsp+arg_0], rbx
0x180016325  push    rdi
0x180016326  sub     rsp, 20h
0x18001632a  mov     edi, ecx
0x18001632c  call    BZ2_bzlibVersion
0x180016331  mov     ecx, 2; Ix
0x180016336  mov     rbx, rax
0x180016339  call    cs:__imp___acrt_iob_func
0x18001633f  mov     r9, rbx
0x180016342  lea     rdx, aBzip2Libbzip2I; "\n\nbzip2/libbzip2: internal error numb"...
0x180016349  mov     rcx, rax; Stream
0x18001634c  mov     r8d, edi
0x18001634f  call    fprintf
0x180016354  cmp     edi, 3EFh
0x18001635a  jnz     short loc_180016376
0x18001635c  mov     ecx, 2; Ix
0x180016361  call    cs:__imp___acrt_iob_func
0x180016367  mov     rcx, rax; Stream
0x18001636a  lea     rdx, aASpecialNoteAb; "\n*** A special note about internal err"...
0x180016371  call    fprintf
0x180016376  mov     ecx, 3; Code
0x18001637b  call    cs:__imp_exit
```
