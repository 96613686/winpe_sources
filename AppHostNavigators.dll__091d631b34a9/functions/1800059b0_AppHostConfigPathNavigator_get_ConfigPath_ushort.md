# AppHostConfigPathNavigator::get_ConfigPath(ushort * *)

- ea: `0x1800059b0`
- end: `0x180005a70`
- name: `?get_ConfigPath@AppHostConfigPathNavigator@@UEAAJPEAPEAG@Z`
- size: `192`
- prototype: `__int64 __fastcall(AppHostConfigPathNavigator *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800021e0`
- `0x1800059b0`
- `0x1800130a0`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005a28`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005a28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall AppHostConfigPathNavigator::get_ConfigPath(AppHostConfigPathNavigator *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
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
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int16 *))(**((_QWORD **)this + 5) + 72LL))(
    *((_QWORD *)this + 5),
    *((_QWORD *)this + 4),
    1,
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
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800059b0  push    rbx
0x1800059b2  sub     rsp, 60h
0x1800059b6  mov     rax, cs:__security_cookie
0x1800059bd  xor     rax, rsp
0x1800059c0  mov     [rsp+68h+var_18], rax
0x1800059c5  mov     rbx, rdx
0x1800059c8  mov     rdx, rcx
0x1800059cb  test    rbx, rbx
0x1800059ce  jnz     short loc_1800059DA
0x1800059d0  mov     eax, 80070057h
0x1800059d5  jmp     loc_180005A5C
0x1800059da  mov     [rsp+68h+var_2E], 0
0x1800059df  mov     [rsp+68h+var_2C], 2
0x1800059e7  lea     rax, [rsp+68h+var_30]
0x1800059ec  mov     [rsp+68h+strIn], rax
0x1800059f1  mov     [rsp+68h+ui], 0
0x1800059f9  xor     eax, eax
0x1800059fb  mov     [rsp+68h+var_30], ax
0x180005a00  mov     rcx, [rcx+28h]
0x180005a04  mov     rax, [rcx]
0x180005a07  lea     r9, [rsp+68h+var_30]
0x180005a0c  mov     r8d, 1
0x180005a12  mov     rdx, [rdx+20h]
0x180005a16  mov     rax, [rax+48h]
0x180005a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a1f  mov     edx, [rsp+68h+ui]; ui
0x180005a23  mov     rcx, [rsp+68h+strIn]; strIn
0x180005a28  call    cs:__imp_SysAllocStringLen
0x180005a2e  mov     [rbx], rax
0x180005a31  lea     rcx, [rsp+68h+var_30]; this
0x180005a36  test    rax, rax
0x180005a39  jnz     short loc_180005A47
0x180005a3b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180005a40  mov     eax, 80070057h
0x180005a45  jmp     short loc_180005A5C
0x180005a47  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180005a4c  nop
0x180005a4d  xor     eax, eax
0x180005a4f  jmp     short loc_180005A5C
0x180005a51  mov     eax, [rsp+68h+var_38]
0x180005a55  jmp     short loc_180005A5C
0x180005a57  mov     eax, 8000FFFFh
0x180005a5c  mov     rcx, [rsp+68h+var_18]
0x180005a61  xor     rcx, rsp; StackCookie
0x180005a64  call    __security_check_cookie
0x180005a69  add     rsp, 60h
0x180005a6d  pop     rbx
0x180005a6e  retn
```
