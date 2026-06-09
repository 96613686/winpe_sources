# CVideoObjectDecoder::UpdateMBPacked_PerBlk(uchar *,uchar const *,uchar const *,uchar const *,CMBMode const *)

- ea: `0x18000c164`
- end: `0x18000c322`
- name: `?UpdateMBPacked_PerBlk@CVideoObjectDecoder@@AEAAXPEAEPEBE11PEBVCMBMode@@@Z`
- size: `446`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const struct CMBMode *)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000baf0`
- `0x18000bc80`
- `0x180011aa8`

## callees

- `0x18000c164`
- `0x180022010`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::UpdateMBPacked_PerBlk(
        CVideoObjectDecoder *this,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        const struct CMBMode *a6)
{
  char *v10; // r15
  _DWORD *v11; // r12
  const unsigned __int8 *v12; // rbp
  unsigned __int8 *v13; // r14
  const unsigned __int8 *v14; // rsi
  const unsigned __int8 *v15; // r13
  unsigned __int8 *v16; // r14
  const unsigned __int8 *v17; // rbp
  __int64 v18; // rax
  const unsigned __int8 *v19; // rsi
  const unsigned __int8 *v20; // r13

  if ( !*((_DWORD *)a6 + 4) || *((_DWORD *)a6 + 9) || *((_DWORD *)a6 + 10) )
  {
    (*((void (__fastcall **)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))this
     + 188))(
      a2,
      a3,
      a4,
      a5,
      *((_DWORD *)this + 84),
      *((_DWORD *)this + 85),
      *((_DWORD *)this + 342));
  }
  else
  {
    v10 = (char *)this + 1520;
    v11 = (_DWORD *)((char *)this + 1368);
    if ( *((_DWORD *)a6 + 5) )
      (*(void (__fastcall **)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))v10)(
        a2,
        a3,
        a4,
        a5,
        *((_DWORD *)this + 84),
        *((_DWORD *)this + 85),
        *v11);
    v12 = a3 + 8;
    v13 = &a2[*((int *)this + 346)];
    v14 = a4 + 4;
    v15 = a5 + 4;
    if ( *((_DWORD *)a6 + 6) )
      (*(void (__fastcall **)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))v10)(
        v13,
        v12,
        v14,
        v15,
        *((_DWORD *)this + 84),
        *((_DWORD *)this + 85),
        *v11);
    v16 = &v13[*((int *)this + 348)];
    v17 = &v12[*((int *)this + 940)];
    v18 = *((int *)this + 941);
    v19 = &v14[v18];
    v20 = &v15[v18];
    if ( *((_DWORD *)a6 + 7) )
      (*(void (__fastcall **)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))v10)(
        v16,
        v17,
        v19,
        v20,
        *((_DWORD *)this + 84),
        *((_DWORD *)this + 85),
        *v11);
    if ( *((_DWORD *)a6 + 8) )
      (*(void (__fastcall **)(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))v10)(
        &v16[*((int *)this + 346)],
        v17 + 8,
        v19 + 4,
        v20 + 4,
        *((_DWORD *)this + 84),
        *((_DWORD *)this + 85),
        *v11);
  }
}

```

## disassembly

```asm
0x18000c164  push    rbx
0x18000c166  push    rbp
0x18000c167  push    rsi
0x18000c168  push    rdi
0x18000c169  push    r12
0x18000c16b  push    r13
0x18000c16d  push    r14
0x18000c16f  push    r15
0x18000c171  sub     rsp, 48h
0x18000c175  mov     rdi, [rsp+88h+arg_28]
0x18000c17d  xor     eax, eax
0x18000c17f  mov     rsi, r9
0x18000c182  mov     rbp, r8
0x18000c185  mov     r14, rdx
0x18000c188  mov     rbx, rcx
0x18000c18b  cmp     [rdi+10h], eax
0x18000c18e  jz      loc_18000C2D6
0x18000c194  cmp     [rdi+24h], eax
0x18000c197  jnz     loc_18000C2D6
0x18000c19d  cmp     [rdi+28h], eax
0x18000c1a0  jnz     loc_18000C2D6
0x18000c1a6  lea     r15, [rcx+5F0h]
0x18000c1ad  mov     r13, [rsp+88h+arg_20]
0x18000c1b5  lea     r12, [rcx+558h]
0x18000c1bc  cmp     [rdi+14h], eax
0x18000c1bf  jz      short loc_18000C1F1
0x18000c1c1  mov     ecx, [r12]
0x18000c1c5  mov     r9, r13
0x18000c1c8  mov     rax, [r15]
0x18000c1cb  mov     r8, rsi
0x18000c1ce  mov     [rsp+88h+var_58], ecx
0x18000c1d2  mov     rdx, rbp
0x18000c1d5  mov     ecx, [rbx+154h]
0x18000c1db  mov     [rsp+88h+var_60], ecx
0x18000c1df  mov     ecx, [rbx+150h]
0x18000c1e5  mov     [rsp+88h+var_68], ecx
0x18000c1e9  mov     rcx, r14
0x18000c1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1f1  movsxd  rax, dword ptr [rbx+568h]
0x18000c1f8  add     rbp, 8
0x18000c1fc  add     r14, rax
0x18000c1ff  add     rsi, 4
0x18000c203  add     r13, 4
0x18000c207  cmp     dword ptr [rdi+18h], 0
0x18000c20b  jz      short loc_18000C23D
0x18000c20d  mov     ecx, [r12]
0x18000c211  mov     r9, r13
0x18000c214  mov     rax, [r15]
0x18000c217  mov     r8, rsi
0x18000c21a  mov     [rsp+88h+var_58], ecx
0x18000c21e  mov     rdx, rbp
0x18000c221  mov     ecx, [rbx+154h]
0x18000c227  mov     [rsp+88h+var_60], ecx
0x18000c22b  mov     ecx, [rbx+150h]
0x18000c231  mov     [rsp+88h+var_68], ecx
0x18000c235  mov     rcx, r14
0x18000c238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23d  movsxd  rax, dword ptr [rbx+570h]
0x18000c244  add     r14, rax
0x18000c247  movsxd  rax, dword ptr [rbx+0EB0h]
0x18000c24e  add     rbp, rax
0x18000c251  movsxd  rax, dword ptr [rbx+0EB4h]
0x18000c258  add     rsi, rax
0x18000c25b  add     r13, rax
0x18000c25e  cmp     dword ptr [rdi+1Ch], 0
0x18000c262  jz      short loc_18000C294
0x18000c264  mov     ecx, [r12]
0x18000c268  mov     r9, r13
0x18000c26b  mov     rax, [r15]
0x18000c26e  mov     r8, rsi
0x18000c271  mov     [rsp+88h+var_58], ecx
0x18000c275  mov     rdx, rbp
0x18000c278  mov     ecx, [rbx+154h]
0x18000c27e  mov     [rsp+88h+var_60], ecx
0x18000c282  mov     ecx, [rbx+150h]
0x18000c288  mov     [rsp+88h+var_68], ecx
0x18000c28c  mov     rcx, r14
0x18000c28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c294  cmp     dword ptr [rdi+20h], 0
0x18000c298  jz      short loc_18000C311
0x18000c29a  mov     r10d, [r12]
0x18000c29e  lea     r9, [r13+4]
0x18000c2a2  movsxd  rcx, dword ptr [rbx+568h]
0x18000c2a9  lea     r8, [rsi+4]
0x18000c2ad  mov     rax, [r15]
0x18000c2b0  lea     rdx, [rbp+8]
0x18000c2b4  mov     [rsp+88h+var_58], r10d
0x18000c2b9  add     rcx, r14
0x18000c2bc  mov     r10d, [rbx+154h]
0x18000c2c3  mov     [rsp+88h+var_60], r10d
0x18000c2c8  mov     r10d, [rbx+150h]
0x18000c2cf  mov     [rsp+88h+var_68], r10d
0x18000c2d4  jmp     short loc_18000C30C
0x18000c2d6  mov     ecx, [rcx+558h]
0x18000c2dc  mov     r8, rsi
0x18000c2df  mov     r9, [rsp+88h+arg_20]
0x18000c2e7  mov     rdx, rbp
0x18000c2ea  mov     rax, [rbx+5E0h]
0x18000c2f1  mov     [rsp+88h+var_58], ecx
0x18000c2f5  mov     ecx, [rbx+154h]
0x18000c2fb  mov     [rsp+88h+var_60], ecx
0x18000c2ff  mov     ecx, [rbx+150h]
0x18000c305  mov     [rsp+88h+var_68], ecx
0x18000c309  mov     rcx, r14
0x18000c30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c311  add     rsp, 48h
0x18000c315  pop     r15
0x18000c317  pop     r14
0x18000c319  pop     r13
0x18000c31b  pop     r12
0x18000c31d  pop     rdi
0x18000c31e  pop     rsi
0x18000c31f  pop     rbp
0x18000c320  pop     rbx
0x18000c321  retn
```
