# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001008`
- end: `0x1800010c8`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800033b8`
- `0x18000344c`

## callees

- `0x180001008`
- `0x180001a4c`
- `0x180002300`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6,
        __int64 a7)
{
  int *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  int *v13; // [rsp+50h] [rbp-48h]
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
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &dword_180013CCC;
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
0x180001060  jz      short loc_180001079
0x180001062  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001066  inc     rax
0x180001069  cmp     [rcx+rax*2], r8w
0x18000106e  jnz     short loc_180001066
0x180001070  lea     eax, ds:2[rax*2]
0x180001077  jmp     short loc_180001085
0x180001079  lea     rcx, dword_180013CCC
0x180001080  mov     eax, 2
0x180001085  mov     [rsp+98h+var_40], eax
0x180001089  xor     r9d, r9d
0x18000108c  lea     rax, [rsp+98h+var_68]
0x180001091  mov     [rsp+98h+var_48], rcx
0x180001096  mov     [rsp+98h+var_70], rax
0x18000109b  mov     rcx, r10
0x18000109e  mov     [rsp+98h+var_78], 5
0x1800010a6  mov     [rsp+98h+var_3C], r8d
0x1800010ab  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010b0  mov     rcx, [rsp+98h+var_18]
0x1800010b8  xor     rcx, rsp; StackCookie
0x1800010bb  call    __security_check_cookie
0x1800010c0  add     rsp, 98h
0x1800010c7  retn
```
