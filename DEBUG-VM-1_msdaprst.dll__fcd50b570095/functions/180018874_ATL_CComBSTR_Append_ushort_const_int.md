# ATL::CComBSTR::Append(ushort const *,int)

- ea: `0x180018874`
- end: `0x18001890e`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBGH@Z`
- size: `154`
- prototype: `int(ATL::CComBSTR *__hidden this, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023500`
- `0x180026028`
- `0x180026efc`
- `0x180027c04`

## callees

- `0x180018874`
- `0x18002e012`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800188b1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800188b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800188ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800188ef`
- `OLEAUT32!__imp_SysStringLen` at `0x18001889d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001889d`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(BSTR *this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  signed int v7; // eax
  size_t v8; // rbx
  signed int v9; // esi
  BSTR v10; // rax
  OLECHAR *v11; // r14
  size_t v12; // rbx

  v3 = a3;
  if ( !a2 )
    return a3 != 0 ? 0x80070057 : 0;
  v7 = SysStringLen(*this);
  v8 = v7;
  v9 = v7 + v3;
  if ( v7 + (int)v3 < v7 )
    return 2147942414LL;
  v10 = SysAllocStringLen(0, v9);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  v12 = v8;
  memcpy_0(v10, *this, v12 * 2);
  memcpy_0(&v11[v12], a2, 2 * v3);
  v11[v9] = 0;
  SysFreeString(*this);
  result = 0;
  *this = v11;
  return result;
}

```

## disassembly

```asm
0x180018874  push    rbx
0x180018876  push    rbp
0x180018877  push    rsi
0x180018878  push    rdi
0x180018879  push    r14
0x18001887b  push    r15
0x18001887d  sub     rsp, 28h
0x180018881  movsxd  rdi, r8d
0x180018884  mov     rbp, rdx
0x180018887  mov     r15, rcx
0x18001888a  test    rdx, rdx
0x18001888d  jnz     short loc_18001889A
0x18001888f  neg     edi
0x180018891  sbb     eax, eax
0x180018893  and     eax, 80070057h
0x180018898  jmp     short loc_180018901
0x18001889a  mov     rcx, [rcx]; pbstr
0x18001889d  call    cs:__imp_SysStringLen
0x1800188a3  movsxd  rbx, eax
0x1800188a6  lea     esi, [rbx+rdi]
0x1800188a9  cmp     esi, ebx
0x1800188ab  jl      short loc_1800188FC
0x1800188ad  mov     edx, esi; ui
0x1800188af  xor     ecx, ecx; strIn
0x1800188b1  call    cs:__imp_SysAllocStringLen
0x1800188b7  mov     r14, rax
0x1800188ba  test    rax, rax
0x1800188bd  jz      short loc_1800188FC
0x1800188bf  mov     rdx, [r15]; Src
0x1800188c2  add     rbx, rbx
0x1800188c5  mov     r8, rbx; Size
0x1800188c8  mov     rcx, rax; void *
0x1800188cb  call    memcpy_0
0x1800188d0  mov     r8, rdi
0x1800188d3  lea     rcx, [rbx+r14]; void *
0x1800188d7  add     r8, r8; Size
0x1800188da  mov     rdx, rbp; Src
0x1800188dd  call    memcpy_0
0x1800188e2  movsxd  rcx, esi
0x1800188e5  xor     eax, eax
0x1800188e7  mov     [r14+rcx*2], ax
0x1800188ec  mov     rcx, [r15]; bstrString
0x1800188ef  call    cs:__imp_SysFreeString
0x1800188f5  xor     eax, eax
0x1800188f7  mov     [r15], r14
0x1800188fa  jmp     short loc_180018901
0x1800188fc  mov     eax, 8007000Eh
0x180018901  add     rsp, 28h
0x180018905  pop     r15
0x180018907  pop     r14
0x180018909  pop     rdi
0x18001890a  pop     rsi
0x18001890b  pop     rbp
0x18001890c  pop     rbx
0x18001890d  retn
```
