# TOKEN_KEY::GetIsEqual(IHttpCacheKey *)

- ea: `0x1800046d0`
- end: `0x18000473b`
- name: `?GetIsEqual@TOKEN_KEY@@UEBA_NPEAVIHttpCacheKey@@@Z`
- size: `107`
- prototype: `bool __fastcall(TOKEN_KEY *__hidden this, struct IHttpCacheKey *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800046d0`
- `0x180006010`

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
0x1800046d0  mov     [rsp+arg_0], rbx
0x1800046d5  mov     [rsp+arg_8], rsi
0x1800046da  push    rdi
0x1800046db  sub     rsp, 20h
0x1800046df  mov     rax, [rdx]
0x1800046e2  mov     rsi, rcx
0x1800046e5  mov     rbx, [rcx+28h]
0x1800046e9  mov     rdi, rdx
0x1800046ec  mov     rcx, rdx
0x1800046ef  mov     rax, [rax+28h]
0x1800046f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046f8  sub     rax, rbx
0x1800046fb  movzx   ecx, word ptr [rbx]
0x1800046fe  movzx   edx, word ptr [rbx+rax]
0x180004702  sub     ecx, edx
0x180004704  jnz     short loc_18000470E
0x180004706  add     rbx, 2
0x18000470a  test    edx, edx
0x18000470c  jnz     short loc_1800046FB
0x18000470e  test    ecx, ecx
0x180004710  jnz     short loc_180004729
0x180004712  mov     rax, [rdi]
0x180004715  mov     rcx, rdi
0x180004718  mov     rax, [rax+38h]
0x18000471c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004721  cmp     [rsi+78h], eax
0x180004724  setz    al
0x180004727  jmp     short loc_18000472B
0x180004729  xor     al, al
0x18000472b  mov     rbx, [rsp+28h+arg_0]
0x180004730  mov     rsi, [rsp+28h+arg_8]
0x180004735  add     rsp, 20h
0x180004739  pop     rdi
0x18000473a  retn
```
