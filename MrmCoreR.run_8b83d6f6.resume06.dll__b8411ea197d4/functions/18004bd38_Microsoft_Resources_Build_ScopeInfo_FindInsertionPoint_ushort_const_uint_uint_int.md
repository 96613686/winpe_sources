# Microsoft::Resources::Build::ScopeInfo::FindInsertionPoint(ushort const *,uint,uint,int *)

- ea: `0x18004bd38`
- end: `0x18004bf8a`
- name: `?FindInsertionPoint@ScopeInfo@Build@Resources@Microsoft@@IEBAIPEBGIIPEAH@Z`
- size: `594`
- prototype: `unsigned int(Microsoft::Resources::Build::ScopeInfo *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004b3fc`
- `0x18004bac4`

## callees

- `0x180028ad0`
- `0x180042f70`
- `0x18004bd38`
- `0x18004c6b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004bdbb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004bdfe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004be50`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004bdbb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004bdfe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004be50`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Build::ScopeInfo::FindInsertionPoint(
        Microsoft::Resources::Build::ScopeInfo *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        int *a5)
{
  __int64 v5; // rbx
  int v6; // esi
  int v7; // ebp
  unsigned int v8; // r15d
  unsigned int v9; // edi
  const WCHAR *v10; // r10
  Microsoft::Resources::Build::ScopeInfo *v11; // rax
  unsigned int v12; // r12d
  __int64 v13; // rdx
  __int64 v14; // r14
  __int64 v15; // r8
  __int64 v16; // r13
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // r8
  int v22; // eax
  int v23; // eax
  bool v25; // zf
  _QWORD v26[9]; // [rsp+30h] [rbp-48h] BYREF

  v5 = (a3 + a4) >> 1;
  v6 = 0x7FFFFFFF;
  v7 = a4 - a3 + 1;
  v8 = a4;
  v9 = a3;
  v10 = a2;
  v11 = this;
  v12 = 0x7FFFFFFF;
  while ( 1 )
  {
    v13 = *((_QWORD *)v11 + 7);
    v14 = 0;
    v26[0] = 0;
    if ( v9 < *(_DWORD *)(v13 + 12) )
    {
      v14 = *(_QWORD *)(*(_QWORD *)v13 + 8LL * v9);
      v26[0] = v14;
      v15 = v14;
    }
    else
    {
      v15 = 0;
    }
    if ( v8 < *(_DWORD *)(v13 + 12) )
      v16 = *(_QWORD *)(*(_QWORD *)v13 + 8LL * v8);
    else
      v16 = 0;
    if ( v6 == 0x7FFFFFFF )
    {
      v17 = CompareStringOrdinal(v10, -1, *(LPCWCH *)(v15 + 24), -1, 1);
      v18 = IntToComparison((unsigned int)(v17 - 2));
      v10 = a2;
      v6 = v18;
    }
    if ( (unsigned int)(v6 + 1) <= 1 )
      break;
    if ( v12 == 0x7FFFFFFF )
    {
      v19 = CompareStringOrdinal(v10, -1, *(LPCWCH *)(v16 + 24), -1, 1);
      v12 = IntToComparison((unsigned int)(v19 - 2));
    }
    if ( v12 <= 1 )
    {
      *a5 = v12;
      return v8;
    }
    if ( v7 <= 3 )
    {
      while ( v14 )
      {
        if ( v6 == 0x7FFFFFFF )
          v6 = DefString_CompareWithOptions(a2, *(_QWORD *)(v14 + 24), 1);
        if ( v6 != 1 || v14 == v16 )
          goto LABEL_29;
        Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(
          *((_QWORD *)this + 7),
          ++v9,
          v26);
        v14 = v26[0];
        v6 = 0x7FFFFFFF;
      }
LABEL_23:
      v11 = this;
      v10 = a2;
    }
    else
    {
      v20 = *((_QWORD *)this + 7);
      if ( (unsigned int)v5 < *(_DWORD *)(v20 + 12) )
        v21 = *(_QWORD *)(*(_QWORD *)v20 + 8 * v5);
      else
        v21 = 0;
      v22 = CompareStringOrdinal(a2, -1, *(LPCWCH *)(v21 + 24), -1, 1);
      v23 = IntToComparison((unsigned int)(v22 - 2));
      if ( !v23 )
      {
        *a5 = 0;
        return (unsigned int)v5;
      }
      if ( v23 == -1 )
      {
        v8 = v5;
        v5 = (v9 + (unsigned int)v5) >> 1;
        v7 = v8 - v9 + 1;
        v12 = -1;
        goto LABEL_23;
      }
      v10 = a2;
      v25 = v23 == 1;
      v11 = this;
      if ( v25 )
      {
        v9 = v5;
        v5 = (v8 + (unsigned int)v5) >> 1;
        v6 = 1;
        v7 = v8 - v9 + 1;
        goto LABEL_23;
      }
    }
  }
LABEL_29:
  *a5 = v6;
  return v9;
}

```

## disassembly

```asm
0x18004bd38  mov     [rsp+arg_10], rbx
0x18004bd3d  mov     [rsp+lpString1], rdx
0x18004bd42  mov     [rsp+arg_0], rcx
0x18004bd47  push    rbp
0x18004bd48  push    rsi
0x18004bd49  push    rdi
0x18004bd4a  push    r12
0x18004bd4c  push    r13
0x18004bd4e  push    r14
0x18004bd50  push    r15
0x18004bd52  sub     rsp, 40h
0x18004bd56  lea     ebx, [r8+r9]
0x18004bd5a  mov     ebp, r9d
0x18004bd5d  shr     ebx, 1
0x18004bd5f  sub     ebp, r8d
0x18004bd62  mov     esi, 7FFFFFFFh
0x18004bd67  inc     ebp
0x18004bd69  mov     r15d, r9d
0x18004bd6c  mov     edi, r8d
0x18004bd6f  mov     r10, rdx
0x18004bd72  mov     rax, rcx
0x18004bd75  mov     r12d, esi
0x18004bd78  mov     rdx, [rax+38h]
0x18004bd7c  xor     r14d, r14d
0x18004bd7f  mov     [rsp+78h+var_48], r14
0x18004bd84  cmp     edi, [rdx+0Ch]
0x18004bd87  jb      loc_18004BE86
0x18004bd8d  xor     r8d, r8d
0x18004bd90  cmp     r15d, [rdx+0Ch]
0x18004bd94  jb      loc_18004BE9C
0x18004bd9a  xor     r13d, r13d
0x18004bd9d  cmp     esi, 7FFFFFFFh
0x18004bda3  jnz     short loc_18004BDD3
0x18004bda5  mov     r8, [r8+18h]; lpString2
0x18004bda9  or      r9d, 0FFFFFFFFh; cchCount2
0x18004bdad  or      edx, r9d; cchCount1
0x18004bdb0  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18004bdb8  mov     rcx, r10; lpString1
0x18004bdbb  call    cs:__imp_CompareStringOrdinal
0x18004bdc1  lea     ecx, [rax-2]
0x18004bdc4  call    _IntToComparison
0x18004bdc9  mov     r10, [rsp+78h+lpString1]
0x18004bdd1  mov     esi, eax
0x18004bdd3  lea     eax, [rsi+1]
0x18004bdd6  cmp     eax, 1
0x18004bdd9  jbe     loc_18004BF1F
0x18004bddf  cmp     r12d, 7FFFFFFFh
0x18004bde6  jnz     short loc_18004BE0F
0x18004bde8  mov     r8, [r13+18h]; lpString2
0x18004bdec  or      r9d, 0FFFFFFFFh; cchCount2
0x18004bdf0  or      edx, r9d; cchCount1
0x18004bdf3  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18004bdfb  mov     rcx, r10; lpString1
0x18004bdfe  call    cs:__imp_CompareStringOrdinal
0x18004be04  lea     ecx, [rax-2]
0x18004be07  call    _IntToComparison
0x18004be0c  mov     r12d, eax
0x18004be0f  cmp     r12d, 1
0x18004be13  jbe     loc_18004BEFA
0x18004be19  cmp     ebp, 3
0x18004be1c  jle     loc_18004BF0D
0x18004be22  mov     rax, [rsp+78h+arg_0]
0x18004be2a  mov     rax, [rax+38h]
0x18004be2e  cmp     ebx, [rax+0Ch]
0x18004be31  jb      short loc_18004BEAB
0x18004be33  xor     r8d, r8d
0x18004be36  mov     r8, [r8+18h]; lpString2
0x18004be3a  or      edx, 0FFFFFFFFh; cchCount1
0x18004be3d  mov     rcx, [rsp+78h+lpString1]; lpString1
0x18004be45  mov     r9d, edx; cchCount2
0x18004be48  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18004be50  call    cs:__imp_CompareStringOrdinal
0x18004be56  lea     ecx, [rax-2]
0x18004be59  call    _IntToComparison
0x18004be5e  test    eax, eax
0x18004be60  jnz     short loc_18004BEB4
0x18004be62  mov     rcx, [rsp+78h+arg_20]
0x18004be6a  mov     [rcx], eax
0x18004be6c  mov     eax, ebx
0x18004be6e  mov     rbx, [rsp+78h+arg_10]
0x18004be76  add     rsp, 40h
0x18004be7a  pop     r15
0x18004be7c  pop     r14
0x18004be7e  pop     r13
0x18004be80  pop     r12
0x18004be82  pop     rdi
0x18004be83  pop     rsi
0x18004be84  pop     rbp
0x18004be85  retn
0x18004be86  mov     rax, [rdx]
0x18004be89  mov     ecx, edi
0x18004be8b  mov     r14, [rax+rcx*8]
0x18004be8f  mov     [rsp+78h+var_48], r14
0x18004be94  mov     r8, r14
0x18004be97  jmp     loc_18004BD90
0x18004be9c  mov     rax, [rdx]
0x18004be9f  mov     ecx, r15d
0x18004bea2  mov     r13, [rax+rcx*8]
0x18004bea6  jmp     loc_18004BD9D
0x18004beab  mov     rax, [rax]
0x18004beae  mov     r8, [rax+rbx*8]
0x18004beb2  jmp     short loc_18004BE36
0x18004beb4  cmp     eax, 0FFFFFFFFh
0x18004beb7  jz      short loc_18004BF30
0x18004beb9  mov     r10, [rsp+78h+lpString1]
0x18004bec1  cmp     eax, 1
0x18004bec4  mov     rax, [rsp+78h+arg_0]
0x18004becc  jnz     loc_18004BD78
0x18004bed2  mov     edi, ebx
0x18004bed4  mov     ebp, r15d
0x18004bed7  add     ebx, r15d
0x18004beda  sub     ebp, edi
0x18004bedc  shr     ebx, 1
0x18004bede  mov     esi, 1
0x18004bee3  inc     ebp
0x18004bee5  mov     rax, [rsp+78h+arg_0]
0x18004beed  mov     r10, [rsp+78h+lpString1]
0x18004bef5  jmp     loc_18004BD78
0x18004befa  mov     rax, [rsp+78h+arg_20]
0x18004bf02  mov     [rax], r12d
0x18004bf05  mov     eax, r15d
0x18004bf08  jmp     loc_18004BE6E
0x18004bf0d  test    r14, r14
0x18004bf10  jz      short loc_18004BEE5
0x18004bf12  cmp     esi, 7FFFFFFFh
0x18004bf18  jz      short loc_18004BF44
0x18004bf1a  cmp     esi, 1
0x18004bf1d  jz      short loc_18004BF5F
0x18004bf1f  mov     rax, [rsp+78h+arg_20]
0x18004bf27  mov     [rax], esi
0x18004bf29  mov     eax, edi
0x18004bf2b  jmp     loc_18004BE6E
0x18004bf30  mov     r15d, ebx
0x18004bf33  add     ebx, edi
0x18004bf35  mov     ebp, r15d
0x18004bf38  shr     ebx, 1
0x18004bf3a  sub     ebp, edi
0x18004bf3c  inc     ebp
0x18004bf3e  or      r12d, 0FFFFFFFFh
0x18004bf42  jmp     short loc_18004BEE5
0x18004bf44  mov     rdx, [r14+18h]
0x18004bf48  mov     r8d, 1
0x18004bf4e  mov     rcx, [rsp+78h+lpString1]
0x18004bf56  call    DefString_CompareWithOptions
0x18004bf5b  mov     esi, eax
0x18004bf5d  jmp     short loc_18004BF1A
0x18004bf5f  cmp     r14, r13
0x18004bf62  jz      short loc_18004BF1F
0x18004bf64  mov     rax, [rsp+78h+arg_0]
0x18004bf6c  lea     r8, [rsp+78h+var_48]
0x18004bf71  inc     edi
0x18004bf73  mov     edx, edi
0x18004bf75  mov     rcx, [rax+38h]
0x18004bf79  call    ?Get@?$DynamicArray@PEAVPackageIndexMap@DynamicPackageProfile@Resources@Microsoft@@@Resources@Microsoft@@QEBAJIPEAPEAVPackageIndexMap@DynamicPackageProfile@23@@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(uint,Microsoft::Resources::DynamicPackageProfile::PackageIndexMap * *)
0x18004bf7e  mov     r14, [rsp+78h+var_48]
0x18004bf83  mov     esi, 7FFFFFFFh
0x18004bf88  jmp     short loc_18004BF0D
```
