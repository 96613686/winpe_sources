# CspHandleEventRead

- ea: `0x14001dd4c`
- end: `0x14001decb`
- name: `CspHandleEventRead`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001e628`

## callees

- `0x14001dd4c`
- `0x14001e5f4`
- `0x14001f07c`
- `0x14002074c`

## pseudocode

```c
char __fastcall CspHandleEventRead(_DWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  unsigned __int64 v4; // rsi
  unsigned __int128 v6; // rax
  char v7; // r15
  __int64 v9; // rbp
  int v10; // r14d
  unsigned __int64 v11; // rsi
  unsigned int v12; // r14d
  unsigned int v13; // r14d

  v3 = (unsigned int)(*(_DWORD *)(a2 + 128) - *(_DWORD *)(a2 + 40));
  LODWORD(v4) = a1[36];
  v6 = (unsigned int)(*(_DWORD *)(a2 + 128) - *(_DWORD *)(a2 + 40)) * (unsigned __int128)0xCCCCCCCCCCCCCCCDuLL;
  v7 = a3;
  v9 = *((_QWORD *)&v6 + 1) >> 4;
  if ( (unsigned int)v4 > a1[35] )
  {
    v10 = *((_QWORD *)&v6 + 1) >> 4;
    if ( 100 - (int)v4 <= (unsigned int)v9 )
      v10 = 100 - v4;
    LODWORD(v6) = WriteMessageOutput((_DWORD)a1, a2, 0, (int)a1 + 4 * ((int)v4 + 4 * (int)v4 + 114), 20 * v10);
    if ( (v6 & 0x80000000) != 0LL )
      goto LABEL_11;
    v11 = (unsigned int)(v10 + v4);
    a1[34] = 20 * v10;
    LODWORD(v9) = v9 - v10;
    *((_QWORD *)&v6 + 1) = (v11 * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64;
    v4 = v11 % 0x64;
  }
  if ( (_DWORD)v9 )
  {
    v12 = a1[35];
    if ( (unsigned int)v4 < v12 )
    {
      v13 = v12 - v4;
      if ( v13 > (unsigned int)v9 )
        v13 = v9;
      LODWORD(v6) = WriteMessageOutput((_DWORD)a1, a2, a1[34], (int)a1 + 4 * ((int)v4 + 4 * (int)v4 + 114), 20 * v13);
      if ( (v6 & 0x80000000) != 0LL )
      {
LABEL_11:
        *(_DWORD *)(a2 + 8) = v6;
        CspResetInputEventIfEmpty(a1, *((_QWORD *)&v6 + 1), a3, v3);
        goto LABEL_17;
      }
      a1[34] += 20 * v13;
      LODWORD(v4) = v13 + v4;
    }
  }
  if ( !v7 )
  {
    a1[36] = v4;
    CspResetInputEventIfEmpty(a1, *((_QWORD *)&v6 + 1), a3, v3);
    if ( !a1[34] )
      return 0;
  }
  *(_DWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = (unsigned int)a1[34];
  *(_DWORD *)(a2 + 144) = a1[34] / 0x14u;
LABEL_17:
  CspCompleteConsoleIo(a1, a2);
  return 1;
}

```

## disassembly

```asm
0x14001dd4c  push    rbx
0x14001dd4e  push    rbp
0x14001dd4f  push    rsi
0x14001dd50  push    rdi
0x14001dd51  push    r12
0x14001dd53  push    r13
0x14001dd55  push    r14
0x14001dd57  push    r15
0x14001dd59  sub     rsp, 38h
0x14001dd5d  mov     r9d, [rdx+80h]
0x14001dd64  mov     r13, 0CCCCCCCCCCCCCCCDh
0x14001dd6e  sub     r9d, [rdx+28h]
0x14001dd72  mov     rax, r13
0x14001dd75  mov     esi, [rcx+90h]
0x14001dd7b  mov     rdi, rdx
0x14001dd7e  mul     r9
0x14001dd81  mov     r15b, r8b
0x14001dd84  mov     rbx, rcx
0x14001dd87  mov     rbp, rdx
0x14001dd8a  shr     rbp, 4
0x14001dd8e  cmp     esi, [rcx+8Ch]
0x14001dd94  jbe     short loc_14001DE04
0x14001dd96  mov     eax, 64h ; 'd'
0x14001dd9b  lea     rcx, ds:72h[rsi*4]
0x14001dda3  sub     eax, esi
0x14001dda5  mov     r14d, ebp
0x14001dda8  cmp     eax, ebp
0x14001ddaa  mov     rdx, rdi
0x14001ddad  cmovbe  r14d, eax
0x14001ddb1  add     rcx, rsi
0x14001ddb4  xor     r8d, r8d
0x14001ddb7  lea     r9, [rbx+rcx*4]
0x14001ddbb  mov     rcx, rbx
0x14001ddbe  lea     r12d, [r14+r14*4]
0x14001ddc2  shl     r12d, 2
0x14001ddc6  mov     [rsp+78h+var_58], r12d
0x14001ddcb  call    WriteMessageOutput
0x14001ddd0  test    eax, eax
0x14001ddd2  js      short loc_14001DE50
0x14001ddd4  add     esi, r14d
0x14001ddd7  mov     [rbx+88h], r12d
0x14001ddde  mov     rax, 47AE147AE147AE15h
0x14001dde8  sub     ebp, r14d
0x14001ddeb  mul     rsi
0x14001ddee  mov     eax, esi
0x14001ddf0  sub     rax, rdx
0x14001ddf3  shr     rax, 1
0x14001ddf6  add     rax, rdx
0x14001ddf9  shr     rax, 6
0x14001ddfd  imul    rax, 64h ; 'd'
0x14001de01  sub     rsi, rax
0x14001de04  test    ebp, ebp
0x14001de06  jz      short loc_14001DE66
0x14001de08  mov     r14d, [rbx+8Ch]
0x14001de0f  cmp     esi, r14d
0x14001de12  jnb     short loc_14001DE66
0x14001de14  mov     r8d, [rbx+88h]
0x14001de1b  sub     r14d, esi
0x14001de1e  mov     eax, esi
0x14001de20  cmp     r14d, ebp
0x14001de23  mov     rdx, rdi
0x14001de26  cmova   r14d, ebp
0x14001de2a  lea     rcx, ds:72h[rax*4]
0x14001de32  add     rcx, rax
0x14001de35  lea     ebp, [r14+r14*4]
0x14001de39  shl     ebp, 2
0x14001de3c  mov     [rsp+78h+var_58], ebp
0x14001de40  lea     r9, [rbx+rcx*4]
0x14001de44  mov     rcx, rbx
0x14001de47  call    WriteMessageOutput
0x14001de4c  test    eax, eax
0x14001de4e  jns     short loc_14001DE5D
0x14001de50  mov     rcx, rbx
0x14001de53  mov     [rdi+8], eax
0x14001de56  call    CspResetInputEventIfEmpty
0x14001de5b  jmp     short loc_14001DEAD
0x14001de5d  add     [rbx+88h], ebp
0x14001de63  add     esi, r14d
0x14001de66  test    r15b, r15b
0x14001de69  jnz     short loc_14001DE86
0x14001de6b  mov     rcx, rbx
0x14001de6e  mov     [rbx+90h], esi
0x14001de74  call    CspResetInputEventIfEmpty
0x14001de79  cmp     dword ptr [rbx+88h], 0
0x14001de80  ja      short loc_14001DE86
0x14001de82  xor     al, al
0x14001de84  jmp     short loc_14001DEBA
0x14001de86  mov     dword ptr [rdi+8], 0
0x14001de8d  mov     rax, r13
0x14001de90  mov     ecx, [rbx+88h]
0x14001de96  mov     [rdi+10h], rcx
0x14001de9a  mov     ecx, [rbx+88h]
0x14001dea0  mul     rcx
0x14001dea3  shr     rdx, 4
0x14001dea7  mov     [rdi+90h], edx
0x14001dead  mov     rdx, rdi
0x14001deb0  mov     rcx, rbx
0x14001deb3  call    CspCompleteConsoleIo
0x14001deb8  mov     al, 1
0x14001deba  add     rsp, 38h
0x14001debe  pop     r15
0x14001dec0  pop     r14
0x14001dec2  pop     r13
0x14001dec4  pop     r12
0x14001dec6  pop     rdi
0x14001dec7  pop     rsi
0x14001dec8  pop     rbp
0x14001dec9  pop     rbx
0x14001deca  retn
```
