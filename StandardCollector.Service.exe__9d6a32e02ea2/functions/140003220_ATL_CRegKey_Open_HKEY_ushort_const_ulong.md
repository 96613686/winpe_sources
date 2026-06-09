# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x140003220`
- end: `0x14000332d`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140001230`
- `0x140005400`
- `0x140006620`
- `0x14000a42c`

## callees

- `0x140003220`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140003278`
- `KERNEL32!GetProcAddress` at `0x140003278`
- `KERNEL32!GetModuleHandleW` at `0x140003263`
- `KERNEL32!GetModuleHandleW` at `0x140003263`
- `ADVAPI32!RegOpenKeyExW` at `0x1400032e3`
- `ADVAPI32!RegOpenKeyExW` at `0x1400032e3`
- `ADVAPI32!RegCloseKey` at `0x1400032f7`
- `ADVAPI32!RegCloseKey` at `0x1400032f7`

## string_xrefs

- `0x14000325c`: `Advapi32.dll`
- `0x14000326e`: `RegOpenKeyTransactedW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY a2, const unsigned __int16 *a3)
{
  __int64 v5; // rdi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v8; // eax
  __int64 v9; // rcx
  HKEY phkResult; // [rsp+40h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = *((_QWORD *)this + 2);
  if ( !v5 )
    goto LABEL_8;
  if ( !*(_QWORD *)v5 )
  {
    if ( !*(_DWORD *)(v5 + 8) )
    {
LABEL_7:
      v9 = 1;
      goto LABEL_10;
    }
LABEL_8:
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20219u, &phkResult);
    goto LABEL_9;
  }
  ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
  if ( !ModuleHandleW )
    goto LABEL_7;
  ProcAddress = GetProcAddress(ModuleHandleW, "RegOpenKeyTransactedW");
  if ( !ProcAddress )
    goto LABEL_7;
  v8 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, __int64, HKEY *, _QWORD, _QWORD))ProcAddress)(
         -2147483646,
         a3,
         0,
         131609,
         &phkResult,
         *(_QWORD *)v5,
         0);
LABEL_9:
  v9 = v8;
LABEL_10:
  if ( !(_DWORD)v9 )
  {
    if ( *(_QWORD *)this != v9 )
      LODWORD(v9) = RegCloseKey(*(HKEY *)this);
    *(_QWORD *)this = phkResult;
    *((_DWORD *)this + 2) = 512;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140003220  mov     [rsp+arg_8], rbx
0x140003225  mov     [rsp+arg_18], rsi
0x14000322a  push    rdi
0x14000322b  sub     rsp, 50h
0x14000322f  mov     rax, cs:__security_cookie
0x140003236  xor     rax, rsp
0x140003239  mov     [rsp+58h+var_10], rax
0x14000323e  mov     rsi, r8
0x140003241  mov     rbx, rcx
0x140003244  mov     [rsp+58h+var_18], 0
0x14000324d  mov     rdi, [rcx+10h]
0x140003251  test    rdi, rdi
0x140003254  jz      short loc_1400032C6
0x140003256  cmp     qword ptr [rdi], 0
0x14000325a  jz      short loc_1400032B9
0x14000325c  lea     rcx, ModuleName; "Advapi32.dll"
0x140003263  call    cs:__imp_GetModuleHandleW
0x140003269  test    rax, rax
0x14000326c  jz      short loc_1400032BF
0x14000326e  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x140003275  mov     rcx, rax; hModule
0x140003278  call    cs:__imp_GetProcAddress
0x14000327e  test    rax, rax
0x140003281  jz      short loc_1400032BF
0x140003283  mov     [rsp+58h+var_28], 0
0x14000328c  mov     rcx, [rdi]
0x14000328f  mov     [rsp+58h+var_30], rcx
0x140003294  lea     rcx, [rsp+58h+var_18]
0x140003299  mov     [rsp+58h+phkResult], rcx
0x14000329e  mov     r9d, 20219h
0x1400032a4  xor     r8d, r8d
0x1400032a7  mov     rdx, rsi
0x1400032aa  mov     rcx, 0FFFFFFFF80000002h
0x1400032b1  call    cs:__guard_dispatch_icall_fptr
0x1400032b7  jmp     short loc_1400032E9
0x1400032b9  cmp     dword ptr [rdi+8], 0
0x1400032bd  jnz     short loc_1400032C6
0x1400032bf  mov     ecx, 1
0x1400032c4  jmp     short loc_1400032EB
0x1400032c6  lea     rax, [rsp+58h+var_18]
0x1400032cb  mov     [rsp+58h+phkResult], rax; phkResult
0x1400032d0  mov     r9d, 20219h; samDesired
0x1400032d6  xor     r8d, r8d; ulOptions
0x1400032d9  mov     rdx, rsi; lpSubKey
0x1400032dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400032e3  call    cs:__imp_RegOpenKeyExW
0x1400032e9  mov     ecx, eax
0x1400032eb  test    ecx, ecx
0x1400032ed  jnz     short loc_14000330E
0x1400032ef  cmp     [rbx], rcx
0x1400032f2  jz      short loc_1400032FF
0x1400032f4  mov     rcx, [rbx]; hKey
0x1400032f7  call    cs:__imp_RegCloseKey
0x1400032fd  mov     ecx, eax
0x1400032ff  mov     rax, [rsp+58h+var_18]
0x140003304  mov     [rbx], rax
0x140003307  mov     dword ptr [rbx+8], 200h
0x14000330e  mov     eax, ecx
0x140003310  mov     rcx, [rsp+58h+var_10]
0x140003315  xor     rcx, rsp; StackCookie
0x140003318  call    __security_check_cookie
0x14000331d  mov     rbx, [rsp+58h+arg_8]
0x140003322  mov     rsi, [rsp+58h+arg_18]
0x140003327  add     rsp, 50h
0x14000332b  pop     rdi
0x14000332c  retn
```
