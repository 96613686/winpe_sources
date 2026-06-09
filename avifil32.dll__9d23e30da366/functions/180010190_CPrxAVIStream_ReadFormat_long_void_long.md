# CPrxAVIStream::ReadFormat(long,void *,long *)

- ea: `0x180010190`
- end: `0x1800102b1`
- name: `?ReadFormat@CPrxAVIStream@@UEAAJJPEAXPEAJ@Z`
- size: `289`
- prototype: `int(CPrxAVIStream *__hidden this, int, void *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180010190`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CPrxAVIStream::ReadFormat(CPrxAVIStream *this, int a2, void *a3, int *a4)
{
  __int64 v4; // r14
  int v9; // ecx
  _DWORD *v10; // rbx
  int v11; // eax
  int v12; // eax
  _BYTE v13[16]; // [rsp+20h] [rbp-60h] BYREF
  _DWORD *v14; // [rsp+30h] [rbp-50h]
  int v15; // [rsp+38h] [rbp-48h]
  int v16; // [rsp+3Ch] [rbp-44h]
  unsigned int v17; // [rsp+70h] [rbp-10h] BYREF

  v4 = *((_QWORD *)this + 5);
  v17 = 0;
  if ( !v4 )
    return 2147549190LL;
  if ( !a3 )
    *a4 = 0;
  memset_0(v13, 0, 0x50u);
  v15 = 8;
  v16 = 3;
  if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *, GUID *))(*(_QWORD *)v4 + 24LL))(v4, v13, &IID_IAVIStream) )
    return 2147549195LL;
  *v14 = a2;
  v9 = a3 ? *a4 : 0;
  v14[1] = v9;
  if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *, unsigned int *))(*(_QWORD *)v4 + 32LL))(v4, v13, &v17) )
    return 2147549195LL;
  v10 = v14;
  v11 = *v14;
  v17 = *v14;
  if ( a3 && *a4 && !v11 )
  {
    v12 = v14[1];
    if ( *a4 < v12 )
      v12 = *a4;
    memmove_0(a3, v14 + 2, v12);
  }
  *a4 = v10[1];
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v4 + 40LL))(v4, v13);
  return v17;
}

```

## disassembly

```asm
0x180010190  push    rbp
0x180010192  push    rbx
0x180010193  push    rsi
0x180010194  push    rdi
0x180010195  push    r14
0x180010197  mov     rbp, rsp
0x18001019a  sub     rsp, 80h
0x1800101a1  mov     rax, cs:__security_cookie
0x1800101a8  xor     rax, rsp
0x1800101ab  mov     [rbp+var_8], rax
0x1800101af  mov     r14, [rcx+28h]
0x1800101b3  mov     rdi, r9
0x1800101b6  mov     [rbp+var_10], 0
0x1800101bd  mov     rsi, r8
0x1800101c0  mov     ebx, edx
0x1800101c2  test    r14, r14
0x1800101c5  jnz     short loc_1800101D1
0x1800101c7  mov     eax, 80010006h
0x1800101cc  jmp     loc_180010297
0x1800101d1  test    rsi, rsi
0x1800101d4  jnz     short loc_1800101D9
0x1800101d6  mov     [r9], esi
0x1800101d9  xor     edx, edx; Val
0x1800101db  lea     rcx, [rbp+var_60]; void *
0x1800101df  lea     r8d, [rdx+50h]; Size
0x1800101e3  call    memset_0
0x1800101e8  mov     [rbp+var_48], 8
0x1800101ef  lea     r8, IID_IAVIStream
0x1800101f6  mov     [rbp+var_44], 3
0x1800101fd  lea     rdx, [rbp+var_60]
0x180010201  mov     rax, [r14]
0x180010204  mov     rcx, r14
0x180010207  mov     rax, [rax+18h]
0x18001020b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010210  test    eax, eax
0x180010212  jnz     short loc_180010292
0x180010214  mov     rax, [rbp+var_50]
0x180010218  mov     [rax], ebx
0x18001021a  test    rsi, rsi
0x18001021d  jz      short loc_180010223
0x18001021f  mov     ecx, [rdi]
0x180010221  jmp     short loc_180010225
0x180010223  xor     ecx, ecx
0x180010225  mov     rax, [rbp+var_50]
0x180010229  lea     r8, [rbp+var_10]
0x18001022d  lea     rdx, [rbp+var_60]
0x180010231  mov     [rax+4], ecx
0x180010234  mov     rcx, r14
0x180010237  mov     rax, [r14]
0x18001023a  mov     rax, [rax+20h]
0x18001023e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010243  test    eax, eax
0x180010245  jnz     short loc_180010292
0x180010247  mov     rbx, [rbp+var_50]
0x18001024b  mov     eax, [rbx]
0x18001024d  mov     [rbp+var_10], eax
0x180010250  test    rsi, rsi
0x180010253  jz      short loc_180010275
0x180010255  cmp     dword ptr [rdi], 0
0x180010258  jz      short loc_180010275
0x18001025a  test    eax, eax
0x18001025c  jnz     short loc_180010275
0x18001025e  mov     eax, [rbx+4]
0x180010261  lea     rdx, [rbx+8]; Src
0x180010265  cmp     [rdi], eax
0x180010267  mov     rcx, rsi; void *
0x18001026a  cmovl   eax, [rdi]
0x18001026d  movsxd  r8, eax; Size
0x180010270  call    memmove_0
0x180010275  mov     eax, [rbx+4]
0x180010278  lea     rdx, [rbp+var_60]
0x18001027c  mov     [rdi], eax
0x18001027e  mov     rcx, r14
0x180010281  mov     rax, [r14]
0x180010284  mov     rax, [rax+28h]
0x180010288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001028d  mov     eax, [rbp+var_10]
0x180010290  jmp     short loc_180010297
0x180010292  mov     eax, 8001000Bh
0x180010297  mov     rcx, [rbp+var_8]
0x18001029b  xor     rcx, rsp; StackCookie
0x18001029e  call    __security_check_cookie
0x1800102a3  add     rsp, 80h
0x1800102aa  pop     r14
0x1800102ac  pop     rdi
0x1800102ad  pop     rsi
0x1800102ae  pop     rbx
0x1800102af  pop     rbp
0x1800102b0  retn
```
