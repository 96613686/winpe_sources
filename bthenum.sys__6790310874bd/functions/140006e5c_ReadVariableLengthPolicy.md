# ReadVariableLengthPolicy

- ea: `0x140006e5c`
- end: `0x140006fa2`
- name: `ReadVariableLengthPolicy`
- size: `326`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PUNICODE_STRING ValueName@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400072a8`

## callees

- `0x140006e5c`
- `0x14001f5ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006f11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f75`
- `ntoskrnl!ExAllocatePool2` at `0x140006f36`
- `ntoskrnl!ExAllocatePool2` at `0x140006f36`

## pseudocode

```c
__int64 __fastcall ReadVariableLengthPolicy(
        HANDLE KeyHandle,
        PUNICODE_STRING ValueName,
        unsigned int a3,
        __int64 a4,
        PVOID *a5,
        _DWORD *a6)
{
  PVOID *v6; // rdi
  int v7; // r14d
  _DWORD *v8; // rsi
  void *Pool2; // rax
  int KeyValue; // eax
  __int64 v14; // rbx
  unsigned int v15; // ebp
  __int64 v17; // [rsp+98h] [rbp+20h] BYREF

  v6 = a5;
  v7 = 0;
  v8 = a6;
  LODWORD(v17) = 0;
  *a5 = 0;
  Pool2 = 0;
  *v8 = 0;
  while ( 1 )
  {
    KeyValue = BthQueryKeyValueEx(KeyHandle, ValueName, Pool2, (__int64)&v17);
    v14 = (unsigned int)v17;
    v15 = KeyValue;
    if ( KeyValue < 0 )
    {
      if ( KeyValue == -1073741789 || KeyValue == -2147483643 )
        goto LABEL_10;
      goto LABEL_9;
    }
    if ( (_DWORD)v17 == *v8 )
      break;
LABEL_9:
    if ( (_DWORD)v17 == *v8 )
      goto LABEL_20;
LABEL_10:
    if ( (unsigned int)v17 % a3 )
      goto LABEL_21;
    if ( *v6 )
    {
      ExFreePoolWithTag(*v6, 0);
      *v6 = 0;
    }
    if ( (_DWORD)v14 )
    {
      Pool2 = (void *)ExAllocatePool2(64, v14, 1953329250);
      *v6 = Pool2;
      if ( !Pool2 )
        goto LABEL_21;
    }
    else
    {
      Pool2 = 0;
    }
    *v8 = v14;
    if ( v7 == (_DWORD)v14 )
      goto LABEL_20;
    v7 = v14;
  }
  if ( (unsigned int)v17 % a3 )
  {
    v15 = -1073741823;
LABEL_20:
    if ( (v15 & 0x80000000) == 0 )
      return v15;
LABEL_21:
    v15 = -1073741823;
    goto LABEL_22;
  }
  if ( (_DWORD)v17 )
  {
    *v8 = v17;
    return v15;
  }
LABEL_22:
  if ( *v6 )
  {
    ExFreePoolWithTag(*v6, 0);
    *v6 = 0;
  }
  *v8 = 0;
  return v15;
}

```

## disassembly

```asm
0x140006e5c  mov     rax, rsp
0x140006e5f  mov     [rax+20h], r9d
0x140006e63  push    rbx
0x140006e64  push    rbp
0x140006e65  push    rsi
0x140006e66  push    rdi
0x140006e67  push    r12
0x140006e69  push    r13
0x140006e6b  push    r14
0x140006e6d  push    r15
0x140006e6f  sub     rsp, 38h
0x140006e73  mov     rdi, [rsp+78h+arg_20]
0x140006e7b  xor     r14d, r14d
0x140006e7e  mov     rsi, [rsp+78h+arg_28]
0x140006e86  mov     r15d, r8d
0x140006e89  mov     [rax+20h], r14d
0x140006e8d  mov     r12, rdx
0x140006e90  mov     r13, rcx
0x140006e93  mov     ebx, r14d
0x140006e96  mov     [rdi], r14
0x140006e99  mov     eax, r14d
0x140006e9c  mov     [rsi], r14d
0x140006e9f  lea     rcx, [rsp+78h+arg_18]
0x140006ea7  mov     r9d, ebx
0x140006eaa  mov     [rsp+78h+var_58], rcx; __int64
0x140006eaf  mov     r8, rax; void *
0x140006eb2  mov     rcx, r13; KeyHandle
0x140006eb5  mov     rdx, r12; ValueName
0x140006eb8  call    BthQueryKeyValueEx
0x140006ebd  mov     ebx, dword ptr [rsp+78h+arg_18]
0x140006ec4  mov     ebp, eax
0x140006ec6  test    eax, eax
0x140006ec8  js      short loc_140006EEC
0x140006eca  cmp     ebx, [rsi]
0x140006ecc  jnz     short loc_140006EFA
0x140006ece  xor     edx, edx
0x140006ed0  mov     eax, ebx
0x140006ed2  div     r15d
0x140006ed5  test    edx, edx
0x140006ed7  jnz     loc_140006F5D
0x140006edd  test    ebx, ebx
0x140006edf  jz      loc_140006F6B
0x140006ee5  mov     [rsi], ebx
0x140006ee7  jmp     loc_140006F8E
0x140006eec  cmp     eax, 0C0000023h
0x140006ef1  jz      short loc_140006EFE
0x140006ef3  cmp     eax, 80000005h
0x140006ef8  jz      short loc_140006EFE
0x140006efa  cmp     ebx, [rsi]
0x140006efc  jz      short loc_140006F62
0x140006efe  xor     edx, edx; Tag
0x140006f00  mov     eax, ebx
0x140006f02  div     r15d
0x140006f05  test    edx, edx
0x140006f07  jnz     short loc_140006F66
0x140006f09  mov     rcx, [rdi]; P
0x140006f0c  test    rcx, rcx
0x140006f0f  jz      short loc_140006F24
0x140006f11  call    cs:__imp_ExFreePoolWithTag
0x140006f18  nop     dword ptr [rax+rax+00h]
0x140006f1d  mov     qword ptr [rdi], 0
0x140006f24  test    ebx, ebx
0x140006f26  jz      short loc_140006F4C
0x140006f28  mov     rdx, rbx
0x140006f2b  mov     ecx, 40h ; '@'
0x140006f30  mov     r8d, 746D7062h
0x140006f36  call    cs:__imp_ExAllocatePool2
0x140006f3d  nop     dword ptr [rax+rax+00h]
0x140006f42  mov     [rdi], rax
0x140006f45  test    rax, rax
0x140006f48  jz      short loc_140006F66
0x140006f4a  jmp     short loc_140006F4E
0x140006f4c  xor     eax, eax
0x140006f4e  mov     [rsi], ebx
0x140006f50  cmp     r14d, ebx
0x140006f53  jz      short loc_140006F62
0x140006f55  mov     r14d, ebx
0x140006f58  jmp     loc_140006E9F
0x140006f5d  mov     ebp, 0C0000001h
0x140006f62  test    ebp, ebp
0x140006f64  jns     short loc_140006F8E
0x140006f66  mov     ebp, 0C0000001h
0x140006f6b  mov     rcx, [rdi]; P
0x140006f6e  test    rcx, rcx
0x140006f71  jz      short loc_140006F88
0x140006f73  xor     edx, edx; Tag
0x140006f75  call    cs:__imp_ExFreePoolWithTag
0x140006f7c  nop     dword ptr [rax+rax+00h]
0x140006f81  mov     qword ptr [rdi], 0
0x140006f88  mov     dword ptr [rsi], 0
0x140006f8e  mov     eax, ebp
0x140006f90  add     rsp, 38h
0x140006f94  pop     r15
0x140006f96  pop     r14
0x140006f98  pop     r13
0x140006f9a  pop     r12
0x140006f9c  pop     rdi
0x140006f9d  pop     rsi
0x140006f9e  pop     rbp
0x140006f9f  pop     rbx
0x140006fa0  retn
```
