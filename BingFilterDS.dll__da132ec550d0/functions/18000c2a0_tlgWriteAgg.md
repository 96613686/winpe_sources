# _tlgWriteAgg

- ea: `0x18000c2a0`
- end: `0x18000c3dc`
- name: `_tlgWriteAgg`
- size: `316`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, unsigned __int8, struct _EVENT_DATA_DESCRIPTOR *UserData)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008e50`

## callees

- `0x180002b86`
- `0x18000b870`
- `0x18000c2a0`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  int v6; // r8d
  ULONGLONG v8; // rax
  unsigned __int16 *v9; // rdx
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v12; // r9
  unsigned __int64 v13; // r10
  char *v14; // rcx
  char v15; // al
  char v18; // al
  char v19; // dl
  __int64 v20; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  v6 = (int)UserData;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v8 = *(_QWORD *)(a2 + 3);
  v9 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v8;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v9;
  UserData[1].Size = *v9;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( *(void (__fastcall **)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v12 = 0;
    v13 = Ptr + UserData[1].Size;
    v14 = (char *)(Ptr + 2);
    do
      v15 = *v14++;
    while ( v15 < 0 );
    while ( *v14++ )
      ;
    while ( (unsigned __int64)v14 < v13 )
    {
      while ( *v14++ )
        ;
      if ( *v14 >= 0 )
        break;
      v18 = *v14 & 0x7F;
      if ( v14[1] >= 0 )
        break;
      for ( v14 += 2; ; ++v14 )
      {
        v19 = *v14;
        if ( *v14 >= 0 )
          break;
        if ( v19 != (char)0x80 )
          goto LABEL_17;
      }
      if ( v18 != 9 || (unsigned __int8)(v19 - 113) > 2u )
        break;
      v20 = v12++;
      UserData[v20 + 2].Reserved1 = v19;
    }
LABEL_17:
    if ( v12 )
    {
      LOBYTE(v6) = a4;
      return InsertEventEntryInLookUpTable(a1, (unsigned int)&EventDescriptor, v6, (_DWORD)UserData, v12);
    }
    else
    {
      return EventWriteTransfer_0(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c2a0  push    rbx
0x18000c2a2  sub     rsp, 40h
0x18000c2a6  movzx   eax, byte ptr [rdx]
0x18000c2a9  mov     r11, rcx
0x18000c2ac  mov     r8, [rsp+48h+arg_20]
0x18000c2b1  mov     ebx, r9d
0x18000c2b4  shl     eax, 18h
0x18000c2b7  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000c2bb  movzx   eax, word ptr [rdx+1]
0x18000c2bf  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000c2c3  mov     rax, [rdx+3]
0x18000c2c7  add     rdx, 0Bh
0x18000c2cb  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000c2d0  mov     rax, [rcx+8]
0x18000c2d4  mov     [r8], rax
0x18000c2d7  mov     rax, [rcx+8]
0x18000c2db  movzx   ecx, word ptr [rax]
0x18000c2de  mov     [r8+8], ecx
0x18000c2e2  lea     rcx, _TraceLoggingMetadata
0x18000c2e9  mov     dword ptr [r8+0Ch], 2
0x18000c2f1  mov     [r8+10h], rdx
0x18000c2f5  movzx   eax, word ptr [rdx]
0x18000c2f8  mov     [r8+18h], eax
0x18000c2fc  lea     rax, _TraceLoggingMetadataEnd
0x18000c303  sub     eax, ecx
0x18000c305  mov     dword ptr [r8+1Ch], 1
0x18000c30d  mov     dword ptr [rsp+48h+arg_20], eax
0x18000c311  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000c318  mov     eax, dword ptr [rsp+48h+arg_20]
0x18000c31c  mov     eax, 0C000000Dh
0x18000c321  cmp     [r11+28h], rcx
0x18000c325  jnz     loc_18000C3D6
0x18000c32b  mov     rax, [r8+10h]
0x18000c32f  xor     r9b, r9b
0x18000c332  mov     r10d, [r8+18h]
0x18000c336  add     r10, rax
0x18000c339  lea     rcx, [rax+2]
0x18000c33d  movzx   eax, byte ptr [rcx]
0x18000c340  inc     rcx
0x18000c343  test    al, al
0x18000c345  js      short loc_18000C33D
0x18000c347  mov     al, [rcx]
0x18000c349  inc     rcx
0x18000c34c  test    al, al
0x18000c34e  jnz     short loc_18000C347
0x18000c350  jmp     short loc_18000C397
0x18000c352  mov     al, [rcx]
0x18000c354  inc     rcx
0x18000c357  test    al, al
0x18000c359  jnz     short loc_18000C352
0x18000c35b  mov     al, [rcx]
0x18000c35d  test    al, al
0x18000c35f  jns     short loc_18000C39C
0x18000c361  and     al, 7Fh
0x18000c363  cmp     byte ptr [rcx+1], 0
0x18000c367  jge     short loc_18000C39C
0x18000c369  add     rcx, 2
0x18000c36d  jmp     short loc_18000C377
0x18000c36f  cmp     dl, 80h
0x18000c372  jnz     short loc_18000C39C
0x18000c374  inc     rcx
0x18000c377  mov     dl, [rcx]
0x18000c379  test    dl, dl
0x18000c37b  js      short loc_18000C36F
0x18000c37d  cmp     al, 9
0x18000c37f  jnz     short loc_18000C39C
0x18000c381  lea     eax, [rdx-71h]
0x18000c384  cmp     al, 2
0x18000c386  ja      short loc_18000C39C
0x18000c388  movzx   eax, r9b
0x18000c38c  add     rax, rax
0x18000c38f  inc     r9b
0x18000c392  mov     [r8+rax*8+2Dh], dl
0x18000c397  cmp     rcx, r10
0x18000c39a  jb      short loc_18000C352
0x18000c39c  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000c3a1  test    r9b, r9b
0x18000c3a4  jz      short loc_18000C3BB
0x18000c3a6  mov     byte ptr [rsp+48h+UserDataCount], r9b
0x18000c3ab  mov     rcx, r11
0x18000c3ae  mov     r9, r8
0x18000c3b1  mov     r8b, bl
0x18000c3b4  call    InsertEventEntryInLookUpTable
0x18000c3b9  jmp     short loc_18000C3D6
0x18000c3bb  mov     rcx, [r11+20h]; RegHandle
0x18000c3bf  xor     r9d, r9d; RelatedActivityId
0x18000c3c2  mov     [rsp+48h+UserData], r8; UserData
0x18000c3c7  xor     r8d, r8d; ActivityId
0x18000c3ca  movzx   eax, bl
0x18000c3cd  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000c3d1  call    EventWriteTransfer_0
0x18000c3d6  add     rsp, 40h
0x18000c3da  pop     rbx
0x18000c3db  retn
```
