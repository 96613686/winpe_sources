# IISAuthenticationEvents::AUTH_SUCCEEDED::TranslateEnumAuthTypeToString(IISAuthenticationEvents::AUTH_SUCCEEDED::enumAuthType)

- ea: `0x180001c30`
- end: `0x180001c86`
- name: `?TranslateEnumAuthTypeToString@AUTH_SUCCEEDED@IISAuthenticationEvents@@SAPEBGW4enumAuthType@12@@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019d0`

## callees

- `0x180001c30`

## pseudocode

```c
const wchar_t *__fastcall IISAuthenticationEvents::AUTH_SUCCEEDED::TranslateEnumAuthTypeToString(int a1)
{
  const wchar_t *result; // rax

  switch ( a1 )
  {
    case 1:
      result = L"Anonymous";
      break;
    case 2:
      result = L"Basic";
      break;
    case 4:
      result = L"NT";
      break;
    case 16:
      result = L"Digest";
      break;
    case 64:
      result = L"Passport";
      break;
    case 128:
      result = L"CertMap";
      break;
    default:
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180001c30  lea     eax, [rcx-1]; switch 128 cases
0x180001c33  cmp     eax, 7Fh
0x180001c36  ja      short def_180001C51; jumptable 0000000180001C51 default case, cases 3,5-15,17-63,65-127
0x180001c38  lea     rdx, __ImageBase
0x180001c3f  movzx   ecx, ds:(byte_180001CA4 - 180000000h)[rdx+rax]
0x180001c47  mov     eax, ds:(jpt_180001C51 - 180000000h)[rdx+rcx*4]
0x180001c4e  add     rax, rdx
0x180001c51  jmp     rax; switch jump
0x180001c53  lea     rax, aAnonymous; jumptable 0000000180001C51 case 1
0x180001c5a  retn
0x180001c5b  lea     rax, aBasic; jumptable 0000000180001C51 case 2
0x180001c62  retn
0x180001c63  lea     rax, aNt; jumptable 0000000180001C51 case 4
0x180001c6a  retn
0x180001c6b  lea     rax, aDigest; jumptable 0000000180001C51 case 16
0x180001c72  retn
0x180001c73  lea     rax, aPassport; jumptable 0000000180001C51 case 64
0x180001c7a  retn
0x180001c7b  lea     rax, aCertmap; jumptable 0000000180001C51 case 128
0x180001c82  retn
0x180001c83  xor     eax, eax; jumptable 0000000180001C51 default case, cases 3,5-15,17-63,65-127
0x180001c85  retn
```
