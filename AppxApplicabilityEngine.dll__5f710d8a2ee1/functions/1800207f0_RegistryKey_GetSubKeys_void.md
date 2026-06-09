# RegistryKey::GetSubKeys(void)

- ea: `0x1800207f0`
- end: `0x180020921`
- name: `?GetSubKeys@RegistryKey@@UEBA?AV?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@XZ`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800107e8`
- `0x180011a64`
- `0x180020040`
- `0x1800207f0`
- `0x180020edc`
- `0x1800211a8`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020899`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020899`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall RegistryKey::GetSubKeys(__int64 a1, _QWORD *a2)
{
  DWORD i; // edi
  RegistryKey *v5; // rax
  unsigned int v6; // r9d
  __int64 v7; // rdx
  unsigned int lpReserved; // [rsp+20h] [rbp-278h]
  DWORD cchName; // [rsp+44h] [rbp-254h] BYREF
  __int64 v11; // [rsp+48h] [rbp-250h]
  _QWORD *v12; // [rsp+50h] [rbp-248h]
  RegistryKey *v13; // [rsp+58h] [rbp-240h]
  _BYTE v14[8]; // [rsp+60h] [rbp-238h] BYREF
  std::tr1::_Ref_count_base *v15; // [rsp+68h] [rbp-230h]
  WCHAR Name[264]; // [rsp+70h] [rbp-228h] BYREF

  v11 = -2;
  v12 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  if ( *(_QWORD *)(a1 + 64) )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      if ( RegEnumKeyExW(*(HKEY *)(a1 + 64), i, Name, &cchName, 0, 0, 0, 0) )
        break;
      v5 = (RegistryKey *)operator new(0x50u);
      v13 = v5;
      if ( v5 )
        v5 = RegistryKey::RegistryKey(v5, *(HKEY *)(a1 + 64), Name, v6, lpReserved);
      v7 = std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(v14, v5);
      std::vector<std::tr1::shared_ptr<IRegistryKey>>::push_back(a2, v7);
      if ( v15 )
        std::tr1::_Ref_count_base::_Decref(v15);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800207f0  mov     rax, rsp
0x1800207f3  push    rdi
0x1800207f4  sub     rsp, 290h
0x1800207fb  mov     [rsp+298h+var_250], 0FFFFFFFFFFFFFFFEh
0x180020804  mov     [rax+18h], rbx
0x180020808  mov     [rax+20h], rsi
0x18002080c  mov     rax, cs:__security_cookie
0x180020813  xor     rax, rsp
0x180020816  mov     [rsp+298h+var_18], rax
0x18002081e  mov     rbx, rdx
0x180020821  mov     rsi, rcx
0x180020824  mov     [rsp+298h+var_248], rdx
0x180020829  mov     [rsp+298h+var_258], 0
0x180020831  mov     qword ptr [rdx], 0
0x180020838  mov     qword ptr [rdx+8], 0
0x180020840  mov     qword ptr [rdx+10h], 0
0x180020848  mov     [rsp+298h+var_258], 1
0x180020850  cmp     qword ptr [rcx+40h], 0
0x180020855  jz      loc_1800208F8
0x18002085b  xor     edi, edi
0x18002085d  mov     [rsp+298h+cchName], 104h
0x180020865  mov     [rsp+298h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002086e  mov     [rsp+298h+lpcchClass], 0; lpcchClass
0x180020877  mov     [rsp+298h+lpClass], 0; lpClass
0x180020880  mov     [rsp+298h+lpReserved], 0; unsigned int
0x180020889  lea     r9, [rsp+298h+cchName]; lpcchName
0x18002088e  lea     r8, [rsp+298h+Name]; lpName
0x180020893  mov     edx, edi; dwIndex
0x180020895  mov     rcx, [rsi+40h]; hKey
0x180020899  call    cs:__imp_RegEnumKeyExW
0x18002089f  test    eax, eax
0x1800208a1  jnz     short loc_1800208F8
0x1800208a3  lea     ecx, [rax+50h]; Size
0x1800208a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800208ab  mov     [rsp+298h+var_240], rax
0x1800208b0  test    rax, rax
0x1800208b3  jz      short loc_1800208C7
0x1800208b5  lea     r8, [rsp+298h+Name]; unsigned __int16 *
0x1800208ba  mov     rdx, [rsi+40h]; HKEY
0x1800208be  mov     rcx, rax; this
0x1800208c1  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@PEBGKK@Z; RegistryKey::RegistryKey(HKEY__ *,ushort const *,ulong,ulong)
0x1800208c6  nop
0x1800208c7  mov     rdx, rax
0x1800208ca  lea     rcx, [rsp+298h+var_238]
0x1800208cf  call    ??$?0VRegistryKey@@@?$shared_ptr@VIRegistryKey@@@tr1@std@@QEAA@PEAVRegistryKey@@@Z; std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(RegistryKey *)
0x1800208d4  nop
0x1800208d5  mov     rdx, rax
0x1800208d8  mov     rcx, rbx
0x1800208db  call    ?push_back@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@QEAAX$$QEAV?$shared_ptr@VIRegistryKey@@@tr1@2@@Z; std::vector<std::tr1::shared_ptr<IRegistryKey>>::push_back(std::tr1::shared_ptr<IRegistryKey> &&)
0x1800208e0  nop
0x1800208e1  mov     rcx, [rsp+298h+var_230]; this
0x1800208e6  test    rcx, rcx
0x1800208e9  jz      short loc_1800208F1
0x1800208eb  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800208f0  nop
0x1800208f1  inc     edi
0x1800208f3  jmp     loc_18002085D
0x1800208f8  mov     rax, rbx
0x1800208fb  mov     rcx, [rsp+298h+var_18]
0x180020903  xor     rcx, rsp; StackCookie
0x180020906  call    __security_check_cookie
0x18002090b  lea     r11, [rsp+298h+var_8]
0x180020913  mov     rbx, [r11+20h]
0x180020917  mov     rsi, [r11+28h]
0x18002091b  mov     rsp, r11
0x18002091e  pop     rdi
0x18002091f  retn
```
