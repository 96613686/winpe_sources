# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800082cc`
- end: `0x180008443`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180015840`
- `0x18001cda8`

## callees

- `0x1800082cc`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008428`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008428`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 *a6,
        const wchar_t **a7,
        __int64 **a8,
        __int64 a9)
{
  __int64 v9; // r8
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  const wchar_t *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  const wchar_t *v16; // rcx
  int v17; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 *v21; // [rsp+60h] [rbp-41h]
  int v22; // [rsp+68h] [rbp-39h]
  int v23; // [rsp+6Ch] [rbp-35h]
  const wchar_t *v24; // [rsp+70h] [rbp-31h]
  int v25; // [rsp+78h] [rbp-29h]
  int v26; // [rsp+7Ch] [rbp-25h]
  __int64 v27; // [rsp+80h] [rbp-21h]
  __int64 v28; // [rsp+88h] [rbp-19h]
  const wchar_t *v29; // [rsp+90h] [rbp-11h]
  int v30; // [rsp+98h] [rbp-9h]
  int v31; // [rsp+9Ch] [rbp-5h]
  __int64 *v32; // [rsp+A0h] [rbp-1h]
  int v33; // [rsp+A8h] [rbp+7h]
  int v34; // [rsp+ACh] [rbp+Bh]
  __int64 v35; // [rsp+B0h] [rbp+Fh]
  __int64 v36; // [rsp+B8h] [rbp+17h]

  v35 = a9;
  v9 = -1;
  v36 = 4;
  v10 = *a8;
  if ( *a8 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &qword_18002AF20;
    v12 = 2;
  }
  v33 = v12;
  v32 = v10;
  v34 = 0;
  v13 = *a7;
  if ( *a7 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &byte_18002AE5D;
    v15 = 1;
  }
  v30 = v15;
  v29 = v13;
  v31 = 0;
  v28 = 16;
  v27 = *a6;
  v16 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v16 + v9) );
    v17 = v9 + 1;
  }
  else
  {
    v16 = &byte_18002AE5D;
    v17 = 1;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v24 = v16;
  v25 = v17;
  v26 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v22 = *(unsigned __int16 *)(a2 + 11);
  v21 = a2 + 11;
  UserData.Reserved = 2;
  v23 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
}

```

## disassembly

```asm
0x1800082cc  push    rbp
0x1800082ce  lea     rbp, [rsp-2Fh]
0x1800082d3  sub     rsp, 0D0h
0x1800082da  mov     rax, cs:__security_cookie
0x1800082e1  xor     rax, rsp
0x1800082e4  mov     [rbp+2Fh+var_10], rax
0x1800082e8  mov     rax, [rbp+2Fh+arg_40]
0x1800082ec  xor     r9d, r9d; RelatedActivityId
0x1800082ef  mov     [rbp+2Fh+var_20], rax
0x1800082f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800082f7  mov     rax, [rbp+2Fh+arg_38]
0x1800082fb  mov     [rbp+2Fh+var_18], 4
0x180008303  lea     r11d, [r9+2]
0x180008307  mov     rcx, [rax]
0x18000830a  test    rcx, rcx
0x18000830d  jz      short loc_180008325
0x18000830f  mov     rax, r8
0x180008312  inc     rax
0x180008315  cmp     [rcx+rax*2], r9w
0x18000831a  jnz     short loc_180008312
0x18000831c  lea     eax, ds:2[rax*2]
0x180008323  jmp     short loc_18000832F
0x180008325  lea     rcx, qword_18002AF20
0x18000832c  mov     eax, r11d
0x18000832f  mov     [rbp+2Fh+var_28], eax
0x180008332  mov     r10d, 1
0x180008338  mov     rax, [rbp+2Fh+arg_30]
0x18000833c  mov     [rbp+2Fh+var_30], rcx
0x180008340  mov     [rbp+2Fh+var_24], r9d
0x180008344  mov     rcx, [rax]
0x180008347  test    rcx, rcx
0x18000834a  jz      short loc_18000835C
0x18000834c  mov     rax, r8
0x18000834f  inc     rax
0x180008352  cmp     [rcx+rax], r9b
0x180008356  jnz     short loc_18000834F
0x180008358  inc     eax
0x18000835a  jmp     short loc_180008366
0x18000835c  lea     rcx, byte_18002AE5D
0x180008363  mov     eax, r10d
0x180008366  mov     [rbp+2Fh+var_38], eax
0x180008369  mov     rax, [rbp+2Fh+arg_28]
0x18000836d  mov     [rbp+2Fh+var_40], rcx
0x180008371  mov     [rbp+2Fh+var_34], r9d
0x180008375  mov     [rbp+2Fh+var_48], 10h
0x18000837d  mov     rcx, [rax]
0x180008380  mov     rax, [rbp+2Fh+arg_20]
0x180008384  mov     [rbp+2Fh+var_50], rcx
0x180008388  mov     rcx, [rax]
0x18000838b  test    rcx, rcx
0x18000838e  jz      short loc_18000839E
0x180008390  inc     r8
0x180008393  cmp     [rcx+r8], r9b
0x180008397  jnz     short loc_180008390
0x180008399  inc     r8d
0x18000839c  jmp     short loc_1800083A8
0x18000839e  lea     rcx, byte_18002AE5D
0x1800083a5  mov     r8d, r10d
0x1800083a8  movzx   eax, byte ptr [rdx]
0x1800083ab  shl     eax, 18h
0x1800083ae  mov     dword ptr [rbp+2Fh+EventDescriptor.Id], eax
0x1800083b1  movzx   eax, word ptr [rdx+1]
0x1800083b5  mov     dword ptr [rbp+2Fh+EventDescriptor.Level], eax
0x1800083b8  mov     rax, [rdx+3]
0x1800083bc  mov     [rbp+2Fh+EventDescriptor.Keyword], rax
0x1800083c0  mov     rax, cs:off_180037058
0x1800083c7  mov     [rbp+2Fh+var_80.Ptr], rax
0x1800083cb  mov     [rbp+2Fh+var_60], rcx
0x1800083cf  lea     rcx, [rdx+0Bh]
0x1800083d3  mov     [rbp+2Fh+var_58], r8d
0x1800083d7  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x1800083db  mov     [rbp+2Fh+var_54], r9d
0x1800083df  xor     r8d, r8d; ActivityId
0x1800083e2  movzx   eax, word ptr [rax]
0x1800083e5  mov     [rbp+2Fh+var_80.Size], eax
0x1800083e8  movzx   eax, word ptr [rcx]
0x1800083eb  mov     [rbp+2Fh+var_68], eax
0x1800083ee  lea     rax, _TraceLoggingMetadataEnd
0x1800083f5  mov     [rbp+2Fh+var_70], rcx
0x1800083f9  lea     rcx, _TraceLoggingMetadata
0x180008400  sub     eax, ecx
0x180008402  mov     dword ptr [rbp+2Fh+var_80.0Ch], r11d
0x180008406  mov     [rbp+2Fh+var_64], r10d
0x18000840a  mov     [rbp+2Fh+var_A0], eax
0x18000840d  mov     eax, [rbp+2Fh+var_A0]
0x180008410  mov     rcx, cs:RegHandle; RegHandle
0x180008417  lea     rax, [rbp+2Fh+var_80]
0x18000841b  mov     [rsp+0D0h+UserData], rax; UserData
0x180008420  mov     [rsp+0D0h+UserDataCount], 7; UserDataCount
0x180008428  call    cs:__imp_EventWriteTransfer
0x18000842e  mov     rcx, [rbp+2Fh+var_10]
0x180008432  xor     rcx, rsp; StackCookie
0x180008435  call    __security_check_cookie
0x18000843a  add     rsp, 0D0h
0x180008441  pop     rbp
0x180008442  retn
```
