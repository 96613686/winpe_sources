# InvCacheEnumerateItems

- ea: `0x180028aa0`
- end: `0x180028cbc`
- name: `InvCacheEnumerateItems`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180014990`

## callees

- `0x180028990`
- `0x180028aa0`
- `0x1800295dc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180028c1f`
- `ntdll!RtlAllocateHeap` at `0x180028c77`
- `ntdll!RtlAllocateHeap` at `0x180028c1f`
- `ntdll!RtlAllocateHeap` at `0x180028c77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028bbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028bbf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180028b46`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180028b46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028c3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028c3e`

## string_xrefs

- `0x180028bf6`: `InvCacheOpenItem`
- `0x180028be5`: `RegOpenKeyEx failed [%#x]`

## pseudocode

```c
__int64 __fastcall InvCacheEnumerateItems(HKEY **a1, _DWORD **a2, WCHAR *a3, DWORD *a4, HKEY phkResult)
{
  HKEY v5; // rdi
  __int64 v9; // rax
  HKEY v10; // rcx
  _DWORD *v11; // rsi
  DWORD v12; // edx
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  bool v15; // zf
  __int64 v16; // rax
  HKEY v17; // rcx
  LSTATUS v18; // eax
  HKEY *Heap; // rax
  HKEY *v20; // rdi
  _DWORD *v21; // rax

  v5 = phkResult;
  if ( !phkResult )
    return (unsigned int)-2147024809;
  if ( *(_DWORD *)phkResult != 1 )
    return (unsigned int)-2147024809;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( !a3 )
    return (unsigned int)-2147024809;
  if ( !a4 )
    return (unsigned int)-2147024809;
  *a1 = 0;
  v9 = *((_QWORD *)v5 + 1);
  if ( !v9 )
    return (unsigned int)-2147024809;
  v10 = *(HKEY *)(v9 + 8);
  if ( !v10 )
    return (unsigned int)-2147024809;
  v11 = *a2;
  v12 = 0;
  if ( *a2 )
  {
    if ( *v11 != 3 )
      return (unsigned int)-2147024809;
    v12 = v11[2];
  }
  v13 = RegEnumKeyExW(v10, v12, a3, a4, 0, 0, 0, 0);
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  if ( (v14 & 0x80000000) == 0 )
  {
    if ( v11 )
      ++v11[2];
    v15 = *(_DWORD *)v5 == 1;
    phkResult = 0;
    if ( v15 )
    {
      if ( *a3 )
      {
        v16 = *((_QWORD *)v5 + 1);
        if ( v16 )
        {
          v17 = *(HKEY *)(v16 + 8);
          if ( v17 )
          {
            v18 = RegOpenKeyExW(v17, a3, 0, 0xF003Fu, &phkResult);
            v14 = v18;
            if ( v18 > 0 )
              v14 = (unsigned __int16)v18 | 0x80070000;
            if ( (v14 & 0x80000000) != 0 )
            {
              if ( v14 != -2147024894 )
                AslLogCallPrintf(1, "InvCacheOpenItem", 177, "RegOpenKeyEx failed [%#x]", v14);
              goto LABEL_27;
            }
            Heap = (HKEY *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
            v20 = Heap;
            if ( !Heap )
            {
              v14 = -2147024882;
LABEL_27:
              if ( phkResult )
                RegCloseKey(phkResult);
              return v14;
            }
            *(_DWORD *)Heap = 2;
            v14 = 0;
            Heap[1] = phkResult;
            if ( !v11 )
            {
              v21 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
              if ( !v21 )
              {
                v14 = -2147024882;
                if ( v20 )
                  InvCacheCloseHandle(v20);
                return v14;
              }
              *v21 = 3;
              v21[2] = 1;
              *a2 = v21;
            }
            *a1 = v20;
            return v14;
          }
        }
      }
    }
    return (unsigned int)-2147024809;
  }
  return v14;
}

```

## disassembly

```asm
0x180028aa0  push    rbx
0x180028aa2  push    rbp
0x180028aa3  push    rsi
0x180028aa4  push    rdi
0x180028aa5  push    r14
0x180028aa7  push    r15
0x180028aa9  sub     rsp, 48h
0x180028aad  mov     rdi, [rsp+78h+phkResult]
0x180028ab5  mov     rbp, r8
0x180028ab8  mov     r14, rdx
0x180028abb  mov     r15, rcx
0x180028abe  test    rdi, rdi
0x180028ac1  jz      loc_180028CA8
0x180028ac7  cmp     dword ptr [rdi], 1
0x180028aca  jnz     loc_180028CA8
0x180028ad0  test    rdx, rdx
0x180028ad3  jz      loc_180028CA8
0x180028ad9  test    r8, r8
0x180028adc  jz      loc_180028CA8
0x180028ae2  test    r9, r9
0x180028ae5  jz      loc_180028CA8
0x180028aeb  mov     qword ptr [rcx], 0
0x180028af2  mov     rax, [rdi+8]
0x180028af6  test    rax, rax
0x180028af9  jz      loc_180028CA8
0x180028aff  mov     rcx, [rax+8]; hKey
0x180028b03  test    rcx, rcx
0x180028b06  jz      loc_180028CA8
0x180028b0c  mov     rsi, [r14]
0x180028b0f  xor     edx, edx
0x180028b11  test    rsi, rsi
0x180028b14  jz      short loc_180028B22
0x180028b16  cmp     dword ptr [rsi], 3
0x180028b19  jnz     loc_180028CA8
0x180028b1f  mov     edx, [rsi+8]; dwIndex
0x180028b22  mov     [rsp+78h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180028b2b  mov     [rsp+78h+lpcchClass], 0; lpcchClass
0x180028b34  mov     [rsp+78h+lpClass], 0; lpClass
0x180028b3d  mov     [rsp+78h+lpReserved], 0; lpReserved
0x180028b46  call    cs:__imp_RegEnumKeyExW
0x180028b4c  mov     ebx, eax
0x180028b4e  test    eax, eax
0x180028b50  jle     short loc_180028B5B
0x180028b52  movzx   ebx, ax
0x180028b55  or      ebx, 80070000h
0x180028b5b  test    ebx, ebx
0x180028b5d  js      loc_180028CAD
0x180028b63  test    rsi, rsi
0x180028b66  jz      short loc_180028B6B
0x180028b68  inc     dword ptr [rsi+8]
0x180028b6b  cmp     dword ptr [rdi], 1
0x180028b6e  mov     [rsp+78h+phkResult], 0
0x180028b7a  jnz     loc_180028CA8
0x180028b80  xor     eax, eax
0x180028b82  cmp     ax, [rbp+0]
0x180028b86  jz      loc_180028CA8
0x180028b8c  mov     rax, [rdi+8]
0x180028b90  test    rax, rax
0x180028b93  jz      loc_180028CA8
0x180028b99  mov     rcx, [rax+8]; hKey
0x180028b9d  test    rcx, rcx
0x180028ba0  jz      loc_180028CA8
0x180028ba6  lea     rax, [rsp+78h+phkResult]
0x180028bae  mov     r9d, 0F003Fh; samDesired
0x180028bb4  xor     r8d, r8d; ulOptions
0x180028bb7  mov     [rsp+78h+lpReserved], rax; phkResult
0x180028bbc  mov     rdx, rbp; lpSubKey
0x180028bbf  call    cs:__imp_RegOpenKeyExW
0x180028bc5  mov     ebx, eax
0x180028bc7  test    eax, eax
0x180028bc9  jle     short loc_180028BD4
0x180028bcb  movzx   ebx, ax
0x180028bce  or      ebx, 80070000h
0x180028bd4  mov     ebp, 8007000Eh
0x180028bd9  test    ebx, ebx
0x180028bdb  jns     short loc_180028C09
0x180028bdd  cmp     ebx, 80070002h
0x180028be3  jz      short loc_180028C2F
0x180028be5  lea     r9, aRegopenkeyexFa_0; "RegOpenKeyEx failed [%#x]"
0x180028bec  mov     dword ptr [rsp+78h+lpReserved], ebx
0x180028bf0  mov     r8d, 0B1h
0x180028bf6  lea     rdx, aInvcacheopenit_0; "InvCacheOpenItem"
0x180028bfd  mov     ecx, 1
0x180028c02  call    AslLogCallPrintf
0x180028c07  jmp     short loc_180028C2F
0x180028c09  mov     rcx, gs:60h
0x180028c12  mov     edx, 8; Flags
0x180028c17  mov     rcx, [rcx+30h]; HeapHandle
0x180028c1b  lea     r8d, [rdx+8]; Size
0x180028c1f  call    cs:__imp_RtlAllocateHeap
0x180028c25  mov     rdi, rax
0x180028c28  test    rax, rax
0x180028c2b  jnz     short loc_180028C4A
0x180028c2d  mov     ebx, ebp
0x180028c2f  mov     rcx, [rsp+78h+phkResult]; hKey
0x180028c37  xor     edi, edi
0x180028c39  test    rcx, rcx
0x180028c3c  jz      short loc_180028C44
0x180028c3e  call    cs:__imp_RegCloseKey
0x180028c44  test    ebx, ebx
0x180028c46  js      short loc_180028CAD
0x180028c48  jmp     short loc_180028C5E
0x180028c4a  mov     dword ptr [rax], 2
0x180028c50  xor     ebx, ebx
0x180028c52  mov     rax, [rsp+78h+phkResult]
0x180028c5a  mov     [rdi+8], rax
0x180028c5e  test    rsi, rsi
0x180028c61  jnz     short loc_180028CA3
0x180028c63  mov     rcx, gs:60h
0x180028c6c  lea     edx, [rsi+8]; Flags
0x180028c6f  lea     r8d, [rsi+10h]; Size
0x180028c73  mov     rcx, [rcx+30h]; HeapHandle
0x180028c77  call    cs:__imp_RtlAllocateHeap
0x180028c7d  test    rax, rax
0x180028c80  jnz     short loc_180028C93
0x180028c82  mov     ebx, ebp
0x180028c84  test    rdi, rdi
0x180028c87  jz      short loc_180028CAD
0x180028c89  mov     rcx, rdi; P
0x180028c8c  call    InvCacheCloseHandle
0x180028c91  jmp     short loc_180028CAD
0x180028c93  mov     dword ptr [rax], 3
0x180028c99  mov     dword ptr [rax+8], 1
0x180028ca0  mov     [r14], rax
0x180028ca3  mov     [r15], rdi
0x180028ca6  jmp     short loc_180028CAD
0x180028ca8  mov     ebx, 80070057h
0x180028cad  mov     eax, ebx
0x180028caf  add     rsp, 48h
0x180028cb3  pop     r15
0x180028cb5  pop     r14
0x180028cb7  pop     rdi
0x180028cb8  pop     rsi
0x180028cb9  pop     rbp
0x180028cba  pop     rbx
0x180028cbb  retn
```
