# RegistryKey::CreateSubKey(ushort const *)

- ea: `0x180010590`
- end: `0x1800106a0`
- name: `?CreateSubKey@RegistryKey@@UEAA?AV?$shared_ptr@VIRegistryKey@@@tr1@std@@PEBG@Z`
- size: `272`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000d8f8`
- `0x180010590`
- `0x1800106a8`
- `0x180011a64`
- `0x180013294`
- `0x180020040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800105fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800105fd`

## pseudocode

```c
__int64 __fastcall RegistryKey::CreateSubKey(__int64 a1, __int64 a2, const WCHAR *a3)
{
  int v6; // eax
  bool v7; // sf
  _QWORD *v8; // rdi
  HKEY v9; // rbx
  _QWORD *pExceptionObject; // [rsp+70h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+20h] BYREF

  RegistryKey::EnsureKeyExists((RegistryKey *)a1);
  phkResult = 0;
  v6 = RegCreateKeyExW(*(HKEY *)(a1 + 64), a3, 0, 0, *(_DWORD *)(a1 + 72), 0x2001Fu, 0, &phkResult, 0);
  v7 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = v6 < 0;
  }
  if ( v7 )
  {
    LODWORD(pExceptionObject) = v6;
    throw (long *)&pExceptionObject;
  }
  v8 = operator new(0x50u);
  pExceptionObject = v8;
  if ( v8 )
  {
    v9 = phkResult;
    *v8 = &RegistryKey::`vftable';
    v8[1] = 0;
    std::wstring::wstring(v8 + 2, &qword_18002C640);
    *((_DWORD *)v8 + 14) = 0;
    v8[8] = v9;
    *((_DWORD *)v8 + 18) = 0;
  }
  else
  {
    v8 = 0;
  }
  std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(a2, v8);
  return a2;
}

```

## disassembly

```asm
0x180010590  mov     rax, rsp
0x180010593  push    rdi
0x180010594  sub     rsp, 60h
0x180010598  mov     qword ptr [rax-10h], 0FFFFFFFFFFFFFFFEh
0x1800105a0  mov     [rax+10h], rbx
0x1800105a4  mov     [rax+18h], rsi
0x1800105a8  mov     rdi, r8
0x1800105ab  mov     rsi, rdx
0x1800105ae  mov     rbx, rcx
0x1800105b1  call    ?EnsureKeyExists@RegistryKey@@AEAAXXZ; RegistryKey::EnsureKeyExists(void)
0x1800105b6  mov     [rsp+68h+arg_18], 0
0x1800105c2  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x1800105cb  lea     rax, [rsp+68h+arg_18]
0x1800105d3  mov     [rsp+68h+phkResult], rax; phkResult
0x1800105d8  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800105e1  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x1800105e9  mov     eax, [rbx+48h]
0x1800105ec  mov     [rsp+68h+dwOptions], eax; dwOptions
0x1800105f0  xor     r9d, r9d; lpClass
0x1800105f3  xor     r8d, r8d; Reserved
0x1800105f6  mov     rdx, rdi; lpSubKey
0x1800105f9  mov     rcx, [rbx+40h]; hKey
0x1800105fd  call    cs:__imp_RegCreateKeyExW
0x180010603  test    eax, eax
0x180010605  jle     short loc_180010611
0x180010607  movzx   eax, ax
0x18001060a  or      eax, 80070000h
0x18001060f  test    eax, eax
0x180010611  jns     short loc_180010629
0x180010613  mov     dword ptr [rsp+68h+pExceptionObject], eax
0x180010617  lea     rdx, _TI1J; pThrowInfo
0x18001061e  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180010623  call    _CxxThrowException_0
0x180010629  mov     ecx, 50h ; 'P'; Size
0x18001062e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010633  mov     rdi, rax
0x180010636  mov     [rsp+68h+pExceptionObject], rax
0x18001063b  test    rax, rax
0x18001063e  jz      short loc_18001067E
0x180010640  mov     rbx, [rsp+68h+arg_18]
0x180010648  lea     rax, ??_7RegistryKey@@6B@; const RegistryKey::`vftable'
0x18001064f  mov     [rdi], rax
0x180010652  mov     qword ptr [rdi+8], 0
0x18001065a  lea     rcx, [rdi+10h]
0x18001065e  lea     rdx, qword_18002C640
0x180010665  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001066a  mov     dword ptr [rdi+38h], 0
0x180010671  mov     [rdi+40h], rbx
0x180010675  mov     dword ptr [rdi+48h], 0
0x18001067c  jmp     short loc_180010680
0x18001067e  xor     edi, edi
0x180010680  mov     rdx, rdi
0x180010683  mov     rcx, rsi
0x180010686  call    ??$?0VRegistryKey@@@?$shared_ptr@VIRegistryKey@@@tr1@std@@QEAA@PEAVRegistryKey@@@Z; std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(RegistryKey *)
0x18001068b  mov     rax, rsi
0x18001068e  lea     r11, [rsp+68h+var_8]
0x180010693  mov     rbx, [r11+18h]
0x180010697  mov     rsi, [r11+20h]
0x18001069b  mov     rsp, r11
0x18001069e  pop     rdi
0x18001069f  retn
```
