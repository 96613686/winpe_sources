# TOKEN_KEY::GetIsEqual(IHttpCacheKey *)

- ea: `0x180005960`
- end: `0x1800059cb`
- name: `?GetIsEqual@TOKEN_KEY@@UEBA_NPEAVIHttpCacheKey@@@Z`
- size: `107`
- prototype: `bool __fastcall(TOKEN_KEY *__hidden this, struct IHttpCacheKey *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005960`
- `0x180008010`

## pseudocode

```c
bool __fastcall TOKEN_KEY::GetIsEqual(TOKEN_KEY *this, struct IHttpCacheKey *a2)
{
  unsigned __int16 *v3; // rbx
  __int64 v5; // rax
  int v6; // edx
  int v7; // ecx

  v3 = (unsigned __int16 *)*((_QWORD *)this + 5);
  v5 = (*(__int64 (__fastcall **)(struct IHttpCacheKey *))(*(_QWORD *)a2 + 40LL))(a2) - (_QWORD)v3;
  do
  {
    v6 = *(unsigned __int16 *)((char *)v3 + v5);
    v7 = *v3 - v6;
    if ( v7 )
      break;
    ++v3;
  }
  while ( v6 );
  return !v7
      && *((_DWORD *)this + 30) == (*(unsigned int (__fastcall **)(struct IHttpCacheKey *))(*(_QWORD *)a2 + 56LL))(a2);
}

```

## disassembly

```asm
0x180005960  mov     [rsp+arg_0], rbx
0x180005965  mov     [rsp+arg_8], rsi
0x18000596a  push    rdi
0x18000596b  sub     rsp, 20h
0x18000596f  mov     rax, [rdx]
0x180005972  mov     rsi, rcx
0x180005975  mov     rbx, [rcx+28h]
0x180005979  mov     rdi, rdx
0x18000597c  mov     rcx, rdx
0x18000597f  mov     rax, [rax+28h]
0x180005983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005988  sub     rax, rbx
0x18000598b  movzx   ecx, word ptr [rbx]
0x18000598e  movzx   edx, word ptr [rbx+rax]
0x180005992  sub     ecx, edx
0x180005994  jnz     short loc_18000599E
0x180005996  add     rbx, 2
0x18000599a  test    edx, edx
0x18000599c  jnz     short loc_18000598B
0x18000599e  test    ecx, ecx
0x1800059a0  jnz     short loc_1800059B9
0x1800059a2  mov     rax, [rdi]
0x1800059a5  mov     rcx, rdi
0x1800059a8  mov     rax, [rax+38h]
0x1800059ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b1  cmp     [rsi+78h], eax
0x1800059b4  setz    al
0x1800059b7  jmp     short loc_1800059BB
0x1800059b9  xor     al, al
0x1800059bb  mov     rbx, [rsp+28h+arg_0]
0x1800059c0  mov     rsi, [rsp+28h+arg_8]
0x1800059c5  add     rsp, 20h
0x1800059c9  pop     rdi
0x1800059ca  retn
```
