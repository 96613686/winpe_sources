# VInitPrintVerifier

- ea: `0x18002ef38`
- end: `0x18002f072`
- name: `VInitPrintVerifier`
- size: `314`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004090`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180020acc`
- `0x18002ef38`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x18002efb2`
- `KERNEL32!GetSystemDirectoryW` at `0x18002efb2`
- `KERNEL32!GetModuleHandleW` at `0x18002effe`
- `KERNEL32!GetModuleHandleW` at `0x18002effe`
- `KERNEL32!GetProcAddress` at `0x18002f020`
- `KERNEL32!GetProcAddress` at `0x18002f020`

## string_xrefs

- `0x18002ef73`: `vfprint.dll`
- `0x18002efda`: `vfprint.dll`

## pseudocode

```c
__int64 VInitPrintVerifier()
{
  const wchar_t *v0; // rax
  __int64 v1; // rdx
  __int64 v2; // rbx
  __int64 SystemDirectoryW; // rcx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  wchar_t Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  v0 = L"vfprint.dll";
  v1 = 259;
  do
  {
    if ( !*v0 )
      break;
    ++v0;
    --v1;
  }
  while ( v1 );
  v2 = (259 - v1) & -(__int64)(v1 != 0);
  if ( !v1
    || (SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u), (unsigned __int64)(SystemDirectoryW - 1) > 0x101)
    || (unsigned __int64)(SystemDirectoryW + v2) >= 0x103
    || (Buffer[SystemDirectoryW] = 92, StringCchCatW(Buffer, 0x104u, L"vfprint.dll") < 0) )
  {
    ghPrintVerifierModule = 0;
LABEL_12:
    result = 0;
    goto LABEL_13;
  }
  ModuleHandleW = GetModuleHandleW(Buffer);
  ghPrintVerifierModule = ModuleHandleW;
  if ( !ModuleHandleW )
    goto LABEL_12;
  ProcAddress = GetProcAddress(ModuleHandleW, "PrintVerifierIsLayerEnabled");
  if ( !ProcAddress )
    goto LABEL_12;
  result = ((__int64 (__fastcall *)(__int64))ProcAddress)(2);
LABEL_13:
  gbPrintVerifierDriverLayerEnabled = result;
  return result;
}

```

## disassembly

```asm
0x18002ef38  mov     [rsp+arg_0], rbx
0x18002ef3d  mov     [rsp+arg_8], rsi
0x18002ef42  push    rdi
0x18002ef43  sub     rsp, 240h
0x18002ef4a  mov     rax, cs:__security_cookie
0x18002ef51  xor     rax, rsp
0x18002ef54  mov     [rsp+248h+var_18], rax
0x18002ef5c  xor     edx, edx; Val
0x18002ef5e  lea     rcx, [rsp+248h+Buffer]; void *
0x18002ef63  mov     r8d, 208h; Size
0x18002ef69  call    memset_0
0x18002ef6e  mov     esi, 103h
0x18002ef73  lea     rax, aVfprintDll; "vfprint.dll"
0x18002ef7a  mov     edx, esi
0x18002ef7c  xor     edi, edi
0x18002ef7e  cmp     [rax], di
0x18002ef81  jz      short loc_18002EF8D
0x18002ef83  add     rax, 2
0x18002ef87  sub     rdx, 1
0x18002ef8b  jnz     short loc_18002EF7E
0x18002ef8d  mov     rcx, rsi
0x18002ef90  mov     rax, rdx
0x18002ef93  sub     rcx, rdx
0x18002ef96  neg     rax
0x18002ef99  sbb     rbx, rbx
0x18002ef9c  and     rbx, rcx
0x18002ef9f  test    rdx, rdx
0x18002efa2  jz      loc_18002F03D
0x18002efa8  mov     edx, 104h; uSize
0x18002efad  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18002efb2  call    cs:__imp_GetSystemDirectoryW
0x18002efb9  nop     dword ptr [rax+rax+00h]
0x18002efbe  mov     ecx, eax
0x18002efc0  lea     rax, [rcx-1]
0x18002efc4  cmp     rax, 101h
0x18002efca  ja      short loc_18002F03D
0x18002efcc  lea     rax, [rcx+rbx]
0x18002efd0  cmp     rax, rsi
0x18002efd3  jnb     short loc_18002F03D
0x18002efd5  mov     eax, 5Ch ; '\'
0x18002efda  lea     r8, aVfprintDll; "vfprint.dll"
0x18002efe1  mov     [rsp+rcx*2+248h+Buffer], ax
0x18002efe6  mov     edx, 104h; cchDest
0x18002efeb  lea     rcx, [rsp+248h+Buffer]; pszDest
0x18002eff0  call    StringCchCatW
0x18002eff5  test    eax, eax
0x18002eff7  js      short loc_18002F03D
0x18002eff9  lea     rcx, [rsp+248h+Buffer]; lpModuleName
0x18002effe  call    cs:__imp_GetModuleHandleW
0x18002f005  nop     dword ptr [rax+rax+00h]
0x18002f00a  mov     cs:ghPrintVerifierModule, rax
0x18002f011  test    rax, rax
0x18002f014  jz      short loc_18002F044
0x18002f016  lea     rdx, aPrintverifieri; "PrintVerifierIsLayerEnabled"
0x18002f01d  mov     rcx, rax; hModule
0x18002f020  call    cs:__imp_GetProcAddress
0x18002f027  nop     dword ptr [rax+rax+00h]
0x18002f02c  test    rax, rax
0x18002f02f  jz      short loc_18002F044
0x18002f031  mov     ecx, 2
0x18002f036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f03b  jmp     short loc_18002F046
0x18002f03d  mov     cs:ghPrintVerifierModule, rdi
0x18002f044  mov     eax, edi
0x18002f046  mov     cs:gbPrintVerifierDriverLayerEnabled, eax
0x18002f04c  mov     rcx, [rsp+248h+var_18]
0x18002f054  xor     rcx, rsp; StackCookie
0x18002f057  call    __security_check_cookie
0x18002f05c  lea     r11, [rsp+248h+var_8]
0x18002f064  mov     rbx, [r11+10h]
0x18002f068  mov     rsi, [r11+18h]
0x18002f06c  mov     rsp, r11
0x18002f06f  pop     rdi
0x18002f070  retn
```
