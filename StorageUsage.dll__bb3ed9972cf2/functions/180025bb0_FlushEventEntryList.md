# FlushEventEntryList

- ea: `0x180025bb0`
- end: `0x180025c3f`
- name: `FlushEventEntryList`
- size: `143`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025c48`

## callees

- `0x180005d7c`
- `0x180025b28`
- `0x180025bb0`

## pseudocode

```c
__int64 __fastcall FlushEventEntryList(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)
{
  PCEVENT_DESCRIPTOR v2; // rdi
  int v4; // edx
  __int64 v5; // rcx
  const EVENT_DESCRIPTOR *Keyword; // rbx
  __int64 result; // rax

  if ( EventDescriptor )
  {
    v2 = EventDescriptor;
    do
    {
      v4 = 2;
      if ( (unsigned int)BYTE5(v2[2].Keyword) + 2 > 2 )
      {
        do
        {
          v5 = v4++;
          *(_BYTE *)(*(_QWORD *)&v2[1].Id + 16 * v5 + 13) = 0;
        }
        while ( v4 < BYTE5(v2[2].Keyword) + 2 );
      }
      EventWriteTransfer_0(RegHandle, v2, 0, 0, BYTE4(v2[2].Keyword), *(PEVENT_DATA_DESCRIPTOR *)&v2[1].Id);
      Keyword = (const EVENT_DESCRIPTOR *)v2[1].Keyword;
      result = DestroyEventEntry(v2);
      v2 = Keyword;
    }
    while ( Keyword );
  }
  return result;
}

```

## disassembly

```asm
0x180025bb0  test    rdx, rdx
0x180025bb3  jz      locret_180025C3E
0x180025bb9  mov     [rsp+arg_0], rbx
0x180025bbe  mov     [rsp+arg_8], rsi
0x180025bc3  push    rdi
0x180025bc4  sub     rsp, 30h
0x180025bc8  mov     rdi, rdx
0x180025bcb  mov     rsi, rcx
0x180025bce  movzx   eax, byte ptr [rdi+2Dh]
0x180025bd2  mov     edx, 2
0x180025bd7  add     eax, edx
0x180025bd9  cmp     eax, edx
0x180025bdb  jbe     short loc_180025BF9
0x180025bdd  mov     rax, [rdi+10h]
0x180025be1  movsxd  rcx, edx
0x180025be4  inc     edx
0x180025be6  add     rcx, rcx
0x180025be9  mov     byte ptr [rax+rcx*8+0Dh], 0
0x180025bee  movzx   eax, byte ptr [rdi+2Dh]
0x180025bf2  add     eax, 2
0x180025bf5  cmp     edx, eax
0x180025bf7  jl      short loc_180025BDD
0x180025bf9  movzx   edx, byte ptr [rdi+2Ch]
0x180025bfd  xor     r9d, r9d; RelatedActivityId
0x180025c00  mov     rax, [rdi+10h]
0x180025c04  xor     r8d, r8d; ActivityId
0x180025c07  mov     [rsp+38h+UserData], rax; UserData
0x180025c0c  mov     rcx, rsi; RegHandle
0x180025c0f  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x180025c13  mov     rdx, rdi; EventDescriptor
0x180025c16  call    EventWriteTransfer_0
0x180025c1b  mov     rbx, [rdi+18h]
0x180025c1f  mov     rcx, rdi
0x180025c22  call    DestroyEventEntry
0x180025c27  mov     rdi, rbx
0x180025c2a  test    rbx, rbx
0x180025c2d  jnz     short loc_180025BCE
0x180025c2f  mov     rbx, [rsp+38h+arg_0]
0x180025c34  mov     rsi, [rsp+38h+arg_8]
0x180025c39  add     rsp, 30h
0x180025c3d  pop     rdi
0x180025c3e  retn
```
