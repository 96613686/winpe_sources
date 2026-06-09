# Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)

- ea: `0x1400192a0`
- end: `0x1400193c5`
- name: `?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z`
- size: `293`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018bc4`

## callees

- `0x140002310`
- `0x14000d338`
- `0x14000f1ac`
- `0x14000f278`
- `0x1400192a0`
- `0x14001a9a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400192e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400192e9`

## string_xrefs

- `0x140019359`: `onecore\vm\common\vml\VmRegistry.h`
- `0x1400193ad`: `onecore\vm\common\vml\VmRegistry.h`
- `0x140019394`: `Registry type mismatch - expected = %u, actual = %u`

## pseudocode

```c
__int64 __fastcall Vml::VmRegistryKey::QueryValue(HKEY *this, const unsigned __int16 *a2, BYTE *a3)
{
  HKEY v3; // rcx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  void *v7; // rdx
  __int64 v8; // r8
  unsigned int v10; // [rsp+20h] [rbp-28h]
  DWORD v11; // [rsp+30h] [rbp-18h] BYREF
  DWORD v12; // [rsp+34h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = *this;
  v12 = 4;
  v5 = 0;
  v11 = 0;
  v6 = RegQueryValueExW(v3, L"ProcessShutdownTimeoutSeconds", 0, &v11, a3, &v12);
  if ( v6 == 2 )
  {
    v12 = 0;
LABEL_8:
    if ( v12 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16388) )
        VmlDebugTrace(16388, L"Unexpected error - DWORD value larger than 4 bytes");
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2FC,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)0x7A,
        v10);
    }
    return v5;
  }
  if ( v6 == 234 )
    goto LABEL_8;
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(retaddr, v7, v8, (const char *)v6, v10);
  if ( v11 != 4 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16388) )
      VmlDebugTrace(16388, L"Registry type mismatch - expected = %u, actual = %u", 4, v11);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x48F,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)0x65D,
      v10);
  }
  LOBYTE(v5) = a3 != 0;
  if ( !a3 )
    goto LABEL_8;
  return v5;
}

```

## disassembly

```asm
0x1400192a0  mov     r11, rsp
0x1400192a3  mov     [r11+10h], rbx
0x1400192a7  push    rdi
0x1400192a8  sub     rsp, 40h
0x1400192ac  mov     rax, cs:__security_cookie
0x1400192b3  xor     rax, rsp
0x1400192b6  mov     [rsp+48h+var_10], rax
0x1400192bb  mov     rcx, [rcx]; hKey
0x1400192be  lea     rax, [r11-14h]
0x1400192c2  mov     [r11-20h], rax
0x1400192c6  lea     r9, [r11-18h]; lpType
0x1400192ca  mov     [r11-28h], r8
0x1400192ce  lea     rdx, ValueName; "ProcessShutdownTimeoutSeconds"
0x1400192d5  mov     rdi, r8
0x1400192d8  mov     [rsp+48h+var_14], 4
0x1400192e0  xor     ebx, ebx
0x1400192e2  xor     r8d, r8d; lpReserved
0x1400192e5  mov     [rsp+48h+var_18], ebx
0x1400192e9  call    cs:__imp_RegQueryValueExW
0x1400192ef  cmp     eax, 2
0x1400192f2  jz      short loc_14001932B
0x1400192f4  cmp     eax, 0EAh
0x1400192f9  jz      short loc_14001932F
0x1400192fb  test    eax, eax
0x1400192fd  jnz     short loc_140019371
0x1400192ff  cmp     [rsp+48h+var_18], 4
0x140019304  jnz     short loc_14001937F
0x140019306  test    rdi, rdi
0x140019309  setnz   bl
0x14001930c  test    rdi, rdi
0x14001930f  jz      short loc_14001932F
0x140019311  mov     eax, ebx
0x140019313  mov     rcx, [rsp+48h+var_10]
0x140019318  xor     rcx, rsp; StackCookie
0x14001931b  call    __security_check_cookie
0x140019320  mov     rbx, [rsp+48h+arg_8]
0x140019325  add     rsp, 40h
0x140019329  pop     rdi
0x14001932a  retn
0x14001932b  mov     [rsp+48h+var_14], ebx
0x14001932f  cmp     [rsp+48h+var_14], 0
0x140019334  jz      short loc_140019311
0x140019336  mov     ebx, 4004h
0x14001933b  mov     ecx, ebx
0x14001933d  call    VmlIsDebugTraceEnabled
0x140019342  test    eax, eax
0x140019344  jz      short loc_140019354
0x140019346  lea     rdx, aUnexpectedErro; "Unexpected error - DWORD value larger t"...
0x14001934d  mov     ecx, ebx
0x14001934f  call    VmlDebugTrace
0x140019354  mov     rcx, [rsp+48h]; this
0x140019359  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140019360  mov     r9d, 7Ah ; 'z'; char *
0x140019366  mov     edx, 2FCh; void *
0x14001936b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140019371  mov     rcx, [rsp+48h]; this
0x140019376  mov     r9d, eax; char *
0x140019379  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14001937f  mov     ebx, 4004h
0x140019384  mov     ecx, ebx
0x140019386  call    VmlIsDebugTraceEnabled
0x14001938b  test    eax, eax
0x14001938d  jz      short loc_1400193A8
0x14001938f  mov     r9d, [rsp+48h+var_18]
0x140019394  lea     rdx, aRegistryTypeMi; "Registry type mismatch - expected = %u,"...
0x14001939b  mov     r8d, 4
0x1400193a1  mov     ecx, ebx
0x1400193a3  call    VmlDebugTrace
0x1400193a8  mov     rcx, [rsp+48h]; this
0x1400193ad  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1400193b4  mov     r9d, 65Dh; char *
0x1400193ba  mov     edx, 48Fh; void *
0x1400193bf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
