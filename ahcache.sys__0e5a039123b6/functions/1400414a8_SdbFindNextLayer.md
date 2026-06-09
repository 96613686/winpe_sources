# SdbFindNextLayer

- ea: `0x1400414a8`
- end: `0x14004162f`
- name: `SdbFindNextLayer`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140040d5c`

## callees

- `0x1400079f0`
- `0x14003e364`
- `0x1400414a8`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x14004150e`
- `ntoskrnl!wcscpy_s` at `0x14004150e`
- `ntoskrnl!wcscat_s` at `0x140041528`
- `ntoskrnl!wcscat_s` at `0x140041528`
- `ntoskrnl!wcschr` at `0x1400415c4`
- `ntoskrnl!wcschr` at `0x1400415c4`
- `ntoskrnl!wcsspn` at `0x140041613`
- `ntoskrnl!wcsspn` at `0x140041613`

## string_xrefs

- `0x1400415d8`: `Command line does not terminate`

## pseudocode

```c
__int64 __fastcall SdbFindNextLayer(const wchar_t **a1, const wchar_t **a2, const wchar_t **a3)
{
  const wchar_t *v3; // rdi
  unsigned int v7; // esi
  const wchar_t *v8; // r15
  const wchar_t *v9; // rdx
  wchar_t v10; // r8
  wchar_t *i; // rax
  const wchar_t *v12; // rcx
  const wchar_t *v14; // rbp
  wchar_t *v15; // rax
  const wchar_t *v16; // rbx
  wchar_t Dst; // [rsp+20h] [rbp-48h] BYREF

  v3 = *a1;
  *a2 = 0;
  v7 = 0;
  if ( a3 )
    *a3 = 0;
  if ( v3 && *v3 )
  {
    v8 = 0;
    wcscpy_s(&Dst, 4u, L" \t");
    wcscat_s(&Dst, 4u, L"<");
    v9 = v3;
LABEL_6:
    v10 = *v9;
    if ( !*v9 )
      goto LABEL_13;
    for ( i = &Dst; ; ++i )
    {
      if ( !*i )
      {
        ++v9;
        goto LABEL_6;
      }
      if ( *i == v10 )
        break;
    }
    if ( v9 )
    {
      *v9 = 0;
      v14 = v9 + 1;
      if ( v10 == 60 )
      {
        v15 = wcschr(v14, 0x3Eu);
        if ( !v15 )
        {
          AslLogCallPrintf(1, "SdbFindNextLayer", 4405, "Command line does not terminate");
          return v7;
        }
        v8 = v14;
        *v15 = 0;
        v16 = v15 + 1;
      }
      else
      {
        v16 = v9 + 1;
      }
      v12 = &v16[wcsspn(v16, L" \t")];
    }
    else
    {
LABEL_13:
      v12 = 0;
    }
    if ( *v3 )
    {
      *a1 = v12;
      v7 = 1;
      *a2 = v3;
      if ( a3 )
        *a3 = v8;
    }
    else
    {
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1400414a8  mov     [rsp+arg_18], rbx
0x1400414ad  push    rbp
0x1400414ae  push    rsi
0x1400414af  push    rdi
0x1400414b0  push    r12
0x1400414b2  push    r13
0x1400414b4  push    r14
0x1400414b6  push    r15
0x1400414b8  sub     rsp, 30h
0x1400414bc  mov     rax, cs:__security_cookie
0x1400414c3  xor     rax, rsp
0x1400414c6  mov     [rsp+68h+var_40], rax
0x1400414cb  mov     rdi, [rcx]
0x1400414ce  xor     ebp, ebp
0x1400414d0  mov     [rdx], rbp
0x1400414d3  mov     r14, r8
0x1400414d6  mov     r13, rdx
0x1400414d9  mov     r12, rcx
0x1400414dc  mov     esi, ebp
0x1400414de  test    r8, r8
0x1400414e1  jz      short loc_1400414E6
0x1400414e3  mov     [r8], rbp
0x1400414e6  test    rdi, rdi
0x1400414e9  jz      loc_140041586
0x1400414ef  cmp     [rdi], bp
0x1400414f2  jz      loc_140041586
0x1400414f8  mov     ebx, 4
0x1400414fd  lea     r8, Control; " \t"
0x140041504  mov     edx, ebx; SizeInWords
0x140041506  lea     rcx, [rsp+68h+Dst]; Dst
0x14004150b  mov     r15, rbp
0x14004150e  call    cs:__imp_wcscpy_s
0x140041515  nop     dword ptr [rax+rax+00h]
0x14004151a  lea     r8, asc_14000B5E4; "<"
0x140041521  mov     edx, ebx; SizeInWords
0x140041523  lea     rcx, [rsp+68h+Dst]; Dst
0x140041528  call    cs:__imp_wcscat_s
0x14004152f  nop     dword ptr [rax+rax+00h]
0x140041534  mov     rdx, rdi
0x140041537  movzx   r8d, word ptr [rdx]
0x14004153b  test    r8w, r8w
0x14004153f  jz      short loc_140041565
0x140041541  lea     rax, [rsp+68h+Dst]
0x140041546  movzx   ecx, word ptr [rax]
0x140041549  test    cx, cx
0x14004154c  jz      short loc_14004155A
0x14004154e  cmp     cx, r8w
0x140041552  jz      short loc_140041560
0x140041554  add     rax, 2
0x140041558  jmp     short loc_140041546
0x14004155a  add     rdx, 2
0x14004155e  jmp     short loc_140041537
0x140041560  test    rdx, rdx
0x140041563  jnz     short loc_1400415AE
0x140041565  mov     rcx, rbp
0x140041568  cmp     [rdi], bp
0x14004156b  jz      loc_140041628
0x140041571  mov     [r12], rcx
0x140041575  mov     esi, 1
0x14004157a  mov     [r13+0], rdi
0x14004157e  test    r14, r14
0x140041581  jz      short loc_140041586
0x140041583  mov     [r14], r15
0x140041586  mov     eax, esi
0x140041588  mov     rcx, [rsp+68h+var_40]
0x14004158d  xor     rcx, rsp; StackCookie
0x140041590  call    __security_check_cookie
0x140041595  mov     rbx, [rsp+68h+arg_18]
0x14004159d  add     rsp, 30h
0x1400415a1  pop     r15
0x1400415a3  pop     r14
0x1400415a5  pop     r13
0x1400415a7  pop     r12
0x1400415a9  pop     rdi
0x1400415aa  pop     rsi
0x1400415ab  pop     rbp
0x1400415ac  retn
0x1400415ae  mov     [rdx], bp
0x1400415b1  lea     rbp, [rdx+2]
0x1400415b5  cmp     r8w, 3Ch ; '<'
0x1400415ba  jnz     short loc_140041604
0x1400415bc  mov     edx, 3Eh ; '>'; Ch
0x1400415c1  mov     rcx, rbp; Str
0x1400415c4  call    cs:__imp_wcschr
0x1400415cb  nop     dword ptr [rax+rax+00h]
0x1400415d0  mov     rbx, rax
0x1400415d3  test    rax, rax
0x1400415d6  jnz     short loc_1400415F6
0x1400415d8  lea     r9, aCommandLineDoe; "Command line does not terminate"
0x1400415df  mov     r8d, 1135h
0x1400415e5  lea     rdx, aSdbfindnextlay; "SdbFindNextLayer"
0x1400415ec  lea     ecx, [rax+1]
0x1400415ef  call    AslLogCallPrintf
0x1400415f4  jmp     short loc_140041586
0x1400415f6  mov     r15, rbp
0x1400415f9  xor     ebp, ebp
0x1400415fb  mov     [rax], bp
0x1400415fe  add     rbx, 2
0x140041602  jmp     short loc_140041609
0x140041604  mov     rbx, rbp
0x140041607  xor     ebp, ebp
0x140041609  lea     rdx, Control; " \t"
0x140041610  mov     rcx, rbx; Str
0x140041613  call    cs:__imp_wcsspn
0x14004161a  nop     dword ptr [rax+rax+00h]
0x14004161f  lea     rcx, [rbx+rax*2]
0x140041623  jmp     loc_140041568
0x140041628  mov     esi, ebp
0x14004162a  jmp     loc_140041586
```
