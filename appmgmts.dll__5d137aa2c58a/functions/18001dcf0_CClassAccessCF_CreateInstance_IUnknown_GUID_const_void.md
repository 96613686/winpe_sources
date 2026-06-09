# CClassAccessCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001dcf0`
- end: `0x18001ddae`
- name: `?CreateInstance@CClassAccessCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `190`
- prototype: `__int64 __fastcall(CClassAccessCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001dcf0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dd15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dd15`

## pseudocode

```c
__int64 __fastcall CClassAccessCF::CreateInstance(
        CClassAccessCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  int v8; // edi

  if ( a2 )
  {
    *a4 = 0;
    return 2147942487LL;
  }
  else
  {
    v6 = LocalAlloc(0, 0x30u);
    v7 = v6;
    if ( v6 )
    {
      v6[5] = 1;
      *v6 = &CClassAccess::`vftable';
      v6[1] = 0;
      *((_DWORD *)v6 + 4) = 0;
      v6[3] = 0;
      v6[4] = 0;
      v8 = ((__int64 (__fastcall *)(_QWORD *, const struct _GUID *, void **))CClassAccess::`vftable')(v6, a3, a4);
      if ( v8 < 0 )
        v8 = -2147418113;
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
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
0x18001dcf0  mov     [rsp+arg_0], rbx
0x18001dcf5  mov     [rsp+arg_8], rsi
0x18001dcfa  push    rdi
0x18001dcfb  sub     rsp, 20h
0x18001dcff  mov     rdi, r9
0x18001dd02  mov     rsi, r8
0x18001dd05  test    rdx, rdx
0x18001dd08  jnz     loc_18001DD92
0x18001dd0e  mov     edx, 30h ; '0'; uBytes
0x18001dd13  xor     ecx, ecx; uFlags
0x18001dd15  call    cs:__imp_LocalAlloc
0x18001dd1b  mov     rbx, rax
0x18001dd1e  test    rax, rax
0x18001dd21  jz      short loc_18001DD82
0x18001dd23  lea     rax, ??_7CClassAccess@@6B@; const CClassAccess::`vftable'
0x18001dd2a  mov     qword ptr [rbx+28h], 1
0x18001dd32  mov     [rbx], rax
0x18001dd35  mov     r8, rdi
0x18001dd38  mov     rax, [rax]
0x18001dd3b  mov     rdx, rsi
0x18001dd3e  mov     rcx, rbx
0x18001dd41  mov     qword ptr [rbx+8], 0
0x18001dd49  mov     dword ptr [rbx+10h], 0
0x18001dd50  mov     qword ptr [rbx+18h], 0
0x18001dd58  mov     qword ptr [rbx+20h], 0
0x18001dd60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd65  mov     edi, eax
0x18001dd67  mov     rcx, rbx
0x18001dd6a  test    edi, edi
0x18001dd6c  mov     eax, 8000FFFFh
0x18001dd71  cmovs   edi, eax
0x18001dd74  mov     rax, [rbx]
0x18001dd77  mov     rax, [rax+10h]
0x18001dd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd80  jmp     short loc_18001DD8E
0x18001dd82  mov     qword ptr [rdi], 0
0x18001dd89  mov     edi, 8007000Eh
0x18001dd8e  mov     eax, edi
0x18001dd90  jmp     short loc_18001DD9E
0x18001dd92  mov     qword ptr [r9], 0
0x18001dd99  mov     eax, 80070057h
0x18001dd9e  mov     rbx, [rsp+28h+arg_0]
0x18001dda3  mov     rsi, [rsp+28h+arg_8]
0x18001dda8  add     rsp, 20h
0x18001ddac  pop     rdi
0x18001ddad  retn
```
