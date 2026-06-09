# NcbPolicyCleanupPoliciesUnderLock

- ea: `0x1800076e0`
- end: `0x18000785d`
- name: `NcbPolicyCleanupPoliciesUnderLock`
- size: `381`
- prototype: `__int64 __fastcall(PSID Sid1)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180007870`
- `0x180007a70`
- `0x18002290c`

## callees

- `0x1800076e0`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18000775d`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000775d`
- `ntdll!RtlEqualSid` at `0x180007742`
- `ntdll!RtlEqualSid` at `0x180007742`
- `ntdll!RtlInitEnumerationHashTable` at `0x18000770d`
- `ntdll!RtlInitEnumerationHashTable` at `0x18000770d`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000784c`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000784c`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000771f`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180007829`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000771f`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180007829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007772`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000778f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007809`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007772`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000778f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007809`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007780`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000779d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007803`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007817`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007780`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000779d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007803`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007817`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077e6`

## pseudocode

```c
__int64 __fastcall NcbPolicyCleanupPoliciesUnderLock(PSID Sid1)
{
  __int64 i; // rbx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  void *v5; // rdi
  HANDLE v6; // rax
  void *v7; // rdi
  HANDLE v8; // rax
  void *v9; // rdi
  HANDLE v10; // rax
  void *v11; // rcx
  void *v12; // rdi
  HANDLE v13; // rax
  HANDLE v14; // rax
  _OWORD v16[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v17; // [rsp+40h] [rbp-18h]

  v17 = 0;
  memset(v16, 0, sizeof(v16));
  RtlInitEnumerationHashTable(g_NcbPolicies, v16);
  for ( i = RtlEnumerateEntryHashTable(g_NcbPolicies, v16); i; i = RtlEnumerateEntryHashTable(g_NcbPolicies, v16) )
  {
    if ( !Sid1 || RtlEqualSid(Sid1, *(PSID *)(i + 24)) )
    {
      RtlRemoveEntryHashTable(g_NcbPolicies, i, 0);
      --g_NcbPolicyCounter;
      v3 = *(void **)(i + 48);
      if ( v3 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
      }
      v5 = *(void **)(i + 64);
      if ( v5 )
      {
        v6 = GetProcessHeap();
        HeapFree(v6, 0, v5);
      }
      v7 = *(void **)(i + 56);
      if ( v7 )
      {
        v8 = GetProcessHeap();
        HeapFree(v8, 0, v7);
      }
      v9 = *(void **)(i + 40);
      if ( v9 )
      {
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v9);
      }
      v11 = *(void **)(i + 32);
      if ( v11 )
        LocalFree(v11);
      v12 = *(void **)(i + 24);
      if ( v12 )
      {
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v12);
      }
      v14 = GetProcessHeap();
      HeapFree(v14, 0, (LPVOID)i);
    }
  }
  return RtlEndEnumerationHashTable(g_NcbPolicies, v16);
}

```

## disassembly

```asm
0x1800076e0  mov     [rsp+arg_8], rbx
0x1800076e5  push    rsi
0x1800076e6  sub     rsp, 50h
0x1800076ea  xorps   xmm0, xmm0
0x1800076ed  lea     rdx, [rsp+58h+var_38]
0x1800076f2  mov     rsi, rcx
0x1800076f5  xor     eax, eax
0x1800076f7  lea     rcx, g_NcbPolicies
0x1800076fe  mov     [rsp+58h+var_18], rax
0x180007703  movups  [rsp+58h+var_38], xmm0
0x180007708  movups  [rsp+58h+var_28], xmm0
0x18000770d  call    cs:__imp_RtlInitEnumerationHashTable
0x180007713  lea     rdx, [rsp+58h+var_38]
0x180007718  lea     rcx, g_NcbPolicies
0x18000771f  call    cs:__imp_RtlEnumerateEntryHashTable
0x180007725  mov     rbx, rax
0x180007728  test    rax, rax
0x18000772b  jz      loc_180007840
0x180007731  mov     [rsp+58h+arg_0], rdi
0x180007736  test    rsi, rsi
0x180007739  jz      short loc_180007750
0x18000773b  mov     rdx, [rbx+18h]; Sid2
0x18000773f  mov     rcx, rsi; Sid1
0x180007742  call    cs:__imp_RtlEqualSid
0x180007748  test    al, al
0x18000774a  jz      loc_18000781D
0x180007750  xor     r8d, r8d
0x180007753  lea     rcx, g_NcbPolicies
0x18000775a  mov     rdx, rbx
0x18000775d  call    cs:__imp_RtlRemoveEntryHashTable
0x180007763  dec     cs:g_NcbPolicyCounter
0x180007769  mov     rdi, [rbx+30h]
0x18000776d  test    rdi, rdi
0x180007770  jz      short loc_180007786
0x180007772  call    cs:__imp_GetProcessHeap
0x180007778  mov     r8, rdi; lpMem
0x18000777b  xor     edx, edx; dwFlags
0x18000777d  mov     rcx, rax; hHeap
0x180007780  call    cs:__imp_HeapFree
0x180007786  mov     rdi, [rbx+40h]
0x18000778a  test    rdi, rdi
0x18000778d  jz      short loc_1800077A3
0x18000778f  call    cs:__imp_GetProcessHeap
0x180007795  mov     r8, rdi; lpMem
0x180007798  xor     edx, edx; dwFlags
0x18000779a  mov     rcx, rax; hHeap
0x18000779d  call    cs:__imp_HeapFree
0x1800077a3  mov     rdi, [rbx+38h]
0x1800077a7  test    rdi, rdi
0x1800077aa  jz      short loc_1800077C0
0x1800077ac  call    cs:__imp_GetProcessHeap
0x1800077b2  mov     r8, rdi; lpMem
0x1800077b5  xor     edx, edx; dwFlags
0x1800077b7  mov     rcx, rax; hHeap
0x1800077ba  call    cs:__imp_HeapFree
0x1800077c0  mov     rdi, [rbx+28h]
0x1800077c4  test    rdi, rdi
0x1800077c7  jz      short loc_1800077DD
0x1800077c9  call    cs:__imp_GetProcessHeap
0x1800077cf  mov     r8, rdi; lpMem
0x1800077d2  xor     edx, edx; dwFlags
0x1800077d4  mov     rcx, rax; hHeap
0x1800077d7  call    cs:__imp_HeapFree
0x1800077dd  mov     rcx, [rbx+20h]; hMem
0x1800077e1  test    rcx, rcx
0x1800077e4  jz      short loc_1800077EC
0x1800077e6  call    cs:__imp_LocalFree
0x1800077ec  mov     rdi, [rbx+18h]
0x1800077f0  test    rdi, rdi
0x1800077f3  jz      short loc_180007809
0x1800077f5  call    cs:__imp_GetProcessHeap
0x1800077fb  mov     r8, rdi; lpMem
0x1800077fe  xor     edx, edx; dwFlags
0x180007800  mov     rcx, rax; hHeap
0x180007803  call    cs:__imp_HeapFree
0x180007809  call    cs:__imp_GetProcessHeap
0x18000780f  mov     r8, rbx; lpMem
0x180007812  xor     edx, edx; dwFlags
0x180007814  mov     rcx, rax; hHeap
0x180007817  call    cs:__imp_HeapFree
0x18000781d  lea     rdx, [rsp+58h+var_38]
0x180007822  lea     rcx, g_NcbPolicies
0x180007829  call    cs:__imp_RtlEnumerateEntryHashTable
0x18000782f  mov     rbx, rax
0x180007832  test    rax, rax
0x180007835  jnz     loc_180007736
0x18000783b  mov     rdi, [rsp+58h+arg_0]
0x180007840  lea     rdx, [rsp+58h+var_38]
0x180007845  lea     rcx, g_NcbPolicies
0x18000784c  call    cs:__imp_RtlEndEnumerationHashTable
0x180007852  mov     rbx, [rsp+58h+arg_8]
0x180007857  add     rsp, 50h
0x18000785b  pop     rsi
0x18000785c  retn
```
