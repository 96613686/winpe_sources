# ?__abi_QueryInterface@?QObject@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJAEAVGuid@2@PEAPEAX@Z

- ea: `0x14000eb70`
- end: `0x14000ede1`
- name: `?__abi_QueryInterface@?QObject@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJAEAVGuid@2@PEAPEAX@Z`
- size: `625`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000edf0`
- `0x14000ee00`
- `0x14000ee10`
- `0x14000ee20`
- `0x14000ee30`
- `0x14000ee40`
- `0x14000ee50`
- `0x14000ee60`
- `0x14000ee70`
- `0x14000ee80`

## callees

- `0x140008470`
- `0x14000eb70`
- `0x14000ee90`

## pseudocode

```c
__int64 __fastcall ___abi_QueryInterface__QObject_Platform____Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_2_UE_AAAJAEAVGuid_2_PEAPEAX_Z(
        _QWORD *a1,
        __int64 a2,
        void **a3)
{
  unsigned __int64 v6; // rdx
  __int64 v7; // rax
  unsigned __int64 v8; // rdx

  if ( !*(_DWORD *)a2 )
  {
    if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_13;
    }
    if ( *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
      goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == -1350114592 )
  {
    if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_13;
    }
    if ( *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4] )
      goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == 2120490263
    && *(_DWORD *)(a2 + 4) == 1343316573
    && *(_DWORD *)(a2 + 8) == 500875198
    && *(_DWORD *)(a2 + 12) == 23865584 )
  {
LABEL_18:
    *a3 = a1;
    if ( a1[11] )
    {
      v7 = a1[11];
      goto LABEL_47;
    }
    return 0;
  }
LABEL_13:
  v6 = (unsigned __int64)(a1 + 11);
  if ( (-(__int64)(a1[12] != 0) & (unsigned __int64)(a1 + 11)) != 0
    && *(_DWORD *)a2 == -1796592748
    && *(_DWORD *)(a2 + 4) == 1239476684
    && *(_DWORD *)(a2 + 8) == 1693384640
    && *(_DWORD *)(a2 + 12) == -1873047606 )
  {
    goto LABEL_18;
  }
  if ( *(_DWORD *)a2 != 1272349405 )
  {
    switch ( *(_DWORD *)a2 )
    {
      case 0x30D5A829:
        if ( *(_DWORD *)(a2 + 4) != 1076264868
          || *(_DWORD *)(a2 + 8) != 1540864899
          || *(_DWORD *)(a2 + 12) != -1633071442 )
        {
          goto LABEL_49;
        }
        v8 = (unsigned __int64)(a1 + 3);
        break;
      case 0x38:
        if ( *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
          goto LABEL_49;
        v8 = (unsigned __int64)(a1 + 14);
        break;
      case 0xD35AA93C:
        if ( *(_DWORD *)(a2 + 4) != 899275731 || *(_DWORD *)(a2 + 8) != 931621284 || *(_DWORD *)(a2 + 12) != -960019994 )
          goto LABEL_49;
        v8 = (unsigned __int64)(a1 + 4);
        break;
      default:
        if ( *(_DWORD *)a2 != -392911235
          || *(_DWORD *)(a2 + 4) != 937190348
          || *(_DWORD *)(a2 + 8) != 639045002
          || *(_DWORD *)(a2 + 12) != 975021596 )
        {
          goto LABEL_49;
        }
        v8 = (unsigned __int64)(a1 + 2);
        break;
    }
LABEL_45:
    *a3 = (void *)(v8 & -(__int64)(a1 != 0));
    if ( a1[11] )
    {
      v7 = a1[11];
LABEL_47:
      if ( *(int *)(v7 + 12) >= 0 )
        _InterlockedIncrement((volatile signed __int32 *)(a1[11] + 12LL));
    }
    return 0;
  }
  if ( *(_DWORD *)(a2 + 4) == 1089041748 && *(_DWORD *)(a2 + 8) == 1703058330 && *(_DWORD *)(a2 + 12) == 1652481614 )
  {
    v8 = (unsigned __int64)(a1 + 1);
    goto LABEL_45;
  }
LABEL_49:
  if ( (-(__int64)(a1[12] != 0) & v6) != 0
    && !(unsigned int)__abi_FTMWeakRefData::__abi_QueryInterface(
                        (__abi_FTMWeakRefData *)(v6 & -(__int64)(a1[12] != 0)),
                        (struct Platform::Guid *)a2,
                        a3) )
  {
    return 0;
  }
  return ___abi_QueryInterface__QObject_Platform____WriteOnlyArray_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_2_UE_AAAJAEAVGuid_2_PEAPEAX_Z(
           a1 + 4,
           a2,
           a3);
}

```

## disassembly

```asm
0x14000eb70  mov     [rsp+arg_0], rbx
0x14000eb75  mov     [rsp+arg_8], rsi
0x14000eb7a  push    rdi
0x14000eb7b  sub     rsp, 20h
0x14000eb7f  cmp     dword ptr [rdx], 0
0x14000eb82  mov     rsi, r8
0x14000eb85  mov     rdi, rdx
0x14000eb88  mov     rbx, rcx
0x14000eb8b  jnz     short loc_14000EBB2
0x14000eb8d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000eb93  cmp     [rdx+4], eax
0x14000eb96  jnz     short loc_14000EC04
0x14000eb98  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000eb9e  cmp     [rdx+8], eax
0x14000eba1  jnz     short loc_14000EC04
0x14000eba3  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000eba9  cmp     [rdx+0Ch], eax
0x14000ebac  jz      loc_14000EC40
0x14000ebb2  cmp     dword ptr [rdx], 0AF86E2E0h
0x14000ebb8  jnz     short loc_14000EBDB
0x14000ebba  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x14000ebc0  cmp     [rdx+4], eax
0x14000ebc3  jnz     short loc_14000EC04
0x14000ebc5  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x14000ebcb  cmp     [rdx+8], eax
0x14000ebce  jnz     short loc_14000EC04
0x14000ebd0  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x14000ebd6  cmp     [rdx+0Ch], eax
0x14000ebd9  jz      short loc_14000EC40
0x14000ebdb  cmp     dword ptr [rdx], 7E641D17h
0x14000ebe1  jnz     short loc_14000EC04
0x14000ebe3  mov     eax, cs:dword_14003A064
0x14000ebe9  cmp     [rdx+4], eax
0x14000ebec  jnz     short loc_14000EC04
0x14000ebee  mov     eax, cs:dword_14003A068
0x14000ebf4  cmp     [rdx+8], eax
0x14000ebf7  jnz     short loc_14000EC04
0x14000ebf9  mov     eax, cs:dword_14003A06C
0x14000ebff  cmp     [rdx+0Ch], eax
0x14000ec02  jz      short loc_14000EC40
0x14000ec04  mov     rax, [rcx+60h]
0x14000ec08  lea     rdx, [rcx+58h]
0x14000ec0c  neg     rax
0x14000ec0f  sbb     rax, rax
0x14000ec12  test    rdx, rax
0x14000ec15  jz      short loc_14000EC59
0x14000ec17  cmp     dword ptr [rdi], 94EA2B94h
0x14000ec1d  jnz     short loc_14000EC59
0x14000ec1f  mov     eax, cs:dword_140039C6C
0x14000ec25  cmp     [rdi+4], eax
0x14000ec28  jnz     short loc_14000EC59
0x14000ec2a  mov     eax, cs:dword_140039C70
0x14000ec30  cmp     [rdi+8], eax
0x14000ec33  jnz     short loc_14000EC59
0x14000ec35  mov     eax, cs:dword_140039C74
0x14000ec3b  cmp     [rdi+0Ch], eax
0x14000ec3e  jnz     short loc_14000EC59
0x14000ec40  mov     [r8], rbx
0x14000ec43  mov     rax, [rcx+58h]
0x14000ec47  test    rax, rax
0x14000ec4a  jz      loc_14000EDBE
0x14000ec50  mov     rax, [rcx+58h]
0x14000ec54  jmp     loc_14000ED85
0x14000ec59  cmp     dword ptr [rdi], 4BD682DDh
0x14000ec5f  jnz     short loc_14000EC97
0x14000ec61  mov     eax, cs:dword_14003A074
0x14000ec67  cmp     [rdi+4], eax
0x14000ec6a  jnz     loc_14000ED96
0x14000ec70  mov     eax, cs:dword_14003A078
0x14000ec76  cmp     [rdi+8], eax
0x14000ec79  jnz     loc_14000ED96
0x14000ec7f  mov     eax, cs:dword_14003A07C
0x14000ec85  cmp     [rdi+0Ch], eax
0x14000ec88  jnz     loc_14000ED96
0x14000ec8e  lea     rdx, [rcx+8]
0x14000ec92  jmp     loc_14000ED69
0x14000ec97  cmp     dword ptr [rdi], 30D5A829h
0x14000ec9d  jnz     short loc_14000ECD5
0x14000ec9f  mov     eax, cs:dword_14003A364
0x14000eca5  cmp     [rdi+4], eax
0x14000eca8  jnz     loc_14000ED96
0x14000ecae  mov     eax, cs:dword_14003A368
0x14000ecb4  cmp     [rdi+8], eax
0x14000ecb7  jnz     loc_14000ED96
0x14000ecbd  mov     eax, cs:dword_14003A36C
0x14000ecc3  cmp     [rdi+0Ch], eax
0x14000ecc6  jnz     loc_14000ED96
0x14000eccc  lea     rdx, [rcx+18h]
0x14000ecd0  jmp     loc_14000ED69
0x14000ecd5  cmp     dword ptr [rdi], 38h ; '8'
0x14000ecd8  jnz     short loc_14000ED0D
0x14000ecda  mov     eax, cs:dword_140039C24
0x14000ece0  cmp     [rdi+4], eax
0x14000ece3  jnz     loc_14000ED96
0x14000ece9  mov     eax, cs:dword_140039C28
0x14000ecef  cmp     [rdi+8], eax
0x14000ecf2  jnz     loc_14000ED96
0x14000ecf8  mov     eax, cs:dword_140039C2C
0x14000ecfe  cmp     [rdi+0Ch], eax
0x14000ed01  jnz     loc_14000ED96
0x14000ed07  lea     rdx, [rcx+70h]
0x14000ed0b  jmp     short loc_14000ED69
0x14000ed0d  cmp     dword ptr [rdi], 0D35AA93Ch
0x14000ed13  jnz     short loc_14000ED3C
0x14000ed15  mov     eax, cs:dword_14003A094
0x14000ed1b  cmp     [rdi+4], eax
0x14000ed1e  jnz     short loc_14000ED96
0x14000ed20  mov     eax, cs:dword_14003A098
0x14000ed26  cmp     [rdi+8], eax
0x14000ed29  jnz     short loc_14000ED96
0x14000ed2b  mov     eax, cs:dword_14003A09C
0x14000ed31  cmp     [rdi+0Ch], eax
0x14000ed34  jnz     short loc_14000ED96
0x14000ed36  lea     rdx, [rcx+20h]
0x14000ed3a  jmp     short loc_14000ED69
0x14000ed3c  cmp     dword ptr [rdi], 0E894A67Dh
0x14000ed42  jnz     short loc_14000ED96
0x14000ed44  mov     eax, cs:dword_14003A084
0x14000ed4a  cmp     [rdi+4], eax
0x14000ed4d  jnz     short loc_14000ED96
0x14000ed4f  mov     eax, cs:dword_14003A088
0x14000ed55  cmp     [rdi+8], eax
0x14000ed58  jnz     short loc_14000ED96
0x14000ed5a  mov     eax, cs:dword_14003A08C
0x14000ed60  cmp     [rdi+0Ch], eax
0x14000ed63  jnz     short loc_14000ED96
0x14000ed65  lea     rdx, [rcx+10h]
0x14000ed69  mov     rax, rbx
0x14000ed6c  neg     rax
0x14000ed6f  sbb     rcx, rcx
0x14000ed72  and     rcx, rdx
0x14000ed75  mov     [r8], rcx
0x14000ed78  mov     rax, [rbx+58h]
0x14000ed7c  test    rax, rax
0x14000ed7f  jz      short loc_14000EDBE
0x14000ed81  mov     rax, [rbx+58h]
0x14000ed85  mov     ecx, [rax+0Ch]
0x14000ed88  test    ecx, ecx
0x14000ed8a  js      short loc_14000EDBE
0x14000ed8c  mov     rax, [rbx+58h]
0x14000ed90  lock inc dword ptr [rax+0Ch]
0x14000ed94  jmp     short loc_14000EDBE
0x14000ed96  mov     rax, [rcx+60h]
0x14000ed9a  neg     rax
0x14000ed9d  sbb     rax, rax
0x14000eda0  test    rdx, rax
0x14000eda3  jz      short loc_14000EDC2
0x14000eda5  mov     rax, [rcx+60h]
0x14000eda9  neg     rax
0x14000edac  sbb     rcx, rcx
0x14000edaf  and     rcx, rdx; this
0x14000edb2  mov     rdx, rdi; struct Platform::Guid *
0x14000edb5  call    ?__abi_QueryInterface@__abi_FTMWeakRefData@@QEAAJAEAVGuid@Platform@@PEAPEAX@Z; __abi_FTMWeakRefData::__abi_QueryInterface(Platform::Guid &,void * *)
0x14000edba  test    eax, eax
0x14000edbc  jnz     short loc_14000EDC2
0x14000edbe  xor     eax, eax
0x14000edc0  jmp     short loc_14000EDD1
0x14000edc2  lea     rcx, [rbx+20h]
0x14000edc6  mov     r8, rsi
0x14000edc9  mov     rdx, rdi
0x14000edcc  call    ?__abi_QueryInterface@?QObject@Platform@@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJAEAVGuid@2@PEAPEAX@Z
0x14000edd1  mov     rbx, [rsp+28h+arg_0]
0x14000edd6  mov     rsi, [rsp+28h+arg_8]
0x14000eddb  add     rsp, 20h
0x14000eddf  pop     rdi
0x14000ede0  retn
```
