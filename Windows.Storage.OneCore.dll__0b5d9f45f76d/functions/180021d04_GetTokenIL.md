# GetTokenIL

- ea: `0x180021d04`
- end: `0x180021d63`
- name: `GetTokenIL`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013ab4`

## callees

- `0x180021b34`
- `0x180021d04`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d4b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180021d3e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180021d3e`

## pseudocode

```c
__int64 __fastcall GetTokenIL(void *a1, DWORD *a2, DWORD a3)
{
  int v4; // edi
  HLOCAL v5; // rbx
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  hMem = 0;
  v4 = SHQueryToken<_TOKEN_MANDATORY_LABEL>(a1, (int)a2, a3, &hMem);
  if ( v4 >= 0 )
  {
    v5 = hMem;
    *a2 = *GetSidSubAuthority(*(PSID *)hMem, 0);
    LocalFree(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180021d04  mov     rax, rsp
0x180021d07  mov     [rax+8], rbx
0x180021d0b  mov     [rax+18h], rsi
0x180021d0f  push    rdi
0x180021d10  sub     rsp, 20h
0x180021d14  lea     r9, [rax+10h]
0x180021d18  mov     dword ptr [rdx], 0
0x180021d1e  mov     rsi, rdx
0x180021d21  mov     qword ptr [rax+10h], 0
0x180021d29  call    ??$SHQueryToken@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; SHQueryToken<_TOKEN_MANDATORY_LABEL>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_MANDATORY_LABEL * *)
0x180021d2e  mov     edi, eax
0x180021d30  test    eax, eax
0x180021d32  js      short loc_180021D51
0x180021d34  mov     rbx, [rsp+28h+hMem]
0x180021d39  xor     edx, edx; nSubAuthority
0x180021d3b  mov     rcx, [rbx]; pSid
0x180021d3e  call    cs:__imp_GetSidSubAuthority
0x180021d44  mov     rcx, rbx; hMem
0x180021d47  mov     edx, [rax]
0x180021d49  mov     [rsi], edx
0x180021d4b  call    cs:__imp_LocalFree
0x180021d51  mov     rbx, [rsp+28h+arg_0]
0x180021d56  mov     eax, edi
0x180021d58  mov     rsi, [rsp+28h+arg_10]
0x180021d5d  add     rsp, 20h
0x180021d61  pop     rdi
0x180021d62  retn
```
