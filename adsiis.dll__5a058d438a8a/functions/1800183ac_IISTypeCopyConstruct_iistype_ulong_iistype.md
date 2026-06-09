# IISTypeCopyConstruct(_iistype *,ulong,_iistype * *)

- ea: `0x1800183ac`
- end: `0x180018438`
- name: `?IISTypeCopyConstruct@@YAJPEAU_iistype@@KPEAPEAU1@@Z`
- size: `140`
- prototype: `__int64 __fastcall(struct _iistype *, unsigned int, struct _iistype **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180010cd8`
- `0x180010ecc`
- `0x180011034`
- `0x1800111b4`

## callees

- `0x1800182bc`
- `0x1800183ac`
- `0x1800184ac`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x1800183dd`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800183dd`

## pseudocode

```c
__int64 __fastcall IISTypeCopyConstruct(struct _iistype *a1, unsigned int a2, struct _iistype **a3)
{
  struct _iistype *v6; // rdi
  __int64 i; // rbx
  int v9; // ebp

  if ( ((*(_DWORD *)a1 - 5) & 0xFFFFFFFA) == 0 && *(_DWORD *)a1 != 6 )
    a2 = 1;
  v6 = (struct _iistype *)AllocADsMem(24 * a2);
  if ( !v6 )
    return 2147500037LL;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a2 )
    {
      *a3 = v6;
      return 0;
    }
    v9 = IISTypeCopy((struct _iistype *)((char *)a1 + 24 * i), (struct _iistype *)((char *)v6 + 24 * i));
    if ( v9 < 0 )
      break;
  }
  if ( (_DWORD)i )
    IISTypeFreeIISObjects(v6, i - 1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800183ac  push    rbx
0x1800183ae  push    rbp
0x1800183af  push    rsi
0x1800183b0  push    rdi
0x1800183b1  push    r14
0x1800183b3  push    r15
0x1800183b5  sub     rsp, 28h
0x1800183b9  mov     esi, edx
0x1800183bb  mov     r14, r8
0x1800183be  mov     edx, [rcx]
0x1800183c0  mov     r15, rcx
0x1800183c3  lea     eax, [rdx-5]
0x1800183c6  test    eax, 0FFFFFFFAh
0x1800183cb  jnz     short loc_1800183D7
0x1800183cd  cmp     edx, 6
0x1800183d0  jz      short loc_1800183D7
0x1800183d2  mov     esi, 1
0x1800183d7  lea     ecx, [rsi+rsi*2]
0x1800183da  shl     ecx, 3; cb
0x1800183dd  call    cs:__imp_AllocADsMem
0x1800183e3  mov     rdi, rax
0x1800183e6  test    rax, rax
0x1800183e9  jnz     short loc_1800183F2
0x1800183eb  mov     eax, 80004005h
0x1800183f0  jmp     short loc_18001842B
0x1800183f2  xor     ebx, ebx
0x1800183f4  cmp     ebx, esi
0x1800183f6  jnb     short loc_180018426
0x1800183f8  lea     rcx, [rbx+rbx*2]
0x1800183fc  lea     rdx, [rdi+rcx*8]; struct _iistype *
0x180018400  lea     rcx, [r15+rcx*8]; struct _iistype *
0x180018404  call    ?IISTypeCopy@@YAJPEAU_iistype@@0@Z; IISTypeCopy(_iistype *,_iistype *)
0x180018409  mov     ebp, eax
0x18001840b  test    eax, eax
0x18001840d  js      short loc_180018413
0x18001840f  inc     ebx
0x180018411  jmp     short loc_1800183F4
0x180018413  test    ebx, ebx
0x180018415  jz      short loc_180018422
0x180018417  lea     edx, [rbx-1]; unsigned int
0x18001841a  mov     rcx, rdi; struct _iistype *
0x18001841d  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180018422  mov     eax, ebp
0x180018424  jmp     short loc_18001842B
0x180018426  mov     [r14], rdi
0x180018429  xor     eax, eax
0x18001842b  add     rsp, 28h
0x18001842f  pop     r15
0x180018431  pop     r14
0x180018433  pop     rdi
0x180018434  pop     rsi
0x180018435  pop     rbp
0x180018436  pop     rbx
0x180018437  retn
```
