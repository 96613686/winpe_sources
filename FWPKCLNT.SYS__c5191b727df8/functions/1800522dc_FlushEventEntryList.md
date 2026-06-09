# FlushEventEntryList

- ea: `0x1800522dc`
- end: `0x180052373`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a0b0`

## callees

- `0x18000a854`
- `0x1800522dc`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x180052342`
- `ntoskrnl!EtwWriteTransfer` at `0x180052342`

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
0x1800522dc  test    rdx, rdx
0x1800522df  jz      locret_180052371
0x1800522e5  mov     [rsp+arg_0], rbx
0x1800522ea  mov     [rsp+arg_8], rsi
0x1800522ef  push    rdi
0x1800522f0  sub     rsp, 30h
0x1800522f4  mov     rdi, rdx
0x1800522f7  mov     rsi, rcx
0x1800522fa  movzx   eax, byte ptr [rdi+2Dh]
0x1800522fe  mov     edx, 2
0x180052303  add     eax, edx
0x180052305  cmp     eax, edx
0x180052307  jbe     short loc_180052325
0x180052309  mov     rax, [rdi+10h]
0x18005230d  movsxd  rcx, edx
0x180052310  inc     edx
0x180052312  add     rcx, rcx
0x180052315  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18005231a  movzx   eax, byte ptr [rdi+2Dh]
0x18005231e  add     eax, 2
0x180052321  cmp     edx, eax
0x180052323  jl      short loc_180052309
0x180052325  movzx   edx, byte ptr [rdi+2Ch]
0x180052329  xor     r9d, r9d; RelatedActivityId
0x18005232c  mov     rax, [rdi+10h]
0x180052330  xor     r8d, r8d; ActivityId
0x180052333  mov     [rsp+38h+UserData], rax; UserData
0x180052338  mov     rcx, rsi; RegHandle
0x18005233b  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18005233f  mov     rdx, rdi; EventDescriptor
0x180052342  call    cs:__imp_EtwWriteTransfer
0x180052349  nop     dword ptr [rax+rax+00h]
0x18005234e  mov     rbx, [rdi+18h]
0x180052352  mov     rcx, rdi
0x180052355  call    DestroyEventEntry
0x18005235a  mov     rdi, rbx
0x18005235d  test    rbx, rbx
0x180052360  jnz     short loc_1800522FA
0x180052362  mov     rbx, [rsp+38h+arg_0]
0x180052367  mov     rsi, [rsp+38h+arg_8]
0x18005236c  add     rsp, 30h
0x180052370  pop     rdi
0x180052371  retn
```
