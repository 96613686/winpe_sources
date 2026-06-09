# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001308`
- end: `0x180001454`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z`
- size: `332`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, int **, int **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f5b4`

## callees

- `0x180001308`
- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001439`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001439`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int **a7,
        int **a8)
{
  __int64 v9; // rcx
  int *v11; // r8
  __int64 v12; // rax
  int v13; // eax
  int *v14; // rdx
  int v15; // ecx
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

  v9 = -1;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &dword_18003A074;
    v13 = 2;
  }
  v30 = v13;
  v29 = v11;
  v31 = 0;
  v14 = *a7;
  if ( *a7 )
  {
    do
      ++v9;
    while ( *((_WORD *)v14 + v9) );
    v15 = 2 * v9 + 2;
  }
  else
  {
    v14 = &dword_18003A074;
    v15 = 2;
  }
  v24 = a6;
  v22 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v27 = v15;
  v26 = v14;
  v28 = 0;
  v25 = 4;
  v23 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v20 = *(unsigned __int16 *)(a2 + 11);
  v19 = a2 + 11;
  UserData.Reserved = 2;
  v21 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 6u, &UserData);
}

```

## disassembly

```asm
0x180001308  push    rbp
0x18000130a  lea     rbp, [rsp-37h]
0x18000130f  sub     rsp, 0C0h
0x180001316  mov     rax, cs:__security_cookie
0x18000131d  xor     rax, rsp
0x180001320  mov     [rbp+37h+var_10], rax
0x180001324  mov     rax, [rbp+37h+arg_38]
0x180001328  mov     r10, rcx
0x18000132b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000132f  xor     r11d, r11d
0x180001332  mov     r9, rdx
0x180001335  mov     r8, [rax]
0x180001338  test    r8, r8
0x18000133b  jz      short loc_180001353
0x18000133d  mov     rax, rcx
0x180001340  inc     rax
0x180001343  cmp     [r8+rax*2], r11w
0x180001348  jnz     short loc_180001340
0x18000134a  lea     eax, ds:2[rax*2]
0x180001351  jmp     short loc_18000135F
0x180001353  lea     r8, dword_18003A074
0x18000135a  mov     eax, 2
0x18000135f  mov     [rbp+37h+var_18], eax
0x180001362  mov     rax, [rbp+37h+arg_30]
0x180001366  mov     [rbp+37h+var_20], r8
0x18000136a  mov     [rbp+37h+var_14], r11d
0x18000136e  mov     rdx, [rax]
0x180001371  test    rdx, rdx
0x180001374  jz      short loc_180001389
0x180001376  inc     rcx
0x180001379  cmp     [rdx+rcx*2], r11w
0x18000137e  jnz     short loc_180001376
0x180001380  lea     ecx, ds:2[rcx*2]
0x180001387  jmp     short loc_180001395
0x180001389  lea     rdx, dword_18003A074
0x180001390  mov     ecx, 2
0x180001395  mov     rax, [rbp+37h+arg_28]
0x180001399  xor     r8d, r8d; ActivityId
0x18000139c  mov     [rbp+37h+var_40], rax
0x1800013a0  mov     rax, [rbp+37h+arg_20]
0x1800013a4  mov     [rbp+37h+var_50], rax
0x1800013a8  movzx   eax, byte ptr [r9]
0x1800013ac  shl     eax, 18h
0x1800013af  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x1800013b2  movzx   eax, word ptr [r9+1]
0x1800013b7  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x1800013ba  mov     rax, [r9+3]
0x1800013be  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x1800013c2  mov     rax, [r10+8]
0x1800013c6  mov     [rbp+37h+var_70.Ptr], rax
0x1800013ca  mov     [rbp+37h+var_28], ecx
0x1800013cd  lea     rcx, [r9+0Bh]
0x1800013d1  mov     [rbp+37h+var_30], rdx
0x1800013d5  xor     r9d, r9d; RelatedActivityId
0x1800013d8  mov     [rbp+37h+var_24], r11d
0x1800013dc  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x1800013e0  mov     [rbp+37h+var_38], 4
0x1800013e8  mov     [rbp+37h+var_48], 8
0x1800013f0  movzx   eax, word ptr [rax]
0x1800013f3  mov     [rbp+37h+var_70.Size], eax
0x1800013f6  movzx   eax, word ptr [rcx]
0x1800013f9  mov     [rbp+37h+var_58], eax
0x1800013fc  lea     rax, _TraceLoggingMetadataEnd
0x180001403  mov     [rbp+37h+var_60], rcx
0x180001407  lea     rcx, _TraceLoggingMetadata
0x18000140e  sub     eax, ecx
0x180001410  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x180001417  mov     [rbp+37h+var_54], 1
0x18000141e  mov     [rbp+37h+var_90], eax
0x180001421  mov     eax, [rbp+37h+var_90]
0x180001424  mov     rcx, [r10+20h]; RegHandle
0x180001428  lea     rax, [rbp+37h+var_70]
0x18000142c  mov     [rsp+0C0h+UserData], rax; UserData
0x180001431  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x180001439  call    cs:__imp_EventWriteTransfer
0x18000143f  mov     rcx, [rbp+37h+var_10]
0x180001443  xor     rcx, rsp; StackCookie
0x180001446  call    __security_check_cookie
0x18000144b  add     rsp, 0C0h
0x180001452  pop     rbp
0x180001453  retn
```
