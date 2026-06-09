# AppHostConfigLocationsNavigator::get_EffectiveLocationPath(ushort * *)

- ea: `0x180003c20`
- end: `0x180003cd5`
- name: `?get_EffectiveLocationPath@AppHostConfigLocationsNavigator@@UEAAJPEAPEAG@Z`
- size: `181`
- prototype: `__int64 __fastcall(AppHostConfigLocationsNavigator *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800021e0`
- `0x1800029d0`
- `0x180003c20`
- `0x1800130a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180003c87`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180003c87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall AppHostConfigLocationsNavigator::get_EffectiveLocationPath(
        AppHostConfigLocationsNavigator *this,
        unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  _BYTE v5[4]; // [rsp+28h] [rbp-240h] BYREF
  int v6; // [rsp+2Ch] [rbp-23Ch]
  OLECHAR *strIn; // [rsp+30h] [rbp-238h]
  UINT ui; // [rsp+38h] [rbp-230h]
  __int16 v9; // [rsp+40h] [rbp-228h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5[2] = 0;
  v6 = 520;
  strIn = (OLECHAR *)&v9;
  ui = 0;
  v9 = 0;
  AppHostConfigLocationsNavigator::GetEffectiveLocationPath(
    (AppHostConfigLocationsNavigator *)((char *)this - 8),
    (struct STRU *)v5);
  v4 = SysAllocStringLen(strIn, ui);
  *a2 = v4;
  if ( v4 )
  {
    BUFFER::~BUFFER((BUFFER *)v5);
    return 0;
  }
  else
  {
    BUFFER::~BUFFER((BUFFER *)v5);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180003c20  push    rbx
0x180003c22  sub     rsp, 260h
0x180003c29  mov     rax, cs:__security_cookie
0x180003c30  xor     rax, rsp
0x180003c33  mov     [rsp+268h+var_18], rax
0x180003c3b  mov     rbx, rdx
0x180003c3e  test    rdx, rdx
0x180003c41  jnz     short loc_180003C4A
0x180003c43  mov     eax, 80070057h
0x180003c48  jmp     short loc_180003CBB
0x180003c4a  mov     [rsp+268h+var_23E], 0
0x180003c4f  mov     [rsp+268h+var_23C], 208h
0x180003c57  lea     rax, [rsp+268h+var_228]
0x180003c5c  mov     [rsp+268h+strIn], rax
0x180003c61  mov     [rsp+268h+ui], 0
0x180003c69  xor     eax, eax
0x180003c6b  mov     [rsp+268h+var_228], ax
0x180003c70  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180003c74  lea     rdx, [rsp+268h+var_240]; struct STRU *
0x180003c79  call    ?GetEffectiveLocationPath@AppHostConfigLocationsNavigator@@QEAAXAEAVSTRU@@@Z; AppHostConfigLocationsNavigator::GetEffectiveLocationPath(STRU &)
0x180003c7e  mov     edx, [rsp+268h+ui]; ui
0x180003c82  mov     rcx, [rsp+268h+strIn]; strIn
0x180003c87  call    cs:__imp_SysAllocStringLen
0x180003c8d  mov     [rbx], rax
0x180003c90  lea     rcx, [rsp+268h+var_240]; this
0x180003c95  test    rax, rax
0x180003c98  jnz     short loc_180003CA6
0x180003c9a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003c9f  mov     eax, 8007000Eh
0x180003ca4  jmp     short loc_180003CBB
0x180003ca6  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003cab  nop
0x180003cac  xor     eax, eax
0x180003cae  jmp     short loc_180003CBB
0x180003cb0  mov     eax, [rsp+268h+var_248]
0x180003cb4  jmp     short loc_180003CBB
0x180003cb6  mov     eax, 8000FFFFh
0x180003cbb  mov     rcx, [rsp+268h+var_18]
0x180003cc3  xor     rcx, rsp; StackCookie
0x180003cc6  call    __security_check_cookie
0x180003ccb  add     rsp, 260h
0x180003cd2  pop     rbx
0x180003cd3  retn
```
