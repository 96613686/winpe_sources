# TlgAggregateAbsorbEvent

- ea: `0x180011014`
- end: `0x1800110fd`
- name: `TlgAggregateAbsorbEvent`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010f80`

## callees

- `0x180011014`
- `0x180011104`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800110e5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800110e5`

## pseudocode

```c
ULONG __fastcall TlgAggregateAbsorbEvent(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        unsigned __int8 a3,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  ULONG UserDataCount; // ebx
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v8; // r10
  unsigned __int64 v9; // r11
  char *v10; // rcx
  char v11; // al
  char v14; // r8
  char *v15; // rax
  char v16; // dl
  __int64 v17; // rax

  UserDataCount = a3;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180024078 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v8 = 0;
    v9 = Ptr + UserData[1].Size;
    v10 = (char *)(Ptr + 2);
    do
      v11 = *v10++;
    while ( v11 < 0 );
    while ( *v10++ )
      ;
    while ( (unsigned __int64)v10 < v9 )
    {
      while ( *v10++ )
        ;
      if ( *v10 >= 0 )
        break;
      v14 = *v10 & 0x7F;
      v15 = v10 + 1;
      v10 += 2;
      if ( *v15 >= 0 )
        break;
      while ( 1 )
      {
        v16 = *v10;
        if ( *v10 >= 0 )
          break;
        if ( v16 != (char)0x80 )
          goto LABEL_15;
        ++v10;
      }
      if ( v14 != 9 || (unsigned __int8)(v16 - 113) > 2u )
        break;
      v17 = v8++;
      UserData[v17 + 2].Reserved1 = v16;
    }
LABEL_15:
    if ( v8 )
      return InsertEventEntryInLookUpTable((_DWORD)v10, (_DWORD)a2, (_BYTE)UserDataCount, (_DWORD)UserData, v8);
    else
      return EventWriteTransfer(RegHandle, a2, 0, 0, UserDataCount, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x180011014  mov     [rsp+arg_0], rbx
0x180011019  push    rdi
0x18001101a  sub     rsp, 30h
0x18001101e  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180011025  movzx   ebx, r8b
0x180011029  cmp     cs:qword_180024078, rcx
0x180011030  mov     rdi, rdx
0x180011033  mov     eax, 0C000000Dh
0x180011038  jnz     loc_1800110F1
0x18001103e  mov     rax, [r9+10h]
0x180011042  xor     r10b, r10b
0x180011045  mov     r11d, [r9+18h]
0x180011049  add     r11, rax
0x18001104c  lea     rcx, [rax+2]
0x180011050  movzx   eax, byte ptr [rcx]
0x180011053  inc     rcx
0x180011056  test    al, al
0x180011058  js      short loc_180011050
0x18001105a  mov     al, [rcx]
0x18001105c  inc     rcx
0x18001105f  test    al, al
0x180011061  jnz     short loc_18001105A
0x180011063  cmp     rcx, r11
0x180011066  jnb     short loc_1800110B8
0x180011068  mov     al, [rcx]
0x18001106a  inc     rcx
0x18001106d  test    al, al
0x18001106f  jnz     short loc_180011068
0x180011071  mov     r8b, [rcx]
0x180011074  test    r8b, r8b
0x180011077  jns     short loc_1800110B8
0x180011079  and     r8b, 7Fh
0x18001107d  lea     rax, [rcx+1]
0x180011081  add     rcx, 2
0x180011085  cmp     byte ptr [rax], 0
0x180011088  jge     short loc_1800110B8
0x18001108a  mov     dl, [rcx]
0x18001108c  test    dl, dl
0x18001108e  jns     short loc_18001109A
0x180011090  cmp     dl, 80h
0x180011093  jnz     short loc_1800110B8
0x180011095  inc     rcx
0x180011098  jmp     short loc_18001108A
0x18001109a  cmp     r8b, 9
0x18001109e  jnz     short loc_1800110B8
0x1800110a0  lea     eax, [rdx-71h]
0x1800110a3  cmp     al, 2
0x1800110a5  ja      short loc_1800110B8
0x1800110a7  movzx   eax, r10b
0x1800110ab  add     rax, rax
0x1800110ae  inc     r10b
0x1800110b1  mov     [r9+rax*8+2Dh], dl
0x1800110b6  jmp     short loc_180011063
0x1800110b8  mov     rdx, rdi; EventDescriptor
0x1800110bb  test    r10b, r10b
0x1800110be  jz      short loc_1800110CF
0x1800110c0  mov     r8b, bl
0x1800110c3  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x1800110c8  call    InsertEventEntryInLookUpTable
0x1800110cd  jmp     short loc_1800110F1
0x1800110cf  mov     rcx, cs:RegHandle; RegHandle
0x1800110d6  xor     r8d, r8d; ActivityId
0x1800110d9  mov     [rsp+38h+UserData], r9; UserData
0x1800110de  xor     r9d, r9d; RelatedActivityId
0x1800110e1  mov     [rsp+38h+UserDataCount], ebx; UserDataCount
0x1800110e5  call    cs:__imp_EventWriteTransfer
0x1800110ec  nop     dword ptr [rax+rax+00h]
0x1800110f1  mov     rbx, [rsp+38h+arg_0]
0x1800110f6  add     rsp, 30h
0x1800110fa  pop     rdi
0x1800110fb  retn
```
