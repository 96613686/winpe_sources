# FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)

- ea: `0x140079afc`
- end: `0x140079c40`
- name: `?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(void *, PEX_RUNDOWN_REF_CACHE_AWARE RunRefCacheAware)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f374`
- `0x140036180`
- `0x140046510`
- `0x1400480c4`
- `0x14004c74c`
- `0x14004e944`
- `0x140052008`
- `0x140053914`
- `0x140055468`

## callees

- `0x140005574`
- `0x140006908`
- `0x140079afc`
- `0x140079df4`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140079b2e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140079b2e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140079b3d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140079b3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079bf1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079bf1`

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
0x140079afc  push    rbp
0x140079afe  push    rbx
0x140079aff  push    rsi
0x140079b00  push    rdi
0x140079b01  push    r14
0x140079b03  lea     rbp, [rsp-37h]
0x140079b08  sub     rsp, 0C0h
0x140079b0f  mov     rax, cs:__security_cookie
0x140079b16  xor     rax, rsp
0x140079b19  mov     [rbp+57h+var_30], rax
0x140079b1d  mov     rdi, r9
0x140079b20  mov     sil, r8b
0x140079b23  mov     r14, rdx
0x140079b26  mov     rbx, rcx
0x140079b29  test    r8b, r8b
0x140079b2c  jz      short loc_140079B3A
0x140079b2e  call    cs:__imp_KeEnterCriticalRegion
0x140079b35  nop     dword ptr [rax+rax+00h]
0x140079b3a  mov     rcx, r14; RunRefCacheAware
0x140079b3d  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140079b44  nop     dword ptr [rax+rax+00h]
0x140079b49  test    al, al
0x140079b4b  jz      loc_140079BEC
0x140079b51  xor     edx, edx; Val
0x140079b53  lea     rcx, [rbp+57h+var_AF]; void *
0x140079b57  lea     r8d, [rdx+7Fh]; Size
0x140079b5b  call    memset
0x140079b60  mov     rdx, rdi
0x140079b63  mov     [rbp+57h+var_B8], r14
0x140079b67  lea     rcx, [rbp+57h+var_A8]
0x140079b6b  mov     [rbp+57h+var_B0], sil
0x140079b6f  call    ??4?$function@$$A6AX_N@Z@wistd@@QEAAAEAV01@AEBV01@@Z; wistd::function<void (bool)>::operator=(wistd::function<void (bool)> const &)
0x140079b74  mov     rcx, [rbp+57h+var_38]
0x140079b78  test    rcx, rcx
0x140079b7b  jz      short loc_140079B91
0x140079b7d  mov     [rbp+57h+var_C0], 1
0x140079b81  lea     rdx, [rbp+57h+var_C0]
0x140079b85  mov     rax, [rcx]
0x140079b88  mov     rax, [rax+20h]
0x140079b8c  call    _guard_dispatch_icall
0x140079b91  mov     rax, [rbp+57h+var_B8]
0x140079b95  lea     rcx, [rbx+10h]
0x140079b99  mov     [rbx], rax
0x140079b9c  lea     rdx, [rbp+57h+var_A8]
0x140079ba0  mov     al, [rbp+57h+var_B0]
0x140079ba3  mov     [rbx+8], al
0x140079ba6  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x140079bab  xor     edx, edx; Val
0x140079bad  lea     rcx, [rbp+57h+var_B8]; void *
0x140079bb1  mov     r8d, 88h; Size
0x140079bb7  call    memset
0x140079bbc  lea     rcx, [rbp+57h+var_B8]; this
0x140079bc0  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140079bc5  mov     rcx, [rbp+57h+var_38]
0x140079bc9  test    rcx, rcx
0x140079bcc  jz      short loc_140079BDA
0x140079bce  mov     rax, [rcx]
0x140079bd1  mov     rax, [rax+18h]
0x140079bd5  call    _guard_dispatch_icall
0x140079bda  mov     rcx, [rdi+70h]
0x140079bde  test    rcx, rcx
0x140079be1  jz      short loc_140079C22
0x140079be3  mov     rax, [rcx]
0x140079be6  mov     rax, [rax+18h]
0x140079bea  jmp     short loc_140079C1D
0x140079bec  test    sil, sil
0x140079bef  jz      short loc_140079BFD
0x140079bf1  call    cs:__imp_KeLeaveCriticalRegion
0x140079bf8  nop     dword ptr [rax+rax+00h]
0x140079bfd  xor     edx, edx; Val
0x140079bff  mov     r8d, 88h; Size
0x140079c05  mov     rcx, rbx; void *
0x140079c08  call    memset
0x140079c0d  mov     rcx, [rdi+70h]
0x140079c11  test    rcx, rcx
0x140079c14  jz      short loc_140079C22
0x140079c16  mov     rdx, [rcx]
0x140079c19  mov     rax, [rdx+18h]
0x140079c1d  call    _guard_dispatch_icall
0x140079c22  mov     rax, rbx
0x140079c25  mov     rcx, [rbp+57h+var_30]
0x140079c29  xor     rcx, rsp; StackCookie
0x140079c2c  call    __security_check_cookie
0x140079c31  add     rsp, 0C0h
0x140079c38  pop     r14
0x140079c3a  pop     rdi
0x140079c3b  pop     rsi
0x140079c3c  pop     rbx
0x140079c3d  pop     rbp
0x140079c3e  retn
```
