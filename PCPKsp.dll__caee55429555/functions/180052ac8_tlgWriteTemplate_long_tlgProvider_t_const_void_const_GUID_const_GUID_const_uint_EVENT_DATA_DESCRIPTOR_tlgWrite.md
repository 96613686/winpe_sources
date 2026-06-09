# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180052ac8`
- end: `0x180052c71`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U2@U2@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@443AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014830`

## callees

- `0x180052ac8`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180052c2e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180052c2e`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  int v20; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-99h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 *v24; // [rsp+60h] [rbp-71h]
  int v25; // [rsp+68h] [rbp-69h]
  int v26; // [rsp+6Ch] [rbp-65h]
  __int64 v27; // [rsp+70h] [rbp-61h]
  __int64 v28; // [rsp+78h] [rbp-59h]
  const unsigned __int16 *v29; // [rsp+80h] [rbp-51h]
  int v30; // [rsp+88h] [rbp-49h]
  int v31; // [rsp+8Ch] [rbp-45h]
  const unsigned __int16 *v32; // [rsp+90h] [rbp-41h]
  int v33; // [rsp+98h] [rbp-39h]
  int v34; // [rsp+9Ch] [rbp-35h]
  const unsigned __int16 *v35; // [rsp+A0h] [rbp-31h]
  int v36; // [rsp+A8h] [rbp-29h]
  int v37; // [rsp+ACh] [rbp-25h]
  __int64 v38; // [rsp+B0h] [rbp-21h]
  __int64 v39; // [rsp+B8h] [rbp-19h]
  __int64 v40; // [rsp+C0h] [rbp-11h]
  __int64 v41; // [rsp+C8h] [rbp-9h]
  __int64 v42; // [rsp+D0h] [rbp-1h]
  __int64 v43; // [rsp+D8h] [rbp+7h]

  v42 = a11;
  v40 = a10;
  v12 = -1;
  v38 = a9;
  v43 = 4;
  v41 = 1;
  v39 = 8;
  v13 = *a8;
  if ( *a8 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &word_1800DBB72;
    v15 = 1;
  }
  v36 = v15;
  v35 = v13;
  v37 = 0;
  v16 = *a7;
  if ( *a7 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_BYTE *)v16 + v17) );
    v18 = v17 + 1;
  }
  else
  {
    v16 = &word_1800DBB72;
    v18 = 1;
  }
  v33 = v18;
  v32 = v16;
  v34 = 0;
  v19 = *a6;
  if ( *a6 )
  {
    do
      ++v12;
    while ( *((_BYTE *)v19 + v12) );
    v20 = v12 + 1;
  }
  else
  {
    v19 = &word_1800DBB72;
    v20 = 1;
  }
  v27 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_1801091B0;
  v30 = v20;
  v29 = v19;
  v31 = 0;
  v28 = 8;
  UserData.Size = *(unsigned __int16 *)off_1801091B0;
  v25 = *(unsigned __int16 *)(a2 + 11);
  v24 = a2 + 11;
  UserData.Reserved = 2;
  v26 = 1;
  return EventWriteTransfer(qword_1801091C8, &EventDescriptor, 0, 0, 9u, &UserData);
}

```

## disassembly

```asm
0x180052ac8  push    rbp
0x180052aca  lea     rbp, [rsp-1Fh]
0x180052acf  sub     rsp, 0F0h
0x180052ad6  mov     rax, cs:__security_cookie
0x180052add  xor     rax, rsp
0x180052ae0  mov     [rbp+1Fh+var_10], rax
0x180052ae4  mov     rax, [rbp+1Fh+arg_50]
0x180052ae8  lea     r11, word_1800DBB72
0x180052aef  mov     [rbp+1Fh+var_20], rax
0x180052af3  xor     r9d, r9d; RelatedActivityId
0x180052af6  mov     rax, [rbp+1Fh+arg_48]
0x180052afa  mov     r8, rdx
0x180052afd  mov     [rbp+1Fh+var_30], rax
0x180052b01  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180052b05  mov     rax, [rbp+1Fh+arg_40]
0x180052b09  mov     [rbp+1Fh+var_40], rax
0x180052b0d  lea     r10d, [r9+1]
0x180052b11  mov     rax, [rbp+1Fh+arg_38]
0x180052b15  mov     [rbp+1Fh+var_18], 4
0x180052b1d  mov     [rbp+1Fh+var_28], r10
0x180052b21  mov     [rbp+1Fh+var_38], 8
0x180052b29  mov     rdx, [rax]
0x180052b2c  test    rdx, rdx
0x180052b2f  jz      loc_180052C50
0x180052b35  mov     rax, rcx
0x180052b38  inc     rax
0x180052b3b  cmp     [rdx+rax], r9b
0x180052b3f  jnz     short loc_180052B38
0x180052b41  inc     eax
0x180052b43  mov     [rbp+1Fh+var_48], eax
0x180052b46  mov     rax, [rbp+1Fh+arg_30]
0x180052b4a  mov     [rbp+1Fh+var_50], rdx
0x180052b4e  mov     [rbp+1Fh+var_44], r9d
0x180052b52  mov     rdx, [rax]
0x180052b55  test    rdx, rdx
0x180052b58  jz      loc_180052C5B
0x180052b5e  mov     rax, rcx
0x180052b61  inc     rax
0x180052b64  cmp     [rdx+rax], r9b
0x180052b68  jnz     short loc_180052B61
0x180052b6a  inc     eax
0x180052b6c  mov     [rbp+1Fh+var_58], eax
0x180052b6f  mov     rax, [rbp+1Fh+arg_28]
0x180052b73  mov     [rbp+1Fh+var_60], rdx
0x180052b77  mov     [rbp+1Fh+var_54], r9d
0x180052b7b  mov     rdx, [rax]
0x180052b7e  test    rdx, rdx
0x180052b81  jz      loc_180052C66
0x180052b87  inc     rcx
0x180052b8a  cmp     [rdx+rcx], r9b
0x180052b8e  jnz     short loc_180052B87
0x180052b90  inc     ecx
0x180052b92  mov     rax, [rbp+1Fh+arg_20]
0x180052b96  mov     [rbp+1Fh+var_80], rax
0x180052b9a  movzx   eax, byte ptr [r8]
0x180052b9e  shl     eax, 18h
0x180052ba1  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x180052ba5  movzx   eax, word ptr [r8+1]
0x180052baa  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x180052bae  mov     rax, [r8+3]
0x180052bb2  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x180052bb7  mov     rax, cs:off_1801091B0
0x180052bbe  mov     [rsp+0F0h+var_A0.Ptr], rax
0x180052bc3  mov     [rbp+1Fh+var_68], ecx
0x180052bc6  lea     rcx, [r8+0Bh]
0x180052bca  mov     [rbp+1Fh+var_70], rdx
0x180052bce  xor     r8d, r8d; ActivityId
0x180052bd1  mov     [rbp+1Fh+var_64], r9d
0x180052bd5  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x180052bda  mov     [rbp+1Fh+var_78], 8
0x180052be2  movzx   eax, word ptr [rax]
0x180052be5  mov     [rbp+1Fh+var_A0.Size], eax
0x180052be8  movzx   eax, word ptr [rcx]
0x180052beb  mov     [rbp+1Fh+var_88], eax
0x180052bee  lea     rax, _TraceLoggingMetadataEnd
0x180052bf5  mov     [rbp+1Fh+var_90], rcx
0x180052bf9  lea     rcx, _TraceLoggingMetadata
0x180052c00  sub     eax, ecx
0x180052c02  mov     dword ptr [rbp+1Fh+var_A0.0Ch], 2
0x180052c09  mov     [rbp+1Fh+var_84], r10d
0x180052c0d  mov     [rsp+0F0h+var_C0], eax
0x180052c11  mov     eax, [rsp+0F0h+var_C0]
0x180052c15  mov     rcx, cs:qword_1801091C8; RegHandle
0x180052c1c  lea     rax, [rsp+0F0h+var_A0]
0x180052c21  mov     [rsp+0F0h+UserData], rax; UserData
0x180052c26  mov     [rsp+0F0h+UserDataCount], 9; UserDataCount
0x180052c2e  call    cs:__imp_EventWriteTransfer
0x180052c35  nop     dword ptr [rax+rax+00h]
0x180052c3a  mov     rcx, [rbp+1Fh+var_10]
0x180052c3e  xor     rcx, rsp; StackCookie
0x180052c41  call    __security_check_cookie
0x180052c46  add     rsp, 0F0h
0x180052c4d  pop     rbp
0x180052c4e  retn
0x180052c50  mov     rdx, r11
0x180052c53  mov     eax, r10d
0x180052c56  jmp     loc_180052B43
0x180052c5b  mov     rdx, r11
0x180052c5e  mov     eax, r10d
0x180052c61  jmp     loc_180052B6C
0x180052c66  mov     rdx, r11
0x180052c69  mov     ecx, r10d
0x180052c6c  jmp     loc_180052B92
```
