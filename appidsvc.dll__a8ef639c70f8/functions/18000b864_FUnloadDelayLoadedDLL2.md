# __FUnloadDelayLoadedDLL2

- ea: `0x18000b864`
- end: `0x18000ba59`
- name: `__FUnloadDelayLoadedDLL2`
- size: `501`
- prototype: `BOOL __stdcall(LPCSTR szDll)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003c80`

## callees

- `0x18000b780`
- `0x18000b864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b92d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b92d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b95c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b95c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9f0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b9a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b9a6`

## string_xrefs

- `0x18000b895`: `DiagnosticDataSettings.dll`

## pseudocode

```c
BOOL __stdcall _FUnloadDelayLoadedDLL2(LPCSTR szDll)
{
  PUnloadInfo v1; // rbx
  BOOL v2; // r9d
  _BYTE *v3; // r8
  _BYTE *v4; // rcx
  const char *v6; // rdx
  __int64 v7; // rcx
  const char *i; // rdx
  unsigned int *p_grAttrs; // rdi
  __int64 v11; // rsi
  HMODULE v12; // rbp
  unsigned int v13; // ecx
  char *v14; // r9
  char *v15; // r8
  char *j; // rax
  __int64 k; // rdx
  char v18; // al
  PUnloadInfo v19; // rcx
  PUnloadInfo *p_puiNext; // rdx
  HANDLE ProcessHeap; // rax
  LPCSTR flOldProtect; // [rsp+40h] [rbp+8h] BYREF

  flOldProtect = szDll;
  v1 = _puiHead;
  v2 = 0;
  if ( _puiHead )
  {
    do
    {
      v3 = (char *)&_ImageBase + v1->pidd->rvaDLLName;
      v4 = v3;
      while ( *v4++ )
        ;
      v6 = "DiagnosticDataSettings.dll";
      v7 = v4 - v3 - 1;
      while ( *v6++ )
        ;
      if ( v7 == v6 - "DiagnosticDataSettings.dll" - 1 )
      {
        if ( !v7 )
          break;
        for ( i = "DiagnosticDataSettings.dll"; --v7 && *i == *v3; ++i )
          ++v3;
        if ( *i == *v3 )
          break;
      }
      v1 = v1->puiNext;
    }
    while ( v1 );
    if ( v1 )
    {
      p_grAttrs = &v1->pidd->grAttrs;
      if ( p_grAttrs[6] )
      {
        v11 = p_grAttrs[2];
        v12 = *(HMODULE *)((char *)&_ImageBase + v11);
        AcquireSRWLockExclusive(&DloadSrwLock);
        if ( ++DloadSectionLockCount == 1 )
          DloadProtectSection(4u, &DloadSectionOldProtection);
        ReleaseSRWLockExclusive(&DloadSrwLock);
        v13 = 0;
        v14 = (char *)&_ImageBase + p_grAttrs[3];
        v15 = (char *)&_ImageBase + p_grAttrs[6];
        for ( j = v14; *(_QWORD *)j; ++v13 )
          j += 8;
        for ( k = 8LL * v13; k; --k )
        {
          v18 = *v15++;
          *v14++ = v18;
        }
        FreeLibrary(v12);
        v19 = _puiHead;
        *(_QWORD *)((char *)&_ImageBase + v11) = 0;
        if ( v19 )
        {
          p_puiNext = &_puiHead;
          while ( v19 != v1 )
          {
            p_puiNext = &v19->puiNext;
            v19 = v19->puiNext;
            if ( !v19 )
              goto LABEL_28;
          }
          *p_puiNext = v1->puiNext;
        }
LABEL_28:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v1);
        LODWORD(flOldProtect) = 0;
        AcquireSRWLockExclusive(&DloadSrwLock);
        if ( !--DloadSectionLockCount )
          DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
        ReleaseSRWLockExclusive(&DloadSrwLock);
        return 1;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000b864  mov     [rsp+arg_10], rbx
0x18000b869  mov     [rsp+arg_18], rbp
0x18000b86e  mov     [rsp+flOldProtect], rcx
0x18000b873  push    rsi
0x18000b874  push    rdi
0x18000b875  push    r13
0x18000b877  sub     rsp, 20h
0x18000b87b  mov     rbx, cs:__puiHead
0x18000b882  xor     r9d, r9d
0x18000b885  test    rbx, rbx
0x18000b888  jz      loc_18000BA43
0x18000b88e  lea     r13, __ImageBase
0x18000b895  lea     r10, aDiagnosticdata_0; "DiagnosticDataSettings.dll"
0x18000b89c  mov     rax, [rbx+8]
0x18000b8a0  mov     r8d, [rax+4]
0x18000b8a4  add     r8, r13
0x18000b8a7  mov     rcx, r8
0x18000b8aa  mov     al, [rcx]
0x18000b8ac  inc     rcx
0x18000b8af  test    al, al
0x18000b8b1  jnz     short loc_18000B8AA
0x18000b8b3  sub     rcx, r8
0x18000b8b6  mov     rdx, r10
0x18000b8b9  dec     rcx
0x18000b8bc  mov     al, [rdx]
0x18000b8be  inc     rdx
0x18000b8c1  test    al, al
0x18000b8c3  jnz     short loc_18000B8BC
0x18000b8c5  sub     rdx, r10
0x18000b8c8  dec     rdx
0x18000b8cb  cmp     rcx, rdx
0x18000b8ce  jnz     short loc_18000B8F4
0x18000b8d0  test    rcx, rcx
0x18000b8d3  jz      short loc_18000B8FC
0x18000b8d5  mov     rdx, r10
0x18000b8d8  jmp     short loc_18000B8E7
0x18000b8da  mov     al, [r8]
0x18000b8dd  cmp     [rdx], al
0x18000b8df  jnz     short loc_18000B8ED
0x18000b8e1  inc     rdx
0x18000b8e4  inc     r8
0x18000b8e7  sub     rcx, 1
0x18000b8eb  jnz     short loc_18000B8DA
0x18000b8ed  mov     cl, [r8]
0x18000b8f0  cmp     [rdx], cl
0x18000b8f2  jz      short loc_18000B8FC
0x18000b8f4  mov     rbx, [rbx]
0x18000b8f7  test    rbx, rbx
0x18000b8fa  jnz     short loc_18000B89C
0x18000b8fc  test    rbx, rbx
0x18000b8ff  jz      loc_18000BA43
0x18000b905  mov     rdi, [rbx+8]
0x18000b909  cmp     [rdi+18h], r9d
0x18000b90d  jz      loc_18000BA43
0x18000b913  test    cs:dword_18000EA60, 1000h
0x18000b91d  mov     esi, [rdi+8]
0x18000b920  mov     rbp, [rsi+r13]
0x18000b924  jz      short loc_18000B962
0x18000b926  lea     rcx, DloadSrwLock; SRWLock
0x18000b92d  call    cs:__imp_AcquireSRWLockExclusive
0x18000b933  mov     eax, cs:DloadSectionLockCount
0x18000b939  inc     eax
0x18000b93b  mov     cs:DloadSectionLockCount, eax
0x18000b941  cmp     eax, 1
0x18000b944  jnz     short loc_18000B955
0x18000b946  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000b94d  lea     ecx, [rax+3]; flNewProtect
0x18000b950  call    DloadProtectSection
0x18000b955  lea     rcx, DloadSrwLock; SRWLock
0x18000b95c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b962  mov     r9d, [rdi+0Ch]
0x18000b966  xor     ecx, ecx
0x18000b968  mov     r8d, [rdi+18h]
0x18000b96c  add     r9, r13
0x18000b96f  add     r8, r13
0x18000b972  mov     rax, r9
0x18000b975  cmp     [r9], rcx
0x18000b978  jz      short loc_18000B986
0x18000b97a  lea     rax, [rax+8]
0x18000b97e  inc     ecx
0x18000b980  cmp     qword ptr [rax], 0
0x18000b984  jnz     short loc_18000B97A
0x18000b986  mov     edx, ecx
0x18000b988  shl     rdx, 3
0x18000b98c  test    rdx, rdx
0x18000b98f  jz      short loc_18000B9A3
0x18000b991  mov     al, [r8]
0x18000b994  inc     r8
0x18000b997  mov     [r9], al
0x18000b99a  inc     r9
0x18000b99d  sub     rdx, 1
0x18000b9a1  jnz     short loc_18000B991
0x18000b9a3  mov     rcx, rbp; hLibModule
0x18000b9a6  call    cs:__imp_FreeLibrary
0x18000b9ac  mov     rcx, cs:__puiHead
0x18000b9b3  mov     qword ptr [rsi+r13], 0
0x18000b9bb  test    rcx, rcx
0x18000b9be  jz      short loc_18000B9E2
0x18000b9c0  lea     rdx, __puiHead
0x18000b9c7  cmp     rcx, rbx
0x18000b9ca  jz      short loc_18000B9DC
0x18000b9cc  mov     rax, [rcx]
0x18000b9cf  mov     rdx, rcx
0x18000b9d2  mov     rcx, rax
0x18000b9d5  test    rax, rax
0x18000b9d8  jnz     short loc_18000B9C7
0x18000b9da  jmp     short loc_18000B9E2
0x18000b9dc  mov     rax, [rbx]
0x18000b9df  mov     [rdx], rax
0x18000b9e2  call    cs:__imp_GetProcessHeap
0x18000b9e8  mov     r8, rbx; lpMem
0x18000b9eb  xor     edx, edx; dwFlags
0x18000b9ed  mov     rcx, rax; hHeap
0x18000b9f0  call    cs:__imp_HeapFree
0x18000b9f6  test    cs:dword_18000EA60, 1000h
0x18000ba00  mov     dword ptr [rsp+38h+flOldProtect], 0
0x18000ba08  jz      short loc_18000BA3D
0x18000ba0a  lea     rcx, DloadSrwLock; SRWLock
0x18000ba11  call    cs:__imp_AcquireSRWLockExclusive
0x18000ba17  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000ba1e  jnz     short loc_18000BA30
0x18000ba20  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000ba26  lea     rdx, [rsp+38h+flOldProtect]; lpflOldProtect
0x18000ba2b  call    DloadProtectSection
0x18000ba30  lea     rcx, DloadSrwLock; SRWLock
0x18000ba37  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba3d  mov     r9d, 1
0x18000ba43  mov     rbx, [rsp+38h+arg_10]
0x18000ba48  mov     eax, r9d
0x18000ba4b  mov     rbp, [rsp+38h+arg_18]
0x18000ba50  add     rsp, 20h
0x18000ba54  pop     r13
0x18000ba56  pop     rdi
0x18000ba57  pop     rsi
0x18000ba58  retn
```
