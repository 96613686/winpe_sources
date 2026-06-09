# operator delete(void *)

- ea: `0x180001be0`
- end: `0x180001c55`
- name: `??3@YAXPEAX@Z`
- size: `117`
- prototype: `void __fastcall(void *)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001390`
- `0x180001440`
- `0x1800017c0`
- `0x180002030`
- `0x180002b00`
- `0x1800033e0`
- `0x180003640`
- `0x1800037f0`
- `0x180003f6c`

## callees

- `0x180001be0`
- `0x180002aa0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180001c25`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  void (__cdecl *v1)(void *); // rbx

  if ( a1 )
  {
    if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 1LL)
      || (v1 = (void (__cdecl *)(void *))g_pCachedFree) == 0 )
    {
      v1 = free;
      if ( g_pFree )
        v1 = (void (__cdecl *)(void *))g_pFree;
    }
    ((void (__fastcall *)(void *))v1)(a1);
  }
}

```

## disassembly

```asm
0x180001be0  test    rcx, rcx
0x180001be3  jz      short locret_180001C54
0x180001be5  push    rdi
0x180001be6  sub     rsp, 30h
0x180001bea  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001bf3  mov     [rsp+38h+arg_0], rbx
0x180001bf8  mov     rdi, rcx
0x180001bfb  mov     edx, cs:_tls_index
0x180001c01  mov     rax, gs:58h
0x180001c0a  mov     ecx, 1
0x180001c0f  mov     rax, [rax+rdx*8]
0x180001c13  cmp     byte ptr [rcx+rax], 0
0x180001c17  jz      short loc_180001C25
0x180001c19  mov     rbx, cs:?g_pCachedFree@@3P6AXPEAX@ZEA; void (*g_pCachedFree)(void *)
0x180001c20  test    rbx, rbx
0x180001c23  jnz     short loc_180001C3A
0x180001c25  mov     rbx, cs:__imp_free
0x180001c2c  mov     rax, cs:?g_pFree@@3P6AXPEAX@ZEA; void (*g_pFree)(void *)
0x180001c33  test    rax, rax
0x180001c36  cmovnz  rbx, rax
0x180001c3a  mov     rcx, rbx
0x180001c3d  call    cs:__guard_check_icall_fptr
0x180001c43  nop
0x180001c44  mov     rcx, rdi
0x180001c47  call    rbx ; void (*g_pCachedFree)(void *)
0x180001c49  nop
0x180001c4a  mov     rbx, [rsp+38h+arg_0]
0x180001c4f  add     rsp, 30h
0x180001c53  pop     rdi
0x180001c54  retn
```
