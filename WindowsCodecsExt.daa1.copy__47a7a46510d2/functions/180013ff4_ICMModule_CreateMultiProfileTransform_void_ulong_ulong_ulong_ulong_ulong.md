# ICMModule::CreateMultiProfileTransform(void * *,ulong,ulong *,ulong,ulong,ulong)

- ea: `0x180013ff4`
- end: `0x18001404e`
- name: `?CreateMultiProfileTransform@ICMModule@@SAPEAXPEAPEAXKPEAKKKK@Z`
- size: `90`
- prototype: `__int64 __fastcall(void **, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014930`

## callees

- `0x180007410`
- `0x180013ff4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall ICMModule::CreateMultiProfileTransform(void **a1, __int64 a2, unsigned int *a3)
{
  __int64 v5; // rbx

  v5 = 0;
  if ( ICMModule::EnsureLoaded() )
    return ((__int64 (__fastcall *)(void **, __int64, unsigned int *, __int64, int, _DWORD))ICMModule::s_pfnCreateMultiProfileTransform)(
             a1,
             2,
             a3,
             2,
             131075,
             0);
  return v5;
}

```

## disassembly

```asm
0x180013ff4  mov     [rsp+arg_0], rbx
0x180013ff9  mov     [rsp+arg_8], rsi
0x180013ffe  push    rdi
0x180013fff  sub     rsp, 40h
0x180014003  mov     rdi, r8
0x180014006  mov     rsi, rcx
0x180014009  xor     ebx, ebx
0x18001400b  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x180014010  test    eax, eax
0x180014012  jz      short loc_18001403B
0x180014014  mov     rax, cs:?s_pfnCreateMultiProfileTransform@ICMModule@@0P6APEAXPEAPEAXKPEAKKKK@ZEA; void * (*ICMModule::s_pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x18001401b  lea     edx, [rbx+2]
0x18001401e  mov     r9d, edx
0x180014021  mov     [rsp+48h+var_20], ebx
0x180014025  mov     r8, rdi
0x180014028  mov     [rsp+48h+var_28], 20003h
0x180014030  mov     rcx, rsi
0x180014033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014038  mov     rbx, rax
0x18001403b  mov     rsi, [rsp+48h+arg_8]
0x180014040  mov     rax, rbx
0x180014043  mov     rbx, [rsp+48h+arg_0]
0x180014048  add     rsp, 40h
0x18001404c  pop     rdi
0x18001404d  retn
```
