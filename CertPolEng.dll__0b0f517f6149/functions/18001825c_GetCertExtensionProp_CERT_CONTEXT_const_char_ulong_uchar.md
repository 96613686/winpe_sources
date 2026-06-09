# GetCertExtensionProp(_CERT_CONTEXT const *,char *,ulong *,uchar * *)

- ea: `0x18001825c`
- end: `0x180018305`
- name: `?GetCertExtensionProp@@YAKPEBU_CERT_CONTEXT@@PEADPEAKPEAPEAE@Z`
- size: `169`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, char *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001830c`

## callees

- `0x18001825c`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800182b2`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800182b2`

## pseudocode

```c
__int64 __fastcall GetCertExtensionProp(
        const struct _CERT_CONTEXT *a1,
        char *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  unsigned int v4; // edi
  DWORD i; // ebx
  PCERT_INFO pCertInfo; // rdx
  bool v10; // zf
  __int64 v11; // rsi
  PCERT_INFO v12; // rdx
  PCERT_EXTENSION rgExtension; // rcx

  v4 = 0;
  for ( i = 0; ; ++i )
  {
    pCertInfo = a1->pCertInfo;
    v10 = i == pCertInfo->cExtension;
    if ( i >= pCertInfo->cExtension )
      break;
    v11 = i;
    if ( CompareStringA(0x7Fu, 1u, "2.5.29.17", -1, pCertInfo->rgExtension[v11].pszObjId, -1) == 2 )
    {
      v12 = a1->pCertInfo;
      rgExtension = v12->rgExtension;
      v10 = i == v12->cExtension;
      *a3 = rgExtension[v11].Value.cbData;
      *a4 = rgExtension[v11].Value.pbData;
      break;
    }
  }
  if ( v10 )
  {
    v4 = 1168;
    *a3 = 0;
    *a4 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001825c  push    rbx
0x18001825e  push    rbp
0x18001825f  push    rsi
0x180018260  push    rdi
0x180018261  push    r14
0x180018263  push    r15
0x180018265  sub     rsp, 38h
0x180018269  xor     edi, edi
0x18001826b  mov     r14, r9
0x18001826e  xor     ebx, ebx
0x180018270  mov     r15, r8
0x180018273  mov     rbp, rcx
0x180018276  mov     rdx, [rbp+18h]
0x18001827a  cmp     ebx, [rdx+0C0h]
0x180018280  jnb     short loc_1800182E1
0x180018282  mov     rax, [rdx+0C8h]
0x180018289  lea     r8, String1; "2.5.29.17"
0x180018290  or      r9d, 0FFFFFFFFh; cchCount1
0x180018294  mov     esi, ebx
0x180018296  shl     rsi, 5
0x18001829a  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800182a2  lea     edx, [r9+2]; dwCmpFlags
0x1800182a6  mov     rax, [rax+rsi]
0x1800182aa  lea     ecx, [rdx+7Eh]; Locale
0x1800182ad  mov     [rsp+68h+lpString2], rax; lpString2
0x1800182b2  call    cs:__imp_CompareStringA
0x1800182b8  cmp     eax, 2
0x1800182bb  jz      short loc_1800182C1
0x1800182bd  inc     ebx
0x1800182bf  jmp     short loc_180018276
0x1800182c1  mov     rdx, [rbp+18h]
0x1800182c5  mov     rcx, [rdx+0C8h]
0x1800182cc  cmp     ebx, [rdx+0C0h]
0x1800182d2  mov     eax, [rcx+rsi+10h]
0x1800182d6  mov     [r15], eax
0x1800182d9  mov     rax, [rcx+rsi+18h]
0x1800182de  mov     [r14], rax
0x1800182e1  jnz     short loc_1800182F6
0x1800182e3  mov     edi, 490h
0x1800182e8  mov     dword ptr [r15], 0
0x1800182ef  mov     qword ptr [r14], 0
0x1800182f6  mov     eax, edi
0x1800182f8  add     rsp, 38h
0x1800182fc  pop     r15
0x1800182fe  pop     r14
0x180018300  pop     rdi
0x180018301  pop     rsi
0x180018302  pop     rbp
0x180018303  pop     rbx
0x180018304  retn
```
