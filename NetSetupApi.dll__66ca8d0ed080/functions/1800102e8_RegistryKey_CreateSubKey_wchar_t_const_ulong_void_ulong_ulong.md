# RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)

- ea: `0x1800102e8`
- end: `0x180010443`
- name: `?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z`
- size: `347`
- prototype: `RegistryKey *__fastcall(HKEY *, RegistryKey *, __int64, REGSAM, HANDLE)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006208`

## callees

- `0x180005328`
- `0x1800065d4`
- `0x18000895c`
- `0x18000fbfc`
- `0x1800102e8`
- `0x180010a9c`
- `0x180010b40`
- `0x1800119f0`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::CreateSubKey(HKEY *a1, RegistryKey *a2, __int64 a3, REGSAM a4, HANDLE a5)
{
  HKEY v6; // rcx
  signed int v7; // edi
  LSTATUS v8; // edi
  int v10; // [rsp+20h] [rbp-118h]
  int v11; // [rsp+30h] [rbp-108h]
  _BYTE pExceptionObject[208]; // [rsp+48h] [rbp-F0h] BYREF
  HKEY v13; // [rsp+118h] [rbp-20h] BYREF

  v13 = (HKEY)a2;
  v6 = *a1;
  v13 = 0;
  if ( a5 )
  {
    v7 = RegCreateKeyTransacted_Wrapper(v6, v10, &v13, v11, a5);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (unsigned int)&word_18001F4EC,
          v7);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v7);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  else
  {
    v8 = RegCreateKeyEx_Wrapper(v6, (__int64)a2, a3, a4, v10, &v13);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (unsigned int)&word_18001F4EC,
          v8);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v8);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  RegistryKey::RegistryKey(a2, v13);
  return a2;
}

```

## disassembly

```asm
0x1800102e8  mov     r11, rsp
0x1800102eb  mov     [r11+18h], rbx
0x1800102ef  push    rdi
0x1800102f0  sub     rsp, 130h
0x1800102f7  mov     rax, cs:__security_cookie
0x1800102fe  xor     rax, rsp
0x180010301  mov     [rsp+138h+var_18], rax
0x180010309  mov     rax, [rsp+138h+arg_20]
0x180010311  mov     rbx, rdx
0x180010314  mov     [rsp+138h+var_20], rdx
0x18001031c  mov     rcx, [rcx]; hKey
0x18001031f  mov     qword ptr [r11-20h], 0
0x180010327  test    rax, rax
0x18001032a  jz      short loc_1800103A0
0x18001032c  mov     [rsp+138h+var_100], rax; HANDLE
0x180010331  lea     rax, [r11-20h]
0x180010335  mov     [rsp+138h+var_110], rax; PHKEY
0x18001033a  call    RegCreateKeyTransacted_Wrapper
0x18001033f  mov     edi, eax
0x180010341  test    eax, eax
0x180010343  jz      loc_18001040F
0x180010349  mov     rcx, cs:WPP_GLOBAL_Control
0x180010350  lea     rax, WPP_GLOBAL_Control
0x180010357  cmp     rcx, rax
0x18001035a  jz      short loc_180010382
0x18001035c  cmp     byte ptr [rcx+19h], 2
0x180010360  jb      short loc_180010382
0x180010362  mov     rcx, [rcx+10h]
0x180010366  lea     r9, word_18001F4EC
0x18001036d  mov     edx, 0Fh
0x180010372  mov     [rsp+138h+var_118], edi
0x180010376  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x18001037d  call    WPP_SF_SD
0x180010382  mov     edx, edi; int
0x180010384  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180010389  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18001038e  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180010395  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18001039a  call    _CxxThrowException_0
0x1800103a0  lea     rax, [rsp+138h+var_20]
0x1800103a8  mov     [rsp+138h+var_110], rax; PHKEY
0x1800103ad  call    RegCreateKeyEx_Wrapper
0x1800103b2  mov     edi, eax
0x1800103b4  test    eax, eax
0x1800103b6  jz      short loc_18001040F
0x1800103b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103bf  lea     rax, WPP_GLOBAL_Control
0x1800103c6  cmp     rcx, rax
0x1800103c9  jz      short loc_1800103F1
0x1800103cb  cmp     byte ptr [rcx+19h], 2
0x1800103cf  jb      short loc_1800103F1
0x1800103d1  mov     rcx, [rcx+10h]
0x1800103d5  lea     r9, word_18001F4EC
0x1800103dc  mov     edx, 10h
0x1800103e1  mov     [rsp+138h+var_118], edi
0x1800103e5  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x1800103ec  call    WPP_SF_SD
0x1800103f1  mov     edx, edi; int
0x1800103f3  lea     rcx, [rsp+138h+pExceptionObject]; this
0x1800103f8  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800103fd  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180010404  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180010409  call    _CxxThrowException_0
0x18001040f  mov     rdx, [rsp+138h+var_20]; HKEY
0x180010417  mov     rcx, rbx; this
0x18001041a  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18001041f  mov     rax, rbx
0x180010422  mov     rcx, [rsp+138h+var_18]
0x18001042a  xor     rcx, rsp; StackCookie
0x18001042d  call    __security_check_cookie
0x180010432  mov     rbx, [rsp+138h+arg_10]
0x18001043a  add     rsp, 130h
0x180010441  pop     rdi
0x180010442  retn
```
