# VsmGetLinkedInterfaceProvider

- ea: `0x18001a554`
- end: `0x18001a614`
- name: `VsmGetLinkedInterfaceProvider`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a61c`

## callees

- `0x180005060`
- `0x18001a554`

## import_xrefs

- `bcryptPrimitives!GetAsymmetricEncryptionInterface` at `0x18001a5ec`
- `bcryptPrimitives!GetHashInterface` at `0x18001a5f5`
- `bcryptPrimitives!GetKeyEncapsulationInterface` at `0x18001a5bf`
- `bcryptPrimitives!GetCipherInterface` at `0x18001a601`
- `bcryptPrimitives!GetSignatureInterface` at `0x18001a5da`
- `bcryptPrimitives!GetKeyDerivationInterface` at `0x18001a5c8`
- `bcryptPrimitives!GetSecretAgreementInterface` at `0x18001a5e3`
- `bcryptPrimitives!GetRngInterface` at `0x18001a5d1`

## string_xrefs

- `0x18001a592`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall VsmGetLinkedInterfaceProvider(int a1, _QWORD *a2)
{
  unsigned int v2; // ebx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  __int64 v10; // rax

  v2 = 0;
  v3 = a1 - 1;
  if ( !v3 )
  {
    *a2 = GetCipherInterface;
    return v2;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v10 = GetHashInterface;
    goto LABEL_17;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v10 = GetAsymmetricEncryptionInterface;
    goto LABEL_17;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v10 = GetSecretAgreementInterface;
    goto LABEL_17;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v10 = GetSignatureInterface;
    goto LABEL_17;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v10 = GetRngInterface;
    goto LABEL_17;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v10 = GetKeyDerivationInterface;
    goto LABEL_17;
  }
  if ( v9 == 1 )
  {
    v10 = GetKeyEncapsulationInterface;
LABEL_17:
    *a2 = v10;
    return v2;
  }
  v2 = -1073741637;
  DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
  return v2;
}

```

## disassembly

```asm
0x18001a554  push    rbx
0x18001a556  sub     rsp, 20h
0x18001a55a  xor     ebx, ebx
0x18001a55c  sub     ecx, 1
0x18001a55f  jz      loc_18001A601
0x18001a565  sub     ecx, 1
0x18001a568  jz      loc_18001A5F5
0x18001a56e  sub     ecx, 1
0x18001a571  jz      short loc_18001A5EC
0x18001a573  sub     ecx, 1
0x18001a576  jz      short loc_18001A5E3
0x18001a578  sub     ecx, 1
0x18001a57b  jz      short loc_18001A5DA
0x18001a57d  sub     ecx, 1
0x18001a580  jz      short loc_18001A5D1
0x18001a582  sub     ecx, 1
0x18001a585  jz      short loc_18001A5C8
0x18001a587  sub     ecx, 1
0x18001a58a  jz      short loc_18001A5BF
0x18001a58c  cmp     ecx, 0FFFAh
0x18001a592  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a599  mov     ecx, 0C00000BBh
0x18001a59e  lea     rdx, aStatus; "Status"
0x18001a5a5  mov     ebx, 0C00000BBh
0x18001a5aa  mov     r9d, 8FBh
0x18001a5b0  jnz     short loc_18001A5B8
0x18001a5b2  mov     r9d, 8F6h
0x18001a5b8  call    DebugTraceError
0x18001a5bd  jmp     short loc_18001A60B
0x18001a5bf  mov     rax, cs:__imp_GetKeyEncapsulationInterface
0x18001a5c6  jmp     short loc_18001A5FC
0x18001a5c8  mov     rax, cs:__imp_GetKeyDerivationInterface
0x18001a5cf  jmp     short loc_18001A5FC
0x18001a5d1  mov     rax, cs:__imp_GetRngInterface
0x18001a5d8  jmp     short loc_18001A5FC
0x18001a5da  mov     rax, cs:__imp_GetSignatureInterface
0x18001a5e1  jmp     short loc_18001A5FC
0x18001a5e3  mov     rax, cs:__imp_GetSecretAgreementInterface
0x18001a5ea  jmp     short loc_18001A5FC
0x18001a5ec  mov     rax, cs:__imp_GetAsymmetricEncryptionInterface
0x18001a5f3  jmp     short loc_18001A5FC
0x18001a5f5  mov     rax, cs:__imp_GetHashInterface
0x18001a5fc  mov     [rdx], rax
0x18001a5ff  jmp     short loc_18001A60B
0x18001a601  mov     rcx, cs:__imp_GetCipherInterface
0x18001a608  mov     [rdx], rcx
0x18001a60b  mov     eax, ebx
0x18001a60d  add     rsp, 20h
0x18001a611  pop     rbx
0x18001a612  retn
```
