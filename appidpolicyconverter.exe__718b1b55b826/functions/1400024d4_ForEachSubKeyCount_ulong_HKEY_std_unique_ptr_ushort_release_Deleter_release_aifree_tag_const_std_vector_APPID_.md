# ForEachSubKeyCount<ulong (*)(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>> &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>> &,ulong &),std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>> &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>> &,ulong &>(HKEY__ *,ulong,ulong (*const &)(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>> &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>> &,ulong &),std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>> &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>> &,ulong &)

- ea: `0x1400024d4`
- end: `0x140002601`
- name: `??$ForEachSubKeyCount@P6AKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@3@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@AEAV?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@3@AEAK@ZAEAV43@AEAV53@AEAV63@AEAV73@AEAK@@YAKPEAUHKEY__@@KAEBQ6AK0AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@2@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@2@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@AEAV?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@2@AEAK@Z23456@Z`
- size: `301`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD, __int64 (__fastcall **)(HKEY, __int64 *, __int64, __int64, __int64, __int64, __int64), __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400037c8`

## callees

- `0x1400024d4`
- `0x140006fa0`
- `0x140007c18`
- `0x140008ef4`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall ForEachSubKeyCount<unsigned long (*)(HKEY__ *,std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>> &,unsigned long &),std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>> &,unsigned long &>(
        HKEY hKey,
        DWORD a2,
        __int64 (__fastcall **a3)(HKEY, __int64 *, __int64, __int64, __int64, __int64, __int64),
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  DWORD i; // ebx
  unsigned int SubKeyName; // edi
  __int64 v14; // rcx
  unsigned int v16; // ebx
  __int64 v17; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v18[2]; // [rsp+48h] [rbp-10h] BYREF

  for ( i = 0; ; ++i )
  {
    v17 = 0;
    if ( i >= a2 )
      break;
    v18[0] = 0;
    SubKeyName = GetSubKeyName(hKey, i, v18);
    std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>::reset(&v17, v18[0]);
    if ( SubKeyName )
    {
      v14 = v17;
LABEL_9:
      if ( v14 )
        AiFree(v14);
      return SubKeyName;
    }
    SubKeyName = (*a3)(hKey, &v17, a4, a5, a6, a7, a8);
    v14 = v17;
    if ( SubKeyName )
      goto LABEL_9;
    if ( v17 )
      AiFree(v17);
  }
  v18[0] = 0;
  v16 = GetSubKeyName(hKey, i, v18);
  std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>::reset(&v17, v18[0]);
  if ( v16 == 259 )
  {
    if ( v17 )
      AiFree(v17);
    return 0;
  }
  else if ( v16 )
  {
    if ( v17 )
      AiFree(v17);
    return v16;
  }
  else
  {
    if ( v17 )
      AiFree(v17);
    return 1018;
  }
}

```

## disassembly

```asm
0x1400024d4  push    rbp
0x1400024d6  push    rbx
0x1400024d7  push    rsi
0x1400024d8  push    rdi
0x1400024d9  push    r12
0x1400024db  push    r13
0x1400024dd  push    r14
0x1400024df  push    r15
0x1400024e1  mov     rbp, rsp
0x1400024e4  sub     rsp, 58h
0x1400024e8  mov     r15, r9
0x1400024eb  mov     r12, r8
0x1400024ee  mov     r14d, edx
0x1400024f1  mov     rsi, rcx
0x1400024f4  xor     ebx, ebx
0x1400024f6  mov     r13, [rbp+arg_38]
0x1400024fd  mov     [rbp+var_18], 0
0x140002505  cmp     ebx, r14d
0x140002508  jnb     loc_14000258F
0x14000250e  mov     [rbp+var_10], 0
0x140002516  lea     r8, [rbp+var_10]; unsigned __int16 **
0x14000251a  mov     edx, ebx; dwIndex
0x14000251c  mov     rcx, rsi; hKey
0x14000251f  call    ?GetSubKeyName@@YAKPEAUHKEY__@@KPEAPEAG@Z; GetSubKeyName(HKEY__ *,ulong,ushort * *)
0x140002524  mov     edi, eax
0x140002526  mov     rdx, [rbp+var_10]
0x14000252a  lea     rcx, [rbp+var_18]
0x14000252e  call    ?reset@?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>::reset(ushort *)
0x140002533  test    edi, edi
0x140002535  jnz     short loc_14000257D
0x140002537  mov     [rsp+58h+var_28], r13
0x14000253c  mov     rax, [rbp+arg_30]
0x140002540  mov     [rsp+58h+var_30], rax
0x140002545  mov     rax, [rbp+arg_28]
0x140002549  mov     [rsp+58h+var_38], rax
0x14000254e  mov     r9, [rbp+arg_20]
0x140002552  mov     r8, r15
0x140002555  lea     rdx, [rbp+var_18]
0x140002559  mov     rcx, rsi
0x14000255c  mov     rax, [r12]
0x140002560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002565  mov     edi, eax
0x140002567  mov     rcx, [rbp+var_18]
0x14000256b  test    eax, eax
0x14000256d  jnz     short loc_140002581
0x14000256f  test    rcx, rcx
0x140002572  jz      short loc_140002579
0x140002574  call    AiFree
0x140002579  inc     ebx
0x14000257b  jmp     short loc_1400024FD
0x14000257d  mov     rcx, [rbp+var_18]
0x140002581  test    rcx, rcx
0x140002584  jz      short loc_14000258B
0x140002586  call    AiFree
0x14000258b  mov     eax, edi
0x14000258d  jmp     short loc_1400025F0
0x14000258f  mov     [rbp+var_10], 0
0x140002597  lea     r8, [rbp+var_10]; unsigned __int16 **
0x14000259b  mov     edx, ebx; dwIndex
0x14000259d  mov     rcx, rsi; hKey
0x1400025a0  call    ?GetSubKeyName@@YAKPEAUHKEY__@@KPEAPEAG@Z; GetSubKeyName(HKEY__ *,ulong,ushort * *)
0x1400025a5  mov     ebx, eax
0x1400025a7  mov     rdx, [rbp+var_10]
0x1400025ab  lea     rcx, [rbp+var_18]
0x1400025af  call    ?reset@?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>::reset(ushort *)
0x1400025b4  nop
0x1400025b5  mov     rcx, [rbp+var_18]
0x1400025b9  cmp     ebx, 103h
0x1400025bf  jnz     short loc_1400025CF
0x1400025c1  test    rcx, rcx
0x1400025c4  jz      short loc_1400025CB
0x1400025c6  call    AiFree
0x1400025cb  xor     eax, eax
0x1400025cd  jmp     short loc_1400025F0
0x1400025cf  test    ebx, ebx
0x1400025d1  jz      short loc_1400025E1
0x1400025d3  test    rcx, rcx
0x1400025d6  jz      short loc_1400025DD
0x1400025d8  call    AiFree
0x1400025dd  mov     eax, ebx
0x1400025df  jmp     short loc_1400025F0
0x1400025e1  test    rcx, rcx
0x1400025e4  jz      short loc_1400025EB
0x1400025e6  call    AiFree
0x1400025eb  mov     eax, 3FAh
0x1400025f0  add     rsp, 58h
0x1400025f4  pop     r15
0x1400025f6  pop     r14
0x1400025f8  pop     r13
0x1400025fa  pop     r12
0x1400025fc  pop     rdi
0x1400025fd  pop     rsi
0x1400025fe  pop     rbx
0x1400025ff  pop     rbp
0x140002600  retn
```
