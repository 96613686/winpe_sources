# dllmain_dispatch

- ea: `0x180004180`
- end: `0x180004275`
- name: `dllmain_dispatch`
- size: `245`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800042d0`

## callees

- `0x180001340`
- `0x180003c2c`
- `0x180003f80`
- `0x180004180`
- `0x180004278`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800081A4 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (v7 = ((__int64 (*)(void))dllmain_raw)()) != 0
    && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0 )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      dllmain_raw(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
        return (unsigned int)dllmain_raw(hinstDLL, fdwReason, lpvReserved);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180004180  mov     rax, rsp
0x180004183  mov     [rax+20h], rbx
0x180004187  mov     [rax+18h], r8
0x18000418b  mov     [rax+10h], edx
0x18000418e  mov     [rax+8], rcx
0x180004192  push    rsi
0x180004193  push    rdi
0x180004194  push    r14
0x180004196  sub     rsp, 40h
0x18000419a  mov     rsi, r8
0x18000419d  mov     edi, edx
0x18000419f  mov     r14, rcx
0x1800041a2  test    edx, edx
0x1800041a4  jnz     short loc_1800041B5
0x1800041a6  cmp     cs:dword_1800081A4, edx
0x1800041ac  jg      short loc_1800041B5
0x1800041ae  xor     eax, eax
0x1800041b0  jmp     loc_180004267
0x1800041b5  lea     eax, [rdx-1]
0x1800041b8  cmp     eax, 1
0x1800041bb  ja      short loc_1800041E7
0x1800041bd  call    dllmain_raw
0x1800041c2  mov     ebx, eax
0x1800041c4  mov     [rsp+58h+var_28], eax
0x1800041c8  test    eax, eax
0x1800041ca  jz      loc_18000425D
0x1800041d0  mov     r8, rsi
0x1800041d3  mov     edx, edi
0x1800041d5  mov     rcx, r14
0x1800041d8  call    dllmain_crt_dispatch
0x1800041dd  mov     ebx, eax
0x1800041df  mov     [rsp+58h+var_28], eax
0x1800041e3  test    eax, eax
0x1800041e5  jz      short loc_18000425D
0x1800041e7  mov     r8, rsi; lpvReserved
0x1800041ea  mov     edx, edi; fdwReason
0x1800041ec  mov     rcx, r14; hinstDLL
0x1800041ef  call    DllMain
0x1800041f4  mov     ebx, eax
0x1800041f6  mov     [rsp+58h+var_28], eax
0x1800041fa  cmp     edi, 1
0x1800041fd  jnz     short loc_18000422A
0x1800041ff  test    eax, eax
0x180004201  jnz     short loc_18000422A
0x180004203  mov     r8, rsi; lpvReserved
0x180004206  xor     edx, edx; fdwReason
0x180004208  mov     rcx, r14; hinstDLL
0x18000420b  call    DllMain
0x180004210  mov     r8, rsi
0x180004213  xor     edx, edx
0x180004215  mov     rcx, r14
0x180004218  call    dllmain_crt_dispatch
0x18000421d  mov     r8, rsi
0x180004220  xor     edx, edx
0x180004222  mov     rcx, r14
0x180004225  call    dllmain_raw
0x18000422a  test    edi, edi
0x18000422c  jz      short loc_180004233
0x18000422e  cmp     edi, 3
0x180004231  jnz     short loc_18000425D
0x180004233  mov     r8, rsi
0x180004236  mov     edx, edi
0x180004238  mov     rcx, r14
0x18000423b  call    dllmain_crt_dispatch
0x180004240  mov     ebx, eax
0x180004242  mov     [rsp+58h+var_28], eax
0x180004246  test    eax, eax
0x180004248  jz      short loc_18000425D
0x18000424a  mov     r8, rsi
0x18000424d  mov     edx, edi
0x18000424f  mov     rcx, r14
0x180004252  call    dllmain_raw
0x180004257  mov     ebx, eax
0x180004259  mov     [rsp+58h+var_28], eax
0x18000425d  jmp     short loc_180004265
0x18000425f  xor     ebx, ebx
0x180004261  mov     [rsp+58h+var_28], ebx
0x180004265  mov     eax, ebx
0x180004267  mov     rbx, [rsp+58h+arg_18]
0x18000426c  add     rsp, 40h
0x180004270  pop     r14
0x180004272  pop     rdi
0x180004273  pop     rsi
0x180004274  retn
0x180004f04  push    rbp
0x180004f06  sub     rsp, 30h
0x180004f0a  mov     rbp, rdx
0x180004f0d  mov     rax, [rcx]
0x180004f10  mov     edx, [rax]
0x180004f12  mov     [rsp+38h+var_10], rcx
0x180004f17  mov     [rsp+38h+var_18], edx
0x180004f1b  lea     r9, dllmain_crt_dispatch
0x180004f22  mov     r8, [rbp+70h]
0x180004f26  mov     edx, [rbp+68h]
0x180004f29  mov     rcx, [rbp+60h]
0x180004f2d  call    __scrt_dllmain_exception_filter
0x180004f32  nop
0x180004f33  add     rsp, 30h
0x180004f37  pop     rbp
0x180004f38  retn
```
