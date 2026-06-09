# RegistryKey::SetValue(wchar_t const *,wchar_t const *)

- ea: `0x180028284`
- end: `0x18002832b`
- name: `?SetValue@RegistryKey@@QEBAXPEB_W0@Z`
- size: `167`
- prototype: `void __fastcall(HKEY *this, const wchar_t *, const BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800283fc`

## callees

- `0x1800032e4`
- `0x180008c78`
- `0x180028284`
- `0x1800289c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800282c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800282c2`

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
0x180028284  push    rbx
0x180028286  push    rbp
0x180028287  push    rsi
0x180028288  push    rdi
0x180028289  sub     rsp, 108h
0x180028290  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028294  mov     rdi, r8
0x180028297  xor     ebp, ebp
0x180028299  mov     rsi, rdx
0x18002829c  inc     rax
0x18002829f  cmp     [r8+rax*2], bp
0x1800282a4  jnz     short loc_18002829C
0x1800282a6  mov     rcx, [rcx]; hKey
0x1800282a9  lea     eax, ds:2[rax*2]
0x1800282b0  mov     [rsp+128h+cbData], eax; cbData
0x1800282b4  mov     r9d, 1; dwType
0x1800282ba  xor     r8d, r8d; Reserved
0x1800282bd  mov     [rsp+128h+lpData], rdi; lpData
0x1800282c2  call    cs:__imp_RegSetValueExW
0x1800282c8  mov     ebx, eax
0x1800282ca  test    eax, eax
0x1800282cc  jz      short loc_18002831F
0x1800282ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282d5  lea     rax, WPP_GLOBAL_Control
0x1800282dc  cmp     rcx, rax
0x1800282df  jz      short loc_180028301
0x1800282e1  cmp     byte ptr [rcx+19h], 2
0x1800282e5  jb      short loc_180028301
0x1800282e7  mov     rcx, [rcx+10h]
0x1800282eb  mov     edx, 29h ; ')'
0x1800282f0  mov     [rsp+128h+cbData], ebx
0x1800282f4  mov     r9, rsi
0x1800282f7  mov     [rsp+128h+lpData], rdi
0x1800282fc  call    WPP_SF_SSD
0x180028301  mov     edx, ebx; int
0x180028303  lea     rcx, [rsp+128h+pExceptionObject]; this
0x180028308  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18002830d  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180028314  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180028319  call    _CxxThrowException_0
0x18002831f  add     rsp, 108h
0x180028326  pop     rdi
0x180028327  pop     rsi
0x180028328  pop     rbp
0x180028329  pop     rbx
0x18002832a  retn
```
