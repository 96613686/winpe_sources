# CFaxAccount::Delete(ushort const *)

- ea: `0x14000d178`
- end: `0x14000d2fc`
- name: `?Delete@CFaxAccount@@QEAAKPEBG@Z`
- size: `388`
- prototype: `unsigned int __fastcall(CFaxAccount *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x14000d304`

## callees

- `0x140004c78`
- `0x140004f64`
- `0x14000d178`
- `0x1400745e4`
- `0x140074f18`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000d286`
- `ADVAPI32!RegCloseKey` at `0x14000d286`
- `ADVAPI32!RegDeleteValueW` at `0x14000d23b`
- `ADVAPI32!RegDeleteValueW` at `0x14000d23b`
- `KERNEL32!GetLastError` at `0x14000d202`
- `KERNEL32!GetLastError` at `0x14000d2a7`
- `KERNEL32!GetLastError` at `0x14000d202`
- `KERNEL32!GetLastError` at `0x14000d2a7`

## pseudocode

```c
__int64 __fastcall CFaxAccount::Delete(CFaxAccount *this, const unsigned __int16 *a2)
{
  HKEY v3; // rax
  HKEY v4; // rbx
  char LastError; // al
  LSTATUS v6; // eax
  DWORD v7; // ebx
  DWORD v8; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  }
  v3 = OpenRegistryKey(HKEY_LOCAL_MACHINE, a2, 0, 2u);
  v4 = v3;
  if ( v3 )
  {
    v6 = RegDeleteValueW(v3, L"NTUserName");
    if ( v6
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
        (unsigned int)L"NTUserName",
        v6);
    }
    RegCloseKey(v4);
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    LastError = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
      (_DWORD)a2,
      LastError);
  }
  v7 = 0;
  if ( !(unsigned int)DeleteRegistryKey(HKEY_LOCAL_MACHINE, a2) )
  {
    v8 = GetLastError();
    v7 = v8;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
        (_DWORD)a2,
        v8);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000d178  mov     [rsp+arg_0], rbx
0x14000d17d  mov     [rsp+arg_8], rbp
0x14000d182  push    rdi
0x14000d183  sub     rsp, 30h
0x14000d187  mov     rdi, rdx
0x14000d18a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d191  lea     rbp, WPP_GLOBAL_Control
0x14000d198  cmp     rcx, rbp
0x14000d19b  jz      short loc_14000D1BE
0x14000d19d  test    byte ptr [rcx+1Ch], 4
0x14000d1a1  jz      short loc_14000D1BE
0x14000d1a3  cmp     byte ptr [rcx+19h], 5
0x14000d1a7  jb      short loc_14000D1BE
0x14000d1a9  mov     rcx, [rcx+10h]
0x14000d1ad  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d1b4  mov     edx, 20h ; ' '
0x14000d1b9  call    WPP_SF_
0x14000d1be  mov     r9d, 2
0x14000d1c4  xor     r8d, r8d
0x14000d1c7  mov     rdx, rdi
0x14000d1ca  mov     rcx, 0FFFFFFFF80000002h
0x14000d1d1  call    OpenRegistryKey
0x14000d1d6  mov     rbx, rax
0x14000d1d9  test    rax, rax
0x14000d1dc  jnz     short loc_14000D231
0x14000d1de  mov     rax, cs:WPP_GLOBAL_Control
0x14000d1e5  cmp     rax, rbp
0x14000d1e8  jz      loc_14000D292
0x14000d1ee  test    byte ptr [rax+1Ch], 4
0x14000d1f2  jz      loc_14000D292
0x14000d1f8  cmp     byte ptr [rax+19h], 3
0x14000d1fc  jb      loc_14000D292
0x14000d202  call    cs:__imp_GetLastError
0x14000d209  nop     dword ptr [rax+rax+00h]
0x14000d20e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d215  lea     edx, [rbx+21h]
0x14000d218  mov     r9, rdi
0x14000d21b  mov     [rsp+38h+var_18], eax
0x14000d21f  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d226  mov     rcx, [rcx+10h]
0x14000d22a  call    WPP_SF_Sd
0x14000d22f  jmp     short loc_14000D292
0x14000d231  lea     rdx, ValueName; "NTUserName"
0x14000d238  mov     rcx, rbx; hKey
0x14000d23b  call    cs:__imp_RegDeleteValueW
0x14000d242  nop     dword ptr [rax+rax+00h]
0x14000d247  test    eax, eax
0x14000d249  jz      short loc_14000D283
0x14000d24b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d252  cmp     rcx, rbp
0x14000d255  jz      short loc_14000D283
0x14000d257  test    byte ptr [rcx+1Ch], 4
0x14000d25b  jz      short loc_14000D283
0x14000d25d  cmp     byte ptr [rcx+19h], 3
0x14000d261  jb      short loc_14000D283
0x14000d263  mov     rcx, [rcx+10h]
0x14000d267  lea     r9, ValueName; "NTUserName"
0x14000d26e  mov     edx, 22h ; '"'
0x14000d273  mov     [rsp+38h+var_18], eax
0x14000d277  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d27e  call    WPP_SF_Sd
0x14000d283  mov     rcx, rbx; hKey
0x14000d286  call    cs:__imp_RegCloseKey
0x14000d28d  nop     dword ptr [rax+rax+00h]
0x14000d292  mov     rdx, rdi
0x14000d295  mov     rcx, 0FFFFFFFF80000002h
0x14000d29c  xor     ebx, ebx
0x14000d29e  call    DeleteRegistryKey
0x14000d2a3  test    eax, eax
0x14000d2a5  jnz     short loc_14000D2E9
0x14000d2a7  call    cs:__imp_GetLastError
0x14000d2ae  nop     dword ptr [rax+rax+00h]
0x14000d2b3  mov     ebx, eax
0x14000d2b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d2bc  cmp     rcx, rbp
0x14000d2bf  jz      short loc_14000D2E9
0x14000d2c1  test    byte ptr [rcx+1Ch], 4
0x14000d2c5  jz      short loc_14000D2E9
0x14000d2c7  cmp     byte ptr [rcx+19h], 2
0x14000d2cb  jb      short loc_14000D2E9
0x14000d2cd  mov     rcx, [rcx+10h]
0x14000d2d1  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d2d8  mov     edx, 23h ; '#'
0x14000d2dd  mov     [rsp+38h+var_18], eax
0x14000d2e1  mov     r9, rdi
0x14000d2e4  call    WPP_SF_Sd
0x14000d2e9  mov     rbp, [rsp+38h+arg_8]
0x14000d2ee  mov     eax, ebx
0x14000d2f0  mov     rbx, [rsp+38h+arg_0]
0x14000d2f5  add     rsp, 30h
0x14000d2f9  pop     rdi
0x14000d2fa  retn
```
