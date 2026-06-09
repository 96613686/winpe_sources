# ForEachSubKeyCount<ulong (HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<_GUID,std::allocator<_GUID>> &),std::vector<_GUID,std::allocator<_GUID>> &>(HKEY__ *,ulong,ulong (&)(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<_GUID,std::allocator<_GUID>> &),std::vector<_GUID,std::allocator<_GUID>> &)

- ea: `0x1400023d0`
- end: `0x1400024cc`
- name: `??$ForEachSubKeyCount@$$A6AKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@@ZAEAV43@@@YAKPEAUHKEY__@@KA6AK0AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@@Z2@Z`
- size: `252`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400030a0`

## callees

- `0x1400023d0`
- `0x1400036fc`
- `0x140006fa0`
- `0x140007c18`
- `0x140008ef4`

## pseudocode

```c
__int64 __fastcall ForEachSubKeyCount<unsigned long (HKEY__ *,std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>> const &,std::vector<_GUID> &),std::vector<_GUID> &>(
        HKEY hKey,
        DWORD a2,
        __int64 a3,
        __int64 a4)
{
  DWORD i; // ebx
  unsigned int SubKeyName; // edi
  __int64 v9; // rcx
  unsigned int v11; // ebx
  unsigned __int16 *v12[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v13; // [rsp+80h] [rbp+48h] BYREF

  v13 = a3;
  for ( i = 0; ; ++i )
  {
    v13 = 0;
    if ( i >= a2 )
      break;
    v12[0] = 0;
    SubKeyName = GetSubKeyName(hKey, i, v12);
    std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>::reset(&v13, v12[0]);
    if ( SubKeyName )
    {
      v9 = v13;
LABEL_9:
      if ( v9 )
        AiFree(v9);
      return SubKeyName;
    }
    SubKeyName = ConvertOnePolicyId(hKey, &v13, a4);
    v9 = v13;
    if ( SubKeyName )
      goto LABEL_9;
    if ( v13 )
      AiFree(v13);
  }
  v12[0] = 0;
  v11 = GetSubKeyName(hKey, i, v12);
  std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>::reset(&v13, v12[0]);
  if ( v11 == 259 )
  {
    if ( v13 )
      AiFree(v13);
    return 0;
  }
  else if ( v11 )
  {
    if ( v13 )
      AiFree(v13);
    return v11;
  }
  else
  {
    if ( v13 )
      AiFree(v13);
    return 1018;
  }
}

```

## disassembly

```asm
0x1400023d0  mov     [rsp-30h+arg_10], r8
0x1400023d5  push    rbp
0x1400023d6  push    rbx
0x1400023d7  push    rsi
0x1400023d8  push    rdi
0x1400023d9  push    r14
0x1400023db  push    r15
0x1400023dd  mov     rbp, rsp
0x1400023e0  sub     rsp, 38h
0x1400023e4  mov     r15, r9
0x1400023e7  mov     r14d, edx
0x1400023ea  mov     rsi, rcx
0x1400023ed  xor     ebx, ebx
0x1400023ef  mov     [rbp+arg_10], 0
0x1400023f7  cmp     ebx, r14d
0x1400023fa  jnb     short loc_14000245E
0x1400023fc  mov     [rbp+var_18], 0
0x140002404  lea     r8, [rbp+var_18]; unsigned __int16 **
0x140002408  mov     edx, ebx; dwIndex
0x14000240a  mov     rcx, rsi; hKey
0x14000240d  call    ?GetSubKeyName@@YAKPEAUHKEY__@@KPEAPEAG@Z; GetSubKeyName(HKEY__ *,ulong,ushort * *)
0x140002412  mov     edi, eax
0x140002414  mov     rdx, [rbp+var_18]
0x140002418  lea     rcx, [rbp+arg_10]
0x14000241c  call    ?reset@?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>::reset(ushort *)
0x140002421  test    edi, edi
0x140002423  jnz     short loc_14000244C
0x140002425  mov     r8, r15
0x140002428  lea     rdx, [rbp+arg_10]
0x14000242c  mov     rcx, rsi
0x14000242f  call    ?ConvertOnePolicyId@@YAKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@@Z; ConvertOnePolicyId(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<_GUID> &)
0x140002434  mov     edi, eax
0x140002436  mov     rcx, [rbp+arg_10]
0x14000243a  test    eax, eax
0x14000243c  jnz     short loc_140002450
0x14000243e  test    rcx, rcx
0x140002441  jz      short loc_140002448
0x140002443  call    AiFree
0x140002448  inc     ebx
0x14000244a  jmp     short loc_1400023EF
0x14000244c  mov     rcx, [rbp+arg_10]
0x140002450  test    rcx, rcx
0x140002453  jz      short loc_14000245A
0x140002455  call    AiFree
0x14000245a  mov     eax, edi
0x14000245c  jmp     short loc_1400024BF
0x14000245e  mov     [rbp+var_18], 0
0x140002466  lea     r8, [rbp+var_18]; unsigned __int16 **
0x14000246a  mov     edx, ebx; dwIndex
0x14000246c  mov     rcx, rsi; hKey
0x14000246f  call    ?GetSubKeyName@@YAKPEAUHKEY__@@KPEAPEAG@Z; GetSubKeyName(HKEY__ *,ulong,ushort * *)
0x140002474  mov     ebx, eax
0x140002476  mov     rdx, [rbp+var_18]
0x14000247a  lea     rcx, [rbp+arg_10]
0x14000247e  call    ?reset@?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>::reset(ushort *)
0x140002483  nop
0x140002484  mov     rcx, [rbp+arg_10]
0x140002488  cmp     ebx, 103h
0x14000248e  jnz     short loc_14000249E
0x140002490  test    rcx, rcx
0x140002493  jz      short loc_14000249A
0x140002495  call    AiFree
0x14000249a  xor     eax, eax
0x14000249c  jmp     short loc_1400024BF
0x14000249e  test    ebx, ebx
0x1400024a0  jz      short loc_1400024B0
0x1400024a2  test    rcx, rcx
0x1400024a5  jz      short loc_1400024AC
0x1400024a7  call    AiFree
0x1400024ac  mov     eax, ebx
0x1400024ae  jmp     short loc_1400024BF
0x1400024b0  test    rcx, rcx
0x1400024b3  jz      short loc_1400024BA
0x1400024b5  call    AiFree
0x1400024ba  mov     eax, 3FAh
0x1400024bf  add     rsp, 38h
0x1400024c3  pop     r15
0x1400024c5  pop     r14
0x1400024c7  pop     rdi
0x1400024c8  pop     rsi
0x1400024c9  pop     rbx
0x1400024ca  pop     rbp
0x1400024cb  retn
```
