# tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x1800738b0`
- end: `0x180073c02`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `850`
- prototype: `__int64 __fastcall(tson *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007bf34`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x18000990c`
- `0x180071ec4`
- `0x180073038`
- `0x1800738b0`
- `0x18007bd1c`
- `0x18007c854`
- `0x18007d2f4`
- `0x18007d894`
- `0x18007ec58`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800739b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800739b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180073a24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180073b2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180073a24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180073b2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007399f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180073a10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180073b1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007399f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180073a10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180073b1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800739f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073a62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800739f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073a62`

## pseudocode

```c
void __fastcall tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 *a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v4; // rax
  _QWORD *v8; // r14
  unsigned __int64 v9; // rdi
  __int64 v10; // rbx
  char *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  _WORD *v15; // rdx
  unsigned __int16 v16; // cx
  unsigned __int64 v17; // rax
  __int64 v18; // rbp
  HANDLE ProcessHeap; // rax
  _QWORD *v20; // r15
  char v21; // al
  _QWORD *v22; // rcx
  void *v23; // rcx
  _QWORD *v24; // rdi
  HANDLE v25; // rax
  void *v26; // rcx
  __int64 v27; // rax
  void **v28; // r14
  __int64 v29; // rbx
  char *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned __int16 *v33; // rcx
  _WORD *v34; // rdx
  unsigned __int16 v35; // cx
  void *v36; // rdi
  HANDLE v37; // rax
  struct wil::StoredFailureInfo *v38; // r8
  char v39; // r11
  tson::input_archive *v40; // rcx
  void *v41; // [rsp+20h] [rbp-118h] BYREF
  _BYTE v42[152]; // [rsp+30h] [rbp-108h] BYREF
  __int64 v43; // [rsp+C8h] [rbp-70h]
  __int64 v44; // [rsp+D0h] [rbp-68h]

  v4 = *a2;
  *((_BYTE *)this + 24) = *((_BYTE *)a2 + 8);
  *((_QWORD *)this + 2) = v4;
  v8 = (_QWORD *)a2[2];
  tson::input_archive::startNode(this);
  v9 = 0;
  v10 = 0;
  if ( !*((_BYTE *)this + 25) )
  {
    v11 = (char *)this + 32;
    v12 = *((_QWORD *)this + 17);
    if ( v12 )
      v11 = &v11[4 * v12 - 4];
    else
      *v11 = 1;
    if ( *((_DWORD *)v11 + 1) != 1 && *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147023267;
    v13 = *(_QWORD *)this;
    v14 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    v15 = v14 + 1;
    if ( (unsigned __int64)(v14 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      v16 = 0;
      *(_BYTE *)(v13 + 24) = 1;
    }
    else
    {
      v16 = *v14;
      *(_QWORD *)(v13 + 8) = v15;
    }
    v10 = v16;
  }
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(v8);
  while ( v10 )
  {
    v41 = 0;
    --v10;
    tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
      this,
      &v41);
    v17 = v8[1];
    if ( v8[2] < v17 )
      goto LABEL_30;
    if ( v17 )
    {
      v18 = 2 * v17;
      if ( 2 * v17 <= v17 )
        goto LABEL_27;
    }
    else
    {
      v18 = 10;
    }
    ProcessHeap = GetProcessHeap();
    v9 = 0;
    v20 = HeapAlloc(ProcessHeap, 0, 8 * v18);
    if ( !v20 )
    {
      v21 = 0;
      goto LABEL_28;
    }
    if ( *v8 )
    {
      if ( v8[2] )
      {
        do
        {
          v22 = (_QWORD *)*v8;
          v20[v9] = *(_QWORD *)(*v8 + 8 * v9);
          v22[v9] = 0;
          v23 = *(void **)(*v8 + 8 * v9);
          if ( v23 )
            CoTaskMemFree(v23);
          ++v9;
        }
        while ( v9 < v8[2] );
      }
      v24 = (_QWORD *)*v8;
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v24);
      v9 = 0;
    }
    *v8 = v20;
    v8[1] = v18;
LABEL_27:
    v21 = 1;
LABEL_28:
    if ( v21 )
    {
LABEL_30:
      *(_QWORD *)(*v8 + 8LL * v8[2]) = v41;
      v26 = 0;
      ++v8[2];
      goto LABEL_31;
    }
    v26 = v41;
LABEL_31:
    if ( v26 )
      CoTaskMemFree(v26);
  }
  tson::input_archive::finishNode(this);
  v27 = *a3;
  *((_BYTE *)this + 24) = *((_BYTE *)a3 + 8);
  *((_QWORD *)this + 2) = v27;
  v28 = (void **)a3[2];
  tson::input_archive::startNode(this);
  v29 = 0;
  if ( !*((_BYTE *)this + 25) )
  {
    v30 = (char *)this + 32;
    v31 = *((_QWORD *)this + 17);
    if ( v31 )
      v30 = &v30[4 * v31 - 4];
    else
      *v30 = 1;
    if ( *((_DWORD *)v30 + 1) != 1 && *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147023267;
    v32 = *(_QWORD *)this;
    v33 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    v34 = v33 + 1;
    if ( (unsigned __int64)(v33 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      v35 = 0;
      *(_BYTE *)(v32 + 24) = 1;
    }
    else
    {
      v35 = *v33;
      *(_QWORD *)(v32 + 8) = v34;
    }
    v29 = v35;
  }
  if ( *v28 )
  {
    if ( v28[2] )
    {
      do
        wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)((char *)*v28 + 168 * v9++));
      while ( v9 < (unsigned __int64)v28[2] );
    }
    v36 = *v28;
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v36);
    *v28 = 0;
  }
  v28[1] = 0;
  for ( v28[2] = 0; v29; --v29 )
  {
    v43 = 0;
    v44 = 0;
    memset_0(v42, 0, sizeof(v42));
    tson::input_archive::startNode(this);
    tson::load_nothrow(this, (struct tson::input_archive *)v42, v38);
    tson::input_archive::finishNode(this);
    tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(v28, v42);
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)v42);
  }
  tson::input_archive::finishNode(this);
  v39 = *(_BYTE *)(a4 + 8);
  *((_QWORD *)this + 2) = *(_QWORD *)a4;
  *((_BYTE *)this + 24) = v39;
  tson::input_archive::startNode(v40);
  tson::load_nothrow<tip2::test_flag>(this);
  tson::input_archive::finishNode(this);
}

```

## disassembly

```asm
0x1800738b0  push    rbx
0x1800738b2  push    rbp
0x1800738b3  push    rsi
0x1800738b4  push    rdi
0x1800738b5  push    r12
0x1800738b7  push    r13
0x1800738b9  push    r14
0x1800738bb  push    r15
0x1800738bd  sub     rsp, 0F8h
0x1800738c4  mov     rax, cs:__security_cookie
0x1800738cb  xor     rax, rsp
0x1800738ce  mov     [rsp+138h+var_58], rax
0x1800738d6  mov     rax, [rdx]
0x1800738d9  mov     rsi, rcx
0x1800738dc  mov     cl, [rdx+8]
0x1800738df  mov     r13, r9
0x1800738e2  mov     r12, r8
0x1800738e5  mov     [rsi+18h], cl
0x1800738e8  mov     rcx, rsi; this
0x1800738eb  mov     [rsi+10h], rax
0x1800738ef  mov     r14, [rdx+10h]
0x1800738f3  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x1800738f8  xor     edi, edi
0x1800738fa  mov     ebx, edi
0x1800738fc  cmp     [rsi+19h], dil
0x180073900  jnz     short loc_180073951
0x180073902  lea     rax, [rsi+20h]
0x180073906  mov     rcx, [rax+68h]
0x18007390a  test    rcx, rcx
0x18007390d  jz      short loc_180073919
0x18007390f  lea     rax, [rax+rcx*4]
0x180073913  add     rax, 0FFFFFFFFFFFFFFFCh
0x180073917  jmp     short loc_18007391C
0x180073919  mov     byte ptr [rax], 1
0x18007391c  cmp     dword ptr [rax+4], 1
0x180073920  jz      short loc_18007392E
0x180073922  cmp     [rsi+8], edi
0x180073925  jl      short loc_18007392E
0x180073927  mov     dword ptr [rsi+8], 8007065Dh
0x18007392e  mov     rax, [rsi]
0x180073931  mov     rcx, [rax+8]
0x180073935  lea     rdx, [rcx+2]
0x180073939  cmp     rdx, [rax+10h]
0x18007393d  ja      short loc_180073948
0x18007393f  movzx   ecx, word ptr [rcx]
0x180073942  mov     [rax+8], rdx
0x180073946  jmp     short loc_18007394E
0x180073948  mov     ecx, edi
0x18007394a  mov     byte ptr [rax+18h], 1
0x18007394e  movzx   ebx, cx
0x180073951  mov     rcx, r14
0x180073954  call    ?clear@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAAXXZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(void)
0x180073959  jmp     loc_180073A6E
0x18007395e  lea     rdx, [rsp+138h+var_118]
0x180073963  mov     [rsp+138h+var_118], rdi
0x180073968  dec     rbx
0x18007396b  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x180073970  mov     rax, [r14+8]
0x180073974  cmp     [r14+10h], rax
0x180073978  jb      loc_180073A46
0x18007397e  test    rax, rax
0x180073981  jz      short loc_180073992
0x180073983  lea     rbp, [rax+rax]
0x180073987  cmp     rbp, rax
0x18007398a  jbe     loc_180073A39
0x180073990  jmp     short loc_180073997
0x180073992  mov     ebp, 0Ah
0x180073997  lea     rdi, ds:0[rbp*8]
0x18007399f  call    cs:__imp_GetProcessHeap
0x1800739a6  nop     dword ptr [rax+rax+00h]
0x1800739ab  mov     r8, rdi; dwBytes
0x1800739ae  xor     edx, edx; dwFlags
0x1800739b0  mov     rcx, rax; hHeap
0x1800739b3  call    cs:__imp_HeapAlloc
0x1800739ba  nop     dword ptr [rax+rax+00h]
0x1800739bf  xor     edi, edi
0x1800739c1  mov     r15, rax
0x1800739c4  test    rax, rax
0x1800739c7  jnz     short loc_1800739CE
0x1800739c9  mov     al, dil
0x1800739cc  jmp     short loc_180073A3B
0x1800739ce  cmp     [r14], rdi
0x1800739d1  jz      short loc_180073A32
0x1800739d3  cmp     [r14+10h], rdi
0x1800739d7  jbe     short loc_180073A0D
0x1800739d9  mov     rcx, [r14]
0x1800739dc  mov     rax, [rcx+rdi*8]
0x1800739e0  mov     [r15+rdi*8], rax
0x1800739e4  mov     qword ptr [rcx+rdi*8], 0
0x1800739ec  mov     rax, [r14]
0x1800739ef  mov     rcx, [rax+rdi*8]; pv
0x1800739f3  test    rcx, rcx
0x1800739f6  jz      short loc_180073A04
0x1800739f8  call    cs:__imp_CoTaskMemFree
0x1800739ff  nop     dword ptr [rax+rax+00h]
0x180073a04  inc     rdi
0x180073a07  cmp     rdi, [r14+10h]
0x180073a0b  jb      short loc_1800739D9
0x180073a0d  mov     rdi, [r14]
0x180073a10  call    cs:__imp_GetProcessHeap
0x180073a17  nop     dword ptr [rax+rax+00h]
0x180073a1c  mov     r8, rdi; lpMem
0x180073a1f  xor     edx, edx; dwFlags
0x180073a21  mov     rcx, rax; hHeap
0x180073a24  call    cs:__imp_HeapFree
0x180073a2b  nop     dword ptr [rax+rax+00h]
0x180073a30  xor     edi, edi
0x180073a32  mov     [r14], r15
0x180073a35  mov     [r14+8], rbp
0x180073a39  mov     al, 1
0x180073a3b  test    al, al
0x180073a3d  jnz     short loc_180073A46
0x180073a3f  mov     rcx, [rsp+138h+var_118]
0x180073a44  jmp     short loc_180073A5D
0x180073a46  mov     rdx, [r14+10h]
0x180073a4a  mov     rcx, [r14]
0x180073a4d  mov     rax, [rsp+138h+var_118]
0x180073a52  mov     [rcx+rdx*8], rax
0x180073a56  mov     rcx, rdi; pv
0x180073a59  inc     qword ptr [r14+10h]
0x180073a5d  test    rcx, rcx
0x180073a60  jz      short loc_180073A6E
0x180073a62  call    cs:__imp_CoTaskMemFree
0x180073a69  nop     dword ptr [rax+rax+00h]
0x180073a6e  mov     rcx, rsi; this
0x180073a71  test    rbx, rbx
0x180073a74  jnz     loc_18007395E
0x180073a7a  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180073a7f  mov     cl, [r12+8]
0x180073a84  mov     rax, [r12]
0x180073a88  mov     [rsi+18h], cl
0x180073a8b  mov     rcx, rsi; this
0x180073a8e  mov     [rsi+10h], rax
0x180073a92  mov     r14, [r12+10h]
0x180073a97  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180073a9c  mov     rbx, rdi
0x180073a9f  cmp     [rsi+19h], dil
0x180073aa3  jnz     short loc_180073AF4
0x180073aa5  lea     rax, [rsi+20h]
0x180073aa9  mov     rcx, [rax+68h]
0x180073aad  test    rcx, rcx
0x180073ab0  jz      short loc_180073ABC
0x180073ab2  lea     rax, [rax+rcx*4]
0x180073ab6  add     rax, 0FFFFFFFFFFFFFFFCh
0x180073aba  jmp     short loc_180073ABF
0x180073abc  mov     byte ptr [rax], 1
0x180073abf  cmp     dword ptr [rax+4], 1
0x180073ac3  jz      short loc_180073AD1
0x180073ac5  cmp     [rsi+8], edi
0x180073ac8  jl      short loc_180073AD1
0x180073aca  mov     dword ptr [rsi+8], 8007065Dh
0x180073ad1  mov     rax, [rsi]
0x180073ad4  mov     rcx, [rax+8]
0x180073ad8  lea     rdx, [rcx+2]
0x180073adc  cmp     rdx, [rax+10h]
0x180073ae0  ja      short loc_180073AEB
0x180073ae2  movzx   ecx, word ptr [rcx]
0x180073ae5  mov     [rax+8], rdx
0x180073ae9  jmp     short loc_180073AF1
0x180073aeb  mov     ecx, edi
0x180073aed  mov     byte ptr [rax+18h], 1
0x180073af1  movzx   ebx, cx
0x180073af4  cmp     [r14], rdi
0x180073af7  jz      short loc_180073B40
0x180073af9  cmp     qword ptr [r14+10h], 0
0x180073afe  jbe     short loc_180073B18
0x180073b00  imul    rcx, rdi, 0A8h
0x180073b07  add     rcx, [r14]; this
0x180073b0a  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180073b0f  inc     rdi
0x180073b12  cmp     rdi, [r14+10h]
0x180073b16  jb      short loc_180073B00
0x180073b18  mov     rdi, [r14]
0x180073b1b  call    cs:__imp_GetProcessHeap
0x180073b22  nop     dword ptr [rax+rax+00h]
0x180073b27  mov     r8, rdi; lpMem
0x180073b2a  xor     edx, edx; dwFlags
0x180073b2c  mov     rcx, rax; hHeap
0x180073b2f  call    cs:__imp_HeapFree
0x180073b36  nop     dword ptr [rax+rax+00h]
0x180073b3b  xor     edi, edi
0x180073b3d  mov     [r14], rdi
0x180073b40  mov     [r14+8], rdi
0x180073b44  mov     [r14+10h], rdi
0x180073b48  test    rbx, rbx
0x180073b4b  jz      short loc_180073BA9
0x180073b4d  xor     edx, edx; Val
0x180073b4f  mov     [rsp+138h+var_70], rdi
0x180073b57  mov     r8d, 98h; Size
0x180073b5d  mov     [rsp+138h+var_68], rdi
0x180073b65  lea     rcx, [rsp+138h+var_108]; void *
0x180073b6a  call    memset_0
0x180073b6f  mov     rcx, rsi; this
0x180073b72  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180073b77  lea     rdx, [rsp+138h+var_108]; struct tson::input_archive *
0x180073b7c  mov     rcx, rsi; this
0x180073b7f  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAVStoredFailureInfo@wil@@@Z; tson::load_nothrow(tson::input_archive &,wil::StoredFailureInfo &)
0x180073b84  mov     rcx, rsi; this
0x180073b87  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180073b8c  lea     rdx, [rsp+138h+var_108]
0x180073b91  mov     rcx, r14
0x180073b94  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x180073b99  lea     rcx, [rsp+138h+var_108]; this
0x180073b9e  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180073ba3  sub     rbx, 1
0x180073ba7  jnz     short loc_180073B4D
0x180073ba9  mov     rcx, rsi; this
0x180073bac  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180073bb1  mov     rax, [r13+0]
0x180073bb5  mov     r11b, [r13+8]
0x180073bb9  mov     [rsi+10h], rax
0x180073bbd  mov     [rsi+18h], r11b
0x180073bc1  mov     rbx, [r13+10h]
0x180073bc5  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180073bca  mov     rdx, rbx
0x180073bcd  mov     rcx, rsi; this
0x180073bd0  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180073bd5  mov     rcx, rsi; this
0x180073bd8  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180073bdd  mov     rcx, [rsp+138h+var_58]
0x180073be5  xor     rcx, rsp; StackCookie
0x180073be8  call    __security_check_cookie
0x180073bed  add     rsp, 0F8h
0x180073bf4  pop     r15
0x180073bf6  pop     r14
0x180073bf8  pop     r13
0x180073bfa  pop     r12
0x180073bfc  pop     rdi
0x180073bfd  pop     rsi
0x180073bfe  pop     rbp
0x180073bff  pop     rbx
0x180073c00  retn
```
