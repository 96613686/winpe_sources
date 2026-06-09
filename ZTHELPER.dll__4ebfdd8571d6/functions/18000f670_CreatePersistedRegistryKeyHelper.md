# CreatePersistedRegistryKeyHelper

- ea: `0x18000f670`
- end: `0x18000f784`
- name: `CreatePersistedRegistryKeyHelper`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, __int64, int, _QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180002fc8`
- `0x180003d88`
- `0x18000ff50`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x180009eac`
- `0x18000f670`
- `0x180013c84`
- `0x180016134`

## import_xrefs

- `KERNELBASE!RegCreateKeyExInternalW` at `0x18000f722`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x18000f722`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18000f73c`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18000f73c`

## pseudocode

```c
__int64 __fastcall CreatePersistedRegistryKeyHelper(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        _QWORD *a8)
{
  int PersistedRegistryLocation; // eax
  unsigned int Key; // eax
  int v13; // ecx
  int v14; // r8d
  unsigned int v15; // ebx
  _BYTE v17[528]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(v17, 0, 0x20Au);
  *a8 = 0;
  PersistedRegistryLocation = WxGetPersistedRegistryLocation(a1, a2, a3, (__int64)v17);
  if ( PersistedRegistryLocation >= 0 )
  {
    if ( a7 )
      Key = RegCreateKeyExInternalW(-2147483646, v17, 0, 0, 0, a5, 0, a8, 0, a6);
    else
      Key = RegOpenKeyExInternalW(-2147483646, v17, 0, a5, a8, a6);
  }
  else
  {
    Key = WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
  }
  v15 = Key;
  if ( Key && (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_SD(v13, 10, v14, (unsigned int)v17, Key);
  return v15;
}

```

## disassembly

```asm
0x18000f670  push    rbx
0x18000f672  push    rbp
0x18000f673  push    rsi
0x18000f674  push    rdi
0x18000f675  push    r14
0x18000f677  sub     rsp, 270h
0x18000f67e  mov     rax, cs:__security_cookie
0x18000f685  xor     rax, rsp
0x18000f688  mov     [rsp+298h+var_38], rax
0x18000f690  mov     rbp, [rsp+298h+arg_28]
0x18000f698  mov     rsi, r8
0x18000f69b  mov     r14, [rsp+298h+arg_38]
0x18000f6a3  mov     rdi, rdx
0x18000f6a6  mov     rbx, rcx
0x18000f6a9  xor     edx, edx; Val
0x18000f6ab  mov     r8d, 20Ah; Size
0x18000f6b1  lea     rcx, [rsp+298h+var_248]; void *
0x18000f6b6  call    memset_0
0x18000f6bb  lea     r9, [rsp+298h+var_248]
0x18000f6c0  mov     qword ptr [r14], 0
0x18000f6c7  mov     r8, rsi
0x18000f6ca  mov     rdx, rdi
0x18000f6cd  mov     rcx, rbx
0x18000f6d0  call    WxGetPersistedRegistryLocation
0x18000f6d5  test    eax, eax
0x18000f6d7  jns     short loc_18000F6E2
0x18000f6d9  mov     ecx, eax
0x18000f6db  call    WX_WIN32_FROM_HR
0x18000f6e0  jmp     short loc_18000F742
0x18000f6e2  xor     r8d, r8d
0x18000f6e5  lea     rdx, [rsp+298h+var_248]
0x18000f6ea  mov     rcx, 0FFFFFFFF80000002h
0x18000f6f1  cmp     [rsp+298h+arg_30], r8d
0x18000f6f9  jz      short loc_18000F72A
0x18000f6fb  mov     eax, [rsp+298h+arg_20]
0x18000f702  xor     r9d, r9d
0x18000f705  mov     [rsp+298h+var_250], rbp
0x18000f70a  mov     [rsp+298h+var_258], r8
0x18000f70f  mov     [rsp+298h+var_260], r14
0x18000f714  mov     [rsp+298h+var_268], r8
0x18000f719  mov     dword ptr [rsp+298h+var_270], eax
0x18000f71d  mov     dword ptr [rsp+298h+var_278], r8d
0x18000f722  call    cs:__imp_RegCreateKeyExInternalW
0x18000f728  jmp     short loc_18000F742
0x18000f72a  mov     r9d, [rsp+298h+arg_20]
0x18000f732  mov     [rsp+298h+var_270], rbp
0x18000f737  mov     [rsp+298h+var_278], r14
0x18000f73c  call    cs:__imp_RegOpenKeyExInternalW
0x18000f742  mov     ebx, eax
0x18000f744  test    eax, eax
0x18000f746  jz      short loc_18000F764
0x18000f748  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f74f  jz      short loc_18000F764
0x18000f751  mov     edx, 0Ah
0x18000f756  mov     dword ptr [rsp+298h+var_278], eax
0x18000f75a  lea     r9, [rsp+298h+var_248]
0x18000f75f  call    WPP_SF_SD
0x18000f764  mov     eax, ebx
0x18000f766  mov     rcx, [rsp+298h+var_38]
0x18000f76e  xor     rcx, rsp; StackCookie
0x18000f771  call    __security_check_cookie
0x18000f776  add     rsp, 270h
0x18000f77d  pop     r14
0x18000f77f  pop     rdi
0x18000f780  pop     rsi
0x18000f781  pop     rbp
0x18000f782  pop     rbx
0x18000f783  retn
```
