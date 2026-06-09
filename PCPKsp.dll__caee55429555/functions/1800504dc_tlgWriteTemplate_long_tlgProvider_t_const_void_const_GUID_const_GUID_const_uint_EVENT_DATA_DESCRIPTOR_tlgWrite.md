# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800504dc`
- end: `0x180050642`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@5@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002195c`

## callees

- `0x1800504dc`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180050602`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180050602`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        int **a7,
        int **a8)
{
  __int64 v8; // rcx
  int *v10; // r8
  __int64 v11; // rax
  int v12; // eax
  int *v13; // rdx
  int v14; // ecx
  __int64 v15; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 *v19; // [rsp+60h] [rbp-29h]
  int v20; // [rsp+68h] [rbp-21h]
  int v21; // [rsp+6Ch] [rbp-1Dh]
  __int64 v22; // [rsp+70h] [rbp-19h]
  __int64 v23; // [rsp+78h] [rbp-11h]
  __int64 v24; // [rsp+80h] [rbp-9h]
  __int64 v25; // [rsp+88h] [rbp-1h]
  int *v26; // [rsp+90h] [rbp+7h]
  int v27; // [rsp+98h] [rbp+Fh]
  int v28; // [rsp+9Ch] [rbp+13h]
  int *v29; // [rsp+A0h] [rbp+17h]
  int v30; // [rsp+A8h] [rbp+1Fh]
  int v31; // [rsp+ACh] [rbp+23h]

  v8 = -1;
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
    v10 = &dword_1800DB714;
    v12 = 2;
  }
  v30 = v12;
  v29 = v10;
  v31 = 0;
  v13 = *a7;
  if ( *a7 )
  {
    do
      ++v8;
    while ( *((_WORD *)v13 + v8) );
    v14 = 2 * v8 + 2;
  }
  else
  {
    v13 = &dword_1800DB714;
    v14 = 2;
  }
  v27 = v14;
  v26 = v13;
  v28 = 0;
  v15 = *a6;
  v22 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_1801091E8;
  v24 = v15;
  v25 = 16;
  v23 = 8;
  UserData.Size = *(unsigned __int16 *)off_1801091E8;
  v20 = *(unsigned __int16 *)(a2 + 11);
  v19 = a2 + 11;
  UserData.Reserved = 2;
  v21 = 1;
  return EventWriteTransfer(qword_180109200, &EventDescriptor, 0, 0, 6u, &UserData);
}

```

## disassembly

```asm
0x1800504dc  push    rbp
0x1800504de  lea     rbp, [rsp-37h]
0x1800504e3  sub     rsp, 0C0h
0x1800504ea  mov     rax, cs:__security_cookie
0x1800504f1  xor     rax, rsp
0x1800504f4  mov     [rbp+37h+var_10], rax
0x1800504f8  mov     rax, [rbp+37h+arg_38]
0x1800504fc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180050500  xor     r10d, r10d
0x180050503  mov     r9, rdx
0x180050506  mov     r11d, 2
0x18005050c  mov     r8, [rax]
0x18005050f  test    r8, r8
0x180050512  jz      loc_180050624
0x180050518  mov     rax, rcx
0x18005051b  inc     rax
0x18005051e  cmp     [r8+rax*2], r10w
0x180050523  jnz     short loc_18005051B
0x180050525  lea     eax, ds:2[rax*2]
0x18005052c  mov     [rbp+37h+var_18], eax
0x18005052f  mov     rax, [rbp+37h+arg_30]
0x180050533  mov     [rbp+37h+var_20], r8
0x180050537  mov     [rbp+37h+var_14], r10d
0x18005053b  mov     rdx, [rax]
0x18005053e  test    rdx, rdx
0x180050541  jz      loc_180050633
0x180050547  inc     rcx
0x18005054a  cmp     [rdx+rcx*2], r10w
0x18005054f  jnz     short loc_180050547
0x180050551  lea     ecx, ds:2[rcx*2]
0x180050558  mov     rax, [rbp+37h+arg_28]
0x18005055c  xor     r8d, r8d; ActivityId
0x18005055f  mov     [rbp+37h+var_28], ecx
0x180050562  mov     [rbp+37h+var_30], rdx
0x180050566  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x18005056a  mov     [rbp+37h+var_24], r10d
0x18005056e  mov     rcx, [rax]
0x180050571  mov     rax, [rbp+37h+arg_20]
0x180050575  mov     [rbp+37h+var_50], rax
0x180050579  movzx   eax, byte ptr [r9]
0x18005057d  shl     eax, 18h
0x180050580  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x180050583  movzx   eax, word ptr [r9+1]
0x180050588  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x18005058b  mov     rax, [r9+3]
0x18005058f  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x180050593  mov     rax, cs:off_1801091E8
0x18005059a  mov     [rbp+37h+var_70.Ptr], rax
0x18005059e  mov     [rbp+37h+var_40], rcx
0x1800505a2  lea     rcx, [r9+0Bh]
0x1800505a6  mov     [rbp+37h+var_38], 10h
0x1800505ae  xor     r9d, r9d; RelatedActivityId
0x1800505b1  mov     [rbp+37h+var_48], 8
0x1800505b9  movzx   eax, word ptr [rax]
0x1800505bc  mov     [rbp+37h+var_70.Size], eax
0x1800505bf  movzx   eax, word ptr [rcx]
0x1800505c2  mov     [rbp+37h+var_58], eax
0x1800505c5  lea     rax, _TraceLoggingMetadataEnd
0x1800505cc  mov     [rbp+37h+var_60], rcx
0x1800505d0  lea     rcx, _TraceLoggingMetadata
0x1800505d7  sub     eax, ecx
0x1800505d9  mov     dword ptr [rbp+37h+var_70.0Ch], r11d
0x1800505dd  mov     [rbp+37h+var_54], 1
0x1800505e4  mov     [rbp+37h+var_90], eax
0x1800505e7  mov     eax, [rbp+37h+var_90]
0x1800505ea  mov     rcx, cs:qword_180109200; RegHandle
0x1800505f1  lea     rax, [rbp+37h+var_70]
0x1800505f5  mov     [rsp+0C0h+UserData], rax; UserData
0x1800505fa  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x180050602  call    cs:__imp_EventWriteTransfer
0x180050609  nop     dword ptr [rax+rax+00h]
0x18005060e  mov     rcx, [rbp+37h+var_10]
0x180050612  xor     rcx, rsp; StackCookie
0x180050615  call    __security_check_cookie
0x18005061a  add     rsp, 0C0h
0x180050621  pop     rbp
0x180050622  retn
0x180050624  lea     r8, dword_1800DB714
0x18005062b  mov     eax, r11d
0x18005062e  jmp     loc_18005052C
0x180050633  lea     rdx, dword_1800DB714
0x18005063a  mov     ecx, r11d
0x18005063d  jmp     loc_180050558
```
