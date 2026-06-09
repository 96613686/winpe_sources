# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180019a10`
- end: `0x180019b10`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `256`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, char **, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180011cfc`
- `0x180020980`
- `0x1800209e0`
- `0x180020f7c`
- `0x18003a7fc`
- `0x18003a85c`
- `0x18003aaa0`

## callees

- `0x180019a10`
- `0x18002a030`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019ae6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019ae6`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        char **a5,
        __int64 a6)
{
  char *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 *v13; // [rsp+60h] [rbp+7h]
  int v14; // [rsp+68h] [rbp+Fh]
  int v15; // [rsp+6Ch] [rbp+13h]
  char *v16; // [rsp+70h] [rbp+17h]
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
    while ( *(_WORD *)&v7[2 * v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = byte_180043BA0;
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
0x180019a10  push    rbp
0x180019a12  lea     rbp, [rsp-47h]
0x180019a17  sub     rsp, 0A0h
0x180019a1e  mov     rax, cs:__security_cookie
0x180019a25  xor     rax, rsp
0x180019a28  mov     [rbp+47h+var_10], rax
0x180019a2c  mov     rax, [rbp+47h+arg_28]
0x180019a30  mov     r11d, 4
0x180019a36  mov     [rbp+47h+var_20], rax
0x180019a3a  mov     r10, rcx
0x180019a3d  mov     rax, [rbp+47h+arg_20]
0x180019a41  xor     r8d, r8d; ActivityId
0x180019a44  mov     [rbp+47h+var_18], r11
0x180019a48  lea     r9d, [r11-2]
0x180019a4c  mov     rcx, [rax]
0x180019a4f  test    rcx, rcx
0x180019a52  jz      loc_180019B01
0x180019a58  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019a5c  inc     rax
0x180019a5f  cmp     [rcx+rax*2], r8w
0x180019a64  jnz     short loc_180019A5C
0x180019a66  lea     eax, ds:2[rax*2]
0x180019a6d  mov     [rbp+47h+var_28], eax
0x180019a70  movzx   eax, byte ptr [rdx]
0x180019a73  shl     eax, 18h
0x180019a76  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x180019a79  movzx   eax, word ptr [rdx+1]
0x180019a7d  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180019a80  mov     rax, [rdx+3]
0x180019a84  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x180019a88  mov     rax, [r10+8]
0x180019a8c  mov     [rbp+47h+var_50.Ptr], rax
0x180019a90  mov     [rbp+47h+var_30], rcx
0x180019a94  lea     rcx, [rdx+0Bh]
0x180019a98  mov     [rbp+47h+var_24], r8d
0x180019a9c  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x180019aa0  movzx   eax, word ptr [rax]
0x180019aa3  mov     [rbp+47h+var_50.Size], eax
0x180019aa6  movzx   eax, word ptr [rcx]
0x180019aa9  mov     [rbp+47h+var_38], eax
0x180019aac  lea     rax, _TraceLoggingMetadataEnd
0x180019ab3  mov     [rbp+47h+var_40], rcx
0x180019ab7  lea     rcx, _TraceLoggingMetadata
0x180019abe  sub     eax, ecx
0x180019ac0  mov     dword ptr [rbp+47h+var_50.0Ch], r9d
0x180019ac4  mov     [rbp+47h+var_34], 1
0x180019acb  xor     r9d, r9d; RelatedActivityId
0x180019ace  mov     [rbp+47h+var_70], eax
0x180019ad1  mov     eax, [rbp+47h+var_70]
0x180019ad4  mov     rcx, [r10+20h]; RegHandle
0x180019ad8  lea     rax, [rbp+47h+var_50]
0x180019adc  mov     [rsp+0A0h+UserData], rax; UserData
0x180019ae1  mov     [rsp+0A0h+UserDataCount], r11d; UserDataCount
0x180019ae6  call    cs:__imp_EventWriteTransfer
0x180019aec  mov     rcx, [rbp+47h+var_10]
0x180019af0  xor     rcx, rsp; StackCookie
0x180019af3  call    __security_check_cookie
0x180019af8  add     rsp, 0A0h
0x180019aff  pop     rbp
0x180019b00  retn
0x180019b01  lea     rcx, byte_180043BA0
0x180019b08  mov     eax, r9d
0x180019b0b  jmp     loc_180019A6D
```
