# CFaxAccount::Delete(ushort const *)

- ea: `0x14000cac8`
- end: `0x14000cc2f`
- name: `?Delete@CFaxAccount@@QEAAKPEBG@Z`
- size: `359`
- prototype: `__int64 __fastcall(CFaxAccount *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x14000cc38`

## callees

- `0x140004b30`
- `0x140004df0`
- `0x14000cac8`
- `0x140070020`
- `0x1400708c4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000cbc6`
- `ADVAPI32!RegCloseKey` at `0x14000cbc6`
- `ADVAPI32!RegDeleteValueW` at `0x14000cb81`
- `ADVAPI32!RegDeleteValueW` at `0x14000cb81`
- `KERNEL32!GetLastError` at `0x14000cb4e`
- `KERNEL32!GetLastError` at `0x14000cbe1`
- `KERNEL32!GetLastError` at `0x14000cb4e`
- `KERNEL32!GetLastError` at `0x14000cbe1`

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
  v3 = (HKEY)OpenRegistryKey(-2147483646, a2, 0, 2);
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
  if ( !(unsigned int)DeleteRegistryKey(-2147483646, a2) )
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
0x14000cac8  mov     [rsp+arg_0], rbx
0x14000cacd  mov     [rsp+arg_8], rbp
0x14000cad2  push    rdi
0x14000cad3  sub     rsp, 30h
0x14000cad7  mov     rdi, rdx
0x14000cada  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cae1  lea     rbp, WPP_GLOBAL_Control
0x14000cae8  cmp     rcx, rbp
0x14000caeb  jz      short loc_14000CB0E
0x14000caed  test    byte ptr [rcx+1Ch], 4
0x14000caf1  jz      short loc_14000CB0E
0x14000caf3  cmp     byte ptr [rcx+19h], 5
0x14000caf7  jb      short loc_14000CB0E
0x14000caf9  mov     rcx, [rcx+10h]
0x14000cafd  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000cb04  mov     edx, 20h ; ' '
0x14000cb09  call    WPP_SF_
0x14000cb0e  mov     r9d, 2
0x14000cb14  xor     r8d, r8d
0x14000cb17  mov     rdx, rdi
0x14000cb1a  mov     rcx, 0FFFFFFFF80000002h
0x14000cb21  call    OpenRegistryKey
0x14000cb26  mov     rbx, rax
0x14000cb29  test    rax, rax
0x14000cb2c  jnz     short loc_14000CB77
0x14000cb2e  mov     rax, cs:WPP_GLOBAL_Control
0x14000cb35  cmp     rax, rbp
0x14000cb38  jz      loc_14000CBCC
0x14000cb3e  test    byte ptr [rax+1Ch], 4
0x14000cb42  jz      loc_14000CBCC
0x14000cb48  cmp     byte ptr [rax+19h], 3
0x14000cb4c  jb      short loc_14000CBCC
0x14000cb4e  call    cs:__imp_GetLastError
0x14000cb54  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb5b  lea     edx, [rbx+21h]
0x14000cb5e  mov     r9, rdi
0x14000cb61  mov     [rsp+38h+var_18], eax
0x14000cb65  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000cb6c  mov     rcx, [rcx+10h]
0x14000cb70  call    WPP_SF_Sd
0x14000cb75  jmp     short loc_14000CBCC
0x14000cb77  lea     rdx, ValueName; "NTUserName"
0x14000cb7e  mov     rcx, rbx; hKey
0x14000cb81  call    cs:__imp_RegDeleteValueW
0x14000cb87  test    eax, eax
0x14000cb89  jz      short loc_14000CBC3
0x14000cb8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb92  cmp     rcx, rbp
0x14000cb95  jz      short loc_14000CBC3
0x14000cb97  test    byte ptr [rcx+1Ch], 4
0x14000cb9b  jz      short loc_14000CBC3
0x14000cb9d  cmp     byte ptr [rcx+19h], 3
0x14000cba1  jb      short loc_14000CBC3
0x14000cba3  mov     rcx, [rcx+10h]
0x14000cba7  lea     r9, ValueName; "NTUserName"
0x14000cbae  mov     edx, 22h ; '"'
0x14000cbb3  mov     [rsp+38h+var_18], eax
0x14000cbb7  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000cbbe  call    WPP_SF_Sd
0x14000cbc3  mov     rcx, rbx; hKey
0x14000cbc6  call    cs:__imp_RegCloseKey
0x14000cbcc  mov     rdx, rdi
0x14000cbcf  mov     rcx, 0FFFFFFFF80000002h
0x14000cbd6  xor     ebx, ebx
0x14000cbd8  call    DeleteRegistryKey
0x14000cbdd  test    eax, eax
0x14000cbdf  jnz     short loc_14000CC1D
0x14000cbe1  call    cs:__imp_GetLastError
0x14000cbe7  mov     ebx, eax
0x14000cbe9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbf0  cmp     rcx, rbp
0x14000cbf3  jz      short loc_14000CC1D
0x14000cbf5  test    byte ptr [rcx+1Ch], 4
0x14000cbf9  jz      short loc_14000CC1D
0x14000cbfb  cmp     byte ptr [rcx+19h], 2
0x14000cbff  jb      short loc_14000CC1D
0x14000cc01  mov     rcx, [rcx+10h]
0x14000cc05  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000cc0c  mov     edx, 23h ; '#'
0x14000cc11  mov     [rsp+38h+var_18], eax
0x14000cc15  mov     r9, rdi
0x14000cc18  call    WPP_SF_Sd
0x14000cc1d  mov     rbp, [rsp+38h+arg_8]
0x14000cc22  mov     eax, ebx
0x14000cc24  mov     rbx, [rsp+38h+arg_0]
0x14000cc29  add     rsp, 30h
0x14000cc2d  pop     rdi
0x14000cc2e  retn
```
