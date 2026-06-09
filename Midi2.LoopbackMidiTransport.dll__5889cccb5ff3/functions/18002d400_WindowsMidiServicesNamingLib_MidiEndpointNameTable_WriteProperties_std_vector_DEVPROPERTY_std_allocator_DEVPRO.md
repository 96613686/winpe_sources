# WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(std::vector<_DEVPROPERTY,std::allocator<_DEVPROPERTY>> &)

- ea: `0x18002d400`
- end: `0x18002d7a1`
- name: `?WriteProperties@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJAEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@@Z`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18001d454`

## callees

- `0x180004ff4`
- `0x18000500c`
- `0x18001b624`
- `0x18001c188`
- `0x18001c400`
- `0x18002ac74`
- `0x18002ad40`
- `0x18002d400`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(__int64 a1, __int64 a2)
{
  _QWORD **v4; // rdi
  _QWORD *v5; // rbx
  __int128 *v6; // rax
  __int64 **v7; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  _QWORD *v10; // rdi
  _QWORD *v11; // rbx
  __int128 *v12; // rax
  __int64 **v13; // rcx
  __int64 k; // rax
  __int64 *m; // rcx
  _QWORD *v16; // rdi
  char *v17; // r15
  char v18; // al
  size_t v19; // r13
  unsigned __int64 v20; // rsi
  _QWORD *v21; // rdx
  unsigned __int64 v22; // rcx
  char *v23; // rax
  unsigned __int64 v24; // rbx
  _OWORD *v25; // rdx
  __int64 v26; // rcx
  int v28; // [rsp+20h] [rbp-E0h] BYREF
  void **v29; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v30; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v31; // [rsp+40h] [rbp-C0h]
  __int128 v32; // [rsp+50h] [rbp-B0h]
  void *Src[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int128 v35; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+90h] [rbp-70h]
  __int128 v37; // [rsp+A0h] [rbp-60h]
  __int128 v38; // [rsp+B0h] [rbp-50h]
  __int128 v39; // [rsp+C0h] [rbp-40h]
  __int128 v40; // [rsp+D0h] [rbp-30h]
  __int128 v41; // [rsp+E0h] [rbp-20h]
  __int128 v42; // [rsp+F0h] [rbp-10h]
  __int128 v43; // [rsp+100h] [rbp+0h]
  __int128 v44; // [rsp+110h] [rbp+10h]
  __int128 v45; // [rsp+120h] [rbp+20h]
  __int128 v46; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  *(_OWORD *)Src = 0;
  v34 = 0;
  v4 = *(_QWORD ***)a1;
  v5 = **(_QWORD ***)a1;
  v29 = Src;
  while ( v5 != v4 )
  {
    v6 = (__int128 *)v5[5];
    v35 = *v6;
    v36 = v6[1];
    v37 = v6[2];
    v38 = v6[3];
    v39 = v6[4];
    v40 = v6[5];
    v41 = v6[6];
    v42 = v6[7];
    v43 = v6[8];
    v44 = v6[9];
    v45 = v6[10];
    v46 = v6[11];
    v47 = *((_QWORD *)v6 + 24);
    std::back_insert_iterator<std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator=(&v29, &v35);
    v7 = (__int64 **)v5[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = v5[1]; !*(_BYTE *)(i + 25) && v5 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v5 = (_QWORD *)i;
      v5 = (_QWORD *)i;
    }
    else
    {
      v5 = (_QWORD *)v5[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v5 = j;
    }
  }
  v10 = *(_QWORD **)(a1 + 16);
  v11 = (_QWORD *)*v10;
  v29 = Src;
  while ( v11 != v10 )
  {
    v12 = (__int128 *)v11[5];
    v35 = *v12;
    v36 = v12[1];
    v37 = v12[2];
    v38 = v12[3];
    v39 = v12[4];
    v40 = v12[5];
    v41 = v12[6];
    v42 = v12[7];
    v43 = v12[8];
    v44 = v12[9];
    v45 = v12[10];
    v46 = v12[11];
    v47 = *((_QWORD *)v12 + 24);
    std::back_insert_iterator<std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator=(&v29, &v35);
    v13 = (__int64 **)v11[2];
    if ( *((_BYTE *)v13 + 25) )
    {
      for ( k = v11[1]; !*(_BYTE *)(k + 25) && v11 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
        v11 = (_QWORD *)k;
      v11 = (_QWORD *)k;
    }
    else
    {
      v11 = (_QWORD *)v11[2];
      for ( m = *v13; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v11 = m;
    }
  }
  v16 = (_QWORD *)(a1 + 32);
  v17 = *(char **)(a1 + 32);
  if ( v17 == *(char **)(a1 + 40) )
    v17 = *(char **)(a1 + 40);
  else
    *(_QWORD *)(a1 + 40) = v17;
  if ( !(0x8F5C28F5C28F5C29uLL * (((char *)Src[1] - (char *)Src[0]) >> 3)) )
    goto LABEL_27;
  v19 = 8 * (((char *)Src[1] - (char *)Src[0]) >> 3);
  v20 = v19 + 8;
  LOBYTE(v28) = 0;
  v21 = (_QWORD *)*v16;
  v22 = (unsigned __int64)&v17[-*v16];
  if ( v19 + 8 >= v22 )
  {
    if ( v20 <= v22 )
      goto LABEL_35;
    if ( v20 > v16[2] - (_QWORD)v21 )
    {
      std::vector<enum std::byte>::_Resize_reallocate<enum std::byte>(v16, v20, &v28);
      goto LABEL_35;
    }
    v24 = v20 - v22;
    memset_0(v17, 0, v20 - v22);
    v23 = &v17[v24];
  }
  else
  {
    v23 = (char *)v21 + v20;
  }
  v16[1] = v23;
LABEL_35:
  if ( v16[1] - *v16 != v20 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"avcore\\midi2\\libs\\midiendpointnaminglib\\midiendpointnametable.cpp",
      (const char *)0x80004003LL,
      v28);
LABEL_27:
    v18 = 0;
    goto LABEL_38;
  }
  *(_QWORD *)*v16 = v20;
  memcpy_0((void *)(*v16 + 8LL), Src[0], v19);
  v18 = 1;
LABEL_38:
  v25 = *(_OWORD **)(a2 + 8);
  v30 = PKEY_MIDI_Midi1PortNameTable;
  v31 = 0x3C0u;
  if ( v18 )
  {
    LODWORD(v32) = 4099;
    v26 = *v16;
    DWORD1(v32) = *((_DWORD *)v16 + 2) - *v16;
    *((_QWORD *)&v32 + 1) = v26;
  }
  else
  {
    v32 = 0u;
  }
  if ( v25 == *(_OWORD **)(a2 + 16) )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(a2, v25, &v30);
  }
  else
  {
    *v25 = PKEY_MIDI_Midi1PortNameTable;
    v25[1] = v31;
    v25[2] = v32;
    *(_QWORD *)(a2 + 8) += 48LL;
  }
  std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::~vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(Src);
  return 0;
}

```

## disassembly

```asm
0x18002d400  mov     [rsp-8+arg_10], rbx
0x18002d405  push    rbp
0x18002d406  push    rsi
0x18002d407  push    rdi
0x18002d408  push    r12
0x18002d40a  push    r13
0x18002d40c  push    r14
0x18002d40e  push    r15
0x18002d410  lea     rbp, [rsp-50h]
0x18002d415  sub     rsp, 150h
0x18002d41c  mov     r14, rdx
0x18002d41f  mov     rsi, rcx
0x18002d422  xorps   xmm0, xmm0
0x18002d425  movdqu  xmmword ptr [rsp+180h+Src], xmm0
0x18002d42b  xor     r12d, r12d
0x18002d42e  mov     [rsp+180h+var_110], r12
0x18002d433  mov     rdi, [rcx]
0x18002d436  mov     rbx, [rdi]
0x18002d439  lea     rax, [rsp+180h+Src]
0x18002d43e  mov     [rsp+180h+var_158], rax
0x18002d443  cmp     rbx, rdi
0x18002d446  jz      loc_18002D523
0x18002d44c  mov     rax, [rbx+28h]
0x18002d450  movups  xmm0, xmmword ptr [rax]
0x18002d453  movups  [rbp+80h+var_100], xmm0
0x18002d457  movups  xmm1, xmmword ptr [rax+10h]
0x18002d45b  movups  [rbp+80h+var_F0], xmm1
0x18002d45f  movups  xmm0, xmmword ptr [rax+20h]
0x18002d463  movups  [rbp+80h+var_E0], xmm0
0x18002d467  movups  xmm1, xmmword ptr [rax+30h]
0x18002d46b  movups  [rbp+80h+var_D0], xmm1
0x18002d46f  movups  xmm0, xmmword ptr [rax+40h]
0x18002d473  movups  [rbp+80h+var_C0], xmm0
0x18002d477  movups  xmm1, xmmword ptr [rax+50h]
0x18002d47b  movups  [rbp+80h+var_B0], xmm1
0x18002d47f  movups  xmm0, xmmword ptr [rax+60h]
0x18002d483  movups  [rbp+80h+var_A0], xmm0
0x18002d487  movups  xmm1, xmmword ptr [rax+70h]
0x18002d48b  movups  [rbp+80h+var_90], xmm1
0x18002d48f  movups  xmm0, xmmword ptr [rax+80h]
0x18002d496  movups  [rbp+80h+var_80], xmm0
0x18002d49a  movups  xmm1, xmmword ptr [rax+90h]
0x18002d4a1  movups  [rbp+80h+var_70], xmm1
0x18002d4a5  movups  xmm0, xmmword ptr [rax+0A0h]
0x18002d4ac  movups  [rbp+80h+var_60], xmm0
0x18002d4b0  movups  xmm1, xmmword ptr [rax+0B0h]
0x18002d4b7  movups  [rbp+80h+var_50], xmm1
0x18002d4bb  mov     rax, [rax+0C0h]
0x18002d4c2  mov     [rbp+80h+var_40], rax
0x18002d4c6  lea     rdx, [rbp+80h+var_100]
0x18002d4ca  lea     rcx, [rsp+180h+var_158]
0x18002d4cf  call    ??4?$back_insert_iterator@V?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@QEAAAEAV01@$$QEAUMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@Z; std::back_insert_iterator<std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator=(WindowsMidiServicesNamingLib::Midi1PortNameEntry &&)
0x18002d4d4  mov     rcx, [rbx+10h]
0x18002d4d8  cmp     [rcx+19h], r12b
0x18002d4dc  jz      short loc_18002D4FF
0x18002d4de  mov     rax, [rbx+8]
0x18002d4e2  jmp     short loc_18002D4F1
0x18002d4e4  cmp     rbx, [rax+10h]
0x18002d4e8  jnz     short loc_18002D4F7
0x18002d4ea  mov     rbx, rax
0x18002d4ed  mov     rax, [rax+8]
0x18002d4f1  cmp     [rax+19h], r12b
0x18002d4f5  jz      short loc_18002D4E4
0x18002d4f7  mov     rbx, rax
0x18002d4fa  jmp     loc_18002D443
0x18002d4ff  mov     rbx, rcx
0x18002d502  mov     rcx, [rcx]
0x18002d505  cmp     [rcx+19h], r12b
0x18002d509  jnz     loc_18002D443
0x18002d50f  mov     rbx, rcx
0x18002d512  mov     rax, [rcx]
0x18002d515  mov     rcx, rax
0x18002d518  cmp     [rax+19h], r12b
0x18002d51c  jz      short loc_18002D50F
0x18002d51e  jmp     loc_18002D443
0x18002d523  mov     rdi, [rsi+10h]
0x18002d527  mov     rbx, [rdi]
0x18002d52a  lea     rax, [rsp+180h+Src]
0x18002d52f  mov     [rsp+180h+var_158], rax
0x18002d534  cmp     rbx, rdi
0x18002d537  jz      loc_18002D614
0x18002d53d  mov     rax, [rbx+28h]
0x18002d541  movups  xmm0, xmmword ptr [rax]
0x18002d544  movups  [rbp+80h+var_100], xmm0
0x18002d548  movups  xmm1, xmmword ptr [rax+10h]
0x18002d54c  movups  [rbp+80h+var_F0], xmm1
0x18002d550  movups  xmm0, xmmword ptr [rax+20h]
0x18002d554  movups  [rbp+80h+var_E0], xmm0
0x18002d558  movups  xmm1, xmmword ptr [rax+30h]
0x18002d55c  movups  [rbp+80h+var_D0], xmm1
0x18002d560  movups  xmm0, xmmword ptr [rax+40h]
0x18002d564  movups  [rbp+80h+var_C0], xmm0
0x18002d568  movups  xmm1, xmmword ptr [rax+50h]
0x18002d56c  movups  [rbp+80h+var_B0], xmm1
0x18002d570  movups  xmm0, xmmword ptr [rax+60h]
0x18002d574  movups  [rbp+80h+var_A0], xmm0
0x18002d578  movups  xmm1, xmmword ptr [rax+70h]
0x18002d57c  movups  [rbp+80h+var_90], xmm1
0x18002d580  movups  xmm0, xmmword ptr [rax+80h]
0x18002d587  movups  [rbp+80h+var_80], xmm0
0x18002d58b  movups  xmm1, xmmword ptr [rax+90h]
0x18002d592  movups  [rbp+80h+var_70], xmm1
0x18002d596  movups  xmm0, xmmword ptr [rax+0A0h]
0x18002d59d  movups  [rbp+80h+var_60], xmm0
0x18002d5a1  movups  xmm1, xmmword ptr [rax+0B0h]
0x18002d5a8  movups  [rbp+80h+var_50], xmm1
0x18002d5ac  mov     rax, [rax+0C0h]
0x18002d5b3  mov     [rbp+80h+var_40], rax
0x18002d5b7  lea     rdx, [rbp+80h+var_100]
0x18002d5bb  lea     rcx, [rsp+180h+var_158]
0x18002d5c0  call    ??4?$back_insert_iterator@V?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@QEAAAEAV01@$$QEAUMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@Z; std::back_insert_iterator<std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator=(WindowsMidiServicesNamingLib::Midi1PortNameEntry &&)
0x18002d5c5  mov     rcx, [rbx+10h]
0x18002d5c9  cmp     [rcx+19h], r12b
0x18002d5cd  jz      short loc_18002D5F0
0x18002d5cf  mov     rax, [rbx+8]
0x18002d5d3  jmp     short loc_18002D5E2
0x18002d5d5  cmp     rbx, [rax+10h]
0x18002d5d9  jnz     short loc_18002D5E8
0x18002d5db  mov     rbx, rax
0x18002d5de  mov     rax, [rax+8]
0x18002d5e2  cmp     [rax+19h], r12b
0x18002d5e6  jz      short loc_18002D5D5
0x18002d5e8  mov     rbx, rax
0x18002d5eb  jmp     loc_18002D534
0x18002d5f0  mov     rbx, rcx
0x18002d5f3  mov     rcx, [rcx]
0x18002d5f6  cmp     [rcx+19h], r12b
0x18002d5fa  jnz     loc_18002D534
0x18002d600  mov     rbx, rcx
0x18002d603  mov     rax, [rcx]
0x18002d606  mov     rcx, rax
0x18002d609  cmp     [rax+19h], r12b
0x18002d60d  jz      short loc_18002D600
0x18002d60f  jmp     loc_18002D534
0x18002d614  lea     rdi, [rsi+20h]
0x18002d618  mov     r15, [rdi]
0x18002d61b  cmp     r15, [rdi+8]
0x18002d61f  jz      short loc_18002D627
0x18002d621  mov     [rdi+8], r15
0x18002d625  jmp     short loc_18002D62B
0x18002d627  mov     r15, [rdi+8]
0x18002d62b  mov     rax, [rsp+180h+Src+8]
0x18002d630  sub     rax, [rsp+180h+Src]
0x18002d635  sar     rax, 3
0x18002d639  mov     rcx, 8F5C28F5C28F5C29h
0x18002d643  imul    rax, rcx
0x18002d647  test    rax, rax
0x18002d64a  jnz     short loc_18002D654
0x18002d64c  mov     al, r12b
0x18002d64f  jmp     loc_18002D6FE
0x18002d654  imul    r13, rax, 0C8h
0x18002d65b  lea     rsi, [r13+8]
0x18002d65f  mov     byte ptr [rsp+180h+var_160], r12b; int
0x18002d664  mov     rdx, [rdi]
0x18002d667  mov     rcx, r15
0x18002d66a  sub     rcx, rdx
0x18002d66d  cmp     rsi, rcx
0x18002d670  jnb     short loc_18002D678
0x18002d672  lea     rax, [rdx+rsi]
0x18002d676  jmp     short loc_18002D6AF
0x18002d678  jbe     short loc_18002D6B3
0x18002d67a  mov     rax, [rdi+10h]
0x18002d67e  sub     rax, rdx
0x18002d681  cmp     rsi, rax
0x18002d684  jbe     short loc_18002D698
0x18002d686  lea     r8, [rsp+180h+var_160]
0x18002d68b  mov     rdx, rsi
0x18002d68e  mov     rcx, rdi
0x18002d691  call    ??$_Resize_reallocate@W4byte@std@@@?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@AEAAX_KAEBW4byte@1@@Z; std::vector<std::byte>::_Resize_reallocate<std::byte>(unsigned __int64,std::byte const &)
0x18002d696  jmp     short loc_18002D6B3
0x18002d698  mov     rbx, rsi
0x18002d69b  sub     rbx, rcx
0x18002d69e  mov     r8, rbx; Size
0x18002d6a1  xor     edx, edx; Val
0x18002d6a3  mov     rcx, r15; void *
0x18002d6a6  call    memset_0
0x18002d6ab  lea     rax, [r15+rbx]
0x18002d6af  mov     [rdi+8], rax
0x18002d6b3  mov     rcx, [rdi]
0x18002d6b6  mov     rax, [rdi+8]
0x18002d6ba  sub     rax, rcx
0x18002d6bd  cmp     rax, rsi
0x18002d6c0  jz      short loc_18002D6E5
0x18002d6c2  mov     rcx, [rbp+88h]; this
0x18002d6c9  mov     r9d, 80004003h; char *
0x18002d6cf  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiendpointnaming"...
0x18002d6d6  mov     edx, 1B4h; void *
0x18002d6db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d6e0  jmp     loc_18002D64C
0x18002d6e5  mov     [rcx], rsi
0x18002d6e8  mov     rcx, [rdi]
0x18002d6eb  add     rcx, 8; void *
0x18002d6ef  mov     r8, r13; Size
0x18002d6f2  mov     rdx, [rsp+180h+Src]; Src
0x18002d6f7  call    memcpy_0
0x18002d6fc  mov     al, 1
0x18002d6fe  movups  xmm0, cs:PKEY_MIDI_Midi1PortNameTable
0x18002d705  mov     dword ptr [rsp+180h+var_140+4], r12d
0x18002d70a  mov     qword ptr [rsp+180h+var_140+8], r12
0x18002d70f  mov     rdx, [r14+8]
0x18002d713  movups  [rsp+180h+var_150], xmm0
0x18002d718  test    al, al
0x18002d71a  mov     eax, cs:dword_180052200
0x18002d720  mov     dword ptr [rsp+180h+var_140], eax
0x18002d724  jz      short loc_18002D741
0x18002d726  mov     dword ptr [rsp+180h+var_130], 1003h
0x18002d72e  mov     rcx, [rdi]
0x18002d731  mov     eax, [rdi+8]
0x18002d734  sub     eax, ecx
0x18002d736  mov     dword ptr [rsp+180h+var_130+4], eax
0x18002d73a  mov     qword ptr [rsp+180h+var_130+8], rcx
0x18002d73f  jmp     short loc_18002D74B
0x18002d741  mov     qword ptr [rsp+180h+var_130], r12
0x18002d746  mov     qword ptr [rsp+180h+var_130+8], r12
0x18002d74b  cmp     rdx, [r14+10h]
0x18002d74f  jz      short loc_18002D76D
0x18002d751  movups  xmmword ptr [rdx], xmm0
0x18002d754  movups  xmm0, [rsp+180h+var_140]
0x18002d759  movups  xmmword ptr [rdx+10h], xmm0
0x18002d75d  movups  xmm1, [rsp+180h+var_130]
0x18002d762  movups  xmmword ptr [rdx+20h], xmm1
0x18002d766  add     qword ptr [r14+8], 30h ; '0'
0x18002d76b  jmp     short loc_18002D77A
0x18002d76d  lea     r8, [rsp+180h+var_150]
0x18002d772  mov     rcx, r14
0x18002d775  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18002d77a  lea     rcx, [rsp+180h+Src]
0x18002d77f  call    ??1?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@QEAA@XZ; std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::~vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(void)
0x18002d784  xor     eax, eax
0x18002d786  mov     rbx, [rsp+180h+arg_10]
0x18002d78e  add     rsp, 150h
0x18002d795  pop     r15
0x18002d797  pop     r14
0x18002d799  pop     r13
0x18002d79b  pop     r12
0x18002d79d  pop     rdi
0x18002d79e  pop     rsi
0x18002d79f  pop     rbp
0x18002d7a0  retn
```
