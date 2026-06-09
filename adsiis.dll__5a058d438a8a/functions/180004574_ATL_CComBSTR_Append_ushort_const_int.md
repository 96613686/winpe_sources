# ATL::CComBSTR::Append(ushort const *,int)

- ea: `0x180004574`
- end: `0x18000461e`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBGH@Z`
- size: `170`
- prototype: `int(ATL::CComBSTR *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004624`
- `0x1800049c0`

## callees

- `0x180004574`
- `0x18001d652`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800045b9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800045b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800045ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800045ff`
- `OLEAUT32!__imp_SysStringLen` at `0x1800045a6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800045a6`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(const void **this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  OLECHAR *v7; // rcx
  signed int v8; // ebx
  signed int v9; // ebp
  BSTR v10; // rax
  BSTR v11; // r14

  v3 = a3;
  if ( !a2 )
    return a3 != 0 ? 0x80070057 : 0;
  v7 = (OLECHAR *)*this;
  if ( v7 )
    v8 = SysStringLen(v7);
  else
    v8 = 0;
  v9 = v8 + v3;
  if ( v8 + (int)v3 < v8 )
    return 2147942414LL;
  v10 = SysAllocStringLen(0, v9);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  if ( *this )
    memcpy_0(v10, *this, 2LL * v8);
  memcpy_0(&v11[v8], a2, 2 * v3);
  v11[v9] = 0;
  SysFreeString((BSTR)*this);
  result = 0;
  *this = v11;
  return result;
}

```

## disassembly

```asm
0x180004574  push    rbx
0x180004576  push    rbp
0x180004577  push    rsi
0x180004578  push    rdi
0x180004579  push    r14
0x18000457b  push    r15
0x18000457d  sub     rsp, 28h
0x180004581  movsxd  rdi, r8d
0x180004584  mov     r15, rdx
0x180004587  mov     rsi, rcx
0x18000458a  test    rdx, rdx
0x18000458d  jnz     short loc_18000459A
0x18000458f  neg     edi
0x180004591  sbb     eax, eax
0x180004593  and     eax, 80070057h
0x180004598  jmp     short loc_180004611
0x18000459a  mov     rcx, [rcx]; pbstr
0x18000459d  test    rcx, rcx
0x1800045a0  jnz     short loc_1800045A6
0x1800045a2  xor     ebx, ebx
0x1800045a4  jmp     short loc_1800045AE
0x1800045a6  call    cs:__imp_SysStringLen
0x1800045ac  mov     ebx, eax
0x1800045ae  lea     ebp, [rbx+rdi]
0x1800045b1  cmp     ebp, ebx
0x1800045b3  jl      short loc_18000460C
0x1800045b5  mov     edx, ebp; ui
0x1800045b7  xor     ecx, ecx; strIn
0x1800045b9  call    cs:__imp_SysAllocStringLen
0x1800045bf  mov     r14, rax
0x1800045c2  test    rax, rax
0x1800045c5  jz      short loc_18000460C
0x1800045c7  mov     rdx, [rsi]; Src
0x1800045ca  test    rdx, rdx
0x1800045cd  jz      short loc_1800045DD
0x1800045cf  movsxd  r8, ebx
0x1800045d2  mov     rcx, rax; void *
0x1800045d5  add     r8, r8; Size
0x1800045d8  call    memcpy_0
0x1800045dd  movsxd  rax, ebx
0x1800045e0  mov     r8, rdi
0x1800045e3  add     r8, r8; Size
0x1800045e6  mov     rdx, r15; Src
0x1800045e9  lea     rcx, [r14+rax*2]; void *
0x1800045ed  call    memcpy_0
0x1800045f2  movsxd  rcx, ebp
0x1800045f5  xor     eax, eax
0x1800045f7  mov     [r14+rcx*2], ax
0x1800045fc  mov     rcx, [rsi]; bstrString
0x1800045ff  call    cs:__imp_SysFreeString
0x180004605  xor     eax, eax
0x180004607  mov     [rsi], r14
0x18000460a  jmp     short loc_180004611
0x18000460c  mov     eax, 8007000Eh
0x180004611  add     rsp, 28h
0x180004615  pop     r15
0x180004617  pop     r14
0x180004619  pop     rdi
0x18000461a  pop     rsi
0x18000461b  pop     rbp
0x18000461c  pop     rbx
0x18000461d  retn
```
