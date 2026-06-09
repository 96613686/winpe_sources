# details::Any<DOT11_BSSID_CANDIDATE,_lambda_a5fe7faf4cc35cad4ca5418db229ddae_>(ulong,DOT11_BSSID_CANDIDATE *,_lambda_a5fe7faf4cc35cad4ca5418db229ddae_ &)

- ea: `0x1400c26e8`
- end: `0x1400c2747`
- name: `??$Any@UDOT11_BSSID_CANDIDATE@@V_lambda_a5fe7faf4cc35cad4ca5418db229ddae_@@@details@@YA_NKPEAUDOT11_BSSID_CANDIDATE@@AEAV_lambda_a5fe7faf4cc35cad4ca5418db229ddae_@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400836f4`

## callees

- `0x1400c26e8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400c2718`
- `ntoskrnl!RtlCompareMemory` at `0x1400c2718`

## pseudocode

```c
char __fastcall details::Any<DOT11_BSSID_CANDIDATE,_lambda_a5fe7faf4cc35cad4ca5418db229ddae_>(
        int a1,
        char *a2,
        const void **a3)
{
  char *v4; // rbx
  char *v5; // rdi

  v4 = a2;
  v5 = &a2[12 * a1];
  while ( v4 != v5 )
  {
    if ( RtlCompareMemory(*a3, v4, 6u) == 6 )
      return 1;
    v4 += 12;
  }
  return 0;
}

```

## disassembly

```asm
0x1400c26e8  mov     [rsp+arg_0], rbx
0x1400c26ed  mov     [rsp+arg_8], rsi
0x1400c26f2  push    rdi
0x1400c26f3  sub     rsp, 20h
0x1400c26f7  mov     eax, ecx
0x1400c26f9  mov     rsi, r8
0x1400c26fc  mov     rbx, rdx
0x1400c26ff  lea     rcx, [rax+rax*2]
0x1400c2703  lea     rdi, [rdx+rcx*4]
0x1400c2707  cmp     rbx, rdi
0x1400c270a  jz      short loc_1400C2734
0x1400c270c  mov     rcx, [rsi]; Source1
0x1400c270f  mov     r8d, 6; Length
0x1400c2715  mov     rdx, rbx; Source2
0x1400c2718  call    cs:__imp_RtlCompareMemory
0x1400c271f  nop     dword ptr [rax+rax+00h]
0x1400c2724  cmp     rax, 6
0x1400c2728  jz      short loc_1400C2730
0x1400c272a  add     rbx, 0Ch
0x1400c272e  jmp     short loc_1400C2707
0x1400c2730  mov     al, 1
0x1400c2732  jmp     short loc_1400C2736
0x1400c2734  xor     al, al
0x1400c2736  mov     rbx, [rsp+28h+arg_0]
0x1400c273b  mov     rsi, [rsp+28h+arg_8]
0x1400c2740  add     rsp, 20h
0x1400c2744  pop     rdi
0x1400c2745  retn
```
