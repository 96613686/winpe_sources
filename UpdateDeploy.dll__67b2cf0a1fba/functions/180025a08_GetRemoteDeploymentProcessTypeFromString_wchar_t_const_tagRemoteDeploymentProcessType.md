# GetRemoteDeploymentProcessTypeFromString(wchar_t const *,tagRemoteDeploymentProcessType *)

- ea: `0x180025a08`
- end: `0x180025b23`
- name: `?GetRemoteDeploymentProcessTypeFromString@@YAJPEB_WPEAW4tagRemoteDeploymentProcessType@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(PCNZWCH lpString2, enum tagRemoteDeploymentProcessType *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025b2c`

## callees

- `0x180003180`
- `0x180025a08`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025a6c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025a97`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025ac2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025a6c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025a97`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025ac2`

## string_xrefs

- `0x180025b01`: `C:\__w\1\s\src\Client\UpdateDeployment\inc\HandlerMappingParser.h`

## pseudocode

```c
__int64 __fastcall GetRemoteDeploymentProcessTypeFromString(PCNZWCH lpString2, enum tagRemoteDeploymentProcessType *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int lpString2a; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !lpString2 || !*lpString2 )
  {
    v4 = -2147024809;
    v5 = 82;
    goto LABEL_17;
  }
  if ( a2 )
  {
    if ( L"1" == lpString2 || CompareStringW(0x7Fu, 1u, L"1", -1, lpString2, -1) == 2 )
    {
      *(_DWORD *)a2 = 1;
    }
    else if ( L"2" == lpString2 || CompareStringW(0x7Fu, 1u, L"2", -1, lpString2, -1) == 2 )
    {
      *(_DWORD *)a2 = 2;
    }
    else
    {
      if ( L"3" != lpString2 && CompareStringW(0x7Fu, 1u, L"3", -1, lpString2, -1) != 2 )
      {
        v4 = -2145120257;
        v5 = 99;
        goto LABEL_17;
      }
      *(_DWORD *)a2 = 3;
    }
    return 0;
  }
  v4 = -2147467261;
  v5 = 83;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\inc\\HandlerMappingParser.h",
    (const char *)v4,
    lpString2a);
  return v4;
}

```

## disassembly

```asm
0x180025a08  mov     [rsp+arg_0], rbx
0x180025a0d  mov     [rsp+arg_8], rdi
0x180025a12  push    r14
0x180025a14  sub     rsp, 30h
0x180025a18  xor     eax, eax
0x180025a1a  mov     rdi, rdx
0x180025a1d  mov     rbx, rcx
0x180025a20  test    rcx, rcx
0x180025a23  jz      loc_180025AF2
0x180025a29  cmp     [rcx], ax
0x180025a2c  jz      loc_180025AF2
0x180025a32  test    rdx, rdx
0x180025a35  jnz     short loc_180025A44
0x180025a37  mov     ebx, 80004003h
0x180025a3c  lea     edx, [rdi+53h]
0x180025a3f  jmp     loc_180025AFC
0x180025a44  lea     r8, String1; "1"
0x180025a4b  cmp     r8, rbx
0x180025a4e  jz      loc_180025AE8
0x180025a54  or      r14d, 0FFFFFFFFh
0x180025a58  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x180025a5d  mov     r9d, r14d; cchCount1
0x180025a60  mov     [rsp+38h+lpString2], rbx; lpString2
0x180025a65  lea     edx, [r14+2]; dwCmpFlags
0x180025a69  lea     ecx, [rdx+7Eh]; Locale
0x180025a6c  call    cs:__imp_CompareStringW
0x180025a72  cmp     eax, 2
0x180025a75  jz      short loc_180025AE8
0x180025a77  lea     r8, a2; "2"
0x180025a7e  cmp     r8, rbx
0x180025a81  jz      short loc_180025AE0
0x180025a83  lea     edx, [r14+2]; dwCmpFlags
0x180025a87  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x180025a8c  lea     ecx, [rdx+7Eh]; Locale
0x180025a8f  mov     [rsp+38h+lpString2], rbx; lpString2
0x180025a94  mov     r9d, r14d; cchCount1
0x180025a97  call    cs:__imp_CompareStringW
0x180025a9d  cmp     eax, 2
0x180025aa0  jz      short loc_180025AE0
0x180025aa2  lea     r8, a3; "3"
0x180025aa9  cmp     r8, rbx
0x180025aac  jz      short loc_180025AD8
0x180025aae  lea     edx, [r14+2]; dwCmpFlags
0x180025ab2  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x180025ab7  lea     ecx, [rdx+7Eh]; Locale
0x180025aba  mov     [rsp+38h+lpString2], rbx; lpString2
0x180025abf  mov     r9d, r14d; cchCount1
0x180025ac2  call    cs:__imp_CompareStringW
0x180025ac8  cmp     eax, 2
0x180025acb  jz      short loc_180025AD8
0x180025acd  mov     ebx, 80240FFFh
0x180025ad2  lea     edx, [r14+64h]
0x180025ad6  jmp     short loc_180025AFC
0x180025ad8  mov     dword ptr [rdi], 3
0x180025ade  jmp     short loc_180025AEE
0x180025ae0  mov     dword ptr [rdi], 2
0x180025ae6  jmp     short loc_180025AEE
0x180025ae8  mov     dword ptr [rdi], 1
0x180025aee  xor     eax, eax
0x180025af0  jmp     short loc_180025B12
0x180025af2  mov     ebx, 80070057h
0x180025af7  mov     edx, 52h ; 'R'; void *
0x180025afc  mov     rcx, [rsp+38h]; this
0x180025b01  lea     r8, aCW1SSrcClientU_2; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180025b08  mov     r9d, ebx; char *
0x180025b0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025b10  mov     eax, ebx
0x180025b12  mov     rbx, [rsp+38h+arg_0]
0x180025b17  mov     rdi, [rsp+38h+arg_8]
0x180025b1c  add     rsp, 30h
0x180025b20  pop     r14
0x180025b22  retn
```
