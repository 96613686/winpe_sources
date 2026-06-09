# CClassContainerCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800204f0`
- end: `0x1800205ee`
- name: `?CreateInstance@CClassContainerCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(CClassContainerCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800204f0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020515`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020515`

## pseudocode

```c
__int64 __fastcall CClassContainerCF::CreateInstance(
        CClassContainerCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  int v8; // edi

  if ( a2 )
  {
    *a4 = 0;
    return 2147942487LL;
  }
  else
  {
    v6 = LocalAlloc(0, 0x260u);
    v7 = v6;
    if ( v6 )
    {
      v6[136] = 0;
      *(_QWORD *)v6 = &CClassContainer::`vftable';
      *((_QWORD *)v6 + 74) = 0;
      *((_QWORD *)v6 + 69) = 0;
      *((_QWORD *)v6 + 70) = 0;
      *((_QWORD *)v6 + 67) = 0;
      *((_QWORD *)v6 + 66) = 0;
      *((_QWORD *)v6 + 71) = 0;
      *((_OWORD *)v6 + 36) = 0;
      v6[150] = 1;
      v8 = (**(__int64 (__fastcall ***)(HLOCAL, const struct _GUID *, void **))v6)(v6, a3, a4);
      if ( v8 < 0 )
        v8 = -2147418113;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
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
0x1800204f0  mov     [rsp+arg_0], rbx
0x1800204f5  mov     [rsp+arg_8], rsi
0x1800204fa  push    rdi
0x1800204fb  sub     rsp, 20h
0x1800204ff  mov     rdi, r9
0x180020502  mov     rsi, r8
0x180020505  test    rdx, rdx
0x180020508  jnz     loc_1800205D2
0x18002050e  mov     edx, 260h; uBytes
0x180020513  xor     ecx, ecx; uFlags
0x180020515  call    cs:__imp_LocalAlloc
0x18002051b  mov     rbx, rax
0x18002051e  test    rax, rax
0x180020521  jz      loc_1800205C2
0x180020527  mov     dword ptr [rbx+220h], 0
0x180020531  lea     rax, ??_7CClassContainer@@6B@; const CClassContainer::`vftable'
0x180020538  mov     [rbx], rax
0x18002053b  xorps   xmm0, xmm0
0x18002053e  mov     qword ptr [rbx+250h], 0
0x180020549  mov     r8, rdi
0x18002054c  mov     qword ptr [rbx+228h], 0
0x180020557  mov     rdx, rsi
0x18002055a  mov     qword ptr [rbx+230h], 0
0x180020565  mov     rcx, rbx
0x180020568  mov     qword ptr [rbx+218h], 0
0x180020573  mov     qword ptr [rbx+210h], 0
0x18002057e  mov     qword ptr [rbx+238h], 0
0x180020589  movups  xmmword ptr [rbx+240h], xmm0
0x180020590  mov     dword ptr [rbx+258h], 1
0x18002059a  mov     rax, [rbx]
0x18002059d  mov     rax, [rax]
0x1800205a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205a5  mov     edi, eax
0x1800205a7  mov     rcx, rbx
0x1800205aa  test    edi, edi
0x1800205ac  mov     eax, 8000FFFFh
0x1800205b1  cmovs   edi, eax
0x1800205b4  mov     rax, [rbx]
0x1800205b7  mov     rax, [rax+10h]
0x1800205bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205c0  jmp     short loc_1800205CE
0x1800205c2  mov     qword ptr [rdi], 0
0x1800205c9  mov     edi, 8007000Eh
0x1800205ce  mov     eax, edi
0x1800205d0  jmp     short loc_1800205DE
0x1800205d2  mov     qword ptr [r9], 0
0x1800205d9  mov     eax, 80070057h
0x1800205de  mov     rbx, [rsp+28h+arg_0]
0x1800205e3  mov     rsi, [rsp+28h+arg_8]
0x1800205e8  add     rsp, 20h
0x1800205ec  pop     rdi
0x1800205ed  retn
```
