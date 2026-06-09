# CLocationPersistedRegPathHelper::GetPersistedRegPath(ushort const *,ushort const *,ushort *,ushort const *)

- ea: `0x180032d80`
- end: `0x180032ef0`
- name: `?GetPersistedRegPath@CLocationPersistedRegPathHelper@@SAJPEBG0PEAG0@Z`
- size: `368`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18009890c`
- `0x1800cdc34`
- `0x1800cdd2c`
- `0x1800cdf0c`
- `0x1800e2680`
- `0x1800e429c`
- `0x1800e4698`
- `0x1800e4884`
- `0x1800e4dfc`
- `0x180117d40`
- `0x18011885c`
- `0x180118a88`
- `0x1801324e0`

## callees

- `0x180032d80`
- `0x18008fa98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180032e3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180032e78`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180032e3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180032e78`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180032dc9`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180032dc9`

## string_xrefs

- `0x180032ebe`: `onecoreuap\drivers\MobilePC\Location\Product\idk\LocationRegistryHelper.h`
- `0x180032eb2`: `Path is too long. buff len: %zu. subPath len: %zu`
- `0x180032ea6`: `CLocationPersistedRegPathHelper::GetPersistedRegPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLocationPersistedRegPathHelper::GetPersistedRegPath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 result; // rax
  __int64 v7; // rax
  __int64 v8; // r8
  int v9; // edx
  int v10; // edx
  wil::details *v11; // [rsp+28h] [rbp-30h]
  wil::details::in1diag5 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a1 || !a2 || !a3 || !a4 )
    return 2147942487LL;
  result = GetPersistedRegistryLocationW(a4, a2, a3, 510, 0);
  if ( (_DWORD)result )
  {
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    do
      ++v7;
    while ( a1[v7] );
    if ( (unsigned __int64)(v7 + v8 + 1) >= 0xFF )
    {
      LODWORD(v11) = -2147418113;
      wil::details::in1diag5::Return_HrMsg(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\idk\\LocationRegistryHelper.h",
        "CLocationPersistedRegPathHelper::GetPersistedRegPath",
        "E_UNEXPECTED",
        v11,
        (__int64)"Path is too long. buff len: %zu. subPath len: %zu",
        (const char *)v8,
        v7);
      return 2147549183LL;
    }
    else
    {
      if ( *a1 )
      {
        v9 = a3[v8 - 1] - 92;
        if ( a3[v8 - 1] == 92 )
          v9 = a3[v8];
        if ( v9 )
        {
          v10 = *a1 - 92;
          if ( *a1 == 92 )
            v10 = a1[1];
          if ( v10 )
            _o_wcscat_s(a3, 255, L"\\");
        }
        _o_wcscat_s(a3, 255, a1);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180032d80  mov     [rsp+arg_0], rbx
0x180032d85  push    rdi
0x180032d86  sub     rsp, 50h
0x180032d8a  mov     rax, r9
0x180032d8d  mov     rdi, r8
0x180032d90  mov     rbx, rcx
0x180032d93  test    rcx, rcx
0x180032d96  jz      loc_180032EE6
0x180032d9c  test    rdx, rdx
0x180032d9f  jz      loc_180032EE6
0x180032da5  test    r8, r8
0x180032da8  jz      loc_180032EE6
0x180032dae  test    rax, rax
0x180032db1  jz      loc_180032EE6
0x180032db7  mov     r9d, 1FEh
0x180032dbd  mov     [rsp+58h+var_38], 0
0x180032dc6  mov     rcx, rax
0x180032dc9  call    cs:__imp_GetPersistedRegistryLocationW
0x180032dcf  test    eax, eax
0x180032dd1  jnz     loc_180032E80
0x180032dd7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180032dde  mov     r8, rax
0x180032de1  inc     r8
0x180032de4  cmp     word ptr [rdi+r8*2], 0
0x180032dea  jnz     short loc_180032DE1
0x180032dec  nop     dword ptr [rax+00h]
0x180032df0  inc     rax
0x180032df3  cmp     word ptr [rbx+rax*2], 0
0x180032df8  jnz     short loc_180032DF0
0x180032dfa  lea     rcx, [r8+1]
0x180032dfe  add     rcx, rax
0x180032e01  cmp     rcx, 0FFh
0x180032e08  jnb     loc_180032E95
0x180032e0e  xor     eax, eax
0x180032e10  cmp     [rbx], ax
0x180032e13  jz      short loc_180032E45
0x180032e15  movzx   edx, word ptr [rdi+r8*2-2]
0x180032e1b  mov     r9d, 5Ch ; '\'
0x180032e21  sub     edx, r9d
0x180032e24  jnz     short loc_180032E30
0x180032e26  movzx   edx, word ptr [rdi+r8*2]
0x180032e2b  movzx   ecx, ax
0x180032e2e  sub     edx, ecx
0x180032e30  test    edx, edx
0x180032e32  jnz     short loc_180032E52
0x180032e34  mov     r8, rbx
0x180032e37  mov     edx, 0FFh
0x180032e3c  mov     rcx, rdi
0x180032e3f  call    cs:__imp__o_wcscat_s
0x180032e45  xor     eax, eax
0x180032e47  mov     rbx, [rsp+58h+arg_0]
0x180032e4c  add     rsp, 50h
0x180032e50  pop     rdi
0x180032e51  retn
0x180032e52  movzx   edx, word ptr [rbx]
0x180032e55  sub     edx, r9d
0x180032e58  jnz     short loc_180032E65
0x180032e5a  movzx   edx, word ptr [rbx+2]
0x180032e5e  xor     eax, eax
0x180032e60  movzx   ecx, ax
0x180032e63  sub     edx, ecx
0x180032e65  test    edx, edx
0x180032e67  jz      short loc_180032E34
0x180032e69  lea     r8, asc_18016EDDC; "\\"
0x180032e70  mov     edx, 0FFh
0x180032e75  mov     rcx, rdi
0x180032e78  call    cs:__imp__o_wcscat_s
0x180032e7e  jmp     short loc_180032E34
0x180032e80  jle     short loc_180032E47
0x180032e82  mov     rbx, [rsp+58h+arg_0]
0x180032e87  movzx   eax, ax
0x180032e8a  or      eax, 80070000h
0x180032e8f  add     rsp, 50h
0x180032e93  pop     rdi
0x180032e94  retn
0x180032e95  mov     rcx, [rsp+58h]; this
0x180032e9a  lea     rdx, aEUnexpected; "E_UNEXPECTED"
0x180032ea1  mov     [rsp+58h+var_18], rax
0x180032ea6  lea     r9, aClocationpersi; "CLocationPersistedRegPathHelper::GetPer"...
0x180032ead  mov     [rsp+58h+var_20], r8; char *
0x180032eb2  lea     rax, aPathIsTooLongB; "Path is too long. buff len: %zu. subPat"...
0x180032eb9  mov     [rsp+58h+var_28], rax; __int64
0x180032ebe  lea     r8, aOnecoreuapDriv_0; "onecoreuap\\drivers\\MobilePC\\Location"...
0x180032ec5  mov     dword ptr [rsp+58h+var_30], 8000FFFFh; wil::details *
0x180032ecd  mov     [rsp+58h+var_38], rdx; char *
0x180032ed2  mov     edx, 35h ; '5'; void *
0x180032ed7  call    ?Return_HrMsg@in1diag5@details@wil@@YAXPEAXIPEBD11J1ZZ; wil::details::in1diag5::Return_HrMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x180032edc  mov     eax, 8000FFFFh
0x180032ee1  jmp     loc_180032E47
0x180032ee6  mov     eax, 80070057h
0x180032eeb  jmp     loc_180032E47
```
