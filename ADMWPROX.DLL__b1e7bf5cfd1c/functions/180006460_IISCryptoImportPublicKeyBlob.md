# IISCryptoImportPublicKeyBlob

- ea: `0x180006460`
- end: `0x180006502`
- name: `IISCryptoImportPublicKeyBlob`
- size: `162`
- prototype: `__int64 __fastcall(HCRYPTKEY *phKey, __int64, HCRYPTPROV)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004f68`
- `0x180005988`

## callees

- `0x180004870`
- `0x180006460`
- `0x180007234`

## import_xrefs

- `ADVAPI32!CryptImportKey` at `0x1800064b0`
- `ADVAPI32!CryptImportKey` at `0x1800064b0`

## pseudocode

```c
__int64 __fastcall IISCryptoImportPublicKeyBlob(HCRYPTKEY *phKey, __int64 a2, HCRYPTPROV a3)
{
  unsigned int v4; // ebx
  unsigned int LastError; // eax

  if ( dword_18000FC34 )
  {
    v4 = 0;
    if ( !CryptImportKey(a3, (const BYTE *)(a2 + 16), *(_DWORD *)(a2 + 8), 0, 0, phKey) )
    {
      LastError = IcpGetLastError();
      v4 = LastError;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "inetsrv\\iis\\mb\\crypto\\key.cxx",
          0x5B2u,
          "IISCryptoImportPublicKeyBlob",
          "IISCryptoImportPublicKeyBlob.CryptImportKey failed err=0x%x.\n",
          LastError);
    }
    return v4;
  }
  else if ( a3 == 1984918096 && *(_DWORD *)a2 == 1648583497 )
  {
    *phKey = *(_QWORD *)(a2 + 8);
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
0x180006460  push    rbx
0x180006462  sub     rsp, 30h
0x180006466  cmp     cs:dword_18000FC34, 0
0x18000646d  mov     rax, r8
0x180006470  mov     r8, rdx
0x180006473  jnz     short loc_180006497
0x180006475  cmp     rax, 764F7250h
0x18000647b  jnz     short loc_180006490
0x18000647d  cmp     dword ptr [rdx], 62436349h
0x180006483  jnz     short loc_180006490
0x180006485  mov     rax, [rdx+8]
0x180006489  mov     [rcx], rax
0x18000648c  xor     eax, eax
0x18000648e  jmp     short loc_1800064FC
0x180006490  mov     eax, 80070057h
0x180006495  jmp     short loc_1800064FC
0x180006497  mov     r8d, [r8+8]; dwDataLen
0x18000649b  xor     ebx, ebx
0x18000649d  mov     [rsp+38h+phKey], rcx; phKey
0x1800064a2  add     rdx, 10h; pbData
0x1800064a6  mov     rcx, rax; hProv
0x1800064a9  mov     [rsp+38h+dwFlags], ebx; dwFlags
0x1800064ad  xor     r9d, r9d; hPubKey
0x1800064b0  call    cs:__imp_CryptImportKey
0x1800064b6  test    eax, eax
0x1800064b8  jnz     short loc_1800064FA
0x1800064ba  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x1800064bf  test    byte ptr cs:g_dwDebugFlags, 3
0x1800064c6  mov     ebx, eax
0x1800064c8  jz      short loc_1800064FA
0x1800064ca  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800064d1  lea     r9, aIiscryptoimpor; "IISCryptoImportPublicKeyBlob"
0x1800064d8  mov     dword ptr [rsp+38h+phKey], eax; char
0x1800064dc  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x1800064e3  lea     rax, aIiscryptoimpor_0; "IISCryptoImportPublicKeyBlob.CryptImpor"...
0x1800064ea  mov     r8d, 5B2h; unsigned int
0x1800064f0  mov     qword ptr [rsp+38h+dwFlags], rax; char *
0x1800064f5  call    PuDbgPrint
0x1800064fa  mov     eax, ebx
0x1800064fc  add     rsp, 30h
0x180006500  pop     rbx
0x180006501  retn
```
