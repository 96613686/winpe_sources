# SdbpCheckMatchingRegistry

- ea: `0x140052770`
- end: `0x140052895`
- name: `SdbpCheckMatchingRegistry`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14003e364`
- `0x140052770`
- `0x14005289c`
- `0x140052bf0`

## string_xrefs

- `0x140052873`: `SdbpCheckMatchingRegistry`
- `0x140052866`: `Failed to read MATCHING_REG entry`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistry(_DWORD *a1, __int64 a2, void *a3, __int64 a4, unsigned int a5, __int64 a6)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  unsigned int v10; // [rsp+58h] [rbp-1h] BYREF
  int v11; // [rsp+5Ch] [rbp+3h] BYREF
  size_t v12; // [rsp+60h] [rbp+7h] BYREF
  void *v13; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v14; // [rsp+70h] [rbp+17h] BYREF
  void *v15; // [rsp+78h] [rbp+1Fh] BYREF
  void *v16; // [rsp+80h] [rbp+27h] BYREF
  __int16 *v17; // [rsp+88h] [rbp+2Fh] BYREF
  int v18; // [rsp+A8h] [rbp+4Fh] BYREF

  v6 = a5;
  v7 = 0;
  *a1 = 0;
  v11 = 0;
  v17 = 0;
  v16 = 0;
  v10 = 0;
  v15 = 0;
  v18 = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  if ( (unsigned int)SdbpGetRegistryMatchingAttributes(
                       a3,
                       v6,
                       &v17,
                       (__int64 *)&v16,
                       &v10,
                       (__int64 *)&v15,
                       &v18,
                       &v14,
                       (__int64 *)&v13,
                       &v12) )
  {
    if ( (unsigned int)SdbpCheckMatchingRegistryEntry((__int64)v17, v16, v10, v15, v18, v14, v13, v12, &v11) )
    {
      v7 = 1;
      *(_DWORD *)(a6 + 80) = 1;
      *a1 = v11;
    }
    else
    {
      AslLogCallPrintf(1, "SdbpCheckMatchingRegistry", 1786, "Failed to check MATCHING_REG entry");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistry", 1769, "Failed to read MATCHING_REG entry");
  }
  return v7;
}

```

## disassembly

```asm
0x140052770  mov     r11, rsp
0x140052773  mov     [r11+10h], rbx
0x140052777  mov     [r11+18h], rdi
0x14005277b  push    rbp
0x14005277c  lea     rbp, [r11-47h]
0x140052780  sub     rsp, 90h
0x140052787  mov     edx, [rbp+3Fh+arg_20]
0x14005278a  lea     r9, [rbp+3Fh+var_18]
0x14005278e  xor     ebx, ebx
0x140052790  mov     rdi, rcx
0x140052793  mov     [rcx], ebx
0x140052795  mov     rax, r8
0x140052798  lea     rcx, [rbp+3Fh+var_38]
0x14005279c  mov     [rbp+3Fh+var_3C], ebx
0x14005279f  mov     [r11-50h], rcx
0x1400527a3  lea     r8, [rbp+3Fh+var_10]
0x1400527a7  lea     rcx, [rbp+3Fh+var_30]
0x1400527ab  mov     [rbp+3Fh+var_10], rbx
0x1400527af  mov     [r11-58h], rcx
0x1400527b3  lea     rcx, [rbp+3Fh+var_28]
0x1400527b7  mov     [r11-60h], rcx
0x1400527bb  lea     rcx, [rbp+3Fh+arg_0]
0x1400527bf  mov     [r11-68h], rcx
0x1400527c3  lea     rcx, [rbp+3Fh+var_20]
0x1400527c7  mov     [r11-70h], rcx
0x1400527cb  lea     rcx, [rbp+3Fh+var_40]
0x1400527cf  mov     [r11-78h], rcx
0x1400527d3  mov     rcx, rax
0x1400527d6  mov     [rbp+3Fh+var_18], rbx
0x1400527da  mov     [rbp+3Fh+var_40], ebx
0x1400527dd  mov     [rbp+3Fh+var_20], rbx
0x1400527e1  mov     [rbp+3Fh+arg_0], ebx
0x1400527e4  mov     [rbp+3Fh+var_28], rbx
0x1400527e8  mov     [rbp+3Fh+var_30], rbx
0x1400527ec  mov     [rbp+3Fh+var_38], rbx
0x1400527f0  call    SdbpGetRegistryMatchingAttributes
0x1400527f5  test    eax, eax
0x1400527f7  jz      short loc_140052866
0x1400527f9  mov     r9, [rbp+3Fh+var_20]
0x1400527fd  lea     rax, [rbp+3Fh+var_3C]
0x140052801  mov     r8d, [rbp+3Fh+var_40]
0x140052805  mov     rdx, [rbp+3Fh+var_18]
0x140052809  mov     rcx, [rbp+3Fh+var_10]
0x14005280d  mov     [rsp+90h+var_50], rax
0x140052812  mov     rax, [rbp+3Fh+var_38]
0x140052816  mov     [rsp+90h+var_58], rax
0x14005281b  mov     rax, [rbp+3Fh+var_30]
0x14005281f  mov     [rsp+90h+var_60], rax
0x140052824  mov     rax, [rbp+3Fh+var_28]
0x140052828  mov     [rsp+90h+var_68], rax
0x14005282d  mov     eax, [rbp+3Fh+arg_0]
0x140052830  mov     dword ptr [rsp+90h+var_70], eax
0x140052834  call    SdbpCheckMatchingRegistryEntry
0x140052839  test    eax, eax
0x14005283b  jz      short loc_140052886
0x14005283d  mov     rcx, [rbp+3Fh+arg_28]
0x140052841  mov     ebx, 1
0x140052846  mov     [rcx+50h], ebx
0x140052849  mov     ecx, [rbp+3Fh+var_3C]
0x14005284c  mov     [rdi], ecx
0x14005284e  lea     r11, [rsp+90h+var_s0]
0x140052856  mov     eax, ebx
0x140052858  mov     rbx, [r11+18h]
0x14005285c  mov     rdi, [r11+20h]
0x140052860  mov     rsp, r11
0x140052863  pop     rbp
0x140052864  retn
0x140052866  lea     r9, aFailedToReadMa_1; "Failed to read MATCHING_REG entry"
0x14005286d  mov     r8d, 6E9h
0x140052873  lea     rdx, aSdbpcheckmatch_5; "SdbpCheckMatchingRegistry"
0x14005287a  mov     ecx, 1
0x14005287f  call    AslLogCallPrintf
0x140052884  jmp     short loc_14005284E
0x140052886  lea     r9, aFailedToCheckM_0; "Failed to check MATCHING_REG entry"
0x14005288d  mov     r8d, 6FAh
0x140052893  jmp     short loc_140052873
```
