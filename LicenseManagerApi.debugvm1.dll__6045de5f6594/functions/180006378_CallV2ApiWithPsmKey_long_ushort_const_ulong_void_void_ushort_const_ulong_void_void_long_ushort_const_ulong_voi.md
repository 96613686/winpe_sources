# CallV2ApiWithPsmKey<long (*)(ushort const *,ulong,void *,void *),ushort const *,ulong &,void * &,void * &>(long (*)(ushort const *,ulong,void *,void *),ushort const *,ulong &,void * &,void * &)

- ea: `0x180006378`
- end: `0x180006403`
- name: `??$CallV2ApiWithPsmKey@P6AJPEBGKPEAX1@ZPEBGAEAKAEAPEAXAEAPEAX@@YAJP6AJPEBGKPEAX1@Z0AEAKAEAPEAX4@Z`
- size: `139`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(_BYTE *, _QWORD, _QWORD, _QWORD), __int64, unsigned int *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fd90`
- `0x180010960`

## callees

- `0x180001960`
- `0x180006378`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x1800063c7`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x1800063c7`

## pseudocode

```c
__int64 __fastcall CallV2ApiWithPsmKey<long (*)(unsigned short const *,unsigned long,void *,void *),unsigned short const *,unsigned long &,void * &,void * &>(
        __int64 (__fastcall *a1)(_BYTE *, _QWORD, _QWORD, _QWORD),
        __int64 a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 result; // rax
  int v9[4]; // [rsp+30h] [rbp-218h] BYREF
  _BYTE v10[464]; // [rsp+40h] [rbp-208h] BYREF

  v9[0] = 232;
  result = PsmCreateKey(a2, L"LMV1xF00Dx7238", v10, v9);
  if ( (int)result >= 0 )
    return a1(v10, *a3, *a4, *a5);
  return result;
}

```

## disassembly

```asm
0x180006378  push    rbx
0x18000637a  push    rsi
0x18000637b  push    rdi
0x18000637c  push    r14
0x18000637e  sub     rsp, 228h
0x180006385  mov     rax, cs:__security_cookie
0x18000638c  xor     rax, rsp
0x18000638f  mov     [rsp+248h+var_38], rax
0x180006397  mov     r14, [rsp+248h+arg_20]
0x18000639f  mov     rax, rdx
0x1800063a2  mov     rsi, r9
0x1800063a5  mov     [rsp+248h+var_218], 0E8h
0x1800063ad  mov     rdi, r8
0x1800063b0  lea     r9, [rsp+248h+var_218]
0x1800063b5  mov     rbx, rcx
0x1800063b8  lea     r8, [rsp+248h+var_208]
0x1800063bd  mov     rcx, rax
0x1800063c0  lea     rdx, aLmv1xf00dx7238; "LMV1xF00Dx7238"
0x1800063c7  call    cs:__imp_PsmCreateKey
0x1800063cd  test    eax, eax
0x1800063cf  js      short loc_1800063E6
0x1800063d1  mov     r9, [r14]
0x1800063d4  lea     rcx, [rsp+248h+var_208]
0x1800063d9  mov     r8, [rsi]
0x1800063dc  mov     rax, rbx
0x1800063df  mov     edx, [rdi]
0x1800063e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063e6  mov     rcx, [rsp+248h+var_38]
0x1800063ee  xor     rcx, rsp; StackCookie
0x1800063f1  call    __security_check_cookie
0x1800063f6  add     rsp, 228h
0x1800063fd  pop     r14
0x1800063ff  pop     rdi
0x180006400  pop     rsi
0x180006401  pop     rbx
0x180006402  retn
```
