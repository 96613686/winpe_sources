# AslpFileGetHeaderAttributesNE

- ea: `0x14004ac98`
- end: `0x14004ae32`
- name: `AslpFileGetHeaderAttributesNE`
- size: `410`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14004a724`

## callees

- `0x1400349f4`
- `0x140034adc`
- `0x14003e364`
- `0x140043420`
- `0x14004ac98`
- `0x14004ae38`

## string_xrefs

- `0x14004ad86`: `AslStringXmlSanitize failed [%x]`
- `0x14004adf2`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetHeaderAttributesNE(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // edi
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  v15 = 0;
  v4 = AslFileMappingEnsure(a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    v7 = "AslFileMappingEnsure failed [%x]";
    v8 = 3489;
    goto LABEL_8;
  }
  if ( *(_DWORD *)(a2 + 64) == 5 )
  {
    *(_DWORD *)(a1 + 600) |= 2u;
    *(_DWORD *)(a1 + 632) |= 2u;
    *(_DWORD *)(a1 + 728) |= 2u;
    *(_DWORD *)(a1 + 56) |= 2u;
    *(_DWORD *)(a1 + 824) |= 2u;
    *(_DWORD *)(a1 + 760) |= 2u;
    *(_DWORD *)(a1 + 952) |= 2u;
    *(_DWORD *)(a1 + 984) |= 2u;
    *(_DWORD *)(a1 + 1016) |= 2u;
    *(_DWORD *)(a1 + 1080) |= 2u;
    v9 = -1;
    if ( (int)AslpFileGet16BitDescription(&v14, a2) < 0 )
    {
      *(_DWORD *)(a1 + 664) |= 2u;
    }
    else
    {
      v4 = AslStringXmlSanitize(v14);
      v5 = v4;
      if ( v4 < 0 )
      {
        v7 = "AslStringXmlSanitize failed [%x]";
        v8 = 3525;
        goto LABEL_8;
      }
      *(_DWORD *)(a1 + 640) = 4;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      *(_DWORD *)(a1 + 664) |= 5u;
      *(_QWORD *)(a1 + 648) = v11;
      *(_QWORD *)(a1 + 656) = v10;
    }
    if ( (int)AslpFileGet16BitModuleName(&v15, a2) < 0 )
      goto LABEL_4;
    v4 = AslStringXmlSanitize(v15);
    v5 = v4;
    if ( v4 >= 0 )
    {
      *(_DWORD *)(a1 + 672) = 4;
      do
        ++v9;
      while ( *(_WORD *)(v12 + 2 * v9) );
      *(_DWORD *)(a1 + 696) |= 5u;
      *(_QWORD *)(a1 + 680) = v9;
      *(_QWORD *)(a1 + 688) = v12;
      return 0;
    }
    v7 = "AslStringXmlSanitize failed [%x]";
    v8 = 3546;
LABEL_8:
    v13 = v4;
    AslLogCallPrintf(1, "AslpFileGetHeaderAttributesNE", v8, v7, v13);
    return v5;
  }
  *(_DWORD *)(a1 + 664) |= 2u;
LABEL_4:
  *(_DWORD *)(a1 + 696) |= 2u;
  return 0;
}

```

## disassembly

```asm
0x14004ac98  mov     rax, rsp
0x14004ac9b  mov     [rax+8], rbx
0x14004ac9f  mov     [rax+10h], rbp
0x14004aca3  push    rdi
0x14004aca4  push    r14
0x14004aca6  push    r15
0x14004aca8  sub     rsp, 30h
0x14004acac  mov     rbx, rcx
0x14004acaf  xor     r15d, r15d
0x14004acb2  mov     rcx, rdx
0x14004acb5  mov     [rax+18h], r15
0x14004acb9  mov     [rax+20h], r15
0x14004acbd  mov     r14, rdx
0x14004acc0  call    AslFileMappingEnsure
0x14004acc5  mov     edi, eax
0x14004acc7  test    eax, eax
0x14004acc9  js      short loc_14004ACFA
0x14004accb  cmp     dword ptr [r14+40h], 5
0x14004acd0  jz      short loc_14004AD1E
0x14004acd2  or      dword ptr [rbx+298h], 2
0x14004acd9  or      dword ptr [rbx+2B8h], 2
0x14004ace0  mov     edi, r15d
0x14004ace3  mov     rbx, [rsp+48h+arg_0]
0x14004ace8  mov     eax, edi
0x14004acea  mov     rbp, [rsp+48h+arg_8]
0x14004acef  add     rsp, 30h
0x14004acf3  pop     r15
0x14004acf5  pop     r14
0x14004acf7  pop     rdi
0x14004acf8  retn
0x14004acfa  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14004ad01  mov     r8d, 0DA1h
0x14004ad07  lea     rdx, aAslpfilegethea_1; "AslpFileGetHeaderAttributesNE"
0x14004ad0e  mov     [rsp+48h+var_28], eax
0x14004ad12  mov     ecx, 1
0x14004ad17  call    AslLogCallPrintf
0x14004ad1c  jmp     short loc_14004ACE3
0x14004ad1e  or      dword ptr [rbx+258h], 2
0x14004ad25  lea     rcx, [rsp+48h+arg_10]
0x14004ad2a  or      dword ptr [rbx+278h], 2
0x14004ad31  mov     rdx, r14
0x14004ad34  or      dword ptr [rbx+2D8h], 2
0x14004ad3b  or      dword ptr [rbx+38h], 2
0x14004ad3f  or      dword ptr [rbx+338h], 2
0x14004ad46  or      dword ptr [rbx+2F8h], 2
0x14004ad4d  or      dword ptr [rbx+3B8h], 2
0x14004ad54  or      dword ptr [rbx+3D8h], 2
0x14004ad5b  or      dword ptr [rbx+3F8h], 2
0x14004ad62  or      dword ptr [rbx+438h], 2
0x14004ad69  call    AslpFileGet16BitDescription
0x14004ad6e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14004ad72  test    eax, eax
0x14004ad74  js      short loc_14004ADC6
0x14004ad76  mov     rcx, [rsp+48h+arg_10]
0x14004ad7b  call    AslStringXmlSanitize
0x14004ad80  mov     edi, eax
0x14004ad82  test    eax, eax
0x14004ad84  jns     short loc_14004AD98
0x14004ad86  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x14004ad8d  mov     r8d, 0DC5h
0x14004ad93  jmp     loc_14004AD07
0x14004ad98  mov     dword ptr [rbx+280h], 4
0x14004ada2  mov     rax, rbp
0x14004ada5  inc     rax
0x14004ada8  cmp     [rcx+rax*2], r15w
0x14004adad  jnz     short loc_14004ADA5
0x14004adaf  or      dword ptr [rbx+298h], 5
0x14004adb6  mov     [rbx+288h], rax
0x14004adbd  mov     [rbx+290h], rcx
0x14004adc4  jmp     short loc_14004ADCD
0x14004adc6  or      dword ptr [rbx+298h], 2
0x14004adcd  mov     rdx, r14
0x14004add0  lea     rcx, [rsp+48h+arg_18]
0x14004add5  call    AslpFileGet16BitModuleName
0x14004adda  test    eax, eax
0x14004addc  js      loc_14004ACD9
0x14004ade2  mov     rcx, [rsp+48h+arg_18]
0x14004ade7  call    AslStringXmlSanitize
0x14004adec  mov     edi, eax
0x14004adee  test    eax, eax
0x14004adf0  jns     short loc_14004AE04
0x14004adf2  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x14004adf9  mov     r8d, 0DDAh
0x14004adff  jmp     loc_14004AD07
0x14004ae04  mov     dword ptr [rbx+2A0h], 4
0x14004ae0e  inc     rbp
0x14004ae11  cmp     [rcx+rbp*2], r15w
0x14004ae16  jnz     short loc_14004AE0E
0x14004ae18  or      dword ptr [rbx+2B8h], 5
0x14004ae1f  mov     [rbx+2A8h], rbp
0x14004ae26  mov     [rbx+2B0h], rcx
0x14004ae2d  jmp     loc_14004ACE0
```
