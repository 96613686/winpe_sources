# StandardCollectorHostClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140004750`
- end: `0x140004838`
- name: `?CreateInstance@StandardCollectorHostClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(StandardCollectorHostClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140004750`
- `0x140004838`
- `0x140013834`
- `0x14001473e`
- `0x140014c70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000481c`
- `KERNEL32!LeaveCriticalSection` at `0x14000481c`
- `KERNEL32!EnterCriticalSection` at `0x14000479d`
- `KERNEL32!EnterCriticalSection` at `0x14000479d`

## pseudocode

```c
__int64 __fastcall StandardCollectorHostClassFactory::CreateInstance(
        StandardCollectorHostClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  StandardCollectorHost *v9; // rsi
  __int64 v10; // rcx
  unsigned int v11; // edi
  void *v12; // [rsp+20h] [rbp-28h]
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+68h] [rbp+20h]

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v9 = (StandardCollectorHost *)*((_QWORD *)this + 2);
  if ( !v9 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v12 = operator new(0x98u);
      memset_0(v12, 0, 0x98u);
      v9 = StandardCollectorHost::StandardCollectorHost((StandardCollectorHost *)v12);
      v10 = *((_QWORD *)this + 2);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 2) = v9;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v11 = -2147024882;
        v8 = v13;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1400047F6);
        goto LABEL_11;
      }
    }
  }
  v11 = (**(__int64 (__fastcall ***)(StandardCollectorHost *, const struct _GUID *, void **))v9)(v9, a3, a4);
LABEL_11:
  LeaveCriticalSection(v8);
  return v11;
}

```

## disassembly

```asm
0x140004750  mov     [rsp+arg_0], rbx
0x140004755  mov     [rsp+arg_8], rsi
0x14000475a  push    rdi
0x14000475b  push    r14
0x14000475d  push    r15
0x14000475f  sub     rsp, 30h
0x140004763  mov     r14, r9
0x140004766  mov     r15, r8
0x140004769  mov     rdi, rcx
0x14000476c  test    r9, r9
0x14000476f  jnz     short loc_14000477B
0x140004771  mov     eax, 80004003h
0x140004776  jmp     loc_140004824
0x14000477b  mov     qword ptr [r9], 0
0x140004782  test    rdx, rdx
0x140004785  jz      short loc_140004791
0x140004787  mov     eax, 80040110h
0x14000478c  jmp     loc_140004824
0x140004791  lea     rbx, [rcx+18h]
0x140004795  mov     [rsp+48h+arg_18], rbx
0x14000479a  mov     rcx, rbx; lpCriticalSection
0x14000479d  call    cs:__imp_EnterCriticalSection
0x1400047a3  nop
0x1400047a4  mov     rsi, [rdi+10h]
0x1400047a8  test    rsi, rsi
0x1400047ab  jnz     short loc_140004802
0x1400047ad  mov     ecx, 98h; Size
0x1400047b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400047b7  mov     rsi, rax
0x1400047ba  mov     [rsp+48h+var_28], rax
0x1400047bf  xor     edx, edx; Val
0x1400047c1  mov     r8d, 98h; Size
0x1400047c7  mov     rcx, rax; void *
0x1400047ca  call    memset_0
0x1400047cf  mov     rcx, rsi; this
0x1400047d2  call    ??0StandardCollectorHost@@QEAA@XZ; StandardCollectorHost::StandardCollectorHost(void)
0x1400047d7  mov     rsi, rax
0x1400047da  mov     rcx, [rdi+10h]
0x1400047de  test    rcx, rcx
0x1400047e1  jz      short loc_1400047F0
0x1400047e3  mov     rax, [rcx]
0x1400047e6  mov     rax, [rax+10h]
0x1400047ea  call    cs:__guard_dispatch_icall_fptr
0x1400047f0  mov     [rdi+10h], rsi
0x1400047f4  jmp     short loc_140004802
0x1400047f6  mov     edi, 8007000Eh
0x1400047fb  mov     rbx, [rsp+48h+arg_18]
0x140004800  jmp     short loc_140004819
0x140004802  mov     rax, [rsi]
0x140004805  mov     r8, r14
0x140004808  mov     rdx, r15
0x14000480b  mov     rcx, rsi
0x14000480e  mov     rax, [rax]
0x140004811  call    cs:__guard_dispatch_icall_fptr
0x140004817  mov     edi, eax
0x140004819  mov     rcx, rbx; lpCriticalSection
0x14000481c  call    cs:__imp_LeaveCriticalSection
0x140004822  mov     eax, edi
0x140004824  mov     rbx, [rsp+48h+arg_0]
0x140004829  mov     rsi, [rsp+48h+arg_8]
0x14000482e  add     rsp, 30h
0x140004832  pop     r15
0x140004834  pop     r14
0x140004836  pop     rdi
0x140004837  retn
```
