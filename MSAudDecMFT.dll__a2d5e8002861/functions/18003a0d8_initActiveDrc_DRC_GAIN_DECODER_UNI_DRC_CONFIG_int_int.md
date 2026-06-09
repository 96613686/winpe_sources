# initActiveDrc(DRC_GAIN_DECODER *,UNI_DRC_CONFIG *,int,int)

- ea: `0x18003a0d8`
- end: `0x18003a212`
- name: `?initActiveDrc@@YA?AW4DRC_ERROR@@PEAUDRC_GAIN_DECODER@@PEAUUNI_DRC_CONFIG@@HH@Z`
- size: `314`
- prototype: `enum DRC_ERROR __high(struct DRC_GAIN_DECODER *, struct UNI_DRC_CONFIG *, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800394f8`

## callees

- `0x180039ee4`
- `0x18003a0d8`
- `0x18003a388`
- `0x18003b0d4`

## pseudocode

```c
__int64 __fastcall initActiveDrc(_DWORD *a1, struct UNI_DRC_CONFIG *a2, int a3, int a4)
{
  int v4; // ebp
  struct DRC_INSTRUCTIONS_UNI_DRC *v7; // rax
  struct UNI_DRC_CONFIG *v8; // rcx
  struct DRC_INSTRUCTIONS_UNI_DRC *v9; // rsi
  struct DRC_COEFFICIENTS_UNI_DRC *v10; // rdi
  int v11; // r9d
  int v12; // r8d
  int v13; // ecx
  __int64 result; // rax
  int v15; // ecx
  struct DRC_COEFFICIENTS_UNI_DRC *v16; // rax

  v4 = (int)a2;
  v7 = selectDrcInstructions(a2, a3);
  v9 = v7;
  if ( !v7 )
    return 4294967196LL;
  v10 = 0;
  if ( *(char *)v7 >= 0 )
  {
    v16 = selectDrcCoefficients(v8, *((unsigned __int8 *)v7 + 2));
    v10 = v16;
    if ( v16 && (!*((_BYTE *)v16 + 1) || *((unsigned __int16 *)v16 + 1) == a1[1]) )
    {
      result = generateDrcInstructionsDerivedData(a1[4], v4, (_DWORD)v9, (_DWORD)v16, (__int64)&a1[72 * a1[4] + 6]);
      if ( (_DWORD)result )
        return result;
      goto LABEL_3;
    }
    return 4294967196LL;
  }
LABEL_3:
  v11 = 0;
  *(_QWORD *)&a1[72 * a1[4] + 8] = v9;
  v12 = 0;
  *(_QWORD *)&a1[72 * a1[4] + 10] = v10;
  while ( v12 < *((unsigned __int8 *)v9 + 809) )
  {
    if ( *((_BYTE *)&a1[72 * a1[4] + 30] + v12) > 1u )
    {
      if ( a1[222] != -1 )
        return 4294967196LL;
      v11 = 1;
    }
    ++v12;
  }
  v13 = a1[4];
  if ( v11 )
    a1[222] = v13;
  if ( a1[223] == -1 && !a4 )
    a1[223] = v13;
  result = 0;
  v15 = v13 + 1;
  a1[4] = v15;
  if ( v15 > 3 )
    return 4294967196LL;
  return result;
}

```

## disassembly

```asm
0x18003a0d8  push    rbx
0x18003a0da  push    rbp
0x18003a0db  push    rsi
0x18003a0dc  push    rdi
0x18003a0dd  push    r14
0x18003a0df  sub     rsp, 30h
0x18003a0e3  mov     rbp, rdx
0x18003a0e6  mov     rbx, rcx
0x18003a0e9  mov     rcx, rbp; struct UNI_DRC_CONFIG *
0x18003a0ec  mov     edx, r8d; int
0x18003a0ef  mov     r14d, r9d
0x18003a0f2  call    ?selectDrcInstructions@@YAPEAUDRC_INSTRUCTIONS_UNI_DRC@@PEAUUNI_DRC_CONFIG@@H@Z; selectDrcInstructions(UNI_DRC_CONFIG *,int)
0x18003a0f7  mov     rsi, rax
0x18003a0fa  test    rax, rax
0x18003a0fd  jz      loc_18003A18C
0x18003a103  xor     edi, edi
0x18003a105  cmp     [rax], dil
0x18003a108  jge     short loc_18003A17B
0x18003a10a  movsxd  rax, dword ptr [rbx+10h]
0x18003a10e  xor     r9d, r9d
0x18003a111  lea     rcx, [rax+rax*8]
0x18003a115  shl     rcx, 5
0x18003a119  mov     [rcx+rbx+20h], rsi
0x18003a11e  movsxd  rax, dword ptr [rbx+10h]
0x18003a122  lea     rcx, [rax+rax*8]
0x18003a126  shl     rcx, 5
0x18003a12a  xor     r8d, r8d
0x18003a12d  mov     [rcx+rbx+28h], rdi
0x18003a132  movzx   r10d, byte ptr [rsi+329h]
0x18003a13a  cmp     r8d, r10d
0x18003a13d  jl      short loc_18003A193
0x18003a13f  mov     ecx, [rbx+10h]
0x18003a142  test    r9d, r9d
0x18003a145  jnz     loc_18003A207
0x18003a14b  cmp     dword ptr [rbx+37Ch], 0FFFFFFFFh
0x18003a152  jnz     short loc_18003A15F
0x18003a154  test    r14d, r14d
0x18003a157  jnz     short loc_18003A15F
0x18003a159  mov     [rbx+37Ch], ecx
0x18003a15f  xor     eax, eax
0x18003a161  inc     ecx
0x18003a163  cmp     ecx, 3
0x18003a166  mov     [rbx+10h], ecx
0x18003a169  lea     edx, [rax-64h]
0x18003a16c  cmovg   eax, edx
0x18003a16f  add     rsp, 30h
0x18003a173  pop     r14
0x18003a175  pop     rdi
0x18003a176  pop     rsi
0x18003a177  pop     rbp
0x18003a178  pop     rbx
0x18003a179  retn
0x18003a17b  movzx   edx, byte ptr [rax+2]; int
0x18003a17f  call    ?selectDrcCoefficients@@YAPEAUDRC_COEFFICIENTS_UNI_DRC@@PEAUUNI_DRC_CONFIG@@H@Z; selectDrcCoefficients(UNI_DRC_CONFIG *,int)
0x18003a184  mov     rdi, rax
0x18003a187  test    rax, rax
0x18003a18a  jnz     short loc_18003A1C3
0x18003a18c  mov     eax, 0FFFFFF9Ch
0x18003a191  jmp     short loc_18003A16F
0x18003a193  movsxd  rax, dword ptr [rbx+10h]
0x18003a197  movsxd  rcx, r8d
0x18003a19a  lea     rax, [rax+rax*8]
0x18003a19e  shl     rax, 5
0x18003a1a2  add     rax, rbx
0x18003a1a5  cmp     byte ptr [rcx+rax+78h], 1
0x18003a1aa  jbe     short loc_18003A1BB
0x18003a1ac  cmp     dword ptr [rbx+378h], 0FFFFFFFFh
0x18003a1b3  jnz     short loc_18003A18C
0x18003a1b5  mov     r9d, 1
0x18003a1bb  inc     r8d
0x18003a1be  jmp     loc_18003A13A
0x18003a1c3  cmp     byte ptr [rax+1], 0
0x18003a1c7  jnz     short loc_18003A1FC
0x18003a1c9  movsxd  rcx, dword ptr [rbx+10h]
0x18003a1cd  mov     r9, rdi
0x18003a1d0  mov     r8, rsi
0x18003a1d3  mov     rdx, rbp
0x18003a1d6  lea     rax, [rcx+rcx*8]
0x18003a1da  shl     rax, 5
0x18003a1de  add     rax, 18h
0x18003a1e2  add     rax, rbx
0x18003a1e5  mov     [rsp+58h+var_38], rax
0x18003a1ea  call    _generateDrcInstructionsDerivedData
0x18003a1ef  test    eax, eax
0x18003a1f1  jz      loc_18003A10A
0x18003a1f7  jmp     loc_18003A16F
0x18003a1fc  movzx   ecx, word ptr [rax+2]
0x18003a200  cmp     ecx, [rbx+4]
0x18003a203  jnz     short loc_18003A18C
0x18003a205  jmp     short loc_18003A1C9
0x18003a207  mov     [rbx+378h], ecx
0x18003a20d  jmp     loc_18003A14B
```
