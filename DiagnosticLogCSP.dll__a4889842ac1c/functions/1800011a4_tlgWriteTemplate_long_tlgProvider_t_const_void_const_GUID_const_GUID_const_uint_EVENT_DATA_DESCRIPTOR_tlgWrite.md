# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800011a4`
- end: `0x180001249`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const WCHAR **, __int64)`
- caller_count: `29`
- callee_count: `3`
- tags: ``

## callers

- `0x18000911c`
- `0x18000baa0`
- `0x18000cd38`
- `0x18000d09c`
- `0x18000d710`
- `0x18000d818`
- `0x18000e054`
- `0x18000e158`
- `0x18000e374`
- `0x18000ea40`
- `0x18000eaf8`
- `0x18000ec90`
- `0x18000ee88`
- `0x18000ef04`
- `0x18000f47c`
- `0x18000f580`
- `0x18000f924`
- `0x180010180`
- `0x180011a8c`
- `0x180011dd0`
- `0x180011e94`
- `0x180012440`
- `0x180012618`
- `0x1800127d4`
- `0x180013090`
- `0x180013820`
- `0x180013b5c`
- `0x180013c54`
- `0x180013e4c`

## callees

- `0x180001104`
- `0x1800011a4`
- `0x180001b60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5,
        __int64 a6)
{
  const WCHAR *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  const WCHAR *v11; // [rsp+50h] [rbp-38h]
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
    while ( v6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &String2;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return ((__int64 (__fastcall *)(int *, __int64, _QWORD, _QWORD, int, _BYTE *))tlgWriteTransfer_EventWriteTransfer)(
           &dword_180048E90,
           a2,
           0,
           0,
           4,
           v10);
}

```

## disassembly

```asm
0x1800011a4  sub     rsp, 88h
0x1800011ab  mov     rax, cs:__security_cookie
0x1800011b2  xor     rax, rsp
0x1800011b5  mov     [rsp+88h+var_18], rax
0x1800011ba  mov     rax, [rsp+88h+arg_28]
0x1800011c2  xor     r8d, r8d
0x1800011c5  mov     [rsp+88h+var_28], rax
0x1800011ca  mov     r9d, 4
0x1800011d0  mov     rax, [rsp+88h+arg_20]
0x1800011d8  mov     [rsp+88h+var_20], r9
0x1800011dd  mov     rcx, [rax]
0x1800011e0  test    rcx, rcx
0x1800011e3  jz      short loc_1800011FC
0x1800011e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011e9  inc     rax
0x1800011ec  cmp     [rcx+rax*2], r8w
0x1800011f1  jnz     short loc_1800011E9
0x1800011f3  lea     eax, ds:2[rax*2]
0x1800011fa  jmp     short loc_180001208
0x1800011fc  lea     rcx, String2
0x180001203  mov     eax, 2
0x180001208  mov     [rsp+88h+var_30], eax
0x18000120c  lea     rax, [rsp+88h+var_58]
0x180001211  mov     [rsp+88h+var_60], rax
0x180001216  mov     [rsp+88h+var_68], r9d
0x18000121b  xor     r9d, r9d
0x18000121e  mov     [rsp+88h+var_38], rcx
0x180001223  lea     rcx, dword_180048E90
0x18000122a  mov     [rsp+88h+var_2C], r8d
0x18000122f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001234  mov     rcx, [rsp+88h+var_18]
0x180001239  xor     rcx, rsp; StackCookie
0x18000123c  call    __security_check_cookie
0x180001241  add     rsp, 88h
0x180001248  retn
```
