# BaseSrvImportApis

- ea: `0x18000b524`
- end: `0x18000b609`
- name: `BaseSrvImportApis`
- size: `229`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a3b0`

## callees

- `0x18000b524`

## import_xrefs

- `ntdll!RtlInitString` at `0x18000b5b0`
- `ntdll!RtlInitString` at `0x18000b5b0`
- `ntdll!LdrGetProcedureAddress` at `0x18000b5cd`
- `ntdll!LdrGetProcedureAddress` at `0x18000b5cd`
- `ntdll!LdrLoadDll` at `0x18000b584`
- `ntdll!LdrLoadDll` at `0x18000b584`
- `ntdll!RtlInitUnicodeString` at `0x18000b56a`
- `ntdll!RtlInitUnicodeString` at `0x18000b56a`

## pseudocode

```c
NTSTATUS BaseSrvImportApis()
{
  wchar_t **v0; // rbx
  int v1; // edi
  NTSTATUS result; // eax
  unsigned int v3; // esi
  wchar_t *v4; // r14
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  struct _STRING Name; // [rsp+30h] [rbp-18h] BYREF
  PVOID BaseAddress; // [rsp+50h] [rbp+8h] BYREF

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
0x18000b524  mov     rax, rsp
0x18000b527  mov     [rax+10h], rbx
0x18000b52b  mov     [rax+18h], rsi
0x18000b52f  mov     [rax+20h], rdi
0x18000b533  mov     [rax+8], rcx
0x18000b537  push    r14
0x18000b539  sub     rsp, 40h
0x18000b53d  and     qword ptr [rax+8], 0
0x18000b542  lea     rbx, rgBaseSrvModuleImport
0x18000b549  xorps   xmm0, xmm0
0x18000b54c  xorps   xmm1, xmm1
0x18000b54f  movups  xmmword ptr [rax-18h], xmm0
0x18000b553  xor     edi, edi
0x18000b555  movups  xmmword ptr [rax-28h], xmm1
0x18000b559  cmp     edi, 1
0x18000b55c  jnb     loc_18000B5F0
0x18000b562  mov     rdx, [rbx]; SourceString
0x18000b565  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18000b56a  call    cs:__imp_RtlInitUnicodeString
0x18000b571  nop     dword ptr [rax+rax+00h]
0x18000b576  lea     r9, [rsp+48h+BaseAddress]; BaseAddress
0x18000b57b  xor     edx, edx; LoadFlags
0x18000b57d  lea     r8, [rsp+48h+DestinationString]; Name
0x18000b582  xor     ecx, ecx; SearchPath
0x18000b584  call    cs:__imp_LdrLoadDll
0x18000b58b  nop     dword ptr [rax+rax+00h]
0x18000b590  test    eax, eax
0x18000b592  js      short loc_18000B5F2
0x18000b594  mov     rax, [rsp+48h+BaseAddress]
0x18000b599  xor     esi, esi
0x18000b59b  mov     r14, [rbx+8]
0x18000b59f  mov     [rbx+18h], rax
0x18000b5a3  cmp     esi, [rbx+10h]
0x18000b5a6  jnb     short loc_18000B5E5
0x18000b5a8  mov     rdx, [r14]; SourceString
0x18000b5ab  lea     rcx, [rsp+48h+Name]; DestinationString
0x18000b5b0  call    cs:__imp_RtlInitString
0x18000b5b7  nop     dword ptr [rax+rax+00h]
0x18000b5bc  mov     r9, [r14+8]; ProcedureAddress
0x18000b5c0  lea     rdx, [rsp+48h+Name]; Name
0x18000b5c5  mov     rcx, [rsp+48h+BaseAddress]; BaseAddress
0x18000b5ca  xor     r8d, r8d; Ordinal
0x18000b5cd  call    cs:__imp_LdrGetProcedureAddress
0x18000b5d4  nop     dword ptr [rax+rax+00h]
0x18000b5d9  test    eax, eax
0x18000b5db  js      short loc_18000B5F2
0x18000b5dd  inc     esi
0x18000b5df  add     r14, 10h
0x18000b5e3  jmp     short loc_18000B5A3
0x18000b5e5  inc     edi
0x18000b5e7  add     rbx, 20h ; ' '
0x18000b5eb  jmp     loc_18000B559
0x18000b5f0  xor     eax, eax
0x18000b5f2  mov     rbx, [rsp+48h+arg_8]
0x18000b5f7  mov     rsi, [rsp+48h+arg_10]
0x18000b5fc  mov     rdi, [rsp+48h+arg_18]
0x18000b601  add     rsp, 40h
0x18000b605  pop     r14
0x18000b607  retn
```
