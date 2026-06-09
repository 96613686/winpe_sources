# FlushEventEntryList

- ea: `0x140120484`
- end: `0x14012051b`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400dd184`

## callees

- `0x1400dd0fc`
- `0x140120484`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1401204ea`
- `ntoskrnl!EtwWriteTransfer` at `0x1401204ea`

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
      EtwWriteTransfer(RegHandle, v2, 0, 0, BYTE4(v2[2].Keyword), *(PEVENT_DATA_DESCRIPTOR *)&v2[1].Id);
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
0x140120484  test    rdx, rdx
0x140120487  jz      locret_140120519
0x14012048d  mov     [rsp+arg_0], rbx
0x140120492  mov     [rsp+arg_8], rsi
0x140120497  push    rdi
0x140120498  sub     rsp, 30h
0x14012049c  mov     rdi, rdx
0x14012049f  mov     rsi, rcx
0x1401204a2  movzx   eax, byte ptr [rdi+2Dh]
0x1401204a6  mov     edx, 2
0x1401204ab  add     eax, edx
0x1401204ad  cmp     eax, edx
0x1401204af  jbe     short loc_1401204CD
0x1401204b1  mov     rax, [rdi+10h]
0x1401204b5  movsxd  rcx, edx
0x1401204b8  inc     edx
0x1401204ba  add     rcx, rcx
0x1401204bd  mov     byte ptr [rax+rcx*8+0Dh], 0
0x1401204c2  movzx   eax, byte ptr [rdi+2Dh]
0x1401204c6  add     eax, 2
0x1401204c9  cmp     edx, eax
0x1401204cb  jl      short loc_1401204B1
0x1401204cd  movzx   edx, byte ptr [rdi+2Ch]
0x1401204d1  xor     r9d, r9d; RelatedActivityId
0x1401204d4  mov     rax, [rdi+10h]
0x1401204d8  xor     r8d, r8d; ActivityId
0x1401204db  mov     [rsp+38h+UserData], rax; UserData
0x1401204e0  mov     rcx, rsi; RegHandle
0x1401204e3  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x1401204e7  mov     rdx, rdi; EventDescriptor
0x1401204ea  call    cs:__imp_EtwWriteTransfer
0x1401204f1  nop     dword ptr [rax+rax+00h]
0x1401204f6  mov     rbx, [rdi+18h]
0x1401204fa  mov     rcx, rdi
0x1401204fd  call    DestroyEventEntry
0x140120502  mov     rdi, rbx
0x140120505  test    rbx, rbx
0x140120508  jnz     short loc_1401204A2
0x14012050a  mov     rbx, [rsp+38h+arg_0]
0x14012050f  mov     rsi, [rsp+38h+arg_8]
0x140120514  add     rsp, 30h
0x140120518  pop     rdi
0x140120519  retn
```
