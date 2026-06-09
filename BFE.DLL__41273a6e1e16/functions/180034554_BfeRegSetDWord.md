# BfeRegSetDWord

- ea: `0x180034554`
- end: `0x180034620`
- name: `BfeRegSetDWord`
- size: `204`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004e3d8`
- `0x180067b74`
- `0x180067cd0`
- `0x1800699e8`
- `0x18006ab60`
- `0x18006afa0`

## callees

- `0x180004070`
- `0x180012d8c`
- `0x1800197d0`
- `0x180034554`
- `0x18003512c`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800345c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800345c9`

## string_xrefs

- `0x1800345dc`: `RegSetValueExW`
- `0x1800345f8`: `BfeRegSetDWord`

## pseudocode

```c
__int64 __fastcall BfeRegSetDWord(__int64 a1, const WCHAR *a2, const WCHAR *a3, int a4)
{
  __int64 v4; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  int Data; // [rsp+38h] [rbp-30h] BYREF

  v4 = 0;
  Data = a4;
  v12 = 0;
  v6 = -2147483646;
  if ( a2 )
  {
    v7 = BfeRegCreateKey(HKEY_LOCAL_MACHINE, a2, 2u, 0, &v12);
    v4 = v12;
    v8 = v7;
    if ( v7 )
      goto LABEL_7;
    v6 = v12;
  }
  else
  {
    v8 = 0;
  }
  v9 = RegSetValueExW((HKEY)v6, a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v9 )
    v8 = WfpReportSysErrorAsWinError(v10, "RegSetValueExW", v9);
LABEL_7:
  BfeRegCloseKey(v4);
  if ( v8 )
    WfpReportError(v8, "BfeRegSetDWord");
  return v8;
}

```

## disassembly

```asm
0x180034554  mov     r11, rsp
0x180034557  push    rbx
0x180034558  push    rsi
0x180034559  push    rdi
0x18003455a  sub     rsp, 50h
0x18003455e  mov     rax, cs:__security_cookie
0x180034565  xor     rax, rsp
0x180034568  mov     [rsp+68h+var_28], rax
0x18003456d  xor     edi, edi
0x18003456f  mov     [r11-30h], r9d
0x180034573  mov     [r11-38h], rdi
0x180034577  mov     rsi, r8
0x18003457a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034581  test    rdx, rdx
0x180034584  jz      short loc_1800345AC
0x180034586  lea     rax, [r11-38h]
0x18003458a  xor     r9d, r9d
0x18003458d  lea     r8d, [rdi+2]
0x180034591  mov     [r11-48h], rax
0x180034595  call    BfeRegCreateKey
0x18003459a  mov     rdi, [rsp+68h+var_38]
0x18003459f  mov     rbx, rax
0x1800345a2  test    rax, rax
0x1800345a5  jnz     short loc_1800345EB
0x1800345a7  mov     rcx, rdi
0x1800345aa  jmp     short loc_1800345AE
0x1800345ac  xor     ebx, ebx
0x1800345ae  mov     r9d, 4; dwType
0x1800345b4  lea     rax, [rsp+68h+Data]
0x1800345b9  mov     [rsp+68h+cbData], r9d; cbData
0x1800345be  xor     r8d, r8d; Reserved
0x1800345c1  mov     rdx, rsi; lpValueName
0x1800345c4  mov     [rsp+68h+lpData], rax; lpData
0x1800345c9  call    cs:__imp_RegSetValueExW
0x1800345d0  nop     dword ptr [rax+rax+00h]
0x1800345d5  test    eax, eax
0x1800345d7  jz      short loc_1800345EB
0x1800345d9  mov     r8d, eax
0x1800345dc  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x1800345e3  call    WfpReportSysErrorAsWinError
0x1800345e8  mov     rbx, rax
0x1800345eb  mov     rcx, rdi
0x1800345ee  call    BfeRegCloseKey
0x1800345f3  test    rbx, rbx
0x1800345f6  jz      short loc_180034607
0x1800345f8  lea     rdx, aBferegsetdword; "BfeRegSetDWord"
0x1800345ff  mov     rcx, rbx
0x180034602  call    WfpReportError
0x180034607  mov     rax, rbx
0x18003460a  mov     rcx, [rsp+68h+var_28]
0x18003460f  xor     rcx, rsp; StackCookie
0x180034612  call    __security_check_cookie
0x180034617  add     rsp, 50h
0x18003461b  pop     rdi
0x18003461c  pop     rsi
0x18003461d  pop     rbx
0x18003461e  retn
```
