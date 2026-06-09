# FlushEventEntryList

- ea: `0x140065b28`
- end: `0x140065bbf`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140047b54`

## callees

- `0x140047ab0`
- `0x140065b28`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140065b8e`
- `ntoskrnl!EtwWriteTransfer` at `0x140065b8e`

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
0x140065b28  test    rdx, rdx
0x140065b2b  jz      locret_140065BBD
0x140065b31  mov     [rsp+arg_0], rbx
0x140065b36  mov     [rsp+arg_8], rsi
0x140065b3b  push    rdi
0x140065b3c  sub     rsp, 30h
0x140065b40  mov     rdi, rdx
0x140065b43  mov     rsi, rcx
0x140065b46  movzx   eax, byte ptr [rdi+2Dh]
0x140065b4a  mov     edx, 2
0x140065b4f  add     eax, edx
0x140065b51  cmp     eax, edx
0x140065b53  jbe     short loc_140065B71
0x140065b55  mov     rax, [rdi+10h]
0x140065b59  movsxd  rcx, edx
0x140065b5c  inc     edx
0x140065b5e  add     rcx, rcx
0x140065b61  mov     byte ptr [rax+rcx*8+0Dh], 0
0x140065b66  movzx   eax, byte ptr [rdi+2Dh]
0x140065b6a  add     eax, 2
0x140065b6d  cmp     edx, eax
0x140065b6f  jl      short loc_140065B55
0x140065b71  movzx   edx, byte ptr [rdi+2Ch]
0x140065b75  xor     r9d, r9d; RelatedActivityId
0x140065b78  mov     rax, [rdi+10h]
0x140065b7c  xor     r8d, r8d; ActivityId
0x140065b7f  mov     [rsp+38h+UserData], rax; UserData
0x140065b84  mov     rcx, rsi; RegHandle
0x140065b87  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x140065b8b  mov     rdx, rdi; EventDescriptor
0x140065b8e  call    cs:__imp_EtwWriteTransfer
0x140065b95  nop     dword ptr [rax+rax+00h]
0x140065b9a  mov     rbx, [rdi+18h]
0x140065b9e  mov     rcx, rdi
0x140065ba1  call    DestroyEventEntry
0x140065ba6  mov     rdi, rbx
0x140065ba9  test    rbx, rbx
0x140065bac  jnz     short loc_140065B46
0x140065bae  mov     rbx, [rsp+38h+arg_0]
0x140065bb3  mov     rsi, [rsp+38h+arg_8]
0x140065bb8  add     rsp, 30h
0x140065bbc  pop     rdi
0x140065bbd  retn
```
