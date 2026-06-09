# ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18000833c`
- end: `0x180008428`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008430`

## callees

- `0x180003f7c`
- `0x18000833c`
- `0x18000b5f6`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        ATL::CComTypeInfoHolder *a1,
        __int64 a2,
        const void **a3,
        unsigned int a4,
        LCID a5,
        _DWORD *a6)
{
  struct ITypeInfo *v6; // r14
  __int64 v9; // rbx
  __int64 result; // rax
  _WORD *v11; // r15
  __int64 v12; // rsi
  unsigned int v13; // ebp

  v6 = qword_1800120A8;
  if ( !qword_1800120A8 || (v9 = qword_1800120B8, result = 0, !qword_1800120B8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(a1, a5);
    v9 = qword_1800120B8;
    v6 = qword_1800120A8;
  }
  if ( v6 )
  {
    if ( v9 && a4 == 1 )
    {
      v11 = *a3;
      if ( *a3 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
      }
      else
      {
        LODWORD(v12) = 0;
      }
      v13 = dword_1800120C0;
      while ( (--v13 & 0x80000000) == 0 )
      {
        if ( (_DWORD)v12 == *(_DWORD *)(v9 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v9 + 16LL * v13), v11, 2LL * *(int *)(v9 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v9 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return ((__int64 (__fastcall *)(struct ITypeInfo *, const void **, _QWORD, _DWORD *))v6->lpVtbl->GetIDsOfNames)(
             v6,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x18000833c  push    rbx
0x18000833e  push    rbp
0x18000833f  push    rsi
0x180008340  push    rdi
0x180008341  push    r12
0x180008343  push    r13
0x180008345  push    r14
0x180008347  push    r15
0x180008349  sub     rsp, 38h
0x18000834d  mov     r14, cs:qword_1800120A8
0x180008354  xor     edx, edx
0x180008356  mov     r12d, r9d
0x180008359  mov     r13, r8
0x18000835c  test    r14, r14
0x18000835f  jz      short loc_18000836F
0x180008361  mov     rbx, cs:qword_1800120B8
0x180008368  mov     eax, edx
0x18000836a  test    rbx, rbx
0x18000836d  jnz     short loc_18000838B
0x18000836f  mov     edx, [rsp+78h+arg_20]; unsigned int
0x180008376  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000837b  mov     rbx, cs:qword_1800120B8
0x180008382  xor     edx, edx
0x180008384  mov     r14, cs:qword_1800120A8
0x18000838b  test    r14, r14
0x18000838e  jz      short loc_180008405
0x180008390  test    rbx, rbx
0x180008393  jz      short loc_1800083E8
0x180008395  cmp     r12d, 1
0x180008399  jnz     short loc_1800083E8
0x18000839b  mov     r15, [r13+0]
0x18000839f  test    r15, r15
0x1800083a2  jnz     short loc_1800083A8
0x1800083a4  mov     esi, edx
0x1800083a6  jmp     short loc_1800083B6
0x1800083a8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800083ac  inc     rsi
0x1800083af  cmp     [r15+rsi*2], dx
0x1800083b4  jnz     short loc_1800083AC
0x1800083b6  mov     ebp, cs:dword_1800120C0
0x1800083bc  jmp     short loc_1800083E3
0x1800083be  mov     edi, ebp
0x1800083c0  add     rdi, rdi
0x1800083c3  cmp     esi, [rbx+rdi*8+8]
0x1800083c7  jnz     short loc_1800083E3
0x1800083c9  movsxd  r8, dword ptr [rbx+rdi*8+8]
0x1800083ce  mov     rdx, r15; Buf2
0x1800083d1  mov     rcx, [rbx+rdi*8]; Buf1
0x1800083d5  add     r8, r8; Size
0x1800083d8  call    memcmp_0
0x1800083dd  xor     edx, edx
0x1800083df  test    eax, eax
0x1800083e1  jz      short loc_180008416
0x1800083e3  sub     ebp, 1
0x1800083e6  jns     short loc_1800083BE
0x1800083e8  mov     rax, [r14]
0x1800083eb  mov     r8d, r12d
0x1800083ee  mov     r9, [rsp+78h+arg_28]
0x1800083f6  mov     rdx, r13
0x1800083f9  mov     rcx, r14
0x1800083fc  mov     rax, [rax+50h]
0x180008400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008405  add     rsp, 38h
0x180008409  pop     r15
0x18000840b  pop     r14
0x18000840d  pop     r13
0x18000840f  pop     r12
0x180008411  pop     rdi
0x180008412  pop     rsi
0x180008413  pop     rbp
0x180008414  pop     rbx
0x180008415  retn
0x180008416  mov     rax, [rsp+78h+arg_28]
0x18000841e  mov     ecx, [rbx+rdi*8+0Ch]
0x180008422  mov     [rax], ecx
0x180008424  mov     eax, edx
0x180008426  jmp     short loc_180008405
```
