# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000559c`
- end: `0x180005748`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@333AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ca54`

## callees

- `0x18000559c`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800056fd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800056fd`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        const wchar_t **a6,
        const wchar_t **a7,
        const wchar_t **a8,
        __int64 a9)
{
  __int64 v9; // rcx
  const wchar_t *v11; // r8
  __int64 v12; // rax
  int v13; // eax
  const wchar_t *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  const wchar_t *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  const wchar_t *v20; // rdx
  int v21; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 *v25; // [rsp+60h] [rbp-41h]
  int v26; // [rsp+68h] [rbp-39h]
  int v27; // [rsp+6Ch] [rbp-35h]
  const wchar_t *v28; // [rsp+70h] [rbp-31h]
  int v29; // [rsp+78h] [rbp-29h]
  int v30; // [rsp+7Ch] [rbp-25h]
  const wchar_t *v31; // [rsp+80h] [rbp-21h]
  int v32; // [rsp+88h] [rbp-19h]
  int v33; // [rsp+8Ch] [rbp-15h]
  const wchar_t *v34; // [rsp+90h] [rbp-11h]
  int v35; // [rsp+98h] [rbp-9h]
  int v36; // [rsp+9Ch] [rbp-5h]
  const wchar_t *v37; // [rsp+A0h] [rbp-1h]
  int v38; // [rsp+A8h] [rbp+7h]
  int v39; // [rsp+ACh] [rbp+Bh]
  __int64 v40; // [rsp+B0h] [rbp+Fh]
  __int64 v41; // [rsp+B8h] [rbp+17h]

  v40 = a9;
  v9 = -1;
  v41 = 4;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &byte_18002AE5D;
    v13 = 1;
  }
  v38 = v13;
  v37 = v11;
  v39 = 0;
  v14 = *a7;
  if ( *a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &byte_18002AE5D;
    v16 = 1;
  }
  v35 = v16;
  v34 = v14;
  v36 = 0;
  v17 = *a6;
  if ( *a6 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &byte_18002AE5D;
    v19 = 1;
  }
  v32 = v19;
  v31 = v17;
  v33 = 0;
  v20 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v20 + v9) );
    v21 = v9 + 1;
  }
  else
  {
    v20 = &byte_18002AE5D;
    v21 = 1;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v29 = v21;
  v28 = v20;
  v30 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v26 = *(unsigned __int16 *)(a2 + 11);
  v25 = a2 + 11;
  UserData.Reserved = 2;
  v27 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
}

```

## disassembly

```asm
0x18000559c  mov     [rsp-8+arg_0], rbx
0x1800055a1  push    rbp
0x1800055a2  lea     rbp, [rsp-2Fh]
0x1800055a7  sub     rsp, 0D0h
0x1800055ae  mov     rax, cs:__security_cookie
0x1800055b5  xor     rax, rsp
0x1800055b8  mov     [rbp+2Fh+var_10], rax
0x1800055bc  mov     rax, [rbp+2Fh+arg_40]
0x1800055c0  lea     r11, byte_18002AE5D
0x1800055c7  xor     r10d, r10d
0x1800055ca  mov     [rbp+2Fh+var_20], rax
0x1800055ce  mov     rax, [rbp+2Fh+arg_38]
0x1800055d2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800055d6  mov     r9, rdx
0x1800055d9  mov     [rbp+2Fh+var_18], 4
0x1800055e1  lea     ebx, [r10+1]
0x1800055e5  mov     r8, [rax]
0x1800055e8  test    r8, r8
0x1800055eb  jz      loc_180005720
0x1800055f1  mov     rax, rcx
0x1800055f4  inc     rax
0x1800055f7  cmp     [r8+rax], r10b
0x1800055fb  jnz     short loc_1800055F4
0x1800055fd  inc     eax
0x1800055ff  mov     [rbp+2Fh+var_28], eax
0x180005602  mov     rax, [rbp+2Fh+arg_30]
0x180005606  mov     [rbp+2Fh+var_30], r8
0x18000560a  mov     [rbp+2Fh+var_24], r10d
0x18000560e  mov     rdx, [rax]
0x180005611  test    rdx, rdx
0x180005614  jz      loc_18000572A
0x18000561a  mov     rax, rcx
0x18000561d  inc     rax
0x180005620  cmp     [rdx+rax], r10b
0x180005624  jnz     short loc_18000561D
0x180005626  inc     eax
0x180005628  mov     [rbp+2Fh+var_38], eax
0x18000562b  mov     rax, [rbp+2Fh+arg_28]
0x18000562f  mov     [rbp+2Fh+var_40], rdx
0x180005633  mov     [rbp+2Fh+var_34], r10d
0x180005637  mov     rdx, [rax]
0x18000563a  test    rdx, rdx
0x18000563d  jz      loc_180005734
0x180005643  mov     rax, rcx
0x180005646  inc     rax
0x180005649  cmp     [rdx+rax], r10b
0x18000564d  jnz     short loc_180005646
0x18000564f  inc     eax
0x180005651  mov     [rbp+2Fh+var_48], eax
0x180005654  mov     rax, [rbp+2Fh+arg_20]
0x180005658  mov     [rbp+2Fh+var_50], rdx
0x18000565c  mov     [rbp+2Fh+var_44], r10d
0x180005660  mov     rdx, [rax]
0x180005663  test    rdx, rdx
0x180005666  jz      loc_18000573E
0x18000566c  inc     rcx
0x18000566f  cmp     [rdx+rcx], r10b
0x180005673  jnz     short loc_18000566C
0x180005675  inc     ecx
0x180005677  movzx   eax, byte ptr [r9]
0x18000567b  xor     r8d, r8d; ActivityId
0x18000567e  shl     eax, 18h
0x180005681  mov     dword ptr [rbp+2Fh+EventDescriptor.Id], eax
0x180005684  movzx   eax, word ptr [r9+1]
0x180005689  mov     dword ptr [rbp+2Fh+EventDescriptor.Level], eax
0x18000568c  mov     rax, [r9+3]
0x180005690  mov     [rbp+2Fh+EventDescriptor.Keyword], rax
0x180005694  mov     rax, cs:off_180037058
0x18000569b  mov     [rbp+2Fh+var_80.Ptr], rax
0x18000569f  mov     [rbp+2Fh+var_58], ecx
0x1800056a2  lea     rcx, [r9+0Bh]
0x1800056a6  mov     [rbp+2Fh+var_60], rdx
0x1800056aa  xor     r9d, r9d; RelatedActivityId
0x1800056ad  mov     [rbp+2Fh+var_54], r10d
0x1800056b1  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x1800056b5  movzx   eax, word ptr [rax]
0x1800056b8  mov     [rbp+2Fh+var_80.Size], eax
0x1800056bb  movzx   eax, word ptr [rcx]
0x1800056be  mov     [rbp+2Fh+var_68], eax
0x1800056c1  lea     rax, _TraceLoggingMetadataEnd
0x1800056c8  mov     [rbp+2Fh+var_70], rcx
0x1800056cc  lea     rcx, _TraceLoggingMetadata
0x1800056d3  sub     eax, ecx
0x1800056d5  mov     dword ptr [rbp+2Fh+var_80.0Ch], 2
0x1800056dc  mov     [rbp+2Fh+var_64], ebx
0x1800056df  mov     [rbp+2Fh+var_A0], eax
0x1800056e2  mov     eax, [rbp+2Fh+var_A0]
0x1800056e5  mov     rcx, cs:RegHandle; RegHandle
0x1800056ec  lea     rax, [rbp+2Fh+var_80]
0x1800056f0  mov     [rsp+0D0h+UserData], rax; UserData
0x1800056f5  mov     [rsp+0D0h+UserDataCount], 7; UserDataCount
0x1800056fd  call    cs:__imp_EventWriteTransfer
0x180005703  mov     rcx, [rbp+2Fh+var_10]
0x180005707  xor     rcx, rsp; StackCookie
0x18000570a  call    __security_check_cookie
0x18000570f  mov     rbx, [rsp+0D0h+arg_0]
0x180005717  add     rsp, 0D0h
0x18000571e  pop     rbp
0x18000571f  retn
0x180005720  mov     r8, r11
0x180005723  mov     eax, ebx
0x180005725  jmp     loc_1800055FF
0x18000572a  mov     rdx, r11
0x18000572d  mov     eax, ebx
0x18000572f  jmp     loc_180005628
0x180005734  mov     rdx, r11
0x180005737  mov     eax, ebx
0x180005739  jmp     loc_180005651
0x18000573e  mov     rdx, r11
0x180005741  mov     ecx, ebx
0x180005743  jmp     loc_180005677
```
