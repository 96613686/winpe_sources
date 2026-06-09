# CVideoObjectDecoder::UpdateMBPacked_PerBlk(uchar *,uchar const *,uchar const *,uchar const *,CMBMode const *)

- ea: `0x18003274c`
- end: `0x180032940`
- name: `?UpdateMBPacked_PerBlk@CVideoObjectDecoder@@AEAAXPEAEPEBE11PEBVCMBMode@@@Z`
- size: `500`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const struct CMBMode *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800320a0`
- `0x180032240`

## callees

- `0x18003274c`
- `0x180046010`

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
  char *v11; // rsi
  void (__fastcall **v12)(char *); // r12
  const unsigned __int8 *v13; // rbp
  unsigned __int8 *v14; // r15
  const unsigned __int8 *v15; // r13
  const unsigned __int8 *v16; // rax
  _DWORD *v17; // r14
  unsigned __int8 *v18; // r15
  __int64 v19; // rax
  const struct CMBMode *v20; // rdx
  const unsigned __int8 *v21; // rbp
  const unsigned __int8 *v22; // r13
  const struct CMBMode *v23; // [rsp+C8h] [rbp+30h]
  const struct CMBMode *v24; // [rsp+C8h] [rbp+30h]

  if ( !*((_DWORD *)a6 + 6) || *((_DWORD *)a6 + 11) || *((_DWORD *)a6 + 12) )
  {
    (*((void (__fastcall **)(char *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))this
     + 320))(
      (char *)this + 2336,
      a2,
      a3,
      a4,
      a5,
      *((_DWORD *)this + 333),
      *((_DWORD *)this + 334),
      *((_DWORD *)this + 603));
  }
  else
  {
    v11 = (char *)this + 2336;
    v12 = (void (__fastcall **)(char *))((char *)this + 2576);
    if ( *((_DWORD *)a6 + 7) )
      (*v12)((char *)this + 2336);
    v13 = a4 + 4;
    v14 = &a2[*((int *)v11 + 23)];
    v15 = a5 + 4;
    v16 = a3 + 8;
    v23 = (const struct CMBMode *)(a3 + 8);
    v17 = (_DWORD *)((char *)this + 2412);
    if ( *((_DWORD *)a6 + 8) )
      ((void (__fastcall *)(char *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))*v12)(
        v11,
        v14,
        v16,
        v13,
        v15,
        *((_DWORD *)this + 333),
        *((_DWORD *)this + 334),
        *v17);
    v18 = &v14[*((int *)this + 609)];
    v19 = *((int *)this + 1907);
    v20 = (const struct CMBMode *)((char *)v23 + *((int *)this + 1906));
    v21 = &v13[v19];
    v22 = &v15[v19];
    v24 = v20;
    if ( *((_DWORD *)a6 + 9) )
    {
      ((void (__fastcall *)(char *, unsigned __int8 *, const struct CMBMode *, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))*v12)(
        v11,
        v18,
        v20,
        v21,
        v22,
        *((_DWORD *)this + 333),
        *((_DWORD *)this + 334),
        *v17);
      v20 = v24;
    }
    if ( *((_DWORD *)a6 + 10) )
      ((void (__fastcall *)(char *, unsigned __int8 *, __int64, const unsigned __int8 *, const unsigned __int8 *, _DWORD, _DWORD, _DWORD))*v12)(
        v11,
        &v18[*((int *)this + 607)],
        (__int64)v20 + 8,
        v21 + 4,
        v22 + 4,
        *((_DWORD *)this + 333),
        *((_DWORD *)this + 334),
        *v17);
  }
}

```

## disassembly

```asm
0x18003274c  push    rbx
0x18003274e  push    rbp
0x18003274f  push    rsi
0x180032750  push    rdi
0x180032751  push    r12
0x180032753  push    r13
0x180032755  push    r14
0x180032757  push    r15
0x180032759  sub     rsp, 58h
0x18003275d  mov     rdi, [rsp+98h+arg_28]
0x180032765  xor     eax, eax
0x180032767  mov     rbp, r9
0x18003276a  mov     r14, r8
0x18003276d  mov     r15, rdx
0x180032770  mov     rbx, rcx
0x180032773  cmp     [rdi+18h], eax
0x180032776  jz      loc_1800328F1
0x18003277c  cmp     [rdi+2Ch], eax
0x18003277f  jnz     loc_1800328F1
0x180032785  cmp     [rdi+30h], eax
0x180032788  jnz     loc_1800328F1
0x18003278e  lea     rsi, [rcx+920h]
0x180032795  mov     r13, [rsp+98h+arg_20]
0x18003279d  lea     r12, [rcx+0A10h]
0x1800327a4  cmp     [rdi+1Ch], eax
0x1800327a7  jz      short loc_1800327D5
0x1800327a9  mov     ecx, [rsi+4Ch]
0x1800327ac  mov     rax, [r12]
0x1800327b0  mov     [rsp+98h+var_60], ecx
0x1800327b4  mov     ecx, [rbx+538h]
0x1800327ba  mov     [rsp+98h+var_68], ecx
0x1800327be  mov     ecx, [rbx+534h]
0x1800327c4  mov     [rsp+98h+var_70], ecx
0x1800327c8  mov     rcx, rsi
0x1800327cb  mov     [rsp+98h+var_78], r13
0x1800327d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327d5  movsxd  rax, dword ptr [rsi+5Ch]
0x1800327d9  add     rbp, 4
0x1800327dd  add     r15, rax
0x1800327e0  add     r13, 4
0x1800327e4  cmp     dword ptr [rdi+20h], 0
0x1800327e8  lea     rax, [r14+8]
0x1800327ec  mov     [rsp+98h+arg_28], rax
0x1800327f4  lea     r14, [rbx+96Ch]
0x1800327fb  jz      short loc_180032832
0x1800327fd  mov     ecx, [r14]
0x180032800  mov     r8, rax
0x180032803  mov     rax, [r12]
0x180032807  mov     r9, rbp
0x18003280a  mov     [rsp+98h+var_60], ecx
0x18003280e  mov     rdx, r15
0x180032811  mov     ecx, [rbx+538h]
0x180032817  mov     [rsp+98h+var_68], ecx
0x18003281b  mov     ecx, [rbx+534h]
0x180032821  mov     [rsp+98h+var_70], ecx
0x180032825  mov     rcx, rsi
0x180032828  mov     [rsp+98h+var_78], r13
0x18003282d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032832  movsxd  rax, dword ptr [rbx+984h]
0x180032839  movsxd  rdx, dword ptr [rbx+1DC8h]
0x180032840  add     r15, rax
0x180032843  movsxd  rax, dword ptr [rbx+1DCCh]
0x18003284a  add     rdx, [rsp+98h+arg_28]
0x180032852  add     rbp, rax
0x180032855  add     r13, rax
0x180032858  mov     [rsp+98h+arg_28], rdx
0x180032860  cmp     dword ptr [rdi+24h], 0
0x180032864  jz      short loc_1800328A3
0x180032866  mov     ecx, [r14]
0x180032869  mov     r8, rdx
0x18003286c  mov     rax, [r12]
0x180032870  mov     r9, rbp
0x180032873  mov     [rsp+98h+var_60], ecx
0x180032877  mov     rdx, r15
0x18003287a  mov     ecx, [rbx+538h]
0x180032880  mov     [rsp+98h+var_68], ecx
0x180032884  mov     ecx, [rbx+534h]
0x18003288a  mov     [rsp+98h+var_70], ecx
0x18003288e  mov     rcx, rsi
0x180032891  mov     [rsp+98h+var_78], r13
0x180032896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003289b  mov     rdx, [rsp+98h+arg_28]
0x1800328a3  cmp     dword ptr [rdi+28h], 0
0x1800328a7  jz      loc_18003292F
0x1800328ad  mov     r10d, [r14]
0x1800328b0  lea     rax, [r13+4]
0x1800328b4  mov     [rsp+98h+var_60], r10d
0x1800328b9  lea     r8, [rdx+8]
0x1800328bd  mov     r10d, [rbx+538h]
0x1800328c4  lea     r9, [rbp+4]
0x1800328c8  movsxd  rdx, dword ptr [rbx+97Ch]
0x1800328cf  mov     rcx, rsi
0x1800328d2  mov     [rsp+98h+var_68], r10d
0x1800328d7  add     rdx, r15
0x1800328da  mov     r10d, [rbx+534h]
0x1800328e1  mov     [rsp+98h+var_70], r10d
0x1800328e6  mov     [rsp+98h+var_78], rax
0x1800328eb  mov     rax, [r12]
0x1800328ef  jmp     short loc_18003292A
0x1800328f1  mov     rax, [rbx+0A00h]
0x1800328f8  add     rcx, 920h
0x1800328ff  mov     edx, [rcx+4Ch]
0x180032902  mov     [rsp+98h+var_60], edx
0x180032906  mov     edx, [rbx+538h]
0x18003290c  mov     [rsp+98h+var_68], edx
0x180032910  mov     edx, [rbx+534h]
0x180032916  mov     [rsp+98h+var_70], edx
0x18003291a  mov     rdx, [rsp+98h+arg_20]
0x180032922  mov     [rsp+98h+var_78], rdx
0x180032927  mov     rdx, r15
0x18003292a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003292f  add     rsp, 58h
0x180032933  pop     r15
0x180032935  pop     r14
0x180032937  pop     r13
0x180032939  pop     r12
0x18003293b  pop     rdi
0x18003293c  pop     rsi
0x18003293d  pop     rbp
0x18003293e  pop     rbx
0x18003293f  retn
```
