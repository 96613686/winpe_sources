# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001304`
- end: `0x1800013c0`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `188`
- prototype: ``
- caller_count: `169`
- callee_count: `3`
- tags: ``

## callers

- `0x180004124`
- `0x1800046f4`
- `0x180004990`
- `0x180004c30`
- `0x180004eec`
- `0x1800050c0`
- `0x180005200`
- `0x180005740`
- `0x180005eb0`
- `0x18000739c`
- `0x180007ec0`
- `0x180009510`
- `0x180009f90`
- `0x18000a1a0`
- `0x18000a340`
- `0x18000a5a0`
- `0x18000ac9c`
- `0x18000b700`
- `0x18000c150`
- `0x18000c1d4`
- `0x18000c258`
- `0x18000c440`
- `0x18000c848`
- `0x18000c9ac`
- `0x18000cc28`
- `0x18000d56c`
- `0x18000da08`
- `0x18000dad8`
- `0x18000dba8`
- `0x18000ded0`
- `0x18000e1dc`
- `0x18000e4ec`
- `0x18000f244`
- `0x18000f800`
- `0x1800100ec`
- `0x180010204`
- `0x18001030c`
- `0x1800103f4`
- `0x180010478`
- `0x1800104fc`
- `0x180010580`
- `0x180010604`
- `0x180010688`
- `0x1800108f4`
- `0x180010dc0`
- `0x180011168`
- `0x180011c7c`
- `0x180011f48`
- `0x1800124e8`
- `0x180012684`

## callees

- `0x180001304`
- `0x180001414`
- `0x18004c8e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 a7)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v12; // [rsp+50h] [rbp-48h]
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
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &qword_1800528B8;
    v9 = 1;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_GameInputEventWriteTransfer((__int64)&dword_180069000, a2, 0, 0, 5, (__int64)v11);
}

```

## disassembly

```asm
0x180001304  mov     r11, rsp
0x180001307  sub     rsp, 98h
0x18000130e  mov     rax, cs:__security_cookie
0x180001315  xor     rax, rsp
0x180001318  mov     [rsp+98h+var_18], rax
0x180001320  mov     rax, [rsp+98h+arg_30]
0x180001328  xor     r8d, r8d
0x18000132b  mov     [r11-28h], rax
0x18000132f  mov     rax, [rsp+98h+arg_28]
0x180001337  mov     [r11-38h], rax
0x18000133b  mov     rax, [rsp+98h+arg_20]
0x180001343  mov     qword ptr [r11-20h], 4
0x18000134b  mov     qword ptr [r11-30h], 4
0x180001353  mov     rcx, [rax]
0x180001356  test    rcx, rcx
0x180001359  jz      short loc_18000136C
0x18000135b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000135f  inc     rax
0x180001362  cmp     [rcx+rax], r8b
0x180001366  jnz     short loc_18000135F
0x180001368  inc     eax
0x18000136a  jmp     short loc_180001378
0x18000136c  lea     rcx, qword_1800528B8
0x180001373  mov     eax, 1
0x180001378  mov     [rsp+98h+var_40], eax
0x18000137c  xor     r9d, r9d
0x18000137f  lea     rax, [rsp+98h+var_68]
0x180001384  mov     [rsp+98h+var_48], rcx
0x180001389  mov     [rsp+98h+var_70], rax
0x18000138e  lea     rcx, dword_180069000
0x180001395  mov     [rsp+98h+var_78], 5
0x18000139d  mov     [rsp+98h+var_3C], r8d
0x1800013a2  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x1800013a7  mov     rcx, [rsp+98h+var_18]
0x1800013af  xor     rcx, rsp; StackCookie
0x1800013b2  call    __security_check_cookie
0x1800013b7  add     rsp, 98h
0x1800013be  retn
```
