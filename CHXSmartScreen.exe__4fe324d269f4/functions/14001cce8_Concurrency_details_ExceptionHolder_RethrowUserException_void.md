# Concurrency::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x14001cce8`
- end: `0x14001cd62`
- name: `?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ`
- size: `122`
- prototype: `void __fastcall(Concurrency::details::_ExceptionHolder *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001d380`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x14001cce8`

## import_xrefs

- `msvcrt!__ExceptionPtrDestroy` at `0x14001cd37`
- `msvcrt!__ExceptionPtrDestroy` at `0x14001cd37`
- `msvcrt!__ExceptionPtrCopy` at `0x14001cd16`
- `msvcrt!__ExceptionPtrCopy` at `0x14001cd16`
- `msvcrt!__ExceptionPtrRethrow` at `0x14001cd2b`
- `msvcrt!__ExceptionPtrRethrow` at `0x14001cd2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_ExceptionHolder::_RethrowUserException(
        Concurrency::details::_ExceptionHolder *this)
{
  signed __int32 v1; // eax
  signed __int32 v2; // ett
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF
  _BYTE *pExceptionObject; // [rsp+40h] [rbp+8h] BYREF

  _m_prefetchw(this);
  v1 = *(_DWORD *)this;
  do
  {
    v2 = v1;
    v1 = _InterlockedCompareExchange((volatile signed __int32 *)this, v1, v1);
  }
  while ( v2 != v1 );
  if ( !v1 )
    _InterlockedExchange((volatile __int32 *)this, 1);
  if ( *((_QWORD *)this + 3) )
  {
    pExceptionObject = (_BYTE *)__abi_winrt_ptr_ctor(*((_QWORD *)this + 3));
    throw (Platform::Exception **)&pExceptionObject;
  }
  __ExceptionPtrCopy(v3, (char *)this + 8);
  pExceptionObject = v3;
  __ExceptionPtrRethrow(v3);
  __ExceptionPtrDestroy(v3);
}

```

## disassembly

```asm
0x14001cce8  sub     rsp, 38h
0x14001ccec  prefetchw byte ptr [rcx]
0x14001ccef  mov     eax, [rcx]
0x14001ccf1  mov     edx, eax
0x14001ccf3  lock cmpxchg [rcx], edx
0x14001ccf7  jnz     short loc_14001CCF1
0x14001ccf9  test    eax, eax
0x14001ccfb  jnz     short loc_14001CD04
0x14001ccfd  mov     eax, 1
0x14001cd02  xchg    eax, [rcx]
0x14001cd04  mov     rax, [rcx+18h]
0x14001cd08  test    rax, rax
0x14001cd0b  jnz     short loc_14001CD43
0x14001cd0d  lea     rdx, [rcx+8]
0x14001cd11  lea     rcx, [rsp+38h+var_18]
0x14001cd16  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14001cd1c  lea     rax, [rsp+38h+var_18]
0x14001cd21  mov     [rsp+38h+pExceptionObject], rax
0x14001cd26  lea     rcx, [rsp+38h+var_18]
0x14001cd2b  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x14001cd31  nop
0x14001cd32  lea     rcx, [rsp+38h+var_18]
0x14001cd37  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x14001cd3d  nop
0x14001cd3e  add     rsp, 38h
0x14001cd42  retn
0x14001cd43  mov     rcx, rax
0x14001cd46  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14001cd4b  mov     [rsp+38h+pExceptionObject], rax
0x14001cd50  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x14001cd57  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14001cd5c  call    _CxxThrowException_0
```
