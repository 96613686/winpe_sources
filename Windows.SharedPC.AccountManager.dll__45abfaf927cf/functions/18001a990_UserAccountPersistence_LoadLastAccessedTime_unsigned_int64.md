# UserAccountPersistence::LoadLastAccessedTime(unsigned __int64 *)

- ea: `0x18001a990`
- end: `0x18001aa03`
- name: `?LoadLastAccessedTime@UserAccountPersistence@@UEAAJPEA_K@Z`
- size: `115`
- prototype: `__int64 __fastcall(UserAccountPersistence *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001a990`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a9dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a9dd`

## string_xrefs

- `0x18001a9a7`: `LastAccessTime`

## pseudocode

```c
LSTATUS __fastcall UserAccountPersistence::LoadLastAccessedTime(UserAccountPersistence *this, unsigned __int64 *a2)
{
  HKEY v2; // rcx
  LSTATUS result; // eax
  DWORD v5; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v6; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v2 = (HKEY)*((_QWORD *)this + 6);
  v6 = 0;
  v5 = 8;
  result = RegGetValueW(v2, 0, L"LastAccessTime", 0x40u, 0, &v6, &v5);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    *a2 = v6;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a990  mov     r11, rsp
0x18001a993  push    rbx
0x18001a994  sub     rsp, 40h
0x18001a998  lea     rax, [r11+8]
0x18001a99c  mov     qword ptr [rdx], 0
0x18001a9a3  mov     rcx, [rcx+30h]; hkey
0x18001a9a7  lea     r8, Value; "LastAccessTime"
0x18001a9ae  mov     [r11-18h], rax
0x18001a9b2  mov     rbx, rdx
0x18001a9b5  lea     rax, [r11+10h]
0x18001a9b9  mov     qword ptr [r11+10h], 0
0x18001a9c1  mov     [r11-20h], rax
0x18001a9c5  mov     r9d, 40h ; '@'; dwFlags
0x18001a9cb  xor     edx, edx; lpSubKey
0x18001a9cd  mov     qword ptr [r11-28h], 0
0x18001a9d5  mov     [rsp+48h+arg_0], 8
0x18001a9dd  call    cs:__imp_RegGetValueW
0x18001a9e3  test    eax, eax
0x18001a9e5  jz      short loc_18001A9F3
0x18001a9e7  jle     short loc_18001A9FD
0x18001a9e9  movzx   eax, ax
0x18001a9ec  or      eax, 80070000h
0x18001a9f1  jmp     short loc_18001A9FD
0x18001a9f3  mov     rax, [rsp+48h+arg_8]
0x18001a9f8  mov     [rbx], rax
0x18001a9fb  xor     eax, eax
0x18001a9fd  add     rsp, 40h
0x18001aa01  pop     rbx
0x18001aa02  retn
```
