# write_information_block

- ea: `0x180105ddc`
- end: `0x18010634f`
- name: `write_information_block`
- size: `1395`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800ffae0`

## callees

- `0x180006c00`
- `0x18000b4d0`
- `0x180014fc0`
- `0x180015810`
- `0x1800aba54`
- `0x1800ee548`
- `0x180104bbc`
- `0x1801051e0`
- `0x1801053a4`
- `0x180105ddc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ctime64_s` at `0x180105e9d`
- `api-ms-win-crt-private-l1-1-0!_o__ctime64_s` at `0x180105e9d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180106312`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180106312`

## string_xrefs

- `0x1801060b0`: `compression-level`
- `0x1801060e1`: `copyright-file`

## pseudocode

```c
__int64 __fastcall write_information_block(__int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax
  int v4; // edx
  const char *v5; // rcx
  const char *v6; // rax
  int v7; // eax
  int v8; // eax
  int v9; // [rsp+30h] [rbp-69h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-61h] BYREF
  __int64 v11; // [rsp+48h] [rbp-51h]
  char v12[128]; // [rsp+50h] [rbp-49h] BYREF

  v1 = *(_QWORD *)(a1 + 248);
  v11 = 0;
  *(_OWORD *)Src = 0;
  if ( *(_QWORD *)(v1 + 66248) >= 0x800u || (result = wb_write_out(), !(_DWORD)result) )
  {
    Src[0] = 0;
    Src[1] = 0;
    v11 = 0;
    if ( archive_string_ensure(Src, 2048) )
    {
      memset_0(Src[0], 0, 0x800u);
      v9 = 0;
      _o__ctime64_s(v12, 128, v1);
      archive_string_sprintf(Src, "INFO %s%s", v12, "libarchive 3.8.4");
      if ( (*(_BYTE *)(v1 + 66392) & 1) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"abstract-file", 1, *(_QWORD *)(v1 + 416));
      if ( (*(_BYTE *)(v1 + 66392) & 2) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"application-id", 1, *(_QWORD *)(v1 + 368));
      if ( (*(_BYTE *)(v1 + 66392) & 4) == 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"allow-vernum", 0, 0);
      if ( (*(_BYTE *)(v1 + 66392) & 8) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"biblio-file", 1, *(_QWORD *)(v1 + 440));
      if ( (*(_BYTE *)(v1 + 66392) & 0x10) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"boot", 1, *(_QWORD *)(v1 + 66320));
      if ( (*(_BYTE *)(v1 + 66392) & 0x20) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"boot-catalog", 1, *(_QWORD *)(v1 + 66288));
      if ( ((*(_DWORD *)(v1 + 66392) >> 6) & 1) != 0 )
        set_option_info(
          (unsigned int)Src,
          (unsigned int)&v9,
          (unsigned int)"boot-info-table",
          0,
          (*(_DWORD *)(v1 + 66392) & 0x40) != 0);
      if ( *(char *)(v1 + 66392) < 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"boot-load-seg", 3, *(_WORD *)(v1 + 66386));
      if ( (*(_DWORD *)(v1 + 66392) & 0x100) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"boot-load-size", 2, *(_WORD *)(v1 + 66388));
      v4 = *(_DWORD *)(v1 + 66392) & 0x600;
      if ( v4 )
      {
        v5 = "fd";
        if ( v4 != 1024 )
          v5 = "no-emulation";
        v6 = "hard-disk";
        if ( v4 != 1536 )
          LOBYTE(v6) = (_BYTE)v5;
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"boot-type", 1, (char)v6);
      }
      if ( (*(_DWORD *)(v1 + 66392) & 0x800) != 0 )
        set_option_info(
          (unsigned int)Src,
          (unsigned int)&v9,
          (unsigned int)"compression-level",
          2,
          *(_DWORD *)(v1 + 688));
      if ( (*(_DWORD *)(v1 + 66392) & 0x1000) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"copyright-file", 1, *(_QWORD *)(v1 + 392));
      if ( ((*(_DWORD *)(v1 + 66392) >> 14) & 7) != 1 )
        set_option_info(
          (unsigned int)Src,
          (unsigned int)&v9,
          (unsigned int)"iso-level",
          2,
          (*(_DWORD *)(v1 + 66392) >> 14) & 7);
      v7 = (*(_DWORD *)(v1 + 66392) >> 17) & 3;
      if ( v7 != 1 )
      {
        if ( v7 == 2 )
          set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"joliet", 1, (char)"long");
        else
          set_option_info(
            (unsigned int)Src,
            (unsigned int)&v9,
            (unsigned int)"joliet",
            0,
            (*(_DWORD *)(v1 + 66392) >> 17) & 3);
      }
      if ( (*(_DWORD *)(v1 + 66392) & 0x80000) == 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"limit-depth", 0, 0);
      if ( (*(_DWORD *)(v1 + 66392) & 0x100000) == 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"limit-dirs", 0, 0);
      if ( (*(_DWORD *)(v1 + 66392) & 0x200000) == 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"pad", 0, 0);
      if ( (*(_DWORD *)(v1 + 66392) & 0x400000) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"publisher", 1, *(_QWORD *)(v1 + 320));
      v8 = *(_DWORD *)(v1 + 66392) & 0x1800000;
      if ( v8 != 0x1000000 )
      {
        if ( v8 )
        {
          if ( v8 == 0x800000 )
            set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"rockridge", 1, (char)"strict");
        }
        else
        {
          set_option_info(
            (unsigned int)Src,
            (unsigned int)&v9,
            (unsigned int)"rockridge",
            0,
            (*(_DWORD *)(v1 + 66392) >> 23) & 3);
        }
      }
      if ( (*(_DWORD *)(v1 + 66392) & 0x2000000) != 0 )
        set_option_info((unsigned int)Src, (unsigned int)&v9, (unsigned int)"volume-id", 1, *(_QWORD *)(v1 + 296));
      if ( ((*(_DWORD *)(v1 + 66392) >> 26) & 1) != 0 )
        set_option_info(
          (unsigned int)Src,
          (unsigned int)&v9,
          (unsigned int)"zisofs",
          0,
          (*(_DWORD *)(v1 + 66392) & 0x4000000) != 0);
      memcpy_0((void *)(*(_QWORD *)(a1 + 248) - *(_QWORD *)(*(_QWORD *)(a1 + 248) + 66248LL) + 66244LL), Src[0], 0x800u);
      Src[1] = 0;
      v11 = 0;
      free(Src[0]);
      Src[0] = 0;
      return wb_consume(a1, 2048);
    }
    else
    {
      archive_set_error(a1, 12, "Can't allocate memory");
      return 4294967266LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180105ddc  mov     [rsp-8+arg_8], rbx
0x180105de1  mov     [rsp-8+arg_10], rsi
0x180105de6  push    rbp
0x180105de7  push    rdi
0x180105de8  push    r12
0x180105dea  lea     rbp, [rsp-47h]
0x180105def  sub     rsp, 0E0h
0x180105df6  mov     rax, cs:__security_cookie
0x180105dfd  xor     rax, rsp
0x180105e00  mov     [rbp+57h+var_20], rax
0x180105e04  mov     rbx, [rcx+0F8h]
0x180105e0b  xor     eax, eax
0x180105e0d  xorps   xmm0, xmm0
0x180105e10  mov     [rbp+57h+var_A8], rax
0x180105e14  mov     r12d, 800h
0x180105e1a  mov     rdi, rcx
0x180105e1d  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180105e21  cmp     [rbx+102C8h], r12
0x180105e28  jnb     short loc_180105E37
0x180105e2a  call    wb_write_out
0x180105e2f  test    eax, eax
0x180105e31  jnz     loc_18010632B
0x180105e37  mov     rdx, r12
0x180105e3a  mov     [rbp+57h+Src], 0
0x180105e42  lea     rcx, [rbp+57h+Src]
0x180105e46  mov     [rbp+57h+Src+8], 0
0x180105e4e  mov     [rbp+57h+var_A8], 0
0x180105e56  call    archive_string_ensure
0x180105e5b  test    rax, rax
0x180105e5e  jnz     short loc_180105E7C
0x180105e60  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x180105e67  mov     rcx, rdi
0x180105e6a  lea     edx, [rax+0Ch]
0x180105e6d  call    archive_set_error
0x180105e72  mov     eax, 0FFFFFFE2h
0x180105e77  jmp     loc_18010632B
0x180105e7c  mov     rcx, [rbp+57h+Src]; void *
0x180105e80  mov     r8, r12; Size
0x180105e83  xor     edx, edx; Val
0x180105e85  call    memset_0
0x180105e8a  mov     r8, rbx
0x180105e8d  mov     [rbp+57h+var_C0], 0
0x180105e94  mov     edx, 80h
0x180105e99  lea     rcx, [rbp+57h+var_A0]
0x180105e9d  call    cs:__imp__o__ctime64_s
0x180105ea3  lea     r9, aLibarchive384; "libarchive 3.8.4"
0x180105eaa  lea     r8, [rbp+57h+var_A0]
0x180105eae  lea     rdx, aInfoSS; "INFO %s%s"
0x180105eb5  lea     rcx, [rbp+57h+Src]
0x180105eb9  call    archive_string_sprintf
0x180105ebe  mov     esi, 1
0x180105ec3  test    [rbx+10358h], sil
0x180105eca  jz      short loc_180105EEF
0x180105ecc  mov     rax, [rbx+1A0h]
0x180105ed3  lea     r8, aAbstractFile_0; "abstract-file"
0x180105eda  mov     r9d, esi
0x180105edd  mov     [rsp+0F0h+var_D0], rax
0x180105ee2  lea     rdx, [rbp+57h+var_C0]
0x180105ee6  lea     rcx, [rbp+57h+Src]
0x180105eea  call    set_option_info
0x180105eef  test    byte ptr [rbx+10358h], 2
0x180105ef6  jz      short loc_180105F1B
0x180105ef8  mov     rax, [rbx+170h]
0x180105eff  lea     r8, aApplicationId; "application-id"
0x180105f06  mov     r9d, esi
0x180105f09  mov     [rsp+0F0h+var_D0], rax
0x180105f0e  lea     rdx, [rbp+57h+var_C0]
0x180105f12  lea     rcx, [rbp+57h+Src]
0x180105f16  call    set_option_info
0x180105f1b  test    byte ptr [rbx+10358h], 4
0x180105f22  jnz     short loc_180105F43
0x180105f24  xor     r9d, r9d
0x180105f27  mov     dword ptr [rsp+0F0h+var_D0], 0
0x180105f2f  lea     r8, aAllowVernum; "allow-vernum"
0x180105f36  lea     rdx, [rbp+57h+var_C0]
0x180105f3a  lea     rcx, [rbp+57h+Src]
0x180105f3e  call    set_option_info
0x180105f43  test    byte ptr [rbx+10358h], 8
0x180105f4a  jz      short loc_180105F6F
0x180105f4c  mov     rax, [rbx+1B8h]
0x180105f53  lea     r8, aBiblioFile; "biblio-file"
0x180105f5a  mov     r9d, esi
0x180105f5d  mov     [rsp+0F0h+var_D0], rax
0x180105f62  lea     rdx, [rbp+57h+var_C0]
0x180105f66  lea     rcx, [rbp+57h+Src]
0x180105f6a  call    set_option_info
0x180105f6f  test    byte ptr [rbx+10358h], 10h
0x180105f76  jz      short loc_180105F9B
0x180105f78  mov     rax, [rbx+10310h]
0x180105f7f  lea     r8, aBoot; "boot"
0x180105f86  mov     r9d, esi
0x180105f89  mov     [rsp+0F0h+var_D0], rax
0x180105f8e  lea     rdx, [rbp+57h+var_C0]
0x180105f92  lea     rcx, [rbp+57h+Src]
0x180105f96  call    set_option_info
0x180105f9b  test    byte ptr [rbx+10358h], 20h
0x180105fa2  jz      short loc_180105FC7
0x180105fa4  mov     rax, [rbx+102F0h]
0x180105fab  lea     r8, aBootCatalog; "boot-catalog"
0x180105fb2  mov     r9d, esi
0x180105fb5  mov     [rsp+0F0h+var_D0], rax
0x180105fba  lea     rdx, [rbp+57h+var_C0]
0x180105fbe  lea     rcx, [rbp+57h+Src]
0x180105fc2  call    set_option_info
0x180105fc7  mov     eax, [rbx+10358h]
0x180105fcd  shr     eax, 6
0x180105fd0  and     eax, esi
0x180105fd2  jz      short loc_180105FEF
0x180105fd4  xor     r9d, r9d
0x180105fd7  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180105fdb  lea     r8, aBootInfoTable; "boot-info-table"
0x180105fe2  lea     rdx, [rbp+57h+var_C0]
0x180105fe6  lea     rcx, [rbp+57h+Src]
0x180105fea  call    set_option_info
0x180105fef  test    byte ptr [rbx+10358h], 80h
0x180105ff6  jz      short loc_18010601D
0x180105ff8  movzx   eax, word ptr [rbx+10352h]
0x180105fff  lea     r8, aBootLoadSeg; "boot-load-seg"
0x180106006  mov     r9d, 3
0x18010600c  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180106010  lea     rdx, [rbp+57h+var_C0]
0x180106014  lea     rcx, [rbp+57h+Src]
0x180106018  call    set_option_info
0x18010601d  test    dword ptr [rbx+10358h], 100h
0x180106027  jz      short loc_18010604E
0x180106029  movzx   eax, word ptr [rbx+10354h]
0x180106030  lea     r8, aBootLoadSize; "boot-load-size"
0x180106037  mov     r9d, 2
0x18010603d  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180106041  lea     rdx, [rbp+57h+var_C0]
0x180106045  lea     rcx, [rbp+57h+Src]
0x180106049  call    set_option_info
0x18010604e  mov     edx, [rbx+10358h]
0x180106054  mov     r8d, 600h
0x18010605a  and     edx, r8d
0x18010605d  jz      short loc_1801060A1
0x18010605f  cmp     edx, 400h
0x180106065  lea     rax, aNoEmulation; "no-emulation"
0x18010606c  lea     rcx, aFd; "fd"
0x180106073  mov     r9d, esi
0x180106076  cmovnz  rcx, rax
0x18010607a  cmp     edx, r8d
0x18010607d  lea     rax, aHardDisk; "hard-disk"
0x180106084  cmovnz  rax, rcx
0x180106088  lea     r8, aBootType; "boot-type"
0x18010608f  lea     rcx, [rbp+57h+Src]
0x180106093  mov     [rsp+0F0h+var_D0], rax
0x180106098  lea     rdx, [rbp+57h+var_C0]
0x18010609c  call    set_option_info
0x1801060a1  test    [rbx+10358h], r12d
0x1801060a8  jz      short loc_1801060CE
0x1801060aa  mov     eax, [rbx+2B0h]
0x1801060b0  lea     r8, aCompressionLev_0; "compression-level"
0x1801060b7  mov     r9d, 2
0x1801060bd  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1801060c1  lea     rdx, [rbp+57h+var_C0]
0x1801060c5  lea     rcx, [rbp+57h+Src]
0x1801060c9  call    set_option_info
0x1801060ce  test    dword ptr [rbx+10358h], 1000h
0x1801060d8  jz      short loc_1801060FD
0x1801060da  mov     rax, [rbx+188h]
0x1801060e1  lea     r8, aCopyrightFile; "copyright-file"
0x1801060e8  mov     r9d, esi
0x1801060eb  mov     [rsp+0F0h+var_D0], rax
0x1801060f0  lea     rdx, [rbp+57h+var_C0]
0x1801060f4  lea     rcx, [rbp+57h+Src]
0x1801060f8  call    set_option_info
0x1801060fd  mov     eax, [rbx+10358h]
0x180106103  shr     eax, 0Eh
0x180106106  and     eax, 7
0x180106109  cmp     eax, esi
0x18010610b  jz      short loc_18010612B
0x18010610d  mov     r9d, 2
0x180106113  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180106117  lea     r8, aIsoLevel; "iso-level"
0x18010611e  lea     rdx, [rbp+57h+var_C0]
0x180106122  lea     rcx, [rbp+57h+Src]
0x180106126  call    set_option_info
0x18010612b  mov     eax, [rbx+10358h]
0x180106131  shr     eax, 11h
0x180106134  and     eax, 3
0x180106137  cmp     eax, esi
0x180106139  jz      short loc_180106171
0x18010613b  lea     r8, aJoliet; "joliet"
0x180106142  lea     rdx, [rbp+57h+var_C0]
0x180106146  lea     rcx, [rbp+57h+Src]
0x18010614a  cmp     eax, 2
0x18010614d  jnz     short loc_180106165
0x18010614f  lea     rax, aLong; "long"
0x180106156  mov     r9d, esi
0x180106159  mov     [rsp+0F0h+var_D0], rax
0x18010615e  call    set_option_info
0x180106163  jmp     short loc_180106171
0x180106165  xor     r9d, r9d
0x180106168  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18010616c  call    set_option_info
0x180106171  test    dword ptr [rbx+10358h], 80000h
0x18010617b  jnz     short loc_18010619C
0x18010617d  xor     r9d, r9d
0x180106180  mov     dword ptr [rsp+0F0h+var_D0], 0
0x180106188  lea     r8, aLimitDepth; "limit-depth"
0x18010618f  lea     rdx, [rbp+57h+var_C0]
0x180106193  lea     rcx, [rbp+57h+Src]
0x180106197  call    set_option_info
0x18010619c  test    dword ptr [rbx+10358h], 100000h
0x1801061a6  jnz     short loc_1801061C7
0x1801061a8  xor     r9d, r9d
0x1801061ab  mov     dword ptr [rsp+0F0h+var_D0], 0
0x1801061b3  lea     r8, aLimitDirs; "limit-dirs"
0x1801061ba  lea     rdx, [rbp+57h+var_C0]
0x1801061be  lea     rcx, [rbp+57h+Src]
0x1801061c2  call    set_option_info
0x1801061c7  test    dword ptr [rbx+10358h], 200000h
0x1801061d1  jnz     short loc_1801061F2
0x1801061d3  xor     r9d, r9d
0x1801061d6  mov     dword ptr [rsp+0F0h+var_D0], 0
0x1801061de  lea     r8, aPad; "pad"
0x1801061e5  lea     rdx, [rbp+57h+var_C0]
0x1801061e9  lea     rcx, [rbp+57h+Src]
0x1801061ed  call    set_option_info
0x1801061f2  test    dword ptr [rbx+10358h], 400000h
0x1801061fc  jz      short loc_180106221
0x1801061fe  mov     rax, [rbx+140h]
0x180106205  lea     r8, aPublisher; "publisher"
0x18010620c  mov     r9d, esi
0x18010620f  mov     [rsp+0F0h+var_D0], rax
0x180106214  lea     rdx, [rbp+57h+var_C0]
0x180106218  lea     rcx, [rbp+57h+Src]
0x18010621c  call    set_option_info
0x180106221  mov     ecx, [rbx+10358h]
0x180106227  mov     eax, ecx
0x180106229  and     eax, 1800000h
0x18010622e  cmp     eax, 1000000h
0x180106233  jz      short loc_180106286
0x180106235  test    eax, eax
0x180106237  jnz     short loc_18010625C
0x180106239  shr     ecx, 17h
0x18010623c  lea     r8, aRockridge; "rockridge"
0x180106243  and     ecx, 3
0x180106246  lea     rdx, [rbp+57h+var_C0]
0x18010624a  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x18010624e  xor     r9d, r9d
0x180106251  lea     rcx, [rbp+57h+Src]
0x180106255  call    set_option_info
0x18010625a  jmp     short loc_180106286
0x18010625c  cmp     eax, 800000h
0x180106261  jnz     short loc_180106286
0x180106263  lea     rax, aStrict; "strict"
0x18010626a  mov     r9d, esi
0x18010626d  lea     r8, aRockridge; "rockridge"
0x180106274  mov     [rsp+0F0h+var_D0], rax
0x180106279  lea     rdx, [rbp+57h+var_C0]
0x18010627d  lea     rcx, [rbp+57h+Src]
0x180106281  call    set_option_info
0x180106286  test    dword ptr [rbx+10358h], 2000000h
0x180106290  jz      short loc_1801062B5
0x180106292  mov     rax, [rbx+128h]
0x180106299  lea     r8, aVolumeId; "volume-id"
0x1801062a0  mov     r9d, esi
0x1801062a3  mov     [rsp+0F0h+var_D0], rax
0x1801062a8  lea     rdx, [rbp+57h+var_C0]
0x1801062ac  lea     rcx, [rbp+57h+Src]
0x1801062b0  call    set_option_info
0x1801062b5  mov     eax, [rbx+10358h]
0x1801062bb  shr     eax, 1Ah
0x1801062be  and     eax, esi
0x1801062c0  jz      short loc_1801062DD
0x1801062c2  xor     r9d, r9d
0x1801062c5  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1801062c9  lea     r8, aZisofs; "zisofs"
0x1801062d0  lea     rdx, [rbp+57h+var_C0]
0x1801062d4  lea     rcx, [rbp+57h+Src]
0x1801062d8  call    set_option_info
0x1801062dd  mov     rcx, [rdi+0F8h]
0x1801062e4  mov     r8, r12; Size
0x1801062e7  mov     rdx, [rbp+57h+Src]; Src
0x1801062eb  sub     rcx, [rcx+102C8h]
0x1801062f2  add     rcx, 102C4h; void *
0x1801062f9  call    memcpy_0
0x1801062fe  mov     rcx, [rbp+57h+Src]; Block
0x180106302  mov     [rbp+57h+Src+8], 0
0x18010630a  mov     [rbp+57h+var_A8], 0
0x180106312  call    cs:__imp_free
0x180106318  mov     rdx, r12
0x18010631b  mov     [rbp+57h+Src], 0
0x180106323  mov     rcx, rdi
0x180106326  call    wb_consume
0x18010632b  mov     rcx, [rbp+57h+var_20]
0x18010632f  xor     rcx, rsp; StackCookie
0x180106332  call    __security_check_cookie
0x180106337  lea     r11, [rsp+0F0h+var_10]
0x18010633f  mov     rbx, [r11+28h]
0x180106343  mov     rsi, [r11+30h]
0x180106347  mov     rsp, r11
0x18010634a  pop     r12
0x18010634c  pop     rdi
0x18010634d  pop     rbp
0x18010634e  retn
```
