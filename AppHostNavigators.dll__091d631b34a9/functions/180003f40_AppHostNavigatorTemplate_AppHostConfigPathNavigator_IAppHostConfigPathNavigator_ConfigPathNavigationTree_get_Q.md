# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::get_QueryRepresentation(ushort * *)

- ea: `0x180003f40`
- end: `0x180003ffa`
- name: `?get_QueryRepresentation@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@UEAAJPEAPEAG@Z`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800021e0`
- `0x180003f40`
- `0x1800130a0`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180003fb2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180003fb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::get_QueryRepresentation(
        __int64 a1,
        BSTR *a2)
{
  BSTR v4; // rax
  __int16 v5; // [rsp+38h] [rbp-30h] BYREF
  char v6; // [rsp+3Ah] [rbp-2Eh]
  int v7; // [rsp+3Ch] [rbp-2Ch]
  OLECHAR *strIn; // [rsp+40h] [rbp-28h]
  UINT ui; // [rsp+48h] [rbp-20h]

  if ( !a2 )
    return 2147942487LL;
  v6 = 0;
  v7 = 2;
  strIn = (OLECHAR *)&v5;
  ui = 0;
  v5 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int16 *))(**(_QWORD **)(a1 + 40) + 72LL))(
    *(_QWORD *)(a1 + 40),
    *(_QWORD *)(a1 + 32),
    0,
    &v5);
  v4 = SysAllocStringLen(strIn, ui);
  *a2 = v4;
  if ( v4 )
  {
    BUFFER::~BUFFER((BUFFER *)&v5);
    return 0;
  }
  else
  {
    BUFFER::~BUFFER((BUFFER *)&v5);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180003f40  push    rbx
0x180003f42  sub     rsp, 60h
0x180003f46  mov     rax, cs:__security_cookie
0x180003f4d  xor     rax, rsp
0x180003f50  mov     [rsp+68h+var_18], rax
0x180003f55  mov     rbx, rdx
0x180003f58  mov     rdx, rcx
0x180003f5b  test    rbx, rbx
0x180003f5e  jnz     short loc_180003F67
0x180003f60  mov     eax, 80070057h
0x180003f65  jmp     short loc_180003FE6
0x180003f67  mov     [rsp+68h+var_2E], 0
0x180003f6c  mov     [rsp+68h+var_2C], 2
0x180003f74  lea     rax, [rsp+68h+var_30]
0x180003f79  mov     [rsp+68h+strIn], rax
0x180003f7e  mov     [rsp+68h+ui], 0
0x180003f86  xor     eax, eax
0x180003f88  mov     [rsp+68h+var_30], ax
0x180003f8d  mov     rcx, [rcx+28h]
0x180003f91  mov     rax, [rcx]
0x180003f94  lea     r9, [rsp+68h+var_30]
0x180003f99  xor     r8d, r8d
0x180003f9c  mov     rdx, [rdx+20h]
0x180003fa0  mov     rax, [rax+48h]
0x180003fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fa9  mov     edx, [rsp+68h+ui]; ui
0x180003fad  mov     rcx, [rsp+68h+strIn]; strIn
0x180003fb2  call    cs:__imp_SysAllocStringLen
0x180003fb8  mov     [rbx], rax
0x180003fbb  lea     rcx, [rsp+68h+var_30]; this
0x180003fc0  test    rax, rax
0x180003fc3  jnz     short loc_180003FD1
0x180003fc5  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003fca  mov     eax, 8007000Eh
0x180003fcf  jmp     short loc_180003FE6
0x180003fd1  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003fd6  nop
0x180003fd7  xor     eax, eax
0x180003fd9  jmp     short loc_180003FE6
0x180003fdb  mov     eax, [rsp+68h+var_38]
0x180003fdf  jmp     short loc_180003FE6
0x180003fe1  mov     eax, 8000FFFFh
0x180003fe6  mov     rcx, [rsp+68h+var_18]
0x180003feb  xor     rcx, rsp; StackCookie
0x180003fee  call    __security_check_cookie
0x180003ff3  add     rsp, 60h
0x180003ff7  pop     rbx
0x180003ff8  retn
```
