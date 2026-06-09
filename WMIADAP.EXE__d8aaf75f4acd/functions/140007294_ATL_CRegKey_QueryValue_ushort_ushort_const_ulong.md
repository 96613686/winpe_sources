# ATL::CRegKey::QueryValue(ushort *,ushort const *,ulong *)

- ea: `0x140007294`
- end: `0x140007345`
- name: `?QueryValue@CRegKey@ATL@@QEAAJPEAGPEBGPEAK@Z`
- size: `177`
- prototype: `__int64 __fastcall(HKEY *this, BYTE *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140006df0`

## callees

- `0x140007294`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400072cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400072cc`

## string_xrefs

- `0x1400072bf`: `Working Directory`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::QueryValue(HKEY *this, BYTE *a2, const unsigned __int16 *a3, unsigned int *a4)
{
  HKEY v4; // rcx
  unsigned int Value; // edx
  unsigned __int64 v8; // rax
  __int64 result; // rax
  const unsigned __int16 *v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  v4 = *this;
  LODWORD(v10) = 0;
  Value = RegQueryValueExW(v4, L"Working Directory", 0, (LPDWORD)&v10, a2, a4);
  if ( (_DWORD)v10 != 1 && (_DWORD)v10 != 2 )
  {
    if ( (_DWORD)v10 == 7 && (*(_BYTE *)a4 & 1) == 0 && (*a4 & 0xFFFFFFFE) >= 4 )
    {
      if ( !a2 )
        return Value;
      v8 = (unsigned __int64)*a4 >> 1;
      if ( !*(_WORD *)&a2[2 * v8 - 2] && !*(_WORD *)&a2[2 * v8 - 4] )
        return Value;
    }
    return 13;
  }
  if ( (*(_BYTE *)a4 & 1) != 0 )
    return 13;
  if ( !a2 )
    return Value;
  result = 13;
  if ( !*(_WORD *)&a2[2 * ((unsigned __int64)*a4 >> 1) - 2] )
    return Value;
  return result;
}

```

## disassembly

```asm
0x140007294  mov     rax, rsp
0x140007297  mov     [rax+8], rbx
0x14000729b  mov     [rax+10h], rsi
0x14000729f  mov     [rax+18h], r8
0x1400072a3  push    rdi
0x1400072a4  sub     rsp, 30h
0x1400072a8  mov     rcx, [rcx]; hKey
0x1400072ab  mov     rdi, r9
0x1400072ae  mov     [rax-10h], r9
0x1400072b2  mov     rbx, rdx
0x1400072b5  mov     [rax-18h], rdx
0x1400072b9  lea     r9, [rax+18h]; lpType
0x1400072bd  xor     esi, esi
0x1400072bf  lea     rdx, aWorkingDirecto; "Working Directory"
0x1400072c6  xor     r8d, r8d; lpReserved
0x1400072c9  mov     [rax+18h], esi
0x1400072cc  call    cs:__imp_RegQueryValueExW
0x1400072d2  mov     edx, eax
0x1400072d4  mov     eax, dword ptr [rsp+38h+arg_10]
0x1400072d8  sub     eax, 1
0x1400072db  jz      short loc_140007312
0x1400072dd  sub     eax, 1
0x1400072e0  jz      short loc_140007312
0x1400072e2  cmp     eax, 5
0x1400072e5  jnz     short loc_140007330
0x1400072e7  test    byte ptr [rdi], 1
0x1400072ea  jnz     short loc_140007330
0x1400072ec  mov     eax, [rdi]
0x1400072ee  and     eax, 0FFFFFFFEh
0x1400072f1  cmp     eax, 4
0x1400072f4  jb      short loc_140007330
0x1400072f6  test    rbx, rbx
0x1400072f9  jz      short loc_14000730E
0x1400072fb  mov     eax, [rdi]
0x1400072fd  shr     rax, 1
0x140007300  cmp     [rbx+rax*2-2], si
0x140007305  jnz     short loc_140007330
0x140007307  cmp     [rbx+rax*2-4], si
0x14000730c  jnz     short loc_140007330
0x14000730e  mov     eax, edx
0x140007310  jmp     short loc_140007335
0x140007312  test    byte ptr [rdi], 1
0x140007315  jnz     short loc_140007330
0x140007317  test    rbx, rbx
0x14000731a  jz      short loc_14000730E
0x14000731c  mov     ecx, [rdi]
0x14000731e  mov     eax, 0Dh
0x140007323  shr     rcx, 1
0x140007326  cmp     [rbx+rcx*2-2], si
0x14000732b  cmovz   eax, edx
0x14000732e  jmp     short loc_140007335
0x140007330  mov     eax, 0Dh
0x140007335  mov     rbx, [rsp+38h+arg_0]
0x14000733a  mov     rsi, [rsp+38h+arg_8]
0x14000733f  add     rsp, 30h
0x140007343  pop     rdi
0x140007344  retn
```
