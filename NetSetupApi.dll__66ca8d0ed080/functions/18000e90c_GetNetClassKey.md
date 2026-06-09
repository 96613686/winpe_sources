# GetNetClassKey

- ea: `0x18000e90c`
- end: `0x18000ea17`
- name: `GetNetClassKey`
- size: `267`
- prototype: `RegistryKey *__fastcall(RegistryKey *this, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180006af8`

## callees

- `0x180005328`
- `0x1800072d8`
- `0x18000895c`
- `0x18000e90c`
- `0x18000ec70`
- `0x180011500`
- `0x1800117e8`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e9b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e9b2`

## pseudocode

```c
RegistryKey *__fastcall GetNetClassKey(RegistryKey *this, __int64 a2)
{
  NetSetup2::Property *lpVtbl; // rcx
  HKEY Uint64; // rbx
  int v5; // eax
  int pExceptionObject; // [rsp+38h] [rbp-29h] BYREF
  __int64 v8; // [rsp+40h] [rbp-21h] BYREF
  _QWORD *v9; // [rsp+48h] [rbp-19h] BYREF
  int v10; // [rsp+50h] [rbp-11h]
  __int128 v11; // [rsp+54h] [rbp-Dh]
  __int64 v12; // [rsp+68h] [rbp+7h]
  _BYTE v13[24]; // [rsp+70h] [rbp+Fh] BYREF
  _BYTE v14[24]; // [rsp+88h] [rbp+27h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+3Fh] BYREF

  v12 = -2;
  phkResult = (HKEY)this;
  v8 = a2;
  v9 = 0;
  v10 = 9;
  v11 = 0;
  lpVtbl = (NetSetup2::Property *)NetSetup2::ActiveObject::GetProperty(
                                    (NetSetup2::ActiveObject *)&v8,
                                    (const struct _NETSETUPPROPKEY *)v13,
                                    (unsigned int)NETSETUPPKEY_Transaction_CurrentControlSetRegistryHandle).lpVtbl;
  Uint64 = (HKEY)NetSetup2::Property::GetUint64(lpVtbl);
  std::vector<unsigned char>::_Tidy((__int64)v14);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v9);
  phkResult = 0;
  v5 = RegOpenKeyExW(Uint64, L"Control\\Class\\{4d36e972-e325-11ce-bfc1-08002be10318}", 0, 0x20019u, &phkResult);
  if ( phkResult )
  {
    RegistryKey::RegistryKey(this, phkResult);
  }
  else
  {
    if ( v5 != 2 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      pExceptionObject = v5;
      throw (long *)&pExceptionObject;
    }
    *(_QWORD *)this = phkResult;
  }
  return this;
}

```

## disassembly

```asm
0x18000e90c  mov     rax, rsp
0x18000e90f  push    rbp
0x18000e910  lea     rbp, [rax-5Fh]
0x18000e914  sub     rsp, 0B0h
0x18000e91b  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x18000e923  mov     [rax+10h], rbx
0x18000e927  mov     [rax+18h], rdi
0x18000e92b  mov     rax, cs:__security_cookie
0x18000e932  xor     rax, rsp
0x18000e935  mov     [rbp+57h+var_10], rax
0x18000e939  mov     rdi, rcx
0x18000e93c  mov     [rbp+57h+var_18], rcx
0x18000e940  xorps   xmm0, xmm0
0x18000e943  mov     [rbp+57h+var_78], rdx
0x18000e947  mov     [rbp+57h+var_70], 0
0x18000e94f  mov     [rbp+57h+var_68], 9
0x18000e956  movdqu  [rbp+57h+var_64], xmm0
0x18000e95b  lea     r8, NETSETUPPKEY_Transaction_CurrentControlSetRegistryHandle
0x18000e962  lea     rdx, [rbp+57h+var_48]; struct _NETSETUPPROPKEY *
0x18000e966  lea     rcx, [rbp+57h+var_78]; this
0x18000e96a  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18000e96f  nop
0x18000e970  mov     rcx, rax; this
0x18000e973  call    ?GetUint64@Property@NetSetup2@@QEBA_KXZ; NetSetup2::Property::GetUint64(void)
0x18000e978  mov     rbx, rax
0x18000e97b  lea     rcx, [rbp+57h+var_30]
0x18000e97f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000e984  nop
0x18000e985  lea     rcx, [rbp+57h+var_70]
0x18000e989  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18000e98e  mov     [rbp+57h+var_18], 0
0x18000e996  lea     rax, [rbp+57h+var_18]
0x18000e99a  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18000e99f  mov     r9d, 20019h; samDesired
0x18000e9a5  xor     r8d, r8d; ulOptions
0x18000e9a8  lea     rdx, aControlClass4d; "Control\\Class\\{4d36e972-e325-11ce-bfc"...
0x18000e9af  mov     rcx, rbx; hKey
0x18000e9b2  call    cs:__imp_RegOpenKeyExW
0x18000e9b8  mov     rdx, [rbp+57h+var_18]; HKEY
0x18000e9bc  test    rdx, rdx
0x18000e9bf  jnz     short loc_18000E9EB
0x18000e9c1  cmp     eax, 2
0x18000e9c4  jnz     short loc_18000E9CB
0x18000e9c6  mov     [rdi], rdx
0x18000e9c9  jmp     short loc_18000E9F3
0x18000e9cb  test    eax, eax
0x18000e9cd  jle     short loc_18000E9D7
0x18000e9cf  movzx   eax, ax
0x18000e9d2  or      eax, 80070000h
0x18000e9d7  mov     [rbp+57h+pExceptionObject], eax
0x18000e9da  lea     rdx, _TI1J; pThrowInfo
0x18000e9e1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000e9e5  call    _CxxThrowException_0
0x18000e9eb  mov     rcx, rdi; this
0x18000e9ee  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18000e9f3  mov     rax, rdi
0x18000e9f6  mov     rcx, [rbp+57h+var_10]
0x18000e9fa  xor     rcx, rsp; StackCookie
0x18000e9fd  call    __security_check_cookie
0x18000ea02  lea     r11, [rsp+0B0h+var_s0]
0x18000ea0a  mov     rbx, [r11+18h]
0x18000ea0e  mov     rdi, [r11+20h]
0x18000ea12  mov     rsp, r11
0x18000ea15  pop     rbp
0x18000ea16  retn
```
