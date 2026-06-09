# IISTypeFreeIISObjects(_iistype *,ulong)

- ea: `0x1800184ac`
- end: `0x180018512`
- name: `?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z`
- size: `102`
- prototype: `void __fastcall(struct _iistype *, unsigned int)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ed0`
- `0x180003050`
- `0x1800032a0`
- `0x1800035a0`
- `0x180005a90`
- `0x180005e40`
- `0x180006b00`
- `0x180006d90`
- `0x180006f60`
- `0x180007300`
- `0x18000fee8`
- `0x180010104`
- `0x1800103bc`
- `0x180010ac4`
- `0x180010c50`
- `0x180010ecc`
- `0x1800110bc`
- `0x1800111b4`
- `0x1800183ac`
- `0x180018c08`

## callees

- `0x180018440`
- `0x1800184ac`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsMem` at `0x1800184fc`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800184fc`

## pseudocode

```c
void __fastcall IISTypeFreeIISObjects(struct _iistype *a1, unsigned int a2)
{
  int v4; // ecx
  __int64 i; // rdi

  if ( a1 )
  {
    v4 = *(_DWORD *)a1;
    if ( ((v4 - 5) & 0xFFFFFFFA) != 0 || v4 == 6 )
    {
      for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
        IISTypeClear((struct _iistype *)((char *)a1 + 24 * i));
    }
    else
    {
      IISTypeClear(a1);
    }
    FreeADsMem(a1);
  }
}

```

## disassembly

```asm
0x1800184ac  test    rcx, rcx
0x1800184af  jz      short locret_180018511
0x1800184b1  mov     [rsp+arg_0], rbx
0x1800184b6  mov     [rsp+arg_8], rsi
0x1800184bb  push    rdi
0x1800184bc  sub     rsp, 20h
0x1800184c0  mov     rbx, rcx
0x1800184c3  mov     esi, edx
0x1800184c5  mov     ecx, [rcx]
0x1800184c7  lea     eax, [rcx-5]
0x1800184ca  test    eax, 0FFFFFFFAh
0x1800184cf  jnz     short loc_1800184E0
0x1800184d1  cmp     ecx, 6
0x1800184d4  jz      short loc_1800184E0
0x1800184d6  mov     rcx, rbx; struct _iistype *
0x1800184d9  call    ?IISTypeClear@@YAJPEAU_iistype@@@Z; IISTypeClear(_iistype *)
0x1800184de  jmp     short loc_1800184F9
0x1800184e0  xor     edi, edi
0x1800184e2  test    esi, esi
0x1800184e4  jz      short loc_1800184F9
0x1800184e6  lea     rcx, [rdi+rdi*2]
0x1800184ea  lea     rcx, [rbx+rcx*8]; struct _iistype *
0x1800184ee  call    ?IISTypeClear@@YAJPEAU_iistype@@@Z; IISTypeClear(_iistype *)
0x1800184f3  inc     edi
0x1800184f5  cmp     edi, esi
0x1800184f7  jb      short loc_1800184E6
0x1800184f9  mov     rcx, rbx; pMem
0x1800184fc  call    cs:__imp_FreeADsMem
0x180018502  mov     rbx, [rsp+28h+arg_0]
0x180018507  mov     rsi, [rsp+28h+arg_8]
0x18001850c  add     rsp, 20h
0x180018510  pop     rdi
0x180018511  retn
```
