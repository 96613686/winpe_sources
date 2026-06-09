# RevokableAccessor::RevokableAccessor(void)

- ea: `0x18000f850`
- end: `0x18000f8e1`
- name: `??0RevokableAccessor@@QEAA@XZ`
- size: `145`
- prototype: `RevokableAccessor *__fastcall(RevokableAccessor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800051b4`

## callees

- `0x180001230`
- `0x18000257c`
- `0x18000f850`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18000f891`
- `KERNEL32!CreateMutexW` at `0x18000f891`

## pseudocode

```c
RevokableAccessor *__fastcall RevokableAccessor::RevokableAccessor(RevokableAccessor *this)
{
  _DWORD *v2; // rax
  HANDLE MutexW; // rax
  int pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+24h] [rbp-14h] BYREF
  int v7; // [rsp+28h] [rbp-10h] BYREF

  try
  {
    v2 = operator new[](8u);
  }
  catch ( std::bad_alloc )
  {
    v7 = 0;
    throw (TestException *)&v7;
  }
  *(_QWORD *)this = v2;
  if ( !v2 )
  {
    pExceptionObject = 0;
    throw (TestException *)&pExceptionObject;
  }
  *((_QWORD *)this + 1) = v2;
  *((_QWORD *)this + 2) = v2 + 1;
  *v2 = 0;
  **((_DWORD **)this + 2) = 1;
  MutexW = CreateMutexW(0, 0, 0);
  *((_QWORD *)this + 4) = MutexW;
  if ( MutexW == (HANDLE)-1LL )
  {
    v6 = 1;
    throw (TestException *)&v6;
  }
  *((_DWORD *)this + 6) = 1;
  return this;
}

```

## disassembly

```asm
0x18000f850  push    rbx
0x18000f852  sub     rsp, 30h
0x18000f856  mov     rbx, rcx
0x18000f859  mov     ecx, 8; unsigned __int64
0x18000f85e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f863  mov     rcx, rax
0x18000f866  mov     [rbx], rax
0x18000f869  test    rcx, rcx
0x18000f86c  jz      short loc_18000F8B1
0x18000f86e  mov     [rbx+8], rcx
0x18000f872  add     rax, 4
0x18000f876  mov     [rbx+10h], rax
0x18000f87a  mov     dword ptr [rcx], 0
0x18000f880  mov     rax, [rbx+10h]
0x18000f884  mov     dword ptr [rax], 1
0x18000f88a  xor     r8d, r8d; lpName
0x18000f88d  xor     edx, edx; bInitialOwner
0x18000f88f  xor     ecx, ecx; lpMutexAttributes
0x18000f891  call    cs:__imp_CreateMutexW
0x18000f897  mov     [rbx+20h], rax
0x18000f89b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f89f  jz      short loc_18000F8C7
0x18000f8a1  mov     dword ptr [rbx+18h], 1
0x18000f8a8  mov     rax, rbx
0x18000f8ab  add     rsp, 30h
0x18000f8af  pop     rbx
0x18000f8b0  retn
0x18000f8b1  mov     [rsp+38h+pExceptionObject], ecx
0x18000f8b5  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000f8bc  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000f8c1  call    _CxxThrowException_0
0x18000f8c7  mov     [rsp+38h+var_14], 1
0x18000f8cf  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000f8d6  lea     rcx, [rsp+38h+var_14]; pExceptionObject
0x18000f8db  call    _CxxThrowException_0
```
