# SdbpCheckMatchingWildcardRegistry

- ea: `0x14002f700`
- end: `0x14002f825`
- name: `SdbpCheckMatchingWildcardRegistry`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14002f700`
- `0x14002f82c`
- `0x14003e364`
- `0x14005289c`

## string_xrefs

- `0x14002f789`: `Failed to read MATCHING_WILDCARD_REGISTRY entry`
- `0x14002f796`: `SdbpCheckMatchingWildcardRegistry`
- `0x14002f7ed`: `Failed to check MATCHING_WILDCARD_REGISTRY entry`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingWildcardRegistry(
        _DWORD *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int v10; // [rsp+58h] [rbp-1h] BYREF
  int v11; // [rsp+5Ch] [rbp+3h] BYREF
  __int64 v12; // [rsp+60h] [rbp+7h] BYREF
  __int64 v13; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v14; // [rsp+70h] [rbp+17h] BYREF
  __int64 v15; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v16; // [rsp+80h] [rbp+27h] BYREF
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
  if ( (unsigned int)SdbpGetRegistryMatchingAttributes(a3, v6, &v17, &v16, &v10, &v15, &v18, &v14, &v13, &v12) )
  {
    if ( (unsigned int)SdbpCheckMatchingWildcardRegistryEntry(
                         (_DWORD)v17,
                         v16,
                         v10,
                         v15,
                         v18,
                         v14,
                         v13,
                         v12,
                         (__int64)&v11) )
    {
      v7 = 1;
      *(_DWORD *)(a6 + 80) = 1;
      *a1 = v11;
    }
    else
    {
      AslLogCallPrintf(1, "SdbpCheckMatchingWildcardRegistry", 1699, "Failed to check MATCHING_WILDCARD_REGISTRY entry");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingWildcardRegistry", 1682, "Failed to read MATCHING_WILDCARD_REGISTRY entry");
  }
  return v7;
}

```

## disassembly

```asm
0x14002f700  mov     r11, rsp
0x14002f703  mov     [r11+10h], rbx
0x14002f707  mov     [r11+18h], rdi
0x14002f70b  push    rbp
0x14002f70c  lea     rbp, [r11-47h]
0x14002f710  sub     rsp, 90h
0x14002f717  mov     edx, [rbp+3Fh+arg_20]
0x14002f71a  lea     r9, [rbp+3Fh+var_18]
0x14002f71e  xor     ebx, ebx
0x14002f720  mov     rdi, rcx
0x14002f723  mov     [rcx], ebx
0x14002f725  mov     rax, r8
0x14002f728  lea     rcx, [rbp+3Fh+var_38]
0x14002f72c  mov     [rbp+3Fh+var_3C], ebx
0x14002f72f  mov     [r11-50h], rcx
0x14002f733  lea     r8, [rbp+3Fh+var_10]
0x14002f737  lea     rcx, [rbp+3Fh+var_30]
0x14002f73b  mov     [rbp+3Fh+var_10], rbx
0x14002f73f  mov     [r11-58h], rcx
0x14002f743  lea     rcx, [rbp+3Fh+var_28]
0x14002f747  mov     [r11-60h], rcx
0x14002f74b  lea     rcx, [rbp+3Fh+arg_0]
0x14002f74f  mov     [r11-68h], rcx
0x14002f753  lea     rcx, [rbp+3Fh+var_20]
0x14002f757  mov     [r11-70h], rcx
0x14002f75b  lea     rcx, [rbp+3Fh+var_40]
0x14002f75f  mov     [r11-78h], rcx
0x14002f763  mov     rcx, rax
0x14002f766  mov     [rbp+3Fh+var_18], rbx
0x14002f76a  mov     [rbp+3Fh+var_40], ebx
0x14002f76d  mov     [rbp+3Fh+var_20], rbx
0x14002f771  mov     [rbp+3Fh+arg_0], ebx
0x14002f774  mov     [rbp+3Fh+var_28], rbx
0x14002f778  mov     [rbp+3Fh+var_30], rbx
0x14002f77c  mov     [rbp+3Fh+var_38], rbx
0x14002f780  call    SdbpGetRegistryMatchingAttributes
0x14002f785  test    eax, eax
0x14002f787  jnz     short loc_14002F7A9
0x14002f789  lea     r9, aFailedToReadMa; "Failed to read MATCHING_WILDCARD_REGIST"...
0x14002f790  mov     r8d, 692h
0x14002f796  lea     rdx, aSdbpcheckmatch_0; "SdbpCheckMatchingWildcardRegistry"
0x14002f79d  mov     ecx, 1
0x14002f7a2  call    AslLogCallPrintf
0x14002f7a7  jmp     short loc_14002F80D
0x14002f7a9  mov     r9, [rbp+3Fh+var_20]
0x14002f7ad  lea     rax, [rbp+3Fh+var_3C]
0x14002f7b1  mov     r8d, [rbp+3Fh+var_40]
0x14002f7b5  mov     rdx, [rbp+3Fh+var_18]
0x14002f7b9  mov     rcx, [rbp+3Fh+var_10]
0x14002f7bd  mov     [rsp+90h+var_50], rax
0x14002f7c2  mov     rax, [rbp+3Fh+var_38]
0x14002f7c6  mov     [rsp+90h+var_58], rax
0x14002f7cb  mov     rax, [rbp+3Fh+var_30]
0x14002f7cf  mov     [rsp+90h+var_60], rax
0x14002f7d4  mov     rax, [rbp+3Fh+var_28]
0x14002f7d8  mov     [rsp+90h+var_68], rax
0x14002f7dd  mov     eax, [rbp+3Fh+arg_0]
0x14002f7e0  mov     dword ptr [rsp+90h+var_70], eax
0x14002f7e4  call    SdbpCheckMatchingWildcardRegistryEntry
0x14002f7e9  test    eax, eax
0x14002f7eb  jnz     short loc_14002F7FC
0x14002f7ed  lea     r9, aFailedToCheckM; "Failed to check MATCHING_WILDCARD_REGIS"...
0x14002f7f4  mov     r8d, 6A3h
0x14002f7fa  jmp     short loc_14002F796
0x14002f7fc  mov     rcx, [rbp+3Fh+arg_28]
0x14002f800  mov     ebx, 1
0x14002f805  mov     [rcx+50h], ebx
0x14002f808  mov     ecx, [rbp+3Fh+var_3C]
0x14002f80b  mov     [rdi], ecx
0x14002f80d  lea     r11, [rsp+90h+var_s0]
0x14002f815  mov     eax, ebx
0x14002f817  mov     rbx, [r11+18h]
0x14002f81b  mov     rdi, [r11+20h]
0x14002f81f  mov     rsp, r11
0x14002f822  pop     rbp
0x14002f823  retn
```
