# std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>,std::allocator<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>::~vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>,std::allocator<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>(void)

- ea: `0x18000e350`
- end: `0x18000e401`
- name: `??1?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000e408`
- `0x18000e450`
- `0x18000fd8c`
- `0x180016428`
- `0x180017dfa`

## callees

- `0x180002054`
- `0x18000e350`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e383`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        __int64 a1)
{
  void **v1; // rbx
  void **v3; // rsi
  void *v4; // rcx
  void **v5; // rcx
  unsigned __int64 v6; // rdx
  void **v7; // rax

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(void ***)(a1 + 8);
    while ( v1 != v3 )
    {
      v4 = *v1;
      *v1 = 0;
      if ( v4 )
        CoTaskMemFree(v4);
      ++v1;
    }
    v5 = *(void ***)a1;
    v6 = 8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3);
    if ( v6 < 0x1000 )
    {
      v7 = *(void ***)a1;
    }
    else
    {
      v7 = (void **)*(v5 - 1);
      if ( (unsigned __int64)((char *)v5 - (char *)v7 - 8) > 0x1F )
        __fastfail(5u);
      v6 += 39LL;
    }
    operator delete(v7, v6);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000e350  mov     [rsp+arg_0], rbx
0x18000e355  mov     [rsp+arg_8], rsi
0x18000e35a  push    rdi
0x18000e35b  sub     rsp, 20h
0x18000e35f  mov     rbx, [rcx]
0x18000e362  mov     rdi, rcx
0x18000e365  test    rbx, rbx
0x18000e368  jz      loc_18000E3F1
0x18000e36e  mov     rsi, [rcx+8]
0x18000e372  jmp     short loc_18000E38D
0x18000e374  mov     rcx, [rbx]; pv
0x18000e377  mov     qword ptr [rbx], 0
0x18000e37e  test    rcx, rcx
0x18000e381  jz      short loc_18000E389
0x18000e383  call    cs:__imp_CoTaskMemFree
0x18000e389  add     rbx, 8
0x18000e38d  cmp     rbx, rsi
0x18000e390  jnz     short loc_18000E374
0x18000e392  mov     rcx, [rdi]
0x18000e395  mov     rax, [rdi+10h]
0x18000e399  sub     rax, rcx
0x18000e39c  sar     rax, 3
0x18000e3a0  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18000e3a8  cmp     rdx, 1000h
0x18000e3af  jb      short loc_18000E3CF
0x18000e3b1  mov     rax, [rcx-8]
0x18000e3b5  sub     rcx, rax
0x18000e3b8  sub     rcx, 8
0x18000e3bc  cmp     rcx, 1Fh
0x18000e3c0  ja      short loc_18000E3C8
0x18000e3c2  add     rdx, 27h ; '''
0x18000e3c6  jmp     short loc_18000E3D2
0x18000e3c8  mov     ecx, 5
0x18000e3cd  int     29h; Win8: RtlFailFast(ecx)
0x18000e3cf  mov     rax, rcx
0x18000e3d2  mov     rcx, rax; void *
0x18000e3d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e3da  mov     qword ptr [rdi], 0
0x18000e3e1  mov     qword ptr [rdi+8], 0
0x18000e3e9  mov     qword ptr [rdi+10h], 0
0x18000e3f1  mov     rbx, [rsp+28h+arg_0]
0x18000e3f6  mov     rsi, [rsp+28h+arg_8]
0x18000e3fb  add     rsp, 20h
0x18000e3ff  pop     rdi
0x18000e400  retn
```
