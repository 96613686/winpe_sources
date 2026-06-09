# CCommandHandler::SetSelection(IShellItemArray *)

- ea: `0x180004560`
- end: `0x18000466d`
- name: `?SetSelection@CCommandHandler@@UEAAJPEAUIShellItemArray@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(CCommandHandler *this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004560`
- `0x1800061ec`
- `0x18000c010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800045a5`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800045a5`

## pseudocode

```c
__int64 __fastcall CCommandHandler::SetSelection(CCommandHandler *this, struct IUnknown *a2)
{
  struct IUnknown *v4; // rcx
  int v5; // edx
  HRESULT v6; // edi
  int v7; // eax
  int v9; // [rsp+40h] [rbp+20h] BYREF
  struct IUnknown *v10; // [rsp+50h] [rbp+30h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+38h] BYREF

  v4 = 0;
  v10 = 0;
  v5 = *((_DWORD *)this + 10);
  if ( !v5 )
  {
    if ( a2 )
    {
      v6 = 0;
      ATL::AtlComPtrAssign(&v10, a2);
      goto LABEL_10;
    }
LABEL_16:
    v9 = 0;
    goto LABEL_17;
  }
  if ( v5 != 1 )
    goto LABEL_16;
  ppvOut = 0;
  v6 = IUnknown_QueryService(
         *((IUnknown **)this + 9),
         &IID_IFolderView,
         &GUID_1af3a467_214f_4298_908e_06b03e0b39f9,
         &ppvOut);
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(void *, GUID *, struct IUnknown **))(*(_QWORD *)ppvOut + 40LL))(
           ppvOut,
           &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
           &v10);
  if ( ppvOut )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
LABEL_10:
  v4 = v10;
  if ( !v10 )
    goto LABEL_16;
  v9 = 0;
  if ( v6 >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(struct IUnknown *, int *))a2->lpVtbl[2].AddRef)(a2, &v9);
    if ( v9 == 1 && v7 >= 0 )
      ((void (__fastcall *)(struct IUnknown *, _QWORD, char *))a2->lpVtbl[2].Release)(a2, 0, (char *)this + 48);
    v4 = v10;
  }
LABEL_17:
  if ( v4 )
    ((void (__fastcall *)(struct IUnknown *))v4->lpVtbl->Release)(v4);
  return 0;
}

```

## disassembly

```asm
0x180004560  mov     [rsp-18h+arg_8], rbx
0x180004565  push    rbp
0x180004566  push    rsi
0x180004567  push    rdi
0x180004568  mov     rbp, rsp
0x18000456b  sub     rsp, 20h
0x18000456f  mov     rbx, rdx
0x180004572  mov     rsi, rcx
0x180004575  xor     ecx, ecx
0x180004577  mov     [rbp+arg_10], rcx
0x18000457b  mov     edx, [rsi+28h]
0x18000457e  test    edx, edx
0x180004580  jz      short loc_1800045E6
0x180004582  cmp     edx, 1
0x180004585  jnz     loc_180004645
0x18000458b  mov     [rbp+ppvOut], rcx
0x18000458f  lea     r9, [rbp+ppvOut]; ppvOut
0x180004593  lea     r8, _GUID_1af3a467_214f_4298_908e_06b03e0b39f9; riid
0x18000459a  lea     rdx, IID_IFolderView; guidService
0x1800045a1  mov     rcx, [rsi+48h]; punk
0x1800045a5  call    cs:__imp_IUnknown_QueryService
0x1800045ab  mov     edi, eax
0x1800045ad  test    eax, eax
0x1800045af  js      short loc_1800045CE
0x1800045b1  mov     rcx, [rbp+ppvOut]
0x1800045b5  mov     rax, [rcx]
0x1800045b8  lea     r8, [rbp+arg_10]
0x1800045bc  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x1800045c3  mov     rax, [rax+28h]
0x1800045c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045cc  mov     edi, eax
0x1800045ce  mov     rcx, [rbp+ppvOut]
0x1800045d2  test    rcx, rcx
0x1800045d5  jz      short loc_1800045E4
0x1800045d7  mov     rax, [rcx]
0x1800045da  mov     rax, [rax+10h]
0x1800045de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e3  nop
0x1800045e4  jmp     short loc_1800045F9
0x1800045e6  test    rbx, rbx
0x1800045e9  jz      short loc_180004645
0x1800045eb  xor     edi, edi
0x1800045ed  mov     rdx, rbx; struct IUnknown *
0x1800045f0  lea     rcx, [rbp+arg_10]; struct IUnknown **
0x1800045f4  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800045f9  mov     rcx, [rbp+arg_10]
0x1800045fd  test    rcx, rcx
0x180004600  jz      short loc_180004645
0x180004602  mov     [rbp+arg_0], 0
0x180004609  test    edi, edi
0x18000460b  js      short loc_18000464C
0x18000460d  mov     rax, [rbx]
0x180004610  lea     rdx, [rbp+arg_0]
0x180004614  mov     rcx, rbx
0x180004617  mov     rax, [rax+38h]
0x18000461b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004620  cmp     [rbp+arg_0], 1
0x180004624  jnz     short loc_18000463F
0x180004626  test    eax, eax
0x180004628  js      short loc_18000463F
0x18000462a  mov     rax, [rbx]
0x18000462d  lea     r8, [rsi+30h]
0x180004631  xor     edx, edx
0x180004633  mov     rcx, rbx
0x180004636  mov     rax, [rax+40h]
0x18000463a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463f  mov     rcx, [rbp+arg_10]
0x180004643  jmp     short loc_18000464C
0x180004645  mov     [rbp+arg_0], 0
0x18000464c  test    rcx, rcx
0x18000464f  jz      short loc_18000465E
0x180004651  mov     rax, [rcx]
0x180004654  mov     rax, [rax+10h]
0x180004658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000465d  nop
0x18000465e  xor     eax, eax
0x180004660  mov     rbx, [rsp+20h+arg_8]
0x180004665  add     rsp, 20h
0x180004669  pop     rdi
0x18000466a  pop     rsi
0x18000466b  pop     rbp
0x18000466c  retn
```
