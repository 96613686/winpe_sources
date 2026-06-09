# RegistryKey::SetValue(wchar_t const *,wchar_t const *)

- ea: `0x18007fc44`
- end: `0x18007fceb`
- name: `?SetValue@RegistryKey@@QEBAXPEB_W0@Z`
- size: `167`
- prototype: `void(RegistryKey *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180028db4`
- `0x180056030`
- `0x18005bb18`
- `0x18005e3d8`

## callees

- `0x180052698`
- `0x180065035`
- `0x18007fc44`
- `0x18007fd8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007fc82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007fc82`

## pseudocode

```c
void __fastcall RegistryKey::SetValue(HKEY *this, const wchar_t *a2, const BYTE *lpData)
{
  __int64 v3; // rax
  int v5; // esi
  LSTATUS v6; // ebx
  int v7; // r8d
  _BYTE pExceptionObject[248]; // [rsp+30h] [rbp-F8h] BYREF

  v3 = -1;
  v5 = (int)a2;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  v6 = RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * v3 + 2);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v7, v5, (__int64)lpData, v6);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
    throw (Win32Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18007fc44  push    rbx
0x18007fc46  push    rbp
0x18007fc47  push    rsi
0x18007fc48  push    rdi
0x18007fc49  sub     rsp, 108h
0x18007fc50  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007fc54  mov     rdi, r8
0x18007fc57  xor     ebp, ebp
0x18007fc59  mov     rsi, rdx
0x18007fc5c  inc     rax
0x18007fc5f  cmp     [r8+rax*2], bp
0x18007fc64  jnz     short loc_18007FC5C
0x18007fc66  mov     rcx, [rcx]; hKey
0x18007fc69  lea     eax, ds:2[rax*2]
0x18007fc70  mov     [rsp+128h+cbData], eax; cbData
0x18007fc74  mov     r9d, 1; dwType
0x18007fc7a  xor     r8d, r8d; Reserved
0x18007fc7d  mov     [rsp+128h+lpData], rdi; lpData
0x18007fc82  call    cs:__imp_RegSetValueExW
0x18007fc88  mov     ebx, eax
0x18007fc8a  test    eax, eax
0x18007fc8c  jz      short loc_18007FCDF
0x18007fc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fc95  lea     rax, WPP_GLOBAL_Control
0x18007fc9c  cmp     rcx, rax
0x18007fc9f  jz      short loc_18007FCC1
0x18007fca1  cmp     byte ptr [rcx+19h], 2
0x18007fca5  jb      short loc_18007FCC1
0x18007fca7  mov     rcx, [rcx+10h]
0x18007fcab  mov     edx, 29h ; ')'
0x18007fcb0  mov     [rsp+128h+cbData], ebx
0x18007fcb4  mov     r9, rsi
0x18007fcb7  mov     [rsp+128h+lpData], rdi
0x18007fcbc  call    WPP_SF_SSD
0x18007fcc1  mov     edx, ebx; int
0x18007fcc3  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18007fcc8  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18007fccd  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18007fcd4  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18007fcd9  call    _CxxThrowException_0
0x18007fcdf  add     rsp, 108h
0x18007fce6  pop     rdi
0x18007fce7  pop     rsi
0x18007fce8  pop     rbp
0x18007fce9  pop     rbx
0x18007fcea  retn
```
