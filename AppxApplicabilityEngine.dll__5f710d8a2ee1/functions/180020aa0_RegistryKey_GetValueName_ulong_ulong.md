# RegistryKey::GetValueName(ulong,ulong *)

- ea: `0x180020aa0`
- end: `0x180020b61`
- name: `?GetValueName@RegistryKey@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAK@Z`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000d8f8`
- `0x180013294`
- `0x180020aa0`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180020b0c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180020b0c`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetValueName(__int64 a1, __int64 a2, DWORD a3, DWORD *lpType)
{
  HKEY v4; // rcx
  WCHAR *v6; // rdx
  int v7; // eax
  bool v8; // sf
  DWORD cchValueName; // [rsp+40h] [rbp-E8h] BYREF
  __int64 pExceptionObject; // [rsp+48h] [rbp-E0h] BYREF
  WCHAR ValueName[88]; // [rsp+60h] [rbp-C8h] BYREF

  pExceptionObject = a2;
  v4 = *(HKEY *)(a1 + 64);
  if ( v4 )
  {
    cchValueName = 82;
    v7 = RegEnumValueW(v4, a3, ValueName, &cchValueName, 0, lpType, 0, 0);
    v8 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v8 = v7 < 0;
    }
    if ( v8 )
    {
      LODWORD(pExceptionObject) = v7;
      throw (long *)&pExceptionObject;
    }
    v6 = ValueName;
  }
  else
  {
    v6 = (WCHAR *)&qword_18002C640;
  }
  std::wstring::wstring(a2, v6);
  return a2;
}

```

## disassembly

```asm
0x180020aa0  push    rbx
0x180020aa2  sub     rsp, 120h
0x180020aa9  mov     rax, cs:__security_cookie
0x180020ab0  xor     rax, rsp
0x180020ab3  mov     [rsp+128h+var_18], rax
0x180020abb  mov     [rsp+128h+pExceptionObject], rdx
0x180020ac0  mov     eax, r8d
0x180020ac3  mov     rcx, [rcx+40h]; hKey
0x180020ac7  mov     rbx, rdx
0x180020aca  test    rcx, rcx
0x180020acd  jnz     short loc_180020AD8
0x180020acf  lea     rdx, qword_18002C640
0x180020ad6  jmp     short loc_180020B3D
0x180020ad8  mov     [rsp+128h+lpcbData], 0; lpcbData
0x180020ae1  lea     r8, [rsp+128h+ValueName]; lpValueName
0x180020ae6  mov     [rsp+128h+lpData], 0; lpData
0x180020aef  mov     edx, eax; dwIndex
0x180020af1  mov     [rsp+128h+lpType], r9; lpType
0x180020af6  lea     r9, [rsp+128h+cchValueName]; lpcchValueName
0x180020afb  mov     [rsp+128h+cchValueName], 52h ; 'R'
0x180020b03  mov     [rsp+128h+lpReserved], 0; lpReserved
0x180020b0c  call    cs:__imp_RegEnumValueW
0x180020b12  test    eax, eax
0x180020b14  jle     short loc_180020B20
0x180020b16  movzx   eax, ax
0x180020b19  or      eax, 80070000h
0x180020b1e  test    eax, eax
0x180020b20  jns     short loc_180020B38
0x180020b22  lea     rdx, _TI1J; pThrowInfo
0x180020b29  mov     dword ptr [rsp+128h+pExceptionObject], eax
0x180020b2d  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180020b32  call    _CxxThrowException_0
0x180020b38  lea     rdx, [rsp+128h+ValueName]
0x180020b3d  mov     rcx, rbx
0x180020b40  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180020b45  mov     rax, rbx
0x180020b48  mov     rcx, [rsp+128h+var_18]
0x180020b50  xor     rcx, rsp; StackCookie
0x180020b53  call    __security_check_cookie
0x180020b58  add     rsp, 120h
0x180020b5f  pop     rbx
0x180020b60  retn
```
