# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x140001abc`
- end: `0x140001b46`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b614`
- `0x14000b684`
- `0x14000b6f4`
- `0x14000b764`

## callees

- `0x14000198c`
- `0x140001abc`
- `0x140002a30`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  _BYTE v9[32]; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &dword_1400158BC;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140020038, a2, 0, 0, 3, v9);
}

```

## disassembly

```asm
0x140001abc  sub     rsp, 78h
0x140001ac0  mov     rax, cs:__security_cookie
0x140001ac7  xor     rax, rsp
0x140001aca  mov     [rsp+78h+var_18], rax
0x140001acf  mov     rax, [rsp+78h+arg_20]
0x140001ad7  xor     r8d, r8d
0x140001ada  mov     rcx, [rax]
0x140001add  test    rcx, rcx
0x140001ae0  jz      short loc_140001AF9
0x140001ae2  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001ae6  inc     rax
0x140001ae9  cmp     [rcx+rax*2], r8w
0x140001aee  jnz     short loc_140001AE6
0x140001af0  lea     eax, ds:2[rax*2]
0x140001af7  jmp     short loc_140001B05
0x140001af9  lea     rcx, dword_1400158BC
0x140001b00  mov     eax, 2
0x140001b05  mov     [rsp+78h+var_20], eax
0x140001b09  xor     r9d, r9d
0x140001b0c  lea     rax, [rsp+78h+var_48]
0x140001b11  mov     [rsp+78h+var_28], rcx
0x140001b16  mov     [rsp+78h+var_50], rax
0x140001b1b  lea     rcx, dword_140020038
0x140001b22  mov     [rsp+78h+var_58], 3
0x140001b2a  mov     [rsp+78h+var_1C], r8d
0x140001b2f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001b34  mov     rcx, [rsp+78h+var_18]
0x140001b39  xor     rcx, rsp; StackCookie
0x140001b3c  call    __security_check_cookie
0x140001b41  add     rsp, 78h
0x140001b45  retn
```
