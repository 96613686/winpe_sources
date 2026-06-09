# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800015f0`
- end: `0x1800016e9`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `249`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, int **, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800283c4`
- `0x18002849c`

## callees

- `0x1800015f0`
- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800016ce`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800016ce`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6)
{
  int *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 *v13; // [rsp+60h] [rbp+7h]
  int v14; // [rsp+68h] [rbp+Fh]
  int v15; // [rsp+6Ch] [rbp+13h]
  int *v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+78h] [rbp+1Fh]
  int v18; // [rsp+7Ch] [rbp+23h]
  __int64 v19; // [rsp+80h] [rbp+27h]
  __int64 v20; // [rsp+88h] [rbp+2Fh]

  v19 = a6;
  v20 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &dword_18003A074;
    v9 = 2;
  }
  v17 = v9;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v16 = v7;
  v18 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v14 = *(unsigned __int16 *)(a2 + 11);
  v13 = a2 + 11;
  UserData.Reserved = 2;
  v15 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
}

```

## disassembly

```asm
0x1800015f0  push    rbp
0x1800015f2  lea     rbp, [rsp-47h]
0x1800015f7  sub     rsp, 0A0h
0x1800015fe  mov     rax, cs:__security_cookie
0x180001605  xor     rax, rsp
0x180001608  mov     [rbp+47h+var_10], rax
0x18000160c  mov     rax, [rbp+47h+arg_28]
0x180001610  mov     r11d, 4
0x180001616  mov     [rbp+47h+var_20], rax
0x18000161a  mov     r10, rcx
0x18000161d  mov     rax, [rbp+47h+arg_20]
0x180001621  xor     r8d, r8d; ActivityId
0x180001624  mov     [rbp+47h+var_18], r11
0x180001628  lea     r9d, [r11-2]
0x18000162c  mov     rcx, [rax]
0x18000162f  test    rcx, rcx
0x180001632  jz      short loc_18000164B
0x180001634  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001638  inc     rax
0x18000163b  cmp     [rcx+rax*2], r8w
0x180001640  jnz     short loc_180001638
0x180001642  lea     eax, ds:2[rax*2]
0x180001649  jmp     short loc_180001655
0x18000164b  lea     rcx, dword_18003A074
0x180001652  mov     eax, r9d
0x180001655  mov     [rbp+47h+var_28], eax
0x180001658  movzx   eax, byte ptr [rdx]
0x18000165b  shl     eax, 18h
0x18000165e  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x180001661  movzx   eax, word ptr [rdx+1]
0x180001665  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180001668  mov     rax, [rdx+3]
0x18000166c  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x180001670  mov     rax, [r10+8]
0x180001674  mov     [rbp+47h+var_50.Ptr], rax
0x180001678  mov     [rbp+47h+var_30], rcx
0x18000167c  lea     rcx, [rdx+0Bh]
0x180001680  mov     [rbp+47h+var_24], r8d
0x180001684  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x180001688  movzx   eax, word ptr [rax]
0x18000168b  mov     [rbp+47h+var_50.Size], eax
0x18000168e  movzx   eax, word ptr [rcx]
0x180001691  mov     [rbp+47h+var_38], eax
0x180001694  lea     rax, _TraceLoggingMetadataEnd
0x18000169b  mov     [rbp+47h+var_40], rcx
0x18000169f  lea     rcx, _TraceLoggingMetadata
0x1800016a6  sub     eax, ecx
0x1800016a8  mov     dword ptr [rbp+47h+var_50.0Ch], r9d
0x1800016ac  mov     [rbp+47h+var_34], 1
0x1800016b3  xor     r9d, r9d; RelatedActivityId
0x1800016b6  mov     [rbp+47h+var_70], eax
0x1800016b9  mov     eax, [rbp+47h+var_70]
0x1800016bc  mov     rcx, [r10+20h]; RegHandle
0x1800016c0  lea     rax, [rbp+47h+var_50]
0x1800016c4  mov     [rsp+0A0h+UserData], rax; UserData
0x1800016c9  mov     [rsp+0A0h+UserDataCount], r11d; UserDataCount
0x1800016ce  call    cs:__imp_EventWriteTransfer
0x1800016d4  mov     rcx, [rbp+47h+var_10]
0x1800016d8  xor     rcx, rsp; StackCookie
0x1800016db  call    __security_check_cookie
0x1800016e0  add     rsp, 0A0h
0x1800016e7  pop     rbp
0x1800016e8  retn
```
