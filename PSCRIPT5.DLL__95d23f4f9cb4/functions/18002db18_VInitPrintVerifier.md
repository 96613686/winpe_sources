# VInitPrintVerifier

- ea: `0x18002db18`
- end: `0x18002dc3f`
- name: `VInitPrintVerifier`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004000`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18001fe90`
- `0x18002db18`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x18002db92`
- `KERNEL32!GetSystemDirectoryW` at `0x18002db92`
- `KERNEL32!GetModuleHandleW` at `0x18002dbd8`
- `KERNEL32!GetModuleHandleW` at `0x18002dbd8`
- `KERNEL32!GetProcAddress` at `0x18002dbf4`
- `KERNEL32!GetProcAddress` at `0x18002dbf4`

## string_xrefs

- `0x18002db53`: `vfprint.dll`
- `0x18002dbb4`: `vfprint.dll`

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
0x18002db18  mov     [rsp+arg_0], rbx
0x18002db1d  mov     [rsp+arg_8], rsi
0x18002db22  push    rdi
0x18002db23  sub     rsp, 240h
0x18002db2a  mov     rax, cs:__security_cookie
0x18002db31  xor     rax, rsp
0x18002db34  mov     [rsp+248h+var_18], rax
0x18002db3c  xor     edx, edx; Val
0x18002db3e  lea     rcx, [rsp+248h+Buffer]; void *
0x18002db43  mov     r8d, 208h; Size
0x18002db49  call    memset_0
0x18002db4e  mov     esi, 103h
0x18002db53  lea     rax, aVfprintDll; "vfprint.dll"
0x18002db5a  mov     edx, esi
0x18002db5c  xor     edi, edi
0x18002db5e  cmp     [rax], di
0x18002db61  jz      short loc_18002DB6D
0x18002db63  add     rax, 2
0x18002db67  sub     rdx, 1
0x18002db6b  jnz     short loc_18002DB5E
0x18002db6d  mov     rcx, rsi
0x18002db70  mov     rax, rdx
0x18002db73  sub     rcx, rdx
0x18002db76  neg     rax
0x18002db79  sbb     rbx, rbx
0x18002db7c  and     rbx, rcx
0x18002db7f  test    rdx, rdx
0x18002db82  jz      loc_18002DC0B
0x18002db88  mov     edx, 104h; uSize
0x18002db8d  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18002db92  call    cs:__imp_GetSystemDirectoryW
0x18002db98  mov     ecx, eax
0x18002db9a  lea     rax, [rcx-1]
0x18002db9e  cmp     rax, 101h
0x18002dba4  ja      short loc_18002DC0B
0x18002dba6  lea     rax, [rcx+rbx]
0x18002dbaa  cmp     rax, rsi
0x18002dbad  jnb     short loc_18002DC0B
0x18002dbaf  mov     eax, 5Ch ; '\'
0x18002dbb4  lea     r8, aVfprintDll; "vfprint.dll"
0x18002dbbb  mov     [rsp+rcx*2+248h+Buffer], ax
0x18002dbc0  mov     edx, 104h; cchDest
0x18002dbc5  lea     rcx, [rsp+248h+Buffer]; pszDest
0x18002dbca  call    StringCchCatW
0x18002dbcf  test    eax, eax
0x18002dbd1  js      short loc_18002DC0B
0x18002dbd3  lea     rcx, [rsp+248h+Buffer]; lpModuleName
0x18002dbd8  call    cs:__imp_GetModuleHandleW
0x18002dbde  mov     cs:ghPrintVerifierModule, rax
0x18002dbe5  test    rax, rax
0x18002dbe8  jz      short loc_18002DC12
0x18002dbea  lea     rdx, aPrintverifieri; "PrintVerifierIsLayerEnabled"
0x18002dbf1  mov     rcx, rax; hModule
0x18002dbf4  call    cs:__imp_GetProcAddress
0x18002dbfa  test    rax, rax
0x18002dbfd  jz      short loc_18002DC12
0x18002dbff  mov     ecx, 2
0x18002dc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc09  jmp     short loc_18002DC14
0x18002dc0b  mov     cs:ghPrintVerifierModule, rdi
0x18002dc12  mov     eax, edi
0x18002dc14  mov     cs:gbPrintVerifierDriverLayerEnabled, eax
0x18002dc1a  mov     rcx, [rsp+248h+var_18]
0x18002dc22  xor     rcx, rsp; StackCookie
0x18002dc25  call    __security_check_cookie
0x18002dc2a  lea     r11, [rsp+248h+var_8]
0x18002dc32  mov     rbx, [r11+10h]
0x18002dc36  mov     rsi, [r11+18h]
0x18002dc3a  mov     rsp, r11
0x18002dc3d  pop     rdi
0x18002dc3e  retn
```
