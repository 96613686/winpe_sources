# GenerateSecDescrBerVal

- ea: `0x180005284`
- end: `0x180005327`
- name: `GenerateSecDescrBerVal`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a00`

## callees

- `0x180005284`
- `0x18001a450`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800052b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800052b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005314`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052c0`

## string_xrefs

- `0x1800052db`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSecDescrBerVal(__int64 a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  PSECURITY_DESCRIPTOR v4; // rcx
  ULONG v6; // [rsp+38h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  v6 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;;GA;;;EA)(A;;GA;;;DA)(A;;GA;;;SY)", 1u, &v7, &v6) )
  {
    v3 = 0;
    *(_DWORD *)a1 = v6;
    *(_QWORD *)(a1 + 8) = v7;
    v4 = 0;
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    SidKeyDebugTraceError(v3, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x13Eu);
    v4 = v7;
  }
  if ( v4 )
    LocalFree(v4);
  return v3;
}

```

## disassembly

```asm
0x180005284  mov     rax, rsp
0x180005287  mov     [rax+8], rbx
0x18000528b  push    rdi
0x18000528c  sub     rsp, 20h
0x180005290  mov     rdi, rcx
0x180005293  mov     qword ptr [rax+18h], 0
0x18000529b  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;EA)(A;;GA;;;DA)(A;;GA;;;SY)"
0x1800052a2  mov     dword ptr [rax+10h], 0
0x1800052a9  lea     r9, [rax+10h]; SecurityDescriptorSize
0x1800052ad  mov     edx, 1; StringSDRevision
0x1800052b2  lea     r8, [rax+18h]; SecurityDescriptor
0x1800052b6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800052bc  test    eax, eax
0x1800052be  jnz     short loc_1800052F7
0x1800052c0  call    cs:__imp_GetLastError
0x1800052c6  mov     ebx, eax
0x1800052c8  test    eax, eax
0x1800052ca  jle     short loc_1800052D5
0x1800052cc  movzx   ebx, ax
0x1800052cf  or      ebx, 80070000h
0x1800052d5  mov     r9d, 13Eh; unsigned int
0x1800052db  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800052e2  lea     rdx, aHr; "hr"
0x1800052e9  mov     ecx, ebx; unsigned int
0x1800052eb  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800052f0  mov     rcx, [rsp+28h+arg_10]
0x1800052f5  jmp     short loc_18000530F
0x1800052f7  mov     ecx, [rsp+28h+arg_8]
0x1800052fb  xor     ebx, ebx
0x1800052fd  mov     [rdi], ecx
0x1800052ff  mov     rcx, [rsp+28h+arg_10]
0x180005304  mov     [rdi+8], rcx
0x180005308  xor     ecx, ecx; hMem
0x18000530a  mov     [rsp+28h+arg_10], rcx
0x18000530f  test    rcx, rcx
0x180005312  jz      short loc_18000531A
0x180005314  call    cs:__imp_LocalFree
0x18000531a  mov     eax, ebx
0x18000531c  mov     rbx, [rsp+28h+arg_0]
0x180005321  add     rsp, 20h
0x180005325  pop     rdi
0x180005326  retn
```
