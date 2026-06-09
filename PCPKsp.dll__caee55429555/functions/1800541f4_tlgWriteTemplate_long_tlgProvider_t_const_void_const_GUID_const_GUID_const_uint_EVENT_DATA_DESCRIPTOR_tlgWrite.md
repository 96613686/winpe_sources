# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800541f4`
- end: `0x180054375`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@553@Z`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005e744`

## callees

- `0x1800541f4`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054335`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054335`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int **a10)
{
  __int64 v11; // r8
  int *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  int *v15; // rcx
  int v16; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 *v20; // [rsp+60h] [rbp-59h]
  int v21; // [rsp+68h] [rbp-51h]
  int v22; // [rsp+6Ch] [rbp-4Dh]
  int *v23; // [rsp+70h] [rbp-49h]
  int v24; // [rsp+78h] [rbp-41h]
  int v25; // [rsp+7Ch] [rbp-3Dh]
  __int64 v26; // [rsp+80h] [rbp-39h]
  __int64 v27; // [rsp+88h] [rbp-31h]
  __int64 v28; // [rsp+90h] [rbp-29h]
  __int64 v29; // [rsp+98h] [rbp-21h]
  __int64 v30; // [rsp+A0h] [rbp-19h]
  __int64 v31; // [rsp+A8h] [rbp-11h]
  __int64 v32; // [rsp+B0h] [rbp-9h]
  __int64 v33; // [rsp+B8h] [rbp-1h]
  int *v34; // [rsp+C0h] [rbp+7h]
  int v35; // [rsp+C8h] [rbp+Fh]
  int v36; // [rsp+CCh] [rbp+13h]

  v11 = -1;
  v12 = *a10;
  if ( *a10 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &dword_1800DB714;
    v14 = 2;
  }
  v35 = v14;
  v32 = a9;
  v30 = a8;
  v28 = a7;
  v34 = v12;
  v36 = 0;
  v33 = 4;
  v26 = *a6;
  v31 = 4;
  v29 = 4;
  v15 = *a5;
  v27 = 16;
  if ( v15 )
  {
    do
      ++v11;
    while ( *((_WORD *)v15 + v11) );
    v16 = 2 * v11 + 2;
  }
  else
  {
    v15 = &dword_1800DB714;
    v16 = 2;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v23 = v15;
  v24 = v16;
  v25 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v21 = *(unsigned __int16 *)(a2 + 11);
  v20 = a2 + 11;
  UserData.Reserved = 2;
  v22 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 8u, &UserData);
}

```

## disassembly

```asm
0x1800541f4  push    rbp
0x1800541f6  lea     rbp, [rsp-27h]
0x1800541fb  sub     rsp, 0E0h
0x180054202  mov     rax, cs:__security_cookie
0x180054209  xor     rax, rsp
0x18005420c  mov     [rbp+27h+var_10], rax
0x180054210  mov     rax, [rbp+27h+arg_48]
0x180054214  mov     r10, rcx
0x180054217  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005421b  xor     r9d, r9d; RelatedActivityId
0x18005421e  mov     r11d, 2
0x180054224  mov     rcx, [rax]
0x180054227  test    rcx, rcx
0x18005422a  jz      loc_180054357
0x180054230  mov     rax, r8
0x180054233  inc     rax
0x180054236  cmp     [rcx+rax*2], r9w
0x18005423b  jnz     short loc_180054233
0x18005423d  lea     eax, ds:2[rax*2]
0x180054244  mov     [rbp+27h+var_18], eax
0x180054247  mov     rax, [rbp+27h+arg_40]
0x18005424b  mov     [rbp+27h+var_30], rax
0x18005424f  mov     rax, [rbp+27h+arg_38]
0x180054253  mov     [rbp+27h+var_40], rax
0x180054257  mov     rax, [rbp+27h+arg_30]
0x18005425b  mov     [rbp+27h+var_50], rax
0x18005425f  mov     rax, [rbp+27h+arg_28]
0x180054263  mov     [rbp+27h+var_20], rcx
0x180054267  mov     [rbp+27h+var_14], r9d
0x18005426b  mov     [rbp+27h+var_28], 4
0x180054273  mov     rcx, [rax]
0x180054276  mov     rax, [rbp+27h+arg_20]
0x18005427a  mov     [rbp+27h+var_60], rcx
0x18005427e  mov     [rbp+27h+var_38], 4
0x180054286  mov     [rbp+27h+var_48], 4
0x18005428e  mov     rcx, [rax]
0x180054291  mov     [rbp+27h+var_58], 10h
0x180054299  test    rcx, rcx
0x18005429c  jz      loc_180054366
0x1800542a2  inc     r8
0x1800542a5  cmp     [rcx+r8*2], r9w
0x1800542aa  jnz     short loc_1800542A2
0x1800542ac  lea     r8d, ds:2[r8*2]
0x1800542b4  movzx   eax, byte ptr [rdx]
0x1800542b7  shl     eax, 18h
0x1800542ba  mov     dword ptr [rsp+0E0h+EventDescriptor.Id], eax
0x1800542be  movzx   eax, word ptr [rdx+1]
0x1800542c2  mov     dword ptr [rbp+27h+EventDescriptor.Level], eax
0x1800542c5  mov     rax, [rdx+3]
0x1800542c9  mov     [rbp+27h+EventDescriptor.Keyword], rax
0x1800542cd  mov     rax, [r10+8]
0x1800542d1  mov     [rbp+27h+var_90.Ptr], rax
0x1800542d5  mov     [rbp+27h+var_70], rcx
0x1800542d9  lea     rcx, [rdx+0Bh]
0x1800542dd  mov     [rbp+27h+var_68], r8d
0x1800542e1  lea     rdx, [rsp+0E0h+EventDescriptor]; EventDescriptor
0x1800542e6  mov     [rbp+27h+var_64], r9d
0x1800542ea  xor     r8d, r8d; ActivityId
0x1800542ed  movzx   eax, word ptr [rax]
0x1800542f0  mov     [rbp+27h+var_90.Size], eax
0x1800542f3  movzx   eax, word ptr [rcx]
0x1800542f6  mov     [rbp+27h+var_78], eax
0x1800542f9  lea     rax, _TraceLoggingMetadataEnd
0x180054300  mov     [rbp+27h+var_80], rcx
0x180054304  lea     rcx, _TraceLoggingMetadata
0x18005430b  sub     eax, ecx
0x18005430d  mov     dword ptr [rbp+27h+var_90.0Ch], r11d
0x180054311  mov     [rbp+27h+var_74], 1
0x180054318  mov     [rsp+0E0h+var_B0], eax
0x18005431c  mov     eax, [rsp+0E0h+var_B0]
0x180054320  mov     rcx, [r10+20h]; RegHandle
0x180054324  lea     rax, [rbp+27h+var_90]
0x180054328  mov     [rsp+0E0h+UserData], rax; UserData
0x18005432d  mov     [rsp+0E0h+UserDataCount], 8; UserDataCount
0x180054335  call    cs:__imp_EventWriteTransfer
0x18005433c  nop     dword ptr [rax+rax+00h]
0x180054341  mov     rcx, [rbp+27h+var_10]
0x180054345  xor     rcx, rsp; StackCookie
0x180054348  call    __security_check_cookie
0x18005434d  add     rsp, 0E0h
0x180054354  pop     rbp
0x180054355  retn
0x180054357  lea     rcx, dword_1800DB714
0x18005435e  mov     eax, r11d
0x180054361  jmp     loc_180054244
0x180054366  lea     rcx, dword_1800DB714
0x18005436d  mov     r8d, r11d
0x180054370  jmp     loc_1800542B4
```
