# UpdatePlayready

- ea: `0x18000c310`
- end: `0x18000c43f`
- name: `UpdatePlayready`
- size: `303`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001d090`

## callees

- `0x1800022b0`
- `0x18000c310`
- `0x18000c448`
- `0x18000c5d8`
- `0x18002dd60`
- `0x18002de14`
- `0x18002dfac`
- `0x18002e078`
- `0x18002e1fc`

## string_xrefs

- `0x18000c37e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Media Center\Service\Content Security\Shared`
- `0x18000c3ff`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Media Center\Service\Content Security\Shared`
- `0x18000c372`: `PlayReadyInstalled`

## pseudocode

```c
__int64 UpdatePlayready()
{
  __int64 v0; // rcx
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 v3; // rcx
  int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  BYTE v8[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v9[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v10[88]; // [rsp+60h] [rbp-A0h] BYREF
  int v11; // [rsp+B8h] [rbp-48h]

  sub_18002DD60(v10);
  if ( !v11 )
  {
    *(_DWORD *)v9 = 0;
    *(_DWORD *)v8 = 4;
    if ( (unsigned int)sub_18000C448(
                         v0,
                         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Media Center\\Service\\Content Security\\Shared",
                         v1,
                         v2,
                         L"PlayReadyInstalled",
                         4,
                         v9,
                         (LPDWORD)v8)
      || !*(_DWORD *)v9 )
    {
      v4 = 1;
      goto LABEL_9;
    }
    v11 = 1;
  }
  v4 = sub_18002E078(v10);
  if ( v4 >= 0 )
  {
    v4 = sub_18002DFAC(v10);
    if ( v4 >= 0 )
    {
      v4 = -2147467263;
      sub_18002E1FC();
    }
  }
  *(_DWORD *)v8 = v4;
  sub_18000C5D8(
    v3,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Media Center\\Service\\Content Security\\Shared",
    v5,
    v6,
    L"CrlLastReturnCode",
    4u,
    v8,
    4u,
    0);
LABEL_9:
  sub_18002DE14(v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c310  mov     [rsp-8+arg_0], rbx
0x18000c315  push    rbp
0x18000c316  lea     rbp, [rsp-260h]
0x18000c31e  sub     rsp, 360h
0x18000c325  mov     rax, cs:__security_cookie
0x18000c32c  xor     rax, rsp
0x18000c32f  mov     [rbp+260h+var_10], rax
0x18000c336  lea     rcx, [rsp+360h+var_300]
0x18000c33b  call    sub_18002DD60
0x18000c340  cmp     [rbp+260h+var_2A8], 0
0x18000c344  jnz     short loc_18000C3A2
0x18000c346  mov     dword ptr [rsp+360h+var_308], 0
0x18000c34e  mov     dword ptr [rsp+360h+var_310], 4
0x18000c356  lea     rax, [rsp+360h+var_310]
0x18000c35b  mov     qword ptr [rsp+360h+var_328], rax
0x18000c360  lea     rax, [rsp+360h+var_308]
0x18000c365  mov     [rsp+360h+var_330], rax
0x18000c36a  mov     [rsp+360h+dwType], 4
0x18000c372  lea     rax, aPlayreadyinsta; "PlayReadyInstalled"
0x18000c379  mov     [rsp+360h+lpValueName], rax
0x18000c37e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000c385  call    sub_18000C448
0x18000c38a  test    eax, eax
0x18000c38c  jnz     loc_18000C438
0x18000c392  cmp     dword ptr [rsp+360h+var_308], eax
0x18000c396  jz      loc_18000C438
0x18000c39c  lea     ebx, [rax+1]
0x18000c39f  mov     [rbp+260h+var_2A8], ebx
0x18000c3a2  lea     rcx, [rsp+360h+var_300]
0x18000c3a7  call    sub_18002E078
0x18000c3ac  mov     ebx, eax
0x18000c3ae  test    eax, eax
0x18000c3b0  js      short loc_18000C3CD
0x18000c3b2  lea     rcx, [rsp+360h+var_300]
0x18000c3b7  call    sub_18002DFAC
0x18000c3bc  mov     ebx, eax
0x18000c3be  test    eax, eax
0x18000c3c0  js      short loc_18000C3CD
0x18000c3c2  mov     ebx, 80004001h
0x18000c3c7  call    sub_18002E1FC
0x18000c3cc  nop
0x18000c3cd  mov     dword ptr [rsp+360h+var_310], ebx
0x18000c3d1  mov     [rsp+360h+var_320], 0; int
0x18000c3d9  mov     [rsp+360h+var_328], 4; DWORD
0x18000c3e1  lea     rax, [rsp+360h+var_310]
0x18000c3e6  mov     [rsp+360h+var_330], rax; BYTE *
0x18000c3eb  mov     [rsp+360h+dwType], 4; dwType
0x18000c3f3  lea     rax, aCrllastreturnc; "CrlLastReturnCode"
0x18000c3fa  mov     [rsp+360h+lpValueName], rax; lpValueName
0x18000c3ff  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000c406  call    sub_18000C5D8
0x18000c40b  lea     rcx, [rsp+360h+var_300]
0x18000c410  call    sub_18002DE14
0x18000c415  mov     eax, ebx
0x18000c417  mov     rcx, [rbp+260h+var_10]
0x18000c41e  xor     rcx, rsp; StackCookie
0x18000c421  call    __security_check_cookie
0x18000c426  mov     rbx, [rsp+360h+arg_0]
0x18000c42e  add     rsp, 360h
0x18000c435  pop     rbp
0x18000c436  retn
0x18000c438  mov     ebx, 1
0x18000c43d  jmp     short loc_18000C40B
```
