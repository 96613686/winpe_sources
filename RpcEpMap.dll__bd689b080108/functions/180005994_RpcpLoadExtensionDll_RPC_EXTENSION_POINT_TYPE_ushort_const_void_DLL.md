# RpcpLoadExtensionDll(RPC_EXTENSION_POINT_TYPE,ushort const *,void *,DLL * *)

- ea: `0x180005994`
- end: `0x180005ad6`
- name: `?RpcpLoadExtensionDll@@YAJW4RPC_EXTENSION_POINT_TYPE@@PEBGPEAXPEAPEAVDLL@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, HMODULE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800058d8`

## callees

- `0x180005994`
- `0x180005f48`
- `0x18000a750`
- `0x18000a778`
- `0x18000a8b4`
- `0x18000a980`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a80`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005a06`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005a06`

## string_xrefs

- `0x1800059df`: `Software\Microsoft\Rpc\Extensions`
- `0x180005a79`: `I_RpcExtInitializeExtensionPoint`

## pseudocode

```c
__int64 __fastcall RpcpLoadExtensionDll(__int64 a1, const WCHAR *a2, __int64 a3, HMODULE **a4)
{
  LSTATUS ValueW; // eax
  unsigned int v8; // ebx
  DLL *v9; // rax
  __int64 v10; // r8
  HMODULE *v11; // rax
  HMODULE *v12; // rdi
  FARPROC ProcAddress; // rax
  int v15; // [rsp+40h] [rbp-258h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-254h] BYREF
  unsigned __int16 pvData[264]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(pvData, 0, 0x208u);
  pcbData[0] = 520;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc\\Extensions", a2, 2u, 0, pvData, pcbData);
  if ( !ValueW )
  {
    if ( !pvData[0] )
      return 1764;
    v15 = 0;
    v9 = (DLL *)operator new(8u);
    if ( !v9 )
      return 14;
    v11 = (HMODULE *)DLL::DLL(v9, pvData, v10, &v15);
    v12 = v11;
    if ( !v11 )
      return 14;
    v8 = v15;
    if ( v15 != 87 )
    {
      if ( v15 )
      {
LABEL_16:
        DLL::`scalar deleting destructor'(v12);
        return v8;
      }
      if ( *v11 )
      {
        ProcAddress = GetProcAddress(*v11, "I_RpcExtInitializeExtensionPoint");
        if ( ProcAddress )
        {
          if ( !((unsigned int (__fastcall *)(__int64, __int64))ProcAddress)(4, a3) )
          {
            *a4 = v12;
            return 0;
          }
        }
      }
    }
    v8 = 1764;
    goto LABEL_16;
  }
  v8 = 1764;
  if ( ValueW != 2 )
    return 14;
  return v8;
}

```

## disassembly

```asm
0x180005994  push    rbx
0x180005996  push    rbp
0x180005997  push    rsi
0x180005998  push    rdi
0x180005999  push    r14
0x18000599b  sub     rsp, 270h
0x1800059a2  mov     rax, cs:__security_cookie
0x1800059a9  xor     rax, rsp
0x1800059ac  mov     [rsp+298h+var_38], rax
0x1800059b4  mov     rbp, r8
0x1800059b7  lea     rcx, [rsp+298h+var_248]; void *
0x1800059bc  mov     rbx, rdx
0x1800059bf  mov     edi, 208h
0x1800059c4  mov     r8d, edi; Size
0x1800059c7  xor     edx, edx; Val
0x1800059c9  mov     rsi, r9
0x1800059cc  call    memset_0
0x1800059d1  lea     rax, [rsp+298h+var_254]
0x1800059d6  mov     [rsp+298h+var_254], edi
0x1800059da  mov     [rsp+298h+pcbData], rax; pcbData
0x1800059df  lea     rdx, SubKey; "Software\\Microsoft\\Rpc\\Extensions"
0x1800059e6  xor     r14d, r14d
0x1800059e9  lea     rax, [rsp+298h+var_248]
0x1800059ee  mov     [rsp+298h+pvData], rax; pvData
0x1800059f3  mov     r8, rbx; lpValue
0x1800059f6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800059fd  mov     [rsp+298h+pdwType], r14; pdwType
0x180005a02  lea     r9d, [r14+2]; dwFlags
0x180005a06  call    cs:__imp_RegGetValueW
0x180005a0c  test    eax, eax
0x180005a0e  jz      short loc_180005A24
0x180005a10  cmp     eax, 2
0x180005a13  lea     ecx, [r14+0Eh]
0x180005a17  mov     ebx, 6E4h
0x180005a1c  cmovnz  ebx, ecx
0x180005a1f  jmp     loc_180005AB6
0x180005a24  cmp     [rsp+298h+var_248], r14w
0x180005a2a  jnz     short loc_180005A36
0x180005a2c  mov     ebx, 6E4h
0x180005a31  jmp     loc_180005AB6
0x180005a36  mov     ecx, 8; unsigned __int64
0x180005a3b  mov     [rsp+298h+var_258], r14d
0x180005a40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005a45  test    rax, rax
0x180005a48  jz      short loc_180005AB1
0x180005a4a  lea     r9, [rsp+298h+var_258]; int *
0x180005a4f  mov     rcx, rax; this
0x180005a52  lea     rdx, [rsp+298h+var_248]; unsigned __int16 *
0x180005a57  call    ??0DLL@@QEAA@PEAGKPEAJ@Z; DLL::DLL(ushort *,ulong,long *)
0x180005a5c  mov     rdi, rax
0x180005a5f  test    rax, rax
0x180005a62  jz      short loc_180005AB1
0x180005a64  mov     ebx, [rsp+298h+var_258]
0x180005a68  cmp     ebx, 57h ; 'W'
0x180005a6b  jz      short loc_180005AA2
0x180005a6d  test    ebx, ebx
0x180005a6f  jnz     short loc_180005AA7
0x180005a71  mov     rcx, [rax]; hModule
0x180005a74  test    rcx, rcx
0x180005a77  jz      short loc_180005AA2
0x180005a79  lea     rdx, ProcName; "I_RpcExtInitializeExtensionPoint"
0x180005a80  call    cs:__imp_GetProcAddress
0x180005a86  test    rax, rax
0x180005a89  jz      short loc_180005AA2
0x180005a8b  mov     rdx, rbp
0x180005a8e  lea     ecx, [rbx+4]
0x180005a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a96  test    eax, eax
0x180005a98  jnz     short loc_180005AA2
0x180005a9a  mov     [rsi], rdi
0x180005a9d  mov     ebx, r14d
0x180005aa0  jmp     short loc_180005AB6
0x180005aa2  mov     ebx, 6E4h
0x180005aa7  mov     rcx, rdi; this
0x180005aaa  call    ??_GDLL@@QEAAPEAXI@Z; DLL::`scalar deleting destructor'(uint)
0x180005aaf  jmp     short loc_180005AB6
0x180005ab1  mov     ebx, 0Eh
0x180005ab6  mov     eax, ebx
0x180005ab8  mov     rcx, [rsp+298h+var_38]
0x180005ac0  xor     rcx, rsp; StackCookie
0x180005ac3  call    __security_check_cookie
0x180005ac8  add     rsp, 270h
0x180005acf  pop     r14
0x180005ad1  pop     rdi
0x180005ad2  pop     rsi
0x180005ad3  pop     rbp
0x180005ad4  pop     rbx
0x180005ad5  retn
```
