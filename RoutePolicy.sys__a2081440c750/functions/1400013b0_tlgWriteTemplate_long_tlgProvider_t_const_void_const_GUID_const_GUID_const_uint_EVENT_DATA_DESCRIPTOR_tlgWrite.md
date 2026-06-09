# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x1400013b0`
- end: `0x140001438`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `136`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400037a4`
- `0x140004330`
- `0x140007280`

## callees

- `0x1400012f0`
- `0x1400013b0`
- `0x14000a680`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5)
{
  int *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  int *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_BYTE *)v5 + v6) );
    v7 = v6 + 1;
  }
  else
  {
    v5 = &dword_14000C864;
    v7 = 1;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x1400013b0  sub     rsp, 78h
0x1400013b4  mov     rax, cs:__security_cookie
0x1400013bb  xor     rax, rsp
0x1400013be  mov     [rsp+78h+var_18], rax
0x1400013c3  mov     rax, [rsp+78h+arg_20]
0x1400013cb  mov     rcx, [rax]
0x1400013ce  test    rcx, rcx
0x1400013d1  jz      short loc_1400013E4
0x1400013d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400013d7  inc     rax
0x1400013da  cmp     byte ptr [rcx+rax], 0
0x1400013de  jnz     short loc_1400013D7
0x1400013e0  inc     eax
0x1400013e2  jmp     short loc_1400013F0
0x1400013e4  lea     rcx, dword_14000C864
0x1400013eb  mov     eax, 1
0x1400013f0  mov     [rsp+78h+var_20], eax
0x1400013f4  xor     r9d, r9d; int
0x1400013f7  lea     rax, [rsp+78h+var_48]
0x1400013fc  mov     [rsp+78h+var_28], rcx
0x140001401  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x140001406  lea     rcx, dword_140012050; int
0x14000140d  xor     r8d, r8d; int
0x140001410  mov     [rsp+78h+var_58], 3; ULONG
0x140001418  mov     [rsp+78h+var_1C], 0
0x140001420  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001425  mov     rcx, [rsp+78h+var_18]
0x14000142a  xor     rcx, rsp; StackCookie
0x14000142d  call    __security_check_cookie
0x140001432  add     rsp, 78h
0x140001436  retn
```
