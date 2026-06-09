# DefStringResult_CompareWithOptions

- ea: `0x180046b84`
- end: `0x180046c4b`
- name: `DefStringResult_CompareWithOptions`
- size: `199`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180045c3c`
- `0x180045cd0`
- `0x180045f44`
- `0x18004743c`
- `0x180098fe0`
- `0x1800a57f0`
- `0x1800ba180`

## callees

- `0x180028ad0`
- `0x180046b84`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046be8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046c32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046be8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046c32`

## pseudocode

```c
__int64 __fastcall DefStringResult_CompareWithOptions(__int64 a1, const WCHAR *a2, char a3, int *a4)
{
  int v4; // ebx
  const WCHAR *v6; // rcx
  int v7; // eax
  int v9; // eax

  v4 = 0x7FFFFFFF;
  *a4 = 0x7FFFFFFF;
  if ( !a1 || !*(_QWORD *)a1 && *(_DWORD *)(a1 + 8) || !*(_DWORD *)(a1 + 8) && *(_QWORD *)a1 )
    return 2147942487LL;
  v6 = *(const WCHAR **)(a1 + 16);
  if ( v6 )
  {
    if ( a2 )
    {
      if ( (a3 & 1) != 0 )
      {
        v7 = CompareStringOrdinal(v6, -1, a2, -1, 1) - 2;
        if ( v7 != 0x7FFFFFFF )
        {
          if ( v7 < 0 )
            v4 = -1;
          else
            v4 = v7 > 0;
        }
        *a4 = v4;
      }
      else
      {
        v9 = CompareStringOrdinal(v6, -1, a2, -1, 0);
        *a4 = IntToComparison((unsigned int)(v9 - 2));
      }
    }
    else
    {
      *a4 = 1;
    }
  }
  else
  {
    *a4 = -(a2 != 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180046b84  mov     [rsp+arg_0], rbx
0x180046b89  push    rdi
0x180046b8a  sub     rsp, 30h
0x180046b8e  mov     ebx, 7FFFFFFFh
0x180046b93  mov     rdi, r9
0x180046b96  mov     [r9], ebx
0x180046b99  test    rcx, rcx
0x180046b9c  jz      loc_180046C44
0x180046ba2  cmp     qword ptr [rcx], 0
0x180046ba6  jnz     short loc_180046BB2
0x180046ba8  cmp     dword ptr [rcx+8], 0
0x180046bac  ja      loc_180046C44
0x180046bb2  cmp     dword ptr [rcx+8], 0
0x180046bb6  jnz     short loc_180046BC2
0x180046bb8  cmp     qword ptr [rcx], 0
0x180046bbc  jnz     loc_180046C44
0x180046bc2  mov     rcx, [rcx+10h]; lpString1
0x180046bc6  test    rcx, rcx
0x180046bc9  jz      short loc_180046C1D
0x180046bcb  test    rdx, rdx
0x180046bce  jz      short loc_180046C14
0x180046bd0  or      r9d, 0FFFFFFFFh; cchCount2
0x180046bd4  test    r8b, 1
0x180046bd8  mov     r8, rdx; lpString2
0x180046bdb  jz      short loc_180046C27
0x180046bdd  or      edx, r9d; cchCount1
0x180046be0  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180046be8  call    cs:__imp_CompareStringOrdinal
0x180046bee  add     eax, 0FFFFFFFEh
0x180046bf1  cmp     eax, ebx
0x180046bf3  jz      short loc_180046C00
0x180046bf5  test    eax, eax
0x180046bf7  js      short loc_180046C0F
0x180046bf9  xor     ebx, ebx
0x180046bfb  test    eax, eax
0x180046bfd  setnle  bl
0x180046c00  mov     [rdi], ebx
0x180046c02  xor     eax, eax
0x180046c04  mov     rbx, [rsp+38h+arg_0]
0x180046c09  add     rsp, 30h
0x180046c0d  pop     rdi
0x180046c0e  retn
0x180046c0f  or      ebx, 0FFFFFFFFh
0x180046c12  jmp     short loc_180046C00
0x180046c14  mov     dword ptr [r9], 1
0x180046c1b  jmp     short loc_180046C02
0x180046c1d  neg     rdx
0x180046c20  sbb     eax, eax
0x180046c22  mov     [r9], eax
0x180046c25  jmp     short loc_180046C02
0x180046c27  or      edx, 0FFFFFFFFh; cchCount1
0x180046c2a  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180046c32  call    cs:__imp_CompareStringOrdinal
0x180046c38  lea     ecx, [rax-2]
0x180046c3b  call    _IntToComparison
0x180046c40  mov     [rdi], eax
0x180046c42  jmp     short loc_180046C02
0x180046c44  mov     eax, 80070057h
0x180046c49  jmp     short loc_180046C04
```
