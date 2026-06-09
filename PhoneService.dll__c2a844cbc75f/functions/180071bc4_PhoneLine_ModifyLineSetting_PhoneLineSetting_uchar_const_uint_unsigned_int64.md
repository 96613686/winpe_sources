# PhoneLine::ModifyLineSetting(PhoneLineSetting,uchar const *,uint,unsigned __int64)

- ea: `0x180071bc4`
- end: `0x180071f99`
- name: `?ModifyLineSetting@PhoneLine@@QEAAJW4PhoneLineSetting@@PEBEI_K@Z`
- size: `981`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c620`

## callees

- `0x180006e94`
- `0x180070030`
- `0x180071ba8`
- `0x180071bc4`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071d2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071de7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071ec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071f5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071d2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071de7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071ec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071f5a`
- `PhoneUtil!RemoveMetadataFromNumber` at `0x180071cba`
- `PhoneUtil!RemoveMetadataFromNumber` at `0x180071cba`
- `PhoneUtil!IsNumberDialable` at `0x180071cf5`
- `PhoneUtil!IsNumberDialable` at `0x180071cf5`

## string_xrefs

- `0x180071bfb`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180071c3c`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180071cd3`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180071d11`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180071db2`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180071dfd`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180071e95`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180071f29`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`

## pseudocode

```c
__int64 __fastcall PhoneLine::ModifyLineSetting(__int64 a1, int a2, unsigned int *a3, unsigned int a4, __int64 a5)
{
  int v9; // eax
  BackTraceCollection *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rbx
  __int64 v13; // r9
  int v14; // eax
  BackTraceCollection *v15; // rcx
  unsigned int v16; // edi
  BackTraceCollection *v17; // rcx
  int v18; // eax
  BackTraceCollection *v19; // rcx
  __int64 v20; // r9
  int v21; // eax
  BackTraceCollection *v22; // rcx
  __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-18h] BYREF

  if ( !a4 )
  {
    Log_HREvent_19(2147500037LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1504);
    return 2147500037LL;
  }
  v23 = 0;
  v9 = WrappedComPtrBase<IPhoneLine,SupportsShutdown,utl::recursive_mutex>::Get(a1 + 32, &v23);
  v11 = v9;
  if ( v9 < 0 )
  {
    BackTraceCollection::Capture(v10, v9);
    Log_HREvent_19(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1507);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    return v11;
  }
  v12 = v23;
  hMem = 0;
  switch ( a2 )
  {
    case 2:
      if ( a4 < 4 )
      {
        v13 = 1515;
        goto LABEL_33;
      }
      v23 = 0;
      if ( !v12
        || ((**(void (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
              v12,
              &GUID_94b6a9fd_137e_4465_872e_6687328ecbe8,
              &v23),
            !v23) )
      {
        Log_HREvent_19(2147500034LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1517);
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        if ( hMem )
          LocalFree(hMem);
        if ( !v12 )
          return 2147500034LL;
        goto LABEL_60;
      }
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v23 + 24LL))(v23, *a3, a5);
      v16 = v21;
      if ( v21 < 0 )
      {
        BackTraceCollection::Capture(v22, v21);
        v20 = 1518;
LABEL_41:
        Log_HREvent_19(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", v20);
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
LABEL_43:
        if ( hMem )
          LocalFree(hMem);
        if ( !v12 )
          return v16;
        goto LABEL_46;
      }
LABEL_48:
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      break;
    case 4:
      if ( a4 < 0x88 )
      {
        v13 = 1524;
LABEL_33:
        Log_HREvent_19(2147500037LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", v13);
        if ( hMem )
          LocalFree(hMem);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return 2147500037LL;
      }
      v14 = RemoveMetadataFromNumber(a3 + 2, &hMem);
      v16 = v14;
      if ( v14 < 0 )
      {
        BackTraceCollection::Capture(v15, v14);
        Log_HREvent_19(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1528);
        goto LABEL_43;
      }
      if ( *(_WORD *)hMem && !(unsigned int)IsNumberDialable() )
      {
        v16 = -2147024809;
        BackTraceCollection::Capture(v17, -2147024809);
        Log_HREvent_19(2147942487LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1533);
        if ( hMem )
          LocalFree(hMem);
        if ( !v12 )
          return v16;
LABEL_46:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return v16;
      }
      v23 = 0;
      if ( !v12
        || ((**(void (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
              v12,
              &GUID_94b6a9fd_137e_4465_872e_6687328ecbe8,
              &v23),
            !v23) )
      {
        Log_HREvent_19(2147500034LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1537);
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        if ( hMem )
          LocalFree(hMem);
LABEL_11:
        if ( !v12 )
          return 2147500034LL;
LABEL_60:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return 2147500034LL;
      }
      v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, HLOCAL, _QWORD, __int64))(*(_QWORD *)v23 + 32LL))(
              v23,
              *a3,
              hMem,
              a3[1],
              a5);
      v16 = v18;
      if ( v18 < 0 )
      {
        BackTraceCollection::Capture(v19, v18);
        v20 = 1538;
        goto LABEL_41;
      }
      goto LABEL_48;
    case 8:
      goto LABEL_11;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x180071bc4  mov     [rsp-28h+arg_8], rbx
0x180071bc9  push    rbp
0x180071bca  push    rsi
0x180071bcb  push    rdi
0x180071bcc  push    r14
0x180071bce  push    r15
0x180071bd0  mov     rbp, rsp
0x180071bd3  sub     rsp, 50h
0x180071bd7  mov     rax, cs:__security_cookie
0x180071bde  xor     rax, rsp
0x180071be1  mov     [rbp+var_10], rax
0x180071be5  xor     r15d, r15d
0x180071be8  mov     esi, r9d
0x180071beb  mov     r14, r8
0x180071bee  mov     edi, edx
0x180071bf0  test    r9d, r9d
0x180071bf3  jnz     short loc_180071C18
0x180071bf5  mov     r9d, 5E0h
0x180071bfb  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180071c02  xor     edx, edx
0x180071c04  mov     ecx, 80004005h
0x180071c09  call    Log_HREvent_19
0x180071c0e  mov     eax, 80004005h
0x180071c13  jmp     loc_180071F79
0x180071c18  add     rcx, 20h ; ' '
0x180071c1c  mov     [rbp+var_20], r15
0x180071c20  lea     rdx, [rbp+var_20]
0x180071c24  call    ?Get@?$WrappedComPtrBase@UIPhoneLine@@VSupportsShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneLine@@@Z; WrappedComPtrBase<IPhoneLine,SupportsShutdown,utl::recursive_mutex>::Get(IPhoneLine * *)
0x180071c29  mov     ebx, eax
0x180071c2b  test    eax, eax
0x180071c2d  jns     short loc_180071C6B
0x180071c2f  mov     edx, eax; int
0x180071c31  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180071c36  mov     r9d, 5E3h
0x180071c3c  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180071c43  mov     edx, 1
0x180071c48  mov     ecx, ebx
0x180071c4a  call    Log_HREvent_19
0x180071c4f  mov     rcx, [rbp+var_20]
0x180071c53  test    rcx, rcx
0x180071c56  jz      short loc_180071C64
0x180071c58  mov     rax, [rcx]
0x180071c5b  mov     rax, [rax+10h]
0x180071c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c64  mov     eax, ebx
0x180071c66  jmp     loc_180071F79
0x180071c6b  mov     rbx, [rbp+var_20]
0x180071c6f  mov     [rbp+hMem], r15
0x180071c73  cmp     edi, 2
0x180071c76  jz      loc_180071DF2
0x180071c7c  cmp     edi, 4
0x180071c7f  jz      short loc_180071C9F
0x180071c81  cmp     edi, 8
0x180071c84  jnz     loc_180071EFC
0x180071c8a  test    rbx, rbx
0x180071c8d  jz      loc_180071F74
0x180071c93  mov     rax, [rbx]
0x180071c96  mov     rax, [rax+10h]
0x180071c9a  jmp     loc_180071F6C
0x180071c9f  cmp     esi, 88h
0x180071ca5  jnb     short loc_180071CB2
0x180071ca7  mov     r9d, 5F4h
0x180071cad  jmp     loc_180071DFD
0x180071cb2  lea     rcx, [r14+8]
0x180071cb6  lea     rdx, [rbp+hMem]
0x180071cba  call    cs:__imp_RemoveMetadataFromNumber
0x180071cc0  mov     edi, eax
0x180071cc2  test    eax, eax
0x180071cc4  jns     short loc_180071CEB
0x180071cc6  mov     edx, eax; int
0x180071cc8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180071ccd  mov     r9d, 5F8h
0x180071cd3  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180071cda  mov     edx, 1
0x180071cdf  mov     ecx, edi
0x180071ce1  call    Log_HREvent_19
0x180071ce6  jmp     loc_180071EBD
0x180071ceb  mov     rcx, [rbp+hMem]
0x180071cef  cmp     [rcx], r15w
0x180071cf3  jz      short loc_180071D45
0x180071cf5  call    cs:__imp_IsNumberDialable
0x180071cfb  test    eax, eax
0x180071cfd  jnz     short loc_180071D45
0x180071cff  mov     edi, 80070057h
0x180071d04  mov     edx, edi; int
0x180071d06  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180071d0b  mov     r9d, 5FDh
0x180071d11  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180071d18  xor     edx, edx
0x180071d1a  mov     ecx, edi
0x180071d1c  call    Log_HREvent_19
0x180071d21  mov     rcx, [rbp+hMem]; hMem
0x180071d25  test    rcx, rcx
0x180071d28  jz      short loc_180071D30
0x180071d2a  call    cs:__imp_LocalFree
0x180071d30  test    rbx, rbx
0x180071d33  jz      loc_180071EE0
0x180071d39  mov     rcx, [rbx]
0x180071d3c  mov     rax, [rcx+10h]
0x180071d40  jmp     loc_180071ED8
0x180071d45  mov     [rbp+var_20], r15
0x180071d49  test    rbx, rbx
0x180071d4c  jz      short loc_180071DAC
0x180071d4e  mov     rax, [rbx]
0x180071d51  lea     r8, [rbp+var_20]
0x180071d55  lea     rdx, _GUID_94b6a9fd_137e_4465_872e_6687328ecbe8
0x180071d5c  mov     rcx, rbx
0x180071d5f  mov     rax, [rax]
0x180071d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d67  mov     rcx, [rbp+var_20]
0x180071d6b  test    rcx, rcx
0x180071d6e  jz      short loc_180071DAC
0x180071d70  mov     r9, [rbp+arg_20]
0x180071d74  mov     rax, [rcx]
0x180071d77  mov     r8, [rbp+hMem]
0x180071d7b  mov     edx, [r14]
0x180071d7e  mov     [rsp+50h+var_30], r9
0x180071d83  mov     rax, [rax+20h]
0x180071d87  mov     r9d, [r14+4]
0x180071d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d90  mov     edi, eax
0x180071d92  test    eax, eax
0x180071d94  jns     loc_180071EE7
0x180071d9a  mov     edx, eax; int
0x180071d9c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180071da1  mov     r9d, 602h
0x180071da7  jmp     loc_180071E95
0x180071dac  mov     r9d, 601h
0x180071db2  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180071db9  xor     edx, edx
0x180071dbb  mov     ecx, 80004002h
0x180071dc0  call    Log_HREvent_19
0x180071dc5  mov     rcx, [rbp+var_20]
0x180071dc9  test    rcx, rcx
0x180071dcc  jz      short loc_180071DDA
0x180071dce  mov     rax, [rcx]
0x180071dd1  mov     rax, [rax+10h]
0x180071dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071dda  mov     rcx, [rbp+hMem]; hMem
0x180071dde  test    rcx, rcx
0x180071de1  jz      loc_180071C8A
0x180071de7  call    cs:__imp_LocalFree
0x180071ded  jmp     loc_180071C8A
0x180071df2  cmp     esi, 4
0x180071df5  jnb     short loc_180071E3C
0x180071df7  mov     r9d, 5EBh
0x180071dfd  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180071e04  xor     edx, edx
0x180071e06  mov     ecx, 80004005h
0x180071e0b  call    Log_HREvent_19
0x180071e10  mov     rcx, [rbp+hMem]; hMem
0x180071e14  test    rcx, rcx
0x180071e17  jz      short loc_180071E1F
0x180071e19  call    cs:__imp_LocalFree
0x180071e1f  test    rbx, rbx
0x180071e22  jz      loc_180071C0E
0x180071e28  mov     rax, [rbx]
0x180071e2b  mov     rcx, rbx
0x180071e2e  mov     rax, [rax+10h]
0x180071e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e37  jmp     loc_180071C0E
0x180071e3c  mov     [rbp+var_20], r15
0x180071e40  test    rbx, rbx
0x180071e43  jz      loc_180071F23
0x180071e49  mov     rax, [rbx]
0x180071e4c  lea     r8, [rbp+var_20]
0x180071e50  lea     rdx, _GUID_94b6a9fd_137e_4465_872e_6687328ecbe8
0x180071e57  mov     rcx, rbx
0x180071e5a  mov     rax, [rax]
0x180071e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e62  mov     rcx, [rbp+var_20]
0x180071e66  test    rcx, rcx
0x180071e69  jz      loc_180071F23
0x180071e6f  mov     rax, [rcx]
0x180071e72  mov     r8, [rbp+arg_20]
0x180071e76  mov     edx, [r14]
0x180071e79  mov     rax, [rax+18h]
0x180071e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e82  mov     edi, eax
0x180071e84  test    eax, eax
0x180071e86  jns     short loc_180071EE7
0x180071e88  mov     edx, eax; int
0x180071e8a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180071e8f  mov     r9d, 5EEh
0x180071e95  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180071e9c  mov     edx, 1
0x180071ea1  mov     ecx, edi
0x180071ea3  call    Log_HREvent_19
0x180071ea8  mov     rcx, [rbp+var_20]
0x180071eac  test    rcx, rcx
0x180071eaf  jz      short loc_180071EBD
0x180071eb1  mov     rax, [rcx]
0x180071eb4  mov     rax, [rax+10h]
0x180071eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ebd  mov     rcx, [rbp+hMem]; hMem
0x180071ec1  test    rcx, rcx
0x180071ec4  jz      short loc_180071ECC
0x180071ec6  call    cs:__imp_LocalFree
0x180071ecc  test    rbx, rbx
0x180071ecf  jz      short loc_180071EE0
0x180071ed1  mov     rax, [rbx]
0x180071ed4  mov     rax, [rax+10h]
0x180071ed8  mov     rcx, rbx
0x180071edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ee0  mov     eax, edi
0x180071ee2  jmp     loc_180071F79
0x180071ee7  mov     rcx, [rbp+var_20]
0x180071eeb  test    rcx, rcx
0x180071eee  jz      short loc_180071EFC
0x180071ef0  mov     rax, [rcx]
0x180071ef3  mov     rax, [rax+10h]
0x180071ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071efc  mov     rcx, [rbp+hMem]; hMem
0x180071f00  test    rcx, rcx
0x180071f03  jz      short loc_180071F0B
0x180071f05  call    cs:__imp_LocalFree
0x180071f0b  test    rbx, rbx
0x180071f0e  jz      short loc_180071F1F
0x180071f10  mov     rax, [rbx]
0x180071f13  mov     rcx, rbx
0x180071f16  mov     rax, [rax+10h]
0x180071f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f1f  xor     eax, eax
0x180071f21  jmp     short loc_180071F79
0x180071f23  mov     r9d, 5EDh
0x180071f29  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180071f30  xor     edx, edx
0x180071f32  mov     ecx, 80004002h
0x180071f37  call    Log_HREvent_19
0x180071f3c  mov     rcx, [rbp+var_20]
0x180071f40  test    rcx, rcx
0x180071f43  jz      short loc_180071F51
0x180071f45  mov     rax, [rcx]
0x180071f48  mov     rax, [rax+10h]
0x180071f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f51  mov     rcx, [rbp+hMem]; hMem
0x180071f55  test    rcx, rcx
0x180071f58  jz      short loc_180071F60
0x180071f5a  call    cs:__imp_LocalFree
0x180071f60  test    rbx, rbx
0x180071f63  jz      short loc_180071F74
0x180071f65  mov     rcx, [rbx]
0x180071f68  mov     rax, [rcx+10h]
0x180071f6c  mov     rcx, rbx
0x180071f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f74  mov     eax, 80004002h
0x180071f79  mov     rcx, [rbp+var_10]
0x180071f7d  xor     rcx, rsp; StackCookie
0x180071f80  call    __security_check_cookie
0x180071f85  mov     rbx, [rsp+50h+arg_8]
0x180071f8d  add     rsp, 50h
0x180071f91  pop     r15
0x180071f93  pop     r14
0x180071f95  pop     rdi
0x180071f96  pop     rsi
0x180071f97  pop     rbp
0x180071f98  retn
```
