# AiInitializeSoftwarePathMacroList

- ea: `0x180004ca0`
- end: `0x180004ddd`
- name: `AiInitializeSoftwarePathMacroList`
- size: `317`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800028d0`
- `0x1800061c8`

## callees

- `0x180004ca0`
- `0x180004de4`
- `0x1800051fc`
- `0x18000879c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004ccb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004ccb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004da3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004da3`
- `ntdll!RtlFreeHeap` at `0x180004dc9`
- `ntdll!RtlFreeHeap` at `0x180004dc9`
- `ntdll!RtlInitUnicodeString` at `0x180004d16`
- `ntdll!RtlInitUnicodeString` at `0x180004d25`
- `ntdll!RtlInitUnicodeString` at `0x180004d54`
- `ntdll!RtlInitUnicodeString` at `0x180004d16`
- `ntdll!RtlInitUnicodeString` at `0x180004d25`
- `ntdll!RtlInitUnicodeString` at `0x180004d54`

## pseudocode

```c
__int64 AiInitializeSoftwarePathMacroList()
{
  int v0; // ebx
  unsigned int v1; // esi
  __int64 v2; // rdi
  __int64 v3; // rcx
  int v4; // eax
  PVOID P[2]; // [rsp+20h] [rbp-40h] BYREF
  struct _UNICODE_STRING v7; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v9; // [rsp+50h] [rbp-10h] BYREF

  v9 = 0;
  DestinationString = 0;
  v7 = 0;
  *(_OWORD *)P = 0;
  RtlAcquireSRWLockExclusive(&qword_180010830);
  if ( AipPathMacroList )
  {
    v0 = 0;
    goto LABEL_13;
  }
  v1 = 0;
  while ( 1 )
  {
    v2 = 4LL * v1;
    if ( !LODWORD(AipRegistryPathMacros[v2 + 3]) && (!HIDWORD(AipRegistryPathMacros[v2 + 3]) || dword_180010804) )
      break;
LABEL_10:
    if ( ++v1 >= 2 )
    {
      v0 = AipExpandPathMacros();
      if ( v0 >= 0 )
        AipPathMacroList = 1;
      goto LABEL_13;
    }
  }
  RtlInitUnicodeString(&DestinationString, AipRegistryPathMacros[v2 + 1]);
  RtlInitUnicodeString(&v7, AipRegistryPathMacros[v2 + 2]);
  P[1] = 0;
  v4 = AiRegReadStringValue(v3, &DestinationString, &v7, P);
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&v9, AipRegistryPathMacros[v2]);
    v0 = AipAddPathMacro(&v9, P, 14);
    if ( v0 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
      goto LABEL_13;
    }
    LODWORD(AipRegistryPathMacros[v2 + 3]) = 1;
    goto LABEL_10;
  }
  v0 = 0;
  if ( v4 != -1073741772 )
    v0 = v4;
LABEL_13:
  RtlReleaseSRWLockExclusive(&qword_180010830);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180004ca0  push    rbp
0x180004ca2  push    rbx
0x180004ca3  push    rsi
0x180004ca4  push    rdi
0x180004ca5  push    r15
0x180004ca7  mov     rbp, rsp
0x180004caa  sub     rsp, 60h
0x180004cae  xorps   xmm0, xmm0
0x180004cb1  lea     rcx, qword_180010830
0x180004cb8  xorps   xmm1, xmm1
0x180004cbb  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x180004cbf  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180004cc3  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x180004cc7  movups  xmmword ptr [rbp+P], xmm1
0x180004ccb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004cd1  cmp     cs:AipPathMacroList, 0
0x180004cd8  jz      short loc_180004CE1
0x180004cda  xor     ebx, ebx
0x180004cdc  jmp     loc_180004D9C
0x180004ce1  xor     esi, esi
0x180004ce3  lea     r15, AipRegistryPathMacros
0x180004cea  mov     edi, esi
0x180004cec  shl     rdi, 5
0x180004cf0  cmp     dword ptr [rdi+r15+18h], 0
0x180004cf6  jnz     loc_180004D7C
0x180004cfc  cmp     dword ptr [rdi+r15+1Ch], 0
0x180004d02  jz      short loc_180004D0D
0x180004d04  cmp     cs:dword_180010804, 0
0x180004d0b  jz      short loc_180004D7C
0x180004d0d  mov     rdx, [rdi+r15+8]; SourceString
0x180004d12  lea     rcx, [rbp+DestinationString]; DestinationString
0x180004d16  call    cs:__imp_RtlInitUnicodeString
0x180004d1c  mov     rdx, [rdi+r15+10h]; SourceString
0x180004d21  lea     rcx, [rbp+var_30]; DestinationString
0x180004d25  call    cs:__imp_RtlInitUnicodeString
0x180004d2b  lea     r9, [rbp+P]
0x180004d2f  mov     [rbp+P+8], 0
0x180004d37  lea     r8, [rbp+var_30]
0x180004d3b  lea     rdx, [rbp+DestinationString]
0x180004d3f  call    AiRegReadStringValue
0x180004d44  test    eax, eax
0x180004d46  js      loc_180004DD1
0x180004d4c  mov     rdx, [rdi+r15]; SourceString
0x180004d50  lea     rcx, [rbp+var_10]; DestinationString
0x180004d54  call    cs:__imp_RtlInitUnicodeString
0x180004d5a  mov     r8d, 0Eh
0x180004d60  lea     rdx, [rbp+P]
0x180004d64  lea     rcx, [rbp+var_10]
0x180004d68  call    AipAddPathMacro
0x180004d6d  mov     ebx, eax
0x180004d6f  test    eax, eax
0x180004d71  js      short loc_180004DB6
0x180004d73  mov     dword ptr [rdi+r15+18h], 1
0x180004d7c  inc     esi
0x180004d7e  cmp     esi, 2
0x180004d81  jb      loc_180004CEA
0x180004d87  call    AipExpandPathMacros
0x180004d8c  mov     ebx, eax
0x180004d8e  test    eax, eax
0x180004d90  js      short loc_180004D9C
0x180004d92  mov     cs:AipPathMacroList, 1
0x180004d9c  lea     rcx, qword_180010830
0x180004da3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004da9  mov     eax, ebx
0x180004dab  add     rsp, 60h
0x180004daf  pop     r15
0x180004db1  pop     rdi
0x180004db2  pop     rsi
0x180004db3  pop     rbx
0x180004db4  pop     rbp
0x180004db5  retn
0x180004db6  mov     rcx, gs:60h
0x180004dbf  xor     edx, edx; Flags
0x180004dc1  mov     r8, [rbp+P+8]; P
0x180004dc5  mov     rcx, [rcx+30h]; HeapHandle
0x180004dc9  call    cs:__imp_RtlFreeHeap
0x180004dcf  jmp     short loc_180004D9C
0x180004dd1  xor     ebx, ebx
0x180004dd3  cmp     eax, 0C0000034h
0x180004dd8  cmovnz  ebx, eax
0x180004ddb  jmp     short loc_180004D9C
```
