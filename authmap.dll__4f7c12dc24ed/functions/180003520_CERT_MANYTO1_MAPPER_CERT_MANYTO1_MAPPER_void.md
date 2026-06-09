# CERT_MANYTO1_MAPPER::~CERT_MANYTO1_MAPPER(void)

- ea: `0x180003520`
- end: `0x180003573`
- name: `??1CERT_MANYTO1_MAPPER@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(CERT_MANYTO1_MAPPER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001c50`

## callees

- `0x180001048`
- `0x180003520`
- `0x18000357c`

## pseudocode

```c
void __fastcall CERT_MANYTO1_MAPPER::~CERT_MANYTO1_MAPPER(CERT_MANYTO1_MAPPER *this)
{
  CERT_MAP_RULE **v1; // rdi
  CERT_MAP_RULE *v2; // rbx
  CERT_MAP_RULE *v3; // rax
  CERT_MAP_RULE **v4; // rcx

  v1 = (CERT_MAP_RULE **)((char *)this + 8);
  while ( 1 )
  {
    v2 = *v1;
    if ( *v1 == (CERT_MAP_RULE *)v1 )
      break;
    v3 = *(CERT_MAP_RULE **)v2;
    if ( *(CERT_MAP_RULE **)(*(_QWORD *)v2 + 8LL) != v2 || (v4 = (CERT_MAP_RULE **)*((_QWORD *)v2 + 1), *v4 != v2) )
      __fastfail(3u);
    *v4 = v3;
    *((_QWORD *)v3 + 1) = v4;
    CERT_MAP_RULE::~CERT_MAP_RULE(v2);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180003520  mov     [rsp+arg_0], rbx
0x180003525  push    rdi
0x180003526  sub     rsp, 20h
0x18000352a  lea     rdi, [rcx+8]
0x18000352e  mov     rbx, [rdi]
0x180003531  cmp     rbx, rdi
0x180003534  jz      short loc_180003568
0x180003536  mov     rax, [rbx]
0x180003539  cmp     [rax+8], rbx
0x18000353d  jnz     short loc_180003561
0x18000353f  mov     rcx, [rbx+8]
0x180003543  cmp     [rcx], rbx
0x180003546  jnz     short loc_180003561
0x180003548  mov     [rcx], rax
0x18000354b  mov     [rax+8], rcx
0x18000354f  mov     rcx, rbx; this
0x180003552  call    ??1CERT_MAP_RULE@@QEAA@XZ; CERT_MAP_RULE::~CERT_MAP_RULE(void)
0x180003557  mov     rcx, rbx; Block
0x18000355a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000355f  jmp     short loc_18000352E
0x180003561  mov     ecx, 3
0x180003566  int     29h; Win8: RtlFailFast(ecx)
0x180003568  mov     rbx, [rsp+28h+arg_0]
0x18000356d  add     rsp, 20h
0x180003571  pop     rdi
0x180003572  retn
```
