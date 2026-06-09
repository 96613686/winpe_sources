# OleStdCopyTargetDevice

- ea: `0x1800043c8`
- end: `0x18000446b`
- name: `OleStdCopyTargetDevice`
- size: `163`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000436c`

## callees

- `0x180001460`
- `0x1800043c8`
- `0x180017365`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180004402`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180004402`

## pseudocode

```c
void *__fastcall OleStdCopyTargetDevice(unsigned int *Src)
{
  __int64 v3; // rbx
  void *v4; // rbx
  LPMALLOC ppMalloc; // [rsp+20h] [rbp-18h] BYREF

  if ( !Src )
    return 0;
  v3 = *Src;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) )
    return 0;
  v4 = (void *)((__int64 (__fastcall *)(LPMALLOC, __int64))ppMalloc->lpVtbl->Alloc)(ppMalloc, v3);
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  if ( v4 )
    memmove_0(v4, Src, *Src);
  return v4;
}

```

## disassembly

```asm
0x1800043c8  mov     [rsp+arg_8], rbx
0x1800043cd  push    rdi
0x1800043ce  sub     rsp, 30h
0x1800043d2  mov     rax, cs:__security_cookie
0x1800043d9  xor     rax, rsp
0x1800043dc  mov     [rsp+38h+var_10], rax
0x1800043e1  mov     rdi, rcx
0x1800043e4  test    rcx, rcx
0x1800043e7  jnz     short loc_1800043ED
0x1800043e9  xor     eax, eax
0x1800043eb  jmp     short loc_180004453
0x1800043ed  mov     ebx, [rcx]
0x1800043ef  lea     rdx, [rsp+38h+ppMalloc]; ppMalloc
0x1800043f4  mov     ecx, 1; dwMemContext
0x1800043f9  mov     [rsp+38h+ppMalloc], 0
0x180004402  call    cs:__imp_CoGetMalloc
0x180004408  test    eax, eax
0x18000440a  jz      short loc_180004410
0x18000440c  xor     ebx, ebx
0x18000440e  jmp     short loc_180004450
0x180004410  mov     rcx, [rsp+38h+ppMalloc]
0x180004415  mov     rdx, rbx
0x180004418  mov     rax, [rcx]
0x18000441b  mov     rax, [rax+18h]
0x18000441f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004424  mov     rcx, [rsp+38h+ppMalloc]
0x180004429  mov     rbx, rax
0x18000442c  test    rcx, rcx
0x18000442f  jz      short loc_18000443D
0x180004431  mov     rax, [rcx]
0x180004434  mov     rax, [rax+10h]
0x180004438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443d  test    rbx, rbx
0x180004440  jz      short loc_180004450
0x180004442  mov     r8d, [rdi]; Size
0x180004445  mov     rdx, rdi; Src
0x180004448  mov     rcx, rbx; void *
0x18000444b  call    memmove_0
0x180004450  mov     rax, rbx
0x180004453  mov     rcx, [rsp+38h+var_10]
0x180004458  xor     rcx, rsp; StackCookie
0x18000445b  call    __security_check_cookie
0x180004460  mov     rbx, [rsp+38h+arg_8]
0x180004465  add     rsp, 30h
0x180004469  pop     rdi
0x18000446a  retn
```
