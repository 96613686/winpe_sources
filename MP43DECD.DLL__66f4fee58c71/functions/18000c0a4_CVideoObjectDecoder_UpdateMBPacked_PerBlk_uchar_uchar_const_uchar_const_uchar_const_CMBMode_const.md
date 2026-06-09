# CVideoObjectDecoder::UpdateMBPacked_PerBlk(uchar *,uchar const *,uchar const *,uchar const *,CMBMode const *)

- ea: `0x18000c0a4`
- end: `0x18000c262`
- name: `?UpdateMBPacked_PerBlk@CVideoObjectDecoder@@AEAAXPEAEPEBE11PEBVCMBMode@@@Z`
- size: `446`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const struct CMBMode *)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000ba30`
- `0x18000bbc0`
- `0x1800119e8`

## callees

- `0x18000c0a4`
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
0x18000c0a4  push    rbx
0x18000c0a6  push    rbp
0x18000c0a7  push    rsi
0x18000c0a8  push    rdi
0x18000c0a9  push    r12
0x18000c0ab  push    r13
0x18000c0ad  push    r14
0x18000c0af  push    r15
0x18000c0b1  sub     rsp, 48h
0x18000c0b5  mov     rdi, [rsp+88h+arg_28]
0x18000c0bd  xor     eax, eax
0x18000c0bf  mov     rsi, r9
0x18000c0c2  mov     rbp, r8
0x18000c0c5  mov     r14, rdx
0x18000c0c8  mov     rbx, rcx
0x18000c0cb  cmp     [rdi+10h], eax
0x18000c0ce  jz      loc_18000C216
0x18000c0d4  cmp     [rdi+24h], eax
0x18000c0d7  jnz     loc_18000C216
0x18000c0dd  cmp     [rdi+28h], eax
0x18000c0e0  jnz     loc_18000C216
0x18000c0e6  lea     r15, [rcx+5F0h]
0x18000c0ed  mov     r13, [rsp+88h+arg_20]
0x18000c0f5  lea     r12, [rcx+558h]
0x18000c0fc  cmp     [rdi+14h], eax
0x18000c0ff  jz      short loc_18000C131
0x18000c101  mov     ecx, [r12]
0x18000c105  mov     r9, r13
0x18000c108  mov     rax, [r15]
0x18000c10b  mov     r8, rsi
0x18000c10e  mov     [rsp+88h+var_58], ecx
0x18000c112  mov     rdx, rbp
0x18000c115  mov     ecx, [rbx+154h]
0x18000c11b  mov     [rsp+88h+var_60], ecx
0x18000c11f  mov     ecx, [rbx+150h]
0x18000c125  mov     [rsp+88h+var_68], ecx
0x18000c129  mov     rcx, r14
0x18000c12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c131  movsxd  rax, dword ptr [rbx+568h]
0x18000c138  add     rbp, 8
0x18000c13c  add     r14, rax
0x18000c13f  add     rsi, 4
0x18000c143  add     r13, 4
0x18000c147  cmp     dword ptr [rdi+18h], 0
0x18000c14b  jz      short loc_18000C17D
0x18000c14d  mov     ecx, [r12]
0x18000c151  mov     r9, r13
0x18000c154  mov     rax, [r15]
0x18000c157  mov     r8, rsi
0x18000c15a  mov     [rsp+88h+var_58], ecx
0x18000c15e  mov     rdx, rbp
0x18000c161  mov     ecx, [rbx+154h]
0x18000c167  mov     [rsp+88h+var_60], ecx
0x18000c16b  mov     ecx, [rbx+150h]
0x18000c171  mov     [rsp+88h+var_68], ecx
0x18000c175  mov     rcx, r14
0x18000c178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c17d  movsxd  rax, dword ptr [rbx+570h]
0x18000c184  add     r14, rax
0x18000c187  movsxd  rax, dword ptr [rbx+0EB0h]
0x18000c18e  add     rbp, rax
0x18000c191  movsxd  rax, dword ptr [rbx+0EB4h]
0x18000c198  add     rsi, rax
0x18000c19b  add     r13, rax
0x18000c19e  cmp     dword ptr [rdi+1Ch], 0
0x18000c1a2  jz      short loc_18000C1D4
0x18000c1a4  mov     ecx, [r12]
0x18000c1a8  mov     r9, r13
0x18000c1ab  mov     rax, [r15]
0x18000c1ae  mov     r8, rsi
0x18000c1b1  mov     [rsp+88h+var_58], ecx
0x18000c1b5  mov     rdx, rbp
0x18000c1b8  mov     ecx, [rbx+154h]
0x18000c1be  mov     [rsp+88h+var_60], ecx
0x18000c1c2  mov     ecx, [rbx+150h]
0x18000c1c8  mov     [rsp+88h+var_68], ecx
0x18000c1cc  mov     rcx, r14
0x18000c1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1d4  cmp     dword ptr [rdi+20h], 0
0x18000c1d8  jz      short loc_18000C251
0x18000c1da  mov     r10d, [r12]
0x18000c1de  lea     r9, [r13+4]
0x18000c1e2  movsxd  rcx, dword ptr [rbx+568h]
0x18000c1e9  lea     r8, [rsi+4]
0x18000c1ed  mov     rax, [r15]
0x18000c1f0  lea     rdx, [rbp+8]
0x18000c1f4  mov     [rsp+88h+var_58], r10d
0x18000c1f9  add     rcx, r14
0x18000c1fc  mov     r10d, [rbx+154h]
0x18000c203  mov     [rsp+88h+var_60], r10d
0x18000c208  mov     r10d, [rbx+150h]
0x18000c20f  mov     [rsp+88h+var_68], r10d
0x18000c214  jmp     short loc_18000C24C
0x18000c216  mov     ecx, [rcx+558h]
0x18000c21c  mov     r8, rsi
0x18000c21f  mov     r9, [rsp+88h+arg_20]
0x18000c227  mov     rdx, rbp
0x18000c22a  mov     rax, [rbx+5E0h]
0x18000c231  mov     [rsp+88h+var_58], ecx
0x18000c235  mov     ecx, [rbx+154h]
0x18000c23b  mov     [rsp+88h+var_60], ecx
0x18000c23f  mov     ecx, [rbx+150h]
0x18000c245  mov     [rsp+88h+var_68], ecx
0x18000c249  mov     rcx, r14
0x18000c24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c251  add     rsp, 48h
0x18000c255  pop     r15
0x18000c257  pop     r14
0x18000c259  pop     r13
0x18000c25b  pop     r12
0x18000c25d  pop     rdi
0x18000c25e  pop     rsi
0x18000c25f  pop     rbp
0x18000c260  pop     rbx
0x18000c261  retn
```
