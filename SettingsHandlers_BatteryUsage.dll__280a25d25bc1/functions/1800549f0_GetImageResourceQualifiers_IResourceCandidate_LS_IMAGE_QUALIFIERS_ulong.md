# _GetImageResourceQualifiers(IResourceCandidate *,LS_IMAGE_QUALIFIERS *,ulong *)

- ea: `0x1800549f0`
- end: `0x180054b32`
- name: `?_GetImageResourceQualifiers@@YAXPEAUIResourceCandidate@@PEAW4LS_IMAGE_QUALIFIERS@@PEAK@Z`
- size: `322`
- prototype: `void __fastcall(struct IResourceCandidate *, enum LS_IMAGE_QUALIFIERS *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800544b8`

## callees

- `0x1800549f0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054a93`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054ab7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054ae0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054a93`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054ab7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054b14`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x180054aef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x180054aef`

## pseudocode

```c
void __fastcall _GetImageResourceQualifiers(
        struct IResourceCandidate *a1,
        enum LS_IMAGE_QUALIFIERS *a2,
        unsigned int *a3)
{
  __int64 v4; // rax
  unsigned int i; // edi
  __int64 v8; // rax
  int (__fastcall *v9)(struct IResourceCandidate *, _QWORD, LPCWCH *); // rax
  int v10; // eax
  LPCWCH lpString1[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v12; // [rsp+40h] [rbp-28h]
  __int64 v13; // [rsp+50h] [rbp-18h]
  unsigned int v14; // [rsp+A0h] [rbp+38h] BYREF

  *(_DWORD *)a2 = 0;
  *a3 = 100;
  v4 = *(_QWORD *)a1;
  v14 = 0;
  if ( (*(int (__fastcall **)(struct IResourceCandidate *, unsigned int *))(v4 + 48))(a1, &v14) >= 0 )
  {
    for ( i = 0; !*(_DWORD *)a2; ++i )
    {
      if ( i >= v14 )
        break;
      v13 = 0;
      v8 = *(_QWORD *)a1;
      *(_OWORD *)lpString1 = 0;
      v9 = *(int (__fastcall **)(struct IResourceCandidate *, _QWORD, LPCWCH *))(v8 + 56);
      v12 = 0;
      if ( v9(a1, i, lpString1) >= 0 )
      {
        if ( CompareStringOrdinal(lpString1[0], -1, L"contrast", -1, 1) == 2
          && CompareStringOrdinal(lpString1[1], -1, L"white", -1, 1) == 2 )
        {
          *(_DWORD *)a2 |= 1u;
        }
        else if ( CompareStringOrdinal(lpString1[0], -1, L"scale", -1, 1) == 2 )
        {
          v10 = StrToIntW(lpString1[1]);
          *a3 = v10;
          if ( v10 )
            *(_DWORD *)a2 |= 2u;
          else
            *a3 = 100;
        }
        CoTaskMemFree((LPVOID)lpString1[0]);
        CoTaskMemFree((LPVOID)lpString1[1]);
      }
    }
  }
}

```

## disassembly

```asm
0x1800549f0  push    rbp
0x1800549f2  push    rbx
0x1800549f3  push    rsi
0x1800549f4  push    rdi
0x1800549f5  push    r13
0x1800549f7  push    r14
0x1800549f9  mov     rbp, rsp
0x1800549fc  sub     rsp, 68h
0x180054a00  mov     dword ptr [rdx], 0
0x180054a06  mov     rbx, rdx
0x180054a09  mov     dword ptr [r8], 64h ; 'd'
0x180054a10  lea     rdx, [rbp+arg_0]
0x180054a14  mov     rax, [rcx]
0x180054a17  mov     rsi, r8
0x180054a1a  mov     r14, rcx
0x180054a1d  mov     [rbp+arg_0], 0
0x180054a24  mov     rax, [rax+30h]
0x180054a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a2d  test    eax, eax
0x180054a2f  js      loc_180054B25
0x180054a35  xor     edi, edi
0x180054a37  cmp     [rbx], edi
0x180054a39  jnz     loc_180054B25
0x180054a3f  or      r13d, 0FFFFFFFFh
0x180054a43  cmp     edi, [rbp+arg_0]
0x180054a46  jnb     loc_180054B25
0x180054a4c  xor     eax, eax
0x180054a4e  lea     r8, [rbp+lpString1]
0x180054a52  mov     [rbp+var_18], rax
0x180054a56  xorps   xmm0, xmm0
0x180054a59  mov     rax, [r14]
0x180054a5c  mov     edx, edi
0x180054a5e  mov     rcx, r14
0x180054a61  movups  xmmword ptr [rbp+lpString1], xmm0
0x180054a65  mov     rax, [rax+38h]
0x180054a69  movups  [rbp+var_28], xmm0
0x180054a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a72  test    eax, eax
0x180054a74  js      loc_180054B1A
0x180054a7a  mov     rcx, [rbp+lpString1]; lpString1
0x180054a7e  lea     r8, aContrast; "contrast"
0x180054a85  mov     r9d, r13d; cchCount2
0x180054a88  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180054a90  mov     edx, r13d; cchCount1
0x180054a93  call    cs:__imp_CompareStringOrdinal
0x180054a99  cmp     eax, 2
0x180054a9c  jnz     short loc_180054AC7
0x180054a9e  mov     rcx, [rbp+lpString1+8]; lpString1
0x180054aa2  lea     r8, aWhite; "white"
0x180054aa9  mov     r9d, r13d; cchCount2
0x180054aac  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180054ab4  mov     edx, r13d; cchCount1
0x180054ab7  call    cs:__imp_CompareStringOrdinal
0x180054abd  cmp     eax, 2
0x180054ac0  jnz     short loc_180054AC7
0x180054ac2  or      dword ptr [rbx], 1
0x180054ac5  jmp     short loc_180054B06
0x180054ac7  mov     rcx, [rbp+lpString1]; lpString1
0x180054acb  lea     r8, aScale; "scale"
0x180054ad2  mov     r9d, r13d; cchCount2
0x180054ad5  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180054add  mov     edx, r13d; cchCount1
0x180054ae0  call    cs:__imp_CompareStringOrdinal
0x180054ae6  cmp     eax, 2
0x180054ae9  jnz     short loc_180054B06
0x180054aeb  mov     rcx, [rbp+lpString1+8]; pszSrc
0x180054aef  call    cs:__imp_StrToIntW
0x180054af5  mov     [rsi], eax
0x180054af7  test    eax, eax
0x180054af9  jz      short loc_180054B00
0x180054afb  or      dword ptr [rbx], 2
0x180054afe  jmp     short loc_180054B06
0x180054b00  mov     dword ptr [rsi], 64h ; 'd'
0x180054b06  mov     rcx, [rbp+lpString1]; pv
0x180054b0a  call    cs:__imp_CoTaskMemFree
0x180054b10  mov     rcx, [rbp+lpString1+8]; pv
0x180054b14  call    cs:__imp_CoTaskMemFree
0x180054b1a  inc     edi
0x180054b1c  cmp     dword ptr [rbx], 0
0x180054b1f  jz      loc_180054A43
0x180054b25  add     rsp, 68h
0x180054b29  pop     r14
0x180054b2b  pop     r13
0x180054b2d  pop     rdi
0x180054b2e  pop     rsi
0x180054b2f  pop     rbx
0x180054b30  pop     rbp
0x180054b31  retn
```
