# AhcStoreLoad

- ea: `0x14004b014`
- end: `0x14004b2a2`
- name: `AhcStoreLoad`
- size: `654`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140027b3c`
- `0x1400293c4`

## callees

- `0x140007ad0`
- `0x140026638`
- `0x14003e364`
- `0x14004b014`
- `0x14004b2b0`
- `0x14004b2fc`
- `0x14004b8ac`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14004b0c7`
- `ntoskrnl!RtlComputeCrc32` at `0x14004b0c7`

## string_xrefs

- `0x14004b230`: `Failed to read store entry header [%x]`
- `0x14004b20d`: `Different cache magic value`
- `0x14004b1cc`: `Failed to read key [%x]`

## pseudocode

```c
__int64 __fastcall AhcStoreLoad(__int64 a1, _QWORD *a2)
{
  unsigned __int64 v2; // r15
  unsigned __int64 v3; // r14
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // rdx
  __int64 v9; // r10
  int v10; // eax
  int v11; // ebx
  __int64 v12; // r8
  int v13; // eax
  int inserted; // ebx
  int v15; // eax
  _QWORD *v16; // rdx
  _QWORD *v17; // rax
  bool v18; // zf
  const char *v19; // r9
  __int64 v20; // r8
  __int128 v22; // [rsp+30h] [rbp-10h] BYREF
  __int64 v23; // [rsp+70h] [rbp+30h] BYREF
  _QWORD *v24; // [rsp+78h] [rbp+38h] BYREF

  v2 = a2[1];
  v3 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  while ( 1 )
  {
    v6 = a2[4];
    if ( v6 >= v2 || v3 >= *(_QWORD *)(a1 + 120) )
      break;
    v7 = a2[1];
    if ( v6 > v7 || (v8 = v6 + 12, v6 + 12 < v6) || v8 > v7 )
    {
      v19 = "Failed to read store entry header [%x]";
      v20 = 1510;
      goto LABEL_28;
    }
    v9 = a2[5];
    v10 = *(_DWORD *)(v9 + v6);
    v11 = *(_DWORD *)(v9 + v6 + 4);
    v12 = *(unsigned int *)(v9 + v6 + 8);
    a2[4] = v8;
    if ( v10 != 1936994353 )
    {
      AslLogCallPrintf(1, "AhcStoreLoad", 1519, "Different cache magic value");
      inserted = -1073741823;
      goto LABEL_31;
    }
    if ( v8 + v12 < v8 || v8 + v12 > v7 )
    {
      v19 = "Failed to calculate checksum [%x]";
      v20 = 1534;
LABEL_28:
      inserted = -1073741811;
      AslLogCallPrintf(1, "AhcStoreLoad", v20, v19, -1073741811);
      goto LABEL_31;
    }
    if ( RtlComputeCrc32(0, (PUCHAR)(v9 + v8), v12) != v11 )
    {
      AslLogCallPrintf(1, "AhcStoreLoad", 1539, "Checksum error");
      inserted = -1073741761;
      goto LABEL_31;
    }
    v13 = AhcpStoreKeyLoad((unsigned __int16 *)&v22, a2);
    inserted = v13;
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, "AhcStoreLoad", 1550, "Failed to read key [%x]", v13);
      goto LABEL_31;
    }
    v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(a1 + 168))(&v23, a2);
    inserted = v15;
    if ( v15 < 0 )
    {
      AslLogCallPrintf(1, "AhcStoreLoad", 1560, "Failed to load item [%x]", v15);
      goto LABEL_31;
    }
    inserted = AhcpStoreInsertAvlEntry(&v24, a1, &v22, v23);
    if ( inserted < 0 )
    {
      AslLogCallPrintf(1, "AhcStoreLoad", 1566, "Failed to insert an entry to the AVL store");
      goto LABEL_31;
    }
    v16 = *(_QWORD **)(a1 + 112);
    if ( *v16 != a1 + 104 )
      __fastfail(3u);
    v17 = v24;
    *v24 = a1 + 104;
    v17[1] = v16;
    *v16 = v17;
    v18 = *((_QWORD *)&v22 + 1) == 0;
    *(_QWORD *)(a1 + 112) = v17;
    if ( !v18 )
    {
      AslAnsiStringFree(&v22);
      *(_QWORD *)&v22 = 0;
      *((_QWORD *)&v22 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    }
    if ( v23 )
    {
      (*(void (**)(void))(a1 + 144))();
      v23 = 0;
    }
    ++v3;
  }
  inserted = 0;
LABEL_31:
  if ( v23 )
  {
    (*(void (**)(void))(a1 + 144))();
    v23 = 0;
  }
  if ( *((_QWORD *)&v22 + 1) )
    AhcpStoreKeyDelete(&v22);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14004b014  mov     [rsp-28h+arg_10], rbx
0x14004b019  mov     [rsp-28h+arg_18], rsi
0x14004b01e  push    rbp
0x14004b01f  push    rdi
0x14004b020  push    r13
0x14004b022  push    r14
0x14004b024  push    r15
0x14004b026  mov     rbp, rsp
0x14004b029  sub     rsp, 40h
0x14004b02d  mov     r15, [rdx+8]
0x14004b031  xor     r14d, r14d
0x14004b034  xorps   xmm0, xmm0
0x14004b037  mov     [rbp+arg_8], 0
0x14004b03f  mov     rdi, rdx
0x14004b042  mov     [rbp+arg_0], r14
0x14004b046  mov     rsi, rcx
0x14004b049  lea     r13d, [r14+1]
0x14004b04d  movups  [rbp+var_10], xmm0
0x14004b051  mov     rcx, [rdi+20h]
0x14004b055  cmp     rcx, r15
0x14004b058  jnb     loc_14004B257
0x14004b05e  cmp     r14, [rsi+78h]
0x14004b062  jnb     loc_14004B257
0x14004b068  mov     r9, [rdi+8]
0x14004b06c  cmp     rcx, r9
0x14004b06f  ja      loc_14004B230
0x14004b075  lea     rdx, [rcx+0Ch]
0x14004b079  cmp     rdx, rcx
0x14004b07c  jb      loc_14004B230
0x14004b082  cmp     rdx, r9
0x14004b085  ja      loc_14004B230
0x14004b08b  mov     r10, [rdi+28h]
0x14004b08f  mov     eax, [r10+rcx]
0x14004b093  mov     ebx, [r10+rcx+4]
0x14004b098  mov     r8d, [r10+rcx+8]; Length
0x14004b09d  mov     [rdi+20h], rdx
0x14004b0a1  cmp     eax, 73743031h
0x14004b0a6  jnz     loc_14004B20D
0x14004b0ac  lea     rcx, [rdx+r8]
0x14004b0b0  cmp     rcx, rdx
0x14004b0b3  jb      loc_14004B1FE
0x14004b0b9  cmp     rcx, r9
0x14004b0bc  ja      loc_14004B1FE
0x14004b0c2  add     rdx, r10; Buffer
0x14004b0c5  xor     ecx, ecx; InitialCrc
0x14004b0c7  call    cs:__imp_RtlComputeCrc32
0x14004b0ce  nop     dword ptr [rax+rax+00h]
0x14004b0d3  cmp     eax, ebx
0x14004b0d5  jnz     loc_14004B1DB
0x14004b0db  mov     rdx, rdi
0x14004b0de  lea     rcx, [rbp+var_10]
0x14004b0e2  call    AhcpStoreKeyLoad
0x14004b0e7  mov     ebx, eax
0x14004b0e9  test    eax, eax
0x14004b0eb  js      loc_14004B1C8
0x14004b0f1  mov     rax, [rsi+0A8h]
0x14004b0f8  lea     rcx, [rbp+arg_0]
0x14004b0fc  mov     rdx, rdi
0x14004b0ff  call    _guard_dispatch_icall
0x14004b104  mov     ebx, eax
0x14004b106  test    eax, eax
0x14004b108  js      loc_14004B1B5
0x14004b10e  mov     r9, [rbp+arg_0]
0x14004b112  lea     r8, [rbp+var_10]
0x14004b116  mov     rdx, rsi
0x14004b119  lea     rcx, [rbp+arg_8]
0x14004b11d  call    AhcpStoreInsertAvlEntry
0x14004b122  mov     ebx, eax
0x14004b124  test    eax, eax
0x14004b126  js      short loc_14004B194
0x14004b128  lea     rcx, [rsi+68h]
0x14004b12c  mov     rdx, [rcx+8]
0x14004b130  cmp     [rdx], rcx
0x14004b133  jnz     short loc_14004B18D
0x14004b135  mov     rax, [rbp+arg_8]
0x14004b139  mov     [rax], rcx
0x14004b13c  mov     [rax+8], rdx
0x14004b140  mov     [rdx], rax
0x14004b143  cmp     qword ptr [rbp+var_10+8], 0
0x14004b148  mov     [rcx+8], rax
0x14004b14c  jz      short loc_14004B168
0x14004b14e  lea     rcx, [rbp+var_10]
0x14004b152  call    AslAnsiStringFree
0x14004b157  xorps   xmm0, xmm0
0x14004b15a  movups  [rbp+var_10], xmm0
0x14004b15e  psrldq  xmm0, 8
0x14004b163  movq    qword ptr [rbp+var_10+8], xmm0
0x14004b168  mov     rcx, [rbp+arg_0]
0x14004b16c  test    rcx, rcx
0x14004b16f  jz      short loc_14004B185
0x14004b171  mov     rax, [rsi+90h]
0x14004b178  call    _guard_dispatch_icall
0x14004b17d  mov     [rbp+arg_0], 0
0x14004b185  add     r14, r13
0x14004b188  jmp     loc_14004B051
0x14004b18d  mov     ecx, 3
0x14004b192  int     29h; Win8: RtlFailFast(ecx)
0x14004b194  lea     r9, aFailedToInsert_0; "Failed to insert an entry to the AVL st"...
0x14004b19b  mov     r8d, 61Eh
0x14004b1a1  lea     rdx, aAhcstoreload; "AhcStoreLoad"
0x14004b1a8  mov     ecx, r13d
0x14004b1ab  call    AslLogCallPrintf
0x14004b1b0  jmp     loc_14004B259
0x14004b1b5  mov     [rsp+40h+var_20], eax
0x14004b1b9  lea     r9, aFailedToLoadIt; "Failed to load item [%x]"
0x14004b1c0  mov     r8d, 618h
0x14004b1c6  jmp     short loc_14004B246
0x14004b1c8  mov     [rsp+40h+var_20], eax
0x14004b1cc  lea     r9, aFailedToReadKe; "Failed to read key [%x]"
0x14004b1d3  mov     r8d, 60Eh
0x14004b1d9  jmp     short loc_14004B246
0x14004b1db  lea     r9, aChecksumError; "Checksum error"
0x14004b1e2  mov     r8d, 603h
0x14004b1e8  lea     rdx, aAhcstoreload; "AhcStoreLoad"
0x14004b1ef  mov     ecx, r13d
0x14004b1f2  call    AslLogCallPrintf
0x14004b1f7  mov     ebx, 0C000003Fh
0x14004b1fc  jmp     short loc_14004B259
0x14004b1fe  lea     r9, aFailedToCalcul; "Failed to calculate checksum [%x]"
0x14004b205  mov     r8d, 5FEh
0x14004b20b  jmp     short loc_14004B23D
0x14004b20d  lea     r9, aDifferentCache; "Different cache magic value"
0x14004b214  mov     r8d, 5EFh
0x14004b21a  lea     rdx, aAhcstoreload; "AhcStoreLoad"
0x14004b221  mov     ecx, r13d
0x14004b224  call    AslLogCallPrintf
0x14004b229  mov     ebx, 0C0000001h
0x14004b22e  jmp     short loc_14004B259
0x14004b230  lea     r9, aFailedToReadSt_0; "Failed to read store entry header [%x]"
0x14004b237  mov     r8d, 5E6h
0x14004b23d  mov     ebx, 0C000000Dh
0x14004b242  mov     [rsp+40h+var_20], ebx
0x14004b246  lea     rdx, aAhcstoreload; "AhcStoreLoad"
0x14004b24d  mov     ecx, r13d
0x14004b250  call    AslLogCallPrintf
0x14004b255  jmp     short loc_14004B259
0x14004b257  xor     ebx, ebx
0x14004b259  mov     rcx, [rbp+arg_0]
0x14004b25d  test    rcx, rcx
0x14004b260  jz      short loc_14004B276
0x14004b262  mov     rax, [rsi+90h]
0x14004b269  call    _guard_dispatch_icall
0x14004b26e  mov     [rbp+arg_0], 0
0x14004b276  cmp     qword ptr [rbp+var_10+8], 0
0x14004b27b  jz      short loc_14004B286
0x14004b27d  lea     rcx, [rbp+var_10]
0x14004b281  call    AhcpStoreKeyDelete
0x14004b286  lea     r11, [rsp+40h+var_s0]
0x14004b28b  mov     eax, ebx
0x14004b28d  mov     rbx, [r11+40h]
0x14004b291  mov     rsi, [r11+48h]
0x14004b295  mov     rsp, r11
0x14004b298  pop     r15
0x14004b29a  pop     r14
0x14004b29c  pop     r13
0x14004b29e  pop     rdi
0x14004b29f  pop     rbp
0x14004b2a0  retn
```
