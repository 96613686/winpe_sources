# RegistryMultiStringValue::Get(void)

- ea: `0x18000d930`
- end: `0x18000d9b9`
- name: `?Get@RegistryMultiStringValue@@UEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180004080`
- `0x18000d930`
- `0x18000d9c0`
- `0x1800227c0`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryMultiStringValue::Get(__int64 a1, __int64 a2)
{
  _QWORD *v3; // r8
  _BYTE v5[40]; // [rsp+48h] [rbp-40h] BYREF

  v3 = (_QWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) >= 8u )
    v3 = (_QWORD *)*v3;
  (***(void (__fastcall ****)(_QWORD, _BYTE *, _QWORD *, __int64))(a1 + 8))(*(_QWORD *)(a1 + 8), v5, v3, 32);
  WstringContainerFromDelimitedString<std::vector<std::wstring>>(a2, v5, 0);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(v5);
  return a2;
}

```

## disassembly

```asm
0x18000d930  push    rbx
0x18000d932  sub     rsp, 80h
0x18000d939  mov     [rsp+88h+var_50], 0FFFFFFFFFFFFFFFEh
0x18000d942  mov     rax, cs:__security_cookie
0x18000d949  xor     rax, rsp
0x18000d94c  mov     [rsp+88h+var_18], rax
0x18000d951  mov     rbx, rdx
0x18000d954  mov     [rsp+88h+var_48], rdx
0x18000d959  mov     r10, [rcx+8]
0x18000d95d  mov     rax, [r10]
0x18000d960  lea     r8, [rcx+10h]
0x18000d964  cmp     qword ptr [r8+18h], 8
0x18000d969  jb      short loc_18000D96E
0x18000d96b  mov     r8, [r8]
0x18000d96e  mov     r9d, 20h ; ' '
0x18000d974  lea     rdx, [rsp+88h+var_40]
0x18000d979  mov     rcx, r10
0x18000d97c  mov     rax, [rax]
0x18000d97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d984  nop
0x18000d985  xor     r8d, r8d
0x18000d988  lea     rdx, [rsp+88h+var_40]
0x18000d98d  mov     rcx, rbx
0x18000d990  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@G@Z; WstringContainerFromDelimitedString<std::vector<std::wstring>>(std::wstring const &,ushort)
0x18000d995  nop
0x18000d996  lea     rcx, [rsp+88h+var_40]
0x18000d99b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000d9a0  mov     rax, rbx
0x18000d9a3  mov     rcx, [rsp+88h+var_18]
0x18000d9a8  xor     rcx, rsp; StackCookie
0x18000d9ab  call    __security_check_cookie
0x18000d9b0  add     rsp, 80h
0x18000d9b7  pop     rbx
0x18000d9b8  retn
```
