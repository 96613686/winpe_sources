# FlushEventEntryList

- ea: `0x1800728d4`
- end: `0x180072964`
- name: `FlushEventEntryList`
- size: `144`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007296c`

## callees

- `0x18007284c`
- `0x1800728d4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18007293a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18007293a`

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
      EventWriteTransfer(RegHandle, v2, 0, 0, BYTE4(v2[2].Keyword), *(PEVENT_DATA_DESCRIPTOR *)&v2[1].Id);
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
0x1800728d4  test    rdx, rdx
0x1800728d7  jz      locret_180072963
0x1800728dd  mov     [rsp+arg_0], rbx
0x1800728e2  mov     [rsp+arg_8], rsi
0x1800728e7  push    rdi
0x1800728e8  sub     rsp, 30h
0x1800728ec  mov     rdi, rdx
0x1800728ef  mov     rsi, rcx
0x1800728f2  movzx   eax, byte ptr [rdi+2Dh]
0x1800728f6  mov     edx, 2
0x1800728fb  add     eax, edx
0x1800728fd  cmp     eax, edx
0x1800728ff  jbe     short loc_18007291D
0x180072901  mov     rax, [rdi+10h]
0x180072905  movsxd  rcx, edx
0x180072908  inc     edx
0x18007290a  add     rcx, rcx
0x18007290d  mov     byte ptr [rax+rcx*8+0Dh], 0
0x180072912  movzx   eax, byte ptr [rdi+2Dh]
0x180072916  add     eax, 2
0x180072919  cmp     edx, eax
0x18007291b  jl      short loc_180072901
0x18007291d  movzx   edx, byte ptr [rdi+2Ch]
0x180072921  xor     r9d, r9d; RelatedActivityId
0x180072924  mov     rax, [rdi+10h]
0x180072928  xor     r8d, r8d; ActivityId
0x18007292b  mov     [rsp+38h+UserData], rax; UserData
0x180072930  mov     rcx, rsi; RegHandle
0x180072933  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x180072937  mov     rdx, rdi; EventDescriptor
0x18007293a  call    cs:__imp_EventWriteTransfer
0x180072940  mov     rbx, [rdi+18h]
0x180072944  mov     rcx, rdi
0x180072947  call    DestroyEventEntry
0x18007294c  mov     rdi, rbx
0x18007294f  test    rbx, rbx
0x180072952  jnz     short loc_1800728F2
0x180072954  mov     rbx, [rsp+38h+arg_0]
0x180072959  mov     rsi, [rsp+38h+arg_8]
0x18007295e  add     rsp, 30h
0x180072962  pop     rdi
0x180072963  retn
```
