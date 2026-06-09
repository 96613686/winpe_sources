# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800011d8`
- end: `0x1800012c9`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64 **, __int64 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800068f8`

## callees

- `0x18000108c`
- `0x1800011d8`
- `0x18000aa50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6,
        __int64 a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rdx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  __int64 *v19; // [rsp+60h] [rbp-38h]
  int v20; // [rsp+68h] [rbp-30h]
  int v21; // [rsp+6Ch] [rbp-2Ch]
  __int64 v22; // [rsp+70h] [rbp-28h]
  __int64 v23; // [rsp+78h] [rbp-20h]

  v22 = a7;
  v8 = -1;
  v23 = 8;
  v9 = 2;
  v10 = *a6;
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &qword_18000F388;
    v12 = 2;
  }
  v20 = v12;
  v19 = v10;
  v21 = 0;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_WORD *)v13 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = &qword_18000F388;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, a2, 0, 0, 5u, &v15);
}

```

## disassembly

```asm
0x1800011d8  sub     rsp, 98h
0x1800011df  mov     rax, cs:__security_cookie
0x1800011e6  xor     rax, rsp
0x1800011e9  mov     [rsp+98h+var_18], rax
0x1800011f1  mov     rax, [rsp+98h+arg_30]
0x1800011f9  xor     r9d, r9d; int
0x1800011fc  mov     [rsp+98h+var_28], rax
0x180001201  mov     r10, rdx
0x180001204  mov     rax, [rsp+98h+arg_28]
0x18000120c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001210  mov     [rsp+98h+var_20], 8
0x180001219  lea     r8d, [r9+2]
0x18000121d  mov     rdx, [rax]
0x180001220  test    rdx, rdx
0x180001223  jz      short loc_18000123B
0x180001225  mov     rax, rcx
0x180001228  inc     rax
0x18000122b  cmp     [rdx+rax*2], r9w
0x180001230  jnz     short loc_180001228
0x180001232  lea     eax, ds:2[rax*2]
0x180001239  jmp     short loc_180001245
0x18000123b  lea     rdx, qword_18000F388
0x180001242  mov     eax, r8d
0x180001245  mov     [rsp+98h+var_30], eax
0x180001249  mov     rax, [rsp+98h+arg_20]
0x180001251  mov     [rsp+98h+var_38], rdx
0x180001256  mov     [rsp+98h+var_2C], r9d
0x18000125b  mov     rdx, [rax]
0x18000125e  test    rdx, rdx
0x180001261  jz      short loc_180001277
0x180001263  inc     rcx
0x180001266  cmp     [rdx+rcx*2], r9w
0x18000126b  jnz     short loc_180001263
0x18000126d  lea     r8d, ds:2[rcx*2]
0x180001275  jmp     short loc_18000127E
0x180001277  lea     rdx, qword_18000F388
0x18000127e  lea     rax, [rsp+98h+var_68]
0x180001283  mov     [rsp+98h+var_48], rdx
0x180001288  mov     [rsp+98h+var_40], r8d
0x18000128d  lea     rcx, dword_180013018; int
0x180001294  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x180001299  xor     r8d, r8d; int
0x18000129c  mov     rdx, r10; int
0x18000129f  mov     [rsp+98h+var_78], 5; ULONG
0x1800012a7  mov     [rsp+98h+var_3C], r9d
0x1800012ac  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012b1  mov     rcx, [rsp+98h+var_18]
0x1800012b9  xor     rcx, rsp; StackCookie
0x1800012bc  call    __security_check_cookie
0x1800012c1  add     rsp, 98h
0x1800012c8  retn
```
