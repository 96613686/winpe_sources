# RegistryFunctions::RegSetKeyValueW(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x180008920`
- end: `0x1800089ff`
- name: `?RegSetKeyValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1KPEBXK@Z`
- size: `223`
- prototype: `__int64 __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180008920`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800089c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800089c4`

## pseudocode

```c
__int64 __fastcall RegistryFunctions::RegSetKeyValueW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  unsigned int v10; // esi
  HKEY v11; // rcx
  HKEY v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = 0;
  if ( a3 && *a3 )
  {
    v10 = (*(__int64 (__fastcall **)(RegistryFunctions *, HKEY, const unsigned __int16 *, _QWORD, _QWORD, _DWORD, int, _QWORD, HKEY *, _QWORD))(*(_QWORD *)this + 128LL))(
            this,
            a2,
            a3,
            0,
            0,
            0,
            2,
            0,
            &v13,
            0);
    if ( v10 )
      return v10;
    v11 = v13;
  }
  else
  {
    v11 = a2;
    v13 = a2;
  }
  v10 = RegSetValueExW(v11, a4, 0, dwType, lpData, cbData);
  if ( v13 != a2 )
    (*(void (__fastcall **)(RegistryFunctions *))(*(_QWORD *)this + 8LL))(this);
  return v10;
}

```

## disassembly

```asm
0x180008920  mov     r11, rsp
0x180008923  mov     [r11+8], rbx
0x180008927  mov     [r11+10h], rbp
0x18000892b  push    rsi
0x18000892c  push    rdi
0x18000892d  push    r14
0x18000892f  sub     rsp, 60h
0x180008933  xor     r14d, r14d
0x180008936  mov     rbp, r9
0x180008939  mov     [r11+18h], r14
0x18000893d  mov     rdi, rdx
0x180008940  mov     rbx, rcx
0x180008943  test    r8, r8
0x180008946  jz      short loc_180008993
0x180008948  cmp     [r8], r14w
0x18000894c  jz      short loc_180008993
0x18000894e  mov     rax, [rcx]
0x180008951  xor     r9d, r9d
0x180008954  mov     [r11-30h], r14
0x180008958  lea     rcx, [r11+18h]
0x18000895c  mov     [r11-38h], rcx
0x180008960  mov     rcx, rbx
0x180008963  mov     [r11-40h], r14
0x180008967  mov     rax, [rax+80h]
0x18000896e  mov     [rsp+78h+var_48], 2
0x180008976  mov     [r11-50h], r14d
0x18000897a  mov     [r11-58h], r14
0x18000897e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008983  mov     esi, eax
0x180008985  test    eax, eax
0x180008987  jnz     short loc_1800089E8
0x180008989  mov     rcx, [rsp+78h+arg_10]
0x180008991  jmp     short loc_18000899E
0x180008993  mov     rcx, rdi; hKey
0x180008996  mov     [rsp+78h+arg_10], rcx
0x18000899e  mov     eax, [rsp+78h+arg_30]
0x1800089a5  xor     r8d, r8d; Reserved
0x1800089a8  mov     r9d, [rsp+78h+dwType]; dwType
0x1800089b0  mov     rdx, rbp; lpValueName
0x1800089b3  mov     [rsp+78h+cbData], eax; cbData
0x1800089b7  mov     rax, [rsp+78h+arg_28]
0x1800089bf  mov     [rsp+78h+lpData], rax; lpData
0x1800089c4  call    cs:__imp_RegSetValueExW
0x1800089ca  mov     rdx, [rsp+78h+arg_10]
0x1800089d2  mov     esi, eax
0x1800089d4  cmp     rdx, rdi
0x1800089d7  jz      short loc_1800089E8
0x1800089d9  mov     rcx, [rbx]
0x1800089dc  mov     rax, [rcx+8]
0x1800089e0  mov     rcx, rbx
0x1800089e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e8  lea     r11, [rsp+78h+var_18]
0x1800089ed  mov     eax, esi
0x1800089ef  mov     rbx, [r11+20h]
0x1800089f3  mov     rbp, [r11+28h]
0x1800089f7  mov     rsp, r11
0x1800089fa  pop     r14
0x1800089fc  pop     rdi
0x1800089fd  pop     rsi
0x1800089fe  retn
```
