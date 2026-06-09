# operator new(unsigned __int64)

- ea: `0x180001b10`
- end: `0x180001b9f`
- name: `??2@YAPEAX_K@Z`
- size: `143`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800017c0`
- `0x180001a60`
- `0x1800035d0`
- `0x180003640`

## callees

- `0x180001b10`
- `0x180001d30`
- `0x180002aa0`
- `0x180004ac0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180001b57`

## pseudocode

```c
void *__fastcall operator new(__int64 a1)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v2; // rdi
  void *(__cdecl *v3)(size_t); // rbx
  void *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v2 = 1;
  if ( a1 )
    v2 = a1;
  if ( !*(_BYTE *)(ThreadLocalStoragePointer[tls_index] + 1LL) || (v3 = (void *(__cdecl *)(size_t))g_pCachedMalloc) == 0 )
  {
    v3 = malloc;
    if ( g_pMalloc )
      v3 = (void *(__cdecl *)(size_t))g_pMalloc;
  }
  result = (void *)((__int64 (__fastcall *)(__int64, __int64))v3)(v2, 1);
  if ( !result )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180001b10  mov     [rsp+arg_0], rbx
0x180001b15  push    rdi
0x180001b16  sub     rsp, 40h
0x180001b1a  mov     rax, gs:58h
0x180001b23  test    rcx, rcx
0x180001b26  mov     edi, 1
0x180001b2b  mov     edx, 1
0x180001b30  cmovnz  rdi, rcx
0x180001b34  mov     ecx, cs:_tls_index
0x180001b3a  mov     rax, [rax+rcx*8]
0x180001b3e  cmp     byte ptr [rdx+rax], 0
0x180001b42  jz      short loc_180001B50
0x180001b44  mov     rbx, cs:?g_pCachedMalloc@@3P6APEAX_K@ZEA; void * (*g_pCachedMalloc)(unsigned __int64)
0x180001b4b  test    rbx, rbx
0x180001b4e  jnz     short loc_180001B65
0x180001b50  mov     rax, cs:?g_pMalloc@@3P6APEAX_K@ZEA; void * (*g_pMalloc)(unsigned __int64)
0x180001b57  mov     rbx, cs:__imp_malloc
0x180001b5e  test    rax, rax
0x180001b61  cmovnz  rbx, rax
0x180001b65  mov     rcx, rbx
0x180001b68  call    cs:__guard_check_icall_fptr
0x180001b6e  mov     rcx, rdi
0x180001b71  call    rbx ; void * (*g_pCachedMalloc)(unsigned __int64)
0x180001b73  test    rax, rax
0x180001b76  jz      short loc_180001B83
0x180001b78  mov     rbx, [rsp+48h+arg_0]
0x180001b7d  add     rsp, 40h
0x180001b81  pop     rdi
0x180001b82  retn
0x180001b83  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001b88  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180001b8d  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001b94  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001b99  call    _CxxThrowException_0
```
