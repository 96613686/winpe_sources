# OpenClientProcessHandle(AlpcImpersonator const &)

- ea: `0x18000d2bc`
- end: `0x18000d377`
- name: `?OpenClientProcessHandle@@YA?AVWin32Handle@@AEBVAlpcImpersonator@@@Z`
- size: `187`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c20c`
- `0x18000ff74`
- `0x180095cac`
- `0x18009664c`
- `0x1800974a8`

## callees

- `0x18000d2bc`
- `0x1800217ac`
- `0x18002faf0`

## import_xrefs

- `ntdll!NtAlpcOpenSenderProcess` at `0x18000d31f`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18000d31f`

## pseudocode

```c
_QWORD *__fastcall OpenClientProcessHandle(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rdx
  signed int v4; // eax
  __int64 v5; // rax
  _QWORD v7[4]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v8; // [rsp+58h] [rbp-18h]
  int v9; // [rsp+88h] [rbp+18h] BYREF
  __int64 v10; // [rsp+90h] [rbp+20h] BYREF

  v2 = *a2;
  v7[0] = 48;
  memset(&v7[1], 0, 24);
  v8 = 0;
  v10 = 0;
  v4 = NtAlpcOpenSenderProcess(&v10, *(_QWORD *)(v2 + 32), *(_QWORD *)(v2 + 40), 0, 64, v7);
  if ( v4 < 0 )
  {
    Exception::Exception((Exception *)&v9, v4 | 0x10000000, v4);
    LogAndThrow<OSException>(&v9, 1668312161, 278);
  }
  v5 = v10;
  *a1 = v10;
  if ( v5 == -1 )
    *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18000d2bc  mov     [rsp-8+arg_0], rbx
0x18000d2c1  push    rbp
0x18000d2c2  mov     rbp, rsp
0x18000d2c5  sub     rsp, 70h
0x18000d2c9  mov     rdx, [rdx]
0x18000d2cc  lea     rax, [rbp+var_38]
0x18000d2d0  mov     [rbp+var_38], 30h ; '0'
0x18000d2d8  xorps   xmm0, xmm0
0x18000d2db  mov     [rbp+var_20], 0
0x18000d2e3  mov     rbx, rcx
0x18000d2e6  mov     [rbp+var_30], 0
0x18000d2ee  lea     rcx, [rbp+arg_10]
0x18000d2f2  mov     [rbp+var_28], 0
0x18000d2fa  xor     r9d, r9d
0x18000d2fd  movdqu  [rbp+var_18], xmm0
0x18000d302  mov     [rbp+arg_10], 0
0x18000d30a  mov     r8, [rdx+28h]
0x18000d30e  mov     rdx, [rdx+20h]
0x18000d312  mov     [rsp+70h+var_48], rax
0x18000d317  mov     [rsp+70h+var_50], 40h ; '@'
0x18000d31f  call    cs:__imp_NtAlpcOpenSenderProcess
0x18000d325  test    eax, eax
0x18000d327  js      short loc_18000D347
0x18000d329  mov     rax, [rbp+arg_10]
0x18000d32d  mov     [rbx], rax
0x18000d330  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d334  jz      short loc_18000D36E
0x18000d336  mov     rax, rbx
0x18000d339  mov     rbx, [rsp+70h+arg_0]
0x18000d341  add     rsp, 70h
0x18000d345  pop     rbp
0x18000d346  retn
0x18000d347  mov     edx, eax
0x18000d349  lea     rcx, [rbp+arg_8]; this
0x18000d34d  bts     edx, 1Ch; int
0x18000d351  mov     r8d, eax; unsigned int
0x18000d354  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18000d359  mov     edx, 63706C61h
0x18000d35e  lea     rcx, [rbp+arg_8]
0x18000d362  mov     r8d, 116h
0x18000d368  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x18000d36e  mov     qword ptr [rbx], 0
0x18000d375  jmp     short loc_18000D336
```
