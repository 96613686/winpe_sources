# BufferOverStream::EnsureAccessPrivateBuffer(IAccessPrivateBuffer * *)

- ea: `0x1801bdc10`
- end: `0x1801bddb4`
- name: `?EnsureAccessPrivateBuffer@BufferOverStream@@AEAAJPEAPEAUIAccessPrivateBuffer@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(BufferOverStream *this, struct IAccessPrivateBuffer **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801bd9e0`

## callees

- `0x18000f4b4`
- `0x1800122f4`
- `0x1800c8458`
- `0x18016b818`
- `0x1801bdc10`
- `0x1801bddbc`
- `0x180208010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x1801bdce7`
- `SHCORE!IStream_Reset` at `0x1801bdd23`
- `SHCORE!IStream_Reset` at `0x1801bdce7`
- `SHCORE!IStream_Reset` at `0x1801bdd23`
- `SHCORE!IStream_Copy` at `0x1801bdd09`
- `SHCORE!IStream_Copy` at `0x1801bdd09`
- `SHCORE!SHCreateMemStream` at `0x1801bdcab`
- `SHCORE!SHCreateMemStream` at `0x1801bdcab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801bdc33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801bdc33`

## string_xrefs

- `0x1801bdc80`: `onecoreuap\shell\cloudstore\common\src\streamconversion.cpp`
- `0x1801bdcc9`: `onecoreuap\shell\cloudstore\common\src\streamconversion.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BufferOverStream::EnsureAccessPrivateBuffer(
        BufferOverStream *this,
        struct IAccessPrivateBuffer **a2)
{
  char *v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  HRESULT v9; // eax
  HRESULT v10; // eax
  HRESULT v11; // eax
  int v12; // eax
  IStream *v13; // rbx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  IStream *cb; // [rsp+40h] [rbp+20h] BYREF
  IStream *pstmTo; // [rsp+48h] [rbp+28h] BYREF
  char *v19; // [rsp+50h] [rbp+30h] BYREF

  *a2 = 0;
  v4 = (char *)this + 80;
  AcquireSRWLockExclusive((PSRWLOCK)this + 10);
  v19 = v4;
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, struct IAccessPrivateBuffer **))this + 11))(
         *((_QWORD *)this + 11),
         &GUID_ed3071e9_f556_4c46_9294_6640c8c75281,
         a2) >= 0 )
    goto LABEL_18;
  LODWORD(cb) = 0;
  v5 = Get32BitStreamSize(*((struct IStream **)this + 11), (unsigned int *)&cb);
  v6 = v5;
  if ( v5 >= 0 )
  {
    pstmTo = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstmTo);
    pstmTo = SHCreateMemStream(0, 0);
    if ( !pstmTo )
    {
      v6 = -2147024882;
      v7 = 2147942414LL;
      v8 = 98;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\streamconversion.cpp",
        (const char *)v7,
        savedregs);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstmTo);
      goto LABEL_19;
    }
    v9 = IStream_Reset(*((IStream **)this + 11));
    v6 = v9;
    if ( v9 < 0 )
    {
      v7 = (unsigned int)v9;
      v8 = 99;
      goto LABEL_6;
    }
    v10 = IStream_Copy(*((IStream **)this + 11), pstmTo, (DWORD)cb);
    v6 = v10;
    if ( v10 < 0 )
    {
      v7 = (unsigned int)v10;
      v8 = 100;
      goto LABEL_6;
    }
    v11 = IStream_Reset(pstmTo);
    v6 = v11;
    if ( v11 < 0 )
    {
      v7 = (unsigned int)v11;
      v8 = 101;
      goto LABEL_6;
    }
    v12 = (**(__int64 (__fastcall ***)(IStream *, GUID *, struct IAccessPrivateBuffer **))pstmTo)(
            pstmTo,
            &GUID_ed3071e9_f556_4c46_9294_6640c8c75281,
            a2);
    v6 = v12;
    if ( v12 < 0 )
    {
      v7 = (unsigned int)v12;
      v8 = 102;
      goto LABEL_6;
    }
    v13 = pstmTo;
    if ( *((IStream **)this + 11) != pstmTo )
    {
      cb = pstmTo;
      Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::InternalAddRef(&cb);
      cb = (IStream *)*((_QWORD *)this + 11);
      *((_QWORD *)this + 11) = v13;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&cb);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstmTo);
LABEL_18:
    v6 = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5F,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\streamconversion.cpp",
    (const char *)(unsigned int)v5,
    savedregs);
LABEL_19:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v19);
  return v6;
}

```

## disassembly

```asm
0x1801bdc10  mov     [rsp-18h+arg_18], rbx
0x1801bdc15  push    rbp
0x1801bdc16  push    rsi
0x1801bdc17  push    rdi; int
0x1801bdc18  mov     rbp, rsp
0x1801bdc1b  sub     rsp, 20h
0x1801bdc1f  mov     rsi, rdx
0x1801bdc22  mov     rdi, rcx
0x1801bdc25  mov     qword ptr [rdx], 0
0x1801bdc2c  lea     rbx, [rcx+50h]
0x1801bdc30  mov     rcx, rbx; SRWLock
0x1801bdc33  call    cs:__imp_AcquireSRWLockExclusive
0x1801bdc39  mov     [rbp+arg_10], rbx
0x1801bdc3d  mov     rcx, [rdi+58h]
0x1801bdc41  mov     rax, [rcx]
0x1801bdc44  mov     r8, rsi
0x1801bdc47  lea     rdx, _GUID_ed3071e9_f556_4c46_9294_6640c8c75281
0x1801bdc4e  mov     rax, [rax]
0x1801bdc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bdc56  nop
0x1801bdc57  test    eax, eax
0x1801bdc59  jns     loc_1801BDD9A
0x1801bdc5f  mov     dword ptr [rbp+cb], 0
0x1801bdc66  lea     rdx, [rbp+cb]; unsigned int *
0x1801bdc6a  mov     rcx, [rdi+58h]; struct IStream *
0x1801bdc6e  call    ?Get32BitStreamSize@@YAJPEAUIStream@@PEAI@Z; Get32BitStreamSize(IStream *,uint *)
0x1801bdc73  mov     ebx, eax
0x1801bdc75  test    eax, eax
0x1801bdc77  jns     short loc_1801BDC96
0x1801bdc79  mov     rcx, [rbp+18h]; this
0x1801bdc7d  mov     r9d, eax; char *
0x1801bdc80  lea     r8, aOnecoreuapShel_97; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1801bdc87  mov     edx, 5Fh ; '_'; void *
0x1801bdc8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bdc91  jmp     loc_1801BDD9C
0x1801bdc96  mov     [rbp+pstmTo], 0
0x1801bdc9e  lea     rcx, [rbp+pstmTo]
0x1801bdca2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801bdca7  xor     edx, edx; cbInit
0x1801bdca9  xor     ecx, ecx; pInit
0x1801bdcab  call    cs:__imp_SHCreateMemStream
0x1801bdcb1  mov     [rbp+pstmTo], rax
0x1801bdcb5  test    rax, rax
0x1801bdcb8  jnz     short loc_1801BDCE3
0x1801bdcba  mov     ebx, 8007000Eh
0x1801bdcbf  mov     r9d, ebx; char *
0x1801bdcc2  lea     edx, [rax+62h]; void *
0x1801bdcc5  mov     rcx, [rbp+18h]; this
0x1801bdcc9  lea     r8, aOnecoreuapShel_97; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1801bdcd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bdcd5  lea     rcx, [rbp+pstmTo]
0x1801bdcd9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801bdcde  jmp     loc_1801BDD9C
0x1801bdce3  mov     rcx, [rdi+58h]; pstm
0x1801bdce7  call    cs:__imp_IStream_Reset
0x1801bdced  mov     ebx, eax
0x1801bdcef  test    eax, eax
0x1801bdcf1  jns     short loc_1801BDCFD
0x1801bdcf3  mov     r9d, eax
0x1801bdcf6  mov     edx, 63h ; 'c'
0x1801bdcfb  jmp     short loc_1801BDCC5
0x1801bdcfd  mov     r8d, dword ptr [rbp+cb]; cb
0x1801bdd01  mov     rdx, [rbp+pstmTo]; pstmTo
0x1801bdd05  mov     rcx, [rdi+58h]; pstmFrom
0x1801bdd09  call    cs:__imp_IStream_Copy
0x1801bdd0f  mov     ebx, eax
0x1801bdd11  test    eax, eax
0x1801bdd13  jns     short loc_1801BDD1F
0x1801bdd15  mov     r9d, eax
0x1801bdd18  mov     edx, 64h ; 'd'
0x1801bdd1d  jmp     short loc_1801BDCC5
0x1801bdd1f  mov     rcx, [rbp+pstmTo]; pstm
0x1801bdd23  call    cs:__imp_IStream_Reset
0x1801bdd29  mov     ebx, eax
0x1801bdd2b  test    eax, eax
0x1801bdd2d  jns     short loc_1801BDD39
0x1801bdd2f  mov     r9d, eax
0x1801bdd32  mov     edx, 65h ; 'e'
0x1801bdd37  jmp     short loc_1801BDCC5
0x1801bdd39  mov     rcx, [rbp+pstmTo]
0x1801bdd3d  mov     rax, [rcx]
0x1801bdd40  mov     r8, rsi
0x1801bdd43  lea     rdx, _GUID_ed3071e9_f556_4c46_9294_6640c8c75281
0x1801bdd4a  mov     rax, [rax]
0x1801bdd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bdd52  mov     ebx, eax
0x1801bdd54  test    eax, eax
0x1801bdd56  jns     short loc_1801BDD65
0x1801bdd58  mov     r9d, eax
0x1801bdd5b  mov     edx, 66h ; 'f'
0x1801bdd60  jmp     loc_1801BDCC5
0x1801bdd65  mov     rbx, [rbp+pstmTo]
0x1801bdd69  cmp     [rdi+58h], rbx
0x1801bdd6d  jz      short loc_1801BDD91
0x1801bdd6f  mov     [rbp+cb], rbx
0x1801bdd73  lea     rcx, [rbp+cb]
0x1801bdd77  call    ?InternalAddRef@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::InternalAddRef(void)
0x1801bdd7c  mov     rax, [rdi+58h]
0x1801bdd80  mov     [rbp+cb], rax
0x1801bdd84  mov     [rdi+58h], rbx
0x1801bdd88  lea     rcx, [rbp+cb]
0x1801bdd8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801bdd91  lea     rcx, [rbp+pstmTo]
0x1801bdd95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801bdd9a  xor     ebx, ebx
0x1801bdd9c  lea     rcx, [rbp+arg_10]
0x1801bdda0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1801bdda5  mov     eax, ebx
0x1801bdda7  mov     rbx, [rsp+20h+arg_18]
0x1801bddac  add     rsp, 20h
0x1801bddb0  pop     rdi
0x1801bddb1  pop     rsi
0x1801bddb2  pop     rbp
0x1801bddb3  retn
```
