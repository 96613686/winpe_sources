# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180007f00`
- end: `0x1800080e3`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@_W@@U3@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@_W@@53AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011408`

## callees

- `0x180007f00`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800080c8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800080c8`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 *a6,
        const wchar_t **a7,
        __int64 **a8,
        __int64 **a9,
        const wchar_t **a10,
        __int64 a11)
{
  __int64 v11; // r8
  const wchar_t *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  const wchar_t *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  const wchar_t *v24; // rcx
  int v25; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-99h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 *v29; // [rsp+60h] [rbp-71h]
  int v30; // [rsp+68h] [rbp-69h]
  int v31; // [rsp+6Ch] [rbp-65h]
  const wchar_t *v32; // [rsp+70h] [rbp-61h]
  int v33; // [rsp+78h] [rbp-59h]
  int v34; // [rsp+7Ch] [rbp-55h]
  __int64 v35; // [rsp+80h] [rbp-51h]
  __int64 v36; // [rsp+88h] [rbp-49h]
  const wchar_t *v37; // [rsp+90h] [rbp-41h]
  int v38; // [rsp+98h] [rbp-39h]
  int v39; // [rsp+9Ch] [rbp-35h]
  __int64 *v40; // [rsp+A0h] [rbp-31h]
  int v41; // [rsp+A8h] [rbp-29h]
  int v42; // [rsp+ACh] [rbp-25h]
  __int64 *v43; // [rsp+B0h] [rbp-21h]
  int v44; // [rsp+B8h] [rbp-19h]
  int v45; // [rsp+BCh] [rbp-15h]
  const wchar_t *v46; // [rsp+C0h] [rbp-11h]
  int v47; // [rsp+C8h] [rbp-9h]
  int v48; // [rsp+CCh] [rbp-5h]
  __int64 v49; // [rsp+D0h] [rbp-1h]
  __int64 v50; // [rsp+D8h] [rbp+7h]

  v49 = a11;
  v11 = -1;
  v50 = 4;
  v12 = *a10;
  if ( *a10 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &byte_18002AE5D;
    v14 = 1;
  }
  v47 = v14;
  v46 = v12;
  v48 = 0;
  v15 = *a9;
  if ( *a9 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_18002AF20;
    v17 = 2;
  }
  v44 = v17;
  v43 = v15;
  v45 = 0;
  v18 = *a8;
  if ( *a8 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v18 = &qword_18002AF20;
    v20 = 2;
  }
  v41 = v20;
  v40 = v18;
  v42 = 0;
  v21 = *a7;
  if ( *a7 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_BYTE *)v21 + v22) );
    v23 = v22 + 1;
  }
  else
  {
    v21 = &byte_18002AE5D;
    v23 = 1;
  }
  v38 = v23;
  v37 = v21;
  v39 = 0;
  v36 = 16;
  v35 = *a6;
  v24 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v24 + v11) );
    v25 = v11 + 1;
  }
  else
  {
    v24 = &byte_18002AE5D;
    v25 = 1;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v32 = v24;
  v33 = v25;
  v34 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v30 = *(unsigned __int16 *)(a2 + 11);
  v29 = a2 + 11;
  UserData.Reserved = 2;
  v31 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 9u, &UserData);
}

```

## disassembly

```asm
0x180007f00  push    rbp
0x180007f02  lea     rbp, [rsp-1Fh]
0x180007f07  sub     rsp, 0F0h
0x180007f0e  mov     rax, cs:__security_cookie
0x180007f15  xor     rax, rsp
0x180007f18  mov     [rbp+1Fh+var_10], rax
0x180007f1c  mov     rax, [rbp+1Fh+arg_50]
0x180007f20  lea     r10, byte_18002AE5D
0x180007f27  xor     r9d, r9d; RelatedActivityId
0x180007f2a  mov     [rbp+1Fh+var_20], rax
0x180007f2e  mov     rax, [rbp+1Fh+arg_48]
0x180007f32  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007f36  mov     [rbp+1Fh+var_18], 4
0x180007f3e  lea     r11d, [r9+1]
0x180007f42  mov     rcx, [rax]
0x180007f45  test    rcx, rcx
0x180007f48  jz      short loc_180007F5A
0x180007f4a  mov     rax, r8
0x180007f4d  inc     rax
0x180007f50  cmp     [rcx+rax], r9b
0x180007f54  jnz     short loc_180007F4D
0x180007f56  inc     eax
0x180007f58  jmp     short loc_180007F60
0x180007f5a  mov     rcx, r10
0x180007f5d  mov     eax, r11d
0x180007f60  mov     [rbp+1Fh+var_28], eax
0x180007f63  mov     rax, [rbp+1Fh+arg_40]
0x180007f67  mov     [rbp+1Fh+var_30], rcx
0x180007f6b  mov     [rbp+1Fh+var_24], r9d
0x180007f6f  mov     rcx, [rax]
0x180007f72  test    rcx, rcx
0x180007f75  jz      short loc_180007F8D
0x180007f77  mov     rax, r8
0x180007f7a  inc     rax
0x180007f7d  cmp     [rcx+rax*2], r9w
0x180007f82  jnz     short loc_180007F7A
0x180007f84  lea     eax, ds:2[rax*2]
0x180007f8b  jmp     short loc_180007F99
0x180007f8d  lea     rcx, qword_18002AF20
0x180007f94  mov     eax, 2
0x180007f99  mov     [rbp+1Fh+var_38], eax
0x180007f9c  mov     rax, [rbp+1Fh+arg_38]
0x180007fa0  mov     [rbp+1Fh+var_40], rcx
0x180007fa4  mov     [rbp+1Fh+var_34], r9d
0x180007fa8  mov     rcx, [rax]
0x180007fab  test    rcx, rcx
0x180007fae  jz      short loc_180007FC6
0x180007fb0  mov     rax, r8
0x180007fb3  inc     rax
0x180007fb6  cmp     [rcx+rax*2], r9w
0x180007fbb  jnz     short loc_180007FB3
0x180007fbd  lea     eax, ds:2[rax*2]
0x180007fc4  jmp     short loc_180007FD2
0x180007fc6  lea     rcx, qword_18002AF20
0x180007fcd  mov     eax, 2
0x180007fd2  mov     [rbp+1Fh+var_48], eax
0x180007fd5  mov     rax, [rbp+1Fh+arg_30]
0x180007fd9  mov     [rbp+1Fh+var_50], rcx
0x180007fdd  mov     [rbp+1Fh+var_44], r9d
0x180007fe1  mov     rcx, [rax]
0x180007fe4  test    rcx, rcx
0x180007fe7  jz      short loc_180007FF9
0x180007fe9  mov     rax, r8
0x180007fec  inc     rax
0x180007fef  cmp     [rcx+rax], r9b
0x180007ff3  jnz     short loc_180007FEC
0x180007ff5  inc     eax
0x180007ff7  jmp     short loc_180007FFF
0x180007ff9  mov     rcx, r10
0x180007ffc  mov     eax, r11d
0x180007fff  mov     [rbp+1Fh+var_58], eax
0x180008002  mov     rax, [rbp+1Fh+arg_28]
0x180008006  mov     [rbp+1Fh+var_60], rcx
0x18000800a  mov     [rbp+1Fh+var_54], r9d
0x18000800e  mov     [rbp+1Fh+var_68], 10h
0x180008016  mov     rcx, [rax]
0x180008019  mov     rax, [rbp+1Fh+arg_20]
0x18000801d  mov     [rbp+1Fh+var_70], rcx
0x180008021  mov     rcx, [rax]
0x180008024  test    rcx, rcx
0x180008027  jz      short loc_180008037
0x180008029  inc     r8
0x18000802c  cmp     [rcx+r8], r9b
0x180008030  jnz     short loc_180008029
0x180008032  inc     r8d
0x180008035  jmp     short loc_18000803D
0x180008037  mov     rcx, r10
0x18000803a  mov     r8d, r11d
0x18000803d  movzx   eax, byte ptr [rdx]
0x180008040  shl     eax, 18h
0x180008043  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x180008047  movzx   eax, word ptr [rdx+1]
0x18000804b  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x18000804f  mov     rax, [rdx+3]
0x180008053  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x180008058  mov     rax, cs:off_180037058
0x18000805f  mov     [rsp+0F0h+var_A0.Ptr], rax
0x180008064  mov     [rbp+1Fh+var_80], rcx
0x180008068  lea     rcx, [rdx+0Bh]
0x18000806c  mov     [rbp+1Fh+var_78], r8d
0x180008070  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x180008075  mov     [rbp+1Fh+var_74], r9d
0x180008079  xor     r8d, r8d; ActivityId
0x18000807c  movzx   eax, word ptr [rax]
0x18000807f  mov     [rbp+1Fh+var_A0.Size], eax
0x180008082  movzx   eax, word ptr [rcx]
0x180008085  mov     [rbp+1Fh+var_88], eax
0x180008088  lea     rax, _TraceLoggingMetadataEnd
0x18000808f  mov     [rbp+1Fh+var_90], rcx
0x180008093  lea     rcx, _TraceLoggingMetadata
0x18000809a  sub     eax, ecx
0x18000809c  mov     dword ptr [rbp+1Fh+var_A0.0Ch], 2
0x1800080a3  mov     [rbp+1Fh+var_84], r11d
0x1800080a7  mov     [rsp+0F0h+var_C0], eax
0x1800080ab  mov     eax, [rsp+0F0h+var_C0]
0x1800080af  mov     rcx, cs:RegHandle; RegHandle
0x1800080b6  lea     rax, [rsp+0F0h+var_A0]
0x1800080bb  mov     [rsp+0F0h+UserData], rax; UserData
0x1800080c0  mov     [rsp+0F0h+UserDataCount], 9; UserDataCount
0x1800080c8  call    cs:__imp_EventWriteTransfer
0x1800080ce  mov     rcx, [rbp+1Fh+var_10]
0x1800080d2  xor     rcx, rsp; StackCookie
0x1800080d5  call    __security_check_cookie
0x1800080da  add     rsp, 0F0h
0x1800080e1  pop     rbp
0x1800080e2  retn
```
