# GaSpecificConfig_Parse

- ea: `0x18001262c`
- end: `0x18001275f`
- name: `GaSpecificConfig_Parse`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011da8`

## callees

- `0x1800110c0`
- `0x18001262c`
- `0x1800127d8`

## pseudocode

```c
__int64 __fastcall GaSpecificConfig_Parse(_DWORD *a1, __int64 a2, struct CDK_BITSTREAM *a3, unsigned int a4)
{
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r8
  int v12; // eax
  __int64 v14; // r8
  unsigned int v15; // eax
  int v16; // ecx
  __int64 v17; // r8
  __int64 v18; // r8

  *a1 = CDKreadBits(a3, 1, (__int64)a3);
  v9 = CDKreadBits(a3, 1, v8);
  a1[1] = v9;
  if ( v9 )
    a1[2] = CDKreadBits(a3, 14, v10);
  a1[3] = CDKreadBits(a3, 1, v10);
  if ( !*(_BYTE *)(a2 + 1224) )
    CProgramConfig_Read((struct CProgramConfig *)(a2 + 732), a3, a4);
  v12 = *(_DWORD *)(a2 + 1200);
  if ( v12 == 6 || v12 == 20 )
    a1[5] = CDKreadBits(a3, 3, v11);
  if ( a1[3] )
  {
    if ( *(_DWORD *)(a2 + 1200) == 22 )
    {
      a1[6] = CDKreadBits(a3, 5, v11);
      a1[7] = CDKreadBits(a3, 11, v14);
    }
    v15 = *(_DWORD *)(a2 + 1200);
    if ( v15 <= 0x17 )
    {
      v16 = 10092544;
      if ( _bittest(&v16, v15) )
      {
        *(_BYTE *)(a2 + 1226) = CDKreadBits(a3, 1, v11);
        *(_BYTE *)(a2 + 1227) = CDKreadBits(a3, 1, v17);
        *(_BYTE *)(a2 + 1228) = CDKreadBits(a3, 1, v18);
      }
    }
    a1[4] = CDKreadBits(a3, 1, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18001262c  push    rbx
0x18001262e  push    rbp
0x18001262f  push    rsi
0x180012630  push    rdi
0x180012631  push    r14
0x180012633  sub     rsp, 20h
0x180012637  mov     rsi, rdx
0x18001263a  mov     rdi, rcx
0x18001263d  mov     r14d, 1
0x180012643  mov     rcx, r8
0x180012646  mov     edx, r14d
0x180012649  mov     ebp, r9d
0x18001264c  mov     rbx, r8
0x18001264f  call    CDKreadBits
0x180012654  mov     edx, r14d
0x180012657  mov     [rdi], eax
0x180012659  mov     rcx, rbx
0x18001265c  call    CDKreadBits
0x180012661  mov     [rdi+4], eax
0x180012664  test    eax, eax
0x180012666  jnz     short loc_1800126A3
0x180012668  mov     edx, r14d
0x18001266b  mov     rcx, rbx
0x18001266e  call    CDKreadBits
0x180012673  mov     [rdi+0Ch], eax
0x180012676  cmp     byte ptr [rsi+4C8h], 0
0x18001267d  jz      short loc_1800126B5
0x18001267f  mov     eax, [rsi+4B0h]
0x180012685  cmp     eax, 6
0x180012688  jz      short loc_1800126C9
0x18001268a  cmp     eax, 14h
0x18001268d  jz      short loc_1800126C9
0x18001268f  cmp     dword ptr [rdi+0Ch], 0
0x180012693  jnz     short loc_1800126DB
0x180012695  xor     eax, eax
0x180012697  add     rsp, 20h
0x18001269b  pop     r14
0x18001269d  pop     rdi
0x18001269e  pop     rsi
0x18001269f  pop     rbp
0x1800126a0  pop     rbx
0x1800126a1  retn
0x1800126a3  mov     edx, 0Eh
0x1800126a8  mov     rcx, rbx
0x1800126ab  call    CDKreadBits
0x1800126b0  mov     [rdi+8], eax
0x1800126b3  jmp     short loc_180012668
0x1800126b5  lea     rcx, [rsi+2DCh]; struct CProgramConfig *
0x1800126bc  mov     r8d, ebp; unsigned int
0x1800126bf  mov     rdx, rbx; struct CDK_BITSTREAM *
0x1800126c2  call    ?CProgramConfig_Read@@YAXPEAUCProgramConfig@@PEAUCDK_BITSTREAM@@I@Z; CProgramConfig_Read(CProgramConfig *,CDK_BITSTREAM *,uint)
0x1800126c7  jmp     short loc_18001267F
0x1800126c9  mov     edx, 3
0x1800126ce  mov     rcx, rbx
0x1800126d1  call    CDKreadBits
0x1800126d6  mov     [rdi+14h], eax
0x1800126d9  jmp     short loc_18001268F
0x1800126db  cmp     dword ptr [rsi+4B0h], 16h
0x1800126e2  jnz     short loc_180012704
0x1800126e4  mov     edx, 5
0x1800126e9  mov     rcx, rbx
0x1800126ec  call    CDKreadBits
0x1800126f1  mov     edx, 0Bh
0x1800126f6  mov     [rdi+18h], eax
0x1800126f9  mov     rcx, rbx
0x1800126fc  call    CDKreadBits
0x180012701  mov     [rdi+1Ch], eax
0x180012704  mov     eax, [rsi+4B0h]
0x18001270a  cmp     eax, 17h
0x18001270d  ja      short loc_18001274C
0x18001270f  mov     ecx, 9A0000h
0x180012714  bt      ecx, eax
0x180012717  jnb     short loc_18001274C
0x180012719  mov     edx, r14d
0x18001271c  mov     rcx, rbx
0x18001271f  call    CDKreadBits
0x180012724  mov     edx, r14d
0x180012727  mov     [rsi+4CAh], al
0x18001272d  mov     rcx, rbx
0x180012730  call    CDKreadBits
0x180012735  mov     edx, r14d
0x180012738  mov     [rsi+4CBh], al
0x18001273e  mov     rcx, rbx
0x180012741  call    CDKreadBits
0x180012746  mov     [rsi+4CCh], al
0x18001274c  mov     edx, r14d
0x18001274f  mov     rcx, rbx
0x180012752  call    CDKreadBits
0x180012757  mov     [rdi+10h], eax
0x18001275a  jmp     loc_180012695
```
