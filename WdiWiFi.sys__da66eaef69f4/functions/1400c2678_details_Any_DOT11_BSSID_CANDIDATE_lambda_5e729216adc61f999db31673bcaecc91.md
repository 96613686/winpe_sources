# details::Any_DOT11_BSSID_CANDIDATE__lambda_5e729216adc61f999db31673bcaecc91___

- ea: `0x1400c2678`
- end: `0x1400c26e1`
- name: `details::Any_DOT11_BSSID_CANDIDATE__lambda_5e729216adc61f999db31673bcaecc91___`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005fa98`

## callees

- `0x1400c2678`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400c26b2`
- `ntoskrnl!RtlCompareMemory` at `0x1400c26b2`

## pseudocode

```c
char __fastcall details::Any_DOT11_BSSID_CANDIDATE__lambda_5e729216adc61f999db31673bcaecc91___(
        int a1,
        char *a2,
        __int64 a3)
{
  char *v4; // rbx
  char *v5; // rdi

  v4 = a2;
  v5 = &a2[12 * a1];
  while ( v4 != v5 )
  {
    if ( RtlCompareMemory((const void *)(**(_QWORD **)a3 + 444LL), v4, 6u) == 6 )
      return 1;
    v4 += 12;
  }
  return 0;
}

```

## disassembly

```asm
0x1400c2678  mov     [rsp+arg_0], rbx
0x1400c267d  mov     [rsp+arg_8], rsi
0x1400c2682  push    rdi
0x1400c2683  sub     rsp, 20h
0x1400c2687  mov     eax, ecx
0x1400c2689  mov     rsi, r8
0x1400c268c  mov     rbx, rdx
0x1400c268f  lea     rcx, [rax+rax*2]
0x1400c2693  lea     rdi, [rdx+rcx*4]
0x1400c2697  cmp     rbx, rdi
0x1400c269a  jz      short loc_1400C26CE
0x1400c269c  mov     rax, [rsi]
0x1400c269f  mov     r8d, 6; Length
0x1400c26a5  mov     rdx, rbx; Source2
0x1400c26a8  mov     rcx, [rax]
0x1400c26ab  add     rcx, 1BCh; Source1
0x1400c26b2  call    cs:__imp_RtlCompareMemory
0x1400c26b9  nop     dword ptr [rax+rax+00h]
0x1400c26be  cmp     rax, 6
0x1400c26c2  jz      short loc_1400C26CA
0x1400c26c4  add     rbx, 0Ch
0x1400c26c8  jmp     short loc_1400C2697
0x1400c26ca  mov     al, 1
0x1400c26cc  jmp     short loc_1400C26D0
0x1400c26ce  xor     al, al
0x1400c26d0  mov     rbx, [rsp+28h+arg_0]
0x1400c26d5  mov     rsi, [rsp+28h+arg_8]
0x1400c26da  add     rsp, 20h
0x1400c26de  pop     rdi
0x1400c26df  retn
```
