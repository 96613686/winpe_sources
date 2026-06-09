# RegistryKey::GetValueQword(wchar_t const *)

- ea: `0x180027be0`
- end: `0x180027d24`
- name: `?GetValueQword@RegistryKey@@QEBA_KPEB_W@Z`
- size: `324`
- prototype: `unsigned __int64 __fastcall(HKEY *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001d9c0`
- `0x1800209dc`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008854`
- `0x180008c78`
- `0x18002498c`
- `0x180027be0`
- `0x180028804`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027c3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027c3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall RegistryKey::GetValueQword(HKEY *this, const wchar_t *a2)
{
  HKEY v2; // rcx
  int v3; // edi
  LSTATUS v4; // eax
  signed int v5; // ebx
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+100h] [rbp+0h] BYREF
  DWORD Type; // [rsp+104h] [rbp+4h] BYREF
  BYTE Data[8]; // [rsp+108h] [rbp+8h] BYREF

  v2 = *this;
  *(_QWORD *)Data = 0;
  v3 = (int)a2;
  cbData = 8;
  Type = 0;
  v4 = RegQueryValueExW(v2, a2, 0, &Type, Data, &cbData);
  v5 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
        v3,
        v4);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v5);
    throw (Win32Exception *)pExceptionObject;
  }
  if ( Type != 11 || cbData != 8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, Type, v3, Type, cbData);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147023267);
    throw (HResultException *)pExceptionObject;
  }
  return *(_QWORD *)Data;
}

```

## disassembly

```asm
0x180027be0  mov     [rsp-8+arg_10], rbx
0x180027be5  mov     [rsp-8+arg_18], rdi
0x180027bea  push    rbp
0x180027beb  lea     rbp, [rsp-20h]
0x180027bf0  sub     rsp, 120h
0x180027bf7  mov     rax, cs:__security_cookie
0x180027bfe  xor     rax, rsp
0x180027c01  mov     [rbp+20h+var_10], rax
0x180027c05  mov     rcx, [rcx]; hKey
0x180027c08  lea     rax, [rbp+20h+cbData]
0x180027c0c  mov     [rsp+120h+lpcbData], rax; lpcbData
0x180027c11  lea     r9, [rbp+20h+Type]; lpType
0x180027c15  lea     rax, [rbp+20h+Data]
0x180027c19  mov     qword ptr [rbp+20h+Data], 0
0x180027c21  xor     r8d, r8d; lpReserved
0x180027c24  mov     [rsp+120h+lpData], rax; lpData
0x180027c29  mov     rdi, rdx
0x180027c2c  mov     [rbp+20h+cbData], 8
0x180027c33  mov     [rbp+20h+Type], 0
0x180027c3a  call    cs:__imp_RegQueryValueExW
0x180027c40  mov     ebx, eax
0x180027c42  test    eax, eax
0x180027c44  jz      short loc_180027C99
0x180027c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c4d  lea     rdx, WPP_GLOBAL_Control
0x180027c54  cmp     rcx, rdx
0x180027c57  jz      short loc_180027C7B
0x180027c59  cmp     byte ptr [rcx+19h], 2
0x180027c5d  jb      short loc_180027C7B
0x180027c5f  mov     rcx, [rcx+10h]
0x180027c63  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027c6a  mov     edx, 1Bh
0x180027c6f  mov     dword ptr [rsp+120h+lpData], eax
0x180027c73  mov     r9, rdi
0x180027c76  call    WPP_SF_Sd
0x180027c7b  mov     edx, ebx; int
0x180027c7d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180027c82  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180027c87  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180027c8e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180027c93  call    _CxxThrowException_0
0x180027c99  mov     r8d, [rbp+20h+Type]
0x180027c9d  mov     eax, [rbp+20h+cbData]
0x180027ca0  cmp     r8d, 0Bh
0x180027ca4  jnz     short loc_180027CD0
0x180027ca6  cmp     eax, 8
0x180027ca9  jnz     short loc_180027CD0
0x180027cab  mov     rax, qword ptr [rbp+20h+Data]
0x180027caf  mov     rcx, [rbp+20h+var_10]
0x180027cb3  xor     rcx, rsp; StackCookie
0x180027cb6  call    __security_check_cookie
0x180027cbb  lea     r11, [rsp+120h+var_s0]
0x180027cc3  mov     rbx, [r11+20h]
0x180027cc7  mov     rdi, [r11+28h]
0x180027ccb  mov     rsp, r11
0x180027cce  pop     rbp
0x180027ccf  retn
0x180027cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cd7  lea     rdx, WPP_GLOBAL_Control
0x180027cde  cmp     rcx, rdx
0x180027ce1  jz      short loc_180027D03
0x180027ce3  cmp     byte ptr [rcx+19h], 2
0x180027ce7  jb      short loc_180027D03
0x180027ce9  mov     rcx, [rcx+10h]
0x180027ced  mov     edx, 1Ch
0x180027cf2  mov     dword ptr [rsp+120h+lpcbData], eax
0x180027cf6  mov     r9, rdi
0x180027cf9  mov     dword ptr [rsp+120h+lpData], r8d
0x180027cfe  call    WPP_SF_SDD
0x180027d03  mov     edx, 8007065Dh; int
0x180027d08  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180027d0d  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180027d12  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180027d19  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180027d1e  call    _CxxThrowException_0
```
