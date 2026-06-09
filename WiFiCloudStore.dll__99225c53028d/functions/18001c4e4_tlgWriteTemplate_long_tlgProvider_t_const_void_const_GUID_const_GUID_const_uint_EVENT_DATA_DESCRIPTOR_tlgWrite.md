# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18001c4e4`
- end: `0x18001c603`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z`
- size: `287`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, __int64, __int64, char **, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001428c`

## callees

- `0x18001c4e4`
- `0x18002a030`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001c5d7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001c5d7`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        char **a7,
        __int64 a8)
{
  char *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 *v15; // [rsp+60h] [rbp-29h]
  int v16; // [rsp+68h] [rbp-21h]
  int v17; // [rsp+6Ch] [rbp-1Dh]
  __int64 v18; // [rsp+70h] [rbp-19h]
  __int64 v19; // [rsp+78h] [rbp-11h]
  __int64 v20; // [rsp+80h] [rbp-9h]
  __int64 v21; // [rsp+88h] [rbp-1h]
  char *v22; // [rsp+90h] [rbp+7h]
  int v23; // [rsp+98h] [rbp+Fh]
  int v24; // [rsp+9Ch] [rbp+13h]
  __int64 v25; // [rsp+A0h] [rbp+17h]
  __int64 v26; // [rsp+A8h] [rbp+1Fh]

  v25 = a8;
  v26 = 8;
  v9 = *a7;
  if ( *a7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v9[2 * v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = byte_180043BA0;
    v11 = 2;
  }
  v23 = v11;
  v20 = a6;
  v18 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v22 = v9;
  v24 = 0;
  v21 = 4;
  v19 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v16 = *(unsigned __int16 *)(a2 + 11);
  v15 = a2 + 11;
  UserData.Reserved = 2;
  v17 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 6u, &UserData);
}

```

## disassembly

```asm
0x18001c4e4  push    rbp
0x18001c4e6  lea     rbp, [rsp-37h]
0x18001c4eb  sub     rsp, 0C0h
0x18001c4f2  mov     rax, cs:__security_cookie
0x18001c4f9  xor     rax, rsp
0x18001c4fc  mov     [rbp+37h+var_10], rax
0x18001c500  mov     rax, [rbp+37h+arg_38]
0x18001c504  mov     r10, rcx
0x18001c507  mov     [rbp+37h+var_20], rax
0x18001c50b  xor     r11d, r11d
0x18001c50e  mov     rax, [rbp+37h+arg_30]
0x18001c512  mov     [rbp+37h+var_18], 8
0x18001c51a  mov     rcx, [rax]
0x18001c51d  test    rcx, rcx
0x18001c520  jz      loc_18001C5F2
0x18001c526  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c52a  inc     rax
0x18001c52d  cmp     [rcx+rax*2], r11w
0x18001c532  jnz     short loc_18001C52A
0x18001c534  lea     eax, ds:2[rax*2]
0x18001c53b  mov     [rbp+37h+var_28], eax
0x18001c53e  mov     rax, [rbp+37h+arg_28]
0x18001c542  mov     [rbp+37h+var_40], rax
0x18001c546  mov     rax, [rbp+37h+arg_20]
0x18001c54a  mov     [rbp+37h+var_50], rax
0x18001c54e  movzx   eax, byte ptr [rdx]
0x18001c551  shl     eax, 18h
0x18001c554  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x18001c557  movzx   eax, word ptr [rdx+1]
0x18001c55b  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x18001c55e  mov     rax, [rdx+3]
0x18001c562  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x18001c566  mov     rax, [r10+8]
0x18001c56a  mov     [rbp+37h+var_70.Ptr], rax
0x18001c56e  mov     [rbp+37h+var_30], rcx
0x18001c572  lea     rcx, [rdx+0Bh]
0x18001c576  mov     [rbp+37h+var_24], r11d
0x18001c57a  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x18001c57e  mov     [rbp+37h+var_38], 4
0x18001c586  mov     [rbp+37h+var_48], 8
0x18001c58e  movzx   eax, word ptr [rax]
0x18001c591  mov     [rbp+37h+var_70.Size], eax
0x18001c594  movzx   eax, word ptr [rcx]
0x18001c597  mov     [rbp+37h+var_58], eax
0x18001c59a  lea     rax, _TraceLoggingMetadataEnd
0x18001c5a1  mov     [rbp+37h+var_60], rcx
0x18001c5a5  lea     rcx, _TraceLoggingMetadata
0x18001c5ac  sub     eax, ecx
0x18001c5ae  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x18001c5b5  mov     [rbp+37h+var_54], 1
0x18001c5bc  mov     [rbp+37h+var_90], eax
0x18001c5bf  mov     eax, [rbp+37h+var_90]
0x18001c5c2  mov     rcx, [r10+20h]; RegHandle
0x18001c5c6  lea     rax, [rbp+37h+var_70]
0x18001c5ca  mov     [rsp+0C0h+UserData], rax; UserData
0x18001c5cf  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x18001c5d7  call    cs:__imp_EventWriteTransfer
0x18001c5dd  mov     rcx, [rbp+37h+var_10]
0x18001c5e1  xor     rcx, rsp; StackCookie
0x18001c5e4  call    __security_check_cookie
0x18001c5e9  add     rsp, 0C0h
0x18001c5f0  pop     rbp
0x18001c5f1  retn
0x18001c5f2  lea     rcx, byte_180043BA0
0x18001c5f9  mov     eax, 2
0x18001c5fe  jmp     loc_18001C53B
```
