# std::vector<STORAGE_USAGE_SCAN_CONFIG,std::allocator<STORAGE_USAGE_SCAN_CONFIG>>::_Emplace_reallocate<STORAGE_USAGE_SCAN_CONFIG>(STORAGE_USAGE_SCAN_CONFIG * const,STORAGE_USAGE_SCAN_CONFIG &&)

- ea: `0x18000f074`
- end: `0x18000f1f3`
- name: `??$_Emplace_reallocate@VSTORAGE_USAGE_SCAN_CONFIG@@@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@AEAAPEAVSTORAGE_USAGE_SCAN_CONFIG@@QEAV2@$$QEAV2@@Z`
- size: `383`
- prototype: `STORAGE_USAGE_SCAN_CONFIG *__fastcall(__int64, __int64, const struct STORAGE_USAGE_SCAN_CONFIG *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180016954`

## callees

- `0x18000eab8`
- `0x18000f074`
- `0x18000f9b0`
- `0x18000fea0`
- `0x1800107a8`
- `0x1800166cc`
- `0x1800167dc`
- `0x180016818`

## pseudocode

```c
STORAGE_USAGE_SCAN_CONFIG *__fastcall std::vector<STORAGE_USAGE_SCAN_CONFIG>::_Emplace_reallocate<STORAGE_USAGE_SCAN_CONFIG>(
        __int64 a1,
        __int64 a2,
        const struct STORAGE_USAGE_SCAN_CONFIG *a3)
{
  __int64 v3; // rbp
  __int64 v5; // rbx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  STORAGE_USAGE_SCAN_CONFIG *v11; // rbp
  STORAGE_USAGE_SCAN_CONFIG *v12; // r11
  const struct STORAGE_USAGE_SCAN_CONFIG *v13; // r8
  const struct STORAGE_USAGE_SCAN_CONFIG *v14; // rdx
  STORAGE_USAGE_SCAN_CONFIG *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  STORAGE_USAGE_SCAN_CONFIG *v18; // r11
  __int128 *v20; // [rsp+20h] [rbp-68h] BYREF
  __int64 v21; // [rsp+30h] [rbp-58h]
  STORAGE_USAGE_SCAN_CONFIG *v22; // [rsp+38h] [rbp-50h]
  char *v23; // [rsp+40h] [rbp-48h]

  v3 = STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings;
  v5 = 0x38E38E38E38E38ELL;
  v7 = 0x8E38E38E38E38E39uLL
     * ((__int64)(*((_QWORD *)&STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 1)
                - STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings) >> 3);
  if ( v7 == 0x38E38E38E38E38ELL )
    std::vector<std::pair<STORAGE_USAGE_SCAN_ARGS,__int64>>::_Xlength();
  v8 = v7 + 1;
  v9 = (0x8E38E38E38E38E39uLL * ((qword_180040628 - (__int64)STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings) >> 3)) >> 1;
  if ( 0x8E38E38E38E38E39uLL * ((qword_180040628 - (__int64)STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings) >> 3) <= 0x38E38E38E38E38ELL - v9 )
  {
    v10 = v7 + 1;
    if ( v9
       - 0x71C71C71C71C71C7LL * ((qword_180040628 - (__int64)STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings) >> 3) >= v8 )
      v10 = v9
          - 0x71C71C71C71C71C7LL
          * ((qword_180040628 - (__int64)STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings) >> 3);
    if ( v10 > 0x38E38E38E38E38ELL )
      std::_Throw_bad_array_new_length();
    v5 = v10;
  }
  v21 = v5;
  v20 = &STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings;
  v11 = (STORAGE_USAGE_SCAN_CONFIG *)&std::_Allocate<16,std::_Default_allocate_traits>(72 * v5)[9 * ((a2 - v3) / 72)];
  v23 = (char *)v11 + 72;
  STORAGE_USAGE_SCAN_CONFIG::STORAGE_USAGE_SCAN_CONFIG(v11, a3);
  v13 = (const struct STORAGE_USAGE_SCAN_CONFIG *)*((_QWORD *)&STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 1);
  v22 = v11;
  if ( a2 == *((_QWORD *)&STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 1) )
  {
    v14 = (const struct STORAGE_USAGE_SCAN_CONFIG *)STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings;
    v15 = v12;
    while ( v14 != v13 )
    {
      STORAGE_USAGE_SCAN_CONFIG::STORAGE_USAGE_SCAN_CONFIG(v15, v14);
      v15 = (STORAGE_USAGE_SCAN_CONFIG *)(v16 + 72);
      v14 = (const struct STORAGE_USAGE_SCAN_CONFIG *)(v17 + 72);
    }
  }
  else
  {
    std::_Uninitialized_move<STORAGE_USAGE_SCAN_CONFIG *>(STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings, a2, v12);
    v22 = v18;
    std::_Uninitialized_move<STORAGE_USAGE_SCAN_CONFIG *>(
      a2,
      *((_QWORD *)&STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 1),
      (char *)v11 + 72);
  }
  std::vector<STORAGE_USAGE_SCAN_CONFIG>::_Change_array(v15, v12, v8, v5, v20, 0, v21);
  std::vector<STORAGE_USAGE_SCAN_CONFIG>::_Reallocation_guard::~_Reallocation_guard(&v20);
  return v11;
}

```

## disassembly

```asm
0x18000f074  push    rbx
0x18000f076  push    rbp
0x18000f077  push    rsi
0x18000f078  push    rdi
0x18000f079  push    r14
0x18000f07b  push    r15
0x18000f07d  sub     rsp, 58h
0x18000f081  mov     rbp, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18000f088  mov     rsi, rdx
0x18000f08b  mov     rax, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A+8; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18000f092  mov     rdx, 8E38E38E38E38E39h
0x18000f09c  sub     rax, rbp
0x18000f09f  mov     rbx, 38E38E38E38E38Eh
0x18000f0a9  sar     rax, 3
0x18000f0ad  mov     r15, r8
0x18000f0b0  imul    rax, rdx
0x18000f0b4  cmp     rax, rbx
0x18000f0b7  jz      loc_18000F1ED
0x18000f0bd  mov     rcx, cs:qword_180040628
0x18000f0c4  lea     rdi, [rax+1]
0x18000f0c8  sub     rcx, rbp
0x18000f0cb  mov     rax, rbx
0x18000f0ce  sar     rcx, 3
0x18000f0d2  imul    rcx, rdx
0x18000f0d6  mov     rdx, rcx
0x18000f0d9  shr     rdx, 1
0x18000f0dc  sub     rax, rdx
0x18000f0df  cmp     rcx, rax
0x18000f0e2  ja      short loc_18000F0FE
0x18000f0e4  lea     rax, [rdx+rcx]
0x18000f0e8  mov     rcx, rdi
0x18000f0eb  cmp     rax, rdi
0x18000f0ee  cmovnb  rcx, rax
0x18000f0f2  cmp     rcx, rbx
0x18000f0f5  ja      loc_18000F1E7
0x18000f0fb  mov     rbx, rcx
0x18000f0fe  lea     rcx, [rbx+rbx*8]
0x18000f102  shl     rcx, 3
0x18000f106  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000f10b  mov     r11, rax
0x18000f10e  mov     [rsp+88h+var_58], rbx
0x18000f113  mov     rcx, rsi
0x18000f116  mov     rax, 0E38E38E38E38E39h
0x18000f120  sub     rcx, rbp
0x18000f123  imul    rcx
0x18000f126  lea     rax, ?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18000f12d  sar     rdx, 2
0x18000f131  mov     rcx, rdx
0x18000f134  mov     [rsp+88h+var_68], rax
0x18000f139  shr     rcx, 3Fh
0x18000f13d  add     rdx, rcx
0x18000f140  lea     rcx, [rdx+rdx*8]
0x18000f144  mov     rdx, r15; struct STORAGE_USAGE_SCAN_CONFIG *
0x18000f147  lea     rbp, [r11+rcx*8]
0x18000f14b  lea     r14, [rbp+48h]
0x18000f14f  mov     rcx, rbp; this
0x18000f152  mov     [rsp+88h+var_48], r14
0x18000f157  call    ??0STORAGE_USAGE_SCAN_CONFIG@@QEAA@AEBV0@@Z; STORAGE_USAGE_SCAN_CONFIG::STORAGE_USAGE_SCAN_CONFIG(STORAGE_USAGE_SCAN_CONFIG const &)
0x18000f15c  mov     r8, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A+8; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18000f163  mov     [rsp+88h+var_50], rbp
0x18000f168  cmp     rsi, r8
0x18000f16b  jnz     short loc_18000F18D
0x18000f16d  mov     rdx, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18000f174  mov     rcx, r11
0x18000f177  jmp     short loc_18000F186
0x18000f179  call    ??0STORAGE_USAGE_SCAN_CONFIG@@QEAA@AEBV0@@Z; STORAGE_USAGE_SCAN_CONFIG::STORAGE_USAGE_SCAN_CONFIG(STORAGE_USAGE_SCAN_CONFIG const &)
0x18000f17e  add     rcx, 48h ; 'H'; this
0x18000f182  add     rdx, 48h ; 'H'; struct STORAGE_USAGE_SCAN_CONFIG *
0x18000f186  cmp     rdx, r8
0x18000f189  jnz     short loc_18000F179
0x18000f18b  jmp     short loc_18000F1B6
0x18000f18d  mov     rcx, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18000f194  mov     r8, r11
0x18000f197  mov     rdx, rsi
0x18000f19a  call    ??$_Uninitialized_move@PEAVSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@YAPEAVSTORAGE_USAGE_SCAN_CONFIG@@QEAV1@0PEAV1@AEAV?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@0@@Z; std::_Uninitialized_move<STORAGE_USAGE_SCAN_CONFIG *>(STORAGE_USAGE_SCAN_CONFIG * const,STORAGE_USAGE_SCAN_CONFIG * const,STORAGE_USAGE_SCAN_CONFIG *,std::allocator<STORAGE_USAGE_SCAN_CONFIG> &)
0x18000f19f  mov     rdx, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A+8; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18000f1a6  mov     r8, r14
0x18000f1a9  mov     rcx, rsi
0x18000f1ac  mov     [rsp+88h+var_50], r11
0x18000f1b1  call    ??$_Uninitialized_move@PEAVSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@YAPEAVSTORAGE_USAGE_SCAN_CONFIG@@QEAV1@0PEAV1@AEAV?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@0@@Z; std::_Uninitialized_move<STORAGE_USAGE_SCAN_CONFIG *>(STORAGE_USAGE_SCAN_CONFIG * const,STORAGE_USAGE_SCAN_CONFIG * const,STORAGE_USAGE_SCAN_CONFIG *,std::allocator<STORAGE_USAGE_SCAN_CONFIG> &)
0x18000f1b6  mov     r9, rbx
0x18000f1b9  mov     [rsp+88h+var_60], 0
0x18000f1c2  mov     r8, rdi
0x18000f1c5  mov     rdx, r11
0x18000f1c8  call    ?_Change_array@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@AEAAXQEAVSTORAGE_USAGE_SCAN_CONFIG@@_K1@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::_Change_array(STORAGE_USAGE_SCAN_CONFIG * const,unsigned __int64,unsigned __int64)
0x18000f1cd  lea     rcx, [rsp+88h+var_68]
0x18000f1d2  call    ??1_Reallocation_guard@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAA@XZ; std::vector<STORAGE_USAGE_SCAN_CONFIG>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000f1d7  mov     rax, rbp
0x18000f1da  add     rsp, 58h
0x18000f1de  pop     r15
0x18000f1e0  pop     r14
0x18000f1e2  pop     rdi
0x18000f1e3  pop     rsi
0x18000f1e4  pop     rbp
0x18000f1e5  pop     rbx
0x18000f1e6  retn
0x18000f1e7  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000f1ed  call    ?_Xlength@?$vector@U?$pair@USTORAGE_USAGE_SCAN_ARGS@@_J@std@@V?$allocator@U?$pair@USTORAGE_USAGE_SCAN_ARGS@@_J@std@@@2@@std@@CAXXZ; std::vector<std::pair<STORAGE_USAGE_SCAN_ARGS,__int64>>::_Xlength(void)
```
