# AsyncWorkQueue::_CancelAllAsync(int)

- ea: `0x1800058c8`
- end: `0x180005a75`
- name: `?_CancelAllAsync@AsyncWorkQueue@@AEAAXH@Z`
- size: `429`
- prototype: `void __fastcall(AsyncWorkQueue *__hidden this, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005590`
- `0x1800055c0`
- `0x180005690`

## callees

- `0x180003da4`
- `0x1800058c8`
- `0x180005bd4`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005903`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005903`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000598b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000598b`

## pseudocode

```c
void __fastcall AsyncWorkQueue::_CancelAllAsync(AsyncWorkQueue *this, int a2)
{
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rcx
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rdx
  _QWORD *i; // rbx
  __int64 v11; // rsi
  __int64 v12; // rdi
  __int64 v13[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v14; // [rsp+30h] [rbp-38h] BYREF
  _QWORD *v15; // [rsp+38h] [rbp-30h]
  __int64 v16; // [rsp+40h] [rbp-28h]
  __int64 v17; // [rsp+48h] [rbp-20h] BYREF

  v14 = &v14;
  v15 = &v14;
  v16 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
    *((_DWORD *)this + 23) = 1;
  v4 = (_QWORD *)*((_QWORD *)this + 8);
  *(_QWORD *)(*((_QWORD *)this + 7) + 8LL) = &v14;
  *v4 = &v14;
  v5 = v15;
  v14[1] = (char *)this + 56;
  *v5 = (char *)this + 56;
  v6 = v14;
  v7 = v15;
  v14 = (_QWORD *)*((_QWORD *)this + 7);
  v15 = (_QWORD *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 7) = v6;
  *((_QWORD *)this + 8) = v7;
  v8 = v16;
  v16 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = v8;
  v9 = (_QWORD *)*((_QWORD *)this + 10);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 32LL))(*v9, v9[1]);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  for ( i = v14; i != &v14; i = (_QWORD *)*i )
  {
    v11 = i[2];
    v13[0] = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v12 = i[3];
    v13[1] = v12;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    v17 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v11)(
           v11,
           &GUID_16f7789f_46bb_4124_aba3_266a56d464c2,
           &v17) >= 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 24LL))(v17, v12);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(v13);
  }
  utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::clear(&v14);
  utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::clear(&v14);
}

```

## disassembly

```asm
0x1800058c8  push    rbp
0x1800058ca  push    rbx
0x1800058cb  push    rsi
0x1800058cc  push    rdi
0x1800058cd  mov     rbp, rsp
0x1800058d0  sub     rsp, 68h
0x1800058d4  mov     rax, cs:__security_cookie
0x1800058db  xor     rax, rsp
0x1800058de  mov     [rbp+var_18], rax
0x1800058e2  mov     ebx, edx
0x1800058e4  mov     rdi, rcx
0x1800058e7  lea     rax, [rbp+var_38]
0x1800058eb  mov     [rbp+var_38], rax
0x1800058ef  lea     rax, [rbp+var_38]
0x1800058f3  mov     [rbp+var_30], rax
0x1800058f7  mov     [rbp+var_28], 0
0x1800058ff  add     rcx, 10h; lpCriticalSection
0x180005903  call    cs:__imp_EnterCriticalSection
0x180005909  test    ebx, ebx
0x18000590b  jz      short loc_180005914
0x18000590d  mov     dword ptr [rdi+5Ch], 1
0x180005914  lea     r8, [rdi+38h]
0x180005918  mov     rcx, [r8+8]
0x18000591c  mov     rax, [r8]
0x18000591f  lea     rdx, [rbp+var_38]
0x180005923  mov     [rax+8], rdx
0x180005927  lea     rax, [rbp+var_38]
0x18000592b  mov     [rcx], rax
0x18000592e  mov     rcx, [rbp+var_30]
0x180005932  mov     rax, [rbp+var_38]
0x180005936  mov     [rax+8], r8
0x18000593a  mov     [rcx], r8
0x18000593d  mov     rcx, [rbp+var_38]
0x180005941  mov     rdx, [rbp+var_30]
0x180005945  mov     rax, [r8]
0x180005948  mov     [rbp+var_38], rax
0x18000594c  mov     rax, [r8+8]
0x180005950  mov     [rbp+var_30], rax
0x180005954  mov     [r8], rcx
0x180005957  mov     [r8+8], rdx
0x18000595b  mov     rcx, [rbp+var_28]
0x18000595f  mov     rax, [r8+10h]
0x180005963  mov     [rbp+var_28], rax
0x180005967  mov     [r8+10h], rcx
0x18000596b  mov     rdx, [rdi+50h]
0x18000596f  test    rdx, rdx
0x180005972  jz      short loc_180005987
0x180005974  mov     rcx, [rdx]
0x180005977  mov     rax, [rcx]
0x18000597a  mov     rdx, [rdx+8]
0x18000597e  mov     rax, [rax+20h]
0x180005982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005987  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000598b  call    cs:__imp_LeaveCriticalSection
0x180005991  mov     rbx, [rbp+var_38]
0x180005995  lea     rax, [rbp+var_38]
0x180005999  cmp     rbx, rax
0x18000599c  jz      loc_180005A4E
0x1800059a2  mov     rsi, [rbx+10h]
0x1800059a6  mov     [rbp+var_48], rsi
0x1800059aa  test    rsi, rsi
0x1800059ad  jz      short loc_1800059BE
0x1800059af  mov     rax, [rsi]
0x1800059b2  mov     rcx, rsi
0x1800059b5  mov     rax, [rax+8]
0x1800059b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059be  mov     rdi, [rbx+18h]
0x1800059c2  mov     [rbp+var_40], rdi
0x1800059c6  test    rdi, rdi
0x1800059c9  jz      short loc_1800059DA
0x1800059cb  mov     rax, [rdi]
0x1800059ce  mov     rcx, rdi
0x1800059d1  mov     rax, [rax+8]
0x1800059d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059da  mov     [rbp+var_20], 0
0x1800059e2  mov     rax, [rsi]
0x1800059e5  lea     r8, [rbp+var_20]
0x1800059e9  lea     rdx, _GUID_16f7789f_46bb_4124_aba3_266a56d464c2
0x1800059f0  mov     rcx, rsi
0x1800059f3  mov     rax, [rax]
0x1800059f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059fb  test    eax, eax
0x1800059fd  js      short loc_180005A12
0x1800059ff  mov     rcx, [rbp+var_20]
0x180005a03  mov     rax, [rcx]
0x180005a06  mov     rdx, rdi
0x180005a09  mov     rax, [rax+18h]
0x180005a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a12  mov     rcx, [rbp+var_20]
0x180005a16  test    rcx, rcx
0x180005a19  jz      short loc_180005A27
0x180005a1b  mov     rax, [rcx]
0x180005a1e  mov     rax, [rax+10h]
0x180005a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a27  test    rdi, rdi
0x180005a2a  jz      short loc_180005A3C
0x180005a2c  mov     rax, [rdi]
0x180005a2f  mov     rcx, rdi
0x180005a32  mov     rax, [rax+10h]
0x180005a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a3b  nop
0x180005a3c  lea     rcx, [rbp+var_48]
0x180005a40  call    ??1?$CComPtrBase@UIAsyncCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(void)
0x180005a45  nop
0x180005a46  mov     rbx, [rbx]
0x180005a49  jmp     loc_180005995
0x180005a4e  lea     rcx, [rbp+var_38]
0x180005a52  call    ?clear@?$list@UAsyncWorkItem@AsyncWorkQueue@@V?$allocator@UAsyncWorkItem@AsyncWorkQueue@@@utl@@@utl@@QEAAXXZ; utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::clear(void)
0x180005a57  lea     rcx, [rbp+var_38]
0x180005a5b  call    ?clear@?$list@UAsyncWorkItem@AsyncWorkQueue@@V?$allocator@UAsyncWorkItem@AsyncWorkQueue@@@utl@@@utl@@QEAAXXZ; utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::clear(void)
0x180005a60  mov     rcx, [rbp+var_18]
0x180005a64  xor     rcx, rsp; StackCookie
0x180005a67  call    __security_check_cookie
0x180005a6c  add     rsp, 68h
0x180005a70  pop     rdi
0x180005a71  pop     rsi
0x180005a72  pop     rbx
0x180005a73  pop     rbp
0x180005a74  retn
```
