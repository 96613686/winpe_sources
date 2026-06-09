# SemanticsUM::CultureState::CultureState(SemanticsUM::SchemaBinary const *)

- ea: `0x1800273dc`
- end: `0x1800274d7`
- name: `??0CultureState@SemanticsUM@@QEAA@PEBVSchemaBinary@1@@Z`
- size: `251`
- prototype: `SemanticsUM::CultureState *__fastcall(SemanticsUM::CultureState *this, const struct SemanticsUM::SchemaBinary *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026b00`

## callees

- `0x1800273dc`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027439`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002746e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800274c0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180089294`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800892d0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027439`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002746e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800274c0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180089294`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800892d0`

## pseudocode

```c
SemanticsUM::CultureState *__fastcall SemanticsUM::CultureState::CultureState(
        SemanticsUM::CultureState *this,
        const struct SemanticsUM::SchemaBinary *a2)
{
  __int64 v3; // rsi
  __int64 i; // rbx
  const WCHAR *v5; // rax
  const WCHAR *v6; // rax
  const WCHAR *v8; // rax
  const WCHAR *v9; // rax
  const WCHAR *v10; // rax

  *(_DWORD *)this = 0;
  v3 = *((_QWORD *)a2 + 27);
  for ( i = *((_QWORD *)a2 + 26); i != v3; i += 24 )
  {
    v5 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))i)(i);
    if ( CompareStringW(0x7Fu, 0, v5, -1, L"bindingPreference", -1) == 2 )
    {
      v6 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 8LL))(i);
      if ( CompareStringW(0x7Fu, 0, v6, -1, L"leftOnly", -1) == 2 )
      {
        *(_DWORD *)this = 0;
      }
      else
      {
        v8 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 8LL))(i);
        if ( CompareStringW(0x7Fu, 0, v8, -1, L"leftPreferred", -1) == 2 )
        {
          *(_DWORD *)this = 1;
        }
        else
        {
          v9 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 8LL))(i);
          if ( CompareStringW(0x7Fu, 0, v9, -1, L"rightPreferred", -1) == 2 )
          {
            *(_DWORD *)this = 2;
          }
          else
          {
            v10 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 8LL))(i);
            if ( CompareStringW(0x7Fu, 0, v10, -1, L"rightOnly", -1) == 2 )
              *(_DWORD *)this = 3;
          }
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800273dc  push    rbx
0x1800273de  push    rbp
0x1800273df  push    rsi
0x1800273e0  push    rdi
0x1800273e1  push    r15
0x1800273e3  sub     rsp, 30h
0x1800273e7  mov     dword ptr [rcx], 0
0x1800273ed  mov     rdi, rcx
0x1800273f0  mov     rsi, [rdx+0D8h]
0x1800273f7  mov     rbx, [rdx+0D0h]
0x1800273fe  cmp     rbx, rsi
0x180027401  jz      loc_180027488
0x180027407  or      ebp, 0FFFFFFFFh
0x18002740a  mov     r15d, 7Fh
0x180027410  mov     rax, [rbx]
0x180027413  mov     rcx, rbx
0x180027416  mov     rax, [rax]
0x180027419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002741e  lea     rcx, aBindingprefere; "bindingPreference"
0x180027425  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x180027429  mov     [rsp+58h+lpString2], rcx; lpString2
0x18002742e  mov     r9d, ebp; cchCount1
0x180027431  mov     ecx, r15d; Locale
0x180027434  mov     r8, rax; lpString1
0x180027437  xor     edx, edx; dwCmpFlags
0x180027439  call    cs:__imp_CompareStringW
0x18002743f  cmp     eax, 2
0x180027442  jnz     short loc_18002747F
0x180027444  mov     rax, [rbx]
0x180027447  mov     rcx, rbx
0x18002744a  mov     rax, [rax+8]
0x18002744e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027453  lea     rcx, aLeftonly; "leftOnly"
0x18002745a  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18002745e  mov     [rsp+58h+lpString2], rcx; lpString2
0x180027463  mov     r9d, ebp; cchCount1
0x180027466  mov     ecx, r15d; Locale
0x180027469  mov     r8, rax; lpString1
0x18002746c  xor     edx, edx; dwCmpFlags
0x18002746e  call    cs:__imp_CompareStringW
0x180027474  cmp     eax, 2
0x180027477  jnz     short loc_180027496
0x180027479  mov     dword ptr [rdi], 0
0x18002747f  add     rbx, 18h
0x180027483  cmp     rbx, rsi
0x180027486  jnz     short loc_180027410
0x180027488  mov     rax, rdi
0x18002748b  add     rsp, 30h
0x18002748f  pop     r15
0x180027491  pop     rdi
0x180027492  pop     rsi
0x180027493  pop     rbp
0x180027494  pop     rbx
0x180027495  retn
0x180027496  mov     rax, [rbx]
0x180027499  mov     rcx, rbx
0x18002749c  mov     rax, [rax+8]
0x1800274a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274a5  lea     rcx, aLeftpreferred; "leftPreferred"
0x1800274ac  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x1800274b0  mov     [rsp+58h+lpString2], rcx; lpString2
0x1800274b5  mov     r9d, ebp; cchCount1
0x1800274b8  mov     ecx, r15d; Locale
0x1800274bb  mov     r8, rax; lpString1
0x1800274be  xor     edx, edx; dwCmpFlags
0x1800274c0  call    cs:__imp_CompareStringW
0x1800274c6  cmp     eax, 2
0x1800274c9  jnz     loc_18008926A
0x1800274cf  mov     dword ptr [rdi], 1
0x1800274d5  jmp     short loc_18002747F
0x18008926a  mov     rax, [rbx]
0x18008926d  mov     rcx, rbx
0x180089270  mov     rax, [rax+8]
0x180089274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089279  lea     rcx, aRightpreferred; "rightPreferred"
0x180089280  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x180089284  mov     [rsp+58h+lpString2], rcx; lpString2
0x180089289  mov     r9d, ebp; cchCount1
0x18008928c  mov     ecx, r15d; Locale
0x18008928f  mov     r8, rax; lpString1
0x180089292  xor     edx, edx; dwCmpFlags
0x180089294  call    cs:__imp_CompareStringW
0x18008929a  cmp     eax, 2
0x18008929d  jnz     short loc_1800892A6
0x18008929f  mov     [rdi], eax
0x1800892a1  jmp     loc_18002747F
0x1800892a6  mov     rax, [rbx]
0x1800892a9  mov     rcx, rbx
0x1800892ac  mov     rax, [rax+8]
0x1800892b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892b5  lea     rcx, aRightonly; "rightOnly"
0x1800892bc  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x1800892c0  mov     [rsp+58h+lpString2], rcx; lpString2
0x1800892c5  mov     r9d, ebp; cchCount1
0x1800892c8  mov     ecx, r15d; Locale
0x1800892cb  mov     r8, rax; lpString1
0x1800892ce  xor     edx, edx; dwCmpFlags
0x1800892d0  call    cs:__imp_CompareStringW
0x1800892d6  cmp     eax, 2
0x1800892d9  jnz     loc_18002747F
0x1800892df  mov     dword ptr [rdi], 3
0x1800892e5  jmp     loc_18002747F
```
