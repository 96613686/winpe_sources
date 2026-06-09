# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)

- ea: `0x18000d034`
- end: `0x18000d17a`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$01@@@Z`
- size: `326`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64 *, int **, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f6f0`
- `0x18000fa10`

## callees

- `0x18000d034`
- `0x180012dd0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d150`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d150`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        int **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  int *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 *v17; // [rsp+60h] [rbp-59h]
  int v18; // [rsp+68h] [rbp-51h]
  int v19; // [rsp+6Ch] [rbp-4Dh]
  __int64 v20; // [rsp+70h] [rbp-49h]
  __int64 v21; // [rsp+78h] [rbp-41h]
  int *v22; // [rsp+80h] [rbp-39h]
  int v23; // [rsp+88h] [rbp-31h]
  int v24; // [rsp+8Ch] [rbp-2Dh]
  __int64 v25; // [rsp+90h] [rbp-29h]
  __int64 v26; // [rsp+98h] [rbp-21h]
  __int64 v27; // [rsp+A0h] [rbp-19h]
  __int64 v28; // [rsp+A8h] [rbp-11h]
  __int64 v29; // [rsp+B0h] [rbp-9h]
  __int64 v30; // [rsp+B8h] [rbp-1h]
  __int64 v31; // [rsp+C0h] [rbp+7h]
  __int64 v32; // [rsp+C8h] [rbp+Fh]

  v31 = a10;
  v29 = a9;
  v27 = a8;
  v25 = a7;
  v32 = 2;
  v30 = 4;
  v28 = 4;
  v10 = *a6;
  v26 = 8;
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &dword_18001EDEC;
    v12 = 2;
  }
  v23 = v12;
  v22 = v10;
  v24 = 0;
  v21 = 16;
  v13 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180026060;
  v20 = v13;
  UserData.Size = *(unsigned __int16 *)off_180026060;
  v18 = *(unsigned __int16 *)(a2 + 11);
  v17 = a2 + 11;
  UserData.Reserved = 2;
  v19 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
}

```

## disassembly

```asm
0x18000d034  push    rbp
0x18000d036  lea     rbp, [rsp-27h]
0x18000d03b  sub     rsp, 0E0h
0x18000d042  mov     rax, cs:__security_cookie
0x18000d049  xor     rax, rsp
0x18000d04c  mov     [rbp+27h+var_10], rax
0x18000d050  mov     rax, [rbp+27h+arg_48]
0x18000d054  mov     r9d, 2
0x18000d05a  mov     [rbp+27h+var_20], rax
0x18000d05e  xor     r8d, r8d; ActivityId
0x18000d061  mov     rax, [rbp+27h+arg_40]
0x18000d065  mov     [rbp+27h+var_30], rax
0x18000d069  mov     rax, [rbp+27h+arg_38]
0x18000d06d  lea     r10d, [r9+6]
0x18000d071  mov     [rbp+27h+var_40], rax
0x18000d075  mov     rax, [rbp+27h+arg_30]
0x18000d079  mov     [rbp+27h+var_50], rax
0x18000d07d  mov     rax, [rbp+27h+arg_28]
0x18000d081  mov     [rbp+27h+var_18], r9
0x18000d085  mov     [rbp+27h+var_28], 4
0x18000d08d  mov     [rbp+27h+var_38], 4
0x18000d095  mov     rcx, [rax]
0x18000d098  mov     [rbp+27h+var_48], r10
0x18000d09c  test    rcx, rcx
0x18000d09f  jz      loc_18000D16B
0x18000d0a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d0a9  inc     rax
0x18000d0ac  cmp     [rcx+rax*2], r8w
0x18000d0b1  jnz     short loc_18000D0A9
0x18000d0b3  lea     eax, ds:2[rax*2]
0x18000d0ba  mov     [rbp+27h+var_58], eax
0x18000d0bd  mov     rax, [rbp+27h+arg_20]
0x18000d0c1  mov     [rbp+27h+var_60], rcx
0x18000d0c5  mov     [rbp+27h+var_54], r8d
0x18000d0c9  mov     [rbp+27h+var_68], 10h
0x18000d0d1  mov     rcx, [rax]
0x18000d0d4  movzx   eax, byte ptr [rdx]
0x18000d0d7  shl     eax, 18h
0x18000d0da  mov     dword ptr [rsp+0E0h+EventDescriptor.Id], eax
0x18000d0de  movzx   eax, word ptr [rdx+1]
0x18000d0e2  mov     dword ptr [rbp+27h+EventDescriptor.Level], eax
0x18000d0e5  mov     rax, [rdx+3]
0x18000d0e9  mov     [rbp+27h+EventDescriptor.Keyword], rax
0x18000d0ed  mov     rax, cs:off_180026060
0x18000d0f4  mov     [rbp+27h+var_90.Ptr], rax
0x18000d0f8  mov     [rbp+27h+var_70], rcx
0x18000d0fc  lea     rcx, [rdx+0Bh]
0x18000d100  lea     rdx, [rsp+0E0h+EventDescriptor]; EventDescriptor
0x18000d105  movzx   eax, word ptr [rax]
0x18000d108  mov     [rbp+27h+var_90.Size], eax
0x18000d10b  movzx   eax, word ptr [rcx]
0x18000d10e  mov     [rbp+27h+var_78], eax
0x18000d111  lea     rax, _TraceLoggingMetadataEnd
0x18000d118  mov     [rbp+27h+var_80], rcx
0x18000d11c  lea     rcx, _TraceLoggingMetadata
0x18000d123  sub     eax, ecx
0x18000d125  mov     dword ptr [rbp+27h+var_90.0Ch], r9d
0x18000d129  mov     [rbp+27h+var_74], 1
0x18000d130  xor     r9d, r9d; RelatedActivityId
0x18000d133  mov     [rsp+0E0h+var_B0], eax
0x18000d137  mov     eax, [rsp+0E0h+var_B0]
0x18000d13b  mov     rcx, cs:RegHandle; RegHandle
0x18000d142  lea     rax, [rbp+27h+var_90]
0x18000d146  mov     [rsp+0E0h+UserData], rax; UserData
0x18000d14b  mov     [rsp+0E0h+UserDataCount], r10d; UserDataCount
0x18000d150  call    cs:__imp_EventWriteTransfer
0x18000d156  mov     rcx, [rbp+27h+var_10]
0x18000d15a  xor     rcx, rsp; StackCookie
0x18000d15d  call    __security_check_cookie
0x18000d162  add     rsp, 0E0h
0x18000d169  pop     rbp
0x18000d16a  retn
0x18000d16b  lea     rcx, dword_18001EDEC
0x18000d172  mov     eax, r9d
0x18000d175  jmp     loc_18000D0BA
```
