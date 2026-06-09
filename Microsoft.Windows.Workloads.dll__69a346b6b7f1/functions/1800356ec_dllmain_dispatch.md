# dllmain_dispatch

- ea: `0x1800356ec`
- end: `0x180035814`
- name: `dllmain_dispatch`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180035820`

## callees

- `0x18003516c`
- `0x180035500`
- `0x180035668`
- `0x1800356ec`
- `0x180035e68`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v7; // ebx
  _crt_argv_mode startup_argv_mode; // eax

  if ( !a2 && dword_1800595A8 <= 0 )
    return 0;
  if ( a2 - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(a1, a2, a3)) != 0) )
  {
    startup_argv_mode = get_startup_argv_mode();
    v7 = startup_argv_mode;
    if ( a2 == 1 && startup_argv_mode == _crt_argv_no_arguments )
    {
      get_startup_argv_mode();
      dllmain_crt_process_detach(a3 != 0);
      if ( pRawDllMain )
        pRawDllMain(a1, 0, a3);
    }
    if ( !a2 || a2 == 3 )
    {
      v7 = dllmain_crt_dispatch(a1, a2, a3);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(a1, a2, a3);
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
0x1800356ec  mov     rax, rsp
0x1800356ef  mov     [rax+20h], rbx
0x1800356f3  mov     [rax+18h], r8
0x1800356f7  mov     [rax+10h], edx
0x1800356fa  mov     [rax+8], rcx
0x1800356fe  push    rsi
0x1800356ff  push    rdi
0x180035700  push    r14
0x180035702  sub     rsp, 40h
0x180035706  mov     rsi, r8
0x180035709  mov     edi, edx
0x18003570b  mov     r14, rcx
0x18003570e  test    edx, edx
0x180035710  jnz     short loc_180035721
0x180035712  cmp     cs:dword_1800595A8, edx
0x180035718  jg      short loc_180035721
0x18003571a  xor     eax, eax
0x18003571c  jmp     loc_180035806
0x180035721  lea     eax, [rdx-1]
0x180035724  cmp     eax, 1
0x180035727  ja      short loc_180035769
0x180035729  mov     rax, cs:_pRawDllMain
0x180035730  test    rax, rax
0x180035733  jnz     short loc_18003573A
0x180035735  lea     ebx, [rax+1]
0x180035738  jmp     short loc_180035742
0x18003573a  call    cs:__guard_dispatch_icall_fptr
0x180035740  mov     ebx, eax
0x180035742  mov     [rsp+58h+var_28], ebx
0x180035746  test    ebx, ebx
0x180035748  jz      loc_1800357FC
0x18003574e  mov     r8, rsi
0x180035751  mov     edx, edi
0x180035753  mov     rcx, r14
0x180035756  call    dllmain_crt_dispatch
0x18003575b  mov     ebx, eax
0x18003575d  mov     [rsp+58h+var_28], eax
0x180035761  test    eax, eax
0x180035763  jz      loc_1800357FC
0x180035769  mov     r8, rsi
0x18003576c  mov     edx, edi
0x18003576e  mov     rcx, r14
0x180035771  call    _get_startup_argv_mode
0x180035776  mov     ebx, eax
0x180035778  mov     [rsp+58h+var_28], eax
0x18003577c  cmp     edi, 1
0x18003577f  jnz     short loc_1800357B7
0x180035781  test    eax, eax
0x180035783  jnz     short loc_1800357B7
0x180035785  mov     r8, rsi
0x180035788  xor     edx, edx
0x18003578a  mov     rcx, r14
0x18003578d  call    _get_startup_argv_mode
0x180035792  test    rsi, rsi
0x180035795  setnz   cl
0x180035798  call    dllmain_crt_process_detach
0x18003579d  mov     rax, cs:_pRawDllMain
0x1800357a4  test    rax, rax
0x1800357a7  jz      short loc_1800357B7
0x1800357a9  mov     r8, rsi
0x1800357ac  xor     edx, edx
0x1800357ae  mov     rcx, r14
0x1800357b1  call    cs:__guard_dispatch_icall_fptr
0x1800357b7  test    edi, edi
0x1800357b9  jz      short loc_1800357C0
0x1800357bb  cmp     edi, 3
0x1800357be  jnz     short loc_1800357FC
0x1800357c0  mov     r8, rsi
0x1800357c3  mov     edx, edi
0x1800357c5  mov     rcx, r14
0x1800357c8  call    dllmain_crt_dispatch
0x1800357cd  mov     ebx, eax
0x1800357cf  mov     [rsp+58h+var_28], eax
0x1800357d3  test    eax, eax
0x1800357d5  jz      short loc_1800357FC
0x1800357d7  mov     rax, cs:_pRawDllMain
0x1800357de  test    rax, rax
0x1800357e1  jnz     short loc_1800357E8
0x1800357e3  lea     ebx, [rax+1]
0x1800357e6  jmp     short loc_1800357F8
0x1800357e8  mov     r8, rsi
0x1800357eb  mov     edx, edi
0x1800357ed  mov     rcx, r14
0x1800357f0  call    cs:__guard_dispatch_icall_fptr
0x1800357f6  mov     ebx, eax
0x1800357f8  mov     [rsp+58h+var_28], ebx
0x1800357fc  jmp     short loc_180035804
0x1800357fe  xor     ebx, ebx
0x180035800  mov     [rsp+58h+var_28], ebx
0x180035804  mov     eax, ebx
0x180035806  mov     rbx, [rsp+58h+arg_18]
0x18003580b  add     rsp, 40h
0x18003580f  pop     r14
0x180035811  pop     rdi
0x180035812  pop     rsi
0x180035813  retn
0x180040bbb  push    rbp
0x180040bbd  sub     rsp, 30h
0x180040bc1  mov     rbp, rdx
0x180040bc4  mov     rax, [rcx]
0x180040bc7  mov     edx, [rax]
0x180040bc9  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180040bce  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180040bd2  lea     r9, dllmain_crt_dispatch; int
0x180040bd9  mov     r8, [rbp+70h]; int
0x180040bdd  mov     edx, [rbp+68h]; int
0x180040be0  mov     rcx, [rbp+60h]; int
0x180040be4  call    __scrt_dllmain_exception_filter
0x180040be9  nop
0x180040bea  add     rsp, 30h
0x180040bee  pop     rbp
0x180040bef  retn
```
