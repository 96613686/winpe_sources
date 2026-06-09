# FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)

- ea: `0x140079e1c`
- end: `0x140079f60`
- name: `?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(void *, PEX_RUNDOWN_REF_CACHE_AWARE RunRefCacheAware)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f3a0`
- `0x1400362c0`
- `0x140046690`
- `0x140048244`
- `0x14004c8cc`
- `0x14004eac4`
- `0x140052188`
- `0x140053a94`
- `0x1400555e8`

## callees

- `0x140005574`
- `0x140006908`
- `0x140079e1c`
- `0x14007a114`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140079e4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140079e4e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140079e5d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140079e5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079f11`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079f11`

## pseudocode

```c
char *__fastcall FsFltWil::AcquireRundownReference(
        char *a1,
        PEX_RUNDOWN_REF_CACHE_AWARE RunRefCacheAware,
        char a3,
        __int64 a4)
{
  struct FsFltWil::Details::RundownRefCacheAware *v8; // rdx
  __int64 v9; // rcx
  void (*v10)(void); // rax
  __int64 v11; // rcx
  char v13[8]; // [rsp+20h] [rbp-69h] BYREF
  _QWORD v14[17]; // [rsp+28h] [rbp-61h] BYREF

  if ( a3 )
    KeEnterCriticalRegion();
  if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
  {
    memset((char *)&v14[1] + 1, 0, 0x7Fu);
    v14[0] = RunRefCacheAware;
    LOBYTE(v14[1]) = a3;
    wistd::function<void (bool)>::operator=(&v14[2], a4);
    if ( v14[16] )
    {
      v13[0] = 1;
      (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)v14[16] + 32LL))(v14[16], v13);
    }
    *(_QWORD *)a1 = v14[0];
    a1[8] = v14[1];
    wistd::function<void (bool)>::function<void (bool)>(a1 + 16, &v14[2]);
    memset(v14, 0, sizeof(v14));
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v14, v8);
    if ( v14[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[16] + 24LL))(v14[16]);
    v9 = *(_QWORD *)(a4 + 112);
    if ( v9 )
    {
      v10 = *(void (**)(void))(*(_QWORD *)v9 + 24LL);
LABEL_14:
      v10();
    }
  }
  else
  {
    if ( a3 )
      KeLeaveCriticalRegion();
    memset(a1, 0, 0x88u);
    v11 = *(_QWORD *)(a4 + 112);
    if ( v11 )
    {
      v10 = *(void (**)(void))(*(_QWORD *)v11 + 24LL);
      goto LABEL_14;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140079e1c  push    rbp
0x140079e1e  push    rbx
0x140079e1f  push    rsi
0x140079e20  push    rdi
0x140079e21  push    r14
0x140079e23  lea     rbp, [rsp-37h]
0x140079e28  sub     rsp, 0C0h
0x140079e2f  mov     rax, cs:__security_cookie
0x140079e36  xor     rax, rsp
0x140079e39  mov     [rbp+57h+var_30], rax
0x140079e3d  mov     rdi, r9
0x140079e40  mov     sil, r8b
0x140079e43  mov     r14, rdx
0x140079e46  mov     rbx, rcx
0x140079e49  test    r8b, r8b
0x140079e4c  jz      short loc_140079E5A
0x140079e4e  call    cs:__imp_KeEnterCriticalRegion
0x140079e55  nop     dword ptr [rax+rax+00h]
0x140079e5a  mov     rcx, r14; RunRefCacheAware
0x140079e5d  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140079e64  nop     dword ptr [rax+rax+00h]
0x140079e69  test    al, al
0x140079e6b  jz      loc_140079F0C
0x140079e71  xor     edx, edx; Val
0x140079e73  lea     rcx, [rbp+57h+var_AF]; void *
0x140079e77  lea     r8d, [rdx+7Fh]; Size
0x140079e7b  call    memset
0x140079e80  mov     rdx, rdi
0x140079e83  mov     [rbp+57h+var_B8], r14
0x140079e87  lea     rcx, [rbp+57h+var_A8]
0x140079e8b  mov     [rbp+57h+var_B0], sil
0x140079e8f  call    ??4?$function@$$A6AX_N@Z@wistd@@QEAAAEAV01@AEBV01@@Z; wistd::function<void (bool)>::operator=(wistd::function<void (bool)> const &)
0x140079e94  mov     rcx, [rbp+57h+var_38]
0x140079e98  test    rcx, rcx
0x140079e9b  jz      short loc_140079EB1
0x140079e9d  mov     [rbp+57h+var_C0], 1
0x140079ea1  lea     rdx, [rbp+57h+var_C0]
0x140079ea5  mov     rax, [rcx]
0x140079ea8  mov     rax, [rax+20h]
0x140079eac  call    _guard_dispatch_icall
0x140079eb1  mov     rax, [rbp+57h+var_B8]
0x140079eb5  lea     rcx, [rbx+10h]
0x140079eb9  mov     [rbx], rax
0x140079ebc  lea     rdx, [rbp+57h+var_A8]
0x140079ec0  mov     al, [rbp+57h+var_B0]
0x140079ec3  mov     [rbx+8], al
0x140079ec6  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x140079ecb  xor     edx, edx; Val
0x140079ecd  lea     rcx, [rbp+57h+var_B8]; void *
0x140079ed1  mov     r8d, 88h; Size
0x140079ed7  call    memset
0x140079edc  lea     rcx, [rbp+57h+var_B8]; this
0x140079ee0  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140079ee5  mov     rcx, [rbp+57h+var_38]
0x140079ee9  test    rcx, rcx
0x140079eec  jz      short loc_140079EFA
0x140079eee  mov     rax, [rcx]
0x140079ef1  mov     rax, [rax+18h]
0x140079ef5  call    _guard_dispatch_icall
0x140079efa  mov     rcx, [rdi+70h]
0x140079efe  test    rcx, rcx
0x140079f01  jz      short loc_140079F42
0x140079f03  mov     rax, [rcx]
0x140079f06  mov     rax, [rax+18h]
0x140079f0a  jmp     short loc_140079F3D
0x140079f0c  test    sil, sil
0x140079f0f  jz      short loc_140079F1D
0x140079f11  call    cs:__imp_KeLeaveCriticalRegion
0x140079f18  nop     dword ptr [rax+rax+00h]
0x140079f1d  xor     edx, edx; Val
0x140079f1f  mov     r8d, 88h; Size
0x140079f25  mov     rcx, rbx; void *
0x140079f28  call    memset
0x140079f2d  mov     rcx, [rdi+70h]
0x140079f31  test    rcx, rcx
0x140079f34  jz      short loc_140079F42
0x140079f36  mov     rdx, [rcx]
0x140079f39  mov     rax, [rdx+18h]
0x140079f3d  call    _guard_dispatch_icall
0x140079f42  mov     rax, rbx
0x140079f45  mov     rcx, [rbp+57h+var_30]
0x140079f49  xor     rcx, rsp; StackCookie
0x140079f4c  call    __security_check_cookie
0x140079f51  add     rsp, 0C0h
0x140079f58  pop     r14
0x140079f5a  pop     rdi
0x140079f5b  pop     rsi
0x140079f5c  pop     rbx
0x140079f5d  pop     rbp
0x140079f5e  retn
```
