# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001244`
- end: `0x1400012ea`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400015fc`
- `0x1400020a0`

## callees

- `0x140001244`
- `0x1400012f0`
- `0x14000a680`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6)
{
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+5Ch] [rbp-2Ch]
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]

  v14 = a6;
  v15 = 4;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v6 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &qword_14000C868;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x140001244  sub     rsp, 88h
0x14000124b  mov     rax, cs:__security_cookie
0x140001252  xor     rax, rsp
0x140001255  mov     [rsp+88h+var_18], rax
0x14000125a  mov     rax, [rsp+88h+arg_28]
0x140001262  xor     r8d, r8d; int
0x140001265  mov     [rsp+88h+var_28], rax
0x14000126a  mov     r9d, 4
0x140001270  mov     rax, [rsp+88h+arg_20]
0x140001278  mov     [rsp+88h+var_20], r9
0x14000127d  mov     rcx, [rax]
0x140001280  test    rcx, rcx
0x140001283  jz      short loc_14000129C
0x140001285  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001289  inc     rax
0x14000128c  cmp     [rcx+rax*2], r8w
0x140001291  jnz     short loc_140001289
0x140001293  lea     eax, ds:2[rax*2]
0x14000129a  jmp     short loc_1400012A8
0x14000129c  lea     rcx, qword_14000C868
0x1400012a3  mov     eax, 2
0x1400012a8  mov     [rsp+88h+var_30], eax
0x1400012ac  lea     rax, [rsp+88h+var_58]
0x1400012b1  mov     [rsp+88h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x1400012b6  mov     [rsp+88h+var_68], r9d; ULONG
0x1400012bb  xor     r9d, r9d; int
0x1400012be  mov     [rsp+88h+var_38], rcx
0x1400012c3  lea     rcx, dword_140012050; int
0x1400012ca  mov     [rsp+88h+var_2C], r8d
0x1400012cf  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400012d4  mov     rcx, [rsp+88h+var_18]
0x1400012d9  xor     rcx, rsp; StackCookie
0x1400012dc  call    __security_check_cookie
0x1400012e1  add     rsp, 88h
0x1400012e8  retn
```
