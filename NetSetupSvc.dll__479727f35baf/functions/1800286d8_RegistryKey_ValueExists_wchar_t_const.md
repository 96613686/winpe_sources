# RegistryKey::ValueExists(wchar_t const *)

- ea: `0x1800286d8`
- end: `0x18002877e`
- name: `?ValueExists@RegistryKey@@QEBA_NPEB_W@Z`
- size: `166`
- prototype: `bool __fastcall(RegistryKey *__hidden this, const wchar_t *)`
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009cfc`
- `0x18000a4d0`
- `0x18000a570`
- `0x18001e828`
- `0x18001eb14`
- `0x18001f2e4`
- `0x18001f984`
- `0x18001fe58`
- `0x1800209dc`
- `0x180021580`
- `0x180021650`
- `0x180023718`

## callees

- `0x1800032e4`
- `0x180008c78`
- `0x18002498c`
- `0x1800286d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028703`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028703`

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
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
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
0x1800286d8  mov     [rsp+arg_0], rbx
0x1800286dd  push    rdi
0x1800286de  sub     rsp, 100h
0x1800286e5  mov     rcx, [rcx]; hKey
0x1800286e8  xor     r9d, r9d; lpType
0x1800286eb  mov     [rsp+108h+lpcbData], 0; lpcbData
0x1800286f4  xor     r8d, r8d; lpReserved
0x1800286f7  mov     [rsp+108h+lpData], 0; lpData
0x180028700  mov     rdi, rdx
0x180028703  call    cs:__imp_RegQueryValueExW
0x180028709  mov     ebx, eax
0x18002870b  cmp     eax, 2
0x18002870e  jnz     short loc_180028714
0x180028710  xor     al, al
0x180028712  jmp     short loc_18002876D
0x180028714  test    ebx, ebx
0x180028716  jz      short loc_18002876B
0x180028718  mov     rcx, cs:WPP_GLOBAL_Control
0x18002871f  lea     rax, WPP_GLOBAL_Control
0x180028726  cmp     rcx, rax
0x180028729  jz      short loc_18002874D
0x18002872b  cmp     byte ptr [rcx+19h], 2
0x18002872f  jb      short loc_18002874D
0x180028731  mov     rcx, [rcx+10h]
0x180028735  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x18002873c  mov     edx, 13h
0x180028741  mov     dword ptr [rsp+108h+lpData], ebx
0x180028745  mov     r9, rdi
0x180028748  call    WPP_SF_Sd
0x18002874d  mov     edx, ebx; int
0x18002874f  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180028754  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180028759  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180028760  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180028765  call    _CxxThrowException_0
0x18002876b  mov     al, 1
0x18002876d  mov     rbx, [rsp+108h+arg_0]
0x180028775  add     rsp, 100h
0x18002877c  pop     rdi
0x18002877d  retn
```
