# IsCapabilityLicensedApp(ushort const *)

- ea: `0x18000e534`
- end: `0x18000e607`
- name: `?IsCapabilityLicensedApp@@YA_NPEBG@Z`
- size: `211`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000be7c`
- `0x18000eaec`

## callees

- `0x18000e534`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000e5aa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000e5aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e5d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e5f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e5d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e5f1`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18000e58a`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18000e58a`

## pseudocode

```c
char __fastcall IsCapabilityLicensedApp(const unsigned __int16 *a1)
{
  char v1; // si
  __int64 v2; // rbx
  HLOCAL *v3; // rcx
  __int64 i; // rdi
  unsigned int v6; // [rsp+78h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+30h] BYREF

  v1 = 0;
  hMem = 0;
  v6 = 0;
  if ( (int)QueryApplicationCapabilities(a1, &hMem, &v6, 0, 0, 0, 0, 0, 0) >= 0 )
  {
    v2 = 0;
    if ( v6 )
    {
      while ( !EqualSid(*((PSID *)hMem + v2), &unk_180016040) )
      {
        v2 = (unsigned int)(v2 + 1);
        if ( (unsigned int)v2 >= v6 )
          goto LABEL_7;
      }
      v1 = 1;
    }
  }
LABEL_7:
  v3 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( i = 0; (unsigned int)i < v6; v3 = (HLOCAL *)hMem )
    {
      LocalFree(v3[i]);
      *((_QWORD *)hMem + i) = 0;
      i = (unsigned int)(i + 1);
    }
    LocalFree(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18000e534  mov     rax, rsp
0x18000e537  mov     [rax+8], rbx
0x18000e53b  push    rbp
0x18000e53c  push    rsi
0x18000e53d  push    rdi
0x18000e53e  mov     rbp, rsp
0x18000e541  sub     rsp, 50h
0x18000e545  mov     qword ptr [rax-28h], 0
0x18000e54d  lea     r8, [rbp+arg_8]
0x18000e551  mov     qword ptr [rax-30h], 0
0x18000e559  lea     rdx, [rbp+hMem]
0x18000e55d  mov     qword ptr [rax-38h], 0
0x18000e565  xor     r9d, r9d
0x18000e568  mov     qword ptr [rax-40h], 0
0x18000e570  xor     sil, sil
0x18000e573  mov     qword ptr [rax-48h], 0
0x18000e57b  mov     [rbp+hMem], 0
0x18000e583  mov     [rbp+arg_8], 0
0x18000e58a  call    cs:__imp_QueryApplicationCapabilities
0x18000e590  test    eax, eax
0x18000e592  js      short loc_18000E5C0
0x18000e594  xor     ebx, ebx
0x18000e596  cmp     [rbp+arg_8], ebx
0x18000e599  jbe     short loc_18000E5C0
0x18000e59b  mov     rcx, [rbp+hMem]
0x18000e59f  lea     rdx, unk_180016040; pSid2
0x18000e5a6  mov     rcx, [rcx+rbx*8]; pSid1
0x18000e5aa  call    cs:__imp_EqualSid
0x18000e5b0  test    eax, eax
0x18000e5b2  jnz     short loc_18000E5BD
0x18000e5b4  inc     ebx
0x18000e5b6  cmp     ebx, [rbp+arg_8]
0x18000e5b9  jb      short loc_18000E59B
0x18000e5bb  jmp     short loc_18000E5C0
0x18000e5bd  mov     sil, 1
0x18000e5c0  mov     rcx, [rbp+hMem]
0x18000e5c4  test    rcx, rcx
0x18000e5c7  jz      short loc_18000E5F7
0x18000e5c9  xor     edi, edi
0x18000e5cb  cmp     [rbp+arg_8], edi
0x18000e5ce  jbe     short loc_18000E5F1
0x18000e5d0  mov     rcx, [rcx+rdi*8]; hMem
0x18000e5d4  call    cs:__imp_LocalFree
0x18000e5da  mov     rax, [rbp+hMem]
0x18000e5de  mov     qword ptr [rax+rdi*8], 0
0x18000e5e6  inc     edi
0x18000e5e8  mov     rcx, [rbp+hMem]; hMem
0x18000e5ec  cmp     edi, [rbp+arg_8]
0x18000e5ef  jb      short loc_18000E5D0
0x18000e5f1  call    cs:__imp_LocalFree
0x18000e5f7  mov     rbx, [rsp+50h+arg_0]
0x18000e5fc  mov     al, sil
0x18000e5ff  add     rsp, 50h
0x18000e603  pop     rdi
0x18000e604  pop     rsi
0x18000e605  pop     rbp
0x18000e606  retn
```
