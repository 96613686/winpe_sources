# AreVideoStreamsCompatible(IAVIStream *,IAVIStream *)

- ea: `0x180011190`
- end: `0x1800112f7`
- name: `?AreVideoStreamsCompatible@@YAHPEAUIAVIStream@@0@Z`
- size: `359`
- prototype: `__int64 __fastcall(PAVISTREAM pavi, PAVISTREAM)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012224`

## callees

- `0x180001460`
- `0x1800086a0`
- `0x180011190`
- `0x180018010`

## pseudocode

```c
_BOOL8 __fastcall AreVideoStreamsCompatible(PAVISTREAM pavi, PAVISTREAM a2)
{
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  _BOOL8 result; // rax
  int v9; // [rsp+30h] [rbp-9h] BYREF
  int v10; // [rsp+34h] [rbp-5h] BYREF
  __int128 v11; // [rsp+38h] [rbp-1h] BYREF
  __int128 v12; // [rsp+48h] [rbp+Fh]
  __int64 v13; // [rsp+58h] [rbp+1Fh]
  __int128 v14; // [rsp+60h] [rbp+27h] BYREF
  __int128 v15; // [rsp+70h] [rbp+37h]
  __int64 v16; // [rsp+80h] [rbp+47h]

  v9 = 0;
  v10 = 0;
  v16 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v11 = 0;
  v12 = 0;
  v4 = AVIStreamStart(pavi);
  result = 0;
  if ( ((int (__fastcall *)(PAVISTREAM, _QWORD, _QWORD, int *))pavi->lpVtbl->ReadFormat)(pavi, v4, 0, &v9) >= 0 )
  {
    v5 = AVIStreamStart(a2);
    if ( ((int (__fastcall *)(PAVISTREAM, _QWORD, _QWORD, int *))a2->lpVtbl->ReadFormat)(a2, v5, 0, &v10) >= 0
      && v9 == v10 )
    {
      v9 = 40;
      v10 = 40;
      v6 = AVIStreamStart(pavi);
      if ( ((int (__fastcall *)(PAVISTREAM, _QWORD, __int128 *, int *))pavi->lpVtbl->ReadFormat)(pavi, v6, &v14, &v9) >= 0 )
      {
        v7 = AVIStreamStart(a2);
        if ( ((int (__fastcall *)(PAVISTREAM, _QWORD, __int128 *, int *))a2->lpVtbl->ReadFormat)(a2, v7, &v11, &v10) >= 0
          && (_DWORD)v15 == (_DWORD)v12
          && (_DWORD)v14 == (_DWORD)v11
          && *(_QWORD *)((char *)&v14 + 4) == *(_QWORD *)((char *)&v11 + 4)
          && HIWORD(v14) == HIWORD(v11) )
        {
          return 1;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011190  mov     [rsp-8+arg_10], rbx
0x180011195  mov     [rsp-8+arg_18], rdi
0x18001119a  push    rbp
0x18001119b  lea     rbp, [rsp-57h]
0x1800111a0  sub     rsp, 90h
0x1800111a7  mov     rax, cs:__security_cookie
0x1800111ae  xor     rax, rsp
0x1800111b1  mov     [rbp+57h+var_8], rax
0x1800111b5  xorps   xmm0, xmm0
0x1800111b8  mov     [rbp+57h+var_60], 0
0x1800111bf  xor     eax, eax
0x1800111c1  mov     [rbp+57h+var_5C], 0
0x1800111c8  xorps   xmm1, xmm1
0x1800111cb  mov     [rbp+57h+var_10], rax
0x1800111cf  movups  [rbp+57h+var_30], xmm0
0x1800111d3  mov     [rbp+57h+var_38], rax
0x1800111d7  mov     rbx, rdx
0x1800111da  movups  [rbp+57h+var_20], xmm0
0x1800111de  mov     rdi, rcx
0x1800111e1  movups  [rbp+57h+var_58], xmm1
0x1800111e5  movups  [rbp+57h+var_48], xmm1
0x1800111e9  call    AVIStreamStart
0x1800111ee  mov     rcx, [rdi]
0x1800111f1  lea     r9, [rbp+57h+var_60]
0x1800111f5  mov     edx, eax
0x1800111f7  xor     r8d, r8d
0x1800111fa  mov     r10, [rcx+30h]
0x1800111fe  mov     rcx, rdi
0x180011201  mov     rax, r10
0x180011204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011209  test    eax, eax
0x18001120b  js      loc_1800112D4
0x180011211  mov     rcx, rbx; pavi
0x180011214  call    AVIStreamStart
0x180011219  mov     rcx, [rbx]
0x18001121c  lea     r9, [rbp+57h+var_5C]
0x180011220  mov     edx, eax
0x180011222  xor     r8d, r8d
0x180011225  mov     r10, [rcx+30h]
0x180011229  mov     rcx, rbx
0x18001122c  mov     rax, r10
0x18001122f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011234  test    eax, eax
0x180011236  js      loc_1800112D4
0x18001123c  mov     eax, [rbp+57h+var_5C]
0x18001123f  cmp     [rbp+57h+var_60], eax
0x180011242  jnz     loc_1800112D4
0x180011248  mov     eax, 28h ; '('
0x18001124d  mov     rcx, rdi; pavi
0x180011250  mov     [rbp+57h+var_60], eax
0x180011253  mov     [rbp+57h+var_5C], eax
0x180011256  call    AVIStreamStart
0x18001125b  mov     rdx, [rdi]
0x18001125e  lea     r9, [rbp+57h+var_60]
0x180011262  lea     r8, [rbp+57h+var_30]
0x180011266  mov     rcx, rdi
0x180011269  mov     r10, [rdx+30h]
0x18001126d  mov     edx, eax
0x18001126f  mov     rax, r10
0x180011272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011277  test    eax, eax
0x180011279  js      short loc_1800112D4
0x18001127b  mov     rcx, rbx; pavi
0x18001127e  call    AVIStreamStart
0x180011283  mov     rdx, [rbx]
0x180011286  lea     r9, [rbp+57h+var_5C]
0x18001128a  lea     r8, [rbp+57h+var_58]
0x18001128e  mov     rcx, rbx
0x180011291  mov     r10, [rdx+30h]
0x180011295  mov     edx, eax
0x180011297  mov     rax, r10
0x18001129a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001129f  test    eax, eax
0x1800112a1  js      short loc_1800112D4
0x1800112a3  mov     eax, dword ptr [rbp+57h+var_48]
0x1800112a6  cmp     dword ptr [rbp+57h+var_20], eax
0x1800112a9  jnz     short loc_1800112D4
0x1800112ab  mov     eax, dword ptr [rbp+57h+var_58]
0x1800112ae  cmp     dword ptr [rbp+57h+var_30], eax
0x1800112b1  jnz     short loc_1800112D4
0x1800112b3  mov     eax, dword ptr [rbp+57h+var_58+4]
0x1800112b6  cmp     dword ptr [rbp+57h+var_30+4], eax
0x1800112b9  jnz     short loc_1800112D4
0x1800112bb  mov     eax, dword ptr [rbp+57h+var_58+8]
0x1800112be  cmp     dword ptr [rbp+57h+var_30+8], eax
0x1800112c1  jnz     short loc_1800112D4
0x1800112c3  movzx   eax, word ptr [rbp+57h+var_58+0Eh]
0x1800112c7  cmp     word ptr [rbp+57h+var_30+0Eh], ax
0x1800112cb  jnz     short loc_1800112D4
0x1800112cd  mov     eax, 1
0x1800112d2  jmp     short loc_1800112D6
0x1800112d4  xor     eax, eax
0x1800112d6  mov     rcx, [rbp+57h+var_8]
0x1800112da  xor     rcx, rsp; StackCookie
0x1800112dd  call    __security_check_cookie
0x1800112e2  lea     r11, [rsp+90h+var_s0]
0x1800112ea  mov     rbx, [r11+20h]
0x1800112ee  mov     rdi, [r11+28h]
0x1800112f2  mov     rsp, r11
0x1800112f5  pop     rbp
0x1800112f6  retn
```
