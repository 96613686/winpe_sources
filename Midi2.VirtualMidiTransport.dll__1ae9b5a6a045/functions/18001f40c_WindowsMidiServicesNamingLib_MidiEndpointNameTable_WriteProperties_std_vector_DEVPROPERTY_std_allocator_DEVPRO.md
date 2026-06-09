# WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(std::vector<_DEVPROPERTY,std::allocator<_DEVPROPERTY>> &)

- ea: `0x18001f40c`
- end: `0x18001f7ad`
- name: `?WriteProperties@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJAEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@@Z`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000d9b4`

## callees

- `0x180004688`
- `0x1800046a0`
- `0x18000cbfc`
- `0x1800119f4`
- `0x18001f170`
- `0x18001f2b4`
- `0x18001f340`
- `0x18001f40c`

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
0x18001f40c  mov     [rsp-8+arg_10], rbx
0x18001f411  push    rbp
0x18001f412  push    rsi
0x18001f413  push    rdi
0x18001f414  push    r12
0x18001f416  push    r13
0x18001f418  push    r14
0x18001f41a  push    r15
0x18001f41c  lea     rbp, [rsp-50h]
0x18001f421  sub     rsp, 150h
0x18001f428  mov     r14, rdx
0x18001f42b  mov     rsi, rcx
0x18001f42e  xorps   xmm0, xmm0
0x18001f431  movdqu  xmmword ptr [rsp+180h+Src], xmm0
0x18001f437  xor     r12d, r12d
0x18001f43a  mov     [rsp+180h+var_110], r12
0x18001f43f  mov     rdi, [rcx]
0x18001f442  mov     rbx, [rdi]
0x18001f445  lea     rax, [rsp+180h+Src]
0x18001f44a  mov     [rsp+180h+var_158], rax
0x18001f44f  cmp     rbx, rdi
0x18001f452  jz      loc_18001F52F
0x18001f458  mov     rax, [rbx+28h]
0x18001f45c  movups  xmm0, xmmword ptr [rax]
0x18001f45f  movups  [rbp+80h+var_100], xmm0
0x18001f463  movups  xmm1, xmmword ptr [rax+10h]
0x18001f467  movups  [rbp+80h+var_F0], xmm1
0x18001f46b  movups  xmm0, xmmword ptr [rax+20h]
0x18001f46f  movups  [rbp+80h+var_E0], xmm0
0x18001f473  movups  xmm1, xmmword ptr [rax+30h]
0x18001f477  movups  [rbp+80h+var_D0], xmm1
0x18001f47b  movups  xmm0, xmmword ptr [rax+40h]
0x18001f47f  movups  [rbp+80h+var_C0], xmm0
0x18001f483  movups  xmm1, xmmword ptr [rax+50h]
0x18001f487  movups  [rbp+80h+var_B0], xmm1
0x18001f48b  movups  xmm0, xmmword ptr [rax+60h]
0x18001f48f  movups  [rbp+80h+var_A0], xmm0
0x18001f493  movups  xmm1, xmmword ptr [rax+70h]
0x18001f497  movups  [rbp+80h+var_90], xmm1
0x18001f49b  movups  xmm0, xmmword ptr [rax+80h]
0x18001f4a2  movups  [rbp+80h+var_80], xmm0
0x18001f4a6  movups  xmm1, xmmword ptr [rax+90h]
0x18001f4ad  movups  [rbp+80h+var_70], xmm1
0x18001f4b1  movups  xmm0, xmmword ptr [rax+0A0h]
0x18001f4b8  movups  [rbp+80h+var_60], xmm0
0x18001f4bc  movups  xmm1, xmmword ptr [rax+0B0h]
0x18001f4c3  movups  [rbp+80h+var_50], xmm1
0x18001f4c7  mov     rax, [rax+0C0h]
0x18001f4ce  mov     [rbp+80h+var_40], rax
0x18001f4d2  lea     rdx, [rbp+80h+var_100]
0x18001f4d6  lea     rcx, [rsp+180h+var_158]
0x18001f4db  call    ??4?$back_insert_iterator@V?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@QEAAAEAV01@$$QEAUMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@Z; std::back_insert_iterator<std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator=(WindowsMidiServicesNamingLib::Midi1PortNameEntry &&)
0x18001f4e0  mov     rcx, [rbx+10h]
0x18001f4e4  cmp     [rcx+19h], r12b
0x18001f4e8  jz      short loc_18001F50B
0x18001f4ea  mov     rax, [rbx+8]
0x18001f4ee  jmp     short loc_18001F4FD
0x18001f4f0  cmp     rbx, [rax+10h]
0x18001f4f4  jnz     short loc_18001F503
0x18001f4f6  mov     rbx, rax
0x18001f4f9  mov     rax, [rax+8]
0x18001f4fd  cmp     [rax+19h], r12b
0x18001f501  jz      short loc_18001F4F0
0x18001f503  mov     rbx, rax
0x18001f506  jmp     loc_18001F44F
0x18001f50b  mov     rbx, rcx
0x18001f50e  mov     rcx, [rcx]
0x18001f511  cmp     [rcx+19h], r12b
0x18001f515  jnz     loc_18001F44F
0x18001f51b  mov     rbx, rcx
0x18001f51e  mov     rax, [rcx]
0x18001f521  mov     rcx, rax
0x18001f524  cmp     [rax+19h], r12b
0x18001f528  jz      short loc_18001F51B
0x18001f52a  jmp     loc_18001F44F
0x18001f52f  mov     rdi, [rsi+10h]
0x18001f533  mov     rbx, [rdi]
0x18001f536  lea     rax, [rsp+180h+Src]
0x18001f53b  mov     [rsp+180h+var_158], rax
0x18001f540  cmp     rbx, rdi
0x18001f543  jz      loc_18001F620
0x18001f549  mov     rax, [rbx+28h]
0x18001f54d  movups  xmm0, xmmword ptr [rax]
0x18001f550  movups  [rbp+80h+var_100], xmm0
0x18001f554  movups  xmm1, xmmword ptr [rax+10h]
0x18001f558  movups  [rbp+80h+var_F0], xmm1
0x18001f55c  movups  xmm0, xmmword ptr [rax+20h]
0x18001f560  movups  [rbp+80h+var_E0], xmm0
0x18001f564  movups  xmm1, xmmword ptr [rax+30h]
0x18001f568  movups  [rbp+80h+var_D0], xmm1
0x18001f56c  movups  xmm0, xmmword ptr [rax+40h]
0x18001f570  movups  [rbp+80h+var_C0], xmm0
0x18001f574  movups  xmm1, xmmword ptr [rax+50h]
0x18001f578  movups  [rbp+80h+var_B0], xmm1
0x18001f57c  movups  xmm0, xmmword ptr [rax+60h]
0x18001f580  movups  [rbp+80h+var_A0], xmm0
0x18001f584  movups  xmm1, xmmword ptr [rax+70h]
0x18001f588  movups  [rbp+80h+var_90], xmm1
0x18001f58c  movups  xmm0, xmmword ptr [rax+80h]
0x18001f593  movups  [rbp+80h+var_80], xmm0
0x18001f597  movups  xmm1, xmmword ptr [rax+90h]
0x18001f59e  movups  [rbp+80h+var_70], xmm1
0x18001f5a2  movups  xmm0, xmmword ptr [rax+0A0h]
0x18001f5a9  movups  [rbp+80h+var_60], xmm0
0x18001f5ad  movups  xmm1, xmmword ptr [rax+0B0h]
0x18001f5b4  movups  [rbp+80h+var_50], xmm1
0x18001f5b8  mov     rax, [rax+0C0h]
0x18001f5bf  mov     [rbp+80h+var_40], rax
0x18001f5c3  lea     rdx, [rbp+80h+var_100]
0x18001f5c7  lea     rcx, [rsp+180h+var_158]
0x18001f5cc  call    ??4?$back_insert_iterator@V?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@QEAAAEAV01@$$QEAUMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@Z; std::back_insert_iterator<std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator=(WindowsMidiServicesNamingLib::Midi1PortNameEntry &&)
0x18001f5d1  mov     rcx, [rbx+10h]
0x18001f5d5  cmp     [rcx+19h], r12b
0x18001f5d9  jz      short loc_18001F5FC
0x18001f5db  mov     rax, [rbx+8]
0x18001f5df  jmp     short loc_18001F5EE
0x18001f5e1  cmp     rbx, [rax+10h]
0x18001f5e5  jnz     short loc_18001F5F4
0x18001f5e7  mov     rbx, rax
0x18001f5ea  mov     rax, [rax+8]
0x18001f5ee  cmp     [rax+19h], r12b
0x18001f5f2  jz      short loc_18001F5E1
0x18001f5f4  mov     rbx, rax
0x18001f5f7  jmp     loc_18001F540
0x18001f5fc  mov     rbx, rcx
0x18001f5ff  mov     rcx, [rcx]
0x18001f602  cmp     [rcx+19h], r12b
0x18001f606  jnz     loc_18001F540
0x18001f60c  mov     rbx, rcx
0x18001f60f  mov     rax, [rcx]
0x18001f612  mov     rcx, rax
0x18001f615  cmp     [rax+19h], r12b
0x18001f619  jz      short loc_18001F60C
0x18001f61b  jmp     loc_18001F540
0x18001f620  lea     rdi, [rsi+20h]
0x18001f624  mov     r15, [rdi]
0x18001f627  cmp     r15, [rdi+8]
0x18001f62b  jz      short loc_18001F633
0x18001f62d  mov     [rdi+8], r15
0x18001f631  jmp     short loc_18001F637
0x18001f633  mov     r15, [rdi+8]
0x18001f637  mov     rax, [rsp+180h+Src+8]
0x18001f63c  sub     rax, [rsp+180h+Src]
0x18001f641  sar     rax, 3
0x18001f645  mov     rcx, 8F5C28F5C28F5C29h
0x18001f64f  imul    rax, rcx
0x18001f653  test    rax, rax
0x18001f656  jnz     short loc_18001F660
0x18001f658  mov     al, r12b
0x18001f65b  jmp     loc_18001F70A
0x18001f660  imul    r13, rax, 0C8h
0x18001f667  lea     rsi, [r13+8]
0x18001f66b  mov     byte ptr [rsp+180h+var_160], r12b; int
0x18001f670  mov     rdx, [rdi]
0x18001f673  mov     rcx, r15
0x18001f676  sub     rcx, rdx
0x18001f679  cmp     rsi, rcx
0x18001f67c  jnb     short loc_18001F684
0x18001f67e  lea     rax, [rdx+rsi]
0x18001f682  jmp     short loc_18001F6BB
0x18001f684  jbe     short loc_18001F6BF
0x18001f686  mov     rax, [rdi+10h]
0x18001f68a  sub     rax, rdx
0x18001f68d  cmp     rsi, rax
0x18001f690  jbe     short loc_18001F6A4
0x18001f692  lea     r8, [rsp+180h+var_160]
0x18001f697  mov     rdx, rsi
0x18001f69a  mov     rcx, rdi
0x18001f69d  call    ??$_Resize_reallocate@W4byte@std@@@?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@AEAAX_KAEBW4byte@1@@Z; std::vector<std::byte>::_Resize_reallocate<std::byte>(unsigned __int64,std::byte const &)
0x18001f6a2  jmp     short loc_18001F6BF
0x18001f6a4  mov     rbx, rsi
0x18001f6a7  sub     rbx, rcx
0x18001f6aa  mov     r8, rbx; Size
0x18001f6ad  xor     edx, edx; Val
0x18001f6af  mov     rcx, r15; void *
0x18001f6b2  call    memset_0
0x18001f6b7  lea     rax, [r15+rbx]
0x18001f6bb  mov     [rdi+8], rax
0x18001f6bf  mov     rcx, [rdi]
0x18001f6c2  mov     rax, [rdi+8]
0x18001f6c6  sub     rax, rcx
0x18001f6c9  cmp     rax, rsi
0x18001f6cc  jz      short loc_18001F6F1
0x18001f6ce  mov     rcx, [rbp+88h]; this
0x18001f6d5  mov     r9d, 80004003h; char *
0x18001f6db  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiendpointnaming"...
0x18001f6e2  mov     edx, 1B4h; void *
0x18001f6e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f6ec  jmp     loc_18001F658
0x18001f6f1  mov     [rcx], rsi
0x18001f6f4  mov     rcx, [rdi]
0x18001f6f7  add     rcx, 8; void *
0x18001f6fb  mov     r8, r13; Size
0x18001f6fe  mov     rdx, [rsp+180h+Src]; Src
0x18001f703  call    memcpy_0
0x18001f708  mov     al, 1
0x18001f70a  movups  xmm0, cs:PKEY_MIDI_Midi1PortNameTable
0x18001f711  mov     dword ptr [rsp+180h+var_140+4], r12d
0x18001f716  mov     qword ptr [rsp+180h+var_140+8], r12
0x18001f71b  mov     rdx, [r14+8]
0x18001f71f  movups  [rsp+180h+var_150], xmm0
0x18001f724  test    al, al
0x18001f726  mov     eax, cs:dword_180023FB8
0x18001f72c  mov     dword ptr [rsp+180h+var_140], eax
0x18001f730  jz      short loc_18001F74D
0x18001f732  mov     dword ptr [rsp+180h+var_130], 1003h
0x18001f73a  mov     rcx, [rdi]
0x18001f73d  mov     eax, [rdi+8]
0x18001f740  sub     eax, ecx
0x18001f742  mov     dword ptr [rsp+180h+var_130+4], eax
0x18001f746  mov     qword ptr [rsp+180h+var_130+8], rcx
0x18001f74b  jmp     short loc_18001F757
0x18001f74d  mov     qword ptr [rsp+180h+var_130], r12
0x18001f752  mov     qword ptr [rsp+180h+var_130+8], r12
0x18001f757  cmp     rdx, [r14+10h]
0x18001f75b  jz      short loc_18001F779
0x18001f75d  movups  xmmword ptr [rdx], xmm0
0x18001f760  movups  xmm0, [rsp+180h+var_140]
0x18001f765  movups  xmmword ptr [rdx+10h], xmm0
0x18001f769  movups  xmm1, [rsp+180h+var_130]
0x18001f76e  movups  xmmword ptr [rdx+20h], xmm1
0x18001f772  add     qword ptr [r14+8], 30h ; '0'
0x18001f777  jmp     short loc_18001F786
0x18001f779  lea     r8, [rsp+180h+var_150]
0x18001f77e  mov     rcx, r14
0x18001f781  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x18001f786  lea     rcx, [rsp+180h+Src]
0x18001f78b  call    ??1?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@QEAA@XZ; std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::~vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(void)
0x18001f790  xor     eax, eax
0x18001f792  mov     rbx, [rsp+180h+arg_10]
0x18001f79a  add     rsp, 150h
0x18001f7a1  pop     r15
0x18001f7a3  pop     r14
0x18001f7a5  pop     r13
0x18001f7a7  pop     r12
0x18001f7a9  pop     rdi
0x18001f7aa  pop     rsi
0x18001f7ab  pop     rbp
0x18001f7ac  retn
```
