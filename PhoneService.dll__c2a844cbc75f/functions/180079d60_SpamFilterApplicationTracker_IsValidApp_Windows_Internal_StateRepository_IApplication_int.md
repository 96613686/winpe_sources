# SpamFilterApplicationTracker::IsValidApp(Windows::Internal::StateRepository::IApplication *,int *)

- ea: `0x180079d60`
- end: `0x18007a00d`
- name: `?IsValidApp@SpamFilterApplicationTracker@@MEAAJPEAUIApplication@StateRepository@Internal@Windows@@PEAH@Z`
- size: `685`
- prototype: `int(SpamFilterApplicationTracker *__hidden this, struct Windows::Internal::StateRepository::IApplication *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x180013428`
- `0x180050970`
- `0x180050dcc`
- `0x180050e58`
- `0x180079d60`
- `0x18007a020`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079e21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079ea6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079e21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079ea6`

## string_xrefs

- `0x180079ddf`: `windows.communicationBlockingProvider`
- `0x180079db0`: `onecoreuap\net\phone\phoneservice\service\lib\spamfilterapplicationtracker.cpp`
- `0x180079e7f`: `onecoreuap\net\phone\phoneservice\service\lib\spamfilterapplicationtracker.cpp`

## pseudocode

```c
__int64 __fastcall SpamFilterApplicationTracker::IsValidApp(
        SpamFilterApplicationTracker *this,
        struct Windows::Internal::StateRepository::IApplication *a2,
        int *a3)
{
  int IsModernApp; // eax
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // r9
  int HasSpecificCategory; // eax
  BackTraceCollection *v11; // rcx
  __int64 v12; // rax
  void (__fastcall *v13)(struct Windows::Internal::StateRepository::IApplication *, HSTRING *); // rbx
  BackTraceCollection *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  char *v17; // rcx
  _DWORD *v18; // rax
  _DWORD *v19; // rcx
  BackTraceCollection *v20; // rcx
  _DWORD *v21; // rcx
  BackTraceCollection *v22; // rcx
  const WCHAR *StringRawBuffer; // rax
  int IsRegisteredByApp; // eax
  BackTraceCollection *v25; // rcx
  BackTraceCollection *v26; // rcx
  void *v27; // rcx
  int v28; // [rsp+30h] [rbp-30h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v30; // [rsp+48h] [rbp-18h]
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF

  *a3 = 0;
  v28 = 0;
  IsModernApp = ApplicationTracker::IsModernApp(a2, &v28);
  v7 = IsModernApp;
  if ( IsModernApp < 0 )
  {
    BackTraceCollection::Capture(v6, IsModernApp);
    v8 = 164;
LABEL_3:
    Log_HREvent_22(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\spamfilterapplicationtracker.cpp", v8);
    return v7;
  }
  if ( v28 )
  {
    v28 = 0;
    HasSpecificCategory = ApplicationTracker::HasSpecificCategory(a2, L"windows.communicationBlockingProvider", &v28);
    v7 = HasSpecificCategory;
    if ( HasSpecificCategory < 0 )
    {
      BackTraceCollection::Capture(v11, HasSpecificCategory);
      v8 = 171;
      goto LABEL_3;
    }
    if ( v28 )
    {
      v12 = *(_QWORD *)a2;
      string = 0;
      v13 = *(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplication *, HSTRING *))(v12 + 232);
      WindowsDeleteString(0);
      string = 0;
      v13(a2, &string);
      v28 = 58;
      v30 = -1;
      *(__m128i *)Block = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      if ( !(unsigned __int8)utl::vector<enum _SebiEventType,utl::allocator<enum _SebiEventType>>::_PushBackOne2<enum _SebiEventType>(
                               Block,
                               &v28) )
      {
        v7 = -2147024882;
        BackTraceCollection::Capture(v14, -2147024882);
        v15 = 181;
LABEL_11:
        v16 = 0;
        goto LABEL_12;
      }
      v17 = (char *)Block[1];
      v18 = (_DWORD *)v30;
      v28 = 61;
      if ( Block[1] == (void *)v30 )
      {
        if ( !(unsigned __int8)utl::vector<enum _SebiEventType,utl::allocator<enum _SebiEventType>>::_PushBackOne2<enum _SebiEventType>(
                                 Block,
                                 &v28) )
        {
          v7 = -2147024882;
          BackTraceCollection::Capture(v20, -2147024882);
          v15 = 182;
          goto LABEL_11;
        }
        v18 = (_DWORD *)v30;
        v19 = Block[1];
      }
      else
      {
        *(_DWORD *)Block[1] = 61;
        v19 = v17 + 4;
        Block[1] = v19;
      }
      v28 = 37;
      if ( v19 == v18 )
      {
        if ( !(unsigned __int8)utl::vector<enum _SebiEventType,utl::allocator<enum _SebiEventType>>::_PushBackOne2<enum _SebiEventType>(
                                 Block,
                                 &v28) )
        {
          v7 = -2147024882;
          BackTraceCollection::Capture(v22, -2147024882);
          v15 = 183;
          goto LABEL_11;
        }
        v18 = (_DWORD *)v30;
        v21 = Block[1];
      }
      else
      {
        *v19 = 37;
        v21 = v19 + 1;
        Block[1] = v21;
      }
      v28 = 57;
      if ( v21 == v18 )
      {
        if ( !(unsigned __int8)utl::vector<enum _SebiEventType,utl::allocator<enum _SebiEventType>>::_PushBackOne2<enum _SebiEventType>(
                                 Block,
                                 &v28) )
        {
          v7 = -2147024882;
          BackTraceCollection::Capture(v26, -2147024882);
          v15 = 184;
          goto LABEL_11;
        }
      }
      else
      {
        *v21 = 57;
        Block[1] = v21 + 1;
      }
      v28 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      IsRegisteredByApp = ApplicationTracker::IsRegisteredByApp(StringRawBuffer);
      v7 = IsRegisteredByApp;
      if ( IsRegisteredByApp >= 0 )
      {
        v27 = Block[0];
        if ( v28 )
          *a3 = 1;
        if ( v27 != (void *)-1LL )
          operator delete(v27);
        v7 = 0;
        goto LABEL_14;
      }
      BackTraceCollection::Capture(v25, IsRegisteredByApp);
      v15 = 187;
      v16 = 1;
LABEL_12:
      Log_HREvent_22(
        v7,
        v16,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\spamfilterapplicationtracker.cpp",
        v15);
      if ( Block[0] != (void *)-1LL )
        operator delete(Block[0]);
LABEL_14:
      WindowsDeleteString(string);
      return v7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180079d60  mov     [rsp-18h+arg_0], rbx
0x180079d65  push    rbp
0x180079d66  push    rsi
0x180079d67  push    rdi
0x180079d68  mov     rbp, rsp
0x180079d6b  sub     rsp, 60h
0x180079d6f  mov     rax, cs:__security_cookie
0x180079d76  xor     rax, rsp
0x180079d79  mov     [rbp+var_8], rax
0x180079d7d  mov     rdi, rdx
0x180079d80  mov     dword ptr [r8], 0
0x180079d87  mov     rcx, rdi; struct Windows::Internal::StateRepository::IApplication *
0x180079d8a  mov     [rbp+var_30], 0
0x180079d91  lea     rdx, [rbp+var_30]; int *
0x180079d95  mov     rsi, r8
0x180079d98  call    ?IsModernApp@ApplicationTracker@@KAJPEAUIApplication@StateRepository@Internal@Windows@@PEAH@Z; ApplicationTracker::IsModernApp(Windows::Internal::StateRepository::IApplication *,int *)
0x180079d9d  mov     ebx, eax
0x180079d9f  test    eax, eax
0x180079da1  jns     short loc_180079DCA
0x180079da3  mov     edx, eax; int
0x180079da5  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180079daa  mov     r9d, 0A4h
0x180079db0  lea     r8, aOnecoreuapNetP_19; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180079db7  mov     edx, 1
0x180079dbc  mov     ecx, ebx
0x180079dbe  call    Log_HREvent_22
0x180079dc3  mov     eax, ebx
0x180079dc5  jmp     loc_180079FF1
0x180079dca  cmp     [rbp+var_30], 0
0x180079dce  jz      loc_180079FEF
0x180079dd4  lea     r8, [rbp+var_30]; int *
0x180079dd8  mov     [rbp+var_30], 0
0x180079ddf  lea     rdx, aWindowsCommuni; "windows.communicationBlockingProvider"
0x180079de6  mov     rcx, rdi; struct Windows::Internal::StateRepository::IApplication *
0x180079de9  call    ?HasSpecificCategory@ApplicationTracker@@KAJPEAUIApplication@StateRepository@Internal@Windows@@PEBGPEAH@Z; ApplicationTracker::HasSpecificCategory(Windows::Internal::StateRepository::IApplication *,ushort const *,int *)
0x180079dee  mov     ebx, eax
0x180079df0  test    eax, eax
0x180079df2  jns     short loc_180079E03
0x180079df4  mov     edx, eax; int
0x180079df6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180079dfb  mov     r9d, 0ABh
0x180079e01  jmp     short loc_180079DB0
0x180079e03  cmp     [rbp+var_30], 0
0x180079e07  jz      loc_180079FEF
0x180079e0d  mov     rax, [rdi]
0x180079e10  xor     ecx, ecx; string
0x180079e12  mov     [rbp+string], 0
0x180079e1a  mov     rbx, [rax+0E8h]
0x180079e21  call    cs:__imp_WindowsDeleteString
0x180079e27  lea     rdx, [rbp+string]
0x180079e2b  mov     [rbp+string], 0
0x180079e33  mov     rcx, rdi
0x180079e36  mov     rax, rbx
0x180079e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e3e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180079e46  lea     rdx, [rbp+var_30]
0x180079e4a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180079e4e  mov     [rbp+var_30], 3Ah ; ':'
0x180079e55  lea     rcx, [rbp+Block]
0x180079e59  mov     [rbp+var_18], rdi
0x180079e5d  movdqu  xmmword ptr [rbp+Block], xmm0
0x180079e62  call    ??$_PushBackOne2@W4_SebiEventType@@@?$vector@W4_SebiEventType@@V?$allocator@W4_SebiEventType@@@utl@@@utl@@AEAA_N$$QEAW4_SebiEventType@@@Z; utl::vector<_SebiEventType,utl::allocator<_SebiEventType>>::_PushBackOne2<_SebiEventType>(_SebiEventType &&)
0x180079e67  test    al, al
0x180079e69  jnz     short loc_180079EB1
0x180079e6b  mov     ebx, 8007000Eh
0x180079e70  mov     edx, ebx; int
0x180079e72  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180079e77  mov     r9d, 0B5h
0x180079e7d  xor     edx, edx
0x180079e7f  lea     r8, aOnecoreuapNetP_19; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180079e86  mov     ecx, ebx
0x180079e88  call    Log_HREvent_22
0x180079e8d  mov     rcx, [rbp+Block]; Block
0x180079e91  cmp     rcx, rdi
0x180079e94  jz      short loc_180079EA2
0x180079e96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180079e9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079ea2  mov     rcx, [rbp+string]; string
0x180079ea6  call    cs:__imp_WindowsDeleteString
0x180079eac  jmp     loc_180079DC3
0x180079eb1  mov     rcx, [rbp+Block+8]
0x180079eb5  mov     edx, 3Dh ; '='
0x180079eba  mov     rax, [rbp+var_18]
0x180079ebe  mov     [rbp+var_30], edx
0x180079ec1  cmp     rcx, rax
0x180079ec4  jz      short loc_180079ED2
0x180079ec6  mov     [rcx], edx
0x180079ec8  add     rcx, 4
0x180079ecc  mov     [rbp+Block+8], rcx
0x180079ed0  jmp     short loc_180079EFF
0x180079ed2  lea     rdx, [rbp+var_30]
0x180079ed6  lea     rcx, [rbp+Block]
0x180079eda  call    ??$_PushBackOne2@W4_SebiEventType@@@?$vector@W4_SebiEventType@@V?$allocator@W4_SebiEventType@@@utl@@@utl@@AEAA_N$$QEAW4_SebiEventType@@@Z; utl::vector<_SebiEventType,utl::allocator<_SebiEventType>>::_PushBackOne2<_SebiEventType>(_SebiEventType &&)
0x180079edf  test    al, al
0x180079ee1  jnz     short loc_180079EF7
0x180079ee3  mov     ebx, 8007000Eh
0x180079ee8  mov     edx, ebx; int
0x180079eea  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180079eef  mov     r9d, 0B6h
0x180079ef5  jmp     short loc_180079E7D
0x180079ef7  mov     rax, [rbp+var_18]
0x180079efb  mov     rcx, [rbp+Block+8]
0x180079eff  mov     edx, 25h ; '%'
0x180079f04  mov     [rbp+var_30], edx
0x180079f07  cmp     rcx, rax
0x180079f0a  jz      short loc_180079F18
0x180079f0c  mov     [rcx], edx
0x180079f0e  add     rcx, 4
0x180079f12  mov     [rbp+Block+8], rcx
0x180079f16  jmp     short loc_180079F48
0x180079f18  lea     rdx, [rbp+var_30]
0x180079f1c  lea     rcx, [rbp+Block]
0x180079f20  call    ??$_PushBackOne2@W4_SebiEventType@@@?$vector@W4_SebiEventType@@V?$allocator@W4_SebiEventType@@@utl@@@utl@@AEAA_N$$QEAW4_SebiEventType@@@Z; utl::vector<_SebiEventType,utl::allocator<_SebiEventType>>::_PushBackOne2<_SebiEventType>(_SebiEventType &&)
0x180079f25  test    al, al
0x180079f27  jnz     short loc_180079F40
0x180079f29  mov     ebx, 8007000Eh
0x180079f2e  mov     edx, ebx; int
0x180079f30  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180079f35  mov     r9d, 0B7h
0x180079f3b  jmp     loc_180079E7D
0x180079f40  mov     rax, [rbp+var_18]
0x180079f44  mov     rcx, [rbp+Block+8]
0x180079f48  mov     edx, 39h ; '9'
0x180079f4d  mov     [rbp+var_30], edx
0x180079f50  cmp     rcx, rax
0x180079f53  jz      short loc_180079F9F
0x180079f55  lea     rax, [rcx+4]
0x180079f59  mov     [rcx], edx
0x180079f5b  mov     [rbp+Block+8], rax
0x180079f5f  mov     rcx, [rbp+string]; string
0x180079f63  xor     edx, edx; length
0x180079f65  mov     [rbp+var_30], 0
0x180079f6c  call    cs:__imp_WindowsGetStringRawBuffer
0x180079f72  mov     rcx, rax; applicationUserModelId
0x180079f75  lea     r8, [rbp+var_30]
0x180079f79  lea     rdx, [rbp+Block]
0x180079f7d  call    ?IsRegisteredByApp@ApplicationTracker@@KAJPEBGAEBV?$vector@W4_SebiEventType@@V?$allocator@W4_SebiEventType@@@utl@@@utl@@PEAH@Z; ApplicationTracker::IsRegisteredByApp(ushort const *,utl::vector<_SebiEventType,utl::allocator<_SebiEventType>> const &,int *)
0x180079f82  mov     ebx, eax
0x180079f84  test    eax, eax
0x180079f86  jns     short loc_180079FC7
0x180079f88  mov     edx, eax; int
0x180079f8a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180079f8f  mov     r9d, 0BBh
0x180079f95  mov     edx, 1
0x180079f9a  jmp     loc_180079E7F
0x180079f9f  lea     rdx, [rbp+var_30]
0x180079fa3  lea     rcx, [rbp+Block]
0x180079fa7  call    ??$_PushBackOne2@W4_SebiEventType@@@?$vector@W4_SebiEventType@@V?$allocator@W4_SebiEventType@@@utl@@@utl@@AEAA_N$$QEAW4_SebiEventType@@@Z; utl::vector<_SebiEventType,utl::allocator<_SebiEventType>>::_PushBackOne2<_SebiEventType>(_SebiEventType &&)
0x180079fac  test    al, al
0x180079fae  jnz     short loc_180079F5F
0x180079fb0  mov     ebx, 8007000Eh
0x180079fb5  mov     edx, ebx; int
0x180079fb7  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180079fbc  mov     r9d, 0B8h
0x180079fc2  jmp     loc_180079E7D
0x180079fc7  cmp     [rbp+var_30], 0
0x180079fcb  mov     rcx, [rbp+Block]; Block
0x180079fcf  jz      short loc_180079FD7
0x180079fd1  mov     dword ptr [rsi], 1
0x180079fd7  cmp     rcx, rdi
0x180079fda  jz      short loc_180079FE8
0x180079fdc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180079fe3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180079fe8  xor     ebx, ebx
0x180079fea  jmp     loc_180079EA2
0x180079fef  xor     eax, eax
0x180079ff1  mov     rcx, [rbp+var_8]
0x180079ff5  xor     rcx, rsp; StackCookie
0x180079ff8  call    __security_check_cookie
0x180079ffd  mov     rbx, [rsp+60h+arg_0]
0x18007a005  add     rsp, 60h
0x18007a009  pop     rdi
0x18007a00a  pop     rsi
0x18007a00b  pop     rbp
0x18007a00c  retn
```
