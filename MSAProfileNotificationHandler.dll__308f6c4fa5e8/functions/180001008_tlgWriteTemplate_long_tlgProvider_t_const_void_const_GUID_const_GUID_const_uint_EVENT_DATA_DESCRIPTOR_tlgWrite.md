# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001008`
- end: `0x1800010c2`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002f8c`
- `0x180003020`

## callees

- `0x180001008`
- `0x1800016fc`
- `0x180001cb0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7)
{
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v13; // [rsp+50h] [rbp-48h]
  int v14; // [rsp+58h] [rbp-40h]
  int v15; // [rsp+5Ch] [rbp-3Ch]
  __int64 v16; // [rsp+60h] [rbp-38h]
  __int64 v17; // [rsp+68h] [rbp-30h]
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int64 v19; // [rsp+78h] [rbp-20h]

  v18 = a7;
  v16 = a6;
  v19 = 8;
  v17 = 4;
  v8 = *a5;
  if ( *a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v8 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v8 = &byte_18000DE48;
    v10 = 1;
  }
  v14 = v10;
  v13 = v8;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5, v12);
}

```

## disassembly

```asm
0x180001008  mov     r11, rsp
0x18000100b  sub     rsp, 98h
0x180001012  mov     rax, cs:__security_cookie
0x180001019  xor     rax, rsp
0x18000101c  mov     [rsp+98h+var_18], rax
0x180001024  mov     rax, [rsp+98h+arg_30]
0x18000102c  mov     r10, rcx
0x18000102f  mov     [r11-28h], rax
0x180001033  xor     r8d, r8d
0x180001036  mov     rax, [rsp+98h+arg_28]
0x18000103e  mov     [r11-38h], rax
0x180001042  mov     rax, [rsp+98h+arg_20]
0x18000104a  mov     qword ptr [r11-20h], 8
0x180001052  mov     qword ptr [r11-30h], 4
0x18000105a  mov     rcx, [rax]
0x18000105d  test    rcx, rcx
0x180001060  jz      short loc_180001073
0x180001062  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001066  inc     rax
0x180001069  cmp     [rcx+rax], r8b
0x18000106d  jnz     short loc_180001066
0x18000106f  inc     eax
0x180001071  jmp     short loc_18000107F
0x180001073  lea     rcx, byte_18000DE48
0x18000107a  mov     eax, 1
0x18000107f  mov     [rsp+98h+var_40], eax
0x180001083  xor     r9d, r9d
0x180001086  lea     rax, [rsp+98h+var_68]
0x18000108b  mov     [rsp+98h+var_48], rcx
0x180001090  mov     [rsp+98h+var_70], rax
0x180001095  mov     rcx, r10
0x180001098  mov     [rsp+98h+var_78], 5
0x1800010a0  mov     [rsp+98h+var_3C], r8d
0x1800010a5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010aa  mov     rcx, [rsp+98h+var_18]
0x1800010b2  xor     rcx, rsp; StackCookie
0x1800010b5  call    __security_check_cookie
0x1800010ba  add     rsp, 98h
0x1800010c1  retn
```
