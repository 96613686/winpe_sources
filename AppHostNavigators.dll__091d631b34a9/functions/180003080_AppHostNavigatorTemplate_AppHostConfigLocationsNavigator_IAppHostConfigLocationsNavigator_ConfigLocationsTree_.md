# AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::IsNodeType(ushort *,int *)

- ea: `0x180003080`
- end: `0x18000312c`
- name: `?IsNodeType@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@UEAAJPEAGPEAH@Z`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003080`
- `0x180010624`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::IsNodeType(
        __int64 a1,
        const WCHAR *a2,
        _DWORD *a3)
{
  __int64 v6; // rax
  bool IsEnumValue; // al
  bool v9; // al
  unsigned int v10; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v11[8]; // [rsp+28h] [rbp-20h] BYREF
  LPCWCH lpString2; // [rsp+30h] [rbp-18h]

  if ( !a2 || !a3 )
    return 2147942487LL;
  try
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 40) + 8LL))(*(_QWORD *)(a1 + 40), v11);
    IsEnumValue = Helpers::IsEnumValue(*(LPCWCH *)(v6 + 8), a2);
  }
  catch ( long v10 )
  {
    return v10;
  }
  catch ( ... )
  {
    return 2147549183LL;
  }
  *a3 = IsEnumValue;
  if ( IsEnumValue )
    return 0;
  (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 40) + 88LL))(*(_QWORD *)(a1 + 40), v11);
  v9 = Helpers::IsEnumValue(lpString2, a2);
  *a3 = v9;
  if ( !v9 )
    *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x180003080  mov     [rsp+arg_0], rbx
0x180003085  mov     [rsp+arg_8], rsi
0x18000308a  push    rdi
0x18000308b  sub     rsp, 40h
0x18000308f  mov     rbx, r8
0x180003092  mov     rdi, rdx
0x180003095  mov     rsi, rcx
0x180003098  test    rdx, rdx
0x18000309b  jz      short loc_180003116
0x18000309d  test    rbx, rbx
0x1800030a0  jz      short loc_180003116
0x1800030a2  mov     rcx, [rcx+28h]
0x1800030a6  mov     rax, [rcx]
0x1800030a9  lea     rdx, [rsp+48h+var_20]
0x1800030ae  mov     rax, [rax+8]
0x1800030b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b7  mov     rdx, rdi; lpString1
0x1800030ba  mov     rcx, [rax+8]; lpString2
0x1800030be  call    ?IsEnumValue@Helpers@@SA_NPEBG0@Z; Helpers::IsEnumValue(ushort const *,ushort const *)
0x1800030c3  movzx   eax, al
0x1800030c6  mov     [rbx], eax
0x1800030c8  test    eax, eax
0x1800030ca  jz      short loc_1800030D0
0x1800030cc  xor     eax, eax
0x1800030ce  jmp     short loc_18000311B
0x1800030d0  mov     rcx, [rsi+28h]
0x1800030d4  mov     rax, [rcx]
0x1800030d7  lea     rdx, [rsp+48h+var_20]
0x1800030dc  mov     rax, [rax+58h]
0x1800030e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e5  mov     rdx, rdi; lpString1
0x1800030e8  mov     rcx, [rsp+48h+lpString2]; lpString2
0x1800030ed  call    ?IsEnumValue@Helpers@@SA_NPEBG0@Z; Helpers::IsEnumValue(ushort const *,ushort const *)
0x1800030f2  movzx   eax, al
0x1800030f5  mov     [rbx], eax
0x1800030f7  test    eax, eax
0x1800030f9  jz      short loc_1800030FF
0x1800030fb  xor     eax, eax
0x1800030fd  jmp     short loc_18000311B
0x1800030ff  mov     dword ptr [rbx], 0
0x180003105  xor     eax, eax
0x180003107  jmp     short loc_18000311B
0x180003109  mov     eax, [rsp+48h+var_28]
0x18000310d  jmp     short loc_180003114
0x18000310f  mov     eax, 8000FFFFh
0x180003114  jmp     short loc_18000311B
0x180003116  mov     eax, 80070057h
0x18000311b  mov     rbx, [rsp+48h+arg_0]
0x180003120  mov     rsi, [rsp+48h+arg_8]
0x180003125  add     rsp, 40h
0x180003129  pop     rdi
0x18000312a  retn
```
