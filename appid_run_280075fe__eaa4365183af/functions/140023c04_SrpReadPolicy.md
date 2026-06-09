# SrpReadPolicy

- ea: `0x140023c04`
- end: `0x140023d4d`
- name: `SrpReadPolicy`
- size: `329`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001fef0`
- `0x140021c3c`

## callees

- `0x14002333c`
- `0x140023c04`
- `0x140024978`
- `0x140024c50`
- `0x140024f88`

## pseudocode

```c
__int64 __fastcall SrpReadPolicy(__int64 a1)
{
  int v2; // esi
  _OWORD *v3; // rbx
  int Policy; // ebx
  unsigned int v5; // ecx

  v2 = 0;
  *(_OWORD *)(a1 + 240) = xmmword_14000C040;
  *(_OWORD *)(a1 + 264) = xmmword_14000C030;
  *(_OWORD *)(a1 + 288) = xmmword_14000C020;
  *(_OWORD *)(a1 + 312) = xmmword_14000C010;
  while ( v2 < 4 )
  {
    v3 = (_OWORD *)(a1 + 48LL * v2);
    *v3 = *(_OWORD *)&byte_140009340[16 * v2];
    v3[1] = *(_OWORD *)&aXz[8 * v2];
    AiLogEvent(qword_1400196F8, (const EVENT_DESCRIPTOR *)SrpPolicyLoadStart);
    Policy = SrpLoadPolicy(v3);
    if ( Policy < 0 )
    {
      AiLogEvent(qword_1400196F8, (const EVENT_DESCRIPTOR *)SrpPolicyLoadFailure);
      return (unsigned int)Policy;
    }
    AiLogEvent(qword_1400196F8, (const EVENT_DESCRIPTOR *)SrpPolicyLoadSuccess);
    ++v2;
  }
  Policy = SrpLoadPlugins(a1 + 192);
  if ( Policy >= 0 )
  {
    SrpComputeCombinedAttributes(a1);
    v5 = *(_DWORD *)(a1 + 256) | *(_DWORD *)(a1 + 328);
    *(_DWORD *)(a1 + 344) = 0;
    *(_DWORD *)(a1 + 336) = v5 & 1;
    *(_DWORD *)(a1 + 348) = (v5 >> 1) & 1;
    *(_DWORD *)(a1 + 352) = (v5 >> 2) & 1;
    *(_DWORD *)(a1 + 356) = (v5 >> 3) & 1;
    *(_DWORD *)(a1 + 340) = (v5 >> 4) & 1;
  }
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x140023c04  push    rbx
0x140023c06  push    rsi
0x140023c07  push    rdi
0x140023c08  push    r14
0x140023c0a  sub     rsp, 28h
0x140023c0e  movups  xmm0, cs:xmmword_14000C040
0x140023c15  mov     rdi, rcx
0x140023c18  xor     esi, esi
0x140023c1a  movups  xmm1, cs:xmmword_14000C030
0x140023c21  lea     r14, cs:140000000h
0x140023c28  movdqu  xmmword ptr [rcx+0F0h], xmm0
0x140023c30  movups  xmm0, cs:xmmword_14000C020
0x140023c37  movdqu  xmmword ptr [rcx+108h], xmm1
0x140023c3f  movups  xmm1, cs:xmmword_14000C010
0x140023c46  movdqu  xmmword ptr [rcx+120h], xmm0
0x140023c4e  movdqu  xmmword ptr [rcx+138h], xmm1
0x140023c56  cmp     esi, 4
0x140023c59  jge     short loc_140023CD0
0x140023c5b  movsxd  rax, esi
0x140023c5e  mov     rdx, rax
0x140023c61  add     rdx, rdx
0x140023c64  lea     rbx, [rax+rax*2]
0x140023c68  shl     rbx, 4
0x140023c6c  movups  xmm0, xmmword ptr ds:rva byte_140009340[r14+rdx*8]
0x140023c75  add     rbx, rdi
0x140023c78  movdqu  xmmword ptr [rbx], xmm0
0x140023c7c  movups  xmm0, xmmword ptr ds:rva aXz[r14+rdx*8]; "XZ" ...
0x140023c85  lea     rdx, SrpPolicyLoadStart
0x140023c8c  movdqu  xmmword ptr [rbx+10h], xmm0
0x140023c91  mov     rcx, cs:qword_1400196F8
0x140023c98  call    AiLogEvent
0x140023c9d  mov     rcx, rbx
0x140023ca0  call    SrpLoadPolicy
0x140023ca5  mov     rcx, cs:qword_1400196F8
0x140023cac  mov     ebx, eax
0x140023cae  test    eax, eax
0x140023cb0  js      short loc_140023CC2
0x140023cb2  lea     rdx, SrpPolicyLoadSuccess
0x140023cb9  call    AiLogEvent
0x140023cbe  inc     esi
0x140023cc0  jmp     short loc_140023C56
0x140023cc2  lea     rdx, SrpPolicyLoadFailure
0x140023cc9  call    AiLogEvent
0x140023cce  jmp     short loc_140023D40
0x140023cd0  lea     rcx, [rdi+0C0h]
0x140023cd7  call    SrpLoadPlugins
0x140023cdc  mov     ebx, eax
0x140023cde  test    eax, eax
0x140023ce0  js      short loc_140023D40
0x140023ce2  mov     rcx, rdi
0x140023ce5  call    SrpComputeCombinedAttributes
0x140023cea  mov     ecx, [rdi+148h]
0x140023cf0  or      ecx, [rdi+100h]
0x140023cf6  mov     dword ptr [rdi+158h], 0
0x140023d00  mov     eax, ecx
0x140023d02  and     eax, 1
0x140023d05  mov     [rdi+150h], eax
0x140023d0b  mov     eax, ecx
0x140023d0d  shr     eax, 1
0x140023d0f  and     eax, 1
0x140023d12  mov     [rdi+15Ch], eax
0x140023d18  mov     eax, ecx
0x140023d1a  shr     eax, 2
0x140023d1d  and     eax, 1
0x140023d20  mov     [rdi+160h], eax
0x140023d26  mov     eax, ecx
0x140023d28  shr     eax, 3
0x140023d2b  and     eax, 1
0x140023d2e  shr     ecx, 4
0x140023d31  and     ecx, 1
0x140023d34  mov     [rdi+164h], eax
0x140023d3a  mov     [rdi+154h], ecx
0x140023d40  mov     eax, ebx
0x140023d42  add     rsp, 28h
0x140023d46  pop     r14
0x140023d48  pop     rdi
0x140023d49  pop     rsi
0x140023d4a  pop     rbx
0x140023d4b  retn
```
