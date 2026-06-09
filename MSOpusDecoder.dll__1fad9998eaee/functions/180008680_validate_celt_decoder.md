# validate_celt_decoder

- ea: `0x180008680`
- end: `0x180008943`
- name: `validate_celt_decoder`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005aa0`

## callees

- `0x180008680`
- `0x180008950`
- `0x18000a8b0`

## string_xrefs

- `0x1800086b4`: `assertion failed: st->mode == opus_custom_mode_create(48000, 960, NULL)`
- `0x180008869`: `assertion failed: st->postfilter_period >= COMBFILTER_MINPERIOD || st->postfilter_period == 0`
- `0x1800088b0`: `assertion failed: st->postfilter_period_old >= COMBFILTER_MINPERIOD || st->postfilter_period_old == 0`

## pseudocode

```c
__int64 __fastcall validate_celt_decoder(__int64 *a1)
{
  __int64 v1; // rbx
  int v3; // eax
  int v4; // eax
  int v5; // eax
  __int64 result; // rax

  v1 = *a1;
  if ( v1 != opus_custom_mode_create(48000, 960, 0) )
    celt_fatal(
      "assertion failed: st->mode == opus_custom_mode_create(48000, 960, NULL)",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      131);
  if ( *((_DWORD *)a1 + 2) != 120 )
    celt_fatal(
      "assertion failed: st->overlap == 120",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      132);
  if ( *((int *)a1 + 7) > 21 )
    celt_fatal(
      "assertion failed: st->end <= 21",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      133);
  if ( (unsigned int)(*((_DWORD *)a1 + 3) - 1) > 1 )
    celt_fatal(
      "assertion failed: st->channels == 1 || st->channels == 2",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      141);
  if ( (unsigned int)(*((_DWORD *)a1 + 4) - 1) > 1 )
    celt_fatal(
      "assertion failed: st->stream_channels == 1 || st->stream_channels == 2",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      142);
  if ( *((int *)a1 + 5) <= 0 )
    celt_fatal(
      "assertion failed: st->downsample > 0",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      143);
  v3 = *((_DWORD *)a1 + 6);
  if ( v3 && v3 != 17 )
    celt_fatal(
      "assertion failed: st->start == 0 || st->start == 17",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      144);
  if ( *((_DWORD *)a1 + 6) >= *((_DWORD *)a1 + 7) )
    celt_fatal(
      "assertion failed: st->start < st->end",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      145);
  if ( *((int *)a1 + 11) < 0 )
    celt_fatal(
      "assertion failed: st->arch >= 0",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      147);
  if ( *((int *)a1 + 11) > 7 )
    celt_fatal(
      "assertion failed: st->arch <= OPUS_ARCHMASK",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      148);
  if ( *((int *)a1 + 14) > 720 )
    celt_fatal(
      "assertion failed: st->last_pitch_index <= PLC_PITCH_LAG_MAX",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      150);
  v4 = *((_DWORD *)a1 + 14);
  if ( v4 < 100 && v4 )
    celt_fatal(
      "assertion failed: st->last_pitch_index >= PLC_PITCH_LAG_MIN || st->last_pitch_index == 0",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      151);
  if ( *((int *)a1 + 17) >= 1024 )
    celt_fatal(
      "assertion failed: st->postfilter_period < MAX_PERIOD",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      152);
  v5 = *((_DWORD *)a1 + 17);
  if ( v5 < 15 && v5 )
    celt_fatal(
      "assertion failed: st->postfilter_period >= COMBFILTER_MINPERIOD || st->postfilter_period == 0",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      153);
  if ( *((int *)a1 + 18) >= 1024 )
    celt_fatal(
      "assertion failed: st->postfilter_period_old < MAX_PERIOD",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      154);
  result = *((unsigned int *)a1 + 18);
  if ( (int)result < 15 && (_DWORD)result )
    celt_fatal(
      "assertion failed: st->postfilter_period_old >= COMBFILTER_MINPERIOD || st->postfilter_period_old == 0",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      155);
  if ( *((int *)a1 + 21) > 2 )
    celt_fatal(
      "assertion failed: st->postfilter_tapset <= 2",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      156);
  if ( *((int *)a1 + 21) < 0 )
    celt_fatal(
      "assertion failed: st->postfilter_tapset >= 0",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      157);
  if ( *((int *)a1 + 22) > 2 )
    celt_fatal(
      "assertion failed: st->postfilter_tapset_old <= 2",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      158);
  if ( *((int *)a1 + 22) < 0 )
    celt_fatal(
      "assertion failed: st->postfilter_tapset_old >= 0",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\celt_decoder.c",
      159);
  return result;
}

```

## disassembly

```asm
0x180008680  mov     [rsp+arg_0], rbx
0x180008685  push    rdi
0x180008686  sub     rsp, 20h
0x18000868a  mov     rbx, [rcx]
0x18000868d  mov     rdi, rcx
0x180008690  mov     ecx, 0BB80h
0x180008695  xor     r8d, r8d
0x180008698  mov     edx, 3C0h
0x18000869d  call    opus_custom_mode_create
0x1800086a2  cmp     rbx, rax
0x1800086a5  jz      short loc_1800086C0
0x1800086a7  mov     r8d, 83h
0x1800086ad  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800086b4  lea     rcx, aAssertionFaile_29; "assertion failed: st->mode == opus_cust"...
0x1800086bb  call    celt_fatal
0x1800086c0  cmp     dword ptr [rdi+8], 78h ; 'x'
0x1800086c4  jz      short loc_1800086DF
0x1800086c6  mov     r8d, 84h
0x1800086cc  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800086d3  lea     rcx, aAssertionFaile_5; "assertion failed: st->overlap == 120"
0x1800086da  call    celt_fatal
0x1800086df  cmp     dword ptr [rdi+1Ch], 15h
0x1800086e3  jle     short loc_1800086FE
0x1800086e5  mov     r8d, 85h
0x1800086eb  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800086f2  lea     rcx, aAssertionFaile_17; "assertion failed: st->end <= 21"
0x1800086f9  call    celt_fatal
0x1800086fe  mov     eax, [rdi+0Ch]
0x180008701  dec     eax
0x180008703  cmp     eax, 1
0x180008706  jbe     short loc_180008721
0x180008708  mov     r8d, 8Dh
0x18000870e  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x180008715  lea     rcx, aAssertionFaile_10; "assertion failed: st->channels == 1 || "...
0x18000871c  call    celt_fatal
0x180008721  mov     eax, [rdi+10h]
0x180008724  dec     eax
0x180008726  cmp     eax, 1
0x180008729  jbe     short loc_180008744
0x18000872b  mov     r8d, 8Eh
0x180008731  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x180008738  lea     rcx, aAssertionFaile_82; "assertion failed: st->stream_channels ="...
0x18000873f  call    celt_fatal
0x180008744  cmp     dword ptr [rdi+14h], 0
0x180008748  jg      short loc_180008763
0x18000874a  mov     r8d, 8Fh
0x180008750  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x180008757  lea     rcx, aAssertionFaile_32; "assertion failed: st->downsample > 0"
0x18000875e  call    celt_fatal
0x180008763  mov     eax, [rdi+18h]
0x180008766  test    eax, eax
0x180008768  jz      short loc_180008788
0x18000876a  cmp     eax, 11h
0x18000876d  jz      short loc_180008788
0x18000876f  mov     r8d, 90h
0x180008775  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x18000877c  lea     rcx, aAssertionFaile_39; "assertion failed: st->start == 0 || st-"...
0x180008783  call    celt_fatal
0x180008788  mov     eax, [rdi+1Ch]
0x18000878b  cmp     [rdi+18h], eax
0x18000878e  jl      short loc_1800087A9
0x180008790  mov     r8d, 91h
0x180008796  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x18000879d  lea     rcx, aAssertionFaile_63; "assertion failed: st->start < st->end"
0x1800087a4  call    celt_fatal
0x1800087a9  cmp     dword ptr [rdi+2Ch], 0
0x1800087ad  jge     short loc_1800087C8
0x1800087af  mov     r8d, 93h
0x1800087b5  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800087bc  lea     rcx, aAssertionFaile_52; "assertion failed: st->arch >= 0"
0x1800087c3  call    celt_fatal
0x1800087c8  cmp     dword ptr [rdi+2Ch], 7
0x1800087cc  jle     short loc_1800087E7
0x1800087ce  mov     r8d, 94h
0x1800087d4  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800087db  lea     rcx, aAssertionFaile_65; "assertion failed: st->arch <= OPUS_ARCH"...
0x1800087e2  call    celt_fatal
0x1800087e7  cmp     dword ptr [rdi+38h], 2D0h
0x1800087ee  jle     short loc_180008809
0x1800087f0  mov     r8d, 96h
0x1800087f6  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800087fd  lea     rcx, aAssertionFaile_28; "assertion failed: st->last_pitch_index "...
0x180008804  call    celt_fatal
0x180008809  mov     eax, [rdi+38h]
0x18000880c  cmp     eax, 64h ; 'd'
0x18000880f  jge     short loc_18000882E
0x180008811  test    eax, eax
0x180008813  jz      short loc_18000882E
0x180008815  mov     r8d, 97h
0x18000881b  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x180008822  lea     rcx, aAssertionFaile_24; "assertion failed: st->last_pitch_index "...
0x180008829  call    celt_fatal
0x18000882e  cmp     dword ptr [rdi+44h], 400h
0x180008835  jl      short loc_180008850
0x180008837  mov     r8d, 98h
0x18000883d  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x180008844  lea     rcx, aAssertionFaile_85; "assertion failed: st->postfilter_period"...
0x18000884b  call    celt_fatal
0x180008850  mov     eax, [rdi+44h]
0x180008853  cmp     eax, 0Fh
0x180008856  jge     short loc_180008875
0x180008858  test    eax, eax
0x18000885a  jz      short loc_180008875
0x18000885c  mov     r8d, 99h
0x180008862  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x180008869  lea     rcx, aAssertionFaile_13; "assertion failed: st->postfilter_period"...
0x180008870  call    celt_fatal
0x180008875  cmp     dword ptr [rdi+48h], 400h
0x18000887c  jl      short loc_180008897
0x18000887e  mov     r8d, 9Ah
0x180008884  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x18000888b  lea     rcx, aAssertionFaile_40; "assertion failed: st->postfilter_period"...
0x180008892  call    celt_fatal
0x180008897  mov     eax, [rdi+48h]
0x18000889a  cmp     eax, 0Fh
0x18000889d  jge     short loc_1800088BC
0x18000889f  test    eax, eax
0x1800088a1  jz      short loc_1800088BC
0x1800088a3  mov     r8d, 9Bh
0x1800088a9  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800088b0  lea     rcx, aAssertionFaile_83; "assertion failed: st->postfilter_period"...
0x1800088b7  call    celt_fatal
0x1800088bc  cmp     dword ptr [rdi+54h], 2
0x1800088c0  jle     short loc_1800088DB
0x1800088c2  mov     r8d, 9Ch
0x1800088c8  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800088cf  lea     rcx, aAssertionFaile_35; "assertion failed: st->postfilter_tapset"...
0x1800088d6  call    celt_fatal
0x1800088db  cmp     dword ptr [rdi+54h], 0
0x1800088df  jge     short loc_1800088FA
0x1800088e1  mov     r8d, 9Dh
0x1800088e7  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x1800088ee  lea     rcx, aAssertionFaile_49; "assertion failed: st->postfilter_tapset"...
0x1800088f5  call    celt_fatal
0x1800088fa  cmp     dword ptr [rdi+58h], 2
0x1800088fe  jle     short loc_180008919
0x180008900  mov     r8d, 9Eh
0x180008906  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x18000890d  lea     rcx, aAssertionFaile_68; "assertion failed: st->postfilter_tapset"...
0x180008914  call    celt_fatal
0x180008919  cmp     dword ptr [rdi+58h], 0
0x18000891d  jge     short loc_180008938
0x18000891f  mov     r8d, 9Fh
0x180008925  lea     rdx, aDOsObjAmd64fre_3; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x18000892c  lea     rcx, aAssertionFaile_9; "assertion failed: st->postfilter_tapset"...
0x180008933  call    celt_fatal
0x180008938  mov     rbx, [rsp+28h+arg_0]
0x18000893d  add     rsp, 20h
0x180008941  pop     rdi
0x180008942  retn
```
