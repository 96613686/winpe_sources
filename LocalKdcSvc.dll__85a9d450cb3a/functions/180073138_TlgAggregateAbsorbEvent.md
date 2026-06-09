# TlgAggregateAbsorbEvent

- ea: `0x180073138`
- end: `0x180073224`
- name: `TlgAggregateAbsorbEvent`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007352c`

## callees

- `0x180072a80`
- `0x180073138`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18007320e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18007320e`

## pseudocode

```c
ULONG __fastcall TlgAggregateAbsorbEvent(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        unsigned __int8 a3,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  ULONG UserDataCount; // edi
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v9; // r10
  unsigned __int64 v10; // rbx
  char *v11; // rcx
  char v12; // al
  char v15; // r8
  char *v16; // rax
  char v17; // dl
  __int64 v18; // rax

  UserDataCount = a3;
  result = -1073741811;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v9 = 0;
    v10 = Ptr + UserData[1].Size;
    v11 = (char *)(Ptr + 2);
    do
      v12 = *v11++;
    while ( v12 < 0 );
    while ( *v11++ )
      ;
    while ( (unsigned __int64)v11 < v10 )
    {
      while ( *v11++ )
        ;
      if ( *v11 >= 0 )
        break;
      v15 = *v11 & 0x7F;
      v16 = v11 + 1;
      v11 += 2;
      if ( *v16 >= 0 )
        break;
      while ( 1 )
      {
        v17 = *v11;
        if ( *v11 >= 0 )
          break;
        if ( v17 != (char)0x80 )
          goto LABEL_15;
        ++v11;
      }
      if ( v15 != 9 || (unsigned __int8)(v17 - 113) > 2u )
        break;
      v18 = v9++;
      UserData[v18 + 2].Reserved1 = v17;
    }
LABEL_15:
    if ( v9 )
      return InsertEventEntryInLookUpTable(a1, (_DWORD)a2, (_BYTE)UserDataCount, (_DWORD)UserData, v9);
    else
      return EventWriteTransfer(*(_QWORD *)(a1 + 32), a2, 0, 0, UserDataCount, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x180073138  mov     [rsp+arg_0], rbx
0x18007313d  mov     [rsp+arg_8], rsi
0x180073142  push    rdi
0x180073143  sub     rsp, 30h
0x180073147  mov     r11, rcx
0x18007314a  movzx   edi, r8b
0x18007314e  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180073155  mov     rsi, rdx
0x180073158  mov     eax, 0C000000Dh
0x18007315d  cmp     [r11+28h], rcx
0x180073161  jnz     loc_180073214
0x180073167  mov     rax, [r9+10h]
0x18007316b  xor     r10b, r10b
0x18007316e  mov     ebx, [r9+18h]
0x180073172  add     rbx, rax
0x180073175  lea     rcx, [rax+2]
0x180073179  movzx   eax, byte ptr [rcx]
0x18007317c  inc     rcx
0x18007317f  test    al, al
0x180073181  js      short loc_180073179
0x180073183  mov     al, [rcx]
0x180073185  inc     rcx
0x180073188  test    al, al
0x18007318a  jnz     short loc_180073183
0x18007318c  cmp     rcx, rbx
0x18007318f  jnb     short loc_1800731E1
0x180073191  mov     al, [rcx]
0x180073193  inc     rcx
0x180073196  test    al, al
0x180073198  jnz     short loc_180073191
0x18007319a  mov     r8b, [rcx]
0x18007319d  test    r8b, r8b
0x1800731a0  jns     short loc_1800731E1
0x1800731a2  and     r8b, 7Fh
0x1800731a6  lea     rax, [rcx+1]
0x1800731aa  add     rcx, 2
0x1800731ae  cmp     byte ptr [rax], 0
0x1800731b1  jge     short loc_1800731E1
0x1800731b3  mov     dl, [rcx]
0x1800731b5  test    dl, dl
0x1800731b7  jns     short loc_1800731C3
0x1800731b9  cmp     dl, 80h
0x1800731bc  jnz     short loc_1800731E1
0x1800731be  inc     rcx
0x1800731c1  jmp     short loc_1800731B3
0x1800731c3  cmp     r8b, 9
0x1800731c7  jnz     short loc_1800731E1
0x1800731c9  lea     eax, [rdx-71h]
0x1800731cc  cmp     al, 2
0x1800731ce  ja      short loc_1800731E1
0x1800731d0  movzx   eax, r10b
0x1800731d4  add     rax, rax
0x1800731d7  inc     r10b
0x1800731da  mov     [r9+rax*8+2Dh], dl
0x1800731df  jmp     short loc_18007318C
0x1800731e1  mov     rdx, rsi; EventDescriptor
0x1800731e4  test    r10b, r10b
0x1800731e7  jz      short loc_1800731FB
0x1800731e9  mov     r8b, dil
0x1800731ec  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x1800731f1  mov     rcx, r11
0x1800731f4  call    InsertEventEntryInLookUpTable
0x1800731f9  jmp     short loc_180073214
0x1800731fb  mov     rcx, [r11+20h]; RegHandle
0x1800731ff  xor     r8d, r8d; ActivityId
0x180073202  mov     [rsp+38h+UserData], r9; UserData
0x180073207  xor     r9d, r9d; RelatedActivityId
0x18007320a  mov     [rsp+38h+UserDataCount], edi; UserDataCount
0x18007320e  call    cs:__imp_EventWriteTransfer
0x180073214  mov     rbx, [rsp+38h+arg_0]
0x180073219  mov     rsi, [rsp+38h+arg_8]
0x18007321e  add     rsp, 30h
0x180073222  pop     rdi
0x180073223  retn
```
