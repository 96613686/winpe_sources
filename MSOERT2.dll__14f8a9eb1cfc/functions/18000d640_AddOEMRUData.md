# AddOEMRUData

- ea: `0x18000d640`
- end: `0x18000d84b`
- name: `AddOEMRUData`
- size: `523`
- prototype: `__int64 __fastcall(struct tagOEMRUDATA *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004640`
- `0x18000d5e4`
- `0x18000d640`
- `0x180014010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000d788`
- `ADVAPI32!RegSetValueExW` at `0x18000d819`
- `ADVAPI32!RegSetValueExW` at `0x18000d788`
- `ADVAPI32!RegSetValueExW` at `0x18000d819`
- `KERNEL32!RtlMoveMemory` at `0x18000d756`
- `KERNEL32!RtlMoveMemory` at `0x18000d7d5`
- `KERNEL32!RtlMoveMemory` at `0x18000d756`
- `KERNEL32!RtlMoveMemory` at `0x18000d7d5`
- `SHLWAPI!StrChrW` at `0x18000d79b`
- `SHLWAPI!StrChrW` at `0x18000d79b`

## pseudocode

```c
__int64 __fastcall AddOEMRUData(struct tagOEMRUDATA *a1, BYTE *a2, unsigned int a3)
{
  BYTE *v5; // r8
  char *v6; // r15
  unsigned int v7; // eax
  unsigned int v8; // ebp
  unsigned __int8 **v9; // rdi
  char v10; // r14
  int v11; // r14d
  __int64 v12; // rsi
  WCHAR v13; // di
  unsigned int i; // edi
  unsigned int *v15; // rax
  BYTE *lpData; // r14
  HKEY v17; // rcx
  PWSTR v18; // rax
  unsigned __int64 v19; // rdx
  const BYTE *v20; // rcx
  unsigned int ValueName; // [rsp+70h] [rbp+8h] BYREF
  BYTE *v23; // [rsp+78h] [rbp+10h]

  v23 = a2;
  v5 = a2;
  if ( a1 )
  {
    v6 = (char *)a1 + 32;
    v7 = *((_DWORD *)a1 + 1);
    v8 = 0;
    v9 = (unsigned __int8 **)((char *)a1 + 32);
    v10 = ~(unsigned __int8)(*(_DWORD *)a1 >> 1);
    ValueName = v7;
    v11 = v10 & 1;
    while ( 1 )
    {
      v12 = -1;
      if ( v8 >= v7 )
        break;
      if ( *v9 )
      {
        if ( (unsigned int)OEMRUIsSameData(a1, *v9, v5, a3) )
        {
          v13 = v8 + 97;
LABEL_20:
          v18 = StrChrW(*((PCWSTR *)a1 + 3), v13);
          if ( v18 )
          {
            v19 = -1;
            do
              ++v19;
            while ( v18[v19] );
            StringCchCopyW(v18, v19, v18 + 1);
          }
          if ( v8 != -1 )
          {
            RtlMoveMemory(*((_QWORD *)a1 + 3) + 2LL, *((_QWORD *)a1 + 3), (unsigned int)(2 * *((_DWORD *)a1 + 1)));
            **((_WORD **)a1 + 3) = v13;
          }
          if ( v11 )
          {
            v20 = (const BYTE *)*((_QWORD *)a1 + 3);
            do
              ++v12;
            while ( *(_WORD *)&v20[2 * v12] );
            RegSetValueExW(*((HKEY *)a1 + 2), L"MRUList", 0, 1u, v20, 2 * v12 + 2);
            *(_DWORD *)a1 &= ~0x1000u;
          }
          else
          {
            *(_DWORD *)a1 |= 0x1000u;
          }
          return v8;
        }
        v7 = ValueName;
        v5 = v23;
      }
      ++v8;
      ++v9;
    }
    if ( (*(_DWORD *)a1 & 0x8000) == 0 )
    {
      for ( i = 0; i < v7; ++i )
      {
        if ( !*(_QWORD *)v6 )
        {
          v13 = i + 97;
          goto LABEL_16;
        }
        v6 += 8;
      }
      _mm_lfence();
      v13 = *(_WORD *)(*((_QWORD *)a1 + 3) + 2LL * (v7 - 1));
      v6 = (char *)a1 + 8 * v13 - 744;
LABEL_16:
      if ( a3 + 4 >= a3 )
      {
        v15 = (unsigned int *)((__int64 (__fastcall *)(LPMALLOC, _QWORD, _QWORD))g_pMalloc->lpVtbl->Realloc)(
                                g_pMalloc,
                                *(_QWORD *)v6,
                                a3 + 4);
        if ( v15 )
        {
          lpData = v23;
          *(_QWORD *)v6 = v15;
          *v15 = a3;
          RtlMoveMemory(*(_QWORD *)v6 + 4LL, lpData, a3);
          v17 = (HKEY)*((_QWORD *)a1 + 2);
          v8 = v13 - 97;
          ValueName = v13;
          RegSetValueExW(v17, (LPCWSTR)&ValueName, 0, 3u, lpData, a3);
          v11 = 1;
        }
        else
        {
          v8 = -1;
        }
        goto LABEL_20;
      }
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000d640  mov     [rsp+arg_10], rbx
0x18000d645  mov     [rsp+arg_8], rdx
0x18000d64a  push    rbp
0x18000d64b  push    rsi
0x18000d64c  push    rdi
0x18000d64d  push    r12
0x18000d64f  push    r13
0x18000d651  push    r14
0x18000d653  push    r15
0x18000d655  sub     rsp, 30h
0x18000d659  mov     rbx, rcx
0x18000d65c  mov     r13d, r8d
0x18000d65f  xor     ecx, ecx
0x18000d661  mov     r8, rdx; void *
0x18000d664  test    rbx, rbx
0x18000d667  jz      loc_18000D82D
0x18000d66d  mov     r14d, [rbx]
0x18000d670  lea     r15, [rbx+20h]
0x18000d674  mov     eax, [rbx+4]
0x18000d677  mov     ebp, ecx
0x18000d679  shr     r14d, 1
0x18000d67c  mov     rdi, r15
0x18000d67f  not     r14d
0x18000d682  mov     [rsp+68h+ValueName], eax
0x18000d686  and     r14d, 1
0x18000d68a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000d68e  cmp     ebp, eax
0x18000d690  jnb     short loc_18000D6C8
0x18000d692  mov     rdx, [rdi]; unsigned __int8 *
0x18000d695  test    rdx, rdx
0x18000d698  jz      short loc_18000D6B4
0x18000d69a  mov     r9d, r13d; unsigned int
0x18000d69d  mov     rcx, rbx; struct tagOEMRUDATA *
0x18000d6a0  call    ?OEMRUIsSameData@@YAHPEAUtagOEMRUDATA@@PEAEPEBXI@Z; OEMRUIsSameData(tagOEMRUDATA *,uchar *,void const *,uint)
0x18000d6a5  xor     ecx, ecx
0x18000d6a7  test    eax, eax
0x18000d6a9  jnz     short loc_18000D6BC
0x18000d6ab  mov     eax, [rsp+68h+ValueName]
0x18000d6af  mov     r8, [rsp+68h+arg_8]
0x18000d6b4  inc     ebp
0x18000d6b6  add     rdi, 8
0x18000d6ba  jmp     short loc_18000D68A
0x18000d6bc  mov     edi, 61h ; 'a'
0x18000d6c1  add     edi, ebp
0x18000d6c3  jmp     loc_18000D794
0x18000d6c8  test    dword ptr [rbx], 8000h
0x18000d6ce  jnz     loc_18000D831
0x18000d6d4  mov     edi, ecx
0x18000d6d6  mov     r12d, 61h ; 'a'
0x18000d6dc  cmp     edi, eax
0x18000d6de  jnb     short loc_18000D6F3
0x18000d6e0  cmp     [r15], rcx
0x18000d6e3  jz      short loc_18000D6ED
0x18000d6e5  inc     edi
0x18000d6e7  add     r15, 8
0x18000d6eb  jmp     short loc_18000D6D6
0x18000d6ed  add     di, r12w
0x18000d6f1  jmp     short loc_18000D70F
0x18000d6f3  lfence
0x18000d6f6  lea     ecx, [rax-1]
0x18000d6f9  mov     rax, [rbx+18h]
0x18000d6fd  lea     r15, [rbx-2E8h]
0x18000d704  movzx   edx, word ptr [rax+rcx*2]
0x18000d708  movzx   edi, dx
0x18000d70b  lea     r15, [r15+rdx*8]
0x18000d70f  lea     edx, [r13+4]
0x18000d713  cmp     edx, r13d
0x18000d716  jb      loc_18000D831
0x18000d71c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000d723  mov     r8d, edx
0x18000d726  mov     rdx, [r15]
0x18000d729  mov     rax, [rcx]
0x18000d72c  mov     rax, [rax+20h]
0x18000d730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d735  test    rax, rax
0x18000d738  jnz     short loc_18000D73E
0x18000d73a  mov     ebp, esi
0x18000d73c  jmp     short loc_18000D794
0x18000d73e  mov     r14, [rsp+68h+arg_8]
0x18000d743  mov     r8d, r13d
0x18000d746  mov     [r15], rax
0x18000d749  mov     rdx, r14
0x18000d74c  mov     [rax], r13d
0x18000d74f  mov     rcx, [r15]
0x18000d752  add     rcx, 4
0x18000d756  call    cs:__imp_RtlMoveMemory
0x18000d75c  mov     rcx, [rbx+10h]; hKey
0x18000d760  lea     rdx, [rsp+68h+ValueName]; lpValueName
0x18000d765  xor     eax, eax
0x18000d767  movzx   ebp, di
0x18000d76a  sub     ebp, r12d
0x18000d76d  mov     [rsp+68h+cbData], r13d; cbData
0x18000d772  xor     r8d, r8d; Reserved
0x18000d775  mov     word ptr [rsp+68h+ValueName], di
0x18000d77a  mov     word ptr [rsp+68h+ValueName+2], ax
0x18000d77f  lea     r9d, [rax+3]; dwType
0x18000d783  mov     [rsp+68h+lpData], r14; lpData
0x18000d788  call    cs:__imp_RegSetValueExW
0x18000d78e  mov     r14d, 1
0x18000d794  mov     rcx, [rbx+18h]; pszStart
0x18000d798  movzx   edx, di; wMatch
0x18000d79b  call    cs:__imp_StrChrW
0x18000d7a1  xor     r13d, r13d
0x18000d7a4  test    rax, rax
0x18000d7a7  jz      short loc_18000D7C2
0x18000d7a9  mov     rdx, rsi
0x18000d7ac  inc     rdx; unsigned __int64
0x18000d7af  cmp     [rax+rdx*2], r13w
0x18000d7b4  jnz     short loc_18000D7AC
0x18000d7b6  lea     r8, [rax+2]; unsigned __int16 *
0x18000d7ba  mov     rcx, rax; unsigned __int16 *
0x18000d7bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d7c2  cmp     ebp, esi
0x18000d7c4  jz      short loc_18000D7E2
0x18000d7c6  mov     rdx, [rbx+18h]
0x18000d7ca  mov     r8d, [rbx+4]
0x18000d7ce  add     r8d, r8d
0x18000d7d1  lea     rcx, [rdx+2]
0x18000d7d5  call    cs:__imp_RtlMoveMemory
0x18000d7db  mov     rax, [rbx+18h]
0x18000d7df  mov     [rax], di
0x18000d7e2  test    r14d, r14d
0x18000d7e5  jz      short loc_18000D825
0x18000d7e7  mov     rcx, [rbx+18h]
0x18000d7eb  inc     rsi
0x18000d7ee  cmp     [rcx+rsi*2], r13w
0x18000d7f3  jnz     short loc_18000D7EB
0x18000d7f5  lea     eax, ds:2[rsi*2]
0x18000d7fc  mov     r9d, 1; dwType
0x18000d802  mov     [rsp+68h+cbData], eax; cbData
0x18000d806  lea     rdx, aMrulist; "MRUList"
0x18000d80d  mov     [rsp+68h+lpData], rcx; lpData
0x18000d812  xor     r8d, r8d; Reserved
0x18000d815  mov     rcx, [rbx+10h]; hKey
0x18000d819  call    cs:__imp_RegSetValueExW
0x18000d81f  btr     dword ptr [rbx], 0Ch
0x18000d823  jmp     short loc_18000D829
0x18000d825  bts     dword ptr [rbx], 0Ch
0x18000d829  mov     eax, ebp
0x18000d82b  jmp     short loc_18000D833
0x18000d82d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000d831  mov     eax, esi
0x18000d833  mov     rbx, [rsp+68h+arg_10]
0x18000d83b  add     rsp, 30h
0x18000d83f  pop     r15
0x18000d841  pop     r14
0x18000d843  pop     r13
0x18000d845  pop     r12
0x18000d847  pop     rdi
0x18000d848  pop     rsi
0x18000d849  pop     rbp
0x18000d84a  retn
```
