# unknown_libname_11

- ea: `0x1400327fc`
- end: `0x14003285d`
- name: `unknown_libname_11`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `38`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003204c`
- `0x1400327cc`
- `0x140032860`
- `0x140032c2c`
- `0x140032f9c`
- `0x140034314`
- `0x140044654`
- `0x140044bb0`
- `0x140045690`
- `0x14004b614`
- `0x14004bbf8`
- `0x14004bc68`
- `0x14004c13c`
- `0x14004c310`
- `0x14004c448`
- `0x14004c9d4`
- `0x14004cc1c`
- `0x14004d694`
- `0x14004d864`
- `0x1400a3360`
- `0x1400af059`
- `0x1400af4f2`
- `0x1400af53a`
- `0x1400af592`
- `0x1400af59e`
- `0x1400af5c2`
- `0x1400af5de`
- `0x1400afa5b`
- `0x1400afa67`
- `0x1400afa97`
- `0x1400afaa3`
- `0x1400afaaf`
- `0x1400afabb`
- `0x1400afac7`
- `0x1400afb03`
- `0x1400afcfd`
- `0x1400afe28`
- `0x1400b0090`

## callees

- `0x1400046ec`
- `0x14001bf20`
- `0x1400327fc`

## pseudocode

```c
// Microsoft VisualC v14 64bit runtime
__int64 __fastcall unknown_libname_11(__int64 a1)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 >= 8 )
  {
    v3 = *(_QWORD **)a1;
    if ( 2 * v1 + 2 >= 0x1000 )
    {
      if ( (unsigned __int64)v3 - *(v3 - 1) - 8 > 0x1F )
        invalid_parameter_noinfo_noreturn();
      v3 = (_QWORD *)*(v3 - 1);
    }
    j_j_free(v3);
  }
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1400327fc  push    rbx
0x1400327fe  sub     rsp, 20h
0x140032802  mov     rdx, [rcx+18h]
0x140032806  mov     rbx, rcx
0x140032809  cmp     rdx, 8
0x14003280d  jb      short loc_140032840
0x14003280f  mov     rcx, [rcx]
0x140032812  lea     rdx, ds:2[rdx*2]
0x14003281a  cmp     rdx, 1000h
0x140032821  jb      short loc_14003283B
0x140032823  mov     r8, [rcx-8]
0x140032827  add     rdx, 27h ; '''
0x14003282b  sub     rcx, r8
0x14003282e  lea     rax, [rcx-8]
0x140032832  cmp     rax, 1Fh
0x140032836  ja      short loc_140032857
0x140032838  mov     rcx, r8; Block
0x14003283b  call    j_j_free
0x140032840  xor     eax, eax
0x140032842  mov     qword ptr [rbx+18h], 7
0x14003284a  mov     [rbx+10h], rax
0x14003284e  mov     [rbx], ax
0x140032851  add     rsp, 20h
0x140032855  pop     rbx
0x140032856  retn
0x140032857  call    _invalid_parameter_noinfo_noreturn
```
