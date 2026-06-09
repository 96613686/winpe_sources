# blobReadWrite

- ea: `0x18006a1ac`
- end: `0x18006a29a`
- name: `blobReadWrite`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18008cee0`
- `0x18008cfe0`

## callees

- `0x180009f00`
- `0x18000a404`
- `0x18000a430`
- `0x18000b220`
- `0x180023b30`
- `0x180024440`
- `0x18005ba3c`
- `0x180060134`
- `0x18006a1ac`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall blobReadWrite(
        int *a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 (__fastcall *a5)(_QWORD, _QWORD, _QWORD, __int64))
{
  __int64 v5; // rdi
  __int64 v7; // r14
  __int64 v10; // rsi
  __int64 v11; // rbp
  unsigned int v12; // edi
  unsigned int v13; // ebx

  v5 = a4;
  v7 = a3;
  if ( !a1 )
    return sqlite3ReportError(21, 103016, "misuse");
  v10 = *((_QWORD *)a1 + 4);
  sqlite3_mutex_enter(*(_QWORD *)(v10 + 24));
  if ( (int)v7 < 0 || (int)v5 < 0 || v5 + v7 > *a1 )
  {
    v12 = 1;
  }
  else
  {
    v11 = *((_QWORD *)a1 + 3);
    if ( v11 )
    {
      sqlite3BtreeEnter(*(_QWORD *)(*((_QWORD *)a1 + 2) + 8LL));
      v12 = a5(*((_QWORD *)a1 + 2), (unsigned int)(v5 + a1[1]), (unsigned int)v7, a2);
      sqlite3BtreeLeave(*(_QWORD *)(*((_QWORD *)a1 + 2) + 8LL));
      if ( v12 == 4 )
      {
        sqlite3VdbeFinalize(v11);
        *((_QWORD *)a1 + 3) = 0;
      }
      else
      {
        *(_DWORD *)(v11 + 52) = v12;
      }
    }
    else
    {
      v12 = 4;
    }
  }
  sqlite3Error(v10, v12);
  v13 = sqlite3ApiExit(v10, v12);
  sqlite3_mutex_leave(*(_QWORD *)(v10 + 24));
  return v13;
}

```

## disassembly

```asm
0x18006a1ac  push    rbx
0x18006a1ae  push    rbp
0x18006a1af  push    rsi
0x18006a1b0  push    rdi
0x18006a1b1  push    r14
0x18006a1b3  push    r15
0x18006a1b5  sub     rsp, 38h
0x18006a1b9  movsxd  rdi, r9d
0x18006a1bc  mov     r15, rdx
0x18006a1bf  movsxd  r14, r8d
0x18006a1c2  mov     rbx, rcx
0x18006a1c5  test    rcx, rcx
0x18006a1c8  jnz     short loc_18006A1E3
0x18006a1ca  lea     r8, aMisuse; "misuse"
0x18006a1d1  mov     edx, 19268h
0x18006a1d6  lea     ecx, [rbx+15h]
0x18006a1d9  call    sqlite3ReportError
0x18006a1de  jmp     loc_18006A28D
0x18006a1e3  mov     rsi, [rcx+20h]
0x18006a1e7  mov     rcx, [rsi+18h]
0x18006a1eb  call    sqlite3_mutex_enter
0x18006a1f0  test    r14d, r14d
0x18006a1f3  js      short loc_18006A267
0x18006a1f5  test    edi, edi
0x18006a1f7  js      short loc_18006A267
0x18006a1f9  movsxd  rax, dword ptr [rbx]
0x18006a1fc  lea     rcx, [rdi+r14]
0x18006a200  cmp     rcx, rax
0x18006a203  jg      short loc_18006A267
0x18006a205  mov     rbp, [rbx+18h]
0x18006a209  test    rbp, rbp
0x18006a20c  jnz     short loc_18006A213
0x18006a20e  lea     edi, [rbp+4]
0x18006a211  jmp     short loc_18006A26C
0x18006a213  mov     rcx, [rbx+10h]
0x18006a217  mov     rcx, [rcx+8]
0x18006a21b  call    sqlite3BtreeEnter
0x18006a220  mov     edx, [rbx+4]
0x18006a223  mov     r9, r15
0x18006a226  mov     rcx, [rbx+10h]
0x18006a22a  add     edx, edi
0x18006a22c  mov     rax, [rsp+68h+arg_20]
0x18006a234  mov     r8d, r14d
0x18006a237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a23c  mov     rcx, [rbx+10h]
0x18006a240  mov     edi, eax
0x18006a242  mov     rcx, [rcx+8]
0x18006a246  call    sqlite3BtreeLeave
0x18006a24b  cmp     edi, 4
0x18006a24e  jnz     short loc_18006A262
0x18006a250  mov     rcx, rbp
0x18006a253  call    sqlite3VdbeFinalize
0x18006a258  mov     qword ptr [rbx+18h], 0
0x18006a260  jmp     short loc_18006A26C
0x18006a262  mov     [rbp+34h], edi
0x18006a265  jmp     short loc_18006A26C
0x18006a267  mov     edi, 1
0x18006a26c  mov     edx, edi
0x18006a26e  mov     rcx, rsi
0x18006a271  call    sqlite3Error
0x18006a276  mov     edx, edi
0x18006a278  mov     rcx, rsi
0x18006a27b  call    sqlite3ApiExit
0x18006a280  mov     rcx, [rsi+18h]
0x18006a284  mov     ebx, eax
0x18006a286  call    sqlite3_mutex_leave
0x18006a28b  mov     eax, ebx
0x18006a28d  add     rsp, 38h
0x18006a291  pop     r15
0x18006a293  pop     r14
0x18006a295  pop     rdi
0x18006a296  pop     rsi
0x18006a297  pop     rbp
0x18006a298  pop     rbx
0x18006a299  retn
```
