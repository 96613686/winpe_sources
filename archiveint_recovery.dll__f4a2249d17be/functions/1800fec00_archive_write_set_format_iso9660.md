# archive_write_set_format_iso9660

- ea: `0x1800fec00`
- end: `0x1800fefaf`
- name: `archive_write_set_format_iso9660`
- size: `943`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000523c`
- `0x180006c00`
- `0x18000a2d0`
- `0x18000b4d0`
- `0x180015810`
- `0x1800fec00`
- `0x1801017b0`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800fec4f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800fec4f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fef85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fef85`

## string_xrefs

- `0x1800fec11`: `archive_write_set_format_iso9660`

## pseudocode

```c
__int64 __fastcall archive_write_set_format_iso9660(__int64 a1)
{
  void (__fastcall *v2)(__int64); // rax
  char *v3; // rax
  char *v4; // rbx
  char *v5; // rcx
  _QWORD *v6; // rax
  __int64 virtual_dir; // rax
  __int64 result; // rax

  if ( (unsigned int)_archive_check_magic(a1, 2965749982LL, 1, "archive_write_set_format_iso9660") != -30 )
  {
    v2 = *(void (__fastcall **)(__int64))(a1 + 312);
    if ( v2 )
      v2(a1);
    v3 = (char *)calloc(1u, 0x10360u);
    v4 = v3;
    if ( v3 )
    {
      *(_QWORD *)v3 = 0;
      v5 = v3 + 296;
      *((_DWORD *)v3 + 2) = -1;
      *((_QWORD *)v3 + 2) = 0;
      *((_DWORD *)v3 + 52) = 0;
      *((_DWORD *)v3 + 48) = 0;
      *((_QWORD *)v3 + 25) = 0;
      *((_QWORD *)v3 + 29) = 0;
      *((_DWORD *)v3 + 64) = 0;
      *((_DWORD *)v3 + 60) = 1;
      *((_QWORD *)v3 + 31) = 0;
      v6 = v3 + 136;
      *((_QWORD *)v4 + 18) = v6;
      *v6 = 0;
      *((_QWORD *)v4 + 19) = 0;
      *((_QWORD *)v4 + 20) = v4 + 152;
      *((_QWORD *)v4 + 22) = off_18011E488;
      *((_QWORD *)v4 + 21) = 0;
      *((_QWORD *)v4 + 87) = 0;
      *((_DWORD *)v4 + 176) = 1;
      *((_QWORD *)v4 + 8281) = 0x10000;
      *((_DWORD *)v4 + 16564) = 1;
      *((_QWORD *)v4 + 8283) = 0;
      *((_QWORD *)v4 + 8284) = 0;
      *((_QWORD *)v4 + 8285) = 0;
      *((_QWORD *)v4 + 9) = 0;
      *((_QWORD *)v4 + 10) = 0;
      *((_QWORD *)v4 + 11) = 0;
      *((_QWORD *)v4 + 12) = 0;
      *((_QWORD *)v4 + 13) = 0;
      *((_QWORD *)v4 + 14) = 0;
      *((_QWORD *)v4 + 37) = 0;
      *((_QWORD *)v4 + 39) = 0;
      *((_QWORD *)v4 + 38) = 0;
      archive_strncat(v5, "CDROM", 5);
      *((_QWORD *)v4 + 40) = 0;
      *((_QWORD *)v4 + 46) = 0;
      *((_QWORD *)v4 + 41) = 0;
      *((_QWORD *)v4 + 42) = 0;
      *((_QWORD *)v4 + 43) = 0;
      *((_QWORD *)v4 + 44) = 0;
      *((_QWORD *)v4 + 45) = 0;
      *((_QWORD *)v4 + 48) = 0;
      *((_QWORD *)v4 + 47) = 0;
      archive_strncat(v4 + 368, "libarchive 3.8.4", 16);
      *((_QWORD *)v4 + 49) = 0;
      *((_QWORD *)v4 + 8286) = 0;
      *((_QWORD *)v4 + 50) = 0;
      *((_QWORD *)v4 + 51) = 0;
      *((_QWORD *)v4 + 52) = 0;
      *((_QWORD *)v4 + 53) = 0;
      *((_QWORD *)v4 + 54) = 0;
      *((_QWORD *)v4 + 55) = 0;
      *((_QWORD *)v4 + 56) = 0;
      *((_QWORD *)v4 + 57) = 0;
      *((_QWORD *)v4 + 8288) = 0;
      *((_QWORD *)v4 + 8289) = 0;
      *((_QWORD *)v4 + 8287) = 0;
      archive_strncat(v4 + 66288, "boot.catalog", 12);
      *((_QWORD *)v4 + 8290) = 0;
      *((_QWORD *)v4 + 8291) = 0;
      *((_QWORD *)v4 + 8292) = 0;
      *((_QWORD *)v4 + 8293) = 0;
      v4[66352] = 0;
      *((_QWORD *)v4 + 8295) = 0;
      *((_QWORD *)v4 + 8296) = 0;
      *((_QWORD *)v4 + 8297) = 0;
      *(_DWORD *)(v4 + 66386) = 0x40000;
      *((_QWORD *)v4 + 68) = 0;
      *((_QWORD *)v4 + 69) = 0;
      *((_DWORD *)v4 + 168) = 0;
      *((_DWORD *)v4 + 172) = 9;
      memset_0(v4 + 584, 0, 0x58u);
      *((_DWORD *)v4 + 16598) = *((_DWORD *)v4 + 16598) & 0xF8002000 | 0x13A4004;
      virtual_dir = isoent_create_virtual_dir(a1, v4, &unk_18012277F);
      *((_QWORD *)v4 + 23) = virtual_dir;
      if ( virtual_dir )
      {
        *(_QWORD *)(virtual_dir + 32) = virtual_dir;
        *((_QWORD *)v4 + 3) = *((_QWORD *)v4 + 23);
        *((_QWORD *)v4 + 4) = 0;
        *((_QWORD *)v4 + 5) = 0;
        *((_QWORD *)v4 + 6) = 0;
        if ( archive_string_ensure(v4 + 32, 1) )
        {
          **((_BYTE **)v4 + 4) = 0;
          *((_QWORD *)v4 + 15) = 0;
          *((_QWORD *)v4 + 16) = 0;
          *(_QWORD *)(a1 + 256) = "iso9660";
          *(_QWORD *)(a1 + 272) = iso9660_options;
          *(_QWORD *)(a1 + 288) = iso9660_write_header;
          *(_QWORD *)(a1 + 296) = iso9660_write_data;
          *(_QWORD *)(a1 + 280) = iso9660_finish_entry;
          *(_QWORD *)(a1 + 304) = iso9660_close;
          *(_QWORD *)(a1 + 312) = iso9660_free;
          *(_QWORD *)(a1 + 24) = "ISO9660";
          result = 0;
          *(_QWORD *)(a1 + 248) = v4;
          *(_DWORD *)(a1 + 16) = 0x40000;
          return result;
        }
      }
      free(v4);
      archive_set_error(a1, 12, "Can't allocate memory");
    }
    else
    {
      archive_set_error(a1, 12, "Can't allocate iso9660 data");
    }
  }
  return 4294967266LL;
}

```

## disassembly

```asm
0x1800fec00  push    rbx
0x1800fec02  push    rbp
0x1800fec03  push    rsi
0x1800fec04  push    rdi
0x1800fec05  push    r15
0x1800fec07  sub     rsp, 20h
0x1800fec0b  mov     r15d, 1
0x1800fec11  lea     r9, aArchiveWriteSe_53; "archive_write_set_format_iso9660"
0x1800fec18  mov     r8d, r15d
0x1800fec1b  mov     edx, 0B0C5C0DEh
0x1800fec20  mov     rdi, rcx
0x1800fec23  call    __archive_check_magic
0x1800fec28  cmp     eax, 0FFFFFFE2h
0x1800fec2b  jz      loc_1800FEF9F
0x1800fec31  mov     rax, [rdi+138h]
0x1800fec38  xor     ebp, ebp
0x1800fec3a  test    rax, rax
0x1800fec3d  jz      short loc_1800FEC47
0x1800fec3f  mov     rcx, rdi
0x1800fec42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fec47  mov     edx, 10360h; Size
0x1800fec4c  mov     rcx, r15; Count
0x1800fec4f  call    cs:__imp_calloc
0x1800fec55  mov     rbx, rax
0x1800fec58  test    rax, rax
0x1800fec5b  jnz     short loc_1800FEC69
0x1800fec5d  lea     r8, aCanTAllocateIs; "Can't allocate iso9660 data"
0x1800fec64  jmp     loc_1800FEF92
0x1800fec69  mov     [rax], rbp
0x1800fec6c  lea     rcx, [rbx+128h]
0x1800fec73  mov     dword ptr [rax+8], 0FFFFFFFFh
0x1800fec7a  lea     rdx, aCdrom; "CDROM"
0x1800fec81  mov     [rax+10h], rbp
0x1800fec85  mov     r8d, 5
0x1800fec8b  mov     [rax+0D0h], ebp
0x1800fec91  mov     [rax+0C0h], ebp
0x1800fec97  mov     [rax+0C8h], rbp
0x1800fec9e  mov     [rax+0E8h], rbp
0x1800feca5  mov     [rax+100h], ebp
0x1800fecab  mov     [rax+0F0h], r15d
0x1800fecb2  mov     [rax+0F8h], rbp
0x1800fecb9  add     rax, 88h
0x1800fecbf  mov     [rbx+90h], rax
0x1800fecc6  mov     [rax], rbp
0x1800fecc9  lea     rax, [rbx+98h]
0x1800fecd0  mov     [rax], rbp
0x1800fecd3  mov     [rbx+0A0h], rax
0x1800fecda  lea     rax, off_18011E488
0x1800fece1  mov     [rbx+0B0h], rax
0x1800fece8  mov     [rbx+0A8h], rbp
0x1800fecef  mov     [rbx+2B8h], rbp
0x1800fecf6  mov     [rbx+2C0h], r15d
0x1800fecfd  mov     qword ptr [rbx+102C8h], 10000h
0x1800fed08  mov     [rbx+102D0h], r15d
0x1800fed0f  mov     [rbx+102D8h], rbp
0x1800fed16  mov     [rbx+102E0h], rbp
0x1800fed1d  mov     [rbx+102E8h], rbp
0x1800fed24  mov     [rbx+48h], rbp
0x1800fed28  mov     [rbx+50h], rbp
0x1800fed2c  mov     [rbx+58h], rbp
0x1800fed30  mov     [rbx+60h], rbp
0x1800fed34  mov     [rbx+68h], rbp
0x1800fed38  mov     [rbx+70h], rbp
0x1800fed3c  mov     [rcx], rbp
0x1800fed3f  mov     [rbx+138h], rbp
0x1800fed46  mov     [rbx+130h], rbp
0x1800fed4d  call    archive_strncat
0x1800fed52  lea     rcx, [rbx+170h]
0x1800fed59  mov     [rbx+140h], rbp
0x1800fed60  mov     r8d, 10h
0x1800fed66  mov     [rcx], rbp
0x1800fed69  lea     rdx, aLibarchive384; "libarchive 3.8.4"
0x1800fed70  mov     [rbx+148h], rbp
0x1800fed77  mov     [rbx+150h], rbp
0x1800fed7e  mov     [rbx+158h], rbp
0x1800fed85  mov     [rbx+160h], rbp
0x1800fed8c  mov     [rbx+168h], rbp
0x1800fed93  mov     [rbx+180h], rbp
0x1800fed9a  mov     [rbx+178h], rbp
0x1800feda1  call    archive_strncat
0x1800feda6  lea     rcx, [rbx+102F0h]
0x1800fedad  mov     [rbx+188h], rbp
0x1800fedb4  mov     r8d, 0Ch
0x1800fedba  mov     [rcx], rbp
0x1800fedbd  lea     rdx, aBootCatalog_0; "boot.catalog"
0x1800fedc4  mov     [rbx+190h], rbp
0x1800fedcb  mov     [rbx+198h], rbp
0x1800fedd2  mov     [rbx+1A0h], rbp
0x1800fedd9  mov     [rbx+1A8h], rbp
0x1800fede0  mov     [rbx+1B0h], rbp
0x1800fede7  mov     [rbx+1B8h], rbp
0x1800fedee  mov     [rbx+1C0h], rbp
0x1800fedf5  mov     [rbx+1C8h], rbp
0x1800fedfc  mov     [rbx+10300h], rbp
0x1800fee03  mov     [rbx+10308h], rbp
0x1800fee0a  mov     [rbx+102F8h], rbp
0x1800fee11  call    archive_strncat
0x1800fee16  mov     [rbx+10310h], rbp
0x1800fee1d  mov     [rbx+10318h], rbp
0x1800fee24  mov     [rbx+10320h], rbp
0x1800fee2b  mov     [rbx+10328h], rbp
0x1800fee32  mov     [rbx+10330h], bpl
0x1800fee39  mov     [rbx+10338h], rbp
0x1800fee40  mov     [rbx+10340h], rbp
0x1800fee47  mov     [rbx+10348h], rbp
0x1800fee4e  mov     dword ptr [rbx+10352h], 40000h
0x1800fee58  mov     [rbx+220h], rbp
0x1800fee5f  mov     [rbx+228h], rbp
0x1800fee66  mov     [rbx+2A0h], ebp
0x1800fee6c  xor     edx, edx; Val
0x1800fee6e  mov     dword ptr [rbx+2B0h], 9
0x1800fee78  lea     rcx, [rbx+248h]; void *
0x1800fee7f  lea     r8d, [rdx+58h]; Size
0x1800fee83  call    memset_0
0x1800fee88  mov     eax, [rbx+10358h]
0x1800fee8e  lea     r8, unk_18012277F
0x1800fee95  and     eax, 0F93A6004h
0x1800fee9a  mov     rdx, rbx
0x1800fee9d  or      eax, 13A4004h
0x1800feea2  mov     rcx, rdi
0x1800feea5  mov     [rbx+10358h], eax
0x1800feeab  call    isoent_create_virtual_dir
0x1800feeb0  mov     [rbx+0B8h], rax
0x1800feeb7  test    rax, rax
0x1800feeba  jz      loc_1800FEF82
0x1800feec0  mov     [rax+20h], rax
0x1800feec4  lea     rsi, [rbx+20h]
0x1800feec8  mov     rax, [rbx+0B8h]
0x1800feecf  mov     rcx, rsi
0x1800feed2  mov     rdx, r15
0x1800feed5  mov     [rbx+18h], rax
0x1800feed9  mov     [rsi], rbp
0x1800feedc  mov     [rbx+28h], rbp
0x1800feee0  mov     [rbx+30h], rbp
0x1800feee4  call    archive_string_ensure
0x1800feee9  test    rax, rax
0x1800feeec  jz      loc_1800FEF82
0x1800feef2  mov     rax, [rsi]
0x1800feef5  mov     [rax], bpl
0x1800feef8  lea     rax, aIso9660_0; "iso9660"
0x1800feeff  mov     [rbx+78h], rbp
0x1800fef03  mov     [rbx+80h], rbp
0x1800fef0a  mov     [rdi+100h], rax
0x1800fef11  lea     rax, iso9660_options
0x1800fef18  mov     [rdi+110h], rax
0x1800fef1f  lea     rax, iso9660_write_header
0x1800fef26  mov     [rdi+120h], rax
0x1800fef2d  lea     rax, iso9660_write_data
0x1800fef34  mov     [rdi+128h], rax
0x1800fef3b  lea     rax, iso9660_finish_entry
0x1800fef42  mov     [rdi+118h], rax
0x1800fef49  lea     rax, iso9660_close
0x1800fef50  mov     [rdi+130h], rax
0x1800fef57  lea     rax, iso9660_free
0x1800fef5e  mov     [rdi+138h], rax
0x1800fef65  lea     rax, aIso9660; "ISO9660"
0x1800fef6c  mov     [rdi+18h], rax
0x1800fef70  xor     eax, eax
0x1800fef72  mov     [rdi+0F8h], rbx
0x1800fef79  mov     dword ptr [rdi+10h], 40000h
0x1800fef80  jmp     short loc_1800FEFA4
0x1800fef82  mov     rcx, rbx; Block
0x1800fef85  call    cs:__imp_free
0x1800fef8b  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x1800fef92  mov     edx, 0Ch
0x1800fef97  mov     rcx, rdi
0x1800fef9a  call    archive_set_error
0x1800fef9f  mov     eax, 0FFFFFFE2h
0x1800fefa4  add     rsp, 20h
0x1800fefa8  pop     r15
0x1800fefaa  pop     rdi
0x1800fefab  pop     rsi
0x1800fefac  pop     rbp
0x1800fefad  pop     rbx
0x1800fefae  retn
```
