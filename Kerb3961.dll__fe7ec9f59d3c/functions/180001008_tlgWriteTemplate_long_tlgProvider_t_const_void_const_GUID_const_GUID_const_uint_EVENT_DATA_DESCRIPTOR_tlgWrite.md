# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010c9`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b20`

## callees

- `0x180001008`
- `0x18000120c`
- `0x180001d40`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        char **a5,
        __int64 a6,
        __int64 a7)
{
  char *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-68h] BYREF
  char *v12; // [rsp+50h] [rbp-48h]
  int v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+5Ch] [rbp-3Ch]
  __int64 v15; // [rsp+60h] [rbp-38h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v15 = a6;
  v18 = 4;
  v16 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v7[2 * v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = byte_1800205D8;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180029000, a2, 0, 0, 5u, &v11);
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
0x18000102c  xor     r8d, r8d
0x18000102f  mov     [r11-28h], rax
0x180001033  mov     rax, [rsp+98h+arg_28]
0x18000103b  mov     [r11-38h], rax
0x18000103f  mov     rax, [rsp+98h+arg_20]
0x180001047  mov     qword ptr [r11-20h], 4
0x18000104f  mov     qword ptr [r11-30h], 4
0x180001057  mov     rcx, [rax]
0x18000105a  test    rcx, rcx
0x18000105d  jz      short loc_180001076
0x18000105f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001063  inc     rax
0x180001066  cmp     [rcx+rax*2], r8w
0x18000106b  jnz     short loc_180001063
0x18000106d  lea     eax, ds:2[rax*2]
0x180001074  jmp     short loc_180001082
0x180001076  lea     rcx, byte_1800205D8
0x18000107d  mov     eax, 2
0x180001082  mov     [rsp+98h+var_40], eax
0x180001086  xor     r9d, r9d
0x180001089  lea     rax, [rsp+98h+var_68]
0x18000108e  mov     [rsp+98h+var_48], rcx
0x180001093  mov     [rsp+98h+var_70], rax
0x180001098  lea     rcx, dword_180029000
0x18000109f  mov     [rsp+98h+var_78], 5
0x1800010a7  mov     [rsp+98h+var_3C], r8d
0x1800010ac  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010b1  mov     rcx, [rsp+98h+var_18]
0x1800010b9  xor     rcx, rsp; StackCookie
0x1800010bc  call    __security_check_cookie
0x1800010c1  add     rsp, 98h
0x1800010c8  retn
```
