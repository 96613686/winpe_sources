# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSid<_SID>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSid<_SID> const &)

- ea: `0x1400010b0`
- end: `0x140001165`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSid@U_SID@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSid@U_SID@@@@@Z`
- size: `181`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400016a0`
- `0x140002138`

## callees

- `0x1400010b0`
- `0x1400012f0`
- `0x14000a680`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSid<_SID>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 *a6)
{
  int v6; // eax
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+5Ch] [rbp-2Ch]
  __int64 v15; // [rsp+60h] [rbp-28h]
  int v16; // [rsp+68h] [rbp-20h]
  int v17; // [rsp+6Ch] [rbp-1Ch]

  v6 = *(unsigned __int8 *)(*a6 + 1);
  v15 = *a6;
  v17 = 0;
  v16 = 4 * v6 + 8;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &qword_14000C868;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, a2, 0, 0, 4u, &v11);
}

```

## disassembly

```asm
0x1400010b0  sub     rsp, 88h
0x1400010b7  mov     rax, cs:__security_cookie
0x1400010be  xor     rax, rsp
0x1400010c1  mov     [rsp+88h+var_18], rax
0x1400010c6  mov     rax, [rsp+88h+arg_28]
0x1400010ce  xor     r8d, r8d; int
0x1400010d1  mov     rcx, [rax]
0x1400010d4  movzx   eax, byte ptr [rcx+1]
0x1400010d8  mov     [rsp+88h+var_28], rcx
0x1400010dd  mov     [rsp+88h+var_1C], r8d
0x1400010e2  lea     eax, ds:8[rax*4]
0x1400010e9  mov     [rsp+88h+var_20], eax
0x1400010ed  mov     rax, [rsp+88h+arg_20]
0x1400010f5  mov     rcx, [rax]
0x1400010f8  test    rcx, rcx
0x1400010fb  jz      short loc_140001114
0x1400010fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001101  inc     rax
0x140001104  cmp     [rcx+rax*2], r8w
0x140001109  jnz     short loc_140001101
0x14000110b  lea     eax, ds:2[rax*2]
0x140001112  jmp     short loc_140001120
0x140001114  lea     rcx, qword_14000C868
0x14000111b  mov     eax, 2
0x140001120  mov     [rsp+88h+var_30], eax
0x140001124  xor     r9d, r9d; int
0x140001127  lea     rax, [rsp+88h+var_58]
0x14000112c  mov     [rsp+88h+var_38], rcx
0x140001131  mov     [rsp+88h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x140001136  lea     rcx, dword_140012050; int
0x14000113d  mov     [rsp+88h+var_68], 4; ULONG
0x140001145  mov     [rsp+88h+var_2C], r8d
0x14000114a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000114f  mov     rcx, [rsp+88h+var_18]
0x140001154  xor     rcx, rsp; StackCookie
0x140001157  call    __security_check_cookie
0x14000115c  add     rsp, 88h
0x140001163  retn
```
