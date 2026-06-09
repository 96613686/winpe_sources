# SpatialDecParseSpecificConfigHeader(CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG *,AUDIO_OBJECT_TYPE,SPATIAL_DEC_UPMIX_TYPE)

- ea: `0x18007d75c`
- end: `0x18007d814`
- name: `?SpatialDecParseSpecificConfigHeader@@YA?AW4SACDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@W4AUDIO_OBJECT_TYPE@@W4SPATIAL_DEC_UPMIX_TYPE@@@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180072810`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x18007c55c`
- `0x18007ca70`
- `0x18007d4f4`
- `0x18007d75c`

## pseudocode

```c
__int64 __fastcall SpatialDecParseSpecificConfigHeader(int *a1, _DWORD *a2, __int64 a3)
{
  int v4; // ebp
  int v6; // r15d
  __int64 v7; // r8
  int v8; // esi
  __int64 v9; // r8
  int v10; // ebx
  unsigned int v11; // ebp
  __int64 v12; // rdx
  __int64 v13; // r8

  v4 = a3;
  v6 = CDKreadBits(a1, 1, a3);
  v8 = CDKreadBits(a1, 7, v7);
  if ( v8 == 127 )
    v8 = CDKreadBits(a1, 16, v9) + 127;
  CDKsyncCache_0(a1);
  v10 = a1[2];
  v11 = SpatialDecParseSpecificConfig(a1, a2, v8, v4);
  CDKsyncCache_0(a1);
  v12 = (unsigned int)(a1[2] + 8 * v8 - v10);
  if ( (int)v12 < 0 )
    v11 = -982;
  CDKpushBiDirectional_0(a1, v12);
  if ( !v11 && v6 )
  {
    CDKreadBits(a1, 16, v13);
    v11 = -983;
  }
  SpatialDecDecodeHelperInfo(a2);
  return v11;
}

```

## disassembly

```asm
0x18007d75c  push    rbx
0x18007d75e  push    rbp
0x18007d75f  push    rsi
0x18007d760  push    rdi
0x18007d761  push    r14
0x18007d763  push    r15
0x18007d765  sub     rsp, 28h
0x18007d769  mov     r14, rdx
0x18007d76c  mov     ebp, r8d
0x18007d76f  mov     edx, 1
0x18007d774  mov     rdi, rcx
0x18007d777  call    CDKreadBits
0x18007d77c  mov     edx, 7
0x18007d781  mov     rcx, rdi
0x18007d784  mov     r15d, eax
0x18007d787  call    CDKreadBits
0x18007d78c  mov     esi, eax
0x18007d78e  cmp     eax, 7Fh
0x18007d791  jnz     short loc_18007D7A1
0x18007d793  lea     edx, [rax-6Fh]
0x18007d796  mov     rcx, rdi
0x18007d799  call    CDKreadBits
0x18007d79e  lea     esi, [rax+7Fh]
0x18007d7a1  mov     rcx, rdi
0x18007d7a4  call    CDKsyncCache_0
0x18007d7a9  mov     ebx, [rdi+8]
0x18007d7ac  mov     r9d, ebp
0x18007d7af  mov     r8d, esi
0x18007d7b2  mov     rdx, r14
0x18007d7b5  mov     rcx, rdi
0x18007d7b8  call    ?SpatialDecParseSpecificConfig@@YA?AW4SACDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@HW4AUDIO_OBJECT_TYPE@@@Z; SpatialDecParseSpecificConfig(CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG *,int,AUDIO_OBJECT_TYPE)
0x18007d7bd  mov     rcx, rdi
0x18007d7c0  mov     ebp, eax
0x18007d7c2  call    CDKsyncCache_0
0x18007d7c7  lea     edx, ds:0[rsi*8]
0x18007d7ce  mov     eax, 0FFFFFC2Ah
0x18007d7d3  sub     edx, ebx
0x18007d7d5  mov     rcx, rdi
0x18007d7d8  add     edx, [rdi+8]
0x18007d7db  cmovs   ebp, eax
0x18007d7de  call    CDKpushBiDirectional_0
0x18007d7e3  test    ebp, ebp
0x18007d7e5  jnz     short loc_18007D7FC
0x18007d7e7  test    r15d, r15d
0x18007d7ea  jz      short loc_18007D7FC
0x18007d7ec  lea     edx, [rbp+10h]
0x18007d7ef  mov     rcx, rdi
0x18007d7f2  call    CDKreadBits
0x18007d7f7  mov     ebp, 0FFFFFC29h
0x18007d7fc  mov     rcx, r14
0x18007d7ff  call    SpatialDecDecodeHelperInfo
0x18007d804  mov     eax, ebp
0x18007d806  add     rsp, 28h
0x18007d80a  pop     r15
0x18007d80c  pop     r14
0x18007d80e  pop     rdi
0x18007d80f  pop     rsi
0x18007d810  pop     rbp
0x18007d811  pop     rbx
0x18007d812  retn
```
