# FlushEventEntryList

- ea: `0x18001af80`
- end: `0x18001b017`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011e24`

## callees

- `0x18001af44`
- `0x18001af80`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001afe6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001afe6`

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
0x18001af80  test    rdx, rdx
0x18001af83  jz      locret_18001B015
0x18001af89  mov     [rsp+arg_0], rbx
0x18001af8e  mov     [rsp+arg_8], rsi
0x18001af93  push    rdi
0x18001af94  sub     rsp, 30h
0x18001af98  mov     rdi, rdx
0x18001af9b  mov     rsi, rcx
0x18001af9e  movzx   eax, byte ptr [rdi+2Dh]
0x18001afa2  mov     edx, 2
0x18001afa7  add     eax, edx
0x18001afa9  cmp     eax, edx
0x18001afab  jbe     short loc_18001AFC9
0x18001afad  mov     rax, [rdi+10h]
0x18001afb1  movsxd  rcx, edx
0x18001afb4  inc     edx
0x18001afb6  add     rcx, rcx
0x18001afb9  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18001afbe  movzx   eax, byte ptr [rdi+2Dh]
0x18001afc2  add     eax, 2
0x18001afc5  cmp     edx, eax
0x18001afc7  jl      short loc_18001AFAD
0x18001afc9  movzx   edx, byte ptr [rdi+2Ch]
0x18001afcd  xor     r9d, r9d; RelatedActivityId
0x18001afd0  mov     rax, [rdi+10h]
0x18001afd4  xor     r8d, r8d; ActivityId
0x18001afd7  mov     [rsp+38h+UserData], rax; UserData
0x18001afdc  mov     rcx, rsi; RegHandle
0x18001afdf  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18001afe3  mov     rdx, rdi; EventDescriptor
0x18001afe6  call    cs:__imp_EventWriteTransfer
0x18001afed  nop     dword ptr [rax+rax+00h]
0x18001aff2  mov     rbx, [rdi+18h]
0x18001aff6  mov     rcx, rdi
0x18001aff9  call    DestroyEventEntry
0x18001affe  mov     rdi, rbx
0x18001b001  test    rbx, rbx
0x18001b004  jnz     short loc_18001AF9E
0x18001b006  mov     rbx, [rsp+38h+arg_0]
0x18001b00b  mov     rsi, [rsp+38h+arg_8]
0x18001b010  add     rsp, 30h
0x18001b014  pop     rdi
0x18001b015  retn
```
