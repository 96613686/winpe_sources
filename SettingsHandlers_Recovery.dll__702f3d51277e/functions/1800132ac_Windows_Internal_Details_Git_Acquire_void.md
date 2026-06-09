# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x1800132ac`
- end: `0x180013348`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `156`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000efec`
- `0x18000f15c`
- `0x18000f2cc`
- `0x18000f468`

## callees

- `0x1800132ac`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800132f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800132f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID v2; // rcx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_18005A068 )
  {
    v1 = 0;
    _InterlockedIncrement(&Windows::Internal::Details::_git);
  }
  else
  {
    ppv = 0;
    v1 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v1 >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&qword_18005A068, (signed __int64)ppv, 0) )
        ppv = 0;
      _InterlockedIncrement(&Windows::Internal::Details::_git);
    }
    v2 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800132ac  mov     [rsp+arg_0], rcx
0x1800132b1  push    rbx
0x1800132b2  sub     rsp, 30h
0x1800132b6  cmp     cs:qword_18005A068, 0
0x1800132be  jz      short loc_1800132CB
0x1800132c0  xor     ebx, ebx
0x1800132c2  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x1800132c9  jmp     short loc_180013340
0x1800132cb  mov     [rsp+38h+arg_0], 0
0x1800132d4  lea     rax, [rsp+38h+arg_0]
0x1800132d9  mov     [rsp+38h+ppv], rax; ppv
0x1800132de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800132e5  xor     edx, edx; pUnkOuter
0x1800132e7  lea     r8d, [rdx+1]; dwClsContext
0x1800132eb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800132f2  call    cs:__imp_CoCreateInstance
0x1800132f8  mov     ebx, eax
0x1800132fa  test    eax, eax
0x1800132fc  js      short loc_180013320
0x1800132fe  mov     rcx, [rsp+38h+arg_0]
0x180013303  xor     eax, eax
0x180013305  lock cmpxchg cs:qword_18005A068, rcx
0x18001330e  jnz     short loc_180013319
0x180013310  mov     [rsp+38h+arg_0], 0
0x180013319  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180013320  mov     rcx, [rsp+38h+arg_0]
0x180013325  test    rcx, rcx
0x180013328  jz      short loc_180013340
0x18001332a  mov     [rsp+38h+arg_0], 0
0x180013333  mov     rax, [rcx]
0x180013336  mov     rax, [rax+10h]
0x18001333a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001333f  nop
0x180013340  mov     eax, ebx
0x180013342  add     rsp, 30h
0x180013346  pop     rbx
0x180013347  retn
```
