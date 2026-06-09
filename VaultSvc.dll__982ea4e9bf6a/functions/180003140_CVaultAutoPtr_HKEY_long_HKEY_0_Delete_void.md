# CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)

- ea: `0x180003140`
- end: `0x1800031e3`
- name: `?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ`
- size: `163`
- prototype: `_BYTE *__fastcall(__int64)`
- caller_count: `129`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001970`
- `0x180001aa0`
- `0x180002d10`
- `0x1800032f8`
- `0x18000377c`
- `0x180003810`
- `0x180003ca4`
- `0x180004110`
- `0x180004808`
- `0x180004850`
- `0x180004ed8`
- `0x1800052f8`
- `0x180005674`
- `0x180005690`
- `0x180006324`
- `0x180006680`
- `0x180007af0`
- `0x180008050`
- `0x180008994`
- `0x180008ad0`
- `0x180009a20`
- `0x18000a8cc`
- `0x18000ab94`
- `0x18000af40`
- `0x18000ba4c`
- `0x18000bd14`
- `0x18000bfb0`
- `0x18000c664`
- `0x18000cfec`
- `0x18000d5c4`
- `0x18000d760`
- `0x18000df38`
- `0x18000e148`
- `0x18000e570`
- `0x18000f0d8`
- `0x18000f2e0`
- `0x18000f7d0`
- `0x18000ff18`
- `0x180010520`
- `0x180010f20`
- `0x1800111c0`
- `0x1800118e0`
- `0x180011a94`
- `0x1800135d0`
- `0x1800156f0`
- `0x180016250`
- `0x18001a134`
- `0x18001a404`
- `0x18001ab50`
- `0x18001b060`

## callees

- `0x180003140`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031c0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18000319f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18000319f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BYTE *__fastcall CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(__int64 a1)
{
  _BYTE *result; // rax
  __int64 v3; // rcx
  _BYTE *v4; // rdi
  SIZE_T v5; // rax
  _BYTE *v6; // rdx

  result = *(_BYTE **)(a1 + 8);
  if ( result )
  {
    v3 = *(unsigned int *)(a1 + 16);
    if ( (_DWORD)v3 )
    {
      do
      {
        *result++ = 0;
        --v3;
      }
      while ( v3 );
    }
    v4 = *(_BYTE **)(a1 + 8);
    if ( *(_QWORD *)a1 )
    {
      (*(void (__fastcall **)(_QWORD))a1)(*(_QWORD *)(a1 + 8));
      result = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = 0;
    }
    else
    {
      if ( v4 )
      {
        v5 = LocalSize(*(HLOCAL *)(a1 + 8));
        if ( v5 )
        {
          v6 = v4;
          do
          {
            *v6++ = 0;
            --v5;
          }
          while ( v5 );
        }
        LocalFree(v4);
      }
      result = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = 0;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003140  push    rbx
0x180003142  sub     rsp, 20h
0x180003146  mov     rax, [rcx+8]
0x18000314a  mov     rbx, rcx
0x18000314d  test    rax, rax
0x180003150  jz      loc_1800031DA
0x180003156  mov     ecx, [rcx+10h]
0x180003159  mov     [rsp+28h+arg_0], rdi
0x18000315e  test    ecx, ecx
0x180003160  jz      short loc_18000316F
0x180003162  mov     byte ptr [rax], 0
0x180003165  lea     rax, [rax+1]
0x180003169  sub     rcx, 1
0x18000316d  jnz     short loc_180003162
0x18000316f  mov     rax, [rbx]
0x180003172  mov     rdi, [rbx+8]
0x180003176  test    rax, rax
0x180003179  jz      short loc_180003197
0x18000317b  mov     rcx, rdi
0x18000317e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003183  mov     rdi, [rsp+28h+arg_0]
0x180003188  xor     eax, eax
0x18000318a  mov     [rbx+8], rax
0x18000318e  mov     [rbx+10h], eax
0x180003191  add     rsp, 20h
0x180003195  pop     rbx
0x180003196  retn
0x180003197  test    rdi, rdi
0x18000319a  jz      short loc_1800031C6
0x18000319c  mov     rcx, rdi; hMem
0x18000319f  call    cs:__imp_LocalSize
0x1800031a5  test    rax, rax
0x1800031a8  jz      short loc_1800031BD
0x1800031aa  mov     rdx, rdi
0x1800031ad  nop     dword ptr [rax]
0x1800031b0  mov     byte ptr [rdx], 0
0x1800031b3  lea     rdx, [rdx+1]
0x1800031b7  sub     rax, 1
0x1800031bb  jnz     short loc_1800031B0
0x1800031bd  mov     rcx, rdi; hMem
0x1800031c0  call    cs:__imp_LocalFree
0x1800031c6  mov     rdi, [rsp+28h+arg_0]
0x1800031cb  xor     eax, eax
0x1800031cd  mov     [rbx+8], rax
0x1800031d1  mov     [rbx+10h], eax
0x1800031d4  add     rsp, 20h
0x1800031d8  pop     rbx
0x1800031d9  retn
0x1800031da  mov     [rcx+10h], eax
0x1800031dd  add     rsp, 20h
0x1800031e1  pop     rbx
0x1800031e2  retn
```
