# CAppContainerCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001caa0`
- end: `0x18001cb7c`
- name: `?CreateInstance@CAppContainerCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `220`
- prototype: `__int64 __fastcall(CAppContainerCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001caa0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cac1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cac1`

## pseudocode

```c
__int64 __fastcall CAppContainerCF::CreateInstance(
        CAppContainerCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  char *v6; // rax
  char *v7; // rbx
  int v8; // edi

  if ( a2 )
  {
    *a4 = 0;
    return 2147942487LL;
  }
  else
  {
    v6 = (char *)LocalAlloc(0, 0x4A0u);
    v7 = v6;
    if ( v6 )
    {
      *((_DWORD *)v6 + 134) = 0;
      *(_QWORD *)v6 = &CAppContainer::`vftable';
      *((_QWORD *)v6 + 146) = 0;
      *((_QWORD *)v6 + 68) = 0;
      *((_QWORD *)v6 + 69) = 0;
      *((_QWORD *)v6 + 66) = 0;
      *((_OWORD *)v6 + 35) = 0;
      *(_QWORD *)(v6 + 1140) = 0;
      *((_DWORD *)v6 + 284) = 0;
      *((_DWORD *)v6 + 294) = 1;
      *((_QWORD *)v6 + 144) = 0;
      *((_QWORD *)v6 + 145) = 0;
      v8 = (**(__int64 (__fastcall ***)(HLOCAL, const struct _GUID *, void **))v6)(v6, a3, a4);
      if ( v8 < 0 )
        v8 = -2147418113;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    else
    {
      *a4 = 0;
      return (unsigned int)-2147024882;
    }
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x18001caa0  push    rbx
0x18001caa2  push    rbp
0x18001caa3  push    rsi
0x18001caa4  push    rdi
0x18001caa5  sub     rsp, 28h
0x18001caa9  xor     ebp, ebp
0x18001caab  mov     rdi, r9
0x18001caae  mov     rsi, r8
0x18001cab1  test    rdx, rdx
0x18001cab4  jnz     loc_18001CB6B
0x18001caba  mov     edx, 4A0h; uBytes
0x18001cabf  xor     ecx, ecx; uFlags
0x18001cac1  call    cs:__imp_LocalAlloc
0x18001cac7  mov     rbx, rax
0x18001caca  test    rax, rax
0x18001cacd  jz      loc_18001CB5F
0x18001cad3  mov     [rbx+218h], ebp
0x18001cad9  lea     rax, ??_7CAppContainer@@6B@; const CAppContainer::`vftable'
0x18001cae0  mov     [rbx], rax
0x18001cae3  xorps   xmm0, xmm0
0x18001cae6  mov     [rbx+490h], rbp
0x18001caed  mov     r8, rdi
0x18001caf0  mov     [rbx+220h], rbp
0x18001caf7  mov     rdx, rsi
0x18001cafa  mov     [rbx+228h], rbp
0x18001cb01  mov     rcx, rbx
0x18001cb04  mov     [rbx+210h], rbp
0x18001cb0b  movups  xmmword ptr [rbx+230h], xmm0
0x18001cb12  mov     [rbx+474h], rbp
0x18001cb19  mov     [rbx+470h], ebp
0x18001cb1f  mov     dword ptr [rbx+498h], 1
0x18001cb29  mov     [rbx+480h], rbp
0x18001cb30  mov     [rbx+488h], rbp
0x18001cb37  mov     rax, [rbx]
0x18001cb3a  mov     rax, [rax]
0x18001cb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb42  mov     edi, eax
0x18001cb44  mov     rcx, rbx
0x18001cb47  test    edi, edi
0x18001cb49  mov     eax, 8000FFFFh
0x18001cb4e  cmovs   edi, eax
0x18001cb51  mov     rax, [rbx]
0x18001cb54  mov     rax, [rax+10h]
0x18001cb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb5d  jmp     short loc_18001CB67
0x18001cb5f  mov     [rdi], rbp
0x18001cb62  mov     edi, 8007000Eh
0x18001cb67  mov     eax, edi
0x18001cb69  jmp     short loc_18001CB73
0x18001cb6b  mov     [r9], rbp
0x18001cb6e  mov     eax, 80070057h
0x18001cb73  add     rsp, 28h
0x18001cb77  pop     rdi
0x18001cb78  pop     rsi
0x18001cb79  pop     rbp
0x18001cb7a  pop     rbx
0x18001cb7b  retn
```
