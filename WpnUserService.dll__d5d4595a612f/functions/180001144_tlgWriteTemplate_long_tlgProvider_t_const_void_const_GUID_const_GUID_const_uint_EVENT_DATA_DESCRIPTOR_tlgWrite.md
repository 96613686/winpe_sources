# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001144`
- end: `0x180001204`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 **, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180007e58`
- `0x18000d73c`
- `0x18000d7e0`
- `0x18000d884`

## callees

- `0x180001144`
- `0x180001bdc`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 a7)
{
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v13; // [rsp+50h] [rbp-48h]
  int v14; // [rsp+58h] [rbp-40h]
  int v15; // [rsp+5Ch] [rbp-3Ch]
  __int64 v16; // [rsp+60h] [rbp-38h]
  __int64 v17; // [rsp+68h] [rbp-30h]
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int64 v19; // [rsp+78h] [rbp-20h]

  v18 = a7;
  v16 = a6;
  v19 = 4;
  v17 = 4;
  v8 = *a5;
  if ( *a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &qword_1800142D0;
    v10 = 2;
  }
  v14 = v10;
  v13 = v8;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5, v12);
}

```

## disassembly

```asm
0x180001144  mov     r11, rsp
0x180001147  sub     rsp, 98h
0x18000114e  mov     rax, cs:__security_cookie
0x180001155  xor     rax, rsp
0x180001158  mov     [rsp+98h+var_18], rax
0x180001160  mov     rax, [rsp+98h+arg_30]
0x180001168  mov     r10, rcx
0x18000116b  mov     [r11-28h], rax
0x18000116f  xor     r8d, r8d
0x180001172  mov     rax, [rsp+98h+arg_28]
0x18000117a  mov     [r11-38h], rax
0x18000117e  mov     rax, [rsp+98h+arg_20]
0x180001186  mov     qword ptr [r11-20h], 4
0x18000118e  mov     qword ptr [r11-30h], 4
0x180001196  mov     rcx, [rax]
0x180001199  test    rcx, rcx
0x18000119c  jz      short loc_1800011B5
0x18000119e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011a2  inc     rax
0x1800011a5  cmp     [rcx+rax*2], r8w
0x1800011aa  jnz     short loc_1800011A2
0x1800011ac  lea     eax, ds:2[rax*2]
0x1800011b3  jmp     short loc_1800011C1
0x1800011b5  lea     rcx, qword_1800142D0
0x1800011bc  mov     eax, 2
0x1800011c1  mov     [rsp+98h+var_40], eax
0x1800011c5  xor     r9d, r9d
0x1800011c8  lea     rax, [rsp+98h+var_68]
0x1800011cd  mov     [rsp+98h+var_48], rcx
0x1800011d2  mov     [rsp+98h+var_70], rax
0x1800011d7  mov     rcx, r10
0x1800011da  mov     [rsp+98h+var_78], 5
0x1800011e2  mov     [rsp+98h+var_3C], r8d
0x1800011e7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011ec  mov     rcx, [rsp+98h+var_18]
0x1800011f4  xor     rcx, rsp; StackCookie
0x1800011f7  call    __security_check_cookie
0x1800011fc  add     rsp, 98h
0x180001203  retn
```
