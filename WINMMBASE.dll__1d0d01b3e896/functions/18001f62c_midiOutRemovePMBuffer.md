# midiOutRemovePMBuffer

- ea: `0x18001f62c`
- end: `0x18001f74d`
- name: `midiOutRemovePMBuffer`
- size: `289`
- prototype: `__int64 __fastcall(struct midiemu_tag *, DWORD_PTR dwParam1)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e0f0`
- `0x18001e8c8`
- `0x18001ebc0`

## callees

- `0x18000c570`
- `0x18000fa80`
- `0x180012d08`
- `0x180012d30`
- `0x18001e56c`
- `0x18001f62c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f6fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f6fe`

## pseudocode

```c
BOOL __fastcall midiOutRemovePMBuffer(struct midiemu_tag *a1, DWORD_PTR dwParam1)
{
  _DWORD *v4; // rdi
  int v5; // eax
  struct midihdr_tag *v6; // rsi
  HMIDIOUT v7; // rax
  HANDLE v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_a5414217d91338b5429dfea51ae86c50_Traceguids, dwParam1);
  }
  v4 = *(_DWORD **)(dwParam1 + 36);
  v5 = *v4;
  if ( *v4 )
  {
    v6 = (struct midihdr_tag *)(v4 + 4);
    do
    {
      *v4 = v5 - 1;
      if ( (v6->dwFlags & 6) == 2 )
      {
        v7 = (HMIDIOUT)mseIDtoHMidi(a1, v6->dwReserved[0]);
        midiOutUnprepareHeader(v7, v6, 0x70u);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_a5414217d91338b5429dfea51ae86c50_Traceguids);
      }
      v5 = *v4;
      ++v6;
    }
    while ( *v4 );
  }
  v8 = hHeap;
  *v4 = -1;
  HeapFree(v8, 0, v4);
  *(_DWORD *)(dwParam1 + 24) &= ~4u;
  *(_DWORD *)(dwParam1 + 24) |= 1u;
  *(_QWORD *)(dwParam1 + 36) = 0;
  return DriverCallback(
           *((_QWORD *)a1 + 13),
           *((unsigned __int16 *)a1 + 57),
           *((HDRVR *)a1 + 1),
           0x3C9u,
           *((_QWORD *)a1 + 15),
           dwParam1,
           0);
}

```

## disassembly

```asm
0x18001f62c  push    rbx
0x18001f62e  push    rbp
0x18001f62f  push    rsi
0x18001f630  push    rdi
0x18001f631  push    r15
0x18001f633  sub     rsp, 40h
0x18001f637  mov     rbx, rdx
0x18001f63a  mov     rbp, rcx
0x18001f63d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f644  lea     r15, WPP_GLOBAL_Control
0x18001f64b  cmp     rcx, r15
0x18001f64e  jz      short loc_18001F677
0x18001f650  test    dword ptr [rcx+1Ch], 400000h
0x18001f657  jz      short loc_18001F677
0x18001f659  cmp     byte ptr [rcx+19h], 2
0x18001f65d  jb      short loc_18001F677
0x18001f65f  mov     rcx, [rcx+10h]
0x18001f663  lea     r8, WPP_a5414217d91338b5429dfea51ae86c50_Traceguids
0x18001f66a  mov     edx, 35h ; '5'
0x18001f66f  mov     r9, rbx
0x18001f672  call    WPP_SF_P
0x18001f677  mov     rdi, [rbx+24h]
0x18001f67b  mov     eax, [rdi]
0x18001f67d  test    eax, eax
0x18001f67f  jz      short loc_18001F6EC
0x18001f681  lea     rsi, [rdi+10h]
0x18001f685  dec     eax
0x18001f687  mov     [rdi], eax
0x18001f689  mov     al, [rsi+18h]
0x18001f68c  and     al, 6
0x18001f68e  cmp     al, 2
0x18001f690  jnz     short loc_18001F6B0
0x18001f692  mov     edx, [rsi+30h]; unsigned int
0x18001f695  mov     rcx, rbp; struct midiemu_tag *
0x18001f698  call    ?mseIDtoHMidi@@YAPEAUHMIDI__@@PEAUmidiemu_tag@@K@Z; mseIDtoHMidi(midiemu_tag *,ulong)
0x18001f69d  mov     r8d, 70h ; 'p'; cbmh
0x18001f6a3  mov     rcx, rax; hmo
0x18001f6a6  mov     rdx, rsi; pmh
0x18001f6a9  call    midiOutUnprepareHeader
0x18001f6ae  jmp     short loc_18001F6E0
0x18001f6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6b7  cmp     rcx, r15
0x18001f6ba  jz      short loc_18001F6E0
0x18001f6bc  test    dword ptr [rcx+1Ch], 400000h
0x18001f6c3  jz      short loc_18001F6E0
0x18001f6c5  cmp     byte ptr [rcx+19h], 1
0x18001f6c9  jb      short loc_18001F6E0
0x18001f6cb  mov     rcx, [rcx+10h]
0x18001f6cf  lea     r8, WPP_a5414217d91338b5429dfea51ae86c50_Traceguids
0x18001f6d6  mov     edx, 37h ; '7'
0x18001f6db  call    WPP_SF_
0x18001f6e0  mov     eax, [rdi]
0x18001f6e2  add     rsi, 70h ; 'p'
0x18001f6e6  test    eax, eax
0x18001f6e8  jnz     short loc_18001F685
0x18001f6ea  jmp     short loc_18001F6EE
0x18001f6ec  xor     eax, eax
0x18001f6ee  mov     rcx, cs:hHeap; hHeap
0x18001f6f5  dec     eax
0x18001f6f7  mov     r8, rdi; lpMem
0x18001f6fa  mov     [rdi], eax
0x18001f6fc  xor     edx, edx; dwFlags
0x18001f6fe  call    cs:__imp_HeapFree
0x18001f704  and     dword ptr [rbx+18h], 0FFFFFFFBh
0x18001f708  mov     r9d, 3C9h; dwMsg
0x18001f70e  or      dword ptr [rbx+18h], 1
0x18001f712  mov     qword ptr [rbx+24h], 0
0x18001f71a  mov     rax, [rbp+78h]
0x18001f71e  movzx   edx, word ptr [rbp+72h]; dwFlags
0x18001f722  mov     r8, [rbp+8]; hDevice
0x18001f726  mov     rcx, [rbp+68h]; dwCallback
0x18001f72a  mov     [rsp+68h+dwParam2], 0; dwParam2
0x18001f733  mov     [rsp+68h+dwParam1], rbx; dwParam1
0x18001f738  mov     [rsp+68h+dwUser], rax; dwUser
0x18001f73d  call    DriverCallback
0x18001f742  add     rsp, 40h
0x18001f746  pop     r15
0x18001f748  pop     rdi
0x18001f749  pop     rsi
0x18001f74a  pop     rbp
0x18001f74b  pop     rbx
0x18001f74c  retn
```
