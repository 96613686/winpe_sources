# COlePropertyPage::XPropertyPage::SetObjects(ulong,IUnknown * *)

- ea: `0x1800bfee0`
- end: `0x1800c0037`
- name: `?SetObjects@XPropertyPage@COlePropertyPage@@UEAAJKPEAPEAUIUnknown@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(COlePropertyPage::XPropertyPage *__hidden this, unsigned int, struct IUnknown **)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x18000ce50`
- `0x180011480`
- `0x18002cfb0`
- `0x1800b7a40`
- `0x1800bda20`
- `0x1800bfe80`
- `0x1800bfee0`
- `0x1800d7010`

## import_xrefs

- `USER32!IsWindowVisible` at `0x1800bffcb`
- `USER32!IsWindowVisible` at `0x1800bffcb`
- `USER32!LockWindowUpdate` at `0x1800bffd9`
- `USER32!LockWindowUpdate` at `0x1800c001a`
- `USER32!LockWindowUpdate` at `0x1800bffd9`
- `USER32!LockWindowUpdate` at `0x1800c001a`

## pseudocode

```c
__int64 __fastcall COlePropertyPage::XPropertyPage::SetObjects(
        COlePropertyPage::XPropertyPage *this,
        unsigned int a2,
        struct IUnknown **a3)
{
  char *v3; // rdi
  unsigned __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 Data; // r14
  __int64 v8; // r13
  int v9; // ebp
  size_t v10; // rax
  size_t v11; // rax
  __int64 i; // rbx
  __int64 result; // rax
  HWND v14; // rcx

  v3 = (char *)this - 384;
  v4 = a2;
  v5 = *((_QWORD *)this - 41);
  Data = CThreadLocal<_AFX_THREAD_STATE>::GetData();
  v8 = *(_QWORD *)(Data + 8);
  *(_QWORD *)(Data + 8) = v5;
  COlePropertyPage::CleanupObjectArray((COlePropertyPage *)v3);
  v9 = 1;
  if ( (_DWORD)v4 )
  {
    v10 = 8 * v4;
    if ( !is_mul_ok(v4, 8u) )
      v10 = -1;
    *((_QWORD *)v3 + 37) = operator new(v10);
    v11 = 4 * v4;
    if ( !is_mul_ok(v4, 4u) )
      v11 = -1;
    *((_QWORD *)v3 + 38) = operator new(v11);
    for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
    {
      result = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64))a3[i]->lpVtbl->QueryInterface)(
                 a3[i],
                 &IID_IDispatch,
                 *((_QWORD *)v3 + 37) + 8 * i);
      if ( (int)result < 0 )
        goto LABEL_20;
      AfxConnectionAdvise(
        a3[i],
        &IID_IPropertyNotifySink,
        (struct IUnknown *)v3 + 49,
        0,
        (unsigned int *)(*((_QWORD *)v3 + 38) + 4 * i));
    }
  }
  v14 = (HWND)*((_QWORD *)v3 + 8);
  *((_DWORD *)v3 + 79) = v4;
  if ( v14 && IsWindowVisible(v14) )
    LockWindowUpdate(*((HWND *)v3 + 8));
  else
    v9 = 0;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 440LL))(v3);
  if ( (_DWORD)v4 && *((_QWORD *)v3 + 8) )
  {
    CWnd::UpdateData((CWnd *)v3, 0);
    COlePropertyPage::SetModifiedFlag((COlePropertyPage *)v3, 0);
  }
  if ( v9 )
    LockWindowUpdate(0);
  result = 0;
LABEL_20:
  *(_QWORD *)(Data + 8) = v8;
  return result;
}

```

## disassembly

```asm
0x1800bfee0  push    rbx
0x1800bfee2  push    rbp
0x1800bfee3  push    rsi
0x1800bfee4  push    rdi
0x1800bfee5  push    r12
0x1800bfee7  push    r13
0x1800bfee9  push    r14
0x1800bfeeb  push    r15
0x1800bfeed  sub     rsp, 38h
0x1800bfef1  lea     rdi, [rcx-180h]
0x1800bfef8  mov     esi, edx
0x1800bfefa  mov     rbx, [rdi+38h]
0x1800bfefe  mov     r12, r8
0x1800bff01  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x1800bff06  mov     rcx, rdi; this
0x1800bff09  mov     r14, rax
0x1800bff0c  mov     r13, [rax+8]
0x1800bff10  mov     [rax+8], rbx
0x1800bff14  call    ?CleanupObjectArray@COlePropertyPage@@IEAAXXZ; COlePropertyPage::CleanupObjectArray(void)
0x1800bff19  mov     ebp, 1
0x1800bff1e  test    esi, esi
0x1800bff20  jz      loc_1800BFFBC
0x1800bff26  lea     eax, [rbp+7]
0x1800bff29  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800bff30  mul     rsi
0x1800bff33  cmovb   rax, r15
0x1800bff37  mov     rcx, rax; Size
0x1800bff3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bff3f  mov     [rdi+128h], rax
0x1800bff46  lea     eax, [rbp+3]
0x1800bff49  mul     rsi
0x1800bff4c  cmovb   rax, r15
0x1800bff50  mov     rcx, rax; Size
0x1800bff53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bff58  mov     [rdi+130h], rax
0x1800bff5f  xor     ebx, ebx
0x1800bff61  cmp     ebx, esi
0x1800bff63  jnb     short loc_1800BFFBC
0x1800bff65  mov     rax, [rdi+128h]
0x1800bff6c  mov     rcx, [r12+rbx*8]
0x1800bff70  lea     r8, [rax+rbx*8]
0x1800bff74  mov     rdx, [rcx]
0x1800bff77  mov     rax, [rdx]
0x1800bff7a  lea     rdx, IID_IDispatch
0x1800bff81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bff86  test    eax, eax
0x1800bff88  js      loc_1800C0022
0x1800bff8e  mov     rax, [rdi+130h]
0x1800bff95  lea     r8, [rdi+188h]; struct IUnknown *
0x1800bff9c  xor     r9d, r9d; int
0x1800bff9f  lea     rdx, IID_IPropertyNotifySink; struct _GUID *
0x1800bffa6  lea     rcx, [rax+rbx*4]
0x1800bffaa  mov     [rsp+78h+var_58], rcx; unsigned int *
0x1800bffaf  mov     rcx, [r12+rbx*8]; struct IUnknown *
0x1800bffb3  call    ?AfxConnectionAdvise@@YAHPEAUIUnknown@@AEBU_GUID@@0HPEAK@Z; AfxConnectionAdvise(IUnknown *,_GUID const &,IUnknown *,int,ulong *)
0x1800bffb8  add     ebx, ebp
0x1800bffba  jmp     short loc_1800BFF61
0x1800bffbc  mov     rcx, [rdi+40h]; hWnd
0x1800bffc0  mov     [rdi+13Ch], esi
0x1800bffc6  test    rcx, rcx
0x1800bffc9  jz      short loc_1800BFFE1
0x1800bffcb  call    cs:__imp_IsWindowVisible
0x1800bffd1  test    eax, eax
0x1800bffd3  jz      short loc_1800BFFE1
0x1800bffd5  mov     rcx, [rdi+40h]; hWndLock
0x1800bffd9  call    cs:__imp_LockWindowUpdate
0x1800bffdf  jmp     short loc_1800BFFE3
0x1800bffe1  xor     ebp, ebp
0x1800bffe3  mov     rax, [rdi]
0x1800bffe6  mov     rcx, rdi
0x1800bffe9  mov     rax, [rax+1B8h]
0x1800bfff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfff5  test    esi, esi
0x1800bfff7  jz      short loc_1800C0014
0x1800bfff9  cmp     qword ptr [rdi+40h], 0
0x1800bfffe  jz      short loc_1800C0014
0x1800c0000  xor     edx, edx; int
0x1800c0002  mov     rcx, rdi; this
0x1800c0005  call    ?UpdateData@CWnd@@QEAAHH@Z; CWnd::UpdateData(int)
0x1800c000a  xor     edx, edx; int
0x1800c000c  mov     rcx, rdi; this
0x1800c000f  call    ?SetModifiedFlag@COlePropertyPage@@QEAAXH@Z; COlePropertyPage::SetModifiedFlag(int)
0x1800c0014  test    ebp, ebp
0x1800c0016  jz      short loc_1800C0020
0x1800c0018  xor     ecx, ecx; hWndLock
0x1800c001a  call    cs:__imp_LockWindowUpdate
0x1800c0020  xor     eax, eax
0x1800c0022  mov     [r14+8], r13
0x1800c0026  add     rsp, 38h
0x1800c002a  pop     r15
0x1800c002c  pop     r14
0x1800c002e  pop     r13
0x1800c0030  pop     r12
0x1800c0032  pop     rdi
0x1800c0033  pop     rsi
0x1800c0034  pop     rbp
0x1800c0035  pop     rbx
0x1800c0036  retn
```
