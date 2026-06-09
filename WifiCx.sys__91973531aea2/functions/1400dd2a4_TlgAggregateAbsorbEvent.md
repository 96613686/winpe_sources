# TlgAggregateAbsorbEvent

- ea: `0x1400dd2a4`
- end: `0x1400dd397`
- name: `TlgAggregateAbsorbEvent`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400dd3e4`

## callees

- `0x1400237e4`
- `0x1400dd2a4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400dd37a`
- `ntoskrnl!EtwWriteTransfer` at `0x1400dd37a`

## pseudocode

```c
NTSTATUS __fastcall TlgAggregateAbsorbEvent(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        unsigned __int8 a3,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  ULONG UserDataCount; // edi
  NTSTATUS result; // eax
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
      return EtwWriteTransfer(*(_QWORD *)(a1 + 32), a2, 0, 0, UserDataCount, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1400dd2a4  mov     [rsp+arg_0], rbx
0x1400dd2a9  mov     [rsp+arg_8], rsi
0x1400dd2ae  push    rdi
0x1400dd2af  sub     rsp, 30h
0x1400dd2b3  mov     r11, rcx
0x1400dd2b6  movzx   edi, r8b
0x1400dd2ba  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x1400dd2c1  mov     rsi, rdx
0x1400dd2c4  mov     eax, 0C000000Dh
0x1400dd2c9  cmp     [r11+28h], rcx
0x1400dd2cd  jnz     loc_1400DD386
0x1400dd2d3  mov     rax, [r9+10h]
0x1400dd2d7  xor     r10b, r10b
0x1400dd2da  mov     ebx, [r9+18h]
0x1400dd2de  add     rbx, rax
0x1400dd2e1  lea     rcx, [rax+2]
0x1400dd2e5  movzx   eax, byte ptr [rcx]
0x1400dd2e8  inc     rcx
0x1400dd2eb  test    al, al
0x1400dd2ed  js      short loc_1400DD2E5
0x1400dd2ef  mov     al, [rcx]
0x1400dd2f1  inc     rcx
0x1400dd2f4  test    al, al
0x1400dd2f6  jnz     short loc_1400DD2EF
0x1400dd2f8  cmp     rcx, rbx
0x1400dd2fb  jnb     short loc_1400DD34D
0x1400dd2fd  mov     al, [rcx]
0x1400dd2ff  inc     rcx
0x1400dd302  test    al, al
0x1400dd304  jnz     short loc_1400DD2FD
0x1400dd306  mov     r8b, [rcx]
0x1400dd309  test    r8b, r8b
0x1400dd30c  jns     short loc_1400DD34D
0x1400dd30e  and     r8b, 7Fh
0x1400dd312  lea     rax, [rcx+1]
0x1400dd316  add     rcx, 2
0x1400dd31a  cmp     byte ptr [rax], 0
0x1400dd31d  jge     short loc_1400DD34D
0x1400dd31f  mov     dl, [rcx]
0x1400dd321  test    dl, dl
0x1400dd323  jns     short loc_1400DD32F
0x1400dd325  cmp     dl, 80h
0x1400dd328  jnz     short loc_1400DD34D
0x1400dd32a  inc     rcx
0x1400dd32d  jmp     short loc_1400DD31F
0x1400dd32f  cmp     r8b, 9
0x1400dd333  jnz     short loc_1400DD34D
0x1400dd335  lea     eax, [rdx-71h]
0x1400dd338  cmp     al, 2
0x1400dd33a  ja      short loc_1400DD34D
0x1400dd33c  movzx   eax, r10b
0x1400dd340  add     rax, rax
0x1400dd343  inc     r10b
0x1400dd346  mov     [r9+rax*8+2Dh], dl
0x1400dd34b  jmp     short loc_1400DD2F8
0x1400dd34d  mov     rdx, rsi; EventDescriptor
0x1400dd350  test    r10b, r10b
0x1400dd353  jz      short loc_1400DD367
0x1400dd355  mov     r8b, dil
0x1400dd358  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x1400dd35d  mov     rcx, r11
0x1400dd360  call    InsertEventEntryInLookUpTable
0x1400dd365  jmp     short loc_1400DD386
0x1400dd367  mov     rcx, [r11+20h]; RegHandle
0x1400dd36b  xor     r8d, r8d; ActivityId
0x1400dd36e  mov     [rsp+38h+UserData], r9; UserData
0x1400dd373  xor     r9d, r9d; RelatedActivityId
0x1400dd376  mov     [rsp+38h+UserDataCount], edi; UserDataCount
0x1400dd37a  call    cs:__imp_EtwWriteTransfer
0x1400dd381  nop     dword ptr [rax+rax+00h]
0x1400dd386  mov     rbx, [rsp+38h+arg_0]
0x1400dd38b  mov     rsi, [rsp+38h+arg_8]
0x1400dd390  add     rsp, 30h
0x1400dd394  pop     rdi
0x1400dd395  retn
```
