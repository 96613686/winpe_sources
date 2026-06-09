# CVideoObjectDecoder::DecodePMB(long const *,uchar *,uchar *,uchar *,long,long,long,long)

- ea: `0x18000ef6c`
- end: `0x18000f42f`
- name: `?DecodePMB@CVideoObjectDecoder@@AEAAJPEBJPEAE11JJJJ@Z`
- size: `1219`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this, const int *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int, int, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180010600`
- `0x180010f80`
- `0x1800119e8`

## callees

- `0x18000ef6c`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::DecodePMB(
        CVideoObjectDecoder *this,
        const int *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  char *v9; // r14
  __int64 v10; // r13
  int v12; // ecx
  __int64 v14; // r12
  BOOL v15; // ebp
  BOOL v16; // esi
  __int64 result; // rax
  unsigned __int8 *v18; // r15
  __int64 v19; // r12
  __int64 v20; // rax
  unsigned __int8 *v21; // r15
  __int64 v22; // r13
  __int64 v23; // r12
  __int64 v24; // rax
  const int *v25; // r13
  int v26; // edx
  BOOL v27; // esi
  BOOL v28; // ebp
  __int64 v29; // r15
  __int64 v30; // r15
  __int64 v31; // [rsp+90h] [rbp+8h]
  __int64 v32; // [rsp+90h] [rbp+8h]
  __int64 v33; // [rsp+90h] [rbp+8h]
  __int64 v35; // [rsp+98h] [rbp+10h]

  v9 = (char *)this + 1616;
  v10 = *((_QWORD *)this + 439);
  v12 = *((_DWORD *)this + 84);
  v31 = v10;
  v14 = *((_QWORD *)this + 29) + ((__int64)a6 >> 1) + v12 * ((a7 >> 1) + 32);
  v15 = (a6 & 1) == 0;
  v16 = (a7 & 1) == 0;
  if ( *a2 )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v10);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      a3,
      v9,
      v14 + 32,
      *((unsigned int *)this + 84),
      v15,
      v16);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, int, int, bool, bool, int))this + 456))(
      1,
      1,
      a3,
      v14 + 32,
      v12,
      v12,
      (a6 & 1) == 0,
      (a7 & 1) == 0,
      8);
  }
  v18 = a3 + 8;
  v19 = v14 + 40;
  if ( a2[1] )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v10);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      v18,
      v9,
      v19,
      *((unsigned int *)this + 84),
      v15,
      v16);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, _DWORD, _DWORD, BOOL, BOOL, int))this + 456))(
      1,
      1,
      v18,
      v19,
      *((_DWORD *)this + 84),
      *((_DWORD *)this + 84),
      v15,
      v16,
      8);
  }
  v20 = *((int *)this + 924);
  v21 = &v18[v20];
  v22 = v20 + v19;
  if ( a2[2] )
  {
    v23 = v31;
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v31);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      v21,
      v9,
      v22,
      *((unsigned int *)this + 84),
      v15,
      v16);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, _DWORD, _DWORD, BOOL, BOOL, int))this + 456))(
      1,
      1,
      v21,
      v22,
      *((_DWORD *)this + 84),
      *((_DWORD *)this + 84),
      v15,
      v16,
      8);
    v23 = v31;
  }
  v24 = v22 + 8;
  v25 = a2;
  v32 = v24;
  if ( a2[3] )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v23);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      v21 + 8,
      v9,
      v32,
      *((unsigned int *)this + 84),
      v15,
      v16);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, _DWORD, _DWORD, BOOL, BOOL, int))this + 456))(
      1,
      1,
      v21 + 8,
      v24,
      *((_DWORD *)this + 84),
      *((_DWORD *)this + 84),
      v15,
      v16,
      8);
  }
  v26 = *((_DWORD *)this + 85);
  v27 = (a8 & 1) == 0;
  v28 = (a9 & 1) == 0;
  v29 = (a8 >> 1) + 16 + v26 * ((a9 >> 1) + 16);
  v33 = *((_QWORD *)this + 31);
  v35 = v29 + *((_QWORD *)this + 30);
  if ( v25[4] )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v23);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      a4,
      v9,
      v35,
      *((unsigned int *)this + 85),
      v27,
      v28);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, int, int, bool, bool, int))this + 456))(
      1,
      1,
      a4,
      v29 + *((_QWORD *)this + 30),
      v26,
      v26,
      (a8 & 1) == 0,
      (a9 & 1) == 0,
      8);
  }
  v30 = v33 + v29;
  if ( v25[5] )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v23);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      a5,
      v9,
      v30,
      *((unsigned int *)this + 85),
      v27,
      v28);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, _DWORD, _DWORD, BOOL, BOOL, int))this + 456))(
      1,
      1,
      a5,
      v30,
      *((_DWORD *)this + 85),
      *((_DWORD *)this + 85),
      v27,
      v28,
      8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ef6c  mov     [rsp+arg_10], rbx
0x18000ef71  mov     [rsp+arg_18], r9
0x18000ef76  mov     [rsp+arg_8], rdx
0x18000ef7b  push    rbp
0x18000ef7c  push    rsi
0x18000ef7d  push    rdi
0x18000ef7e  push    r12
0x18000ef80  push    r13
0x18000ef82  push    r14
0x18000ef84  push    r15
0x18000ef86  sub     rsp, 50h
0x18000ef8a  mov     esi, [rsp+88h+arg_30]
0x18000ef91  lea     r14, [rcx+650h]
0x18000ef98  mov     r13, [rcx+0DB8h]
0x18000ef9f  mov     eax, esi
0x18000efa1  movsxd  rbp, [rsp+88h+arg_28]
0x18000efa9  mov     rbx, rcx
0x18000efac  mov     ecx, [rcx+150h]
0x18000efb2  not     esi
0x18000efb4  sar     eax, 1
0x18000efb6  mov     r15, r8
0x18000efb9  add     eax, 20h ; ' '
0x18000efbc  mov     [rsp+88h+arg_0], r13
0x18000efc4  imul    eax, ecx
0x18000efc7  movsxd  r12, eax
0x18000efca  mov     rax, rbp
0x18000efcd  sar     rax, 1
0x18000efd0  not     ebp
0x18000efd2  add     r12, rax
0x18000efd5  mov     eax, 1
0x18000efda  add     r12, [rbx+0E8h]
0x18000efe1  and     ebp, eax
0x18000efe3  and     esi, eax
0x18000efe5  cmp     dword ptr [rdx], 0
0x18000efe8  jz      short loc_18000F047
0x18000efea  mov     rax, [rbx+0E48h]
0x18000eff1  mov     rdx, r13
0x18000eff4  mov     rcx, rbx
0x18000eff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000effc  test    eax, eax
0x18000effe  jnz     loc_18000F417
0x18000f004  mov     r8d, [rbx+0E50h]
0x18000f00b  lea     edi, [rax+8]
0x18000f00e  mov     rax, [rbx+0E10h]
0x18000f015  mov     edx, edi
0x18000f017  mov     rcx, r14
0x18000f01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f01f  mov     r9d, [rbx+150h]
0x18000f026  lea     r8, [r12+20h]
0x18000f02b  mov     rax, [rbx+0E38h]
0x18000f032  mov     rdx, r14
0x18000f035  mov     rcx, r15
0x18000f038  mov     [rsp+88h+var_60], esi
0x18000f03c  mov     [rsp+88h+var_68], ebp
0x18000f040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f045  jmp     short loc_18000F075
0x18000f047  mov     edx, eax
0x18000f049  lea     r9, [r12+20h]
0x18000f04e  mov     edi, 8
0x18000f053  mov     [rsp+88h+var_48], edi
0x18000f057  mov     [rsp+88h+var_50], esi
0x18000f05b  mov     [rsp+88h+var_58], ebp
0x18000f05f  mov     [rsp+88h+var_60], ecx
0x18000f063  mov     [rsp+88h+var_68], ecx
0x18000f067  mov     ecx, eax
0x18000f069  mov     rax, [rbx+0E40h]
0x18000f070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f075  mov     rax, [rsp+88h+arg_8]
0x18000f07d  add     r15, 8
0x18000f081  add     r12, 28h ; '('
0x18000f085  cmp     dword ptr [rax+4], 0
0x18000f089  jz      short loc_18000F0E3
0x18000f08b  mov     rax, [rbx+0E48h]
0x18000f092  mov     rdx, r13
0x18000f095  mov     rcx, rbx
0x18000f098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f09d  test    eax, eax
0x18000f09f  jnz     loc_18000F417
0x18000f0a5  mov     r8d, [rbx+0E50h]
0x18000f0ac  mov     edx, edi
0x18000f0ae  mov     rax, [rbx+0E10h]
0x18000f0b5  mov     rcx, r14
0x18000f0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0bd  mov     r9d, [rbx+150h]
0x18000f0c4  mov     r8, r12
0x18000f0c7  mov     rax, [rbx+0E38h]
0x18000f0ce  mov     rdx, r14
0x18000f0d1  mov     rcx, r15
0x18000f0d4  mov     [rsp+88h+var_60], esi
0x18000f0d8  mov     [rsp+88h+var_68], ebp
0x18000f0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e1  jmp     short loc_18000F116
0x18000f0e3  mov     ecx, [rbx+150h]
0x18000f0e9  mov     r9, r12
0x18000f0ec  mov     rax, [rbx+0E40h]
0x18000f0f3  mov     r8, r15
0x18000f0f6  mov     [rsp+88h+var_48], edi
0x18000f0fa  mov     [rsp+88h+var_50], esi
0x18000f0fe  mov     [rsp+88h+var_58], ebp
0x18000f102  mov     [rsp+88h+var_60], ecx
0x18000f106  mov     [rsp+88h+var_68], ecx
0x18000f10a  mov     ecx, 1
0x18000f10f  mov     edx, ecx
0x18000f111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f116  movsxd  rax, dword ptr [rbx+0E70h]
0x18000f11d  add     r15, rax
0x18000f120  lea     r13, [rax+r12]
0x18000f124  mov     rax, [rsp+88h+arg_8]
0x18000f12c  cmp     dword ptr [rax+8], 0
0x18000f130  jz      short loc_18000F192
0x18000f132  mov     r12, [rsp+88h+arg_0]
0x18000f13a  mov     rcx, rbx
0x18000f13d  mov     rax, [rbx+0E48h]
0x18000f144  mov     rdx, r12
0x18000f147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f14c  test    eax, eax
0x18000f14e  jnz     loc_18000F417
0x18000f154  mov     r8d, [rbx+0E50h]
0x18000f15b  mov     edx, edi
0x18000f15d  mov     rax, [rbx+0E10h]
0x18000f164  mov     rcx, r14
0x18000f167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f16c  mov     r9d, [rbx+150h]
0x18000f173  mov     r8, r13
0x18000f176  mov     rax, [rbx+0E38h]
0x18000f17d  mov     rdx, r14
0x18000f180  mov     rcx, r15
0x18000f183  mov     [rsp+88h+var_60], esi
0x18000f187  mov     [rsp+88h+var_68], ebp
0x18000f18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f190  jmp     short loc_18000F1CF
0x18000f192  mov     ecx, [rbx+150h]
0x18000f198  mov     eax, 1
0x18000f19d  mov     [rsp+88h+var_48], edi
0x18000f1a1  mov     edx, eax
0x18000f1a3  mov     [rsp+88h+var_50], esi
0x18000f1a7  mov     r9, r13
0x18000f1aa  mov     [rsp+88h+var_58], ebp
0x18000f1ae  mov     r8, r15
0x18000f1b1  mov     [rsp+88h+var_60], ecx
0x18000f1b5  mov     [rsp+88h+var_68], ecx
0x18000f1b9  mov     ecx, eax
0x18000f1bb  mov     rax, [rbx+0E40h]
0x18000f1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1c7  mov     r12, [rsp+88h+arg_0]
0x18000f1cf  lea     rax, [r13+8]
0x18000f1d3  mov     r13, [rsp+88h+arg_8]
0x18000f1db  mov     [rsp+88h+arg_0], rax
0x18000f1e3  cmp     dword ptr [r13+0Ch], 0
0x18000f1e8  jz      short loc_18000F248
0x18000f1ea  mov     rax, [rbx+0E48h]
0x18000f1f1  mov     rdx, r12
0x18000f1f4  mov     rcx, rbx
0x18000f1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1fc  test    eax, eax
0x18000f1fe  jnz     loc_18000F417
0x18000f204  mov     r8d, [rbx+0E50h]
0x18000f20b  mov     edx, edi
0x18000f20d  mov     rax, [rbx+0E10h]
0x18000f214  mov     rcx, r14
0x18000f217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f21c  mov     r9d, [rbx+150h]
0x18000f223  lea     rcx, [r15+8]
0x18000f227  mov     r8, [rsp+88h+arg_0]
0x18000f22f  mov     rdx, r14
0x18000f232  mov     rax, [rbx+0E38h]
0x18000f239  mov     [rsp+88h+var_60], esi
0x18000f23d  mov     [rsp+88h+var_68], ebp
0x18000f241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f246  jmp     short loc_18000F27E
0x18000f248  mov     ecx, [rbx+150h]
0x18000f24e  lea     r8, [r15+8]
0x18000f252  mov     [rsp+88h+var_48], edi
0x18000f256  mov     r9, rax
0x18000f259  mov     [rsp+88h+var_50], esi
0x18000f25d  mov     eax, 1
0x18000f262  mov     [rsp+88h+var_58], ebp
0x18000f266  mov     edx, eax
0x18000f268  mov     [rsp+88h+var_60], ecx
0x18000f26c  mov     [rsp+88h+var_68], ecx
0x18000f270  mov     ecx, eax
0x18000f272  mov     rax, [rbx+0E40h]
0x18000f279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f27e  mov     eax, [rsp+88h+arg_40]
0x18000f285  mov     r10d, 1
0x18000f28b  mov     ecx, [rsp+88h+arg_38]
0x18000f292  mov     ebp, eax
0x18000f294  mov     edx, [rbx+154h]
0x18000f29a  mov     esi, ecx
0x18000f29c  sar     eax, 1
0x18000f29e  not     esi
0x18000f2a0  add     eax, 10h
0x18000f2a3  sar     ecx, 1
0x18000f2a5  imul    eax, edx
0x18000f2a8  add     ecx, 10h
0x18000f2ab  not     ebp
0x18000f2ad  and     esi, r10d
0x18000f2b0  and     ebp, r10d
0x18000f2b3  add     eax, ecx
0x18000f2b5  mov     rcx, [rbx+0F8h]
0x18000f2bc  movsxd  r15, eax
0x18000f2bf  mov     rax, [rbx+0F0h]
0x18000f2c6  add     rax, r15
0x18000f2c9  mov     [rsp+88h+arg_0], rcx
0x18000f2d1  cmp     dword ptr [r13+10h], 0
0x18000f2d6  mov     [rsp+88h+arg_8], rax
0x18000f2de  jz      short loc_18000F342
0x18000f2e0  mov     rax, [rbx+0E48h]
0x18000f2e7  mov     rdx, r12
0x18000f2ea  mov     rcx, rbx
0x18000f2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2f2  test    eax, eax
0x18000f2f4  jnz     loc_18000F417
0x18000f2fa  mov     r8d, [rbx+0E50h]
0x18000f301  mov     edx, edi
0x18000f303  mov     rax, [rbx+0E10h]
0x18000f30a  mov     rcx, r14
0x18000f30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f312  mov     r9d, [rbx+154h]
0x18000f319  mov     rdx, r14
0x18000f31c  mov     r8, [rsp+88h+arg_8]
0x18000f324  mov     rcx, [rsp+88h+arg_18]
0x18000f32c  mov     rax, [rbx+0E38h]
0x18000f333  mov     [rsp+88h+var_60], ebp
0x18000f337  mov     [rsp+88h+var_68], esi
0x18000f33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f340  jmp     short loc_18000F373
0x18000f342  mov     r8, [rsp+88h+arg_18]
0x18000f34a  mov     r9, rax
0x18000f34d  mov     rax, [rbx+0E40h]
0x18000f354  mov     ecx, r10d
0x18000f357  mov     [rsp+88h+var_48], edi
0x18000f35b  mov     [rsp+88h+var_50], ebp
0x18000f35f  mov     [rsp+88h+var_58], esi
0x18000f363  mov     [rsp+88h+var_60], edx
0x18000f367  mov     [rsp+88h+var_68], edx
0x18000f36b  mov     edx, r10d
0x18000f36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f373  add     r15, [rsp+88h+arg_0]
0x18000f37b  cmp     dword ptr [r13+14h], 0
0x18000f380  jz      short loc_18000F3DB
0x18000f382  mov     rax, [rbx+0E48h]
0x18000f389  mov     rdx, r12
0x18000f38c  mov     rcx, rbx
0x18000f38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f394  test    eax, eax
0x18000f396  jnz     short loc_18000F417
0x18000f398  mov     r8d, [rbx+0E50h]
0x18000f39f  mov     edx, edi
0x18000f3a1  mov     rax, [rbx+0E10h]
0x18000f3a8  mov     rcx, r14
0x18000f3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b0  mov     r9d, [rbx+154h]
0x18000f3b7  mov     r8, r15
0x18000f3ba  mov     rcx, [rsp+88h+arg_20]
0x18000f3c2  mov     rdx, r14
0x18000f3c5  mov     rax, [rbx+0E38h]
0x18000f3cc  mov     [rsp+88h+var_60], ebp
0x18000f3d0  mov     [rsp+88h+var_68], esi
0x18000f3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3d9  jmp     short loc_18000F415
0x18000f3db  mov     edx, [rbx+154h]
0x18000f3e1  mov     eax, 1
0x18000f3e6  mov     r8, [rsp+88h+arg_20]
0x18000f3ee  mov     ecx, eax
0x18000f3f0  mov     [rsp+88h+var_48], edi
0x18000f3f4  mov     r9, r15
0x18000f3f7  mov     [rsp+88h+var_50], ebp
0x18000f3fb  mov     [rsp+88h+var_58], esi
0x18000f3ff  mov     [rsp+88h+var_60], edx
0x18000f403  mov     [rsp+88h+var_68], edx
0x18000f407  mov     edx, eax
0x18000f409  mov     rax, [rbx+0E40h]
0x18000f410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f415  xor     eax, eax
0x18000f417  mov     rbx, [rsp+88h+arg_10]
0x18000f41f  add     rsp, 50h
0x18000f423  pop     r15
0x18000f425  pop     r14
0x18000f427  pop     r13
0x18000f429  pop     r12
0x18000f42b  pop     rdi
0x18000f42c  pop     rsi
0x18000f42d  pop     rbp
0x18000f42e  retn
```
