# FlushEventEntryList

- ea: `0x14000ee14`
- end: `0x14000eeab`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023b4`

## callees

- `0x140002310`
- `0x14000ee14`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000ee7a`
- `ntoskrnl!EtwWriteTransfer` at `0x14000ee7a`

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
0x14000ee14  test    rdx, rdx
0x14000ee17  jz      locret_14000EEA9
0x14000ee1d  mov     [rsp+arg_0], rbx
0x14000ee22  mov     [rsp+arg_8], rsi
0x14000ee27  push    rdi
0x14000ee28  sub     rsp, 30h
0x14000ee2c  mov     rdi, rdx
0x14000ee2f  mov     rsi, rcx
0x14000ee32  movzx   eax, byte ptr [rdi+2Dh]
0x14000ee36  mov     edx, 2
0x14000ee3b  add     eax, edx
0x14000ee3d  cmp     eax, edx
0x14000ee3f  jbe     short loc_14000EE5D
0x14000ee41  mov     rax, [rdi+10h]
0x14000ee45  movsxd  rcx, edx
0x14000ee48  inc     edx
0x14000ee4a  add     rcx, rcx
0x14000ee4d  mov     byte ptr [rax+rcx*8+0Dh], 0
0x14000ee52  movzx   eax, byte ptr [rdi+2Dh]
0x14000ee56  add     eax, 2
0x14000ee59  cmp     edx, eax
0x14000ee5b  jl      short loc_14000EE41
0x14000ee5d  movzx   edx, byte ptr [rdi+2Ch]
0x14000ee61  xor     r9d, r9d; RelatedActivityId
0x14000ee64  mov     rax, [rdi+10h]
0x14000ee68  xor     r8d, r8d; ActivityId
0x14000ee6b  mov     [rsp+38h+UserData], rax; UserData
0x14000ee70  mov     rcx, rsi; RegHandle
0x14000ee73  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x14000ee77  mov     rdx, rdi; EventDescriptor
0x14000ee7a  call    cs:__imp_EtwWriteTransfer
0x14000ee81  nop     dword ptr [rax+rax+00h]
0x14000ee86  mov     rbx, [rdi+18h]
0x14000ee8a  mov     rcx, rdi
0x14000ee8d  call    DestroyEventEntry
0x14000ee92  mov     rdi, rbx
0x14000ee95  test    rbx, rbx
0x14000ee98  jnz     short loc_14000EE32
0x14000ee9a  mov     rbx, [rsp+38h+arg_0]
0x14000ee9f  mov     rsi, [rsp+38h+arg_8]
0x14000eea4  add     rsp, 30h
0x14000eea8  pop     rdi
0x14000eea9  retn
```
