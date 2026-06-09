# dllmain_dispatch

- ea: `0x180003fe4`
- end: `0x18000410b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004120`

## callees

- `0x180003e00`
- `0x180003fe4`
- `0x1800043bc`
- `0x18000d414`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18005F850 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(hinstDLL, fdwReason, lpvReserved);
        else
          return 1;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003fe4  mov     rax, rsp
0x180003fe7  mov     [rax+20h], rbx
0x180003feb  mov     [rax+18h], r8
0x180003fef  mov     [rax+10h], edx
0x180003ff2  mov     [rax+8], rcx
0x180003ff6  push    rsi
0x180003ff7  push    rdi
0x180003ff8  push    r14
0x180003ffa  sub     rsp, 40h
0x180003ffe  mov     rsi, r8
0x180004001  mov     edi, edx
0x180004003  mov     r14, rcx
0x180004006  test    edx, edx
0x180004008  jnz     short loc_180004019
0x18000400a  cmp     cs:dword_18005F850, edx
0x180004010  jg      short loc_180004019
0x180004012  xor     eax, eax
0x180004014  jmp     loc_1800040FD
0x180004019  lea     eax, [rdx-1]
0x18000401c  cmp     eax, 1
0x18000401f  ja      short loc_180004060
0x180004021  mov     rax, cs:_pRawDllMain
0x180004028  test    rax, rax
0x18000402b  jnz     short loc_180004032
0x18000402d  lea     ebx, [rax+1]
0x180004030  jmp     short loc_180004039
0x180004032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004037  mov     ebx, eax
0x180004039  mov     [rsp+58h+var_28], ebx
0x18000403d  test    ebx, ebx
0x18000403f  jz      loc_1800040F3
0x180004045  mov     r8, rsi
0x180004048  mov     edx, edi
0x18000404a  mov     rcx, r14
0x18000404d  call    dllmain_crt_dispatch
0x180004052  mov     ebx, eax
0x180004054  mov     [rsp+58h+var_28], eax
0x180004058  test    eax, eax
0x18000405a  jz      loc_1800040F3
0x180004060  mov     r8, rsi; lpvReserved
0x180004063  mov     edx, edi; fdwReason
0x180004065  mov     rcx, r14; hinstDLL
0x180004068  call    DllMain
0x18000406d  mov     ebx, eax
0x18000406f  mov     [rsp+58h+var_28], eax
0x180004073  cmp     edi, 1
0x180004076  jnz     short loc_1800040AF
0x180004078  test    eax, eax
0x18000407a  jnz     short loc_1800040AF
0x18000407c  mov     r8, rsi; lpvReserved
0x18000407f  xor     edx, edx; fdwReason
0x180004081  mov     rcx, r14; hinstDLL
0x180004084  call    DllMain
0x180004089  mov     r8, rsi
0x18000408c  xor     edx, edx
0x18000408e  mov     rcx, r14
0x180004091  call    dllmain_crt_dispatch
0x180004096  mov     rax, cs:_pRawDllMain
0x18000409d  test    rax, rax
0x1800040a0  jz      short loc_1800040AF
0x1800040a2  mov     r8, rsi
0x1800040a5  xor     edx, edx
0x1800040a7  mov     rcx, r14
0x1800040aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040af  test    edi, edi
0x1800040b1  jz      short loc_1800040B8
0x1800040b3  cmp     edi, 3
0x1800040b6  jnz     short loc_1800040F3
0x1800040b8  mov     r8, rsi
0x1800040bb  mov     edx, edi
0x1800040bd  mov     rcx, r14
0x1800040c0  call    dllmain_crt_dispatch
0x1800040c5  mov     ebx, eax
0x1800040c7  mov     [rsp+58h+var_28], eax
0x1800040cb  test    eax, eax
0x1800040cd  jz      short loc_1800040F3
0x1800040cf  mov     rax, cs:_pRawDllMain
0x1800040d6  test    rax, rax
0x1800040d9  jnz     short loc_1800040E0
0x1800040db  lea     ebx, [rax+1]
0x1800040de  jmp     short loc_1800040EF
0x1800040e0  mov     r8, rsi
0x1800040e3  mov     edx, edi
0x1800040e5  mov     rcx, r14
0x1800040e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ed  mov     ebx, eax
0x1800040ef  mov     [rsp+58h+var_28], ebx
0x1800040f3  jmp     short loc_1800040FB
0x1800040f5  xor     ebx, ebx
0x1800040f7  mov     [rsp+58h+var_28], ebx
0x1800040fb  mov     eax, ebx
0x1800040fd  mov     rbx, [rsp+58h+arg_18]
0x180004102  add     rsp, 40h
0x180004106  pop     r14
0x180004108  pop     rdi
0x180004109  pop     rsi
0x18000410a  retn
0x1800301ec  push    rbp
0x1800301ee  sub     rsp, 30h
0x1800301f2  mov     rbp, rdx
0x1800301f5  mov     rax, [rcx]
0x1800301f8  mov     edx, [rax]
0x1800301fa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800301ff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180030203  lea     r9, dllmain_crt_dispatch; int
0x18003020a  mov     r8, [rbp+70h]; int
0x18003020e  mov     edx, [rbp+68h]; int
0x180030211  mov     rcx, [rbp+60h]; int
0x180030215  call    __scrt_dllmain_exception_filter
0x18003021a  nop
0x18003021b  add     rsp, 30h
0x18003021f  pop     rbp
0x180030220  retn
```
