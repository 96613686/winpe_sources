# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001000`
- end: `0x180001160`
- name: `??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z`
- size: `352`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, const wchar_t **, const wchar_t **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008a50`
- `0x180022dd0`
- `0x180024120`

## callees

- `0x180001000`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001142`
- `ADVAPI32!EventWriteTransfer` at `0x180001142`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        const wchar_t **a6)
{
  const wchar_t *v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  bool v11; // zf
  int v12; // ecx
  const wchar_t *v13; // rdx
  int v14; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 *v18; // [rsp+60h] [rbp-48h]
  int v19; // [rsp+68h] [rbp-40h]
  int v20; // [rsp+6Ch] [rbp-3Ch]
  const wchar_t *v21; // [rsp+70h] [rbp-38h]
  int v22; // [rsp+78h] [rbp-30h]
  int v23; // [rsp+7Ch] [rbp-2Ch]
  const wchar_t *v24; // [rsp+80h] [rbp-28h]
  int v25; // [rsp+88h] [rbp-20h]
  int v26; // [rsp+8Ch] [rbp-1Ch]

  v8 = *a6;
  v9 = -1;
  if ( *a6 )
  {
    v10 = -1;
    do
      v11 = v8[++v10] == 0;
    while ( !v11 );
    v12 = 2 * v10 + 2;
  }
  else
  {
    v8 = &Src;
    v12 = 2;
  }
  v25 = v12;
  v24 = v8;
  v26 = 0;
  v13 = *a5;
  if ( *a5 )
  {
    do
      v11 = v13[++v9] == 0;
    while ( !v11 );
    v14 = 2 * v9 + 2;
  }
  else
  {
    v13 = &Src;
    v14 = 2;
  }
  v22 = v14;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v21 = v13;
  v23 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v19 = *(unsigned __int16 *)(a2 + 11);
  v18 = a2 + 11;
  UserData.Reserved = 2;
  v20 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
}

```

## disassembly

```asm
0x180001000  sub     rsp, 0A8h
0x180001007  mov     rax, cs:__security_cookie
0x18000100e  xor     rax, rsp
0x180001011  mov     [rsp+0A8h+var_18], rax
0x180001019  mov     rax, [rsp+0A8h+arg_28]
0x180001021  mov     r9, rdx
0x180001024  mov     r10, rcx
0x180001027  mov     r8, [rax]
0x18000102a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001031  test    r8, r8
0x180001034  jz      short loc_180001056
0x180001036  mov     rcx, rax
0x180001039  nop     dword ptr [rax+00000000h]
0x180001040  cmp     word ptr [r8+rcx*2+2], 0
0x180001047  lea     rcx, [rcx+1]
0x18000104b  jnz     short loc_180001040
0x18000104d  lea     ecx, ds:2[rcx*2]
0x180001054  jmp     short loc_180001062
0x180001056  lea     r8, Src
0x18000105d  mov     ecx, 2
0x180001062  mov     [rsp+0A8h+var_20], ecx
0x180001069  mov     rcx, [rsp+0A8h+arg_20]
0x180001071  mov     [rsp+0A8h+var_28], r8
0x180001079  xor     r8d, r8d; ActivityId
0x18000107c  mov     [rsp+0A8h+var_1C], r8d
0x180001084  mov     rdx, [rcx]
0x180001087  test    rdx, rdx
0x18000108a  jz      short loc_1800010A5
0x18000108c  nop     dword ptr [rax+00h]
0x180001090  cmp     [rdx+rax*2+2], r8w
0x180001096  lea     rax, [rax+1]
0x18000109a  jnz     short loc_180001090
0x18000109c  lea     eax, ds:2[rax*2]
0x1800010a3  jmp     short loc_1800010B1
0x1800010a5  lea     rdx, Src
0x1800010ac  mov     eax, 2
0x1800010b1  mov     [rsp+0A8h+var_30], eax
0x1800010b5  lea     rcx, [r9+0Bh]
0x1800010b9  movzx   eax, byte ptr [r9]
0x1800010bd  shl     eax, 18h
0x1800010c0  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], eax
0x1800010c4  movzx   eax, word ptr [r9+1]
0x1800010c9  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x1800010cd  mov     rax, [r9+3]
0x1800010d1  xor     r9d, r9d; RelatedActivityId
0x1800010d4  mov     [rsp+0A8h+EventDescriptor.Keyword], rax
0x1800010d9  mov     rax, [r10+8]
0x1800010dd  mov     [rsp+0A8h+var_58.Ptr], rax
0x1800010e2  mov     [rsp+0A8h+var_38], rdx
0x1800010e7  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x1800010ec  mov     [rsp+0A8h+var_2C], r8d
0x1800010f1  movzx   eax, word ptr [rax]
0x1800010f4  mov     [rsp+0A8h+var_58.Size], eax
0x1800010f8  movzx   eax, word ptr [rcx]
0x1800010fb  mov     [rsp+0A8h+var_40], eax
0x1800010ff  lea     rax, _TraceLoggingMetadataEnd
0x180001106  mov     [rsp+0A8h+var_48], rcx
0x18000110b  lea     rcx, _TraceLoggingMetadata
0x180001112  sub     eax, ecx
0x180001114  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x18000111c  mov     [rsp+0A8h+var_3C], 1
0x180001124  mov     [rsp+0A8h+var_78], eax
0x180001128  mov     eax, [rsp+0A8h+var_78]
0x18000112c  mov     rcx, [r10+20h]; RegHandle
0x180001130  lea     rax, [rsp+0A8h+var_58]
0x180001135  mov     [rsp+0A8h+UserData], rax; UserData
0x18000113a  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x180001142  call    cs:__imp_EventWriteTransfer
0x180001148  mov     rcx, [rsp+0A8h+var_18]
0x180001150  xor     rcx, rsp; StackCookie
0x180001153  call    __security_check_cookie
0x180001158  add     rsp, 0A8h
0x18000115f  retn
```
