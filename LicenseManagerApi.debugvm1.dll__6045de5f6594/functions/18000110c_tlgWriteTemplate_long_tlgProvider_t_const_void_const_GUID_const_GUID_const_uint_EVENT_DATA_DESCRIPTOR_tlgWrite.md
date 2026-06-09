# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000110c`
- end: `0x1800011cd`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010710`
- `0x1800109a0`

## callees

- `0x18000110c`
- `0x180001298`
- `0x180001960`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        void **a5,
        __int64 a6,
        __int64 a7)
{
  _WORD *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-68h] BYREF
  _WORD *v12; // [rsp+50h] [rbp-48h]
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
    while ( v7[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &unk_180016038;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001A010, a2, 0, 0, 5u, &v11);
}

```

## disassembly

```asm
0x18000110c  mov     r11, rsp
0x18000110f  sub     rsp, 98h
0x180001116  mov     rax, cs:__security_cookie
0x18000111d  xor     rax, rsp
0x180001120  mov     [rsp+98h+var_18], rax
0x180001128  mov     rax, [rsp+98h+arg_30]
0x180001130  xor     r8d, r8d
0x180001133  mov     [r11-28h], rax
0x180001137  mov     rax, [rsp+98h+arg_28]
0x18000113f  mov     [r11-38h], rax
0x180001143  mov     rax, [rsp+98h+arg_20]
0x18000114b  mov     qword ptr [r11-20h], 4
0x180001153  mov     qword ptr [r11-30h], 4
0x18000115b  mov     rcx, [rax]
0x18000115e  test    rcx, rcx
0x180001161  jz      short loc_18000117A
0x180001163  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001167  inc     rax
0x18000116a  cmp     [rcx+rax*2], r8w
0x18000116f  jnz     short loc_180001167
0x180001171  lea     eax, ds:2[rax*2]
0x180001178  jmp     short loc_180001186
0x18000117a  lea     rcx, unk_180016038
0x180001181  mov     eax, 2
0x180001186  mov     [rsp+98h+var_40], eax
0x18000118a  xor     r9d, r9d
0x18000118d  lea     rax, [rsp+98h+var_68]
0x180001192  mov     [rsp+98h+var_48], rcx
0x180001197  mov     [rsp+98h+var_70], rax
0x18000119c  lea     rcx, dword_18001A010
0x1800011a3  mov     [rsp+98h+var_78], 5
0x1800011ab  mov     [rsp+98h+var_3C], r8d
0x1800011b0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011b5  mov     rcx, [rsp+98h+var_18]
0x1800011bd  xor     rcx, rsp; StackCookie
0x1800011c0  call    __security_check_cookie
0x1800011c5  add     rsp, 98h
0x1800011cc  retn
```
