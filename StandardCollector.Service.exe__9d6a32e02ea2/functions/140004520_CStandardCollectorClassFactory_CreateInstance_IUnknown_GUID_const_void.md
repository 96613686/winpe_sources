# CStandardCollectorClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140004520`
- end: `0x14000463b`
- name: `?CreateInstance@CStandardCollectorClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `283`
- prototype: `__int64 __fastcall(CStandardCollectorClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140004520`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140004601`
- `KERNEL32!LeaveCriticalSection` at `0x140004601`
- `KERNEL32!EnterCriticalSection` at `0x14000456f`
- `KERNEL32!EnterCriticalSection` at `0x14000456f`

## pseudocode

```c
__int64 __fastcall CStandardCollectorClassFactory::CreateInstance(
        CStandardCollectorClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  _QWORD *v9; // r14
  int v10; // edi
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v9 = (_QWORD *)((char *)this + 24);
  if ( !*((_QWORD *)this + 3) )
  {
    v11 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 *))(**((_QWORD **)this + 2) + 24LL))(
            *((_QWORD *)this + 2),
            0,
            &GUID_d2020dea_eb40_45d5_b420_b9fb623c4fd1,
            &v11);
    if ( v10 < 0
      || (v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD *))(*(_QWORD *)v11 + 24LL))(v11, L"#", v9),
          v10 < 0) )
    {
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      goto LABEL_11;
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v10 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v9)(*v9, a3, a4);
LABEL_11:
  LeaveCriticalSection(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140004520  push    rbx
0x140004522  push    rbp
0x140004523  push    rsi
0x140004524  push    rdi
0x140004525  push    r14
0x140004527  sub     rsp, 40h
0x14000452b  mov     rax, cs:__security_cookie
0x140004532  xor     rax, rsp
0x140004535  mov     [rsp+68h+var_30], rax
0x14000453a  mov     rsi, r9
0x14000453d  mov     rbp, r8
0x140004540  mov     rdi, rcx
0x140004543  test    r9, r9
0x140004546  jnz     short loc_140004552
0x140004548  mov     eax, 80004003h
0x14000454d  jmp     loc_140004609
0x140004552  mov     qword ptr [r9], 0
0x140004559  test    rdx, rdx
0x14000455c  jz      short loc_140004568
0x14000455e  mov     eax, 80040110h
0x140004563  jmp     loc_140004609
0x140004568  lea     rbx, [rcx+20h]
0x14000456c  mov     rcx, rbx; lpCriticalSection
0x14000456f  call    cs:__imp_EnterCriticalSection
0x140004575  lea     r14, [rdi+18h]
0x140004579  cmp     qword ptr [r14], 0
0x14000457d  jnz     short loc_1400045E7
0x14000457f  mov     [rsp+68h+var_38], 0
0x140004588  mov     rcx, [rdi+10h]
0x14000458c  mov     rax, [rcx]
0x14000458f  lea     r9, [rsp+68h+var_38]
0x140004594  lea     r8, _GUID_d2020dea_eb40_45d5_b420_b9fb623c4fd1
0x14000459b  xor     edx, edx
0x14000459d  mov     rax, [rax+18h]
0x1400045a1  call    cs:__guard_dispatch_icall_fptr
0x1400045a7  mov     edi, eax
0x1400045a9  test    eax, eax
0x1400045ab  js      short loc_140004621
0x1400045ad  mov     rcx, [rsp+68h+var_38]
0x1400045b2  mov     rax, [rcx]
0x1400045b5  mov     r8, r14
0x1400045b8  lea     rdx, asc_14001A2B0; "#"
0x1400045bf  mov     rax, [rax+18h]
0x1400045c3  call    cs:__guard_dispatch_icall_fptr
0x1400045c9  mov     edi, eax
0x1400045cb  test    eax, eax
0x1400045cd  js      short loc_140004621
0x1400045cf  mov     rcx, [rsp+68h+var_38]
0x1400045d4  test    rcx, rcx
0x1400045d7  jz      short loc_1400045E7
0x1400045d9  mov     rax, [rcx]
0x1400045dc  mov     rax, [rax+10h]
0x1400045e0  call    cs:__guard_dispatch_icall_fptr
0x1400045e6  nop
0x1400045e7  mov     rcx, [r14]
0x1400045ea  mov     rax, [rcx]
0x1400045ed  mov     r8, rsi
0x1400045f0  mov     rdx, rbp
0x1400045f3  mov     rax, [rax]
0x1400045f6  call    cs:__guard_dispatch_icall_fptr
0x1400045fc  mov     edi, eax
0x1400045fe  mov     rcx, rbx; lpCriticalSection
0x140004601  call    cs:__imp_LeaveCriticalSection
0x140004607  mov     eax, edi
0x140004609  mov     rcx, [rsp+68h+var_30]
0x14000460e  xor     rcx, rsp; StackCookie
0x140004611  call    __security_check_cookie
0x140004616  add     rsp, 40h
0x14000461a  pop     r14
0x14000461c  pop     rdi
0x14000461d  pop     rsi
0x14000461e  pop     rbp
0x14000461f  pop     rbx
0x140004620  retn
0x140004621  mov     rcx, [rsp+68h+var_38]
0x140004626  test    rcx, rcx
0x140004629  jz      short loc_140004639
0x14000462b  mov     rax, [rcx]
0x14000462e  mov     rax, [rax+10h]
0x140004632  call    cs:__guard_dispatch_icall_fptr
0x140004638  nop
0x140004639  jmp     short loc_1400045FE
```
