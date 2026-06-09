# CElementWithIUnknown::GetUnknownFromElement(DirectUI::Element *)

- ea: `0x18002c230`
- end: `0x18002c2b5`
- name: `?GetUnknownFromElement@CElementWithIUnknown@@SAPEAUIUnknown@@PEAVElement@DirectUI@@@Z`
- size: `133`
- prototype: `struct IUnknown *__fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002b930`

## callees

- `0x18002c230`
- `0x18002e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18002c28b`
- `KERNEL32!CompareStringOrdinal` at `0x18002c28b`

## pseudocode

```c
struct IUnknown *__fastcall CElementWithIUnknown::GetUnknownFromElement(struct DirectUI::Element *a1)
{
  __int64 v2; // rbp
  __int64 (*i)(void); // rax
  __int64 v4; // rdi
  const WCHAR *v5; // rbx
  const WCHAR *v6; // rax

  v2 = 0;
  for ( i = *(__int64 (**)(void))(*(_QWORD *)a1 + 280LL); ; i = *(__int64 (**)(void))(*(_QWORD *)v4 + 56LL) )
  {
    v4 = i();
    if ( !v4 )
      break;
    v5 = (const WCHAR *)(*(__int64 (__fastcall **)(struct DirectUI::IClassInfo *))(*(_QWORD *)CElementWithIUnknown::Class
                                                                                 + 64LL))(CElementWithIUnknown::Class);
    v6 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
    if ( CompareStringOrdinal(v6, -1, v5, -1, 0) == 2 )
      return (struct IUnknown *)((char *)a1 + 200);
  }
  return (struct IUnknown *)v2;
}

```

## disassembly

```asm
0x18002c230  push    rbx
0x18002c232  push    rbp
0x18002c233  push    rsi
0x18002c234  push    rdi
0x18002c235  sub     rsp, 38h
0x18002c239  mov     rax, [rcx]
0x18002c23c  mov     rsi, rcx
0x18002c23f  xor     ebp, ebp
0x18002c241  mov     rax, [rax+118h]
0x18002c248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c24d  mov     rdi, rax
0x18002c250  test    rax, rax
0x18002c253  jz      short loc_18002C2A9
0x18002c255  mov     rcx, cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x18002c25c  mov     rax, [rcx]
0x18002c25f  mov     rax, [rax+40h]
0x18002c263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c268  mov     rbx, rax
0x18002c26b  mov     rcx, rdi
0x18002c26e  mov     rax, [rdi]
0x18002c271  mov     rax, [rax+40h]
0x18002c275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c27a  or      r9d, 0FFFFFFFFh; cchCount2
0x18002c27e  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x18002c282  or      edx, r9d; cchCount1
0x18002c285  mov     r8, rbx; lpString2
0x18002c288  mov     rcx, rax; lpString1
0x18002c28b  call    cs:__imp_CompareStringOrdinal
0x18002c291  cmp     eax, 2
0x18002c294  jz      short loc_18002C2A2
0x18002c296  mov     rax, [rdi]
0x18002c299  mov     rcx, rdi
0x18002c29c  mov     rax, [rax+38h]
0x18002c2a0  jmp     short loc_18002C248
0x18002c2a2  lea     rbp, [rsi+0C8h]
0x18002c2a9  mov     rax, rbp
0x18002c2ac  add     rsp, 38h
0x18002c2b0  pop     rdi
0x18002c2b1  pop     rsi
0x18002c2b2  pop     rbp
0x18002c2b3  pop     rbx
0x18002c2b4  retn
```
