# Container::Manager::Core::Details::Resource::AddOutgoingNeighbor(Container::Manager::Core::Details::Resource *)

- ea: `0x180051a14`
- end: `0x18005213b`
- name: `?AddOutgoingNeighbor@Resource@Details@Core@Manager@Container@@AEAAJPEAV12345@@Z`
- size: `1831`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::Resource *__hidden this, struct Container::Manager::Core::Details::Resource *)`
- caller_count: `4`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180050a1c`
- `0x180052300`
- `0x180052530`
- `0x180052890`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x180016774`
- `0x18002c5b4`
- `0x18002dc8c`
- `0x180032344`
- `0x18003c750`
- `0x18004feb4`
- `0x180051a14`
- `0x180052144`
- `0x18005bee8`
- `0x18005ce8c`
- `0x18005d1f0`
- `0x18005d248`
- `0x180065d00`
- `0x180066498`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180051b98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180051bf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180051e69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180051f00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800520fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180051b98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180051bf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180051e69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180051f00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800520fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180051adc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180051adc`

## string_xrefs

- `0x180051a43`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051a86`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051aaf`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051b3b`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051b7c`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051bb9`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051c51`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051cc6`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051e0e`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051ebe`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051f37`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051ffd`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800520b2`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180052129`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180051bcb`: `Cannot create resource because its parent has an ongoing operation of type %d`

## pseudocode

```c
int __fastcall Container::Manager::Core::Details::Resource::AddOutgoingNeighbor(
        Container::Manager::Core::ResourceHandle ***this,
        struct Container::Manager::Core::Details::Resource *a2)
{
  wil::details::in1diag3 *v4; // rcx
  __int64 v5; // r9
  __int64 v6; // rdx
  int v8; // ebx
  __int64 v9; // rdx
  int v10; // eax
  RTL_SRWLOCK *v11; // rdi
  unsigned int i; // ebx
  int v13; // eax
  int v14; // esi
  void *v15; // rcx
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  __int64 v24; // rdx
  Container::Manager::Core::ResourceHandle *v25; // rax
  Container::Manager::Core::ResourceHandle *v26; // rsi
  int v27; // eax
  int v28; // r12d
  _QWORD *v29; // rax
  __int64 v30; // r8
  const char *v31; // r9
  Container::Manager::Core::ResourceHandle *v32; // rdi
  Container::Manager::Core::ResourceHandle **v33; // rdx
  Container::Manager::Core::ResourceHandle *v34; // rdi
  Container::Manager::Core::ResourceHandle *v35; // rdi
  Container::Manager::Core::ResourceHandle *v36; // rdi
  unsigned int v37; // [rsp+20h] [rbp-60h]
  char *v38; // [rsp+28h] [rbp-58h]
  void *v39; // [rsp+30h] [rbp-50h] BYREF
  __int64 v40; // [rsp+38h] [rbp-48h]
  void *v41; // [rsp+40h] [rbp-40h] BYREF
  char *v42; // [rsp+48h] [rbp-38h]
  _WORD v43[8]; // [rsp+50h] [rbp-30h] BYREF
  void *v44; // [rsp+60h] [rbp-20h] BYREF
  char *v45; // [rsp+68h] [rbp-18h]
  _WORD v46[8]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  Container::Manager::Core::ResourceHandle *v48; // [rsp+B8h] [rbp+38h] BYREF
  Container::Manager::Core::Details::Resource *v49; // [rsp+C0h] [rbp+40h]

  if ( *((_BYTE *)a2 + 256) )
  {
    v4 = retaddr;
    v5 = 303;
    v6 = 1525;
    return wil::details::in1diag3::Return_Win32(
             v4,
             (void *)v6,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
             (const char *)v5,
             v37);
  }
  if ( !Container::Manager::Core::Details::Resource::IsDeleteOnClose((Container::Manager::Core::Details::Resource *)this)
    && Container::Manager::Core::Details::Resource::IsDeleteOnClose(a2) )
  {
    v8 = Container::Manager::Core::Details::Resource::LogResourceInformation((Container::Manager::Core::Details::Resource *)this);
    if ( v8 >= 0 )
    {
      v10 = Container::Manager::Core::Details::Resource::LogResourceInformation(a2);
      v4 = retaddr;
      v8 = v10;
      if ( v10 >= 0 )
      {
        v5 = 5069;
        v6 = 1537;
        return wil::details::in1diag3::Return_Win32(
                 v4,
                 (void *)v6,
                 (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
                 (const char *)v5,
                 v37);
      }
      v9 = 1535;
    }
    else
    {
      v4 = retaddr;
      v9 = 1534;
    }
    wil::details::in1diag3::Return_Hr(
      v4,
      (void *)v9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v8,
      v37);
    return v8;
  }
  v11 = (RTL_SRWLOCK *)(*((_QWORD *)a2 + 33) + 16LL);
  AcquireSRWLockShared(v11);
  for ( i = 4; i < 8; ++i )
  {
    if ( i != 5
      && (unsigned __int8)Container::Manager::Core::Details::ResourceOperationMap::IsResourceOperationInProgressLocked(
                            *((_QWORD *)a2 + 33),
                            i) )
    {
      v14 = Container::Manager::Core::Details::Resource::LogResourceInformation((Container::Manager::Core::Details::Resource *)this);
      if ( v14 >= 0 )
      {
        v18 = Container::Manager::Core::Details::Resource::LogResourceInformation(a2);
        v16 = retaddr;
        v14 = v18;
        if ( v18 >= 0 )
        {
          LODWORD(v38) = i;
          v8 = wil::details::in1diag3::Return_Win32Msg(
                 retaddr,
                 (void *)0x61B,
                 (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
                 (const char *)0x139F,
                 (unsigned int)"Cannot create resource because its parent has an ongoing operation of type %d",
                 v38);
          if ( v11 )
            ReleaseSRWLockShared(v11);
          return v8;
        }
        v17 = 1560;
      }
      else
      {
        v16 = retaddr;
        v17 = 1559;
      }
      wil::details::in1diag3::Return_Hr(
        v16,
        (void *)v17,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v14,
        v37);
      goto LABEL_23;
    }
  }
  v44 = v46;
  v45 = (char *)v46;
  v46[0] = 0;
  v13 = Csl::GuidToString(this, &v44);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x621,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v13,
      v37);
    v15 = v44;
    if ( v44 != v46 )
      goto LABEL_19;
    goto LABEL_23;
  }
  v19 = *((_DWORD *)this + 4);
  v41 = v43;
  v42 = (char *)v43;
  v43[0] = 0;
  v20 = v19 - 1;
  if ( !v20 )
  {
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            &v41,
                            L"Storage_",
                            8) )
      goto LABEL_50;
    v24 = 1577;
    goto LABEL_41;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            &v41,
                            L"Layer_",
                            6) )
      goto LABEL_50;
    v24 = 1583;
    goto LABEL_41;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            &v41,
                            L"Snapshot_",
                            9) )
      goto LABEL_50;
    v24 = 1589;
    goto LABEL_41;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            &v41,
                            L"Zygote_",
                            7) )
      goto LABEL_50;
    v24 = 1595;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      v37);
    goto LABEL_92;
  }
  if ( v23 != 1 )
  {
    v14 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x80004005LL,
      v37);
    if ( v41 != v43 )
      operator delete(v41, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v44;
    if ( v44 != v46 )
LABEL_19:
      operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
LABEL_23:
    if ( v11 )
      ReleaseSRWLockShared(v11);
    return v14;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v41,
                           L"BaseImage_",
                           10) )
  {
    v24 = 1601;
    goto LABEL_41;
  }
LABEL_50:
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v41,
                           v44,
                           (v45 - (_BYTE *)v44) >> 1) )
  {
    v24 = 1612;
    goto LABEL_41;
  }
  v25 = (Container::Manager::Core::ResourceHandle *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v25;
  if ( !v25 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x650,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      v37);
LABEL_92:
    if ( v41 != v43 )
      operator delete(v41, (const struct std::nothrow_t *)&std::nothrow);
    if ( v44 != v46 )
      operator delete(v44, (const struct std::nothrow_t *)&std::nothrow);
    if ( v11 )
      ReleaseSRWLockShared(v11);
    return -2147024882;
  }
  v48 = v25;
  *(_QWORD *)v25 = (char *)v25 + 16;
  *((_QWORD *)v25 + 1) = (char *)v25 + 16;
  *((_WORD *)v25 + 8) = 0;
  *((_DWORD *)v25 + 8) = 0;
  *((_QWORD *)v25 + 5) = 0;
  *((_QWORD *)v25 + 8) = 0;
  *((_QWORD *)v25 + 9) = 0;
  *((_BYTE *)v25 + 80) = 0;
  *((_QWORD *)v25 + 6) = 0;
  *((_QWORD *)v25 + 7) = 0;
  v39 = v41;
  v40 = (v42 - (_BYTE *)v41) >> 1;
  v27 = Container::Manager::Core::ResourceHandle::Initialize(v25, &v39);
  v28 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x652,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v27,
      v37);
    Container::Manager::Core::ResourceHandle::~ResourceHandle(v26);
    operator delete(v26, (const struct std::nothrow_t *)0x58);
    if ( v41 != v43 )
      operator delete(v41, (const struct std::nothrow_t *)&std::nothrow);
    if ( v44 != v46 )
      operator delete(v44, (const struct std::nothrow_t *)&std::nothrow);
    if ( v11 )
      ReleaseSRWLockShared(v11);
    return v28;
  }
  *((_BYTE *)v26 + 80) = 1;
  v29 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v29 )
    v29[3] = this;
  utl::_Tree<Container::Manager::Core::Details::Resource *,Container::Manager::Core::Details::Resource *,utl::less<Container::Manager::Core::Details::Resource *>,utl::allocator<Container::Manager::Core::Details::Resource *>,0>::_EmplaceImpl(
    (char *)a2 + 216,
    &v39,
    v30,
    v29);
  if ( !v39 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      v37);
    Container::Manager::Core::ResourceHandle::~ResourceHandle(v26);
    operator delete(v26, (const struct std::nothrow_t *)0x58);
    goto LABEL_92;
  }
  if ( !(_BYTE)v40 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x65D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      v31);
  if ( v11 )
    ReleaseSRWLockShared(v11);
  if ( !(unsigned __int8)utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>::emplace_back<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,0>(
                           this + 24,
                           &v48) )
  {
    v49 = (Container::Manager::Core::Details::Resource *)this;
    utl::_Tree<Container::Manager::Core::Details::Resource *,Container::Manager::Core::Details::Resource *,utl::less<Container::Manager::Core::Details::Resource *>,utl::allocator<Container::Manager::Core::Details::Resource *>,0>::erase((char *)a2 + 216);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      v37);
    v32 = v48;
    if ( v48 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v48);
      operator delete(v32, (const struct std::nothrow_t *)0x58);
    }
    if ( v41 != v43 )
      operator delete(v41, (const struct std::nothrow_t *)&std::nothrow);
    if ( v44 != v46 )
      operator delete(v44, (const struct std::nothrow_t *)&std::nothrow);
    return -2147024882;
  }
  v14 = Container::Manager::Core::ResourceHandle::AddResource(*(this[25] - 1), a2);
  if ( v14 < 0 )
  {
    v49 = (Container::Manager::Core::Details::Resource *)this;
    utl::_Tree<Container::Manager::Core::Details::Resource *,Container::Manager::Core::Details::Resource *,utl::less<Container::Manager::Core::Details::Resource *>,utl::allocator<Container::Manager::Core::Details::Resource *>,0>::erase((char *)a2 + 216);
    v33 = --this[25];
    v34 = *v33;
    *v33 = 0;
    if ( v34 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v34);
      operator delete(v34, (const struct std::nothrow_t *)0x58);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v14,
      v37);
    v35 = v48;
    if ( v48 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v48);
      operator delete(v35, (const struct std::nothrow_t *)0x58);
    }
    if ( v41 != v43 )
      operator delete(v41, (const struct std::nothrow_t *)&std::nothrow);
    if ( v44 != v46 )
      operator delete(v44, (const struct std::nothrow_t *)&std::nothrow);
    return v14;
  }
  v36 = v48;
  if ( v48 )
  {
    Container::Manager::Core::ResourceHandle::~ResourceHandle(v48);
    operator delete(v36, (const struct std::nothrow_t *)0x58);
  }
  if ( v41 != v43 )
    operator delete(v41, (const struct std::nothrow_t *)&std::nothrow);
  if ( v44 != v46 )
    operator delete(v44, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180051a14  mov     [rsp-28h+arg_0], rbx
0x180051a19  mov     [rsp-28h+arg_18], rsi
0x180051a1e  push    rbp
0x180051a1f  push    rdi
0x180051a20  push    r12
0x180051a22  push    r14
0x180051a24  push    r15
0x180051a26  mov     rbp, rsp
0x180051a29  sub     rsp, 80h
0x180051a30  cmp     byte ptr [rdx+100h], 0
0x180051a37  mov     r15, rdx
0x180051a3a  mov     r14, rcx
0x180051a3d  jz      short loc_180051A5F
0x180051a3f  mov     rcx, [rbp+28h]; this
0x180051a43  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051a4a  mov     r9d, 12Fh; char *
0x180051a50  mov     edx, 5F5h; void *
0x180051a55  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180051a5a  jmp     loc_18005210C
0x180051a5f  call    ?IsDeleteOnClose@Resource@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::Resource::IsDeleteOnClose(void)
0x180051a64  test    al, al
0x180051a66  jnz     short loc_180051ACE
0x180051a68  mov     rcx, r15; this
0x180051a6b  call    ?IsDeleteOnClose@Resource@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::Resource::IsDeleteOnClose(void)
0x180051a70  test    al, al
0x180051a72  jz      short loc_180051ACE
0x180051a74  mov     rcx, r14; this
0x180051a77  call    ?LogResourceInformation@Resource@Details@Core@Manager@Container@@AEBAJXZ; Container::Manager::Core::Details::Resource::LogResourceInformation(void)
0x180051a7c  mov     ebx, eax
0x180051a7e  test    eax, eax
0x180051a80  jns     short loc_180051AA1
0x180051a82  mov     rcx, [rbp+28h]; this
0x180051a86  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051a8d  mov     edx, 5FEh; void *
0x180051a92  mov     r9d, ebx; char *
0x180051a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051a9a  mov     eax, ebx
0x180051a9c  jmp     loc_18005210C
0x180051aa1  mov     rcx, r15; this
0x180051aa4  call    ?LogResourceInformation@Resource@Details@Core@Manager@Container@@AEBAJXZ; Container::Manager::Core::Details::Resource::LogResourceInformation(void)
0x180051aa9  mov     rcx, [rbp+28h]
0x180051aad  mov     ebx, eax
0x180051aaf  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051ab6  test    eax, eax
0x180051ab8  jns     short loc_180051AC1
0x180051aba  mov     edx, 5FFh
0x180051abf  jmp     short loc_180051A92
0x180051ac1  mov     r9d, 13CDh
0x180051ac7  mov     edx, 601h
0x180051acc  jmp     short loc_180051A55
0x180051ace  mov     rdi, [r15+108h]
0x180051ad5  add     rdi, 10h
0x180051ad9  mov     rcx, rdi; SRWLock
0x180051adc  call    cs:__imp_AcquireSRWLockShared
0x180051ae3  nop     dword ptr [rax+rax+00h]
0x180051ae8  mov     ebx, 4
0x180051aed  cmp     ebx, 5
0x180051af0  jz      short loc_180051B04
0x180051af2  mov     rcx, [r15+108h]
0x180051af9  mov     edx, ebx
0x180051afb  call    ?IsResourceOperationInProgressLocked@ResourceOperationMap@Details@Core@Manager@Container@@AEBA_NW4ResourceOperationType@2345@@Z; Container::Manager::Core::Details::ResourceOperationMap::IsResourceOperationInProgressLocked(Container::Manager::Core::Details::ResourceOperationType)
0x180051b00  test    al, al
0x180051b02  jnz     short loc_180051B6A
0x180051b04  inc     ebx
0x180051b06  cmp     ebx, 8
0x180051b09  jb      short loc_180051AED
0x180051b0b  lea     rax, [rbp+var_10]
0x180051b0f  mov     rcx, r14
0x180051b12  mov     [rbp+var_20], rax
0x180051b16  lea     rdx, [rbp+var_20]
0x180051b1a  lea     rax, [rbp+var_10]
0x180051b1e  mov     [rbp+var_18], rax
0x180051b22  xor     eax, eax
0x180051b24  mov     [rbp+var_10], ax
0x180051b28  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180051b2d  mov     esi, eax
0x180051b2f  test    eax, eax
0x180051b31  jns     loc_180051C0A
0x180051b37  mov     rcx, [rbp+28h]; this
0x180051b3b  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051b42  mov     r9d, eax; char *
0x180051b45  mov     edx, 621h; void *
0x180051b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051b4f  mov     rcx, [rbp+var_20]; void *
0x180051b53  lea     rax, [rbp+var_10]
0x180051b57  cmp     rcx, rax
0x180051b5a  jz      short loc_180051B90
0x180051b5c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180051b63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051b68  jmp     short loc_180051B90
0x180051b6a  mov     rcx, r14; this
0x180051b6d  call    ?LogResourceInformation@Resource@Details@Core@Manager@Container@@AEBAJXZ; Container::Manager::Core::Details::Resource::LogResourceInformation(void)
0x180051b72  mov     esi, eax
0x180051b74  test    eax, eax
0x180051b76  jns     short loc_180051BAB
0x180051b78  mov     rcx, [rbp+28h]; this
0x180051b7c  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051b83  mov     edx, 617h; void *
0x180051b88  mov     r9d, esi; char *
0x180051b8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051b90  test    rdi, rdi
0x180051b93  jz      short loc_180051BA4
0x180051b95  mov     rcx, rdi; SRWLock
0x180051b98  call    cs:__imp_ReleaseSRWLockShared
0x180051b9f  nop     dword ptr [rax+rax+00h]
0x180051ba4  mov     eax, esi
0x180051ba6  jmp     loc_18005210C
0x180051bab  mov     rcx, r15; this
0x180051bae  call    ?LogResourceInformation@Resource@Details@Core@Manager@Container@@AEBAJXZ; Container::Manager::Core::Details::Resource::LogResourceInformation(void)
0x180051bb3  mov     rcx, [rbp+28h]; this
0x180051bb7  mov     esi, eax
0x180051bb9  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051bc0  test    eax, eax
0x180051bc2  jns     short loc_180051BCB
0x180051bc4  mov     edx, 618h
0x180051bc9  jmp     short loc_180051B88
0x180051bcb  lea     rax, aCannotCreateRe; "Cannot create resource because its pare"...
0x180051bd2  mov     dword ptr [rsp+80h+var_58], ebx; char *
0x180051bd6  mov     r9d, 139Fh; char *
0x180051bdc  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x180051be1  mov     edx, 61Bh; void *
0x180051be6  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180051beb  mov     ebx, eax
0x180051bed  test    rdi, rdi
0x180051bf0  jz      loc_180051A9A
0x180051bf6  mov     rcx, rdi; SRWLock
0x180051bf9  call    cs:__imp_ReleaseSRWLockShared
0x180051c00  nop     dword ptr [rax+rax+00h]
0x180051c05  jmp     loc_180051A9A
0x180051c0a  mov     ecx, [r14+10h]
0x180051c0e  lea     rax, [rbp+var_30]
0x180051c12  mov     [rbp+var_40], rax
0x180051c16  lea     rax, [rbp+var_30]
0x180051c1a  mov     [rbp+var_38], rax
0x180051c1e  xor     eax, eax
0x180051c20  mov     [rbp+var_30], ax
0x180051c24  sub     ecx, 1
0x180051c27  jz      loc_180051D4A
0x180051c2d  sub     ecx, 1
0x180051c30  jz      loc_180051D26
0x180051c36  sub     ecx, 1
0x180051c39  jz      loc_180051D05
0x180051c3f  sub     ecx, 1
0x180051c42  jz      loc_180051CE4
0x180051c48  cmp     ecx, 1
0x180051c4b  jz      short loc_180051C9F
0x180051c4d  mov     rcx, [rbp+28h]; this
0x180051c51  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051c58  mov     esi, 80004005h
0x180051c5d  mov     edx, 648h; void *
0x180051c62  mov     r9d, esi; char *
0x180051c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051c6a  mov     rcx, [rbp+var_40]; void *
0x180051c6e  lea     rax, [rbp+var_30]
0x180051c72  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180051c79  cmp     rcx, rax
0x180051c7c  jz      short loc_180051C86
0x180051c7e  mov     rdx, rbx; struct std::nothrow_t *
0x180051c81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051c86  mov     rcx, [rbp+var_20]
0x180051c8a  lea     rax, [rbp+var_10]
0x180051c8e  cmp     rcx, rax
0x180051c91  jz      loc_180051B90
0x180051c97  mov     rdx, rbx
0x180051c9a  jmp     loc_180051B63
0x180051c9f  mov     r8d, 0Ah
0x180051ca5  lea     rdx, aBaseimage; "BaseImage_"
0x180051cac  lea     rcx, [rbp+var_40]
0x180051cb0  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180051cb5  test    al, al
0x180051cb7  jnz     loc_180051D6E
0x180051cbd  mov     edx, 641h; void *
0x180051cc2  mov     rcx, [rbp+28h]; this
0x180051cc6  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051ccd  mov     r9d, 8007000Eh; char *
0x180051cd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051cd8  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180051cdf  jmp     loc_1800520C9
0x180051ce4  mov     r8d, 7
0x180051cea  lea     rdx, aZygote; "Zygote_"
0x180051cf1  lea     rcx, [rbp+var_40]
0x180051cf5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180051cfa  test    al, al
0x180051cfc  jnz     short loc_180051D6E
0x180051cfe  mov     edx, 63Bh
0x180051d03  jmp     short loc_180051CC2
0x180051d05  mov     r8d, 9
0x180051d0b  lea     rdx, aSnapshot; "Snapshot_"
0x180051d12  lea     rcx, [rbp+var_40]
0x180051d16  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180051d1b  test    al, al
0x180051d1d  jnz     short loc_180051D6E
0x180051d1f  mov     edx, 635h
0x180051d24  jmp     short loc_180051CC2
0x180051d26  mov     r8d, 6
0x180051d2c  lea     rdx, aLayer; "Layer_"
0x180051d33  lea     rcx, [rbp+var_40]
0x180051d37  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180051d3c  test    al, al
0x180051d3e  jnz     short loc_180051D6E
0x180051d40  mov     edx, 62Fh
0x180051d45  jmp     loc_180051CC2
0x180051d4a  mov     r8d, 8
0x180051d50  lea     rdx, aStorage; "Storage_"
0x180051d57  lea     rcx, [rbp+var_40]
0x180051d5b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180051d60  test    al, al
0x180051d62  jnz     short loc_180051D6E
0x180051d64  mov     edx, 629h
0x180051d69  jmp     loc_180051CC2
0x180051d6e  mov     r8, [rbp+var_18]
0x180051d72  lea     rcx, [rbp+var_40]
0x180051d76  mov     rdx, [rbp+var_20]
0x180051d7a  sub     r8, rdx
0x180051d7d  sar     r8, 1
0x180051d80  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180051d85  test    al, al
0x180051d87  jnz     short loc_180051D93
0x180051d89  mov     edx, 64Ch
0x180051d8e  jmp     loc_180051CC2
0x180051d93  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180051d9a  mov     ecx, 58h ; 'X'; unsigned __int64
0x180051d9f  mov     rdx, rbx; struct std::nothrow_t *
0x180051da2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180051da7  mov     rsi, rax
0x180051daa  test    rax, rax
0x180051dad  jz      loc_1800520AE
0x180051db3  lea     rcx, [rax+10h]
0x180051db7  mov     [rbp+arg_8], rsi
0x180051dbb  mov     [rax], rcx
0x180051dbe  lea     rdx, [rbp+var_50]
0x180051dc2  mov     [rax+8], rcx
0x180051dc6  xor     eax, eax
0x180051dc8  mov     [rcx], ax
0x180051dcb  mov     [rsi+20h], eax
0x180051dce  mov     [rsi+28h], rax
0x180051dd2  mov     [rsi+40h], rax
0x180051dd6  mov     [rsi+48h], rax
0x180051dda  mov     [rsi+50h], al
0x180051ddd  mov     [rsi+30h], rax
0x180051de1  mov     [rsi+38h], rax
0x180051de5  mov     rax, [rbp+var_40]
0x180051de9  mov     rcx, [rbp+var_38]
0x180051ded  sub     rcx, rax
0x180051df0  mov     [rbp+var_50], rax
0x180051df4  sar     rcx, 1
0x180051df7  mov     [rbp+var_48], rcx
0x180051dfb  mov     rcx, rsi
0x180051dfe  call    ?Initialize@ResourceHandle@Core@Manager@Container@@QEAAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Container::Manager::Core::ResourceHandle::Initialize(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180051e03  mov     r12d, eax
0x180051e06  test    eax, eax
0x180051e08  jns     short loc_180051E7D
0x180051e0a  mov     rcx, [rbp+28h]; this
0x180051e0e  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051e15  mov     r9d, eax; char *
0x180051e18  mov     edx, 652h; void *
0x180051e1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051e22  mov     rcx, rsi; this
0x180051e25  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x180051e2a  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x180051e2f  mov     rcx, rsi; void *
0x180051e32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051e37  mov     rcx, [rbp+var_40]; void *
0x180051e3b  lea     rax, [rbp+var_30]
0x180051e3f  cmp     rcx, rax
0x180051e42  jz      short loc_180051E4C
0x180051e44  mov     rdx, rbx; struct std::nothrow_t *
0x180051e47  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051e4c  mov     rcx, [rbp+var_20]; void *
0x180051e50  lea     rax, [rbp+var_10]
0x180051e54  cmp     rcx, rax
0x180051e57  jz      short loc_180051E61
0x180051e59  mov     rdx, rbx; struct std::nothrow_t *
0x180051e5c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051e61  test    rdi, rdi
0x180051e64  jz      short loc_180051E75
0x180051e66  mov     rcx, rdi; SRWLock
0x180051e69  call    cs:__imp_ReleaseSRWLockShared
0x180051e70  nop     dword ptr [rax+rax+00h]
0x180051e75  mov     eax, r12d
0x180051e78  jmp     loc_18005210C
0x180051e7d  mov     rdx, rbx; struct std::nothrow_t *
0x180051e80  mov     byte ptr [rsi+50h], 1
0x180051e84  mov     ecx, 20h ; ' '; unsigned __int64
0x180051e89  lea     r12, [r15+0D8h]
0x180051e90  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180051e95  test    rax, rax
0x180051e98  jz      short loc_180051E9E
0x180051e9a  mov     [rax+18h], r14
0x180051e9e  mov     r9, rax
0x180051ea1  lea     rdx, [rbp+var_50]
0x180051ea5  mov     rcx, r12
0x180051ea8  call    ?_EmplaceImpl@?$_Tree@PEAVResource@Details@Core@Manager@Container@@PEAV12345@U?$less@PEAVResource@Details@Core@Manager@Container@@@utl@@V?$allocator@PEAVResource@Details@Core@Manager@Container@@@7@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@_N@2@PEAU?$_TreeNode@PEAVResource@Details@Core@Manager@Container@@@2@0@Z; utl::_Tree<Container::Manager::Core::Details::Resource *,Container::Manager::Core::Details::Resource *,utl::less<Container::Manager::Core::Details::Resource *>,utl::allocator<Container::Manager::Core::Details::Resource *>,0>::_EmplaceImpl(utl::_TreeNode<Container::Manager::Core::Details::Resource *> *,utl::_TreeNode<Container::Manager::Core::Details::Resource *> *)
0x180051ead  cmp     [rbp+var_50], 0
0x180051eb2  mov     rcx, [rbp+28h]; this
0x180051eb6  jnz     short loc_180051EE9
0x180051eb8  mov     r9d, 8007000Eh; char *
0x180051ebe  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180051ec5  mov     edx, 65Bh; void *
0x180051eca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
