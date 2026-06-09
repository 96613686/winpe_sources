# RegistryKey::InitForUserHive(void *,ushort const *,ushort const *,ulong)

- ea: `0x180020c18`
- end: `0x180020d85`
- name: `?InitForUserHive@RegistryKey@@IEAAXPEAXPEBG1K@Z`
- size: `365`
- prototype: `void(RegistryKey *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180020220`

## callees

- `0x180013294`
- `0x18001e844`
- `0x18001ebec`
- `0x180020c18`
- `0x1800227c0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020c78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020cfd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020c78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020cfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall RegistryKey::InitForUserHive(
        HKEY *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HKEY *v6; // rdi
  int v7; // ebx
  _QWORD *v8; // rdx
  int v9; // eax
  bool v10; // sf
  int pExceptionObject; // [rsp+38h] [rbp-41h] BYREF
  __int64 v12; // [rsp+40h] [rbp-39h]
  int v13; // [rsp+48h] [rbp-31h]
  void *v14; // [rsp+50h] [rbp-29h]
  __int64 v15; // [rsp+58h] [rbp-21h]
  _QWORD v16[3]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD *v17; // [rsp+78h] [rbp-1h]
  _QWORD v18[5]; // [rsp+80h] [rbp+7h] BYREF

  v12 = -2;
  v13 = 131097;
  v14 = a2;
  v15 = -2147483647;
  v6 = this + 1;
  v7 = RegOpenKeyExW(HKEY_CURRENT_USER, 0, 0, 0x20019u, this + 1);
  if ( RegCloseKey )
  {
    v16[0] = &std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<long (*const)(HKEY__ *),0>,long,HKEY__ *>::`vftable';
    v16[1] = RegCloseKey;
    v17 = v16;
  }
  else
  {
    v17 = 0;
  }
  std::unique_ptr<void,std::tr1::function<void * (void *)>>::unique_ptr<void,std::tr1::function<void * (void *)>>(
    v18,
    *v6,
    v16);
  if ( v17 )
  {
    v8 = v16;
    LOBYTE(v8) = v17 != v16;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v17 + 24LL))(v17, v8);
    v17 = 0;
  }
  if ( v7 )
  {
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    pExceptionObject = v7;
    throw (long *)&pExceptionObject;
  }
  v9 = RegOpenKeyExW(*v6, a4, 0, 0x20019u, this + 8);
  if ( v9 != 2 )
  {
    v10 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = v9 < 0;
    }
    if ( v10 )
    {
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
  }
  v18[0] = 0;
  std::unique_ptr<void,std::tr1::function<void * (void *)>>::~unique_ptr<void,std::tr1::function<void * (void *)>>(v18);
}

```

## disassembly

```asm
0x180020c18  mov     rax, rsp
0x180020c1b  push    rbp
0x180020c1c  push    rdi
0x180020c1d  push    r14
0x180020c1f  lea     rbp, [rax-57h]
0x180020c23  sub     rsp, 0B0h
0x180020c2a  mov     [rbp+4Fh+var_88], 0FFFFFFFFFFFFFFFEh
0x180020c32  mov     [rax+10h], rbx
0x180020c36  mov     [rax+18h], rsi
0x180020c3a  mov     rax, cs:__security_cookie
0x180020c41  xor     rax, rsp
0x180020c44  mov     [rbp+4Fh+var_20], rax
0x180020c48  mov     r14, r9
0x180020c4b  mov     rsi, rcx
0x180020c4e  mov     [rbp+4Fh+var_80], 20019h
0x180020c55  mov     [rbp+4Fh+var_78], rdx
0x180020c59  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180020c60  mov     [rbp+4Fh+var_70], rcx
0x180020c64  lea     rdi, [rsi+8]
0x180020c68  mov     [rsp+0C0h+phkResult], rdi; phkResult
0x180020c6d  mov     r9d, 20019h; samDesired
0x180020c73  xor     r8d, r8d; ulOptions
0x180020c76  xor     edx, edx; lpSubKey
0x180020c78  call    cs:__imp_RegOpenKeyExW
0x180020c7e  mov     ebx, eax
0x180020c80  mov     rax, cs:__imp_RegCloseKey
0x180020c87  test    rax, rax
0x180020c8a  jnz     short loc_180020C92
0x180020c8c  mov     [rbp+4Fh+var_50], rax
0x180020c90  jmp     short loc_180020CA9
0x180020c92  lea     rcx, ??_7?$_Impl_no_alloc1@U?$_Callable_fun@Q6AJPEAUHKEY__@@@Z$0A@@tr1@std@@JPEAUHKEY__@@@tr1@std@@6B@; const std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<long (*const)(HKEY__ *),0>,long,HKEY__ *>::`vftable'
0x180020c99  mov     [rbp+4Fh+var_68], rcx
0x180020c9d  mov     [rbp+4Fh+var_60], rax
0x180020ca1  lea     rax, [rbp+4Fh+var_68]
0x180020ca5  mov     [rbp+4Fh+var_50], rax
0x180020ca9  lea     r8, [rbp+4Fh+var_68]
0x180020cad  mov     rdx, [rdi]
0x180020cb0  lea     rcx, [rbp+4Fh+var_48]
0x180020cb4  call    ??0?$unique_ptr@XV?$function@$$A6APEAXPEAX@Z@tr1@std@@@std@@QEAA@PEAX$$QEAV?$function@$$A6APEAXPEAX@Z@tr1@1@@Z; std::unique_ptr<void,std::tr1::function<void * (void *)>>::unique_ptr<void,std::tr1::function<void * (void *)>>(void *,std::tr1::function<void * (void *)> &&)
0x180020cb9  nop
0x180020cba  mov     rcx, [rbp+4Fh+var_50]
0x180020cbe  test    rcx, rcx
0x180020cc1  jz      short loc_180020CE1
0x180020cc3  mov     rax, [rcx]
0x180020cc6  lea     rdx, [rbp+4Fh+var_68]
0x180020cca  cmp     rcx, rdx
0x180020ccd  setnz   dl
0x180020cd0  mov     rax, [rax+18h]
0x180020cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cd9  mov     [rbp+4Fh+var_50], 0
0x180020ce1  test    ebx, ebx
0x180020ce3  jnz     short loc_180020D2C
0x180020ce5  lea     rax, [rsi+40h]
0x180020ce9  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180020cee  mov     r9d, 20019h; samDesired
0x180020cf4  xor     r8d, r8d; ulOptions
0x180020cf7  mov     rdx, r14; lpSubKey
0x180020cfa  mov     rcx, [rdi]; hKey
0x180020cfd  call    cs:__imp_RegOpenKeyExW
0x180020d03  cmp     eax, 2
0x180020d06  jz      short loc_180020D4F
0x180020d08  test    eax, eax
0x180020d0a  jle     short loc_180020D16
0x180020d0c  movzx   eax, ax
0x180020d0f  or      eax, 80070000h
0x180020d14  test    eax, eax
0x180020d16  jns     short loc_180020D4F
0x180020d18  mov     [rbp+4Fh+pExceptionObject], eax
0x180020d1b  lea     rdx, _TI1J; pThrowInfo
0x180020d22  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180020d26  call    _CxxThrowException_0
0x180020d2c  jle     short loc_180020D37
0x180020d2e  movzx   ebx, bx
0x180020d31  or      ebx, 80070000h
0x180020d37  test    ebx, ebx
0x180020d39  jns     short loc_180020D4F
0x180020d3b  mov     [rbp+4Fh+pExceptionObject], ebx
0x180020d3e  lea     rdx, _TI1J; pThrowInfo
0x180020d45  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180020d49  call    _CxxThrowException_0
0x180020d4f  mov     [rbp+4Fh+var_48], 0
0x180020d57  lea     rcx, [rbp+4Fh+var_48]
0x180020d5b  call    ??1?$unique_ptr@XV?$function@$$A6APEAXPEAX@Z@tr1@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::tr1::function<void * (void *)>>::~unique_ptr<void,std::tr1::function<void * (void *)>>(void)
0x180020d60  nop
0x180020d61  mov     rcx, [rbp+4Fh+var_20]
0x180020d65  xor     rcx, rsp; StackCookie
0x180020d68  call    __security_check_cookie
0x180020d6d  lea     r11, [rsp+0C0h+var_10]
0x180020d75  mov     rbx, [r11+28h]
0x180020d79  mov     rsi, [r11+30h]
0x180020d7d  mov     rsp, r11
0x180020d80  pop     r14
0x180020d82  pop     rdi
0x180020d83  pop     rbp
0x180020d84  retn
```
