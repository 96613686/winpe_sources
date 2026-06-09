# OPRawPortWrite

- ea: `0x180016940`
- end: `0x1800169d7`
- name: `OPRawPortWrite`
- size: `151`
- prototype: ``
- caller_count: `73`
- callee_count: `4`
- tags: ``

## callers

- `0x180005b1c`
- `0x180005c48`
- `0x180007b70`
- `0x180009524`
- `0x1800096d0`
- `0x180009b84`
- `0x18000a094`
- `0x18000a488`
- `0x18000a8a0`
- `0x18000abb0`
- `0x18000bd5c`
- `0x18000ccd4`
- `0x18000ce00`
- `0x18000e09c`
- `0x18000e4ac`
- `0x18000e800`
- `0x18000ee40`
- `0x18000f998`
- `0x1800115dc`
- `0x180011b54`
- `0x180011ebc`
- `0x1800122cc`
- `0x1800124cc`
- `0x180012558`
- `0x1800125d0`
- `0x18001265c`
- `0x180012b2c`
- `0x180012f88`
- `0x18001313c`
- `0x180013500`
- `0x1800139e8`
- `0x180013ae4`
- `0x180013bf8`
- `0x180013d48`
- `0x180013dbc`
- `0x180014138`
- `0x180014238`
- `0x1800143e4`
- `0x18001462c`
- `0x1800146dc`
- `0x180014988`
- `0x180014ad8`
- `0x180014d48`
- `0x180015264`
- `0x1800158f4`
- `0x180015994`
- `0x180015adc`
- `0x180015d1c`
- `0x180015f84`
- `0x1800162ac`

## callees

- `0x1800160ec`
- `0x1800166a0`
- `0x180016940`
- `0x18005c434`

## pseudocode

```c
__int64 __fastcall OPRawPortWrite(__int64 a1, char *a2, unsigned int a3)
{
  __int64 result; // rax
  int i; // ecx
  _DWORD *v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // edx
  void *v11; // rcx
  __int64 v12; // rbx

  if ( *(_QWORD *)(a1 + 2896) || (result = BAllocateSpoolBuf(a1), (_DWORD)result) )
  {
    for ( i = *(_DWORD *)(a1 + 3440); !i; i = *(_DWORD *)(a1 + 3440) )
    {
      if ( !a3 )
        break;
      v8 = *(_DWORD **)(a1 + 2896);
      v9 = a3;
      v10 = v8[2] - *v8;
      v11 = *(void **)v8;
      if ( v10 <= a3 )
        v9 = v10;
      v12 = v9;
      memcpy_0(v11, a2, v9);
      a2 += v12;
      a3 -= v12;
      **(_QWORD **)(a1 + 2896) += v12;
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 2896) + 8LL) <= **(_QWORD **)(a1 + 2896) )
        OPFlushToSpool(a1);
    }
    return i == 0;
  }
  return result;
}

```

## disassembly

```asm
0x180016940  push    rbx
0x180016942  push    rbp
0x180016943  push    rsi
0x180016944  push    rdi
0x180016945  sub     rsp, 28h
0x180016949  cmp     qword ptr [rcx+0B50h], 0
0x180016951  mov     esi, r8d
0x180016954  mov     rbp, rdx
0x180016957  mov     rdi, rcx
0x18001695a  jnz     short loc_180016965
0x18001695c  call    BAllocateSpoolBuf
0x180016961  test    eax, eax
0x180016963  jz      short loc_1800169CE
0x180016965  mov     ecx, [rdi+0D70h]
0x18001696b  test    ecx, ecx
0x18001696d  jnz     short loc_1800169C7
0x18001696f  test    esi, esi
0x180016971  jz      short loc_1800169C7
0x180016973  mov     rcx, [rdi+0B50h]
0x18001697a  mov     eax, esi
0x18001697c  mov     edx, [rcx+8]
0x18001697f  sub     edx, [rcx]
0x180016981  mov     rcx, [rcx]; void *
0x180016984  cmp     edx, esi
0x180016986  cmovbe  eax, edx
0x180016989  mov     rdx, rbp; Src
0x18001698c  mov     r8d, eax; Size
0x18001698f  mov     ebx, eax
0x180016991  call    memcpy_0
0x180016996  mov     rax, [rdi+0B50h]
0x18001699d  add     rbp, rbx
0x1800169a0  sub     esi, ebx
0x1800169a2  add     [rax], rbx
0x1800169a5  mov     rcx, [rdi+0B50h]
0x1800169ac  mov     rax, [rcx]
0x1800169af  cmp     [rcx+8], rax
0x1800169b3  ja      short loc_1800169BD
0x1800169b5  mov     rcx, rdi
0x1800169b8  call    OPFlushToSpool
0x1800169bd  mov     ecx, [rdi+0D70h]
0x1800169c3  test    ecx, ecx
0x1800169c5  jz      short loc_18001696F
0x1800169c7  xor     eax, eax
0x1800169c9  test    ecx, ecx
0x1800169cb  setz    al
0x1800169ce  add     rsp, 28h
0x1800169d2  pop     rdi
0x1800169d3  pop     rsi
0x1800169d4  pop     rbp
0x1800169d5  pop     rbx
0x1800169d6  retn
```
