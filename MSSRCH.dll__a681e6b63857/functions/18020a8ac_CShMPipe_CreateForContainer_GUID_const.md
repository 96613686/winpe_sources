# CShMPipe::CreateForContainer(_GUID const &)

- ea: `0x18020a8ac`
- end: `0x18020abe9`
- name: `?CreateForContainer@CShMPipe@@QEAAJAEBU_GUID@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(CShMPipe *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18019ea80`

## callees

- `0x18000f880`
- `0x18004b638`
- `0x180109038`
- `0x18012540e`
- `0x18020a8ac`
- `0x1802202c4`

## import_xrefs

- `ntdll!NtMapViewOfSection` at `0x18020a9da`
- `ntdll!NtMapViewOfSection` at `0x18020a9da`
- `ntdll!NtCreateCrossVmEvent` at `0x18020aa64`
- `ntdll!NtCreateCrossVmEvent` at `0x18020aab7`
- `ntdll!NtCreateCrossVmEvent` at `0x18020ab0a`
- `ntdll!NtCreateCrossVmEvent` at `0x18020ab5d`
- `ntdll!NtCreateCrossVmEvent` at `0x18020abb0`
- `ntdll!NtCreateCrossVmEvent` at `0x18020aa64`
- `ntdll!NtCreateCrossVmEvent` at `0x18020aab7`
- `ntdll!NtCreateCrossVmEvent` at `0x18020ab0a`
- `ntdll!NtCreateCrossVmEvent` at `0x18020ab5d`
- `ntdll!NtCreateCrossVmEvent` at `0x18020abb0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020a8d7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020aa29`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020aa82`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020aad5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020ab28`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020ab7b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020a8d7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020aa29`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020aa82`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020aad5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020ab28`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18020ab7b`

## string_xrefs

- `0x18020a8ed`: `onecoreuap\base\appmodel\search\common\pkmutild\shmpipe.cxx`
- `0x18020a942`: `onecoreuap\base\appmodel\search\common\pkmutild\shmpipe.cxx`
- `0x18020a96a`: `onecoreuap\base\appmodel\search\common\pkmutild\shmpipe.cxx`

## pseudocode

```c
int __fastcall CShMPipe::CreateForContainer(CShMPipe *this, const struct _GUID *a2)
{
  char *v2; // rsi
  char *v4; // rbp
  HRESULT Guid; // edi
  __int64 v6; // rdx
  void **v8; // rax
  NTSTATUS VmSharedMemorySection2; // eax
  __int64 v10; // rdx
  void *v11; // rcx
  void **v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int CommitSize; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  ULONG_PTR ViewSize; // [rsp+88h] [rbp+10h] BYREF

  v2 = (char *)this + 360;
  v4 = (char *)this + 248;
  *(struct _GUID *)((char *)this + 360) = *a2;
  Guid = CoCreateGuid((GUID *)((char *)this + 248));
  if ( Guid < 0 )
  {
    v6 = 394;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
      (const char *)(unsigned int)Guid,
      CommitSize);
    return Guid;
  }
  v8 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 72);
  VmSharedMemorySection2 = CreateVmSharedMemorySection2(v8, CommitSize, (__int64)v4, (__int64)v2);
  if ( VmSharedMemorySection2 < 0 )
  {
    v10 = 405;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v10,
             (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
             (const char *)(unsigned int)VmSharedMemorySection2,
             CommitSize);
  }
  v11 = (void *)*((_QWORD *)this + 9);
  v12 = (void **)((char *)this + 80);
  ViewSize = 0;
  VmSharedMemorySection2 = NtMapViewOfSection(
                             v11,
                             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                             (PVOID *)this + 10,
                             0,
                             0,
                             0,
                             &ViewSize,
                             ViewUnmap,
                             0,
                             4u);
  if ( VmSharedMemorySection2 < 0 )
  {
    v10 = 411;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v10,
             (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
             (const char *)(unsigned int)VmSharedMemorySection2,
             CommitSize);
  }
  if ( ViewSize == 0x10000 )
  {
    memset_0(*v12, 0, 0x98u);
    *((_DWORD *)*v12 + 32) = 65384;
    Guid = CoCreateGuid((GUID *)((char *)this + 264));
    if ( Guid < 0 )
    {
      v6 = 419;
      goto LABEL_3;
    }
    v13 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 88);
    CommitSize = (_DWORD)this + 264;
    VmSharedMemorySection2 = NtCreateCrossVmEvent(v13, 2031619, 0, 0);
    if ( VmSharedMemorySection2 < 0 )
    {
      v10 = 421;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v10,
               (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
               (const char *)(unsigned int)VmSharedMemorySection2,
               CommitSize);
    }
    Guid = CoCreateGuid((GUID *)((char *)this + 280));
    if ( Guid < 0 )
    {
      v6 = 423;
      goto LABEL_3;
    }
    v14 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 96);
    CommitSize = (_DWORD)this + 280;
    VmSharedMemorySection2 = NtCreateCrossVmEvent(v14, 2031619, 0, 0);
    if ( VmSharedMemorySection2 < 0 )
    {
      v10 = 425;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v10,
               (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
               (const char *)(unsigned int)VmSharedMemorySection2,
               CommitSize);
    }
    Guid = CoCreateGuid((GUID *)((char *)this + 296));
    if ( Guid < 0 )
    {
      v6 = 427;
      goto LABEL_3;
    }
    v15 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 104);
    CommitSize = (_DWORD)this + 296;
    VmSharedMemorySection2 = NtCreateCrossVmEvent(v15, 2031619, 0, 0);
    if ( VmSharedMemorySection2 < 0 )
    {
      v10 = 429;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v10,
               (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
               (const char *)(unsigned int)VmSharedMemorySection2,
               CommitSize);
    }
    Guid = CoCreateGuid((GUID *)((char *)this + 312));
    if ( Guid < 0 )
    {
      v6 = 431;
      goto LABEL_3;
    }
    v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 112);
    CommitSize = (_DWORD)this + 312;
    VmSharedMemorySection2 = NtCreateCrossVmEvent(v16, 2031619, 0, 0);
    if ( VmSharedMemorySection2 < 0 )
    {
      v10 = 433;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v10,
               (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
               (const char *)(unsigned int)VmSharedMemorySection2,
               CommitSize);
    }
    Guid = CoCreateGuid((GUID *)((char *)this + 328));
    if ( Guid < 0 )
    {
      v6 = 435;
      goto LABEL_3;
    }
    v17 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 120);
    CommitSize = (_DWORD)this + 328;
    VmSharedMemorySection2 = NtCreateCrossVmEvent(v17, 2031619, 0, 0);
    if ( VmSharedMemorySection2 < 0 )
    {
      v10 = 437;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v10,
               (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
               (const char *)(unsigned int)VmSharedMemorySection2,
               CommitSize);
    }
    *((_BYTE *)this + 376) = 1;
    *((_WORD *)this + 4) = 1;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
      (const char *)0x80004005LL,
      CommitSize);
    return -2147467259;
  }
}

```

## disassembly

```asm
0x18020a8ac  mov     [rsp+arg_10], rbx
0x18020a8b1  push    rbp
0x18020a8b2  push    rsi
0x18020a8b3  push    rdi
0x18020a8b4  push    r12
0x18020a8b6  push    r14
0x18020a8b8  sub     rsp, 50h
0x18020a8bc  movups  xmm0, xmmword ptr [rdx]
0x18020a8bf  lea     rsi, [rcx+168h]
0x18020a8c6  mov     rbx, rcx
0x18020a8c9  lea     rbp, [rcx+0F8h]
0x18020a8d0  mov     rcx, rbp; pguid
0x18020a8d3  movdqu  xmmword ptr [rsi], xmm0
0x18020a8d7  call    cs:__imp_CoCreateGuid
0x18020a8dd  mov     edi, eax
0x18020a8df  test    eax, eax
0x18020a8e1  jns     short loc_18020A903
0x18020a8e3  mov     edx, 18Ah; void *
0x18020a8e8  mov     rcx, [rsp+78h]; this
0x18020a8ed  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\search\\com"...
0x18020a8f4  mov     r9d, edi; char *
0x18020a8f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020a8fc  mov     eax, edi
0x18020a8fe  jmp     loc_18020ABD5
0x18020a903  mov     r12d, 10000h
0x18020a909  lea     rcx, [rbx+48h]
0x18020a90d  mov     [rsp+78h+arg_0], r12
0x18020a915  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18020a91a  lea     r9, [rsp+78h+arg_0]
0x18020a922  mov     [rsp+78h+ViewSize], rsi; __int64
0x18020a927  mov     rcx, rax; SectionHandle
0x18020a92a  mov     [rsp+78h+SectionOffset], rbp; __int64
0x18020a92f  call    CreateVmSharedMemorySection2
0x18020a934  test    eax, eax
0x18020a936  jns     short loc_18020A956
0x18020a938  mov     edx, 195h; void *
0x18020a93d  mov     rcx, [rsp+78h]; this
0x18020a942  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\search\\com"...
0x18020a949  mov     r9d, eax; char *
0x18020a94c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18020a951  jmp     loc_18020ABD5
0x18020a956  cmp     dword ptr [rsp+78h+arg_0], r12d
0x18020a95e  jz      short loc_18020A985
0x18020a960  mov     edx, 197h; void *
0x18020a965  mov     rcx, [rsp+78h]; this
0x18020a96a  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\search\\com"...
0x18020a971  mov     ebx, 80004005h
0x18020a976  mov     r9d, ebx; char *
0x18020a979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020a97e  mov     eax, ebx
0x18020a980  jmp     loc_18020ABD5
0x18020a985  mov     rcx, [rbx+48h]; SectionHandle
0x18020a989  lea     rax, [rsp+78h+arg_8]
0x18020a991  mov     [rsp+78h+AccessProtection], 4; AccessProtection
0x18020a999  lea     rdi, [rbx+50h]
0x18020a99d  mov     [rsp+78h+AllocationType], 0; AllocationType
0x18020a9a5  xor     r9d, r9d; ZeroBits
0x18020a9a8  mov     [rsp+78h+InheritDisposition], 2; InheritDisposition
0x18020a9b0  mov     r8, rdi; BaseAddress
0x18020a9b3  mov     [rsp+78h+ViewSize], rax; ViewSize
0x18020a9b8  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18020a9bc  mov     [rsp+78h+SectionOffset], 0; SectionOffset
0x18020a9c5  mov     [rsp+78h+CommitSize], 0; CommitSize
0x18020a9ce  mov     [rsp+78h+arg_8], 0
0x18020a9da  call    cs:__imp_NtMapViewOfSection
0x18020a9e0  test    eax, eax
0x18020a9e2  jns     short loc_18020A9EE
0x18020a9e4  mov     edx, 19Bh
0x18020a9e9  jmp     loc_18020A93D
0x18020a9ee  cmp     [rsp+78h+arg_8], r12
0x18020a9f6  jz      short loc_18020AA02
0x18020a9f8  mov     edx, 19Dh
0x18020a9fd  jmp     loc_18020A965
0x18020aa02  mov     rcx, [rdi]; void *
0x18020aa05  xor     edx, edx; Val
0x18020aa07  mov     r8d, 98h; Size
0x18020aa0d  call    memset_0
0x18020aa12  mov     rax, [rdi]
0x18020aa15  lea     rbp, [rbx+108h]
0x18020aa1c  mov     rcx, rbp; pguid
0x18020aa1f  mov     dword ptr [rax+80h], 0FF68h
0x18020aa29  call    cs:__imp_CoCreateGuid
0x18020aa2f  mov     edi, eax
0x18020aa31  test    eax, eax
0x18020aa33  jns     short loc_18020AA3F
0x18020aa35  mov     edx, 1A3h
0x18020aa3a  jmp     loc_18020A8E8
0x18020aa3f  lea     rcx, [rbx+58h]
0x18020aa43  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18020aa48  mov     r14d, 1F0003h
0x18020aa4e  mov     [rsp+78h+SectionOffset], rsi
0x18020aa53  mov     edx, r14d
0x18020aa56  mov     [rsp+78h+CommitSize], rbp
0x18020aa5b  xor     r9d, r9d
0x18020aa5e  xor     r8d, r8d
0x18020aa61  mov     rcx, rax
0x18020aa64  call    cs:__imp_NtCreateCrossVmEvent
0x18020aa6a  test    eax, eax
0x18020aa6c  jns     short loc_18020AA78
0x18020aa6e  mov     edx, 1A5h
0x18020aa73  jmp     loc_18020A93D
0x18020aa78  lea     rbp, [rbx+118h]
0x18020aa7f  mov     rcx, rbp; pguid
0x18020aa82  call    cs:__imp_CoCreateGuid
0x18020aa88  mov     edi, eax
0x18020aa8a  test    eax, eax
0x18020aa8c  jns     short loc_18020AA98
0x18020aa8e  mov     edx, 1A7h
0x18020aa93  jmp     loc_18020A8E8
0x18020aa98  lea     rcx, [rbx+60h]
0x18020aa9c  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18020aaa1  xor     r9d, r9d
0x18020aaa4  mov     [rsp+78h+SectionOffset], rsi
0x18020aaa9  xor     r8d, r8d
0x18020aaac  mov     [rsp+78h+CommitSize], rbp
0x18020aab1  mov     edx, r14d
0x18020aab4  mov     rcx, rax
0x18020aab7  call    cs:__imp_NtCreateCrossVmEvent
0x18020aabd  test    eax, eax
0x18020aabf  jns     short loc_18020AACB
0x18020aac1  mov     edx, 1A9h
0x18020aac6  jmp     loc_18020A93D
0x18020aacb  lea     rbp, [rbx+128h]
0x18020aad2  mov     rcx, rbp; pguid
0x18020aad5  call    cs:__imp_CoCreateGuid
0x18020aadb  mov     edi, eax
0x18020aadd  test    eax, eax
0x18020aadf  jns     short loc_18020AAEB
0x18020aae1  mov     edx, 1ABh
0x18020aae6  jmp     loc_18020A8E8
0x18020aaeb  lea     rcx, [rbx+68h]
0x18020aaef  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18020aaf4  xor     r9d, r9d
0x18020aaf7  mov     [rsp+78h+SectionOffset], rsi
0x18020aafc  xor     r8d, r8d
0x18020aaff  mov     [rsp+78h+CommitSize], rbp
0x18020ab04  mov     edx, r14d
0x18020ab07  mov     rcx, rax
0x18020ab0a  call    cs:__imp_NtCreateCrossVmEvent
0x18020ab10  test    eax, eax
0x18020ab12  jns     short loc_18020AB1E
0x18020ab14  mov     edx, 1ADh
0x18020ab19  jmp     loc_18020A93D
0x18020ab1e  lea     rbp, [rbx+138h]
0x18020ab25  mov     rcx, rbp; pguid
0x18020ab28  call    cs:__imp_CoCreateGuid
0x18020ab2e  mov     edi, eax
0x18020ab30  test    eax, eax
0x18020ab32  jns     short loc_18020AB3E
0x18020ab34  mov     edx, 1AFh
0x18020ab39  jmp     loc_18020A8E8
0x18020ab3e  lea     rcx, [rbx+70h]
0x18020ab42  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18020ab47  xor     r9d, r9d
0x18020ab4a  mov     [rsp+78h+SectionOffset], rsi
0x18020ab4f  xor     r8d, r8d
0x18020ab52  mov     [rsp+78h+CommitSize], rbp
0x18020ab57  mov     edx, r14d
0x18020ab5a  mov     rcx, rax
0x18020ab5d  call    cs:__imp_NtCreateCrossVmEvent
0x18020ab63  test    eax, eax
0x18020ab65  jns     short loc_18020AB71
0x18020ab67  mov     edx, 1B1h
0x18020ab6c  jmp     loc_18020A93D
0x18020ab71  lea     rbp, [rbx+148h]
0x18020ab78  mov     rcx, rbp; pguid
0x18020ab7b  call    cs:__imp_CoCreateGuid
0x18020ab81  mov     edi, eax
0x18020ab83  test    eax, eax
0x18020ab85  jns     short loc_18020AB91
0x18020ab87  mov     edx, 1B3h
0x18020ab8c  jmp     loc_18020A8E8
0x18020ab91  lea     rcx, [rbx+78h]
0x18020ab95  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18020ab9a  xor     r9d, r9d
0x18020ab9d  mov     [rsp+78h+SectionOffset], rsi
0x18020aba2  xor     r8d, r8d
0x18020aba5  mov     [rsp+78h+CommitSize], rbp
0x18020abaa  mov     edx, r14d
0x18020abad  mov     rcx, rax
0x18020abb0  call    cs:__imp_NtCreateCrossVmEvent
0x18020abb6  test    eax, eax
0x18020abb8  jns     short loc_18020ABC4
0x18020abba  mov     edx, 1B5h
0x18020abbf  jmp     loc_18020A93D
0x18020abc4  mov     eax, 1
0x18020abc9  mov     [rbx+178h], al
0x18020abcf  mov     [rbx+8], ax
0x18020abd3  xor     eax, eax
0x18020abd5  mov     rbx, [rsp+78h+arg_10]
0x18020abdd  add     rsp, 50h
0x18020abe1  pop     r14
0x18020abe3  pop     r12
0x18020abe5  pop     rdi
0x18020abe6  pop     rsi
0x18020abe7  pop     rbp
0x18020abe8  retn
```
