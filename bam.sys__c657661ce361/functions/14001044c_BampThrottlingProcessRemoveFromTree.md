# BampThrottlingProcessRemoveFromTree

- ea: `0x14001044c`
- end: `0x14001059d`
- name: `BampThrottlingProcessRemoveFromTree`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140012450`

## callees

- `0x14001044c`
- `0x140010760`
- `0x1400107a0`
- `0x1400107f0`
- `0x140010880`
- `0x1400108a8`
- `0x140010928`
- `0x140011560`

## pseudocode

```c
__int64 __fastcall BampThrottlingProcessRemoveFromTree(__int64 a1)
{
  __int64 v2; // rdx
  char v3; // bl
  void *v4; // rsi
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 result; // rax
  _QWORD **v8; // r14
  _QWORD *v9; // rbx
  _QWORD *v10; // rax
  __int128 v11; // [rsp+20h] [rbp-38h] BYREF

  v11 = 0;
  BampAcquireThrottledProcessLock(a1);
  v3 = 1;
  if ( (*(_DWORD *)(a1 + 304) & 1) != 0 )
  {
    *((_QWORD *)&v11 + 1) = 1;
    *(_QWORD *)&v11 = a1 + 328;
    BampThrottlingProcessEnumerateWindowlessDescendants(a1, v2, &v11);
  }
  while ( 1 )
  {
    v4 = *(void **)(a1 + 64);
    if ( !v4 )
    {
      v8 = (_QWORD **)(a1 + 32);
      while ( 1 )
      {
        v9 = *v8;
        if ( *v8 == v8 )
          break;
        if ( (_QWORD **)v9[1] != v8 )
          goto LABEL_21;
        v10 = (_QWORD *)*v9;
        if ( *(_QWORD **)(*v9 + 8LL) != v9 )
          goto LABEL_21;
        *v8 = v10;
        v10[1] = v8;
        BampAcquireThrottledProcessLock(v9 - 6);
        v9[2] = 0;
        BampReleaseThrottledProcessLock(v9 - 6);
      }
      v3 = 0;
      goto LABEL_8;
    }
    BampReferenceThrottledProcessInformation(*(_QWORD *)(a1 + 64));
    if ( (unsigned __int8)BampTryAcquireThrottledProcessLock(v4) )
      break;
    BampReleaseThrottledProcessLock(a1);
    BampAcquireThrottledProcessLock(v4);
    BampAcquireThrottledProcessLock(a1);
    if ( *(void **)(a1 + 64) == v4 )
      break;
    BampReleaseThrottledProcessLock(v4);
    BampDereferenceThrottledProcessInformation(v4);
  }
  BampReparentChildren(a1, v4);
  v5 = *(_QWORD *)(a1 + 48);
  if ( *(_QWORD *)(v5 + 8) != a1 + 48 || (v6 = *(_QWORD **)(a1 + 56), *v6 != a1 + 48) )
LABEL_21:
    __fastfail(3u);
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
LABEL_8:
  result = BampReleaseThrottledProcessLock(a1);
  if ( v3 )
    result = BampReleaseThrottledProcessLock(v4);
  if ( v4 )
    return BampDereferenceThrottledProcessInformation(v4);
  return result;
}

```

## disassembly

```asm
0x14001044c  push    rbx
0x14001044e  push    rsi
0x14001044f  push    rdi
0x140010450  push    r14
0x140010452  sub     rsp, 38h
0x140010456  xorps   xmm0, xmm0
0x140010459  mov     rdi, rcx
0x14001045c  movups  [rsp+58h+var_38], xmm0
0x140010461  call    BampAcquireThrottledProcessLock
0x140010466  mov     eax, [rdi+130h]
0x14001046c  mov     ebx, 1
0x140010471  test    bl, al
0x140010473  jnz     loc_14001053C
0x140010479  mov     rsi, [rdi+40h]
0x14001047d  test    rsi, rsi
0x140010480  jz      short loc_1400104F6
0x140010482  mov     rcx, rsi
0x140010485  call    BampReferenceThrottledProcessInformation
0x14001048a  mov     rcx, rsi
0x14001048d  call    BampTryAcquireThrottledProcessLock
0x140010492  test    al, al
0x140010494  jz      loc_14001055F
0x14001049a  mov     rdx, rsi
0x14001049d  mov     rcx, rdi
0x1400104a0  call    BampReparentChildren
0x1400104a5  lea     rax, [rdi+30h]
0x1400104a9  mov     rdx, [rax]
0x1400104ac  cmp     [rdx+8], rax
0x1400104b0  jnz     loc_140010596
0x1400104b6  mov     rcx, [rax+8]
0x1400104ba  cmp     [rcx], rax
0x1400104bd  jnz     loc_140010596
0x1400104c3  mov     [rcx], rdx
0x1400104c6  mov     [rdx+8], rcx
0x1400104ca  mov     rcx, rdi
0x1400104cd  call    BampReleaseThrottledProcessLock
0x1400104d2  test    bl, bl
0x1400104d4  jz      short loc_1400104DE
0x1400104d6  mov     rcx, rsi
0x1400104d9  call    BampReleaseThrottledProcessLock
0x1400104de  test    rsi, rsi
0x1400104e1  jz      short loc_1400104EB
0x1400104e3  mov     rcx, rsi; P
0x1400104e6  call    BampDereferenceThrottledProcessInformation
0x1400104eb  add     rsp, 38h
0x1400104ef  pop     r14
0x1400104f1  pop     rdi
0x1400104f2  pop     rsi
0x1400104f3  pop     rbx
0x1400104f4  retn
0x1400104f6  lea     r14, [rdi+20h]
0x1400104fa  mov     rbx, [r14]
0x1400104fd  cmp     rbx, r14
0x140010500  jnz     short loc_140010506
0x140010502  xor     bl, bl
0x140010504  jmp     short loc_1400104CA
0x140010506  cmp     [rbx+8], r14
0x14001050a  jnz     loc_140010596
0x140010510  mov     rax, [rbx]
0x140010513  cmp     [rax+8], rbx
0x140010517  jnz     short loc_140010596
0x140010519  mov     [r14], rax
0x14001051c  lea     rcx, [rbx-30h]
0x140010520  mov     [rax+8], r14
0x140010524  call    BampAcquireThrottledProcessLock
0x140010529  lea     rcx, [rbx-30h]
0x14001052d  mov     qword ptr [rbx+10h], 0
0x140010535  call    BampReleaseThrottledProcessLock
0x14001053a  jmp     short loc_1400104FA
0x14001053c  lea     rax, [rdi+148h]
0x140010543  mov     qword ptr [rsp+58h+var_38+8], rbx
0x140010548  lea     r8, [rsp+58h+var_38]
0x14001054d  mov     qword ptr [rsp+58h+var_38], rax
0x140010552  mov     rcx, rdi
0x140010555  call    BampThrottlingProcessEnumerateWindowlessDescendants
0x14001055a  jmp     loc_140010479
0x14001055f  mov     rcx, rdi
0x140010562  call    BampReleaseThrottledProcessLock
0x140010567  mov     rcx, rsi
0x14001056a  call    BampAcquireThrottledProcessLock
0x14001056f  mov     rcx, rdi
0x140010572  call    BampAcquireThrottledProcessLock
0x140010577  cmp     [rdi+40h], rsi
0x14001057b  jz      loc_14001049A
0x140010581  mov     rcx, rsi
0x140010584  call    BampReleaseThrottledProcessLock
0x140010589  mov     rcx, rsi; P
0x14001058c  call    BampDereferenceThrottledProcessInformation
0x140010591  jmp     loc_140010479
0x140010596  mov     ecx, 3
0x14001059b  int     29h; Win8: RtlFailFast(ecx)
```
