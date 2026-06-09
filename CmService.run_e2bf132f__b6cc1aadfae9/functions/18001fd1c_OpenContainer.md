# OpenContainer

- ea: `0x18001fd1c`
- end: `0x180020227`
- name: `OpenContainer`
- size: `1291`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, DWORD, Container::Manager::Service::ContainerRpcContextHandle **)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c770`
- `0x18001c860`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180008414`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x18001f5c4`
- `0x18001fd1c`
- `0x18002c418`
- `0x18002efc0`
- `0x18002f230`
- `0x180041d38`
- `0x180041da8`
- `0x18004b318`
- `0x18004bec0`
- `0x180190e70`

## import_xrefs

- `ntdll!NtAccessCheck` at `0x1800200db`
- `ntdll!NtAccessCheck` at `0x1800200db`
- `ntdll!RtlMapGenericMask` at `0x180020040`
- `ntdll!RtlMapGenericMask` at `0x18002007f`
- `ntdll!RtlMapGenericMask` at `0x180020040`
- `ntdll!RtlMapGenericMask` at `0x18002007f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ffca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800201a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800201fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ffca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800201a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800201fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ffad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002018d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800201e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ffad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002018d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800201e3`

## string_xrefs

- `0x18001fd57`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001fda4`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001fe55`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001fecf`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001ff90`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001fff0`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x1800200f7`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180020153`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OpenContainer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        Container::Manager::Service::ContainerRpcContextHandle **a5)
{
  unsigned int v5; // ebx
  bool v7; // zf
  __int64 v8; // rdx
  Container::Manager::Core::ContainerHandle *v9; // rdi
  int Container; // eax
  int v11; // eax
  unsigned int v12; // edi
  Container::Manager::Core::ContainerHandle *v13; // rbx
  char *v14; // rdi
  int UserSidFromToken; // esi
  bool *v16; // r8
  __int64 v17; // rdx
  Container::Manager::Core::ContainerHandle *v18; // rbx
  void *v19; // rdx
  bool *v20; // r9
  char v21; // r14
  DWORD v22; // eax
  int v23; // eax
  bool v24; // cc
  __int64 v25; // r9
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // r9
  NTSTATUS v29; // eax
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  HLOCAL v32; // rbx
  int v33; // eax
  unsigned int v34; // r14d
  Container::Manager::Core::ContainerHandle *v35; // rsi
  Container::Manager::Service::ContainerRpcContextHandle *v36; // rsi
  unsigned int PrivilegeSet; // [rsp+20h] [rbp-61h]
  int v38; // [rsp+40h] [rbp-41h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-39h] BYREF
  ULONG ReturnLength[2]; // [rsp+50h] [rbp-31h] BYREF
  DWORD AccessMask; // [rsp+58h] [rbp-29h] BYREF
  DWORD DesiredAccess; // [rsp+60h] [rbp-21h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-19h] BYREF
  struct _PRIVILEGE_SET v44; // [rsp+70h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  DesiredAccess = a4;
  if ( !a4 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)0x80070057LL,
      PrivilegeSet);
    return v5;
  }
  v7 = *(_BYTE *)(a1 + 16) == 0;
  *(_QWORD *)ReturnLength = 0;
  if ( v7 )
  {
    if ( !BYTE4(a2) )
      __int2c();
    LODWORD(hMem) = a2;
    BYTE4(hMem) = 1;
    memset(&v44, 0, sizeof(v44));
    Container = Container::Manager::Core::FindContainer(&v44, hMem, a3, ReturnLength);
    v5 = Container;
    if ( Container < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x511,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\core.cpp",
        (const char *)(unsigned int)Container,
        PrivilegeSet);
      v8 = 525;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)v5,
        PrivilegeSet);
      v9 = *(Container::Manager::Core::ContainerHandle **)ReturnLength;
      if ( *(_QWORD *)ReturnLength )
      {
        Container::Manager::Core::ContainerHandle::~ContainerHandle(*(Container::Manager::Core::ContainerHandle **)ReturnLength);
        operator delete(v9, (const struct std::nothrow_t *)0x58);
      }
      return v5;
    }
  }
  else
  {
    v5 = Container::Manager::Core::FindContainer(a1, (unsigned int)a3, ReturnLength);
    if ( (v5 & 0x80000000) != 0 )
    {
      v8 = 517;
      goto LABEL_7;
    }
  }
  hObject = 0;
  v11 = Container::Manager::Rpc::OpenRpcClientAccessToken(8, &hObject);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)(unsigned int)v11,
      PrivilegeSet);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v13 = *(Container::Manager::Core::ContainerHandle **)ReturnLength;
    if ( *(_QWORD *)ReturnLength )
    {
      Container::Manager::Core::ContainerHandle::~ContainerHandle(*(Container::Manager::Core::ContainerHandle **)ReturnLength);
      operator delete(v13, (const struct std::nothrow_t *)0x58);
    }
    return v12;
  }
  v14 = (char *)hObject;
  hMem = 0;
  UserSidFromToken = Csl::GetUserSidFromToken(hObject, &hMem);
  if ( UserSidFromToken < 0 )
  {
    v17 = 535;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)(unsigned int)UserSidFromToken,
      PrivilegeSet);
    if ( hMem )
      LocalFree(hMem);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v14);
    v18 = *(Container::Manager::Core::ContainerHandle **)ReturnLength;
LABEL_26:
    if ( v18 )
    {
      Container::Manager::Core::ContainerHandle::~ContainerHandle(v18);
      operator delete(v18, (const struct std::nothrow_t *)0x58);
    }
    return (unsigned int)UserSidFromToken;
  }
  LOBYTE(v38) = 0;
  UserSidFromToken = Csl::IsAdminOrSystem(v14, &v38, v16);
  if ( UserSidFromToken < 0 )
  {
    v17 = 540;
    goto LABEL_21;
  }
  v21 = v38;
  v18 = *(Container::Manager::Core::ContainerHandle **)ReturnLength;
  AccessMask = 0;
  if ( !(_BYTE)v38 )
  {
    RtlMapGenericMask(&DesiredAccess, (PGENERIC_MAPPING)&stru_1801D0FC0);
    ReturnLength[0] = 20;
    LODWORD(hObject) = 0;
    memset(&v44, 0, sizeof(v44));
    v29 = NtAccessCheck(
            *(PSECURITY_DESCRIPTOR *)(*((_QWORD *)v18 + 1) + 80LL),
            v14,
            DesiredAccess,
            (PGENERIC_MAPPING)&stru_1801D0FC0,
            &v44,
            ReturnLength,
            &AccessMask,
            (PNTSTATUS)&hObject);
    if ( v29 >= 0 )
    {
      v30 = (unsigned int)hObject;
      if ( (int)hObject >= 0 )
        goto LABEL_49;
      v31 = 600;
    }
    else
    {
      v30 = (unsigned int)v29;
      v31 = 598;
    }
    v27 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v31,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
            (const char *)v30,
            PrivilegeSet);
    goto LABEL_42;
  }
  v22 = DesiredAccess;
  if ( (DesiredAccess & 0x1000000) != 0 )
  {
    LOBYTE(v38) = 0;
    v23 = Csl::SinglePrivilegeCheck((Csl *)v14, v19, (int)&v38, v20);
    UserSidFromToken = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x231,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v23,
        PrivilegeSet);
      if ( hMem )
        LocalFree(hMem);
      v24 = (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_37:
      if ( v24 )
        CloseHandle(v14);
      goto LABEL_26;
    }
    if ( !(_BYTE)v38 )
    {
      v25 = 1314;
      v26 = 565;
LABEL_41:
      v27 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v26,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
              (const char *)v25,
              PrivilegeSet);
LABEL_42:
      UserSidFromToken = v27;
      if ( hMem )
        LocalFree(hMem);
      v24 = (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_37;
    }
    v22 = DesiredAccess;
  }
  AccessMask = v22;
  if ( (v22 & 0x2000000) != 0 )
    AccessMask = v22 & 0xFDF0FF00 | 0xF00FF;
  RtlMapGenericMask(&AccessMask, (PGENERIC_MAPPING)&stru_1801D0FC0);
LABEL_49:
  if ( (unsigned int)Container::Manager::Core::ContainerHandle::GetContainerType(v18) == 2 && !v21 )
  {
    v25 = 5;
    v26 = 612;
    goto LABEL_41;
  }
  hObject = v18;
  v32 = hMem;
  LOBYTE(v28) = v21;
  *(_QWORD *)ReturnLength = 0;
  v33 = CreateContainerRpcContextHandle(&hObject, hMem, AccessMask, v28);
  v34 = v33;
  if ( v33 >= 0 )
  {
    v36 = *a5;
    *a5 = *(Container::Manager::Service::ContainerRpcContextHandle **)ReturnLength;
    if ( v36 )
    {
      Container::Manager::Service::ContainerRpcContextHandle::~ContainerRpcContextHandle(v36);
      operator delete(v36, (const struct std::nothrow_t *)0x18);
    }
    if ( v32 )
      LocalFree(v32);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)(unsigned int)v33,
      (int)ReturnLength);
    v35 = *(Container::Manager::Core::ContainerHandle **)ReturnLength;
    if ( *(_QWORD *)ReturnLength )
    {
      Container::Manager::Service::ContainerRpcContextHandle::~ContainerRpcContextHandle(*(Container::Manager::Service::ContainerRpcContextHandle **)ReturnLength);
      operator delete(v35, (const struct std::nothrow_t *)0x18);
    }
    if ( v32 )
      LocalFree(v32);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v14);
    return v34;
  }
}

```

## disassembly

```asm
0x18001fd1c  mov     [rsp-8+arg_8], rdx
0x18001fd21  push    rbp
0x18001fd22  push    rbx
0x18001fd23  push    rsi
0x18001fd24  push    rdi
0x18001fd25  push    r14
0x18001fd27  push    r15
0x18001fd29  lea     rbp, [rsp-27h]
0x18001fd2e  sub     rsp, 0A8h
0x18001fd35  mov     rax, cs:__security_cookie
0x18001fd3c  xor     rax, rsp
0x18001fd3f  mov     [rbp+4Fh+var_40], rax
0x18001fd43  mov     r15, [rbp+4Fh+arg_20]
0x18001fd47  mov     r10d, r8d
0x18001fd4a  mov     [rbp+4Fh+DesiredAccess], r9d
0x18001fd4e  test    r9d, r9d
0x18001fd51  jnz     short loc_18001FD77
0x18001fd53  mov     rcx, [rbp+57h]; this
0x18001fd57  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001fd5e  mov     ebx, 80070057h
0x18001fd63  mov     edx, 1FBh; void *
0x18001fd68  mov     r9d, ebx; char *
0x18001fd6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd70  mov     eax, ebx
0x18001fd72  jmp     loc_18002020A
0x18001fd77  cmp     byte ptr [rcx+10h], 0
0x18001fd7b  mov     qword ptr [rbp+4Fh+var_80], 0
0x18001fd83  jz      short loc_18001FDD3
0x18001fd85  lea     r8, [rbp+4Fh+var_80]
0x18001fd89  mov     edx, r10d
0x18001fd8c  call    ?FindContainer@Core@Manager@Container@@YAJAEBU_GUID@@W4_CMS_CLIENT_ID@@AEAV?$unique_ptr@VContainerHandle@Core@Manager@Container@@U?$default_delete@VContainerHandle@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::FindContainer(_GUID const &,_CMS_CLIENT_ID,wistd::unique_ptr<Container::Manager::Core::ContainerHandle,wistd::default_delete<Container::Manager::Core::ContainerHandle>> &)
0x18001fd91  mov     ebx, eax
0x18001fd93  test    eax, eax
0x18001fd95  jns     loc_18001FE35
0x18001fd9b  mov     edx, 205h; void *
0x18001fda0  mov     rcx, [rbp+57h]; this
0x18001fda4  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001fdab  mov     r9d, ebx; char *
0x18001fdae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdb3  mov     rdi, qword ptr [rbp+4Fh+var_80]
0x18001fdb7  test    rdi, rdi
0x18001fdba  jz      short loc_18001FD70
0x18001fdbc  mov     rcx, rdi; this
0x18001fdbf  call    ??1ContainerHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ContainerHandle::~ContainerHandle(void)
0x18001fdc4  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18001fdc9  mov     rcx, rdi; void *
0x18001fdcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fdd1  jmp     short loc_18001FD70
0x18001fdd3  cmp     byte ptr [rbp+4Fh+arg_8+4], 0
0x18001fdd7  jnz     short loc_18001FDDB
0x18001fdd9  int     2Ch; Windows NT - assertion failure
0x18001fddb  movzx   eax, word ptr [rbp+4Fh+hMem+5]
0x18001fddf  lea     r9, [rbp+4Fh+var_80]
0x18001fde3  mov     word ptr [rbp+4Fh+hMem+5], ax
0x18001fde7  lea     rcx, [rbp+4Fh+var_60]
0x18001fdeb  mov     al, byte ptr [rbp+4Fh+hMem+7]
0x18001fdee  xorps   xmm0, xmm0
0x18001fdf1  mov     byte ptr [rbp+4Fh+hMem+7], al
0x18001fdf4  xor     eax, eax
0x18001fdf6  mov     dword ptr [rbp+4Fh+hMem], edx
0x18001fdf9  mov     byte ptr [rbp+4Fh+hMem+4], 1
0x18001fdfd  mov     rdx, [rbp+4Fh+hMem]
0x18001fe01  mov     [rbp+4Fh+var_60.Privilege.Attributes], eax
0x18001fe04  movaps  xmmword ptr [rbp+4Fh+var_60.PrivilegeCount], xmm0
0x18001fe08  call    ?FindContainer@Core@Manager@Container@@YAJV?$optional@U_GUID@@@utl@@V?$optional@K@5@W4_CMS_CLIENT_ID@@AEAV?$unique_ptr@VContainerHandle@Core@Manager@Container@@U?$default_delete@VContainerHandle@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::FindContainer(utl::optional<_GUID>,utl::optional<ulong>,_CMS_CLIENT_ID,wistd::unique_ptr<Container::Manager::Core::ContainerHandle,wistd::default_delete<Container::Manager::Core::ContainerHandle>> &)
0x18001fe0d  mov     ebx, eax
0x18001fe0f  test    eax, eax
0x18001fe11  jns     short loc_18001FE35
0x18001fe13  mov     rcx, [rbp+57h]; this
0x18001fe17  lea     r8, aOnecoreBaseGen_9; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001fe1e  mov     r9d, eax; char *
0x18001fe21  mov     edx, 511h; void *
0x18001fe26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe2b  mov     edx, 20Dh
0x18001fe30  jmp     loc_18001FDA0
0x18001fe35  lea     rdx, [rbp+4Fh+hObject]
0x18001fe39  mov     [rbp+4Fh+hObject], 0
0x18001fe41  mov     ecx, 8
0x18001fe46  call    ?OpenRpcClientAccessToken@Rpc@Manager@Container@@YAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::OpenRpcClientAccessToken(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001fe4b  mov     edi, eax
0x18001fe4d  test    eax, eax
0x18001fe4f  jns     short loc_18001FEA8
0x18001fe51  mov     rcx, [rbp+57h]; this
0x18001fe55  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001fe5c  mov     r9d, eax; char *
0x18001fe5f  mov     edx, 213h; void *
0x18001fe64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe69  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18001fe6d  lea     rdx, [rcx-1]
0x18001fe71  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001fe75  ja      short loc_18001FE83
0x18001fe77  call    cs:__imp_CloseHandle
0x18001fe7e  nop     dword ptr [rax+rax+00h]
0x18001fe83  mov     rbx, qword ptr [rbp+4Fh+var_80]
0x18001fe87  test    rbx, rbx
0x18001fe8a  jz      short loc_18001FEA1
0x18001fe8c  mov     rcx, rbx; this
0x18001fe8f  call    ??1ContainerHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ContainerHandle::~ContainerHandle(void)
0x18001fe94  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18001fe99  mov     rcx, rbx; void *
0x18001fe9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fea1  mov     eax, edi
0x18001fea3  jmp     loc_18002020A
0x18001fea8  mov     rdi, [rbp+4Fh+hObject]
0x18001feac  lea     rdx, [rbp+4Fh+hMem]
0x18001feb0  mov     rcx, rdi
0x18001feb3  mov     [rbp+4Fh+hMem], 0
0x18001febb  call    ?GetUserSidFromToken@Csl@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Csl::GetUserSidFromToken(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18001fec0  mov     esi, eax
0x18001fec2  test    eax, eax
0x18001fec4  jns     short loc_18001FF31
0x18001fec6  mov     edx, 217h; void *
0x18001fecb  mov     rcx, [rbp+57h]; this
0x18001fecf  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001fed6  mov     r9d, esi; char *
0x18001fed9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fede  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18001fee2  test    rcx, rcx
0x18001fee5  jz      short loc_18001FEF3
0x18001fee7  call    cs:__imp_LocalFree
0x18001feee  nop     dword ptr [rax+rax+00h]
0x18001fef3  lea     rax, [rdi-1]
0x18001fef7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001fefb  ja      short loc_18001FF0C
0x18001fefd  mov     rcx, rdi; hObject
0x18001ff00  call    cs:__imp_CloseHandle
0x18001ff07  nop     dword ptr [rax+rax+00h]
0x18001ff0c  mov     rbx, qword ptr [rbp+4Fh+var_80]
0x18001ff10  test    rbx, rbx
0x18001ff13  jz      short loc_18001FF2A
0x18001ff15  mov     rcx, rbx; this
0x18001ff18  call    ??1ContainerHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ContainerHandle::~ContainerHandle(void)
0x18001ff1d  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18001ff22  mov     rcx, rbx; void *
0x18001ff25  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ff2a  mov     eax, esi
0x18001ff2c  jmp     loc_18002020A
0x18001ff31  lea     rdx, [rbp+4Fh+var_90]; void *
0x18001ff35  mov     byte ptr [rbp+4Fh+var_90], 0
0x18001ff39  mov     rcx, rdi; TokenHandle
0x18001ff3c  call    ?IsAdminOrSystem@Csl@@YAJPEAXAEA_N@Z; Csl::IsAdminOrSystem(void *,bool &)
0x18001ff41  mov     esi, eax
0x18001ff43  test    eax, eax
0x18001ff45  jns     short loc_18001FF51
0x18001ff47  mov     edx, 21Ch
0x18001ff4c  jmp     loc_18001FECB
0x18001ff51  mov     r14b, byte ptr [rbp+4Fh+var_90]
0x18001ff55  mov     rbx, qword ptr [rbp+4Fh+var_80]
0x18001ff59  mov     [rbp+4Fh+AccessMask], 0
0x18001ff60  test    r14b, r14b
0x18001ff63  jz      loc_180020074
0x18001ff69  mov     eax, [rbp+4Fh+DesiredAccess]
0x18001ff6c  bt      eax, 18h
0x18001ff70  jnb     loc_180020020
0x18001ff76  lea     r8, [rbp+4Fh+var_90]; int
0x18001ff7a  mov     byte ptr [rbp+4Fh+var_90], 0
0x18001ff7e  mov     rcx, rdi; this
0x18001ff81  call    ?SinglePrivilegeCheck@Csl@@YAJPEAXJAEA_N@Z; Csl::SinglePrivilegeCheck(void *,long,bool &)
0x18001ff86  mov     esi, eax
0x18001ff88  test    eax, eax
0x18001ff8a  jns     short loc_18001FFDB
0x18001ff8c  mov     rcx, [rbp+57h]; this
0x18001ff90  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001ff97  mov     r9d, eax; char *
0x18001ff9a  mov     edx, 231h; void *
0x18001ff9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffa4  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18001ffa8  test    rcx, rcx
0x18001ffab  jz      short loc_18001FFB9
0x18001ffad  call    cs:__imp_LocalFree
0x18001ffb4  nop     dword ptr [rax+rax+00h]
0x18001ffb9  lea     rax, [rdi-1]
0x18001ffbd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ffc1  ja      loc_18001FF10
0x18001ffc7  mov     rcx, rdi; hObject
0x18001ffca  call    cs:__imp_CloseHandle
0x18001ffd1  nop     dword ptr [rax+rax+00h]
0x18001ffd6  jmp     loc_18001FF10
0x18001ffdb  cmp     byte ptr [rbp+4Fh+var_90], 0
0x18001ffdf  jnz     short loc_18002001D
0x18001ffe1  mov     r9d, 522h; char *
0x18001ffe7  mov     edx, 235h; void *
0x18001ffec  mov     rcx, [rbp+57h]; this
0x18001fff0  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001fff7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001fffc  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180020000  mov     esi, eax
0x180020002  test    rcx, rcx
0x180020005  jz      short loc_180020013
0x180020007  call    cs:__imp_LocalFree
0x18002000e  nop     dword ptr [rax+rax+00h]
0x180020013  lea     rcx, [rdi-1]
0x180020017  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002001b  jmp     short loc_18001FFC1
0x18002001d  mov     eax, [rbp+4Fh+DesiredAccess]
0x180020020  mov     [rbp+4Fh+AccessMask], eax
0x180020023  bt      eax, 19h
0x180020027  jnb     short loc_180020035
0x180020029  btr     eax, 19h
0x18002002d  or      eax, 0F00FFh
0x180020032  mov     [rbp+4Fh+AccessMask], eax
0x180020035  lea     rdx, stru_1801D0FC0; GenericMapping
0x18002003c  lea     rcx, [rbp+4Fh+AccessMask]; AccessMask
0x180020040  call    cs:__imp_RtlMapGenericMask
0x180020047  nop     dword ptr [rax+rax+00h]
0x18002004c  mov     rcx, rbx
0x18002004f  call    ?GetContainerType@ContainerHandle@Core@Manager@Container@@QEBA?AW4_CMS_CONTAINER_TYPE@@XZ; Container::Manager::Core::ContainerHandle::GetContainerType(void)
0x180020054  cmp     eax, 2
0x180020057  jnz     loc_18002011C
0x18002005d  test    r14b, r14b
0x180020060  jnz     loc_18002011C
0x180020066  lea     r9d, [rax+3]
0x18002006a  mov     edx, 264h
0x18002006f  jmp     loc_18001FFEC
0x180020074  lea     rdx, stru_1801D0FC0; GenericMapping
0x18002007b  lea     rcx, [rbp+4Fh+DesiredAccess]; AccessMask
0x18002007f  call    cs:__imp_RtlMapGenericMask
0x180020086  nop     dword ptr [rax+rax+00h]
0x18002008b  mov     r8d, [rbp+4Fh+DesiredAccess]; DesiredAccess
0x18002008f  lea     r9, stru_1801D0FC0; GenericMapping
0x180020096  xor     eax, eax
0x180020098  mov     [rbp+4Fh+var_80], 14h
0x18002009f  mov     [rbp+4Fh+var_60.Privilege.Attributes], eax
0x1800200a2  xorps   xmm0, xmm0
0x1800200a5  mov     dword ptr [rbp+4Fh+hObject], eax
0x1800200a8  mov     rdx, rdi; ClientToken
0x1800200ab  movups  xmmword ptr [rbp+4Fh+var_60.PrivilegeCount], xmm0
0x1800200af  mov     rcx, [rbx+8]
0x1800200b3  lea     rax, [rbp+4Fh+hObject]
0x1800200b7  mov     [rsp+0D0h+AccessStatus], rax; AccessStatus
0x1800200bc  lea     rax, [rbp+4Fh+AccessMask]
0x1800200c0  mov     [rsp+0D0h+GrantedAccess], rax; GrantedAccess
0x1800200c5  lea     rax, [rbp+4Fh+var_80]
0x1800200c9  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800200ce  lea     rax, [rbp+4Fh+var_60]
0x1800200d2  mov     rcx, [rcx+50h]; SecurityDescriptor
0x1800200d6  mov     [rsp+0D0h+PrivilegeSet], rax; int
0x1800200db  call    cs:__imp_NtAccessCheck
0x1800200e2  nop     dword ptr [rax+rax+00h]
0x1800200e7  test    eax, eax
0x1800200e9  jns     short loc_180020108
0x1800200eb  mov     r9d, eax; char *
0x1800200ee  mov     edx, 256h; void *
0x1800200f3  mov     rcx, [rbp+57h]; this
0x1800200f7  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x1800200fe  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180020103  jmp     loc_18001FFFC
0x180020108  mov     r9d, dword ptr [rbp+4Fh+hObject]
0x18002010c  test    r9d, r9d
0x18002010f  jns     loc_18002004C
0x180020115  mov     edx, 258h
0x18002011a  jmp     short loc_1800200F3
0x18002011c  mov     r8d, [rbp+4Fh+AccessMask]
0x180020120  lea     rax, [rbp+4Fh+var_80]
0x180020124  mov     [rbp+4Fh+hObject], rbx
0x180020128  lea     rcx, [rbp+4Fh+hObject]
0x18002012c  mov     rbx, [rbp+4Fh+hMem]
0x180020130  mov     r9b, r14b
0x180020133  mov     rdx, rbx
0x180020136  mov     qword ptr [rbp+4Fh+var_80], 0
0x18002013e  mov     [rsp+0D0h+PrivilegeSet], rax; int
0x180020143  call    CreateContainerRpcContextHandle
0x180020148  mov     r14d, eax
0x18002014b  test    eax, eax
0x18002014d  jns     short loc_1800201B7
0x18002014f  mov     rcx, [rbp+57h]; this
0x180020153  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18002015a  mov     r9d, eax; char *
0x18002015d  mov     edx, 26Dh; void *
0x180020162  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020167  mov     rsi, qword ptr [rbp+4Fh+var_80]
0x18002016b  test    rsi, rsi
0x18002016e  jz      short loc_180020185
0x180020170  mov     rcx, rsi; this
0x180020173  call    ??1ContainerRpcContextHandle@Service@Manager@Container@@QEAA@XZ; Container::Manager::Service::ContainerRpcContextHandle::~ContainerRpcContextHandle(void)
0x180020178  mov     edx, 18h; struct std::nothrow_t *
0x18002017d  mov     rcx, rsi; void *
0x180020180  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020185  test    rbx, rbx
0x180020188  jz      short loc_180020199
0x18002018a  mov     rcx, rbx; hMem
0x18002018d  call    cs:__imp_LocalFree
0x180020194  nop     dword ptr [rax+rax+00h]
0x180020199  lea     rax, [rdi-1]
0x18002019d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800201a1  ja      short loc_1800201B2
0x1800201a3  mov     rcx, rdi; hObject
0x1800201a6  call    cs:__imp_CloseHandle
0x1800201ad  nop     dword ptr [rax+rax+00h]
0x1800201b2  mov     eax, r14d
0x1800201b5  jmp     short loc_18002020A
0x1800201b7  mov     rsi, [r15]
0x1800201ba  mov     rax, qword ptr [rbp+4Fh+var_80]
0x1800201be  mov     [r15], rax
0x1800201c1  test    rsi, rsi
0x1800201c4  jz      short loc_1800201DB
0x1800201c6  mov     rcx, rsi; this
0x1800201c9  call    ??1ContainerRpcContextHandle@Service@Manager@Container@@QEAA@XZ; Container::Manager::Service::ContainerRpcContextHandle::~ContainerRpcContextHandle(void)
0x1800201ce  mov     edx, 18h; struct std::nothrow_t *
0x1800201d3  mov     rcx, rsi; void *
  ... truncated ...
```
