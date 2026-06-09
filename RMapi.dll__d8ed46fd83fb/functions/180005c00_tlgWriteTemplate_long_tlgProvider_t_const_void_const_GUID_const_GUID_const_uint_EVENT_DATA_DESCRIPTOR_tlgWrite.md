# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180005c00`
- end: `0x180005df1`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@333AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ca54`

## callees

- `0x180005c00`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005d97`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005d97`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 **a6,
        const wchar_t **a7,
        const wchar_t **a8,
        const wchar_t **a9,
        __int64 a10)
{
  __int64 v10; // rcx
  const wchar_t *v12; // r8
  __int64 v13; // rax
  int v14; // eax
  const wchar_t *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  const wchar_t *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  __int64 *v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  const wchar_t *v24; // rdx
  int v25; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 *v29; // [rsp+60h] [rbp-59h]
  int v30; // [rsp+68h] [rbp-51h]
  int v31; // [rsp+6Ch] [rbp-4Dh]
  const wchar_t *v32; // [rsp+70h] [rbp-49h]
  int v33; // [rsp+78h] [rbp-41h]
  int v34; // [rsp+7Ch] [rbp-3Dh]
  __int64 *v35; // [rsp+80h] [rbp-39h]
  int v36; // [rsp+88h] [rbp-31h]
  int v37; // [rsp+8Ch] [rbp-2Dh]
  const wchar_t *v38; // [rsp+90h] [rbp-29h]
  int v39; // [rsp+98h] [rbp-21h]
  int v40; // [rsp+9Ch] [rbp-1Dh]
  const wchar_t *v41; // [rsp+A0h] [rbp-19h]
  int v42; // [rsp+A8h] [rbp-11h]
  int v43; // [rsp+ACh] [rbp-Dh]
  const wchar_t *v44; // [rsp+B0h] [rbp-9h]
  int v45; // [rsp+B8h] [rbp-1h]
  int v46; // [rsp+BCh] [rbp+3h]
  __int64 v47; // [rsp+C0h] [rbp+7h]
  __int64 v48; // [rsp+C8h] [rbp+Fh]

  v47 = a10;
  v10 = -1;
  v48 = 4;
  v12 = *a9;
  if ( *a9 )
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
  v45 = v14;
  v44 = v12;
  v46 = 0;
  v15 = *a8;
  if ( *a8 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_BYTE *)v15 + v16) );
    v17 = v16 + 1;
  }
  else
  {
    v15 = &byte_18002AE5D;
    v17 = 1;
  }
  v42 = v17;
  v41 = v15;
  v43 = 0;
  v18 = *a7;
  if ( *a7 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_BYTE *)v18 + v19) );
    v20 = v19 + 1;
  }
  else
  {
    v18 = &byte_18002AE5D;
    v20 = 1;
  }
  v39 = v20;
  v38 = v18;
  v40 = 0;
  v21 = *a6;
  if ( *a6 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v21 + v22) );
    v23 = 2 * v22 + 2;
  }
  else
  {
    v21 = &qword_18002AF20;
    v23 = 2;
  }
  v36 = v23;
  v35 = v21;
  v37 = 0;
  v24 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v24 + v10) );
    v25 = v10 + 1;
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
  v33 = v25;
  v32 = v24;
  v34 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v30 = *(unsigned __int16 *)(a2 + 11);
  v29 = a2 + 11;
  UserData.Reserved = 2;
  v31 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
}

```

## disassembly

```asm
0x180005c00  mov     [rsp-8+arg_0], rbx
0x180005c05  push    rbp
0x180005c06  lea     rbp, [rsp-27h]
0x180005c0b  sub     rsp, 0E0h
0x180005c12  mov     rax, cs:__security_cookie
0x180005c19  xor     rax, rsp
0x180005c1c  mov     [rbp+27h+var_10], rax
0x180005c20  mov     rax, [rbp+27h+arg_48]
0x180005c24  lea     r11, byte_18002AE5D
0x180005c2b  xor     r10d, r10d
0x180005c2e  mov     [rbp+27h+var_20], rax
0x180005c32  mov     rax, [rbp+27h+arg_40]
0x180005c36  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180005c3a  mov     r9, rdx
0x180005c3d  mov     [rbp+27h+var_18], 4
0x180005c45  lea     ebx, [r10+1]
0x180005c49  mov     r8, [rax]
0x180005c4c  test    r8, r8
0x180005c4f  jz      loc_180005DBA
0x180005c55  mov     rax, rcx
0x180005c58  inc     rax
0x180005c5b  cmp     [r8+rax], r10b
0x180005c5f  jnz     short loc_180005C58
0x180005c61  inc     eax
0x180005c63  mov     [rbp+27h+var_28], eax
0x180005c66  mov     rax, [rbp+27h+arg_38]
0x180005c6a  mov     [rbp+27h+var_30], r8
0x180005c6e  mov     [rbp+27h+var_24], r10d
0x180005c72  mov     rdx, [rax]
0x180005c75  test    rdx, rdx
0x180005c78  jz      loc_180005DC4
0x180005c7e  mov     rax, rcx
0x180005c81  inc     rax
0x180005c84  cmp     [rdx+rax], r10b
0x180005c88  jnz     short loc_180005C81
0x180005c8a  inc     eax
0x180005c8c  mov     [rbp+27h+var_38], eax
0x180005c8f  mov     rax, [rbp+27h+arg_30]
0x180005c93  mov     [rbp+27h+var_40], rdx
0x180005c97  mov     [rbp+27h+var_34], r10d
0x180005c9b  mov     rdx, [rax]
0x180005c9e  test    rdx, rdx
0x180005ca1  jz      loc_180005DCE
0x180005ca7  mov     rax, rcx
0x180005caa  inc     rax
0x180005cad  cmp     [rdx+rax], r10b
0x180005cb1  jnz     short loc_180005CAA
0x180005cb3  inc     eax
0x180005cb5  mov     [rbp+27h+var_48], eax
0x180005cb8  mov     r8d, 2
0x180005cbe  mov     rax, [rbp+27h+arg_28]
0x180005cc2  mov     [rbp+27h+var_50], rdx
0x180005cc6  mov     [rbp+27h+var_44], r10d
0x180005cca  mov     rdx, [rax]
0x180005ccd  test    rdx, rdx
0x180005cd0  jz      loc_180005DD8
0x180005cd6  mov     rax, rcx
0x180005cd9  inc     rax
0x180005cdc  cmp     [rdx+rax*2], r10w
0x180005ce1  jnz     short loc_180005CD9
0x180005ce3  lea     eax, ds:2[rax*2]
0x180005cea  mov     [rbp+27h+var_58], eax
0x180005ced  mov     rax, [rbp+27h+arg_20]
0x180005cf1  mov     [rbp+27h+var_60], rdx
0x180005cf5  mov     [rbp+27h+var_54], r10d
0x180005cf9  mov     rdx, [rax]
0x180005cfc  test    rdx, rdx
0x180005cff  jz      loc_180005DE7
0x180005d05  inc     rcx
0x180005d08  cmp     [rdx+rcx], r10b
0x180005d0c  jnz     short loc_180005D05
0x180005d0e  inc     ecx
0x180005d10  movzx   eax, byte ptr [r9]
0x180005d14  shl     eax, 18h
0x180005d17  mov     dword ptr [rsp+0E0h+EventDescriptor.Id], eax
0x180005d1b  movzx   eax, word ptr [r9+1]
0x180005d20  mov     dword ptr [rbp+27h+EventDescriptor.Level], eax
0x180005d23  mov     rax, [r9+3]
0x180005d27  mov     [rbp+27h+EventDescriptor.Keyword], rax
0x180005d2b  mov     rax, cs:off_180037058
0x180005d32  mov     [rbp+27h+var_90.Ptr], rax
0x180005d36  mov     [rbp+27h+var_68], ecx
0x180005d39  lea     rcx, [r9+0Bh]
0x180005d3d  mov     [rbp+27h+var_70], rdx
0x180005d41  xor     r9d, r9d; RelatedActivityId
0x180005d44  mov     [rbp+27h+var_64], r10d
0x180005d48  lea     rdx, [rsp+0E0h+EventDescriptor]; EventDescriptor
0x180005d4d  movzx   eax, word ptr [rax]
0x180005d50  mov     [rbp+27h+var_90.Size], eax
0x180005d53  movzx   eax, word ptr [rcx]
0x180005d56  mov     [rbp+27h+var_78], eax
0x180005d59  lea     rax, _TraceLoggingMetadataEnd
0x180005d60  mov     [rbp+27h+var_80], rcx
0x180005d64  lea     rcx, _TraceLoggingMetadata
0x180005d6b  sub     eax, ecx
0x180005d6d  mov     dword ptr [rbp+27h+var_90.0Ch], r8d
0x180005d71  mov     [rbp+27h+var_74], ebx
0x180005d74  xor     r8d, r8d; ActivityId
0x180005d77  mov     [rsp+0E0h+var_B0], eax
0x180005d7b  mov     eax, [rsp+0E0h+var_B0]
0x180005d7f  mov     rcx, cs:RegHandle; RegHandle
0x180005d86  lea     rax, [rbp+27h+var_90]
0x180005d8a  mov     [rsp+0E0h+UserData], rax; UserData
0x180005d8f  mov     [rsp+0E0h+UserDataCount], 8; UserDataCount
0x180005d97  call    cs:__imp_EventWriteTransfer
0x180005d9d  mov     rcx, [rbp+27h+var_10]
0x180005da1  xor     rcx, rsp; StackCookie
0x180005da4  call    __security_check_cookie
0x180005da9  mov     rbx, [rsp+0E0h+arg_0]
0x180005db1  add     rsp, 0E0h
0x180005db8  pop     rbp
0x180005db9  retn
0x180005dba  mov     r8, r11
0x180005dbd  mov     eax, ebx
0x180005dbf  jmp     loc_180005C63
0x180005dc4  mov     rdx, r11
0x180005dc7  mov     eax, ebx
0x180005dc9  jmp     loc_180005C8C
0x180005dce  mov     rdx, r11
0x180005dd1  mov     eax, ebx
0x180005dd3  jmp     loc_180005CB5
0x180005dd8  lea     rdx, qword_18002AF20
0x180005ddf  mov     eax, r8d
0x180005de2  jmp     loc_180005CEA
0x180005de7  mov     rdx, r11
0x180005dea  mov     ecx, ebx
0x180005dec  jmp     loc_180005D10
```
