# IISCryptoGenerateSessionKey

- ea: `0x1800063b4`
- end: `0x18000645a`
- name: `IISCryptoGenerateSessionKey`
- size: `166`
- prototype: `__int64 __fastcall(HCRYPTKEY *phKey, HCRYPTPROV hProv)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004f68`
- `0x180005988`

## callees

- `0x180004870`
- `0x1800063b4`
- `0x180007234`

## import_xrefs

- `ADVAPI32!CryptGenKey` at `0x1800063f8`
- `ADVAPI32!CryptGenKey` at `0x1800063f8`

## string_xrefs

- `0x18000642f`: `IISCryptoGenerateSessionKey.CryptGenKey (advapi32.dll) failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IISCryptoGenerateSessionKey(HCRYPTKEY *phKey, HCRYPTPROV hProv)
{
  unsigned int v4; // ebx
  int LastError; // eax

  if ( dword_18000FC34 )
  {
    v4 = 0;
    if ( !CryptGenKey(hProv, 0x6801u, 1u, phKey) )
    {
      LastError = IcpGetLastError();
      v4 = LastError;
      if ( LastError < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\key.cxx",
            0x149u,
            "IISCryptoGenerateSessionKey",
            "IISCryptoGenerateSessionKey.CryptGenKey (advapi32.dll) failed err=0x%x.\n",
            LastError);
        *phKey = 0;
      }
    }
    return v4;
  }
  else if ( hProv == 1984918096 )
  {
    *phKey = 1800627539;
    return 0;
  }
  else
  {
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800063b4  mov     [rsp+arg_0], rbx
0x1800063b9  push    rdi
0x1800063ba  sub     rsp, 30h
0x1800063be  cmp     cs:dword_18000FC34, 0
0x1800063c5  mov     rax, rdx
0x1800063c8  mov     rdi, rcx
0x1800063cb  jnz     short loc_1800063E7
0x1800063cd  cmp     rax, 764F7250h
0x1800063d3  jnz     short loc_1800063E0
0x1800063d5  mov     qword ptr [rcx], 6B536553h
0x1800063dc  xor     eax, eax
0x1800063de  jmp     short loc_18000644F
0x1800063e0  mov     eax, 80070057h
0x1800063e5  jmp     short loc_18000644F
0x1800063e7  xor     ebx, ebx
0x1800063e9  mov     r9, rdi; phKey
0x1800063ec  mov     edx, 6801h; Algid
0x1800063f1  mov     rcx, rax; hProv
0x1800063f4  lea     r8d, [rbx+1]; dwFlags
0x1800063f8  call    cs:__imp_CryptGenKey
0x1800063fe  test    eax, eax
0x180006400  jnz     short loc_18000644D
0x180006402  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180006407  mov     ebx, eax
0x180006409  test    eax, eax
0x18000640b  jns     short loc_18000644D
0x18000640d  test    byte ptr cs:g_dwDebugFlags, 3
0x180006414  jz      short loc_180006446
0x180006416  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000641d  lea     r9, aIiscryptogener_0; "IISCryptoGenerateSessionKey"
0x180006424  mov     dword ptr [rsp+38h+var_10], eax; char
0x180006428  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18000642f  lea     rax, aIiscryptogener; "IISCryptoGenerateSessionKey.CryptGenKey"...
0x180006436  mov     r8d, 149h; unsigned int
0x18000643c  mov     [rsp+38h+var_18], rax; char *
0x180006441  call    PuDbgPrint
0x180006446  mov     qword ptr [rdi], 0
0x18000644d  mov     eax, ebx
0x18000644f  mov     rbx, [rsp+38h+arg_0]
0x180006454  add     rsp, 30h
0x180006458  pop     rdi
0x180006459  retn
```
