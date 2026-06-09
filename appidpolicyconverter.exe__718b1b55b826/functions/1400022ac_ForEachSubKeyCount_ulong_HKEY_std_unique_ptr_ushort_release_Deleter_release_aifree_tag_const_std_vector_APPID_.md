# ForEachSubKeyCount<ulong (HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,ulong &),std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,ulong &>(HKEY__ *,ulong,ulong (&)(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,ulong &),std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,ulong &)

- ea: `0x1400022ac`
- end: `0x1400023c9`
- name: `??$ForEachSubKeyCount@$$A6AKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@AEAK@ZAEAV43@AEAV53@AEAK@@YAKPEAUHKEY__@@KA6AK0AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@2@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@AEAK@Z234@Z`
- size: `285`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003330`

## callees

- `0x1400022ac`
- `0x1400030a0`
- `0x140006fa0`
- `0x140007c18`
- `0x140008ef4`

## pseudocode

```c
__int64 __fastcall ForEachSubKeyCount<unsigned long (HKEY__ *,std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,unsigned long &),std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,unsigned long &>(
        HKEY hKey,
        DWORD a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  DWORD v8; // ebx
  __int64 v9; // r12
  unsigned int SubKeyName; // edi
  __int64 v11; // rcx
  unsigned int v13; // ebx
  unsigned __int16 *v14[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+80h] [rbp+40h] BYREF

  v15 = a3;
  v8 = 0;
  v9 = a6;
  while ( 1 )
  {
    v15 = 0;
    if ( v8 >= a2 )
      break;
    v14[0] = 0;
    SubKeyName = GetSubKeyName(hKey, v8, v14);
    std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>::reset(&v15, v14[0]);
    if ( SubKeyName )
    {
      v11 = v15;
LABEL_9:
      if ( v11 )
        AiFree(v11);
      return SubKeyName;
    }
    SubKeyName = ConvertOneExecutionCategory(hKey, v9);
    v11 = v15;
    if ( SubKeyName )
      goto LABEL_9;
    if ( v15 )
      AiFree(v15);
    ++v8;
  }
  v14[0] = 0;
  v13 = GetSubKeyName(hKey, v8, v14);
  std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>::reset(&v15, v14[0]);
  if ( v13 == 259 )
  {
    if ( v15 )
      AiFree(v15);
    return 0;
  }
  else if ( v13 )
  {
    if ( v15 )
      AiFree(v15);
    return v13;
  }
  else
  {
    if ( v15 )
      AiFree(v15);
    return 1018;
  }
}

```

## disassembly

```asm
0x1400022ac  mov     [rsp-28h+arg_0], rbx
0x1400022b1  mov     [rsp-28h+arg_8], rsi
0x1400022b6  mov     [rsp-28h+arg_10], r8
0x1400022bb  push    rbp
0x1400022bc  push    rdi
0x1400022bd  push    r12
0x1400022bf  push    r14
0x1400022c1  push    r15
0x1400022c3  mov     rbp, rsp
0x1400022c6  sub     rsp, 40h
0x1400022ca  mov     r15, r9
0x1400022cd  mov     r14d, edx
0x1400022d0  mov     rsi, rcx
0x1400022d3  xor     ebx, ebx
0x1400022d5  mov     r12, [rbp+arg_28]
0x1400022d9  mov     [rbp+arg_10], 0
0x1400022e1  cmp     ebx, r14d
0x1400022e4  jnb     short loc_140002351
0x1400022e6  mov     [rbp+var_10], 0
0x1400022ee  lea     r8, [rbp+var_10]; unsigned __int16 **
0x1400022f2  mov     edx, ebx; dwIndex
0x1400022f4  mov     rcx, rsi; hKey
0x1400022f7  call    ?GetSubKeyName@@YAKPEAUHKEY__@@KPEAPEAG@Z; GetSubKeyName(HKEY__ *,ulong,ushort * *)
0x1400022fc  mov     edi, eax
0x1400022fe  mov     rdx, [rbp+var_10]
0x140002302  lea     rcx, [rbp+arg_10]
0x140002306  call    ?reset@?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>::reset(ushort *)
0x14000230b  test    edi, edi
0x14000230d  jnz     short loc_14000233F
0x14000230f  mov     [rsp+40h+var_20], r12; __int64
0x140002314  mov     r9, [rbp+arg_20]
0x140002318  mov     r8, r15
0x14000231b  lea     rdx, [rbp+arg_10]
0x14000231f  mov     rcx, rsi; hKey
0x140002322  call    ?ConvertOneExecutionCategory@@YAKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@AEAK@Z; ConvertOneExecutionCategory(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,ulong &)
0x140002327  mov     edi, eax
0x140002329  mov     rcx, [rbp+arg_10]
0x14000232d  test    eax, eax
0x14000232f  jnz     short loc_140002343
0x140002331  test    rcx, rcx
0x140002334  jz      short loc_14000233B
0x140002336  call    AiFree
0x14000233b  inc     ebx
0x14000233d  jmp     short loc_1400022D9
0x14000233f  mov     rcx, [rbp+arg_10]
0x140002343  test    rcx, rcx
0x140002346  jz      short loc_14000234D
0x140002348  call    AiFree
0x14000234d  mov     eax, edi
0x14000234f  jmp     short loc_1400023B2
0x140002351  mov     [rbp+var_10], 0
0x140002359  lea     r8, [rbp+var_10]; unsigned __int16 **
0x14000235d  mov     edx, ebx; dwIndex
0x14000235f  mov     rcx, rsi; hKey
0x140002362  call    ?GetSubKeyName@@YAKPEAUHKEY__@@KPEAPEAG@Z; GetSubKeyName(HKEY__ *,ulong,ushort * *)
0x140002367  mov     ebx, eax
0x140002369  mov     rdx, [rbp+var_10]
0x14000236d  lea     rcx, [rbp+arg_10]
0x140002371  call    ?reset@?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>::reset(ushort *)
0x140002376  nop
0x140002377  mov     rcx, [rbp+arg_10]
0x14000237b  cmp     ebx, 103h
0x140002381  jnz     short loc_140002391
0x140002383  test    rcx, rcx
0x140002386  jz      short loc_14000238D
0x140002388  call    AiFree
0x14000238d  xor     eax, eax
0x14000238f  jmp     short loc_1400023B2
0x140002391  test    ebx, ebx
0x140002393  jz      short loc_1400023A3
0x140002395  test    rcx, rcx
0x140002398  jz      short loc_14000239F
0x14000239a  call    AiFree
0x14000239f  mov     eax, ebx
0x1400023a1  jmp     short loc_1400023B2
0x1400023a3  test    rcx, rcx
0x1400023a6  jz      short loc_1400023AD
0x1400023a8  call    AiFree
0x1400023ad  mov     eax, 3FAh
0x1400023b2  mov     rbx, [rsp+40h+arg_0]
0x1400023b7  mov     rsi, [rsp+40h+arg_8]
0x1400023bc  add     rsp, 40h
0x1400023c0  pop     r15
0x1400023c2  pop     r14
0x1400023c4  pop     r12
0x1400023c6  pop     rdi
0x1400023c7  pop     rbp
0x1400023c8  retn
```
