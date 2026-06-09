# RegistryKey::ValueExists(wchar_t const *)

- ea: `0x18000536c`
- end: `0x180005412`
- name: `?ValueExists@RegistryKey@@QEBA_NPEB_W@Z`
- size: `166`
- prototype: `char __fastcall(HKEY *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003f40`
- `0x180006af8`

## callees

- `0x18000536c`
- `0x1800065d4`
- `0x18000895c`
- `0x18000fbfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005397`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005397`

## pseudocode

```c
char __fastcall RegistryKey::ValueExists(HKEY *this, const wchar_t *a2)
{
  int v2; // edi
  LSTATUS Value; // ebx
  _BYTE pExceptionObject[216]; // [rsp+30h] [rbp-D8h] BYREF

  v2 = (int)a2;
  Value = RegQueryValueExW(*this, a2, 0, 0, 0, 0);
  if ( Value == 2 )
    return 0;
  if ( Value )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
        v2,
        Value);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, Value);
    throw (Win32Exception *)pExceptionObject;
  }
  return 1;
}

```

## disassembly

```asm
0x18000536c  mov     [rsp+arg_0], rbx
0x180005371  push    rdi
0x180005372  sub     rsp, 100h
0x180005379  mov     rcx, [rcx]; hKey
0x18000537c  xor     r9d, r9d; lpType
0x18000537f  mov     [rsp+108h+lpcbData], 0; lpcbData
0x180005388  xor     r8d, r8d; lpReserved
0x18000538b  mov     [rsp+108h+lpData], 0; lpData
0x180005394  mov     rdi, rdx
0x180005397  call    cs:__imp_RegQueryValueExW
0x18000539d  mov     ebx, eax
0x18000539f  cmp     eax, 2
0x1800053a2  jnz     short loc_1800053B7
0x1800053a4  xor     al, al
0x1800053a6  mov     rbx, [rsp+108h+arg_0]
0x1800053ae  add     rsp, 100h
0x1800053b5  pop     rdi
0x1800053b6  retn
0x1800053b7  test    ebx, ebx
0x1800053b9  jz      short loc_18000540E
0x1800053bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053c2  lea     rax, WPP_GLOBAL_Control
0x1800053c9  cmp     rcx, rax
0x1800053cc  jz      short loc_1800053F0
0x1800053ce  cmp     byte ptr [rcx+19h], 2
0x1800053d2  jb      short loc_1800053F0
0x1800053d4  mov     rcx, [rcx+10h]
0x1800053d8  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x1800053df  mov     edx, 13h
0x1800053e4  mov     dword ptr [rsp+108h+lpData], ebx
0x1800053e8  mov     r9, rdi
0x1800053eb  call    WPP_SF_SD
0x1800053f0  mov     edx, ebx; int
0x1800053f2  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800053f7  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800053fc  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180005403  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180005408  call    _CxxThrowException_0
0x18000540e  mov     al, 1
0x180005410  jmp     short loc_1800053A6
```
