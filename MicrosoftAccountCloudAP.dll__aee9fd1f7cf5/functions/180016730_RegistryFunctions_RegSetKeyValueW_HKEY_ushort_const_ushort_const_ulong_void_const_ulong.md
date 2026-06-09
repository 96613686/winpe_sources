# RegistryFunctions::RegSetKeyValueW(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x180016730`
- end: `0x18001680f`
- name: `?RegSetKeyValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1KPEBXK@Z`
- size: `223`
- prototype: `int(RegistryFunctions *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180016730`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800167d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800167d4`

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
0x180016730  mov     r11, rsp
0x180016733  mov     [r11+8], rbx
0x180016737  mov     [r11+10h], rbp
0x18001673b  push    rsi
0x18001673c  push    rdi
0x18001673d  push    r14
0x18001673f  sub     rsp, 60h
0x180016743  xor     r14d, r14d
0x180016746  mov     rbp, r9
0x180016749  mov     [r11+18h], r14
0x18001674d  mov     rdi, rdx
0x180016750  mov     rbx, rcx
0x180016753  test    r8, r8
0x180016756  jz      short loc_1800167A3
0x180016758  cmp     [r8], r14w
0x18001675c  jz      short loc_1800167A3
0x18001675e  mov     rax, [rcx]
0x180016761  xor     r9d, r9d
0x180016764  mov     [r11-30h], r14
0x180016768  lea     rcx, [r11+18h]
0x18001676c  mov     [r11-38h], rcx
0x180016770  mov     rcx, rbx
0x180016773  mov     [r11-40h], r14
0x180016777  mov     rax, [rax+80h]
0x18001677e  mov     [rsp+78h+var_48], 2
0x180016786  mov     [r11-50h], r14d
0x18001678a  mov     [r11-58h], r14
0x18001678e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016793  mov     esi, eax
0x180016795  test    eax, eax
0x180016797  jnz     short loc_1800167F8
0x180016799  mov     rcx, [rsp+78h+arg_10]
0x1800167a1  jmp     short loc_1800167AE
0x1800167a3  mov     rcx, rdi; hKey
0x1800167a6  mov     [rsp+78h+arg_10], rcx
0x1800167ae  mov     eax, [rsp+78h+arg_30]
0x1800167b5  xor     r8d, r8d; Reserved
0x1800167b8  mov     r9d, [rsp+78h+dwType]; dwType
0x1800167c0  mov     rdx, rbp; lpValueName
0x1800167c3  mov     [rsp+78h+cbData], eax; cbData
0x1800167c7  mov     rax, [rsp+78h+arg_28]
0x1800167cf  mov     [rsp+78h+lpData], rax; lpData
0x1800167d4  call    cs:__imp_RegSetValueExW
0x1800167da  mov     rdx, [rsp+78h+arg_10]
0x1800167e2  mov     esi, eax
0x1800167e4  cmp     rdx, rdi
0x1800167e7  jz      short loc_1800167F8
0x1800167e9  mov     rcx, [rbx]
0x1800167ec  mov     rax, [rcx+8]
0x1800167f0  mov     rcx, rbx
0x1800167f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f8  lea     r11, [rsp+78h+var_18]
0x1800167fd  mov     eax, esi
0x1800167ff  mov     rbx, [r11+20h]
0x180016803  mov     rbp, [r11+28h]
0x180016807  mov     rsp, r11
0x18001680a  pop     r14
0x18001680c  pop     rdi
0x18001680d  pop     rsi
0x18001680e  retn
```
