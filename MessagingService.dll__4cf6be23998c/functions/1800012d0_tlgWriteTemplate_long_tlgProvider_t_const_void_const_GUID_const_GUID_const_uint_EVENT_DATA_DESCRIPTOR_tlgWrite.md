# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800012d0`
- end: `0x18000138c`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z`
- size: `188`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, char **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006858`
- `0x1800068a8`

## callees

- `0x18000108c`
- `0x1800012d0`
- `0x18000aa50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char **a6,
        __int64 a7)
{
  char *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+58h] [rbp-40h]
  char *v14; // [rsp+60h] [rbp-38h]
  int v15; // [rsp+68h] [rbp-30h]
  int v16; // [rsp+6Ch] [rbp-2Ch]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v18 = 4;
  v7 = *a6;
  if ( *a6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = v8 + 1;
  }
  else
  {
    v7 = byte_18000F74D;
    v9 = 1;
  }
  v15 = v9;
  v12 = a5;
  v14 = v7;
  v16 = 0;
  v13 = 4;
  return tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, a2, 0, 0, 5u, &v11);
}

```

## disassembly

```asm
0x1800012d0  sub     rsp, 98h
0x1800012d7  mov     rax, cs:__security_cookie
0x1800012de  xor     rax, rsp
0x1800012e1  mov     [rsp+98h+var_18], rax
0x1800012e9  mov     rax, [rsp+98h+arg_30]
0x1800012f1  xor     r8d, r8d; int
0x1800012f4  mov     [rsp+98h+var_28], rax
0x1800012f9  mov     rax, [rsp+98h+arg_28]
0x180001301  mov     [rsp+98h+var_20], 4
0x18000130a  mov     rcx, [rax]
0x18000130d  test    rcx, rcx
0x180001310  jz      short loc_180001323
0x180001312  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001316  inc     rax
0x180001319  cmp     [rcx+rax], r8b
0x18000131d  jnz     short loc_180001316
0x18000131f  inc     eax
0x180001321  jmp     short loc_18000132F
0x180001323  lea     rcx, byte_18000F74D
0x18000132a  mov     eax, 1
0x18000132f  mov     [rsp+98h+var_30], eax
0x180001333  xor     r9d, r9d; int
0x180001336  mov     rax, [rsp+98h+arg_20]
0x18000133e  mov     [rsp+98h+var_48], rax
0x180001343  lea     rax, [rsp+98h+var_68]
0x180001348  mov     [rsp+98h+var_38], rcx
0x18000134d  lea     rcx, dword_180013018; int
0x180001354  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x180001359  mov     [rsp+98h+var_78], 5; ULONG
0x180001361  mov     [rsp+98h+var_2C], r8d
0x180001366  mov     [rsp+98h+var_40], 4
0x18000136f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001374  mov     rcx, [rsp+98h+var_18]
0x18000137c  xor     rcx, rsp; StackCookie
0x18000137f  call    __security_check_cookie
0x180001384  add     rsp, 98h
0x18000138b  retn
```
