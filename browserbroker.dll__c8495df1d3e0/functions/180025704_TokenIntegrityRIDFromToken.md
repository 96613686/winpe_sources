# _TokenIntegrityRIDFromToken

- ea: `0x180025704`
- end: `0x180025784`
- name: `_TokenIntegrityRIDFromToken`
- size: `128`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a4fc`
- `0x180020fe8`

## callees

- `0x180025638`
- `0x180025704`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025722`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002575e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025722`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002575e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002576c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002576c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180025754`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180025754`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180025746`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180025746`

## pseudocode

```c
__int64 __fastcall TokenIntegrityRIDFromToken(HANDLE TokenHandle, DWORD *a2)
{
  HANDLE ProcessHeap; // rax
  __int64 v5; // r8
  int TokenInformation_Heap; // edi
  PSID *v7; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  HANDLE v9; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+18h] BYREF

  lpMem = 0;
  ProcessHeap = GetProcessHeap();
  TokenInformation_Heap = GetTokenInformation_HeapFree<_TOKEN_MANDATORY_LABEL>(ProcessHeap, TokenHandle, v5, &lpMem);
  if ( TokenInformation_Heap >= 0 )
  {
    v7 = (PSID *)lpMem;
    SidSubAuthorityCount = GetSidSubAuthorityCount(*(PSID *)lpMem);
    *a2 = *GetSidSubAuthority(*v7, (unsigned int)*SidSubAuthorityCount - 1);
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v7);
  }
  return (unsigned int)TokenInformation_Heap;
}

```

## disassembly

```asm
0x180025704  mov     [rsp+arg_0], rbx
0x180025709  mov     [rsp+arg_8], rsi
0x18002570e  push    rdi
0x18002570f  sub     rsp, 20h
0x180025713  mov     rsi, rdx
0x180025716  mov     [rsp+28h+lpMem], 0
0x18002571f  mov     rbx, rcx
0x180025722  call    cs:__imp_GetProcessHeap
0x180025728  lea     r9, [rsp+28h+lpMem]
0x18002572d  mov     rdx, rbx; TokenHandle
0x180025730  mov     rcx, rax; hHeap
0x180025733  call    ??$GetTokenInformation_HeapFree@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; GetTokenInformation_HeapFree<_TOKEN_MANDATORY_LABEL>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_MANDATORY_LABEL * *)
0x180025738  mov     edi, eax
0x18002573a  test    eax, eax
0x18002573c  js      short loc_180025772
0x18002573e  mov     rbx, [rsp+28h+lpMem]
0x180025743  mov     rcx, [rbx]; pSid
0x180025746  call    cs:__imp_GetSidSubAuthorityCount
0x18002574c  mov     rcx, [rbx]; pSid
0x18002574f  movzx   edx, byte ptr [rax]
0x180025752  dec     edx; nSubAuthority
0x180025754  call    cs:__imp_GetSidSubAuthority
0x18002575a  mov     ecx, [rax]
0x18002575c  mov     [rsi], ecx
0x18002575e  call    cs:__imp_GetProcessHeap
0x180025764  mov     r8, rbx; lpMem
0x180025767  xor     edx, edx; dwFlags
0x180025769  mov     rcx, rax; hHeap
0x18002576c  call    cs:__imp_HeapFree
0x180025772  mov     rbx, [rsp+28h+arg_0]
0x180025777  mov     eax, edi
0x180025779  mov     rsi, [rsp+28h+arg_8]
0x18002577e  add     rsp, 20h
0x180025782  pop     rdi
0x180025783  retn
```
