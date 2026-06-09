# CChangeApplier::UpdateRunningKnowledgeStateForTransfer(int)

- ea: `0x1800465e0`
- end: `0x180046777`
- name: `?UpdateRunningKnowledgeStateForTransfer@CChangeApplier@@AEAAJH@Z`
- size: `407`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180041238`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800465e0`
- `0x180094010`

## string_xrefs

- `0x180046612`: `CChangeApplier::UpdateRunningKnowledgeStateForTransfer`
- `0x18004674f`: `CChangeApplier::UpdateRunningKnowledgeStateForTransfer`

## pseudocode

```c
__int64 __fastcall CChangeApplier::UpdateRunningKnowledgeStateForTransfer(CChangeApplier *this, int a2)
{
  PVOID *v4; // rcx
  __int64 v5; // rax
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      263,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::UpdateRunningKnowledgeStateForTransfer");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *((_QWORD *)this + 68);
  v6 = -2147467261;
  if ( v5 && *((_QWORD *)this + 64) )
  {
    v12 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v5 + 8) + 80LL))(v5 + 8, &v12);
    if ( v6 >= 0 )
    {
      v7 = v12;
      v6 = -2147217379;
      if ( v12 )
      {
        v6 = 0;
        if ( a2 )
        {
          v8 = *((_QWORD *)this + 60);
          if ( v8 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 16LL))(*((_QWORD *)this + 60));
            v7 = v12;
            *((_QWORD *)this + 60) = 0;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
          v7 = v12;
          *((_QWORD *)this + 60) = v12;
          if ( *((_QWORD *)this + 26) )
          {
            v9 = *((_QWORD *)this + 33);
            if ( v9 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
              *((_QWORD *)this + 33) = 0;
            }
            v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 24) + 48LL))(
                    *((_QWORD *)this + 24),
                    *((_QWORD *)this + 60),
                    (char *)this + 264);
            v7 = v12;
            v6 = v10;
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      264,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::UpdateRunningKnowledgeStateForTransfer",
      v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800465e0  push    rbx
0x1800465e2  push    rsi
0x1800465e3  push    rdi
0x1800465e4  push    r14
0x1800465e6  sub     rsp, 38h
0x1800465ea  mov     esi, edx
0x1800465ec  mov     rbx, rcx
0x1800465ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800465f6  lea     r14, WPP_GLOBAL_Control
0x1800465fd  cmp     rcx, r14
0x180046600  jz      short loc_180046631
0x180046602  test    byte ptr [rcx+1Ch], 8
0x180046606  jz      short loc_180046631
0x180046608  cmp     byte ptr [rcx+19h], 5
0x18004660c  jb      short loc_180046631
0x18004660e  mov     rcx, [rcx+10h]
0x180046612  lea     r9, aCchangeapplier_120; "CChangeApplier::UpdateRunningKnowledgeS"...
0x180046619  mov     edx, 107h
0x18004661e  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180046625  call    WPP_SF_s
0x18004662a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046631  mov     rax, [rbx+220h]
0x180046638  mov     edi, 80004003h
0x18004663d  test    rax, rax
0x180046640  jz      loc_18004673A
0x180046646  cmp     qword ptr [rbx+200h], 0
0x18004664e  jz      loc_18004673A
0x180046654  lea     rcx, [rax+8]
0x180046658  mov     [rsp+58h+arg_0], 0
0x180046661  mov     rax, [rcx]
0x180046664  lea     rdx, [rsp+58h+arg_0]
0x180046669  mov     rax, [rax+50h]
0x18004666d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046672  mov     edi, eax
0x180046674  test    eax, eax
0x180046676  js      loc_180046733
0x18004667c  mov     rcx, [rsp+58h+arg_0]
0x180046681  mov     edi, 8004101Dh
0x180046686  test    rcx, rcx
0x180046689  jz      loc_180046733
0x18004668f  xor     edi, edi
0x180046691  test    esi, esi
0x180046693  jz      loc_180046727
0x180046699  mov     rdx, [rbx+1E0h]
0x1800466a0  test    rdx, rdx
0x1800466a3  jz      short loc_1800466C0
0x1800466a5  mov     rax, [rdx]
0x1800466a8  mov     rcx, rdx
0x1800466ab  mov     rax, [rax+10h]
0x1800466af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466b4  mov     rcx, [rsp+58h+arg_0]
0x1800466b9  mov     [rbx+1E0h], rdi
0x1800466c0  mov     rax, [rcx]
0x1800466c3  mov     rax, [rax+8]
0x1800466c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466cc  mov     rcx, [rsp+58h+arg_0]
0x1800466d1  mov     [rbx+1E0h], rcx
0x1800466d8  cmp     [rbx+0D0h], rdi
0x1800466df  jz      short loc_180046727
0x1800466e1  lea     rdi, [rbx+108h]
0x1800466e8  mov     rcx, [rdi]
0x1800466eb  test    rcx, rcx
0x1800466ee  jz      short loc_180046703
0x1800466f0  mov     rax, [rcx]
0x1800466f3  mov     rax, [rax+10h]
0x1800466f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466fc  mov     qword ptr [rdi], 0
0x180046703  mov     rcx, [rbx+0C0h]
0x18004670a  mov     r8, rdi
0x18004670d  mov     rdx, [rbx+1E0h]
0x180046714  mov     rax, [rcx]
0x180046717  mov     rax, [rax+30h]
0x18004671b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046720  mov     rcx, [rsp+58h+arg_0]
0x180046725  mov     edi, eax
0x180046727  mov     rax, [rcx]
0x18004672a  mov     rax, [rax+10h]
0x18004672e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046733  mov     rcx, cs:WPP_GLOBAL_Control
0x18004673a  cmp     rcx, r14
0x18004673d  jz      short loc_18004676B
0x18004673f  test    byte ptr [rcx+1Ch], 8
0x180046743  jz      short loc_18004676B
0x180046745  cmp     byte ptr [rcx+19h], 5
0x180046749  jb      short loc_18004676B
0x18004674b  mov     rcx, [rcx+10h]
0x18004674f  lea     r9, aCchangeapplier_120; "CChangeApplier::UpdateRunningKnowledgeS"...
0x180046756  mov     edx, 108h
0x18004675b  mov     [rsp+58h+var_38], edi
0x18004675f  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180046766  call    WPP_SF_sD
0x18004676b  mov     eax, edi
0x18004676d  add     rsp, 38h
0x180046771  pop     r14
0x180046773  pop     rdi
0x180046774  pop     rsi
0x180046775  pop     rbx
0x180046776  retn
```
