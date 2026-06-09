# RegistryKey::EnsureKeyExists(void)

- ea: `0x1800106a8`
- end: `0x18001074d`
- name: `?EnsureKeyExists@RegistryKey@@AEAAXXZ`
- size: `165`
- prototype: `void __fastcall(RegistryKey *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010510`
- `0x180010590`

## callees

- `0x1800106a8`
- `0x180013294`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001071c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001071c`

## pseudocode

```c
void __fastcall RegistryKey::EnsureKeyExists(RegistryKey *this)
{
  const WCHAR *v1; // rdx
  int Key; // eax
  bool v3; // sf
  int pExceptionObject; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 8) )
  {
    if ( !*((_QWORD *)this + 1) )
    {
      pExceptionObject = -2147418113;
      throw (long *)&pExceptionObject;
    }
    v1 = (const WCHAR *)((char *)this + 16);
    if ( *((_QWORD *)this + 5) >= 8u )
      v1 = *(const WCHAR **)v1;
    Key = RegCreateKeyExW(
            *((HKEY *)this + 1),
            v1,
            0,
            0,
            *((_DWORD *)this + 18),
            *((_DWORD *)this + 14),
            0,
            (PHKEY)this + 8,
            0);
    v3 = Key < 0;
    if ( Key > 0 )
    {
      Key = (unsigned __int16)Key | 0x80070000;
      v3 = Key < 0;
    }
    if ( v3 )
    {
      pExceptionObject = Key;
      throw (long *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x1800106a8  sub     rsp, 58h
0x1800106ac  lea     rax, [rcx+40h]
0x1800106b0  cmp     qword ptr [rax], 0
0x1800106b4  jnz     loc_180010748
0x1800106ba  cmp     qword ptr [rcx+8], 0
0x1800106bf  jnz     short loc_1800106DB
0x1800106c1  lea     rdx, _TI1J; pThrowInfo
0x1800106c8  mov     [rsp+58h+pExceptionObject], 8000FFFFh
0x1800106d0  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800106d5  call    _CxxThrowException_0
0x1800106db  mov     r8d, [rcx+38h]
0x1800106df  lea     rdx, [rcx+10h]
0x1800106e3  cmp     qword ptr [rdx+18h], 8
0x1800106e8  mov     r9d, [rcx+48h]
0x1800106ec  jb      short loc_1800106F1
0x1800106ee  mov     rdx, [rdx]; lpSubKey
0x1800106f1  mov     rcx, [rcx+8]; hKey
0x1800106f5  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800106fe  mov     [rsp+58h+phkResult], rax; phkResult
0x180010703  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001070c  mov     [rsp+58h+samDesired], r8d; samDesired
0x180010711  xor     r8d, r8d; Reserved
0x180010714  mov     [rsp+58h+dwOptions], r9d; dwOptions
0x180010719  xor     r9d, r9d; lpClass
0x18001071c  call    cs:__imp_RegCreateKeyExW
0x180010722  test    eax, eax
0x180010724  jle     short loc_180010730
0x180010726  movzx   eax, ax
0x180010729  or      eax, 80070000h
0x18001072e  test    eax, eax
0x180010730  jns     short loc_180010748
0x180010732  lea     rdx, _TI1J; pThrowInfo
0x180010739  mov     [rsp+58h+pExceptionObject], eax
0x18001073d  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180010742  call    _CxxThrowException_0
0x180010748  add     rsp, 58h
0x18001074c  retn
```
