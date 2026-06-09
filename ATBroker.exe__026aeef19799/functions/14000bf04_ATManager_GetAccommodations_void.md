# ATManager::GetAccommodations(void)

- ea: `0x14000bf04`
- end: `0x14000c100`
- name: `?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ`
- size: `508`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e1dc`
- `0x140011c60`

## callees

- `0x140004890`
- `0x14000bf04`
- `0x1400116c4`
- `0x140015b00`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000bf69`
- `ADVAPI32!RegOpenKeyExW` at `0x14000bf69`
- `ADVAPI32!RegCloseKey` at `0x14000c0c0`
- `ADVAPI32!RegCloseKey` at `0x14000c0c0`
- `KERNEL32!RegEnumKeyExW` at `0x14000c0a7`
- `KERNEL32!RegEnumKeyExW` at `0x14000c0a7`
- `msvcrt!malloc` at `0x14000bfe1`
- `msvcrt!malloc` at `0x14000bfe1`

## string_xrefs

- `0x14000bf5b`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATManager::GetAccommodations(__int64 a1)
{
  HKEY v2; // rdi
  DWORD v3; // r14d
  DWORD i; // edx
  struct Accommodation *v5; // rsi
  __int64 v6; // r15
  unsigned __int64 v7; // rcx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  int v10; // r8d
  _QWORD *j; // rcx
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 **v14; // rax
  HKEY hKey; // [rsp+40h] [rbp-79h] BYREF
  HKEY v17; // [rsp+48h] [rbp-71h]
  __int64 v18; // [rsp+50h] [rbp-69h]
  __int64 v19; // [rsp+58h] [rbp-61h]
  WCHAR Name[64]; // [rsp+60h] [rbp-59h] BYREF

  v2 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs",
          0,
          0x20019u,
          &hKey) )
  {
    v2 = hKey;
    v17 = hKey;
    v3 = 0;
    for ( i = 0; ; i = v3 )
    {
      LODWORD(hKey) = 64;
      if ( RegEnumKeyExW(v2, i, Name, (LPDWORD)&hKey, 0, 0, 0, 0) == 259 )
        break;
      v5 = Accommodation::Open(Name);
      if ( v5 )
      {
        v6 = *(_QWORD *)(a1 + 312);
        if ( !*(_QWORD *)(a1 + 336) )
        {
          v7 = *(unsigned int *)(a1 + 344);
          if ( *(_DWORD *)(a1 + 344) )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / v7 < 0x18 )
              goto LABEL_21;
            v8 = 24 * v7;
          }
          else
          {
            v8 = 0;
          }
          v9 = malloc(v8 + 8);
          if ( !v9 )
LABEL_21:
            ATL::AtlThrowImpl(-2147024882);
          *v9 = *(_QWORD *)(a1 + 328);
          *(_QWORD *)(a1 + 328) = v9;
          v10 = *(_DWORD *)(a1 + 344) - 1;
          for ( j = &v9[2 * v10 + 1 + (unsigned int)v10]; v10 >= 0; --v10 )
          {
            *j = *(_QWORD *)(a1 + 336);
            *(_QWORD *)(a1 + 336) = j;
            j -= 3;
          }
        }
        v12 = *(__int64 **)(a1 + 336);
        v13 = *v12;
        v12[2] = (__int64)v5;
        *(_QWORD *)(a1 + 336) = v13;
        v12[1] = v6;
        *v12 = 0;
        ++*(_QWORD *)(a1 + 320);
        v14 = *(__int64 ***)(a1 + 312);
        if ( v14 )
          *v14 = v12;
        else
          *(_QWORD *)(a1 + 304) = v12;
        *(_QWORD *)(a1 + 312) = v12;
      }
      ++v3;
    }
  }
  if ( v2 )
    RegCloseKey(v2);
  return a1 + 304;
}

```

## disassembly

```asm
0x14000bf04  mov     [rsp-8+arg_8], rbx
0x14000bf09  mov     [rsp-8+arg_10], rsi
0x14000bf0e  push    rbp
0x14000bf0f  push    rdi
0x14000bf10  push    r12
0x14000bf12  push    r14
0x14000bf14  push    r15
0x14000bf16  lea     rbp, [rsp-37h]
0x14000bf1b  sub     rsp, 0F0h
0x14000bf22  mov     rax, cs:__security_cookie
0x14000bf29  xor     rax, rsp
0x14000bf2c  mov     [rbp+57h+var_30], rax
0x14000bf30  mov     rbx, rcx
0x14000bf33  xor     r12d, r12d
0x14000bf36  mov     edi, r12d
0x14000bf39  mov     [rbp+57h+var_C8], r12
0x14000bf3d  mov     [rbp+57h+var_C0], r12
0x14000bf41  mov     [rbp+57h+var_B8], r12
0x14000bf45  mov     [rbp+57h+hKey], r12
0x14000bf49  lea     rax, [rbp+57h+hKey]
0x14000bf4d  mov     [rsp+110h+phkResult], rax; phkResult
0x14000bf52  mov     r9d, 20019h; samDesired
0x14000bf58  xor     r8d, r8d; ulOptions
0x14000bf5b  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x14000bf62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000bf69  call    cs:__imp_RegOpenKeyExW
0x14000bf6f  test    eax, eax
0x14000bf71  jnz     loc_14000C0B8
0x14000bf77  mov     rdi, [rbp+57h+hKey]
0x14000bf7b  mov     [rbp+57h+var_C8], rdi
0x14000bf7f  mov     r14d, r12d
0x14000bf82  xor     edx, edx
0x14000bf84  jmp     loc_14000C081
0x14000bf89  lea     rcx, [rbp+57h+Name]; unsigned __int16 *
0x14000bf8d  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14000bf92  mov     rsi, rax
0x14000bf95  test    rax, rax
0x14000bf98  jz      loc_14000C07B
0x14000bf9e  mov     r15, [rbx+138h]
0x14000bfa5  cmp     [rbx+150h], r12
0x14000bfac  jnz     loc_14000C039
0x14000bfb2  mov     ecx, [rbx+158h]
0x14000bfb8  test    rcx, rcx
0x14000bfbb  jnz     short loc_14000BFC2
0x14000bfbd  mov     rcx, r12
0x14000bfc0  jmp     short loc_14000BFDD
0x14000bfc2  xor     edx, edx
0x14000bfc4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bfc8  div     rcx
0x14000bfcb  cmp     rax, 18h
0x14000bfcf  jb      loc_14000C0F5
0x14000bfd5  lea     rcx, [rcx+rcx*2]
0x14000bfd9  shl     rcx, 3
0x14000bfdd  add     rcx, 8; Size
0x14000bfe1  call    cs:__imp_malloc
0x14000bfe7  test    rax, rax
0x14000bfea  jz      loc_14000C0F5
0x14000bff0  mov     rcx, [rbx+148h]
0x14000bff7  mov     [rax], rcx
0x14000bffa  mov     [rbx+148h], rax
0x14000c001  mov     r8d, [rbx+158h]
0x14000c008  sub     r8d, 1
0x14000c00c  lea     rcx, ds:1[r8*2]
0x14000c014  lea     rcx, [rcx+r8]
0x14000c018  lea     rcx, [rax+rcx*8]
0x14000c01c  js      short loc_14000C039
0x14000c01e  mov     rax, [rbx+150h]
0x14000c025  mov     [rcx], rax
0x14000c028  mov     [rbx+150h], rcx
0x14000c02f  sub     rcx, 18h
0x14000c033  sub     r8d, 1
0x14000c037  jns     short loc_14000C01E
0x14000c039  mov     rcx, [rbx+150h]
0x14000c040  mov     rax, [rcx]
0x14000c043  mov     [rcx+10h], rsi
0x14000c047  mov     [rbx+150h], rax
0x14000c04e  mov     [rcx+8], r15
0x14000c052  mov     [rcx], r12
0x14000c055  inc     qword ptr [rbx+140h]
0x14000c05c  mov     rax, [rbx+138h]
0x14000c063  test    rax, rax
0x14000c066  jz      short loc_14000C06D
0x14000c068  mov     [rax], rcx
0x14000c06b  jmp     short loc_14000C074
0x14000c06d  mov     [rbx+130h], rcx
0x14000c074  mov     [rbx+138h], rcx
0x14000c07b  inc     r14d
0x14000c07e  mov     edx, r14d; dwIndex
0x14000c081  mov     [rsp+110h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14000c086  mov     [rsp+110h+lpcchClass], r12; lpcchClass
0x14000c08b  mov     [rsp+110h+lpClass], r12; lpClass
0x14000c090  mov     [rsp+110h+phkResult], r12; lpReserved
0x14000c095  mov     dword ptr [rbp+57h+hKey], 40h ; '@'
0x14000c09c  lea     r9, [rbp+57h+hKey]; lpcchName
0x14000c0a0  lea     r8, [rbp+57h+Name]; lpName
0x14000c0a4  mov     rcx, rdi; hKey
0x14000c0a7  call    cs:__imp_RegEnumKeyExW
0x14000c0ad  cmp     eax, 103h
0x14000c0b2  jnz     loc_14000BF89
0x14000c0b8  test    rdi, rdi
0x14000c0bb  jz      short loc_14000C0C6
0x14000c0bd  mov     rcx, rdi; hKey
0x14000c0c0  call    cs:__imp_RegCloseKey
0x14000c0c6  lea     rax, [rbx+130h]
0x14000c0cd  mov     rcx, [rbp+57h+var_30]
0x14000c0d1  xor     rcx, rsp; StackCookie
0x14000c0d4  call    __security_check_cookie
0x14000c0d9  lea     r11, [rsp+110h+var_20]
0x14000c0e1  mov     rbx, [r11+38h]
0x14000c0e5  mov     rsi, [r11+40h]
0x14000c0e9  mov     rsp, r11
0x14000c0ec  pop     r15
0x14000c0ee  pop     r14
0x14000c0f0  pop     r12
0x14000c0f2  pop     rdi
0x14000c0f3  pop     rbp
0x14000c0f4  retn
0x14000c0f5  mov     ecx, 8007000Eh; int
0x14000c0fa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
