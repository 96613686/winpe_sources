# AddOEMRUString

- ea: `0x18000d860`
- end: `0x18000da33`
- name: `AddOEMRUString`
- size: `467`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004640`
- `0x18000d860`
- `0x180012d14`
- `0x180014010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000d97e`
- `ADVAPI32!RegSetValueExW` at `0x18000da10`
- `ADVAPI32!RegSetValueExW` at `0x18000d97e`
- `ADVAPI32!RegSetValueExW` at `0x18000da10`
- `KERNEL32!RtlMoveMemory` at `0x18000d9cc`
- `KERNEL32!RtlMoveMemory` at `0x18000d9cc`
- `SHLWAPI!StrChrW` at `0x18000d995`
- `SHLWAPI!StrChrW` at `0x18000d995`

## pseudocode

```c
__int64 __fastcall AddOEMRUString(__int64 a1, const BYTE *a2)
{
  LPWSTR *v5; // r15
  unsigned int v6; // eax
  unsigned int v7; // ebp
  unsigned int (__fastcall *v8)(const BYTE *); // r12
  _QWORD *v9; // rdi
  char v10; // r14
  int v11; // r14d
  __int64 v12; // rsi
  WCHAR v13; // di
  unsigned int i; // edi
  __int64 v15; // rax
  PWSTR v16; // rax
  unsigned __int64 v17; // rdx
  const BYTE *v18; // rcx
  unsigned int ValueName; // [rsp+80h] [rbp+8h] BYREF

  if ( !a1 )
    return -1;
  v5 = (LPWSTR *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 4);
  v7 = 0;
  v8 = *(unsigned int (__fastcall **)(const BYTE *))(a1 + 8);
  v9 = (_QWORD *)(a1 + 32);
  v10 = ~(unsigned __int8)(*(_DWORD *)a1 >> 1);
  ValueName = v6;
  v11 = v10 & 1;
  while ( 1 )
  {
    v12 = -1;
    if ( v7 >= v6 )
      break;
    if ( *v9 )
    {
      if ( !v8(a2) )
      {
        v13 = v7 + 97;
        goto LABEL_21;
      }
      v6 = ValueName;
    }
    ++v7;
    ++v9;
  }
  for ( i = 0; i < v6; ++i )
  {
    if ( !*v5 )
    {
      v13 = i + 97;
      goto LABEL_16;
    }
    ++v5;
  }
  v13 = *(_WORD *)(*(_QWORD *)(a1 + 24) + 2LL * (v6 - 1));
  v5 = (LPWSTR *)(a1 - 744 + 8LL * v13);
LABEL_16:
  if ( Str_SetPtrW(v5, (LPCWSTR)a2) )
  {
    v15 = -1;
    v7 = v13 - 97;
    ValueName = v13;
    do
      ++v15;
    while ( *(_WORD *)&a2[2 * v15] );
    RegSetValueExW(*(HKEY *)(a1 + 16), (LPCWSTR)&ValueName, 0, 1u, a2, 2 * v15 + 2);
    v11 = 1;
  }
  else
  {
    v7 = -1;
  }
LABEL_21:
  v16 = StrChrW(*(PCWSTR *)(a1 + 24), v13);
  if ( v16 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    StringCchCopyW(v16, v17, v16 + 1);
  }
  if ( v7 != -1 )
  {
    RtlMoveMemory(*(_QWORD *)(a1 + 24) + 2LL, *(_QWORD *)(a1 + 24), (unsigned int)(2 * *(_DWORD *)(a1 + 4)));
    **(_WORD **)(a1 + 24) = v13;
  }
  if ( v11 )
  {
    v18 = *(const BYTE **)(a1 + 24);
    do
      ++v12;
    while ( *(_WORD *)&v18[2 * v12] );
    RegSetValueExW(*(HKEY *)(a1 + 16), L"MRUList", 0, 1u, v18, 2 * v12 + 2);
    *(_DWORD *)a1 &= ~0x1000u;
  }
  else
  {
    *(_DWORD *)a1 |= 0x1000u;
  }
  return v7;
}

```

## disassembly

```asm
0x18000d860  push    rbx
0x18000d862  push    rbp
0x18000d863  push    rsi
0x18000d864  push    rdi
0x18000d865  push    r12
0x18000d867  push    r13
0x18000d869  push    r14
0x18000d86b  push    r15
0x18000d86d  sub     rsp, 38h
0x18000d871  mov     rbx, rcx
0x18000d874  mov     r13, rdx
0x18000d877  xor     ecx, ecx
0x18000d879  test    rbx, rbx
0x18000d87c  jnz     short loc_18000D887
0x18000d87e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d882  jmp     loc_18000DA22
0x18000d887  mov     r14d, [rbx]
0x18000d88a  lea     r15, [rbx+20h]
0x18000d88e  mov     eax, [rbx+4]
0x18000d891  mov     ebp, ecx
0x18000d893  mov     r12, [rbx+8]
0x18000d897  mov     rdi, r15
0x18000d89a  shr     r14d, 1
0x18000d89d  not     r14d
0x18000d8a0  mov     [rsp+78h+ValueName], eax
0x18000d8a7  and     r14d, 1
0x18000d8ab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000d8af  cmp     ebp, eax
0x18000d8b1  jnb     short loc_18000D8EA
0x18000d8b3  mov     rdx, [rdi]
0x18000d8b6  test    rdx, rdx
0x18000d8b9  jz      short loc_18000D8D3
0x18000d8bb  mov     rcx, r13
0x18000d8be  mov     rax, r12
0x18000d8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c6  xor     ecx, ecx
0x18000d8c8  test    eax, eax
0x18000d8ca  jz      short loc_18000D8DB
0x18000d8cc  mov     eax, [rsp+78h+ValueName]
0x18000d8d3  inc     ebp
0x18000d8d5  add     rdi, 8
0x18000d8d9  jmp     short loc_18000D8AB
0x18000d8db  mov     edi, 61h ; 'a'
0x18000d8e0  add     edi, ebp
0x18000d8e2  xor     r15d, r15d
0x18000d8e5  jmp     loc_18000D98E
0x18000d8ea  mov     edi, ecx
0x18000d8ec  mov     r12d, 61h ; 'a'
0x18000d8f2  cmp     edi, eax
0x18000d8f4  jnb     short loc_18000D909
0x18000d8f6  cmp     [r15], rcx
0x18000d8f9  jz      short loc_18000D903
0x18000d8fb  inc     edi
0x18000d8fd  add     r15, 8
0x18000d901  jmp     short loc_18000D8EC
0x18000d903  add     di, r12w
0x18000d907  jmp     short loc_18000D922
0x18000d909  lea     ecx, [rax-1]
0x18000d90c  mov     rax, [rbx+18h]
0x18000d910  lea     r15, [rbx-2E8h]
0x18000d917  movzx   edx, word ptr [rax+rcx*2]
0x18000d91b  movzx   edi, dx
0x18000d91e  lea     r15, [r15+rdx*8]
0x18000d922  mov     rdx, r13; psz
0x18000d925  mov     rcx, r15; ppsz
0x18000d928  call    Str_SetPtrW
0x18000d92d  xor     r15d, r15d
0x18000d930  test    eax, eax
0x18000d932  jz      short loc_18000D98C
0x18000d934  movzx   ebp, di
0x18000d937  mov     rax, rsi
0x18000d93a  sub     ebp, r12d
0x18000d93d  mov     word ptr [rsp+78h+ValueName], di
0x18000d945  mov     word ptr [rsp+78h+ValueName+2], r15w
0x18000d94e  inc     rax
0x18000d951  cmp     [r13+rax*2+0], r15w
0x18000d957  jnz     short loc_18000D94E
0x18000d959  mov     rcx, [rbx+10h]; hKey
0x18000d95d  lea     eax, ds:2[rax*2]
0x18000d964  mov     [rsp+78h+cbData], eax; cbData
0x18000d968  lea     rdx, [rsp+78h+ValueName]; lpValueName
0x18000d970  mov     r9d, 1; dwType
0x18000d976  mov     [rsp+78h+lpData], r13; lpData
0x18000d97b  xor     r8d, r8d; Reserved
0x18000d97e  call    cs:__imp_RegSetValueExW
0x18000d984  mov     r14d, 1
0x18000d98a  jmp     short loc_18000D98E
0x18000d98c  mov     ebp, esi
0x18000d98e  mov     rcx, [rbx+18h]; pszStart
0x18000d992  movzx   edx, di; wMatch
0x18000d995  call    cs:__imp_StrChrW
0x18000d99b  test    rax, rax
0x18000d99e  jz      short loc_18000D9B9
0x18000d9a0  mov     rdx, rsi
0x18000d9a3  inc     rdx; unsigned __int64
0x18000d9a6  cmp     [rax+rdx*2], r15w
0x18000d9ab  jnz     short loc_18000D9A3
0x18000d9ad  lea     r8, [rax+2]; unsigned __int16 *
0x18000d9b1  mov     rcx, rax; unsigned __int16 *
0x18000d9b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d9b9  cmp     ebp, esi
0x18000d9bb  jz      short loc_18000D9D9
0x18000d9bd  mov     rdx, [rbx+18h]
0x18000d9c1  mov     r8d, [rbx+4]
0x18000d9c5  add     r8d, r8d
0x18000d9c8  lea     rcx, [rdx+2]
0x18000d9cc  call    cs:__imp_RtlMoveMemory
0x18000d9d2  mov     rax, [rbx+18h]
0x18000d9d6  mov     [rax], di
0x18000d9d9  test    r14d, r14d
0x18000d9dc  jz      short loc_18000DA1C
0x18000d9de  mov     rcx, [rbx+18h]
0x18000d9e2  inc     rsi
0x18000d9e5  cmp     [rcx+rsi*2], r15w
0x18000d9ea  jnz     short loc_18000D9E2
0x18000d9ec  lea     eax, ds:2[rsi*2]
0x18000d9f3  mov     r9d, 1; dwType
0x18000d9f9  mov     [rsp+78h+cbData], eax; cbData
0x18000d9fd  lea     rdx, aMrulist; "MRUList"
0x18000da04  mov     [rsp+78h+lpData], rcx; lpData
0x18000da09  xor     r8d, r8d; Reserved
0x18000da0c  mov     rcx, [rbx+10h]; hKey
0x18000da10  call    cs:__imp_RegSetValueExW
0x18000da16  btr     dword ptr [rbx], 0Ch
0x18000da1a  jmp     short loc_18000DA20
0x18000da1c  bts     dword ptr [rbx], 0Ch
0x18000da20  mov     eax, ebp
0x18000da22  add     rsp, 38h
0x18000da26  pop     r15
0x18000da28  pop     r14
0x18000da2a  pop     r13
0x18000da2c  pop     r12
0x18000da2e  pop     rdi
0x18000da2f  pop     rsi
0x18000da30  pop     rbp
0x18000da31  pop     rbx
0x18000da32  retn
```
