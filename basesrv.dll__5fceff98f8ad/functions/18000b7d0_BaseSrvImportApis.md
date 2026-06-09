# BaseSrvImportApis

- ea: `0x18000b7d0`
- end: `0x18000b8a3`
- name: `BaseSrvImportApis`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a640`

## callees

- `0x18000b7d0`

## import_xrefs

- `ntdll!RtlInitString` at `0x18000b856`
- `ntdll!RtlInitString` at `0x18000b856`
- `ntdll!LdrGetProcedureAddress` at `0x18000b873`
- `ntdll!LdrGetProcedureAddress` at `0x18000b873`
- `ntdll!LdrLoadDll` at `0x18000b82a`
- `ntdll!LdrLoadDll` at `0x18000b82a`
- `ntdll!RtlInitUnicodeString` at `0x18000b810`
- `ntdll!RtlInitUnicodeString` at `0x18000b810`

## pseudocode

```c
NTSTATUS BaseSrvImportApis()
{
  wchar_t **v0; // rbx
  int v1; // edi
  NTSTATUS result; // eax
  unsigned int v3; // esi
  wchar_t *v4; // r14
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _STRING Name; // [rsp+30h] [rbp-38h] BYREF
  PVOID BaseAddress; // [rsp+70h] [rbp+8h] BYREF

  BaseAddress = 0;
  v0 = &rgBaseSrvModuleImport;
  Name = 0;
  v1 = 0;
  DestinationString = 0;
  while ( !v1 )
  {
    RtlInitUnicodeString(&DestinationString, *v0);
    result = LdrLoadDll(0, 0, &DestinationString, &BaseAddress);
    if ( result < 0 )
      return result;
    v3 = 0;
    v4 = v0[1];
    v0[3] = (wchar_t *)BaseAddress;
    while ( v3 < *((_DWORD *)v0 + 4) )
    {
      RtlInitString(&Name, *(PCSZ *)v4);
      result = LdrGetProcedureAddress(BaseAddress, &Name, 0, *((PVOID **)v4 + 1));
      if ( result < 0 )
        return result;
      ++v3;
      v4 += 8;
    }
    v1 = 1;
    v0 += 4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b7d0  mov     rax, rsp
0x18000b7d3  mov     [rax+8], rcx
0x18000b7d7  push    rbx
0x18000b7d8  push    rsi
0x18000b7d9  push    rdi
0x18000b7da  push    r14
0x18000b7dc  sub     rsp, 48h
0x18000b7e0  xorps   xmm0, xmm0
0x18000b7e3  mov     qword ptr [rax+8], 0
0x18000b7eb  xorps   xmm1, xmm1
0x18000b7ee  lea     rbx, rgBaseSrvModuleImport
0x18000b7f5  movups  xmmword ptr [rax-38h], xmm0
0x18000b7f9  xor     edi, edi
0x18000b7fb  movups  xmmword ptr [rax-48h], xmm1
0x18000b7ff  cmp     edi, 1
0x18000b802  jnb     loc_18000B896
0x18000b808  mov     rdx, [rbx]; SourceString
0x18000b80b  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18000b810  call    cs:__imp_RtlInitUnicodeString
0x18000b817  nop     dword ptr [rax+rax+00h]
0x18000b81c  lea     r9, [rsp+68h+BaseAddress]; BaseAddress
0x18000b821  xor     edx, edx; LoadFlags
0x18000b823  lea     r8, [rsp+68h+DestinationString]; Name
0x18000b828  xor     ecx, ecx; SearchPath
0x18000b82a  call    cs:__imp_LdrLoadDll
0x18000b831  nop     dword ptr [rax+rax+00h]
0x18000b836  test    eax, eax
0x18000b838  js      short loc_18000B898
0x18000b83a  mov     rax, [rsp+68h+BaseAddress]
0x18000b83f  xor     esi, esi
0x18000b841  mov     r14, [rbx+8]
0x18000b845  mov     [rbx+18h], rax
0x18000b849  cmp     esi, [rbx+10h]
0x18000b84c  jnb     short loc_18000B88B
0x18000b84e  mov     rdx, [r14]; SourceString
0x18000b851  lea     rcx, [rsp+68h+Name]; DestinationString
0x18000b856  call    cs:__imp_RtlInitString
0x18000b85d  nop     dword ptr [rax+rax+00h]
0x18000b862  mov     r9, [r14+8]; ProcedureAddress
0x18000b866  lea     rdx, [rsp+68h+Name]; Name
0x18000b86b  mov     rcx, [rsp+68h+BaseAddress]; BaseAddress
0x18000b870  xor     r8d, r8d; Ordinal
0x18000b873  call    cs:__imp_LdrGetProcedureAddress
0x18000b87a  nop     dword ptr [rax+rax+00h]
0x18000b87f  test    eax, eax
0x18000b881  js      short loc_18000B898
0x18000b883  inc     esi
0x18000b885  add     r14, 10h
0x18000b889  jmp     short loc_18000B849
0x18000b88b  inc     edi
0x18000b88d  add     rbx, 20h ; ' '
0x18000b891  jmp     loc_18000B7FF
0x18000b896  xor     eax, eax
0x18000b898  add     rsp, 48h
0x18000b89c  pop     r14
0x18000b89e  pop     rdi
0x18000b89f  pop     rsi
0x18000b8a0  pop     rbx
0x18000b8a1  retn
```
