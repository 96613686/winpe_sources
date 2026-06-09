# EnumModules(void *,int (*)(void *,_MODULE_INFO *),void *)

- ea: `0x18002dee0`
- end: `0x18002e152`
- name: `?EnumModules@@YAHPEAXP6AH0PEAU_MODULE_INFO@@@Z0@Z`
- size: `626`
- prototype: `__int64 __fastcall(HANDLE hProcess, int (*)(void *, struct _MODULE_INFO *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002e194`

## callees

- `0x18002dee0`
- `0x18002e158`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18002e082`
- `msvcrt!sprintf_s` at `0x18002e0dc`
- `msvcrt!sprintf_s` at `0x18002e082`
- `msvcrt!sprintf_s` at `0x18002e0dc`
- `ntdll!NtQueryInformationProcess` at `0x18002df77`
- `ntdll!NtQueryInformationProcess` at `0x18002df77`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002dfb1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002dfdf`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002e01c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002e051`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002e0af`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002dfb1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002dfdf`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002e01c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002e051`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002e0af`

## pseudocode

```c
__int64 __fastcall EnumModules(HANDLE hProcess, int (*a2)(void *, struct _MODULE_INFO *), void *a3)
{
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v8; // [rsp+30h] [rbp-D0h] BYREF
  __int64 Buffer; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v12; // [rsp+80h] [rbp-80h]
  __int64 v13; // [rsp+A0h] [rbp-60h]
  __int64 v14; // [rsp+A8h] [rbp-58h]
  int v15; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v16; // [rsp+BAh] [rbp-46h]
  LPCVOID v17; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v18; // [rsp+CAh] [rbp-36h]
  LPCVOID lpBaseAddress; // [rsp+D0h] [rbp-30h]
  _QWORD v20[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v21; // [rsp+1C0h] [rbp+C0h]
  char v22[260]; // [rsp+1C4h] [rbp+C4h] BYREF
  char v23[264]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v24[518]; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int16 v25; // [rsp+5D6h] [rbp+4D6h]

  Buffer = 0;
  v8 = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(v11, 0, 0x138u);
  memset_0(v20, 0, 0x220u);
  if ( NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0) < 0 )
    return 0;
  if ( !*((_QWORD *)&ProcessInformation[0] + 1) )
    return 0;
  if ( !ReadProcessMemory(hProcess, (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 24LL), &Buffer, 8u, 0) )
    return 0;
  v5 = Buffer + 32;
  if ( !ReadProcessMemory(hProcess, (LPCVOID)(Buffer + 32), &v8, 8u, 0) )
    return 0;
  v6 = v8;
  while ( v6 != v5 )
  {
    if ( !ReadProcessMemory(hProcess, (LPCVOID)(v6 - 16), v11, 0x138u, 0) )
      return 0;
    if ( v18 > 0x208u )
      return 0;
    if ( !ReadProcessMemory(hProcess, lpBaseAddress, v24, v18, 0) )
      return 0;
    v25 = 0;
    sprintf_s(v22, 0x104u, "%ws", v24);
    if ( v16 > 0x208u || !ReadProcessMemory(hProcess, v17, v24, v16, 0) )
      return 0;
    v25 = 0;
    sprintf_s(v23, 0x104u, "%ws", v24);
    v20[0] = v13;
    v20[1] = v14;
    v21 = v15;
    if ( !(unsigned int)EnumModulesCallback(a3, (struct _MODULE_INFO *)v20) )
      break;
    v6 = v12;
    v8 = v12;
  }
  return 1;
}

```

## disassembly

```asm
0x18002dee0  mov     [rsp-8+arg_8], rbx
0x18002dee5  mov     [rsp-8+arg_18], rsi
0x18002deea  push    rbp
0x18002deeb  push    rdi
0x18002deec  push    r15
0x18002deee  lea     rbp, [rsp-4F0h]
0x18002def6  sub     rsp, 5F0h
0x18002defd  mov     rax, cs:__security_cookie
0x18002df04  xor     rax, rsp
0x18002df07  mov     [rbp+500h+var_20], rax
0x18002df0e  xorps   xmm0, xmm0
0x18002df11  mov     [rsp+600h+Buffer], 0
0x18002df1a  mov     rsi, r8
0x18002df1d  mov     [rsp+600h+var_5D0], 0
0x18002df26  mov     rbx, rcx
0x18002df29  mov     r8d, 138h; Size
0x18002df2f  lea     rcx, [rsp+600h+var_590]; void *
0x18002df34  xor     edx, edx; Val
0x18002df36  movups  [rsp+600h+ProcessInformation], xmm0
0x18002df3b  movups  [rsp+600h+var_5B0], xmm0
0x18002df40  movups  [rsp+600h+var_5A0], xmm0
0x18002df45  call    memset_0
0x18002df4a  xor     edx, edx; Val
0x18002df4c  lea     rcx, [rbp+500h+var_450]; void *
0x18002df53  mov     r8d, 220h; Size
0x18002df59  call    memset_0
0x18002df5e  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18002df64  mov     [rsp+600h+ReturnLength], 0; ReturnLength
0x18002df6d  lea     r8, [rsp+600h+ProcessInformation]; ProcessInformation
0x18002df72  xor     edx, edx; ProcessInformationClass
0x18002df74  mov     rcx, rbx; ProcessHandle
0x18002df77  call    cs:__imp_NtQueryInformationProcess
0x18002df7d  test    eax, eax
0x18002df7f  js      loc_18002E129
0x18002df85  mov     rdx, qword ptr [rsp+600h+ProcessInformation+8]
0x18002df8a  test    rdx, rdx
0x18002df8d  jz      loc_18002E129
0x18002df93  mov     r15d, 8
0x18002df99  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x18002dfa2  mov     r9d, r15d; nSize
0x18002dfa5  lea     r8, [rsp+600h+Buffer]; lpBuffer
0x18002dfaa  add     rdx, 18h; lpBaseAddress
0x18002dfae  mov     rcx, rbx; hProcess
0x18002dfb1  call    cs:__imp_ReadProcessMemory
0x18002dfb7  test    eax, eax
0x18002dfb9  jz      loc_18002E129
0x18002dfbf  mov     rdi, [rsp+600h+Buffer]
0x18002dfc4  lea     r8, [rsp+600h+var_5D0]; lpBuffer
0x18002dfc9  add     rdi, 20h ; ' '
0x18002dfcd  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x18002dfd6  mov     rdx, rdi; lpBaseAddress
0x18002dfd9  mov     r9d, r15d; nSize
0x18002dfdc  mov     rcx, rbx; hProcess
0x18002dfdf  call    cs:__imp_ReadProcessMemory
0x18002dfe5  test    eax, eax
0x18002dfe7  jz      loc_18002E129
0x18002dfed  mov     rax, [rsp+600h+var_5D0]
0x18002dff2  mov     r15d, 208h
0x18002dff8  cmp     rax, rdi
0x18002dffb  jz      loc_18002E122
0x18002e001  lea     rdx, [rax-10h]; lpBaseAddress
0x18002e005  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x18002e00e  mov     r9d, 138h; nSize
0x18002e014  lea     r8, [rsp+600h+var_590]; lpBuffer
0x18002e019  mov     rcx, rbx; hProcess
0x18002e01c  call    cs:__imp_ReadProcessMemory
0x18002e022  test    eax, eax
0x18002e024  jz      loc_18002E129
0x18002e02a  cmp     [rbp+500h+var_536], r15w
0x18002e02f  ja      loc_18002E129
0x18002e035  movzx   r9d, [rbp+500h+var_536]; nSize
0x18002e03a  lea     r8, [rbp+500h+var_230]; lpBuffer
0x18002e041  mov     rdx, [rbp+500h+lpBaseAddress]; lpBaseAddress
0x18002e045  mov     rcx, rbx; hProcess
0x18002e048  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x18002e051  call    cs:__imp_ReadProcessMemory
0x18002e057  test    eax, eax
0x18002e059  jz      loc_18002E129
0x18002e05f  xor     eax, eax
0x18002e061  lea     r9, [rbp+500h+var_230]
0x18002e068  lea     r8, Format; "%ws"
0x18002e06f  mov     [rbp+500h+var_2A], ax
0x18002e076  mov     edx, 104h; BufferCount
0x18002e07b  lea     rcx, [rbp+500h+var_43C]; Buffer
0x18002e082  call    cs:__imp_sprintf_s
0x18002e088  cmp     [rbp+500h+var_546], r15w
0x18002e08d  ja      loc_18002E129
0x18002e093  movzx   r9d, [rbp+500h+var_546]; nSize
0x18002e098  lea     r8, [rbp+500h+var_230]; lpBuffer
0x18002e09f  mov     rdx, [rbp+500h+var_540]; lpBaseAddress
0x18002e0a3  mov     rcx, rbx; hProcess
0x18002e0a6  mov     [rsp+600h+ReturnLength], 0; lpNumberOfBytesRead
0x18002e0af  call    cs:__imp_ReadProcessMemory
0x18002e0b5  test    eax, eax
0x18002e0b7  jz      short loc_18002E129
0x18002e0b9  xor     eax, eax
0x18002e0bb  lea     r9, [rbp+500h+var_230]
0x18002e0c2  lea     r8, Format; "%ws"
0x18002e0c9  mov     [rbp+500h+var_2A], ax
0x18002e0d0  mov     edx, 104h; BufferCount
0x18002e0d5  lea     rcx, [rbp+500h+var_338]; Buffer
0x18002e0dc  call    cs:__imp_sprintf_s
0x18002e0e2  mov     rax, [rbp+500h+var_560]
0x18002e0e6  lea     rdx, [rbp+500h+var_450]; struct _MODULE_INFO *
0x18002e0ed  mov     [rbp+500h+var_450], rax
0x18002e0f4  mov     rcx, rsi; void *
0x18002e0f7  mov     rax, [rbp+500h+var_558]
0x18002e0fb  mov     [rbp+500h+var_448], rax
0x18002e102  mov     eax, [rbp+500h+var_550]
0x18002e105  mov     [rbp+500h+var_440], eax
0x18002e10b  call    ?EnumModulesCallback@@YAHPEAXPEAU_MODULE_INFO@@@Z; EnumModulesCallback(void *,_MODULE_INFO *)
0x18002e110  test    eax, eax
0x18002e112  jz      short loc_18002E122
0x18002e114  mov     rax, [rbp+500h+var_580]
0x18002e118  mov     [rsp+600h+var_5D0], rax
0x18002e11d  jmp     loc_18002DFF8
0x18002e122  mov     eax, 1
0x18002e127  jmp     short loc_18002E12B
0x18002e129  xor     eax, eax
0x18002e12b  mov     rcx, [rbp+500h+var_20]
0x18002e132  xor     rcx, rsp; StackCookie
0x18002e135  call    __security_check_cookie
0x18002e13a  lea     r11, [rsp+600h+var_10]
0x18002e142  mov     rbx, [r11+28h]
0x18002e146  mov     rsi, [r11+38h]
0x18002e14a  mov     rsp, r11
0x18002e14d  pop     r15
0x18002e14f  pop     rdi
0x18002e150  pop     rbp
0x18002e151  retn
```
