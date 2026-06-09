# SRCacheContext::IsEmpty(int *)

- ea: `0x18000c384`
- end: `0x18000c427`
- name: `?IsEmpty@SRCacheContext@@QEAAJPEAH@Z`
- size: `163`
- prototype: `__int64 __fastcall(HKEY *this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d050`

## callees

- `0x18000940c`
- `0x18000c384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c3e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c3e6`

## string_xrefs

- `0x18000c3f7`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::IsEmpty(HKEY *this, int *a2)
{
  HKEY v2; // rcx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  int lpcSubKeys; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD v9; // [rsp+70h] [rbp+8h] BYREF

  v2 = *this;
  v9 = 0;
  v4 = RegQueryInfoKeyW(v2, 0, 0, 0, &v9, 0, 0, 0, 0, 0, 0, 0);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *a2 = v9 == 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)(unsigned int)v4,
      lpcSubKeys);
    return v5;
  }
}

```

## disassembly

```asm
0x18000c384  mov     rax, rsp
0x18000c387  mov     [rax+10h], rbx
0x18000c38b  push    rdi
0x18000c38c  sub     rsp, 60h
0x18000c390  mov     rcx, [rcx]; hKey
0x18000c393  mov     rdi, rdx
0x18000c396  mov     qword ptr [rax-10h], 0
0x18000c39e  xor     r9d, r9d; lpReserved
0x18000c3a1  mov     qword ptr [rax-18h], 0
0x18000c3a9  xor     r8d, r8d; lpcchClass
0x18000c3ac  mov     qword ptr [rax-20h], 0
0x18000c3b4  xor     edx, edx; lpClass
0x18000c3b6  mov     qword ptr [rax-28h], 0
0x18000c3be  mov     qword ptr [rax-30h], 0
0x18000c3c6  mov     qword ptr [rax-38h], 0
0x18000c3ce  mov     qword ptr [rax-40h], 0
0x18000c3d6  mov     dword ptr [rax+8], 0
0x18000c3dd  lea     rax, [rax+8]
0x18000c3e1  mov     qword ptr [rsp+68h+lpcSubKeys], rax; int
0x18000c3e6  call    cs:__imp_RegQueryInfoKeyW
0x18000c3ec  mov     ebx, eax
0x18000c3ee  test    eax, eax
0x18000c3f0  jns     short loc_18000C40F
0x18000c3f2  mov     rcx, [rsp+68h]; this
0x18000c3f7  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c3fe  mov     r9d, eax; char *
0x18000c401  mov     edx, 17Eh; void *
0x18000c406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c40b  mov     eax, ebx
0x18000c40d  jmp     short loc_18000C41C
0x18000c40f  xor     eax, eax
0x18000c411  cmp     [rsp+68h+arg_0], eax
0x18000c415  setz    al
0x18000c418  mov     [rdi], eax
0x18000c41a  xor     eax, eax
0x18000c41c  mov     rbx, [rsp+68h+arg_8]
0x18000c421  add     rsp, 60h
0x18000c425  pop     rdi
0x18000c426  retn
```
