# createSbrDec(SBR_CHANNEL *,SBR_HEADER_DATA *,TRANSPOSER_SETTINGS *,int,uint,uint,int,int,int)

- ea: `0x18001b728`
- end: `0x18001b95a`
- name: `?createSbrDec@@YA?AW4SBR_ERROR@@PEAUSBR_CHANNEL@@PEAUSBR_HEADER_DATA@@PEAUTRANSPOSER_SETTINGS@@HIIHHH@Z`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001b418`

## callees

- `0x18001b728`
- `0x18001b960`
- `0x180036e88`
- `0x18004dd14`
- `0x18007c1d8`
- `0x1800917e8`

## pseudocode

```c
__int64 __fastcall createSbrDec(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        int a8,
        unsigned int a9)
{
  int v9; // ebx
  int v10; // r14d
  __int64 v11; // rax
  __int64 result; // rax
  unsigned int v15; // r14d
  unsigned int v16; // ebp
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r8

  v9 = *(unsigned __int8 *)(a2 + 6);
  v10 = *(unsigned __int8 *)(a2 + 8);
  v11 = 0;
  *(_DWORD *)(a1 + 15796) = 0;
  *(_DWORD *)(a1 + 15800) = a9;
  do
  {
    *(_DWORD *)(a1 + 4 * v11 + 4652) = 0;
    *(_DWORD *)(a1 + 4 * v11++ + 4808) = 0;
  }
  while ( v11 != 2 );
  *(_BYTE *)(a1 + 4660) = 0;
  *(_OWORD *)(a1 + 4668) = 0;
  *(_DWORD *)(a1 + 4684) = 0;
  *(_BYTE *)(a1 + 4688) = 0;
  *(_DWORD *)(a1 + 4798) = 0;
  *(_WORD *)(a1 + 4802) = 0;
  *(_BYTE *)(a1 + 4804) = 0;
  *(_DWORD *)(a1 + 4648) = -1;
  *(_QWORD *)(a1 + 4640) = 1;
  if ( a8 || (result = resetFreqBandTables(a2, a6), !(_DWORD)result) )
  {
    v15 = v9 * v10;
    memset_0((void *)(a1 + 3888), 0, 0xE0u);
    *(_OWORD *)(a1 + 4112) = 0;
    *(_QWORD *)(a1 + 4128) = 0;
    *(_OWORD *)(a1 + 4136) = 0;
    *(_DWORD *)(a1 + 4152) = 0;
    *(_BYTE *)(a1 + 4156) = 0;
    *(_BYTE *)(a1 + 4157) = v9;
    *(_OWORD *)(a1 + 4160) = 0;
    *(_OWORD *)(a1 + 4173) = 0;
    result = createLppTransposer(
               a1 + 4816,
               a3,
               *(unsigned __int8 *)(a2 + 44),
               a2 + 172,
               *(unsigned __int8 *)(a2 + 43),
               *(unsigned __int8 *)(a2 + 45),
               v9,
               v15,
               a2 + 166,
               *(unsigned __int8 *)(a2 + 42),
               *(_DWORD *)(a2 + 12),
               a8,
               a7);
    if ( !(_DWORD)result && (a6 & 0x100) != 0 )
    {
      v16 = (a6 >> 7) & 1;
      v17 = 0x40 / (2 * v16 + 2);
      v18 = cdkCallocMatrix2D_int_aligned(v15, v17);
      *(_QWORD *)(a1 + 16296) = v18;
      if ( v18
        && (*(_QWORD *)(a1 + 16304) = v18,
            v19 = cdkCallocMatrix2D_int_aligned(v15, v17),
            (*(_QWORD *)(a1 + 16312) = v19) != 0)
        && (v20 = cdkCallocMatrix2D_int_aligned(v15, v17), (*(_QWORD *)(a1 + 16320) = v20) != 0)
        && (v21 = cdkCallocMatrix2D_int_aligned(v15, v17), (*(_QWORD *)(a1 + 16328) = v21) != 0) )
      {
        return QmfTransposerCreate(a1 + 15808, a9, v22, v16);
      }
      else
      {
        return 4;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b728  mov     [rsp+arg_10], r8
0x18001b72d  push    rbx
0x18001b72e  push    rbp
0x18001b72f  push    rsi
0x18001b730  push    rdi
0x18001b731  push    r12
0x18001b733  push    r13
0x18001b735  push    r14
0x18001b737  push    r15
0x18001b739  sub     rsp, 78h
0x18001b73d  movzx   ebx, byte ptr [rdx+6]
0x18001b741  xor     edi, edi
0x18001b743  movzx   r14d, byte ptr [rdx+8]
0x18001b748  mov     eax, edi
0x18001b74a  mov     r12d, [rsp+0B8h+arg_40]
0x18001b752  mov     r15, rdx
0x18001b755  mov     [rcx+3DB4h], edi
0x18001b75b  mov     rsi, rcx
0x18001b75e  mov     [rcx+3DB8h], r12d
0x18001b765  mov     [rcx+rax*4+122Ch], edi
0x18001b76c  mov     [rcx+rax*4+12C8h], edi
0x18001b773  inc     rax
0x18001b776  cmp     rax, 2
0x18001b77a  jnz     short loc_18001B765
0x18001b77c  mov     r13d, [rsp+0B8h+arg_38]
0x18001b784  xor     eax, eax
0x18001b786  mov     ebp, [rsp+0B8h+arg_28]
0x18001b78d  xorps   xmm0, xmm0
0x18001b790  mov     [rcx+1234h], dil
0x18001b797  movups  xmmword ptr [rcx+123Ch], xmm0
0x18001b79e  mov     [rcx+124Ch], eax
0x18001b7a4  mov     [rcx+1250h], dil
0x18001b7ab  mov     [rcx+12BEh], eax
0x18001b7b1  mov     [rcx+12C2h], ax
0x18001b7b8  mov     [rcx+12C4h], dil
0x18001b7bf  mov     dword ptr [rcx+1228h], 0FFFFFFFFh
0x18001b7c9  mov     qword ptr [rcx+1220h], 1
0x18001b7d4  test    r13d, r13d
0x18001b7d7  jnz     short loc_18001B7EB
0x18001b7d9  mov     edx, ebp
0x18001b7db  mov     rcx, r15
0x18001b7de  call    ?resetFreqBandTables@@YA?AW4SBR_ERROR@@PEAUSBR_HEADER_DATA@@I@Z; resetFreqBandTables(SBR_HEADER_DATA *,uint)
0x18001b7e3  test    eax, eax
0x18001b7e5  jnz     loc_18001B948
0x18001b7eb  lea     rcx, [rsi+0F30h]; void *
0x18001b7f2  imul    r14d, ebx
0x18001b7f6  xor     edx, edx; Val
0x18001b7f8  mov     r8d, 0E0h; Size
0x18001b7fe  mov     edi, ebx
0x18001b800  call    memset_0
0x18001b805  xor     eax, eax
0x18001b807  lea     r10, [r15+0A6h]
0x18001b80e  xorps   xmm0, xmm0
0x18001b811  lea     r9, [r15+0ACh]
0x18001b818  movups  xmmword ptr [rsi+1010h], xmm0
0x18001b81f  mov     [rsi+1020h], rax
0x18001b826  lea     rcx, [rsi+12D0h]
0x18001b82d  movups  xmmword ptr [rsi+1028h], xmm0
0x18001b834  mov     [rsi+1038h], eax
0x18001b83a  mov     [rsi+103Ch], al
0x18001b840  mov     eax, [rsp+0B8h+arg_30]
0x18001b847  mov     [rsp+0B8h+var_58], eax
0x18001b84b  mov     [rsi+103Dh], bl
0x18001b851  movups  xmmword ptr [rsi+1040h], xmm0
0x18001b858  mov     [rsp+0B8h+var_60], r13d
0x18001b85d  movups  xmmword ptr [rsi+104Dh], xmm0
0x18001b864  movzx   edx, byte ptr [r15+2Ah]
0x18001b869  mov     eax, [r15+0Ch]
0x18001b86d  movzx   r11d, byte ptr [r15+2Dh]
0x18001b872  movzx   ebx, byte ptr [r15+2Bh]
0x18001b877  movzx   r8d, byte ptr [r15+2Ch]
0x18001b87c  mov     [rsp+0B8h+var_68], eax
0x18001b880  mov     [rsp+0B8h+var_70], edx
0x18001b884  mov     rdx, [rsp+0B8h+arg_10]
0x18001b88c  mov     [rsp+0B8h+var_78], r10
0x18001b891  mov     [rsp+0B8h+var_80], r14d
0x18001b896  mov     [rsp+0B8h+var_88], edi
0x18001b89a  mov     [rsp+0B8h+var_90], r11d
0x18001b89f  mov     [rsp+0B8h+var_98], ebx
0x18001b8a3  call    ?createLppTransposer@@YA?AW4SBR_ERROR@@PEAUSBR_LPP_TRANS@@PEAUTRANSPOSER_SETTINGS@@HPEAEHHHH2HIHH@Z; createLppTransposer(SBR_LPP_TRANS *,TRANSPOSER_SETTINGS *,int,uchar *,int,int,int,int,uchar *,int,uint,int,int)
0x18001b8a8  test    eax, eax
0x18001b8aa  jnz     loc_18001B948
0x18001b8b0  bt      ebp, 8
0x18001b8b4  jnb     loc_18001B948
0x18001b8ba  xor     edx, edx
0x18001b8bc  shr     ebp, 7
0x18001b8bf  and     ebp, 1
0x18001b8c2  lea     eax, [rdx+40h]
0x18001b8c5  lea     ecx, ds:2[rbp*2]
0x18001b8cc  div     ecx
0x18001b8ce  mov     ecx, r14d
0x18001b8d1  mov     edx, eax
0x18001b8d3  mov     ebx, eax
0x18001b8d5  call    ?cdkCallocMatrix2D_int_aligned@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int_aligned(uint,uint,uint,MEMORY_SECTION)
0x18001b8da  mov     [rsi+3FA8h], rax
0x18001b8e1  test    rax, rax
0x18001b8e4  jz      short loc_18001B943
0x18001b8e6  mov     edx, ebx
0x18001b8e8  mov     [rsi+3FB0h], rax
0x18001b8ef  mov     ecx, r14d
0x18001b8f2  call    ?cdkCallocMatrix2D_int_aligned@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int_aligned(uint,uint,uint,MEMORY_SECTION)
0x18001b8f7  mov     [rsi+3FB8h], rax
0x18001b8fe  test    rax, rax
0x18001b901  jz      short loc_18001B943
0x18001b903  mov     edx, ebx
0x18001b905  mov     ecx, r14d
0x18001b908  call    ?cdkCallocMatrix2D_int_aligned@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int_aligned(uint,uint,uint,MEMORY_SECTION)
0x18001b90d  mov     [rsi+3FC0h], rax
0x18001b914  test    rax, rax
0x18001b917  jz      short loc_18001B943
0x18001b919  mov     edx, ebx
0x18001b91b  mov     ecx, r14d
0x18001b91e  call    ?cdkCallocMatrix2D_int_aligned@@YAPEAPEAXIIIW4MEMORY_SECTION@@@Z; cdkCallocMatrix2D_int_aligned(uint,uint,uint,MEMORY_SECTION)
0x18001b923  mov     [rsi+3FC8h], rax
0x18001b92a  test    rax, rax
0x18001b92d  jz      short loc_18001B943
0x18001b92f  lea     rcx, [rsi+3DC0h]
0x18001b936  mov     r9d, ebp
0x18001b939  mov     edx, r12d
0x18001b93c  call    ?QmfTransposerCreate@@YA?AW4SBR_ERROR@@PEAPEAUhbeTransposer@@HHH@Z; QmfTransposerCreate(hbeTransposer * *,int,int,int)
0x18001b941  jmp     short loc_18001B948
0x18001b943  mov     eax, 4
0x18001b948  add     rsp, 78h
0x18001b94c  pop     r15
0x18001b94e  pop     r14
0x18001b950  pop     r13
0x18001b952  pop     r12
0x18001b954  pop     rdi
0x18001b955  pop     rsi
0x18001b956  pop     rbp
0x18001b957  pop     rbx
0x18001b958  retn
```
