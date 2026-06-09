# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001008`
- end: `0x1400010a8`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `160`
- prototype: ``
- caller_count: `32`
- callee_count: `3`
- tags: ``

## callers

- `0x1400016a0`
- `0x1400018cc`
- `0x140001aac`
- `0x140001bfc`
- `0x140001ed8`
- `0x140002abc`
- `0x140002e68`
- `0x140002ff0`
- `0x1400030dc`
- `0x140003340`
- `0x1400037a4`
- `0x140003dac`
- `0x140003f18`
- `0x140004330`
- `0x140004800`
- `0x140004a84`
- `0x140005034`
- `0x140005874`
- `0x140006afc`
- `0x140006cc4`
- `0x140006e28`
- `0x140007280`
- `0x140007da0`
- `0x14000810c`
- `0x1400081ec`
- `0x1400083a0`
- `0x14000865c`
- `0x140008798`
- `0x140008878`
- `0x1400089c8`
- `0x140008ac4`
- `0x14001903c`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x14000a680`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6)
{
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  int *v11; // [rsp+50h] [rbp-38h]
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
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &dword_14000C864;
    v8 = 1;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 88h
0x14000100f  mov     rax, cs:__security_cookie
0x140001016  xor     rax, rsp
0x140001019  mov     [rsp+88h+var_18], rax
0x14000101e  mov     rax, [rsp+88h+arg_28]
0x140001026  xor     r8d, r8d; int
0x140001029  mov     [rsp+88h+var_28], rax
0x14000102e  mov     r9d, 4
0x140001034  mov     rax, [rsp+88h+arg_20]
0x14000103c  mov     [rsp+88h+var_20], r9
0x140001041  mov     rcx, [rax]
0x140001044  test    rcx, rcx
0x140001047  jz      short loc_14000105A
0x140001049  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000104d  inc     rax
0x140001050  cmp     [rcx+rax], r8b
0x140001054  jnz     short loc_14000104D
0x140001056  inc     eax
0x140001058  jmp     short loc_140001066
0x14000105a  lea     rcx, dword_14000C864
0x140001061  mov     eax, 1
0x140001066  mov     [rsp+88h+var_30], eax
0x14000106a  lea     rax, [rsp+88h+var_58]
0x14000106f  mov     [rsp+88h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x140001074  mov     [rsp+88h+var_68], r9d; ULONG
0x140001079  xor     r9d, r9d; int
0x14000107c  mov     [rsp+88h+var_38], rcx
0x140001081  lea     rcx, dword_140012050; int
0x140001088  mov     [rsp+88h+var_2C], r8d
0x14000108d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001092  mov     rcx, [rsp+88h+var_18]
0x140001097  xor     rcx, rsp; StackCookie
0x14000109a  call    __security_check_cookie
0x14000109f  add     rsp, 88h
0x1400010a6  retn
```
