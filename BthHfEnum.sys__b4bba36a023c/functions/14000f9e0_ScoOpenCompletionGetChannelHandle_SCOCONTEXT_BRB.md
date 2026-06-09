# ScoOpenCompletionGetChannelHandle(_SCOCONTEXT *,_BRB *)

- ea: `0x14000f9e0`
- end: `0x14000fa32`
- name: `?ScoOpenCompletionGetChannelHandle@@YAJPEAU_SCOCONTEXT@@PEAU_BRB@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(struct _SCOCONTEXT *, struct _BRB *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fa40`

## callees

- `0x14000f9e0`

## pseudocode

```c
__int64 __fastcall ScoOpenCompletionGetChannelHandle(struct _SCOCONTEXT *a1, struct _BRB *a2)
{
  int v2; // eax
  NTSTATUS Status; // r8d

  v2 = *((_DWORD *)a1 + 7);
  if ( v2 == 33281 )
  {
    Status = a2->BrbHeader.Status;
    if ( Status >= 0 )
      *((_QWORD *)a1 + 16) = a2->BrbL2caOpenChannel.Callback;
  }
  else if ( v2 == 514 || (Status = 0, v2 == 528) )
  {
    Status = a2->BrbHeader.Status;
    if ( Status >= 0 )
      *((_QWORD *)a1 + 16) = a2->BrbScoOpenChannel.ChannelHandle;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000f9e0  mov     eax, [rcx+1Ch]
0x14000f9e3  mov     r9, rcx
0x14000f9e6  cmp     eax, 8201h
0x14000f9eb  jnz     short loc_14000FA06
0x14000f9ed  mov     r8d, [rdx+1Ch]
0x14000f9f1  test    r8d, r8d
0x14000f9f4  js      short loc_14000FA2E
0x14000f9f6  mov     rax, [rdx+0E0h]
0x14000f9fd  mov     [rcx+80h], rax
0x14000fa04  jmp     short loc_14000FA2E
0x14000fa06  cmp     eax, 202h
0x14000fa0b  jz      short loc_14000FA17
0x14000fa0d  xor     r8d, r8d
0x14000fa10  cmp     eax, 210h
0x14000fa15  jnz     short loc_14000FA2E
0x14000fa17  mov     r8d, [rdx+1Ch]
0x14000fa1b  test    r8d, r8d
0x14000fa1e  js      short loc_14000FA2E
0x14000fa20  mov     rcx, [rdx+0B0h]
0x14000fa27  mov     [r9+80h], rcx
0x14000fa2e  mov     eax, r8d
0x14000fa31  retn
```
