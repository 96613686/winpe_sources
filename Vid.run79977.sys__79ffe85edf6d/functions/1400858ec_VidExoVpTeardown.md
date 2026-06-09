# VidExoVpTeardown

- ea: `0x1400858ec`
- end: `0x1400859fb`
- name: `VidExoVpTeardown`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011d70`

## callees

- `0x1400858ec`
- `0x140085cc4`
- `0x140085df8`

## import_xrefs

- `ntoskrnl!KeRemoveQueueDpcEx` at `0x1400859e3`
- `ntoskrnl!KeRemoveQueueDpcEx` at `0x1400859e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085984`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400859b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085984`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400859b9`

## pseudocode

```c
__int64 __fastcall VidExoVpTeardown(__int64 a1, __int64 a2)
{
  __int64 i; // rdi
  unsigned int j; // esi
  __int64 v5; // rax
  __int64 v6; // r14

  if ( *(_QWORD *)(a1 + 11976) )
  {
    if ( *(_DWORD *)(a1 + 11984) )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 11984) >> 6; i = (unsigned int)(i + 1) )
      {
        for ( j = 0; ; ++j )
        {
          v5 = *(_QWORD *)(a1 + 11976);
          if ( j >= 0x40 )
            break;
          v6 = 16LL * j + *(_QWORD *)(v5 + 8 * i);
          if ( (unsigned __int8)VidExoVppLockForDelete(a1, v6) )
          {
            VidExoVppDelete(a1, *(unsigned int **)(v6 + 8), 1);
            *(_QWORD *)(v6 + 8) = 0;
            *(_DWORD *)v6 = 0;
          }
          if ( *(_DWORD *)v6 )
            __fastfail(5u);
        }
        ExFreePoolWithTag(*(PVOID *)(v5 + 8 * i), 0x72446456u);
        *(_QWORD *)(*(_QWORD *)(a1 + 11976) + 8 * i) = 0;
      }
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 11976), 0x72446456u);
    *(_QWORD *)(a1 + 11976) = 0;
    *(_DWORD *)(a1 + 11984) = 0;
  }
  LOBYTE(a2) = 1;
  return KeRemoveQueueDpcEx(a1 + 12000, a2);
}

```

## disassembly

```asm
0x1400858ec  push    rbx
0x1400858ee  push    rbp
0x1400858ef  push    rsi
0x1400858f0  push    rdi
0x1400858f1  push    r14
0x1400858f3  sub     rsp, 20h
0x1400858f7  cmp     qword ptr [rcx+2EC8h], 0
0x1400858ff  mov     rbx, rcx
0x140085902  jz      loc_1400859DA
0x140085908  cmp     dword ptr [rcx+2ED0h], 0
0x14008590f  jbe     loc_1400859AD
0x140085915  xor     edi, edi
0x140085917  mov     eax, [rbx+2ED0h]
0x14008591d  shr     eax, 6
0x140085920  cmp     edi, eax
0x140085922  jnb     loc_1400859AD
0x140085928  xor     esi, esi
0x14008592a  mov     rax, [rbx+2EC8h]
0x140085931  cmp     esi, 40h ; '@'
0x140085934  jnb     short loc_14008597B
0x140085936  mov     r14, [rax+rdi*8]
0x14008593a  mov     ecx, esi
0x14008593c  shl     rcx, 4
0x140085940  add     r14, rcx
0x140085943  mov     rcx, rbx
0x140085946  mov     rdx, r14
0x140085949  call    VidExoVppLockForDelete
0x14008594e  test    al, al
0x140085950  jz      short loc_140085970
0x140085952  mov     rdx, [r14+8]
0x140085956  mov     r8b, 1
0x140085959  mov     rcx, rbx
0x14008595c  call    VidExoVppDelete
0x140085961  mov     qword ptr [r14+8], 0
0x140085969  mov     dword ptr [r14], 0
0x140085970  mov     eax, [r14]
0x140085973  test    eax, eax
0x140085975  jnz     short loc_1400859A6
0x140085977  inc     esi
0x140085979  jmp     short loc_14008592A
0x14008597b  mov     rcx, [rax+rdi*8]; P
0x14008597f  mov     edx, 72446456h; Tag
0x140085984  call    cs:__imp_ExFreePoolWithTag
0x14008598b  nop     dword ptr [rax+rax+00h]
0x140085990  mov     rax, [rbx+2EC8h]
0x140085997  mov     qword ptr [rax+rdi*8], 0
0x14008599f  inc     edi
0x1400859a1  jmp     loc_140085917
0x1400859a6  mov     ecx, 5
0x1400859ab  int     29h; Win8: RtlFailFast(ecx)
0x1400859ad  mov     rcx, [rbx+2EC8h]; P
0x1400859b4  mov     edx, 72446456h; Tag
0x1400859b9  call    cs:__imp_ExFreePoolWithTag
0x1400859c0  nop     dword ptr [rax+rax+00h]
0x1400859c5  mov     qword ptr [rbx+2EC8h], 0
0x1400859d0  mov     dword ptr [rbx+2ED0h], 0
0x1400859da  lea     rcx, [rbx+2EE0h]
0x1400859e1  mov     dl, 1
0x1400859e3  call    cs:__imp_KeRemoveQueueDpcEx
0x1400859ea  nop     dword ptr [rax+rax+00h]
0x1400859ef  add     rsp, 20h
0x1400859f3  pop     r14
0x1400859f5  pop     rdi
0x1400859f6  pop     rsi
0x1400859f7  pop     rbp
0x1400859f8  pop     rbx
0x1400859f9  retn
```
