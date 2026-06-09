# configure_text_mode(int,`anonymous namespace'::file_options,int,__crt_lowio_text_mode &)

- ea: `0x1400241ac`
- end: `0x14002442b`
- name: `?configure_text_mode@@YAHHUfile_options@?A0xa9d50aae@@HAEAW4__crt_lowio_text_mode@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(unsigned int, __int64, int, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140024704`

## callees

- `0x14000471c`
- `0x14000fa6c`
- `0x140018abc`
- `0x140019a10`
- `0x14001a72c`
- `0x140022ad4`
- `0x1400241ac`

## pseudocode

```c
__int64 __fastcall configure_text_mode(unsigned int a1, __int64 a2, int a3, _BYTE *a4)
{
  int v5; // ebx
  int v7; // esi
  int v9; // ecx
  int v10; // edi
  unsigned int v11; // eax
  int v12; // ecx
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // [rsp+50h] [rbp+8h] BYREF

  v5 = 0;
  *a4 = 0;
  v7 = a3;
  if ( *(char *)(qword_1400D69C0[(__int64)(int)a1 >> 6] + 72LL * (a1 & 0x3F) + 56) >= 0 )
    return 0;
  if ( (a3 & 0x74000) == 0 )
  {
    v20 = 0;
    if ( get_fmode(&v20) )
      invoke_watson(0, 0, 0, 0, 0);
    if ( (v20 & 0x74000) != 0 )
      v7 |= v20 & 0x74000;
    else
      v7 |= 0x4000u;
  }
  v9 = v7 & 0x74000;
  v10 = 2;
  if ( (v7 & 0x74000) == 0x4000 )
  {
    *a4 = 0;
    goto LABEL_15;
  }
  if ( ((v9 - 0x10000) & 0xFFFFBFFF) == 0 )
  {
    if ( (v7 & 0x301) != 0x301 )
      goto LABEL_15;
LABEL_13:
    *a4 = 2;
    goto LABEL_15;
  }
  if ( ((v9 - 0x20000) & 0xFFFFBFFF) == 0 )
    goto LABEL_13;
  if ( ((v9 - 0x40000) & 0xFFFFBFFF) == 0 )
    *a4 = 1;
LABEL_15:
  if ( (v7 & 0x70000) == 0 || (*(_BYTE *)a2 & 0x40) != 0 )
    return 0;
  v11 = *(_DWORD *)(a2 + 4) & 0xC0000000;
  if ( v11 != 0x40000000 )
  {
    if ( v11 == 0x80000000 )
      goto LABEL_32;
    if ( v11 != -1073741824 )
      return 0;
  }
  if ( *(_DWORD *)(a2 + 8) != 1 && *(_DWORD *)(a2 + 8) != 2 )
  {
    if ( *(_DWORD *)(a2 + 8) != 3 && *(_DWORD *)(a2 + 8) != 4 )
    {
      if ( *(_DWORD *)(a2 + 8) != 5 )
        return 0;
      goto LABEL_25;
    }
    if ( lseeki64_nolock(a1, 0, 2) )
    {
      if ( lseeki64_nolock(a1, 0, 0) == -1 )
        return *(unsigned int *)sub_14000FA6C(v16, v15);
      if ( (*(_DWORD *)(a2 + 4) & 0x80000000) == 0 )
        return 0;
LABEL_32:
      v20 = 0;
      v18 = sub_140018ABC(a1, &v20, 3);
      if ( v18 == -1 )
        return *(unsigned int *)sub_14000FA6C(v16, v15);
      if ( v18 != 2 )
      {
        if ( v18 != 3 )
          goto LABEL_42;
        if ( v20 == 12565487 )
        {
          *a4 = 1;
          return 0;
        }
      }
      if ( (unsigned __int16)v20 == 65534 )
      {
        *(_DWORD *)sub_14000FA6C((unsigned __int16)v20, v15) = 22;
        return *(unsigned int *)sub_14000FA6C(v16, v15);
      }
      if ( (unsigned __int16)v20 == 65279 )
      {
        if ( lseeki64_nolock(a1, 2, 0) != -1 )
        {
          *a4 = 2;
          return 0;
        }
        return *(unsigned int *)sub_14000FA6C(v16, v15);
      }
LABEL_42:
      if ( lseeki64_nolock(a1, 0, 0) != -1 )
        return 0;
      return *(unsigned int *)sub_14000FA6C(v16, v15);
    }
  }
LABEL_25:
  v12 = (char)*a4;
  v20 = 0;
  v13 = v12 - 1;
  if ( !v13 )
  {
    v10 = 3;
    v14 = 12565487;
LABEL_45:
    v20 = v14;
    while ( 1 )
    {
      v19 = write(a1, (char *)&v20 + v5, v10 - v5);
      if ( v19 == -1 )
        break;
      v5 += v19;
      if ( v10 <= v5 )
        return 0;
    }
    return *(unsigned int *)sub_14000FA6C(v16, v15);
  }
  if ( v13 == 1 )
  {
    v14 = 65279;
    goto LABEL_45;
  }
  return 0;
}

```

## disassembly

```asm
0x1400241ac  mov     r11, rsp
0x1400241af  mov     [r11+10h], rbx
0x1400241b3  mov     [r11+18h], rbp
0x1400241b7  mov     [r11+20h], rsi
0x1400241bb  push    rdi
0x1400241bc  push    r14
0x1400241be  push    r15
0x1400241c0  sub     rsp, 30h
0x1400241c4  movsxd  r15, ecx
0x1400241c7  xor     ebx, ebx
0x1400241c9  mov     r10, r15
0x1400241cc  mov     [r9], bl
0x1400241cf  and     r10d, 3Fh
0x1400241d3  lea     rcx, qword_1400D69C0
0x1400241da  mov     rax, r15
0x1400241dd  mov     r14, r9
0x1400241e0  sar     rax, 6
0x1400241e4  mov     esi, r8d
0x1400241e7  mov     rbp, rdx
0x1400241ea  lea     r10, [r10+r10*8]
0x1400241ee  mov     rax, [rcx+rax*8]
0x1400241f2  cmp     [rax+r10*8+38h], bl
0x1400241f7  jge     loc_1400243FC
0x1400241fd  mov     edi, 74000h
0x140024202  test    edi, r8d
0x140024205  jnz     short loc_140024228
0x140024207  lea     rcx, [r11+8]; PMode
0x14002420b  mov     [rsp+48h+arg_0], ebx
0x14002420f  call    _get_fmode
0x140024214  test    eax, eax
0x140024216  jnz     loc_140024417
0x14002421c  mov     eax, [rsp+48h+arg_0]
0x140024220  and     eax, edi
0x140024222  jnz     short loc_140024262
0x140024224  bts     esi, 0Eh
0x140024228  mov     ecx, esi
0x14002422a  and     ecx, edi
0x14002422c  mov     edi, 2
0x140024231  cmp     ecx, 4000h
0x140024237  jz      short loc_140024278
0x140024239  lea     eax, [rcx-10000h]
0x14002423f  mov     edx, 0FFFFBFFFh
0x140024244  test    edx, eax
0x140024246  jz      short loc_140024266
0x140024248  lea     eax, [rcx-20000h]
0x14002424e  test    edx, eax
0x140024250  jz      short loc_140024273
0x140024252  lea     eax, [rcx-40000h]
0x140024258  test    edx, eax
0x14002425a  jnz     short loc_14002427B
0x14002425c  mov     byte ptr [r14], 1
0x140024260  jmp     short loc_14002427B
0x140024262  or      esi, eax
0x140024264  jmp     short loc_140024228
0x140024266  mov     ecx, 301h
0x14002426b  mov     eax, esi
0x14002426d  and     eax, ecx
0x14002426f  cmp     eax, ecx
0x140024271  jnz     short loc_14002427B
0x140024273  mov     [r14], dil
0x140024276  jmp     short loc_14002427B
0x140024278  mov     [r14], bl
0x14002427b  test    esi, 70000h
0x140024281  jz      loc_1400243FC
0x140024287  test    byte ptr [rbp+0], 40h
0x14002428b  jnz     loc_1400243FC
0x140024291  mov     eax, [rbp+4]
0x140024294  mov     ecx, 0C0000000h
0x140024299  and     eax, ecx
0x14002429b  mov     esi, 80000000h
0x1400242a0  cmp     eax, 40000000h
0x1400242a5  jz      short loc_1400242B7
0x1400242a7  cmp     eax, esi
0x1400242a9  jz      loc_140024335
0x1400242af  cmp     eax, ecx
0x1400242b1  jnz     loc_1400243FC
0x1400242b7  mov     ecx, [rbp+8]
0x1400242ba  sub     ecx, 1
0x1400242bd  jz      short loc_1400242D7
0x1400242bf  sub     ecx, 1
0x1400242c2  jz      short loc_1400242D7
0x1400242c4  sub     ecx, 1
0x1400242c7  jz      short loc_1400242FB
0x1400242c9  sub     ecx, 1
0x1400242cc  jz      short loc_1400242FB
0x1400242ce  cmp     ecx, 1
0x1400242d1  jnz     loc_1400243FC
0x1400242d7  movsx   ecx, byte ptr [r14]
0x1400242db  mov     [rsp+48h+arg_0], ebx
0x1400242df  sub     ecx, 1
0x1400242e2  jz      loc_1400243C6
0x1400242e8  cmp     ecx, 1
0x1400242eb  jnz     loc_1400243FC
0x1400242f1  mov     eax, 0FEFFh
0x1400242f6  jmp     loc_1400243D0
0x1400242fb  mov     r8d, edi
0x1400242fe  xor     edx, edx
0x140024300  mov     ecx, r15d
0x140024303  call    _lseeki64_nolock
0x140024308  test    rax, rax
0x14002430b  jz      short loc_1400242D7
0x14002430d  xor     r8d, r8d
0x140024310  xor     edx, edx
0x140024312  mov     ecx, r15d
0x140024315  call    _lseeki64_nolock
0x14002431a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002431e  jnz     short loc_14002432C
0x140024320  call    sub_14000FA6C
0x140024325  mov     eax, [rax]
0x140024327  jmp     loc_1400243FE
0x14002432c  test    [rbp+4], esi
0x14002432f  jz      loc_1400243FC
0x140024335  mov     r8d, 3
0x14002433b  mov     [rsp+48h+arg_0], ebx
0x14002433f  lea     rdx, [rsp+48h+arg_0]
0x140024344  mov     ecx, r15d
0x140024347  call    sub_140018ABC
0x14002434c  cmp     eax, 0FFFFFFFFh
0x14002434f  jz      short loc_140024320
0x140024351  cmp     eax, edi
0x140024353  jz      short loc_14002436E
0x140024355  cmp     eax, 3
0x140024358  jnz     short loc_1400243AE
0x14002435a  mov     eax, 0BFBBEFh
0x14002435f  cmp     [rsp+48h+arg_0], eax
0x140024363  jnz     short loc_14002436E
0x140024365  mov     byte ptr [r14], 1
0x140024369  jmp     loc_1400243FC
0x14002436e  movzx   ecx, word ptr [rsp+48h+arg_0]
0x140024373  cmp     ecx, 0FFFEh
0x140024379  jnz     short loc_140024388
0x14002437b  call    sub_14000FA6C
0x140024380  mov     dword ptr [rax], 16h
0x140024386  jmp     short loc_140024320
0x140024388  mov     eax, 0FEFFh
0x14002438d  cmp     ecx, eax
0x14002438f  jnz     short loc_1400243AE
0x140024391  xor     r8d, r8d
0x140024394  mov     rdx, rdi
0x140024397  mov     ecx, r15d
0x14002439a  call    _lseeki64_nolock
0x14002439f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400243a3  jz      loc_140024320
0x1400243a9  mov     [r14], dil
0x1400243ac  jmp     short loc_1400243FC
0x1400243ae  xor     r8d, r8d
0x1400243b1  xor     edx, edx
0x1400243b3  mov     ecx, r15d
0x1400243b6  call    _lseeki64_nolock
0x1400243bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400243bf  jnz     short loc_1400243FC
0x1400243c1  jmp     loc_140024320
0x1400243c6  mov     edi, 3
0x1400243cb  mov     eax, 0BFBBEFh
0x1400243d0  mov     [rsp+48h+arg_0], eax
0x1400243d4  mov     r8d, edi
0x1400243d7  movsxd  rax, ebx
0x1400243da  lea     rdx, [rsp+48h+arg_0]
0x1400243df  sub     r8d, ebx; MaxCharCount
0x1400243e2  add     rdx, rax; Buf
0x1400243e5  mov     ecx, r15d; FileHandle
0x1400243e8  call    _write
0x1400243ed  cmp     eax, 0FFFFFFFFh
0x1400243f0  jz      loc_140024320
0x1400243f6  add     ebx, eax
0x1400243f8  cmp     edi, ebx
0x1400243fa  jg      short loc_1400243D4
0x1400243fc  xor     eax, eax
0x1400243fe  mov     rbx, [rsp+48h+arg_8]
0x140024403  mov     rbp, [rsp+48h+arg_10]
0x140024408  mov     rsi, [rsp+48h+arg_18]
0x14002440d  add     rsp, 30h
0x140024411  pop     r15
0x140024413  pop     r14
0x140024415  pop     rdi
0x140024416  retn
0x140024417  xor     r9d, r9d; LineNo
0x14002441a  mov     [rsp+48h+Reserved], rbx; Reserved
0x14002441f  xor     r8d, r8d; FileName
0x140024422  xor     edx, edx; FunctionName
0x140024424  xor     ecx, ecx; Expression
0x140024426  call    _invoke_watson
```
