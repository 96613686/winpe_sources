# BfCombinedMappingLookup

- ea: `0x140017920`
- end: `0x140017bb2`
- name: `BfCombinedMappingLookup`
- size: `658`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013864`
- `0x140014324`
- `0x1400157a0`

## callees

- `0x140001348`
- `0x140014a70`
- `0x140017920`
- `0x1400194b0`

## pseudocode

```c
__int64 __fastcall BfCombinedMappingLookup(
        __int64 **a1,
        __int64 **a2,
        __int64 **a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7,
        __int64 a8,
        int *a9)
{
  __int64 v9; // rsi
  int v10; // ebx
  char v11; // r12
  int v12; // edi
  __int64 v13; // r13
  int v17; // eax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  __int64 **v21; // rcx
  __int64 *v22; // rax
  __int64 **v24; // rcx
  __int64 *v25; // rax
  __int64 **v26; // rcx
  __int64 *v27; // rax
  int v28; // r9d
  char v29; // [rsp+30h] [rbp-58h]
  int v30; // [rsp+38h] [rbp-50h]
  int v31; // [rsp+38h] [rbp-50h]
  __int64 *v32; // [rsp+A0h] [rbp+18h] BYREF

  v9 = a8;
  v10 = 0;
  v11 = a7;
  v12 = 0;
  v13 = a5;
  v32 = 0;
  if ( a3 )
  {
    v17 = BfMappingLookup(a3, a4, a5, 0, a7, (__int64 *)&v32);
    v10 = v17;
    if ( v17 >= 0 )
    {
      v21 = *(__int64 ***)(v9 + 8);
      if ( *v21 != (__int64 *)v9 )
        goto LABEL_16;
      v22 = v32;
      v12 = 1;
      *v32 = v9;
      v22[1] = (__int64)v21;
      *v21 = v22;
      *(_QWORD *)(v9 + 8) = v22;
      if ( (*(_DWORD *)(v22[4] + 8) & 2) == 0 )
        goto LABEL_12;
    }
    else if ( v17 != -1073741766 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v30 = v17;
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          8,
          76,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          111,
          v30);
      }
      goto LABEL_9;
    }
  }
  if ( a2 )
  {
    v10 = BfMappingLookup(a2, a4, v13, 0, v11, (__int64 *)&v32);
    if ( v10 < 0 )
    {
      if ( v10 != -1073741766 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_8;
        v31 = v10;
        v28 = 77;
        v29 = -112;
        goto LABEL_28;
      }
    }
    else
    {
      v26 = *(__int64 ***)(v9 + 8);
      if ( *v26 != (__int64 *)v9 )
        goto LABEL_16;
      v27 = v32;
      ++v12;
      *v32 = v9;
      v27[1] = (__int64)v26;
      *v26 = v27;
      *(_QWORD *)(v9 + 8) = v27;
      if ( (*(_DWORD *)(v27[4] + 8) & 2) == 0 )
        goto LABEL_8;
    }
  }
  if ( !a1 )
    goto LABEL_8;
  v19 = BfMappingLookup(a1, a4, v13, 0, v11, (__int64 *)&v32);
  v10 = v19;
  if ( v19 >= 0 )
  {
    v24 = *(__int64 ***)(v9 + 8);
    if ( *v24 == (__int64 *)v9 )
    {
      v25 = v32;
      ++v12;
      *v32 = v9;
      v25[1] = (__int64)v24;
      *v24 = v25;
      *(_QWORD *)(v9 + 8) = v25;
      goto LABEL_8;
    }
LABEL_16:
    __fastfail(3u);
  }
  if ( v19 != -1073741766 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v31 = v19;
    v28 = 78;
    v29 = -79;
LABEL_28:
    LOBYTE(v20) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      8,
      v28,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v29,
      v31);
  }
LABEL_8:
  if ( v12 )
  {
LABEL_12:
    v10 = 0;
    *a9 = v12;
    return (unsigned int)v10;
  }
LABEL_9:
  BfFreeMappingLookupList(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140017920  mov     r11, rsp
0x140017923  push    rbx
0x140017924  push    rbp
0x140017925  push    rsi
0x140017926  push    rdi
0x140017927  push    r12
0x140017929  push    r13
0x14001792b  push    r14
0x14001792d  push    r15
0x14001792f  sub     rsp, 48h
0x140017933  mov     rsi, [rsp+88h+arg_38]
0x14001793b  xor     ebx, ebx
0x14001793d  movzx   r12d, [rsp+88h+arg_30]
0x140017946  xor     edi, edi
0x140017948  mov     r13, [rsp+88h+arg_20]
0x140017950  mov     r15, r9
0x140017953  mov     [r11+18h], rbx
0x140017957  mov     rax, r8
0x14001795a  mov     r14, rdx
0x14001795d  mov     rbp, rcx
0x140017960  test    r8, r8
0x140017963  jz      short loc_140017993
0x140017965  lea     rcx, [r11+18h]
0x140017969  xor     r9d, r9d
0x14001796c  mov     [r11-60h], rcx
0x140017970  mov     r8, r13
0x140017973  mov     rcx, rax
0x140017976  mov     [r11-68h], r12b
0x14001797a  mov     rdx, r15
0x14001797d  call    BfMappingLookup
0x140017982  mov     ebx, eax
0x140017984  test    eax, eax
0x140017986  jns     short loc_1400179E4
0x140017988  cmp     eax, 0C000003Ah
0x14001798d  jnz     loc_140017AC8
0x140017993  test    r14, r14
0x140017996  jnz     loc_140017A65
0x14001799c  test    rbp, rbp
0x14001799f  jz      short loc_1400179D5
0x1400179a1  lea     rax, [rsp+88h+arg_10]
0x1400179a9  xor     r9d, r9d
0x1400179ac  mov     [rsp+88h+var_60], rax
0x1400179b1  mov     r8, r13
0x1400179b4  mov     rdx, r15
0x1400179b7  mov     byte ptr [rsp+88h+var_68], r12b
0x1400179bc  mov     rcx, rbp
0x1400179bf  call    BfMappingLookup
0x1400179c4  mov     ebx, eax
0x1400179c6  test    eax, eax
0x1400179c8  jns     short loc_140017A38
0x1400179ca  cmp     eax, 0C000003Ah
0x1400179cf  jnz     loc_140017B57
0x1400179d5  cmp     edi, 1
0x1400179d8  jnb     short loc_140017A18
0x1400179da  mov     rcx, rsi
0x1400179dd  call    BfFreeMappingLookupList
0x1400179e2  jmp     short loc_140017A24
0x1400179e4  mov     rcx, [rsi+8]
0x1400179e8  cmp     [rcx], rsi
0x1400179eb  jnz     short loc_140017A5E
0x1400179ed  mov     rax, [rsp+88h+arg_10]
0x1400179f5  mov     edi, 1
0x1400179fa  mov     [rax], rsi
0x1400179fd  mov     [rax+8], rcx
0x140017a01  mov     [rcx], rax
0x140017a04  mov     [rsi+8], rax
0x140017a08  mov     rax, [rax+20h]
0x140017a0c  mov     ecx, [rax+8]
0x140017a0f  test    cl, 2
0x140017a12  jnz     loc_140017993
0x140017a18  mov     rax, [rsp+88h+arg_40]
0x140017a20  xor     ebx, ebx
0x140017a22  mov     [rax], edi
0x140017a24  mov     eax, ebx
0x140017a26  add     rsp, 48h
0x140017a2a  pop     r15
0x140017a2c  pop     r14
0x140017a2e  pop     r13
0x140017a30  pop     r12
0x140017a32  pop     rdi
0x140017a33  pop     rsi
0x140017a34  pop     rbp
0x140017a35  pop     rbx
0x140017a36  retn
0x140017a38  mov     rcx, [rsi+8]
0x140017a3c  cmp     [rcx], rsi
0x140017a3f  jnz     short loc_140017A5E
0x140017a41  mov     rax, [rsp+88h+arg_10]
0x140017a49  inc     edi
0x140017a4b  mov     [rax], rsi
0x140017a4e  mov     [rax+8], rcx
0x140017a52  mov     [rcx], rax
0x140017a55  mov     [rsi+8], rax
0x140017a59  jmp     loc_1400179D5
0x140017a5e  mov     ecx, 3
0x140017a63  int     29h; Win8: RtlFailFast(ecx)
0x140017a65  lea     rax, [rsp+88h+arg_10]
0x140017a6d  xor     r9d, r9d
0x140017a70  mov     [rsp+88h+var_60], rax
0x140017a75  mov     r8, r13
0x140017a78  mov     rdx, r15
0x140017a7b  mov     byte ptr [rsp+88h+var_68], r12b
0x140017a80  mov     rcx, r14
0x140017a83  call    BfMappingLookup
0x140017a88  mov     ebx, eax
0x140017a8a  test    eax, eax
0x140017a8c  js      loc_140017B23
0x140017a92  mov     rcx, [rsi+8]
0x140017a96  cmp     [rcx], rsi
0x140017a99  jnz     short loc_140017A5E
0x140017a9b  mov     rax, [rsp+88h+arg_10]
0x140017aa3  inc     edi
0x140017aa5  mov     [rax], rsi
0x140017aa8  mov     [rax+8], rcx
0x140017aac  mov     [rcx], rax
0x140017aaf  mov     [rsi+8], rax
0x140017ab3  mov     rax, [rax+20h]
0x140017ab7  mov     ecx, [rax+8]
0x140017aba  test    cl, 2
0x140017abd  jz      loc_1400179D5
0x140017ac3  jmp     loc_14001799C
0x140017ac8  lea     rax, WPP_RECORDER_INITIALIZED
0x140017acf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017ad6  jz      loc_1400179DA
0x140017adc  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ae3  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140017aea  mov     [rsp+88h+var_50], ebx
0x140017aee  mov     r9d, 4Ch ; 'L'
0x140017af4  mov     dword ptr [rsp+88h+var_58], 0C6Fh
0x140017afc  mov     r8d, 8
0x140017b02  mov     [rsp+88h+var_60], rax
0x140017b07  mov     dl, 2
0x140017b09  mov     rcx, [rcx+40h]
0x140017b0d  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140017b14  mov     [rsp+88h+var_68], rax
0x140017b19  call    WPP_RECORDER_SF_sDd
0x140017b1e  jmp     loc_1400179DA
0x140017b23  cmp     ebx, 0C000003Ah
0x140017b29  jz      loc_14001799C
0x140017b2f  lea     rax, WPP_RECORDER_INITIALIZED
0x140017b36  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017b3d  jz      loc_1400179D5
0x140017b43  mov     [rsp+88h+var_50], ebx
0x140017b47  mov     r9d, 4Dh ; 'M'
0x140017b4d  mov     dword ptr [rsp+88h+var_58], 0C90h
0x140017b55  jmp     short loc_140017B7D
0x140017b57  lea     rax, WPP_RECORDER_INITIALIZED
0x140017b5e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017b65  jz      loc_1400179D5
0x140017b6b  mov     [rsp+88h+var_50], ebx
0x140017b6f  mov     r9d, 4Eh ; 'N'
0x140017b75  mov     dword ptr [rsp+88h+var_58], 0CB1h
0x140017b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b84  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140017b8b  mov     [rsp+88h+var_60], rax
0x140017b90  mov     r8d, 8
0x140017b96  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140017b9d  mov     dl, 2
0x140017b9f  mov     [rsp+88h+var_68], rax
0x140017ba4  mov     rcx, [rcx+40h]
0x140017ba8  call    WPP_RECORDER_SF_sDd
0x140017bad  jmp     loc_1400179D5
```
