# RecursiveRemoveDirectoryEx

- ea: `0x1400150ac`
- end: `0x140015100`
- name: `RecursiveRemoveDirectoryEx`
- size: `84`
- prototype: `__int64 __fastcall(BOOL, wchar_t *, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140007228`
- `0x140015108`

## callees

- `0x140002310`
- `0x14001344c`

## pseudocode

```c
__int64 __fastcall RecursiveRemoveDirectoryEx(BOOL a1, wchar_t *a2, __int64 a3, __int64 a4)
{
  _QWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  char v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+34h] [rbp-24h]
  __int64 v8; // [rsp+38h] [rbp-20h]
  char v9; // [rsp+40h] [rbp-18h]

  v5[0] = 0;
  v5[1] = 0;
  v6 = 1;
  v7 = 0;
  v8 = a4;
  v9 = 0;
  return CRecursiveRemoveDirectory::RemoveDirectoryW((CRecursiveRemoveDirectory *)v5, a1, a2, 0);
}

```

## disassembly

```asm
0x1400150ac  mov     r11, rsp
0x1400150af  sub     rsp, 58h
0x1400150b3  mov     rax, cs:__security_cookie
0x1400150ba  xor     rax, rsp
0x1400150bd  mov     [rsp+58h+var_10], rax
0x1400150c2  xor     eax, eax
0x1400150c4  mov     r8, rdx; wchar_t *
0x1400150c7  mov     [r11-38h], rax
0x1400150cb  mov     edx, ecx; unsigned int
0x1400150cd  mov     [r11-30h], rax
0x1400150d1  lea     rcx, [r11-38h]; this
0x1400150d5  mov     [rsp+58h+var_28], 1
0x1400150da  mov     [rsp+58h+var_24], eax
0x1400150de  mov     [r11-20h], r9
0x1400150e2  xor     r9d, r9d; wchar_t *
0x1400150e5  mov     [rsp+58h+var_18], al
0x1400150e9  call    ?RemoveDirectoryW@CRecursiveRemoveDirectory@@QEAAJKQEB_W0@Z; CRecursiveRemoveDirectory::RemoveDirectoryW(ulong,wchar_t const * const,wchar_t const * const)
0x1400150ee  mov     rcx, [rsp+58h+var_10]
0x1400150f3  xor     rcx, rsp; StackCookie
0x1400150f6  call    __security_check_cookie
0x1400150fb  add     rsp, 58h
0x1400150ff  retn
```
