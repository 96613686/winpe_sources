# WPFUtils::OSVersionHelper::IsWindowsVersionOrGreater(ulong,ulong,ushort,ulong)

- ea: `0x18000cc9c`
- end: `0x18000cd9d`
- name: `?IsWindowsVersionOrGreater@OSVersionHelper@WPFUtils@@CA_NKKGK@Z`
- size: `257`
- prototype: `bool __fastcall(unsigned int, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000a49c`
- `0x18000a8f0`

## callees

- `0x18000cc9c`
- `0x18000cdb0`
- `0x18000e0cc`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000cd6e`
- `KERNEL32!FreeLibrary` at `0x18000cd6e`
- `KERNEL32!GetProcAddress` at `0x18000cd4c`
- `KERNEL32!GetProcAddress` at `0x18000cd4c`
- `KERNEL32!LoadLibraryW` at `0x18000cd34`
- `KERNEL32!LoadLibraryW` at `0x18000cd34`
- `KERNEL32!VerSetConditionMask` at `0x18000ccff`
- `KERNEL32!VerSetConditionMask` at `0x18000cd0f`
- `KERNEL32!VerSetConditionMask` at `0x18000cd1f`
- `KERNEL32!VerSetConditionMask` at `0x18000ccff`
- `KERNEL32!VerSetConditionMask` at `0x18000cd0f`
- `KERNEL32!VerSetConditionMask` at `0x18000cd1f`

## string_xrefs

- `0x18000cd25`: `ntdll.dll`

## pseudocode

```c
bool __fastcall WPFUtils::OSVersionHelper::IsWindowsVersionOrGreater(__int64 a1, int a2)
{
  ULONGLONG v2; // rax
  ULONGLONG v3; // rax
  int v4; // edi
  ULONGLONG v5; // rsi
  HMODULE LibraryW; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  _DWORD v10[3]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+2Ch] [rbp-D4h]
  _BYTE v12[256]; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v13; // [rsp+134h] [rbp+34h]

  v10[2] = a2;
  v10[0] = 284;
  v11 = 0;
  v10[1] = 6;
  memset_0(v12, 0, sizeof(v12));
  v13 = 0;
  v2 = VerSetConditionMask(0, 2u, 3u);
  v3 = VerSetConditionMask(v2, 1u, 3u);
  v4 = -1073741702;
  v5 = VerSetConditionMask(v3, 0x20u, 3u);
  LibraryW = LoadLibraryW(L"ntdll.dll");
  v7 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "RtlVerifyVersionInfo");
    if ( ProcAddress )
      v4 = ((__int64 (__fastcall *)(_DWORD *, __int64, ULONGLONG))ProcAddress)(v10, 35, v5);
    FreeLibrary(v7);
  }
  return v4 == 0;
}

```

## disassembly

```asm
0x18000cc9c  mov     [rsp-8+arg_0], rbx
0x18000cca1  mov     [rsp-8+arg_10], rsi
0x18000cca6  push    rbp
0x18000cca7  push    rdi
0x18000cca8  push    r14
0x18000ccaa  lea     rbp, [rsp-50h]
0x18000ccaf  sub     rsp, 150h
0x18000ccb6  mov     rax, cs:__security_cookie
0x18000ccbd  xor     rax, rsp
0x18000ccc0  mov     [rbp+60h+var_20], rax
0x18000ccc4  mov     [rsp+160h+var_138], edx
0x18000ccc8  lea     rcx, [rsp+160h+var_12C]; void *
0x18000cccd  xor     r14d, r14d
0x18000ccd0  mov     [rsp+160h+var_140], 11Ch
0x18000ccd8  xor     edx, edx; Val
0x18000ccda  mov     [rsp+160h+var_134], r14
0x18000ccdf  mov     r8d, 100h; Size
0x18000cce5  mov     [rsp+160h+var_13C], 6
0x18000cced  call    memset_0
0x18000ccf2  mov     r8b, 3; Condition
0x18000ccf5  mov     [rbp+60h+var_2C], r14
0x18000ccf9  lea     edx, [r14+2]; TypeMask
0x18000ccfd  xor     ecx, ecx; ConditionMask
0x18000ccff  call    cs:__imp_VerSetConditionMask
0x18000cd05  mov     r8b, 3; Condition
0x18000cd08  lea     edx, [r14+1]; TypeMask
0x18000cd0c  mov     rcx, rax; ConditionMask
0x18000cd0f  call    cs:__imp_VerSetConditionMask
0x18000cd15  mov     r8b, 3; Condition
0x18000cd18  lea     edx, [r14+20h]; TypeMask
0x18000cd1c  mov     rcx, rax; ConditionMask
0x18000cd1f  call    cs:__imp_VerSetConditionMask
0x18000cd25  lea     rcx, LibFileName; "ntdll.dll"
0x18000cd2c  mov     edi, 0C000007Ah
0x18000cd31  mov     rsi, rax
0x18000cd34  call    cs:__imp_LoadLibraryW
0x18000cd3a  mov     rbx, rax
0x18000cd3d  test    rax, rax
0x18000cd40  jz      short loc_18000CD74
0x18000cd42  lea     rdx, aRtlverifyversi; "RtlVerifyVersionInfo"
0x18000cd49  mov     rcx, rax; hModule
0x18000cd4c  call    cs:__imp_GetProcAddress
0x18000cd52  test    rax, rax
0x18000cd55  jz      short loc_18000CD6B
0x18000cd57  mov     r8, rsi
0x18000cd5a  lea     edx, [r14+23h]
0x18000cd5e  lea     rcx, [rsp+160h+var_140]
0x18000cd63  call    cs:__guard_dispatch_icall_fptr
0x18000cd69  mov     edi, eax
0x18000cd6b  mov     rcx, rbx; hLibModule
0x18000cd6e  call    cs:__imp_FreeLibrary
0x18000cd74  test    edi, edi
0x18000cd76  setz    al
0x18000cd79  mov     rcx, [rbp+60h+var_20]
0x18000cd7d  xor     rcx, rsp; StackCookie
0x18000cd80  call    __security_check_cookie
0x18000cd85  lea     r11, [rsp+160h+var_10]
0x18000cd8d  mov     rbx, [r11+20h]
0x18000cd91  mov     rsi, [r11+30h]
0x18000cd95  mov     rsp, r11
0x18000cd98  pop     r14
0x18000cd9a  pop     rdi
0x18000cd9b  pop     rbp
0x18000cd9c  retn
```
