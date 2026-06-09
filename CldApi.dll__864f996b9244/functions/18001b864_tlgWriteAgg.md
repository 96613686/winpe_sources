# _tlgWriteAgg

- ea: `0x18001b864`
- end: `0x18001b9a9`
- name: `_tlgWriteAgg`
- size: `325`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180011e18`
- `0x180017728`
- `0x180019384`

## callees

- `0x1800022fa`
- `0x18001ace0`
- `0x18001b864`

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
  ULONGLONG v7; // rax
  unsigned __int16 *v8; // rdx
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v11; // r9
  unsigned __int64 v12; // r10
  char *v13; // rcx
  char v14; // al
  char v17; // al
  char v18; // dl
  __int64 v19; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  v6 = (int)UserData;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v7 = *(_QWORD *)(a2 + 3);
  v8 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v7;
  UserData->Ptr = (ULONGLONG)off_1800281A8;
  UserData->Size = *(unsigned __int16 *)off_1800281A8;
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v8;
  UserData[1].Size = *v8;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_1800281C8 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v11 = 0;
    v12 = Ptr + UserData[1].Size;
    v13 = (char *)(Ptr + 2);
    do
      v14 = *v13++;
    while ( v14 < 0 );
    while ( *v13++ )
      ;
    while ( (unsigned __int64)v13 < v12 )
    {
      while ( *v13++ )
        ;
      if ( *v13 >= 0 )
        break;
      v17 = *v13 & 0x7F;
      if ( v13[1] >= 0 )
        break;
      for ( v13 += 2; ; ++v13 )
      {
        v18 = *v13;
        if ( *v13 >= 0 )
          break;
        if ( v18 != (char)0x80 )
          goto LABEL_17;
      }
      if ( v17 != 9 || (unsigned __int8)(v18 - 113) > 2u )
        break;
      v19 = v11++;
      UserData[v19 + 2].Reserved1 = v18;
    }
LABEL_17:
    if ( v11 )
    {
      LOBYTE(v6) = a4;
      return InsertEventEntryInLookUpTable((_DWORD)v13, (unsigned int)&EventDescriptor, v6, (_DWORD)UserData, v11);
    }
    else
    {
      return EventWriteTransfer_0(RegHandle, &EventDescriptor, 0, 0, a4, UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b864  mov     [rsp+arg_10], r8
0x18001b869  sub     rsp, 48h
0x18001b86d  movzx   eax, byte ptr [rdx]
0x18001b870  mov     r11d, r9d
0x18001b873  mov     r8, [rsp+48h+arg_20]
0x18001b878  shl     eax, 18h
0x18001b87b  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18001b87f  movzx   eax, word ptr [rdx+1]
0x18001b883  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18001b887  mov     rax, [rdx+3]
0x18001b88b  add     rdx, 0Bh
0x18001b88f  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18001b894  mov     rax, cs:off_1800281A8
0x18001b89b  mov     [r8], rax
0x18001b89e  mov     rax, cs:off_1800281A8
0x18001b8a5  movzx   ecx, word ptr [rax]
0x18001b8a8  mov     [r8+8], ecx
0x18001b8ac  lea     rcx, _TraceLoggingMetadata
0x18001b8b3  mov     dword ptr [r8+0Ch], 2
0x18001b8bb  mov     [r8+10h], rdx
0x18001b8bf  movzx   eax, word ptr [rdx]
0x18001b8c2  mov     [r8+18h], eax
0x18001b8c6  lea     rax, _TraceLoggingMetadataEnd
0x18001b8cd  sub     eax, ecx
0x18001b8cf  mov     dword ptr [r8+1Ch], 1
0x18001b8d7  mov     dword ptr [rsp+48h+arg_10], eax
0x18001b8db  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18001b8e2  mov     eax, dword ptr [rsp+48h+arg_10]
0x18001b8e6  cmp     cs:qword_1800281C8, rcx
0x18001b8ed  mov     eax, 0C000000Dh
0x18001b8f2  jnz     loc_18001B9A4
0x18001b8f8  mov     rax, [r8+10h]
0x18001b8fc  xor     r9b, r9b
0x18001b8ff  mov     r10d, [r8+18h]
0x18001b903  add     r10, rax
0x18001b906  lea     rcx, [rax+2]
0x18001b90a  movzx   eax, byte ptr [rcx]
0x18001b90d  inc     rcx
0x18001b910  test    al, al
0x18001b912  js      short loc_18001B90A
0x18001b914  mov     al, [rcx]
0x18001b916  inc     rcx
0x18001b919  test    al, al
0x18001b91b  jnz     short loc_18001B914
0x18001b91d  jmp     short loc_18001B964
0x18001b91f  mov     al, [rcx]
0x18001b921  inc     rcx
0x18001b924  test    al, al
0x18001b926  jnz     short loc_18001B91F
0x18001b928  mov     al, [rcx]
0x18001b92a  test    al, al
0x18001b92c  jns     short loc_18001B969
0x18001b92e  and     al, 7Fh
0x18001b930  cmp     byte ptr [rcx+1], 0
0x18001b934  jge     short loc_18001B969
0x18001b936  add     rcx, 2
0x18001b93a  jmp     short loc_18001B944
0x18001b93c  cmp     dl, 80h
0x18001b93f  jnz     short loc_18001B969
0x18001b941  inc     rcx
0x18001b944  mov     dl, [rcx]
0x18001b946  test    dl, dl
0x18001b948  js      short loc_18001B93C
0x18001b94a  cmp     al, 9
0x18001b94c  jnz     short loc_18001B969
0x18001b94e  lea     eax, [rdx-71h]
0x18001b951  cmp     al, 2
0x18001b953  ja      short loc_18001B969
0x18001b955  movzx   eax, r9b
0x18001b959  add     rax, rax
0x18001b95c  inc     r9b
0x18001b95f  mov     [r8+rax*8+2Dh], dl
0x18001b964  cmp     rcx, r10
0x18001b967  jb      short loc_18001B91F
0x18001b969  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18001b96e  test    r9b, r9b
0x18001b971  jz      short loc_18001B985
0x18001b973  mov     byte ptr [rsp+48h+UserDataCount], r9b
0x18001b978  mov     r9, r8
0x18001b97b  mov     r8b, r11b
0x18001b97e  call    InsertEventEntryInLookUpTable
0x18001b983  jmp     short loc_18001B9A4
0x18001b985  mov     rcx, cs:RegHandle; RegHandle
0x18001b98c  xor     r9d, r9d; RelatedActivityId
0x18001b98f  mov     [rsp+48h+UserData], r8; UserData
0x18001b994  xor     r8d, r8d; ActivityId
0x18001b997  movzx   eax, r11b
0x18001b99b  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18001b99f  call    EventWriteTransfer_0
0x18001b9a4  add     rsp, 48h
0x18001b9a8  retn
```
