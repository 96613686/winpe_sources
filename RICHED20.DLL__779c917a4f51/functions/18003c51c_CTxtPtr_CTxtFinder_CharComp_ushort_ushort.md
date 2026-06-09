# CTxtPtr::CTxtFinder::CharComp(ushort,ushort)

- ea: `0x18003c51c`
- end: `0x18003c642`
- name: `?CharComp@CTxtFinder@CTxtPtr@@AEBAHGG@Z`
- size: `294`
- prototype: `__int64 __fastcall(CTxtPtr::CTxtFinder *__hidden this, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180081b50`
- `0x180081bc0`

## callees

- `0x18003c51c`
- `0x18008cc28`
- `0x18008dbbc`
- `0x180091140`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18003c58f`
- `KERNEL32!CompareStringW` at `0x18003c58f`
- `KERNEL32!CompareStringA` at `0x18003c61f`
- `KERNEL32!CompareStringA` at `0x18003c61f`

## pseudocode

```c
bool __fastcall CTxtPtr::CTxtFinder::CharComp(CTxtPtr::CTxtFinder *this, WCHAR a2, WCHAR a3)
{
  int v3; // ebx
  WCHAR String1; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String2; // [rsp+38h] [rbp-C8h] BYREF
  PCNZCH lpString2[66]; // [rsp+40h] [rbp-C0h] BYREF
  int cchCount2; // [rsp+250h] [rbp+150h]
  PCNZCH lpString1[66]; // [rsp+260h] [rbp+160h] BYREF
  int cchCount1; // [rsp+470h] [rbp+370h]

  if ( !*((_DWORD *)this + 2) || (unsigned int)a2 - 55296 <= 0x7FF )
    return a2 == a3;
  String2 = a3;
  String1 = a2;
  if ( CW32System::_dwPlatformId == 1 )
  {
    CStrIn::CStrIn((CStrIn *)lpString1, &String1, 1, 0);
    CStrIn::CStrIn((CStrIn *)lpString2, &String2, 1, 0);
    v3 = CompareStringA(0x400u, 0x20001u, lpString1[0], cchCount1, lpString2[0], cchCount2);
    CConvertStr::Free((CConvertStr *)lpString2);
    CConvertStr::Free((CConvertStr *)lpString1);
  }
  else
  {
    v3 = CompareStringW(0x400u, 0x20001u, &String1, 1, &String2, 1);
  }
  return v3 == 2;
}

```

## disassembly

```asm
0x18003c51c  mov     [rsp-8+arg_0], rbx
0x18003c521  push    rbp
0x18003c522  lea     rbp, [rsp-390h]
0x18003c52a  sub     rsp, 490h
0x18003c531  mov     rax, cs:__security_cookie
0x18003c538  xor     rax, rsp
0x18003c53b  mov     [rbp+390h+var_10], rax
0x18003c542  cmp     dword ptr [rcx+8], 0
0x18003c546  jz      short loc_18003C5BF
0x18003c548  movzx   eax, dx
0x18003c54b  sub     eax, 0D800h
0x18003c550  cmp     eax, 7FFh
0x18003c555  jbe     short loc_18003C5BF
0x18003c557  mov     ebx, 1
0x18003c55c  mov     [rsp+490h+String2], r8w
0x18003c562  cmp     cs:?_dwPlatformId@CW32System@@0KA, ebx; ulong CW32System::_dwPlatformId
0x18003c568  mov     [rsp+490h+String1], dx
0x18003c56d  jz      short loc_18003C5C7
0x18003c56f  lea     rax, [rsp+490h+String2]
0x18003c574  mov     [rsp+490h+cchCount2], ebx; cchCount2
0x18003c578  mov     r9d, ebx; cchCount1
0x18003c57b  mov     [rsp+490h+lpString2], rax; lpString2
0x18003c580  lea     r8, [rsp+490h+String1]; lpString1
0x18003c585  mov     edx, 20001h; dwCmpFlags
0x18003c58a  mov     ecx, 400h; Locale
0x18003c58f  call    cs:__imp_CompareStringW
0x18003c595  mov     ebx, eax
0x18003c597  xor     eax, eax
0x18003c599  cmp     ebx, 2
0x18003c59c  setz    al
0x18003c59f  mov     rcx, [rbp+390h+var_10]
0x18003c5a6  xor     rcx, rsp; StackCookie
0x18003c5a9  call    __security_check_cookie
0x18003c5ae  mov     rbx, [rsp+490h+arg_0]
0x18003c5b6  add     rsp, 490h
0x18003c5bd  pop     rbp
0x18003c5be  retn
0x18003c5bf  xor     eax, eax
0x18003c5c1  cmp     dx, r8w
0x18003c5c5  jmp     short loc_18003C59C
0x18003c5c7  xor     r9d, r9d; unsigned int
0x18003c5ca  lea     rdx, [rsp+490h+String1]; unsigned __int16 *
0x18003c5cf  mov     r8d, ebx; int
0x18003c5d2  lea     rcx, [rbp+390h+lpString1]; this
0x18003c5d9  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003c5de  xor     r9d, r9d; unsigned int
0x18003c5e1  lea     rdx, [rsp+490h+String2]; unsigned __int16 *
0x18003c5e6  mov     r8d, ebx; int
0x18003c5e9  lea     rcx, [rsp+490h+var_450]; this
0x18003c5ee  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003c5f3  mov     rcx, [rsp+490h+var_450]
0x18003c5f8  mov     edx, 20001h; dwCmpFlags
0x18003c5fd  mov     eax, [rbp+390h+var_240]
0x18003c603  mov     r9d, [rbp+390h+cchCount1]; cchCount1
0x18003c60a  mov     r8, [rbp+390h+lpString1]; lpString1
0x18003c611  mov     [rsp+490h+cchCount2], eax; cchCount2
0x18003c615  mov     [rsp+490h+lpString2], rcx; lpString2
0x18003c61a  mov     ecx, 400h; Locale
0x18003c61f  call    cs:__imp_CompareStringA
0x18003c625  lea     rcx, [rsp+490h+var_450]; this
0x18003c62a  mov     ebx, eax
0x18003c62c  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003c631  lea     rcx, [rbp+390h+lpString1]; this
0x18003c638  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003c63d  jmp     loc_18003C597
```
