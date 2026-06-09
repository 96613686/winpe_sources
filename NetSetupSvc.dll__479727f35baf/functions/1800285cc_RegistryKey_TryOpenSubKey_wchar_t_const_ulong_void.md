# RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)

- ea: `0x1800285cc`
- end: `0x1800286d0`
- name: `?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009cfc`
- `0x18000a4d0`
- `0x18000a570`
- `0x18000b2c0`
- `0x18000b4b4`
- `0x18000c5e0`
- `0x18001aad4`
- `0x18001ac78`
- `0x18001eb14`
- `0x18001f2e4`
- `0x1800207bc`
- `0x180021350`
- `0x180021650`
- `0x180023718`
- `0x180026cb8`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008c78`
- `0x18002498c`
- `0x180026958`
- `0x1800281b4`
- `0x180028208`
- `0x1800285cc`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::TryOpenSubKey(HKEY *a1, RegistryKey *a2, const WCHAR *a3, REGSAM a4, HANDLE a5)
{
  int v6; // esi
  HKEY v7; // rcx
  LSTATUS v8; // eax
  signed int v9; // edi
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-100h] BYREF
  HKEY v12; // [rsp+108h] [rbp-30h] BYREF

  v12 = (HKEY)a2;
  v6 = (int)a3;
  v7 = *a1;
  v12 = 0;
  if ( a5 )
    v8 = RegOpenKeyTransacted_Wrapper(v7, a3, (__int64)a3, a4, &v12, a5);
  else
    v8 = RegOpenKeyEx_Wrapper(v7, a3, (__int64)a3, a4, &v12);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
          v6,
          v8);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v9);
      throw (Win32Exception *)pExceptionObject;
    }
    *(_QWORD *)a2 = 0;
  }
  else
  {
    RegistryKey::RegistryKey(a2, v12);
  }
  return a2;
}

```

## disassembly

```asm
0x1800285cc  mov     r11, rsp
0x1800285cf  push    rbx
0x1800285d0  push    rsi
0x1800285d1  push    rdi
0x1800285d2  sub     rsp, 120h
0x1800285d9  mov     rax, cs:__security_cookie
0x1800285e0  xor     rax, rsp
0x1800285e3  mov     [rsp+138h+var_28], rax
0x1800285eb  mov     rax, [rsp+138h+arg_20]
0x1800285f3  mov     rbx, rdx
0x1800285f6  mov     [rsp+138h+var_30], rdx
0x1800285fe  mov     rsi, r8
0x180028601  mov     rcx, [rcx]; hKey
0x180028604  mov     rdx, r8; lpSubKey
0x180028607  mov     qword ptr [r11-30h], 0
0x18002860f  test    rax, rax
0x180028612  jz      short loc_180028629
0x180028614  mov     [rsp+138h+var_110], rax; HANDLE
0x180028619  lea     rax, [r11-30h]
0x18002861d  mov     [rsp+138h+var_118], rax; PHKEY
0x180028622  call    RegOpenKeyTransacted_Wrapper
0x180028627  jmp     short loc_18002863B
0x180028629  lea     rax, [rsp+138h+var_30]
0x180028631  mov     [rsp+138h+var_118], rax; PHKEY
0x180028636  call    RegOpenKeyEx_Wrapper
0x18002863b  mov     edi, eax
0x18002863d  test    eax, eax
0x18002863f  jz      short loc_1800286A2
0x180028641  cmp     eax, 2
0x180028644  jz      short loc_180028699
0x180028646  mov     rcx, cs:WPP_GLOBAL_Control
0x18002864d  lea     rax, WPP_GLOBAL_Control
0x180028654  cmp     rcx, rax
0x180028657  jz      short loc_18002867B
0x180028659  cmp     byte ptr [rcx+19h], 2
0x18002865d  jb      short loc_18002867B
0x18002865f  mov     rcx, [rcx+10h]
0x180028663  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x18002866a  mov     edx, 0Ch
0x18002866f  mov     dword ptr [rsp+138h+var_118], edi
0x180028673  mov     r9, rsi
0x180028676  call    WPP_SF_Sd
0x18002867b  mov     edx, edi; int
0x18002867d  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180028682  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180028687  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18002868e  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180028693  call    _CxxThrowException_0
0x180028699  mov     qword ptr [rbx], 0
0x1800286a0  jmp     short loc_1800286B2
0x1800286a2  mov     rdx, [rsp+138h+var_30]; HKEY
0x1800286aa  mov     rcx, rbx; this
0x1800286ad  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x1800286b2  mov     rax, rbx
0x1800286b5  mov     rcx, [rsp+138h+var_28]
0x1800286bd  xor     rcx, rsp; StackCookie
0x1800286c0  call    __security_check_cookie
0x1800286c5  add     rsp, 120h
0x1800286cc  pop     rdi
0x1800286cd  pop     rsi
0x1800286ce  pop     rbx
0x1800286cf  retn
```
