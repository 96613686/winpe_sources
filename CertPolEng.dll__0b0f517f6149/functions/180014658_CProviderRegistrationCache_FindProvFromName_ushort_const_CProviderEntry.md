# CProviderRegistrationCache::FindProvFromName(ushort const *,CProviderEntry * *)

- ea: `0x180014658`
- end: `0x1800146e0`
- name: `?FindProvFromName@CProviderRegistrationCache@@QEAAJPEBGPEAPEAVCProviderEntry@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, const unsigned __int16 *, struct CProviderEntry **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800066f0`

## callees

- `0x180014658`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800146ac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800146ac`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::FindProvFromName(
        CProviderRegistrationCache *this,
        const unsigned __int16 *a2,
        struct CProviderEntry **a3)
{
  __int64 v3; // rbx
  unsigned int i; // esi

  v3 = 0;
  for ( i = -1073741275; (unsigned int)v3 < *((_DWORD *)this + 38); v3 = (unsigned int)(v3 + 1) )
  {
    if ( CompareStringW(0x400u, 1u, a2, -1, (PCNZWCH)(*(_QWORD *)(*((_QWORD *)this + 18) + 8 * v3) + 1584LL), -1) == 2 )
    {
      i = 0;
      *a3 = *(struct CProviderEntry **)(*((_QWORD *)this + 18) + 8 * v3);
    }
  }
  return i;
}

```

## disassembly

```asm
0x180014658  push    rbx
0x18001465a  push    rbp
0x18001465b  push    rsi
0x18001465c  push    rdi
0x18001465d  push    r14
0x18001465f  push    r15
0x180014661  sub     rsp, 38h
0x180014665  xor     ebx, ebx
0x180014667  mov     r14, r8
0x18001466a  mov     r15, rdx
0x18001466d  mov     rdi, rcx
0x180014670  mov     esi, 0C0000225h
0x180014675  cmp     [rcx+98h], ebx
0x18001467b  jbe     short loc_1800146D1
0x18001467d  mov     rax, [rdi+90h]
0x180014684  or      r9d, 0FFFFFFFFh; cchCount1
0x180014688  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180014690  mov     r8, r15; lpString1
0x180014693  mov     rcx, [rax+rbx*8]
0x180014697  lea     edx, [r9+2]; dwCmpFlags
0x18001469b  add     rcx, 630h
0x1800146a2  mov     [rsp+68h+lpString2], rcx; lpString2
0x1800146a7  mov     ecx, 400h; Locale
0x1800146ac  call    cs:__imp_CompareStringW
0x1800146b2  cmp     eax, 2
0x1800146b5  jnz     short loc_1800146C7
0x1800146b7  mov     rax, [rdi+90h]
0x1800146be  xor     esi, esi
0x1800146c0  mov     rcx, [rax+rbx*8]
0x1800146c4  mov     [r14], rcx
0x1800146c7  inc     ebx
0x1800146c9  cmp     ebx, [rdi+98h]
0x1800146cf  jb      short loc_18001467D
0x1800146d1  mov     eax, esi
0x1800146d3  add     rsp, 38h
0x1800146d7  pop     r15
0x1800146d9  pop     r14
0x1800146db  pop     rdi
0x1800146dc  pop     rsi
0x1800146dd  pop     rbp
0x1800146de  pop     rbx
0x1800146df  retn
```
