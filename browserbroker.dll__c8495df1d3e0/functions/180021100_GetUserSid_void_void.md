# GetUserSid(void *,void * *)

- ea: `0x180021100`
- end: `0x1800211b7`
- name: `?GetUserSid@@YAKPEAXPEAPEAX@Z`
- size: `183`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020bfc`

## callees

- `0x180020a84`
- `0x180021100`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021126`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002118e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021126`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002118e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002119c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002119c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021155`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021155`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021188`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021188`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021148`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021148`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180021174`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180021174`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002116b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002116b`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  unsigned int v4; // edi
  HANDLE ProcessHeap; // rax
  __int64 v6; // r8
  PSID *v7; // rsi
  DWORD LengthSid; // ebp
  HLOCAL v9; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  LPVOID lpMem; // [rsp+50h] [rbp+18h] BYREF

  lpMem = 0;
  v4 = 8;
  ProcessHeap = GetProcessHeap();
  if ( (int)GetTokenInformation_HeapFree<_SID_AND_ATTRIBUTES>(ProcessHeap, TokenHandle, v6, &lpMem) >= 0 )
  {
    v7 = (PSID *)lpMem;
    LengthSid = GetLengthSid(*(PSID *)lpMem);
    v9 = LocalAlloc(0x40u, LengthSid);
    v10 = v9;
    if ( v9 )
    {
      CopySid(LengthSid, v9, *v7);
      if ( IsValidSid(v10) )
      {
        *a2 = v10;
        v4 = 0;
      }
      else
      {
        LocalFree(v10);
      }
    }
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v7);
  }
  return v4;
}

```

## disassembly

```asm
0x180021100  mov     [rsp+arg_0], rbx
0x180021105  mov     [rsp+arg_8], rbp
0x18002110a  push    rsi
0x18002110b  push    rdi
0x18002110c  push    r14
0x18002110e  sub     rsp, 20h
0x180021112  mov     r14, rdx
0x180021115  mov     [rsp+38h+lpMem], 0
0x18002111e  mov     rbx, rcx
0x180021121  mov     edi, 8
0x180021126  call    cs:__imp_GetProcessHeap
0x18002112c  lea     r9, [rsp+38h+lpMem]
0x180021131  mov     rdx, rbx; TokenHandle
0x180021134  mov     rcx, rax; hHeap
0x180021137  call    ??$GetTokenInformation_HeapFree@U_SID_AND_ATTRIBUTES@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_SID_AND_ATTRIBUTES@@@Z; GetTokenInformation_HeapFree<_SID_AND_ATTRIBUTES>(void *,void *,_TOKEN_INFORMATION_CLASS,_SID_AND_ATTRIBUTES * *)
0x18002113c  test    eax, eax
0x18002113e  js      short loc_1800211A2
0x180021140  mov     rsi, [rsp+38h+lpMem]
0x180021145  mov     rcx, [rsi]; pSid
0x180021148  call    cs:__imp_GetLengthSid
0x18002114e  mov     edx, eax; uBytes
0x180021150  lea     ecx, [rdi+38h]; uFlags
0x180021153  mov     ebp, eax
0x180021155  call    cs:__imp_LocalAlloc
0x18002115b  mov     rbx, rax
0x18002115e  test    rax, rax
0x180021161  jz      short loc_18002118E
0x180021163  mov     r8, [rsi]; pSourceSid
0x180021166  mov     rdx, rax; pDestinationSid
0x180021169  mov     ecx, ebp; nDestinationSidLength
0x18002116b  call    cs:__imp_CopySid
0x180021171  mov     rcx, rbx; pSid
0x180021174  call    cs:__imp_IsValidSid
0x18002117a  test    eax, eax
0x18002117c  jz      short loc_180021185
0x18002117e  mov     [r14], rbx
0x180021181  xor     edi, edi
0x180021183  jmp     short loc_18002118E
0x180021185  mov     rcx, rbx; hMem
0x180021188  call    cs:__imp_LocalFree
0x18002118e  call    cs:__imp_GetProcessHeap
0x180021194  mov     r8, rsi; lpMem
0x180021197  xor     edx, edx; dwFlags
0x180021199  mov     rcx, rax; hHeap
0x18002119c  call    cs:__imp_HeapFree
0x1800211a2  mov     rbx, [rsp+38h+arg_0]
0x1800211a7  mov     eax, edi
0x1800211a9  mov     rbp, [rsp+38h+arg_8]
0x1800211ae  add     rsp, 20h
0x1800211b2  pop     r14
0x1800211b4  pop     rdi
0x1800211b5  pop     rsi
0x1800211b6  retn
```
