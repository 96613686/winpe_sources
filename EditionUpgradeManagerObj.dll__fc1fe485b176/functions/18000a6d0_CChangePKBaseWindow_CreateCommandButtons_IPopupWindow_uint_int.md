# CChangePKBaseWindow::CreateCommandButtons(IPopupWindow *,uint,int)

- ea: `0x18000a6d0`
- end: `0x18000a9b4`
- name: `?CreateCommandButtons@CChangePKBaseWindow@@UEAAJPEAUIPopupWindow@@IH@Z`
- size: `740`
- prototype: `__int64 __fastcall(CChangePKBaseWindow *this, struct IPopupWindow *, int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e90`
- `0x180001e9c`
- `0x1800090dc`
- `0x180009480`
- `0x18000a4c0`
- `0x18000a6d0`
- `0x18000af78`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a994`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a986`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a986`

## pseudocode

```c
__int64 __fastcall CChangePKBaseWindow::CreateCommandButtons(
        CChangePKBaseWindow *this,
        struct IPopupWindow *a2,
        int a3,
        int a4)
{
  int v4; // esi
  void *v5; // rbx
  unsigned int v9; // edi
  int v10; // ecx
  int v11; // eax
  void *v12; // rax
  int v13; // edx
  __int64 v14; // rcx
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h]
  __int64 v20; // [rsp+88h] [rbp+48h] BYREF
  int v21; // [rsp+98h] [rbp+58h]

  v21 = a4;
  v4 = 0;
  v18 = 0;
  v5 = 0;
  lpMem = 0;
  v20 = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
LABEL_3:
    v10 = v9;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_37;
  }
  if ( (a3 & 0x10000000) != 0 )
  {
    v11 = (*(__int64 (__fastcall **)(CChangePKBaseWindow *, __int64, __int64, __int64 *))(*(_QWORD *)this + 24LL))(
            this,
            106,
            47,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v11 = CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(
            (__int64)&v18,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v4 = HIDWORD(v18);
  }
  if ( (a3 & 0x10000) != 0 )
  {
    v11 = (*(__int64 (__fastcall **)(CChangePKBaseWindow *, __int64, __int64, __int64 *))(*(_QWORD *)this + 24LL))(
            this,
            103,
            38,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v11 = CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(
            (__int64)&v18,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v4 = HIDWORD(v18);
  }
  if ( (a3 & 0x100000) != 0 )
  {
    v11 = (*(__int64 (__fastcall **)(CChangePKBaseWindow *, __int64, __int64, __int64 *))(*(_QWORD *)this + 24LL))(
            this,
            107,
            63,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v11 = CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(
            (__int64)&v18,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v4 = HIDWORD(v18);
  }
  if ( (a3 & 0x100) != 0 )
  {
    v11 = (*(__int64 (__fastcall **)(CChangePKBaseWindow *, __int64, __int64, __int64 *))(*(_QWORD *)this + 24LL))(
            this,
            101,
            4,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v11 = CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(
            (__int64)&v18,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v4 = HIDWORD(v18);
  }
  if ( (a3 & 0x1000) != 0 )
  {
    v11 = (*(__int64 (__fastcall **)(CChangePKBaseWindow *, __int64, __int64, __int64 *))(*(_QWORD *)this + 24LL))(
            this,
            102,
            1,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v11 = CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(
            (__int64)&v18,
            &v20);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v4 = HIDWORD(v18);
  }
  if ( v4 <= 0 )
  {
    v9 = -2147023483;
    goto LABEL_3;
  }
  v12 = operator new[](saturated_mul(v4, 8u));
  v13 = 0;
  v5 = v12;
  do
  {
    v14 = v13++;
    *((_QWORD *)v12 + v14) = *((_QWORD *)lpMem + v14);
  }
  while ( v13 < v4 );
  v11 = (*(__int64 (__fastcall **)(struct IPopupWindow *, _QWORD, void *))(*(_QWORD *)a2 + 64LL))(
          a2,
          (unsigned int)v4,
          v12);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_7;
  v11 = (*(__int64 (__fastcall **)(struct IPopupWindow *, _QWORD))(*(_QWORD *)a2 + 88LL))(a2, (unsigned int)(v4 - 1));
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_7;
  v11 = (*(__int64 (__fastcall **)(struct IPopupWindow *, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, (unsigned int)(v4 - 1));
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_7;
  if ( v21 )
    v4 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 120LL))(
          *((_QWORD *)this + 2),
          (unsigned int)v4);
  v9 = v11;
  if ( v11 < 0 )
  {
LABEL_7:
    v10 = v11;
    goto LABEL_4;
  }
  *((_DWORD *)this + 10) = a3;
LABEL_37:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v5 )
    operator delete(v5);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::SetSize(&v18, 0);
  v15 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
  }
  return v9;
}

```

## disassembly

```asm
0x18000a6d0  mov     [rsp-38h+arg_0], rbx
0x18000a6d5  mov     [rsp-38h+arg_18], r9d
0x18000a6da  push    rbp
0x18000a6db  push    rsi
0x18000a6dc  push    rdi
0x18000a6dd  push    r12
0x18000a6df  push    r13
0x18000a6e1  push    r14
0x18000a6e3  push    r15
0x18000a6e5  mov     rbp, rsp
0x18000a6e8  sub     rsp, 40h
0x18000a6ec  xor     esi, esi
0x18000a6ee  mov     [rbp+var_10], 0
0x18000a6f6  xor     ebx, ebx
0x18000a6f8  mov     [rbp+lpMem], rsi
0x18000a6fc  mov     [rbp+arg_8], rsi
0x18000a700  mov     r15d, r8d
0x18000a703  mov     r12, rdx
0x18000a706  mov     r14, rcx
0x18000a709  test    rdx, rdx
0x18000a70c  jnz     short loc_18000A71F
0x18000a70e  mov     edi, 80070057h
0x18000a713  mov     ecx, edi
0x18000a715  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a71a  jmp     loc_18000A941
0x18000a71f  bt      r15d, 1Ch
0x18000a724  jnb     short loc_18000A75F
0x18000a726  mov     rax, [rcx]
0x18000a729  lea     r9, [rbp+arg_8]
0x18000a72d  mov     edx, 6Ah ; 'j'
0x18000a732  mov     rax, [rax+18h]
0x18000a736  lea     r8d, [rdx-3Bh]
0x18000a73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a73f  mov     edi, eax
0x18000a741  test    eax, eax
0x18000a743  jns     short loc_18000A749
0x18000a745  mov     ecx, eax
0x18000a747  jmp     short loc_18000A715
0x18000a749  lea     rdx, [rbp+arg_8]
0x18000a74d  lea     rcx, [rbp+var_10]
0x18000a751  call    ?Append@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBV?$DP_COM@UIPopupCommand@@@@@Z; CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(DP_COM<IPopupCommand> const &)
0x18000a756  mov     edi, eax
0x18000a758  test    eax, eax
0x18000a75a  js      short loc_18000A745
0x18000a75c  mov     esi, dword ptr [rbp+var_10+4]
0x18000a75f  bt      r15d, 10h
0x18000a764  jnb     short loc_18000A79E
0x18000a766  mov     rax, [r14]
0x18000a769  lea     r9, [rbp+arg_8]
0x18000a76d  mov     edx, 67h ; 'g'
0x18000a772  mov     rcx, r14
0x18000a775  mov     rax, [rax+18h]
0x18000a779  lea     r8d, [rdx-41h]
0x18000a77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a782  mov     edi, eax
0x18000a784  test    eax, eax
0x18000a786  js      short loc_18000A745
0x18000a788  lea     rdx, [rbp+arg_8]
0x18000a78c  lea     rcx, [rbp+var_10]
0x18000a790  call    ?Append@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBV?$DP_COM@UIPopupCommand@@@@@Z; CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(DP_COM<IPopupCommand> const &)
0x18000a795  mov     edi, eax
0x18000a797  test    eax, eax
0x18000a799  js      short loc_18000A745
0x18000a79b  mov     esi, dword ptr [rbp+var_10+4]
0x18000a79e  bt      r15d, 14h
0x18000a7a3  jnb     short loc_18000A7E5
0x18000a7a5  mov     rax, [r14]
0x18000a7a8  lea     r9, [rbp+arg_8]
0x18000a7ac  mov     edx, 6Bh ; 'k'
0x18000a7b1  mov     rcx, r14
0x18000a7b4  mov     rax, [rax+18h]
0x18000a7b8  lea     r8d, [rdx-2Ch]
0x18000a7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c1  mov     edi, eax
0x18000a7c3  test    eax, eax
0x18000a7c5  js      loc_18000A745
0x18000a7cb  lea     rdx, [rbp+arg_8]
0x18000a7cf  lea     rcx, [rbp+var_10]
0x18000a7d3  call    ?Append@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBV?$DP_COM@UIPopupCommand@@@@@Z; CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(DP_COM<IPopupCommand> const &)
0x18000a7d8  mov     edi, eax
0x18000a7da  test    eax, eax
0x18000a7dc  js      loc_18000A745
0x18000a7e2  mov     esi, dword ptr [rbp+var_10+4]
0x18000a7e5  bt      r15d, 8
0x18000a7ea  jnb     short loc_18000A82C
0x18000a7ec  mov     rax, [r14]
0x18000a7ef  lea     r9, [rbp+arg_8]
0x18000a7f3  mov     edx, 65h ; 'e'
0x18000a7f8  mov     rcx, r14
0x18000a7fb  mov     rax, [rax+18h]
0x18000a7ff  lea     r8d, [rdx-61h]
0x18000a803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a808  mov     edi, eax
0x18000a80a  test    eax, eax
0x18000a80c  js      loc_18000A745
0x18000a812  lea     rdx, [rbp+arg_8]
0x18000a816  lea     rcx, [rbp+var_10]
0x18000a81a  call    ?Append@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBV?$DP_COM@UIPopupCommand@@@@@Z; CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(DP_COM<IPopupCommand> const &)
0x18000a81f  mov     edi, eax
0x18000a821  test    eax, eax
0x18000a823  js      loc_18000A745
0x18000a829  mov     esi, dword ptr [rbp+var_10+4]
0x18000a82c  bt      r15d, 0Ch
0x18000a831  jnb     short loc_18000A873
0x18000a833  mov     rax, [r14]
0x18000a836  lea     r9, [rbp+arg_8]
0x18000a83a  mov     edx, 66h ; 'f'
0x18000a83f  mov     rcx, r14
0x18000a842  mov     rax, [rax+18h]
0x18000a846  lea     r8d, [rdx-65h]
0x18000a84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a84f  mov     edi, eax
0x18000a851  test    eax, eax
0x18000a853  js      loc_18000A745
0x18000a859  lea     rdx, [rbp+arg_8]
0x18000a85d  lea     rcx, [rbp+var_10]
0x18000a861  call    ?Append@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBV?$DP_COM@UIPopupCommand@@@@@Z; CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::Append(DP_COM<IPopupCommand> const &)
0x18000a866  mov     edi, eax
0x18000a868  test    eax, eax
0x18000a86a  js      loc_18000A745
0x18000a870  mov     esi, dword ptr [rbp+var_10+4]
0x18000a873  test    esi, esi
0x18000a875  jg      short loc_18000A881
0x18000a877  mov     edi, 80070585h
0x18000a87c  jmp     loc_18000A713
0x18000a881  movsxd  rcx, esi
0x18000a884  mov     eax, 8
0x18000a889  mul     rcx
0x18000a88c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a893  cmovb   rax, rcx
0x18000a897  mov     rcx, rax; unsigned __int64
0x18000a89a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a89f  xor     edx, edx
0x18000a8a1  mov     rbx, rax
0x18000a8a4  test    esi, esi
0x18000a8a6  jle     short loc_18000A8BD
0x18000a8a8  mov     rax, [rbp+lpMem]
0x18000a8ac  movsxd  rcx, edx
0x18000a8af  inc     edx
0x18000a8b1  mov     rax, [rax+rcx*8]
0x18000a8b5  mov     [rbx+rcx*8], rax
0x18000a8b9  cmp     edx, esi
0x18000a8bb  jl      short loc_18000A8A8
0x18000a8bd  mov     rax, [r12]
0x18000a8c1  mov     r8, rbx
0x18000a8c4  mov     edx, esi
0x18000a8c6  mov     rcx, r12
0x18000a8c9  mov     rax, [rax+40h]
0x18000a8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8d2  mov     edi, eax
0x18000a8d4  test    eax, eax
0x18000a8d6  js      loc_18000A745
0x18000a8dc  mov     rax, [r12]
0x18000a8e0  lea     edx, [rsi-1]
0x18000a8e3  mov     rcx, r12
0x18000a8e6  mov     rax, [rax+58h]
0x18000a8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ef  mov     edi, eax
0x18000a8f1  test    eax, eax
0x18000a8f3  js      loc_18000A745
0x18000a8f9  mov     rax, [r12]
0x18000a8fd  lea     edx, [rsi-1]
0x18000a900  mov     rcx, r12
0x18000a903  mov     rax, [rax+68h]
0x18000a907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a90c  mov     edi, eax
0x18000a90e  test    eax, eax
0x18000a910  js      loc_18000A745
0x18000a916  mov     rcx, [r14+10h]
0x18000a91a  xor     r8d, r8d
0x18000a91d  cmp     [rbp+arg_18], r8d
0x18000a921  cmovnz  esi, r8d
0x18000a925  mov     rax, [rcx]
0x18000a928  mov     edx, esi
0x18000a92a  mov     rax, [rax+78h]
0x18000a92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a933  mov     edi, eax
0x18000a935  test    eax, eax
0x18000a937  js      loc_18000A745
0x18000a93d  mov     [r14+28h], r15d
0x18000a941  mov     ecx, edi
0x18000a943  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a948  test    rbx, rbx
0x18000a94b  jz      short loc_18000A955
0x18000a94d  mov     rcx, rbx; void *
0x18000a950  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a955  mov     rcx, [rbp+arg_8]
0x18000a959  test    rcx, rcx
0x18000a95c  jz      short loc_18000A972
0x18000a95e  mov     rax, [rcx]
0x18000a961  mov     rax, [rax+10h]
0x18000a965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a96a  mov     [rbp+arg_8], 0
0x18000a972  xor     edx, edx
0x18000a974  lea     rcx, [rbp+var_10]
0x18000a978  call    ?SetSize@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18000a97d  mov     rbx, [rbp+lpMem]
0x18000a981  test    rbx, rbx
0x18000a984  jz      short loc_18000A99A
0x18000a986  call    cs:__imp_GetProcessHeap
0x18000a98c  mov     r8, rbx; lpMem
0x18000a98f  xor     edx, edx; dwFlags
0x18000a991  mov     rcx, rax; hHeap
0x18000a994  call    cs:__imp_HeapFree
0x18000a99a  mov     rbx, [rsp+40h+arg_0]
0x18000a9a2  mov     eax, edi
0x18000a9a4  add     rsp, 40h
0x18000a9a8  pop     r15
0x18000a9aa  pop     r14
0x18000a9ac  pop     r13
0x18000a9ae  pop     r12
0x18000a9b0  pop     rdi
0x18000a9b1  pop     rsi
0x18000a9b2  pop     rbp
0x18000a9b3  retn
```
