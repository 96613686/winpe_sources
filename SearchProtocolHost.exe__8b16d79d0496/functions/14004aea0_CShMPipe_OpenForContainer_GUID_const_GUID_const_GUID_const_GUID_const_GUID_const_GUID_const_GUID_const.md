# CShMPipe::OpenForContainer(_GUID const &,_GUID const &,_GUID const &,_GUID const &,_GUID const &,_GUID const &,_GUID const &)

- ea: `0x14004aea0`
- end: `0x14004b17f`
- name: `?OpenForContainer@CShMPipe@@QEAAJAEBU_GUID@@000000@Z`
- size: `735`
- prototype: `__int64 __fastcall(CShMPipe *__hidden this, const struct _GUID *, const struct _GUID *, const struct _GUID *, const struct _GUID *, const struct _GUID *, const struct _GUID *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x140028044`
- `0x140037ca8`
- `0x14004aea0`
- `0x14004b69c`
- `0x14006984c`

## import_xrefs

- `ntdll!NtCreateCrossVmEvent` at `0x14004afc4`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b00c`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b05b`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b0aa`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b0f9`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b14d`
- `ntdll!NtCreateCrossVmEvent` at `0x14004afc4`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b00c`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b05b`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b0aa`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b0f9`
- `ntdll!NtCreateCrossVmEvent` at `0x14004b14d`
- `ntdll!NtMapViewOfSection` at `0x14004af4a`
- `ntdll!NtMapViewOfSection` at `0x14004af4a`

## string_xrefs

- `0x14004af6b`: `onecoreuap\base\appmodel\search\common\pkmutild\shmpipe.cxx`

## pseudocode

```c
int __fastcall CShMPipe::OpenForContainer(
        CShMPipe *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        const struct _GUID *a5,
        const struct _GUID *a6,
        const struct _GUID *a7,
        const struct _GUID *a8)
{
  char *v8; // rbx
  void **v10; // rdi
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  NTSTATUS CrossVmEvent; // eax
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rcx
  int CommitSize; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  ULONG_PTR ViewSize; // [rsp+70h] [rbp+8h] BYREF

  v8 = (char *)this + 248;
  v10 = (void **)((char *)this + 72);
  *(struct _GUID *)((char *)this + 248) = *a2;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 72,
    0);
  CrossVmEvent = OpenVmSharedMemorySection2((_DWORD)v10, v13, v14, v15, (__int64)v8);
  if ( CrossVmEvent < 0 )
  {
    v18 = 524;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v18,
             v17,
             (const char *)(unsigned int)CrossVmEvent,
             CommitSize);
  }
  v20 = *v10;
  ViewSize = 0;
  CrossVmEvent = NtMapViewOfSection(
                   v20,
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   (PVOID *)this + 10,
                   0,
                   0,
                   0,
                   &ViewSize,
                   ViewUnmap,
                   0,
                   4u);
  if ( CrossVmEvent < 0 )
  {
    v18 = 528;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v18,
             v17,
             (const char *)(unsigned int)CrossVmEvent,
             CommitSize);
  }
  if ( ViewSize == 0x10000 )
  {
    *(struct _GUID *)((char *)this + 264) = *a3;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 88,
      0);
    CommitSize = (_DWORD)this + 264;
    CrossVmEvent = NtCreateCrossVmEvent((char *)this + 88, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v18 = 534;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v18,
               v17,
               (const char *)(unsigned int)CrossVmEvent,
               CommitSize);
    }
    *(struct _GUID *)((char *)this + 280) = *a4;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 96,
      0);
    CommitSize = (_DWORD)this + 280;
    CrossVmEvent = NtCreateCrossVmEvent((char *)this + 96, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v18 = 538;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v18,
               v17,
               (const char *)(unsigned int)CrossVmEvent,
               CommitSize);
    }
    *(struct _GUID *)((char *)this + 296) = *a5;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 104,
      0);
    CommitSize = (_DWORD)this + 296;
    CrossVmEvent = NtCreateCrossVmEvent((char *)this + 104, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v18 = 542;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v18,
               v17,
               (const char *)(unsigned int)CrossVmEvent,
               CommitSize);
    }
    *(struct _GUID *)((char *)this + 312) = *a6;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 112,
      0);
    CommitSize = (_DWORD)this + 312;
    CrossVmEvent = NtCreateCrossVmEvent((char *)this + 112, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v18 = 546;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v18,
               v17,
               (const char *)(unsigned int)CrossVmEvent,
               CommitSize);
    }
    *(struct _GUID *)((char *)this + 328) = *a7;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 120,
      0);
    CommitSize = (_DWORD)this + 328;
    CrossVmEvent = NtCreateCrossVmEvent((char *)this + 120, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v18 = 550;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v18,
               v17,
               (const char *)(unsigned int)CrossVmEvent,
               CommitSize);
    }
    *(struct _GUID *)((char *)this + 344) = *a8;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 128,
      0);
    CommitSize = (_DWORD)this + 344;
    CrossVmEvent = NtCreateCrossVmEvent((char *)this + 128, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v18 = 554;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v18,
               v17,
               (const char *)(unsigned int)CrossVmEvent,
               CommitSize);
    }
    *((_BYTE *)this + 376) = 1;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
      (const char *)0x80004005LL,
      CommitSize);
    return -2147467259;
  }
}

```

## disassembly

```asm
0x14004aea0  mov     [rsp+arg_8], rbx
0x14004aea5  mov     [rsp+arg_10], rbp
0x14004aeaa  push    rsi
0x14004aeab  push    rdi
0x14004aeac  push    r14
0x14004aeae  sub     rsp, 50h
0x14004aeb2  movups  xmm0, xmmword ptr [rdx]
0x14004aeb5  lea     rbx, [rcx+0F8h]
0x14004aebc  mov     rsi, rcx
0x14004aebf  lea     rdi, [rcx+48h]
0x14004aec3  xor     edx, edx
0x14004aec5  mov     rcx, rdi
0x14004aec8  mov     r14, r9
0x14004aecb  movdqu  xmmword ptr [rbx], xmm0
0x14004aecf  mov     rbp, r8
0x14004aed2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004aed7  mov     rcx, rdi
0x14004aeda  mov     [rsp+68h+CommitSize], rbx; int
0x14004aedf  call    OpenVmSharedMemorySection2
0x14004aee4  test    eax, eax
0x14004aee6  jns     short loc_14004AEFF
0x14004aee8  mov     edx, 20Ch; void *
0x14004aeed  mov     rcx, [rsp+68h]; this
0x14004aef2  mov     r9d, eax; char *
0x14004aef5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14004aefa  jmp     loc_14004B16A
0x14004aeff  mov     rcx, [rdi]; SectionHandle
0x14004af02  lea     rax, [rsp+68h+arg_0]
0x14004af07  mov     [rsp+68h+AccessProtection], 4; AccessProtection
0x14004af0f  lea     r8, [rsi+50h]; BaseAddress
0x14004af13  mov     [rsp+68h+AllocationType], 0; AllocationType
0x14004af1b  xor     r9d, r9d; ZeroBits
0x14004af1e  mov     [rsp+68h+InheritDisposition], 2; InheritDisposition
0x14004af26  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14004af2a  mov     [rsp+68h+ViewSize], rax; ViewSize
0x14004af2f  mov     [rsp+68h+SectionOffset], 0; SectionOffset
0x14004af38  mov     [rsp+68h+CommitSize], 0; int
0x14004af41  mov     [rsp+68h+arg_0], 0
0x14004af4a  call    cs:__imp_NtMapViewOfSection
0x14004af50  test    eax, eax
0x14004af52  jns     short loc_14004AF5B
0x14004af54  mov     edx, 210h
0x14004af59  jmp     short loc_14004AEED
0x14004af5b  cmp     [rsp+68h+arg_0], 10000h
0x14004af64  jz      short loc_14004AF8B
0x14004af66  mov     rcx, [rsp+68h]; this
0x14004af6b  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004af72  mov     ebx, 80004005h
0x14004af77  mov     edx, 212h; void *
0x14004af7c  mov     r9d, ebx; char *
0x14004af7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004af84  mov     eax, ebx
0x14004af86  jmp     loc_14004B16A
0x14004af8b  movups  xmm0, xmmword ptr [rbp+0]
0x14004af8f  lea     rbx, [rsi+108h]
0x14004af96  xor     edx, edx
0x14004af98  lea     rcx, [rsi+58h]
0x14004af9c  movdqu  xmmword ptr [rbx], xmm0
0x14004afa0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004afa5  mov     ebp, 1F0003h
0x14004afaa  mov     [rsp+68h+SectionOffset], 0
0x14004afb3  mov     edx, ebp
0x14004afb5  mov     [rsp+68h+CommitSize], rbx
0x14004afba  xor     r9d, r9d
0x14004afbd  lea     rcx, [rsi+58h]
0x14004afc1  xor     r8d, r8d
0x14004afc4  call    cs:__imp_NtCreateCrossVmEvent
0x14004afca  test    eax, eax
0x14004afcc  jns     short loc_14004AFD8
0x14004afce  mov     edx, 216h
0x14004afd3  jmp     loc_14004AEED
0x14004afd8  movups  xmm0, xmmword ptr [r14]
0x14004afdc  lea     rbx, [rsi+118h]
0x14004afe3  xor     edx, edx
0x14004afe5  lea     rcx, [rsi+60h]
0x14004afe9  movdqu  xmmword ptr [rbx], xmm0
0x14004afed  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004aff2  xor     r9d, r9d
0x14004aff5  mov     [rsp+68h+SectionOffset], 0
0x14004affe  xor     r8d, r8d
0x14004b001  mov     [rsp+68h+CommitSize], rbx
0x14004b006  mov     edx, ebp
0x14004b008  lea     rcx, [rsi+60h]
0x14004b00c  call    cs:__imp_NtCreateCrossVmEvent
0x14004b012  test    eax, eax
0x14004b014  jns     short loc_14004B020
0x14004b016  mov     edx, 21Ah
0x14004b01b  jmp     loc_14004AEED
0x14004b020  mov     rax, [rsp+68h+arg_20]
0x14004b028  lea     rbx, [rsi+128h]
0x14004b02f  xor     edx, edx
0x14004b031  lea     rcx, [rsi+68h]
0x14004b035  movups  xmm0, xmmword ptr [rax]
0x14004b038  movdqu  xmmword ptr [rbx], xmm0
0x14004b03c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004b041  xor     r9d, r9d
0x14004b044  mov     [rsp+68h+SectionOffset], 0
0x14004b04d  xor     r8d, r8d
0x14004b050  mov     [rsp+68h+CommitSize], rbx
0x14004b055  mov     edx, ebp
0x14004b057  lea     rcx, [rsi+68h]
0x14004b05b  call    cs:__imp_NtCreateCrossVmEvent
0x14004b061  test    eax, eax
0x14004b063  jns     short loc_14004B06F
0x14004b065  mov     edx, 21Eh
0x14004b06a  jmp     loc_14004AEED
0x14004b06f  mov     rax, [rsp+68h+arg_28]
0x14004b077  lea     rbx, [rsi+138h]
0x14004b07e  xor     edx, edx
0x14004b080  lea     rcx, [rsi+70h]
0x14004b084  movups  xmm0, xmmword ptr [rax]
0x14004b087  movdqu  xmmword ptr [rbx], xmm0
0x14004b08b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004b090  xor     r9d, r9d
0x14004b093  mov     [rsp+68h+SectionOffset], 0
0x14004b09c  xor     r8d, r8d
0x14004b09f  mov     [rsp+68h+CommitSize], rbx
0x14004b0a4  mov     edx, ebp
0x14004b0a6  lea     rcx, [rsi+70h]
0x14004b0aa  call    cs:__imp_NtCreateCrossVmEvent
0x14004b0b0  test    eax, eax
0x14004b0b2  jns     short loc_14004B0BE
0x14004b0b4  mov     edx, 222h
0x14004b0b9  jmp     loc_14004AEED
0x14004b0be  mov     rax, [rsp+68h+arg_30]
0x14004b0c6  lea     rbx, [rsi+148h]
0x14004b0cd  xor     edx, edx
0x14004b0cf  lea     rcx, [rsi+78h]
0x14004b0d3  movups  xmm0, xmmword ptr [rax]
0x14004b0d6  movdqu  xmmword ptr [rbx], xmm0
0x14004b0da  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004b0df  xor     r9d, r9d
0x14004b0e2  mov     [rsp+68h+SectionOffset], 0
0x14004b0eb  xor     r8d, r8d
0x14004b0ee  mov     [rsp+68h+CommitSize], rbx
0x14004b0f3  mov     edx, ebp
0x14004b0f5  lea     rcx, [rsi+78h]
0x14004b0f9  call    cs:__imp_NtCreateCrossVmEvent
0x14004b0ff  test    eax, eax
0x14004b101  jns     short loc_14004B10D
0x14004b103  mov     edx, 226h
0x14004b108  jmp     loc_14004AEED
0x14004b10d  mov     rax, [rsp+68h+arg_38]
0x14004b115  lea     rdi, [rsi+80h]
0x14004b11c  lea     rbx, [rsi+158h]
0x14004b123  xor     edx, edx
0x14004b125  mov     rcx, rdi
0x14004b128  movups  xmm0, xmmword ptr [rax]
0x14004b12b  movdqu  xmmword ptr [rbx], xmm0
0x14004b12f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004b134  xor     r9d, r9d
0x14004b137  mov     [rsp+68h+SectionOffset], 0
0x14004b140  xor     r8d, r8d
0x14004b143  mov     [rsp+68h+CommitSize], rbx
0x14004b148  mov     edx, ebp
0x14004b14a  mov     rcx, rdi
0x14004b14d  call    cs:__imp_NtCreateCrossVmEvent
0x14004b153  test    eax, eax
0x14004b155  jns     short loc_14004B161
0x14004b157  mov     edx, 22Ah
0x14004b15c  jmp     loc_14004AEED
0x14004b161  mov     byte ptr [rsi+178h], 1
0x14004b168  xor     eax, eax
0x14004b16a  lea     r11, [rsp+68h+var_18]
0x14004b16f  mov     rbx, [r11+28h]
0x14004b173  mov     rbp, [r11+30h]
0x14004b177  mov     rsp, r11
0x14004b17a  pop     r14
0x14004b17c  pop     rdi
0x14004b17d  pop     rsi
0x14004b17e  retn
```
