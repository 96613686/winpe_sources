# CFilterWithBatchedChunk::GetValue(tagPROPVARIANT * *)

- ea: `0x140040df0`
- end: `0x140040ec0`
- name: `?GetValue@CFilterWithBatchedChunk@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CFilterWithBatchedChunk *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140028044`
- `0x140040df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140040e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140040e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140040e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140040e78`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x140040e50`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x140040e50`

## string_xrefs

- `0x140040e61`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`
- `0x140040ea5`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`

## pseudocode

```c
__int64 __fastcall CFilterWithBatchedChunk::GetValue(CFilterWithBatchedChunk *this, PROPVARIANT **a2)
{
  __int64 v2; // rax
  PROPVARIANT *v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  unsigned int v9; // esi
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *((unsigned int *)this + 18);
  if ( (_DWORD)v2 == *((_DWORD *)this + 17) || *(_DWORD *)(104 * v2 + *((_QWORD *)this + 11) + 8) != 2 )
  {
    v6 = -2147215610;
    v7 = 128;
    goto LABEL_9;
  }
  v5 = (PROPVARIANT *)CoTaskMemAlloc(0x18u);
  if ( !v5 )
  {
    v6 = -2147024882;
    v7 = 131;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)v6,
      v11);
    return v6;
  }
  v8 = PropVariantCopy(v5, (const PROPVARIANT *)(104LL * *((unsigned int *)this + 18) + *((_QWORD *)this + 11) + 72LL));
  v9 = v8;
  if ( v8 >= 0 )
  {
    *a2 = v5;
    return *(unsigned int *)(104LL * *((unsigned int *)this + 18) + *((_QWORD *)this + 11) + 96);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)(unsigned int)v8,
      v11);
    CoTaskMemFree(v5);
    return v9;
  }
}

```

## disassembly

```asm
0x140040df0  push    rbx
0x140040df2  push    rsi
0x140040df3  push    rdi
0x140040df4  push    r14
0x140040df6  sub     rsp, 28h
0x140040dfa  mov     eax, [rcx+48h]
0x140040dfd  mov     r14, rdx
0x140040e00  mov     rbx, rcx
0x140040e03  cmp     eax, [rcx+44h]
0x140040e06  jz      loc_140040E96
0x140040e0c  imul    r8, rax, 68h ; 'h'
0x140040e10  mov     rax, [rcx+58h]
0x140040e14  cmp     dword ptr [r8+rax+8], 2
0x140040e1a  jnz     short loc_140040E96
0x140040e1c  mov     ecx, 18h; cb
0x140040e21  call    cs:__imp_CoTaskMemAlloc
0x140040e27  mov     rdi, rax
0x140040e2a  test    rax, rax
0x140040e2d  jnz     short loc_140040E3B
0x140040e2f  mov     ebx, 8007000Eh
0x140040e34  mov     edx, 83h
0x140040e39  jmp     short loc_140040EA0
0x140040e3b  mov     eax, [rbx+48h]
0x140040e3e  mov     rdx, [rbx+58h]
0x140040e42  imul    rcx, rax, 68h ; 'h'
0x140040e46  add     rdx, 48h ; 'H'
0x140040e4a  add     rdx, rcx; pvarSrc
0x140040e4d  mov     rcx, rdi; pvarDest
0x140040e50  call    cs:__imp_PropVariantCopy
0x140040e56  mov     esi, eax
0x140040e58  test    eax, eax
0x140040e5a  jns     short loc_140040E82
0x140040e5c  mov     rcx, [rsp+48h]; this
0x140040e61  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140040e68  mov     r9d, eax; char *
0x140040e6b  mov     edx, 84h; void *
0x140040e70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040e75  mov     rcx, rdi; pv
0x140040e78  call    cs:__imp_CoTaskMemFree
0x140040e7e  mov     eax, esi
0x140040e80  jmp     short loc_140040EB6
0x140040e82  mov     [r14], rdi
0x140040e85  mov     eax, [rbx+48h]
0x140040e88  imul    rcx, rax, 68h ; 'h'
0x140040e8c  mov     rax, [rbx+58h]
0x140040e90  mov     eax, [rcx+rax+60h]
0x140040e94  jmp     short loc_140040EB6
0x140040e96  mov     ebx, 80041706h
0x140040e9b  mov     edx, 80h; void *
0x140040ea0  mov     rcx, [rsp+48h]; this
0x140040ea5  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140040eac  mov     r9d, ebx; char *
0x140040eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040eb4  mov     eax, ebx
0x140040eb6  add     rsp, 28h
0x140040eba  pop     r14
0x140040ebc  pop     rdi
0x140040ebd  pop     rsi
0x140040ebe  pop     rbx
0x140040ebf  retn
```
