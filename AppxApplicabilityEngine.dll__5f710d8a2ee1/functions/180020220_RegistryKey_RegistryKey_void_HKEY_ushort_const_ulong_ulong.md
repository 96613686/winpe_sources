# RegistryKey::RegistryKey(void *,HKEY__ *,ushort const *,ulong,ulong)

- ea: `0x180020220`
- end: `0x180020317`
- name: `??0RegistryKey@@QEAA@PEAXPEAUHKEY__@@PEBGKK@Z`
- size: `247`
- prototype: `RegistryKey *__fastcall(RegistryKey *__hidden this, void *, HKEY hKey, const unsigned __int16 *, unsigned int pExceptionObject, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800107e8`
- `0x18001e964`

## callees

- `0x18000d8f8`
- `0x180013294`
- `0x180020220`
- `0x180020c18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800202b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800202fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800202b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800202fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
RegistryKey *__fastcall RegistryKey::RegistryKey(
        RegistryKey *this,
        void *a2,
        HKEY hKey,
        const unsigned __int16 *a4,
        unsigned int pExceptionObject)
{
  HKEY *phkResult; // r14
  const unsigned __int16 *v10; // r8
  int v11; // eax
  bool v12; // sf

  *(_QWORD *)this = &RegistryKey::`vftable';
  phkResult = (HKEY *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  std::wstring::wstring((char *)this + 16, a4);
  *((_DWORD *)this + 14) = 131097;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  if ( hKey == HKEY_CURRENT_USER )
  {
    RegistryKey::InitForUserHive((HKEY *)this, a2, v10, a4);
  }
  else
  {
    v11 = RegOpenKeyExW(hKey, a4, 0, 0x20019u, (PHKEY)this + 8);
    if ( v11 == 2 )
    {
      RegOpenKeyExW(hKey, 0, 0, 0x20006u, phkResult);
    }
    else
    {
      v12 = v11 < 0;
      if ( v11 > 0 )
      {
        v11 = (unsigned __int16)v11 | 0x80070000;
        v12 = v11 < 0;
      }
      if ( v12 )
      {
        pExceptionObject = v11;
        throw (long *)&pExceptionObject;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180020220  mov     rax, rsp
0x180020223  mov     [rax+8], rcx
0x180020227  push    rsi
0x180020228  push    rdi
0x180020229  push    r14
0x18002022b  sub     rsp, 40h
0x18002022f  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180020237  mov     [rax+10h], rbx
0x18002023b  mov     [rax+18h], rbp
0x18002023f  mov     rdi, r9
0x180020242  mov     rsi, r8
0x180020245  mov     rbp, rdx
0x180020248  mov     rbx, rcx
0x18002024b  lea     rax, ??_7RegistryKey@@6B@; const RegistryKey::`vftable'
0x180020252  mov     [rcx], rax
0x180020255  lea     r14, [rcx+8]
0x180020259  mov     qword ptr [r14], 0
0x180020260  add     rcx, 10h
0x180020264  mov     rdx, r9
0x180020267  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002026c  nop
0x18002026d  mov     r9d, 20019h; samDesired
0x180020273  mov     [rbx+38h], r9d
0x180020277  lea     rax, [rbx+40h]
0x18002027b  mov     qword ptr [rax], 0
0x180020282  mov     dword ptr [rbx+48h], 0
0x180020289  cmp     rsi, 0FFFFFFFF80000001h
0x180020290  jnz     short loc_1800202A2
0x180020292  mov     r9, rdi; unsigned __int16 *
0x180020295  mov     rdx, rbp; void *
0x180020298  mov     rcx, rbx; this
0x18002029b  call    ?InitForUserHive@RegistryKey@@IEAAXPEAXPEBG1K@Z; RegistryKey::InitForUserHive(void *,ushort const *,ushort const *,ulong)
0x1800202a0  jmp     short loc_180020301
0x1800202a2  mov     [rsp+58h+phkResult], rax; phkResult
0x1800202a7  xor     r8d, r8d; ulOptions
0x1800202aa  mov     rdx, rdi; lpSubKey
0x1800202ad  mov     rcx, rsi; hKey
0x1800202b0  call    cs:__imp_RegOpenKeyExW
0x1800202b6  cmp     eax, 2
0x1800202b9  jz      short loc_1800202E7
0x1800202bb  test    eax, eax
0x1800202bd  jle     short loc_1800202C9
0x1800202bf  movzx   eax, ax
0x1800202c2  or      eax, 80070000h
0x1800202c7  test    eax, eax
0x1800202c9  jns     short loc_180020301
0x1800202cb  mov     [rsp+58h+pExceptionObject], eax
0x1800202d2  lea     rdx, _TI1J; pThrowInfo
0x1800202d9  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800202e1  call    _CxxThrowException_0
0x1800202e7  mov     [rsp+58h+phkResult], r14; phkResult
0x1800202ec  mov     r9d, 20006h; samDesired
0x1800202f2  xor     r8d, r8d; ulOptions
0x1800202f5  xor     edx, edx; lpSubKey
0x1800202f7  mov     rcx, rsi; hKey
0x1800202fa  call    cs:__imp_RegOpenKeyExW
0x180020300  nop
0x180020301  mov     rax, rbx
0x180020304  mov     rbx, [rsp+58h+arg_8]
0x180020309  mov     rbp, [rsp+58h+arg_10]
0x18002030e  add     rsp, 40h
0x180020312  pop     r14
0x180020314  pop     rdi
0x180020315  pop     rsi
0x180020316  retn
```
