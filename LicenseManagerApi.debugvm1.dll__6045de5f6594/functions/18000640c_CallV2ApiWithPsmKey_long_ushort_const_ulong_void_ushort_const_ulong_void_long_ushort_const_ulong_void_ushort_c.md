# CallV2ApiWithPsmKey<long (*)(ushort const *,ulong,void *),ushort const *,ulong &,void * &>(long (*)(ushort const *,ulong,void *),ushort const *,ulong &,void * &)

- ea: `0x18000640c`
- end: `0x180006488`
- name: `??$CallV2ApiWithPsmKey@P6AJPEBGKPEAX@ZPEBGAEAKAEAPEAX@@YAJP6AJPEBGKPEAX@Z0AEAKAEAPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(_BYTE *, _QWORD, _QWORD), __int64, unsigned int *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800106e0`
- `0x180010c90`

## callees

- `0x180001960`
- `0x18000640c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x180006451`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x180006451`

## pseudocode

```c
__int64 __fastcall CallV2ApiWithPsmKey<long (*)(unsigned short const *,unsigned long,void *),unsigned short const *,unsigned long &,void * &>(
        __int64 (__fastcall *a1)(_BYTE *, _QWORD, _QWORD),
        __int64 a2,
        unsigned int *a3,
        _QWORD *a4)
{
  __int64 result; // rax
  int v8[4]; // [rsp+20h] [rbp-208h] BYREF
  _BYTE v9[464]; // [rsp+30h] [rbp-1F8h] BYREF

  v8[0] = 232;
  result = PsmCreateKey(a2, L"LMV1xF00Dx7238", v9, v8);
  if ( (int)result >= 0 )
    return a1(v9, *a3, *a4);
  return result;
}

```

## disassembly

```asm
0x18000640c  push    rbx
0x18000640e  push    rsi
0x18000640f  push    rdi
0x180006410  sub     rsp, 210h
0x180006417  mov     rax, cs:__security_cookie
0x18000641e  xor     rax, rsp
0x180006421  mov     [rsp+228h+var_28], rax
0x180006429  mov     rax, rdx
0x18000642c  mov     [rsp+228h+var_208], 0E8h
0x180006434  mov     rsi, r9
0x180006437  lea     rdx, aLmv1xf00dx7238; "LMV1xF00Dx7238"
0x18000643e  mov     rdi, r8
0x180006441  lea     r9, [rsp+228h+var_208]
0x180006446  mov     rbx, rcx
0x180006449  lea     r8, [rsp+228h+var_1F8]
0x18000644e  mov     rcx, rax
0x180006451  call    cs:__imp_PsmCreateKey
0x180006457  test    eax, eax
0x180006459  js      short loc_18000646D
0x18000645b  mov     r8, [rsi]
0x18000645e  lea     rcx, [rsp+228h+var_1F8]
0x180006463  mov     edx, [rdi]
0x180006465  mov     rax, rbx
0x180006468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000646d  mov     rcx, [rsp+228h+var_28]
0x180006475  xor     rcx, rsp; StackCookie
0x180006478  call    __security_check_cookie
0x18000647d  add     rsp, 210h
0x180006484  pop     rdi
0x180006485  pop     rsi
0x180006486  pop     rbx
0x180006487  retn
```
