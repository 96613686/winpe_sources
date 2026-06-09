# CDKreadBit

- ea: `0x180013550`
- end: `0x18001369d`
- name: `CDKreadBit`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c510`
- `0x180012d90`
- `0x1800131b4`
- `0x1800133e8`
- `0x180013dac`
- `0x180014ae0`
- `0x180017e54`
- `0x180018e64`
- `0x180019168`
- `0x180019b98`
- `0x180019ec4`
- `0x1800285e0`
- `0x180044774`
- `0x180047994`
- `0x180073f98`
- `0x1800740e8`
- `0x180079960`
- `0x18007a198`
- `0x18007a444`
- `0x18007aa3c`
- `0x180080608`
- `0x180080fc8`
- `0x180081000`
- `0x180081bb4`
- `0x180081d98`
- `0x18008444c`
- `0x1800934b4`

## callees

- `0x180013550`

## pseudocode

```c
__int64 __fastcall CDKreadBit(__int64 a1)
{
  int v2; // ecx
  int v3; // ecx
  unsigned int v5; // edx
  unsigned int v6; // r8d
  int v7; // r11d
  __int64 v8; // rbx
  __int64 v9; // r10
  __int64 v10; // r9
  __int64 v11; // rdi
  __int64 v12; // rsi
  unsigned int v13; // r9d
  int v14; // r8d
  unsigned int v15; // r8d
  int v16; // r8d

  v2 = *(_DWORD *)(a1 + 4);
  if ( v2 )
  {
    v3 = v2 - 1;
    *(_DWORD *)(a1 + 4) = v3;
    return (*(_DWORD *)a1 >> v3) & 1;
  }
  v5 = *(_DWORD *)(a1 + 36);
  v6 = *(_DWORD *)(a1 + 20) + 32;
  *(_DWORD *)(a1 + 8) -= 32;
  v7 = v6 & 7;
  v8 = *(_QWORD *)(a1 + 24);
  v9 = (v6 - 1) >> 3;
  *(_DWORD *)(a1 + 20) = v6 & (v5 - 1);
  v10 = (unsigned int)(v9 - 3);
  v11 = (unsigned int)(v9 - 2);
  v12 = (unsigned int)(v9 - 1);
  if ( v6 > v5 )
  {
    v16 = *(_DWORD *)(a1 + 32) - 1;
    v13 = *(unsigned __int8 *)(((unsigned int)v9 & v16) + v8)
        | ((*(unsigned __int8 *)((v16 & (unsigned int)v12) + v8)
          | ((*(unsigned __int8 *)((v16 & (unsigned int)v11) + v8)
            | (*(unsigned __int8 *)((v16 & (unsigned int)v10) + v8) << 8)) << 8)) << 8);
    if ( v7 )
    {
      v14 = *(unsigned __int8 *)((v16 & (unsigned int)(v9 - 4)) + v8);
      goto LABEL_6;
    }
LABEL_10:
    v15 = v13;
    goto LABEL_7;
  }
  v13 = *(unsigned __int8 *)(v9 + v8)
      | ((*(unsigned __int8 *)(v12 + v8)
        | ((*(unsigned __int8 *)(v11 + v8) | (*(unsigned __int8 *)(v10 + v8) << 8)) << 8)) << 8);
  if ( (v6 & 7) == 0 )
    goto LABEL_10;
  v14 = *(unsigned __int8 *)((unsigned int)(v9 - 4) + v8);
LABEL_6:
  v15 = (v13 >> (8 - v7)) | (v14 << (v7 + 24));
LABEL_7:
  *(_DWORD *)a1 = v15;
  *(_DWORD *)(a1 + 4) = 31;
  return v15 >> 31;
}

```

## disassembly

```asm
0x180013550  sub     rsp, 8
0x180013554  mov     rax, rcx
0x180013557  mov     ecx, [rcx+4]
0x18001355a  test    ecx, ecx
0x18001355c  jz      short loc_180013570
0x18001355e  dec     ecx
0x180013560  mov     [rax+4], ecx
0x180013563  mov     eax, [rax]
0x180013565  shr     eax, cl
0x180013567  and     eax, 1
0x18001356a  add     rsp, 8
0x18001356e  retn
0x180013570  mov     r8d, [rax+14h]
0x180013574  mov     edx, [rax+24h]
0x180013577  add     r8d, 20h ; ' '
0x18001357b  add     dword ptr [rax+8], 0FFFFFFE0h
0x18001357f  mov     r11d, r8d
0x180013582  mov     [rsp+8+arg_0], rbx
0x180013587  and     r11d, 7
0x18001358b  mov     rbx, [rax+18h]
0x18001358f  mov     [rsp+8+arg_8], rsi
0x180013594  lea     r10d, [r8-1]
0x180013598  shr     r10d, 3
0x18001359c  lea     ecx, [rdx-1]
0x18001359f  and     ecx, r8d
0x1800135a2  mov     [rsp+8+var_8], rdi
0x1800135a6  mov     [rax+14h], ecx
0x1800135a9  lea     r9d, [r10-3]
0x1800135ad  lea     edi, [r10-2]
0x1800135b1  lea     esi, [r10-1]
0x1800135b5  cmp     r8d, edx
0x1800135b8  ja      short loc_18001362D
0x1800135ba  movzx   r9d, byte ptr [r9+rbx]
0x1800135bf  movzx   edx, byte ptr [rdi+rbx]
0x1800135c3  shl     r9d, 8
0x1800135c7  or      r9d, edx
0x1800135ca  movzx   edx, byte ptr [rsi+rbx]
0x1800135ce  shl     r9d, 8
0x1800135d2  or      r9d, edx
0x1800135d5  movzx   edx, byte ptr [r10+rbx]
0x1800135da  shl     r9d, 8
0x1800135de  or      r9d, edx
0x1800135e1  test    r11d, r11d
0x1800135e4  jz      loc_180013695
0x1800135ea  lea     ecx, [r10-4]
0x1800135ee  movzx   r8d, byte ptr [rcx+rbx]
0x1800135f3  lea     ecx, [r11+18h]
0x1800135f7  shl     r8d, cl
0x1800135fa  mov     ecx, 8
0x1800135ff  sub     ecx, r11d
0x180013602  shr     r9d, cl
0x180013605  or      r8d, r9d
0x180013608  mov     rdi, [rsp+8+var_8]
0x18001360c  mov     rsi, [rsp+8+arg_8]
0x180013611  mov     rbx, [rsp+8+arg_0]
0x180013616  mov     [rax], r8d
0x180013619  shr     r8d, 1Fh
0x18001361d  mov     dword ptr [rax+4], 1Fh
0x180013624  mov     eax, r8d
0x180013627  add     rsp, 8
0x18001362b  retn
0x18001362d  mov     r8d, [rax+20h]
0x180013631  mov     edx, r9d
0x180013634  dec     r8d
0x180013637  mov     ecx, r8d
0x18001363a  and     rdx, rcx
0x18001363d  mov     ecx, r8d
0x180013640  movzx   r9d, byte ptr [rdx+rbx]
0x180013645  shl     r9d, 8
0x180013649  mov     edx, edi
0x18001364b  and     rdx, rcx
0x18001364e  movzx   ecx, byte ptr [rdx+rbx]
0x180013652  or      r9d, ecx
0x180013655  mov     edx, esi
0x180013657  shl     r9d, 8
0x18001365b  mov     ecx, r8d
0x18001365e  and     rdx, rcx
0x180013661  movzx   ecx, byte ptr [rdx+rbx]
0x180013665  or      r9d, ecx
0x180013668  mov     edx, r8d
0x18001366b  mov     ecx, r10d
0x18001366e  and     rdx, rcx
0x180013671  shl     r9d, 8
0x180013675  movzx   ecx, byte ptr [rdx+rbx]
0x180013679  or      r9d, ecx
0x18001367c  test    r11d, r11d
0x18001367f  jz      short loc_180013695
0x180013681  mov     ecx, r8d
0x180013684  lea     edx, [r10-4]
0x180013688  and     rdx, rcx
0x18001368b  movzx   r8d, byte ptr [rdx+rbx]
0x180013690  jmp     loc_1800135F3
0x180013695  mov     r8d, r9d
0x180013698  jmp     loc_180013608
```
