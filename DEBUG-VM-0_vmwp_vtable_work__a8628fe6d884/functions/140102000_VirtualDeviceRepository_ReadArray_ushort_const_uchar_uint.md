# VirtualDeviceRepository::ReadArray(ushort const *,uchar *,uint)

- ea: `0x140102000`
- end: `0x14010223b`
- name: `?ReadArray@VirtualDeviceRepository@@UEAAJPEBGPEAEI@Z`
- size: `571`
- prototype: `int(VirtualDeviceRepository *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140042240`
- `0x1400549dc`
- `0x14005b628`
- `0x14006af38`
- `0x140078c98`
- `0x140102000`
- `0x140102244`
- `0x140132940`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401021d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401021d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14010211b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14010211b`

## string_xrefs

- `0x140102137`: `onecore\vm\common\vml\VmMemory.h`
- `0x140102044`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1401020a4`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1401020cc`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x140102101`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x140102176`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x1401021bc`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`
- `0x140102228`: `onecore\vm\common\repository\core\virtualdevicerepository.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VirtualDeviceRepository::ReadArray(
        VirtualDeviceRepository *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  char *v8; // rsi
  int Access; // eax
  int v10; // eax
  HLOCAL v11; // rax
  const char *v12; // r9
  void *v13; // rbx
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  __int64 result; // rax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-68h]
  int v20; // [rsp+20h] [rbp-68h]
  SIZE_T uBytes; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v8 = (char *)this - 24;
  Access = VirtualDeviceRepository::VerifyReadAccess((VirtualDeviceRepository *)((char *)this - 24), a2);
  try
  {
    if ( Access < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x736,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
        (const char *)(unsigned int)Access,
        v19);
    if ( *((_DWORD *)this + 33) )
    {
      LODWORD(uBytes) = 0;
      v10 = (*(__int64 (__fastcall **)(VirtualDeviceRepository *, const unsigned __int16 *, SIZE_T *))(*(_QWORD *)this + 288LL))(
              this,
              a2,
              &uBytes);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x742,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)(unsigned int)v10,
          v19);
      if ( a4 > (unsigned int)uBytes )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x74A,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)0x8000FFFFLL,
          v19);
        if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
          VmlDebugTraceEx(0, &off_1402DA9A8);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74C,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)0x8000FFFFLL,
          v20);
      }
      v11 = LocalAlloc(0x40u, (unsigned int)uBytes);
      v13 = v11;
      if ( !v11 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x355,
          (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
          v12);
      v14 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, HLOCAL, _QWORD))(*(_QWORD *)v8 + 64LL))(
              v8,
              a2,
              v11,
              (unsigned int)uBytes);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x753,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)(unsigned int)v14,
          v19);
      v15 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, unsigned __int8 *))(**((_QWORD **)this + 17) + 216LL))(
              *((_QWORD *)this + 17),
              v13,
              (unsigned int)uBytes,
              a3);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x759,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)(unsigned int)v15,
          a4);
      LocalFree(v13);
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, unsigned __int8 *, _QWORD))(*(_QWORD *)v8 + 64LL))(
              v8,
              a2,
              a3,
              a4);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x75F,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
          (const char *)(unsigned int)v18,
          v19);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x764,
                           (unsigned int)"onecore\\vm\\common\\repository\\core\\virtualdevicerepository.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x140102000  push    rbx
0x140102002  push    rsi
0x140102003  push    rdi
0x140102004  push    r12
0x140102006  push    r14
0x140102008  push    r15
0x14010200a  sub     rsp, 58h
0x14010200e  mov     rax, cs:__security_cookie
0x140102015  xor     rax, rsp
0x140102018  mov     [rsp+88h+var_40], rax
0x14010201d  mov     r15d, r9d
0x140102020  mov     r12, r8
0x140102023  mov     r14, rdx
0x140102026  mov     rdi, rcx
0x140102029  lea     rsi, [rcx-18h]
0x14010202d  mov     rcx, rsi; this
0x140102030  call    ?VerifyReadAccess@VirtualDeviceRepository@@AEAAJPEBG@Z; VirtualDeviceRepository::VerifyReadAccess(ushort const *)
0x140102035  mov     rcx, [rsp+88h]; this
0x14010203d  test    eax, eax
0x14010203f  jns     short loc_140102055
0x140102041  mov     r9d, eax; char *
0x140102044  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x14010204b  mov     edx, 736h; void *
0x140102050  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140102055  cmp     dword ptr [rdi+84h], 0
0x14010205c  jz      loc_140102201
0x140102062  xorps   xmm0, xmm0
0x140102065  movups  [rsp+88h+var_58], xmm0
0x14010206a  mov     qword ptr [rsp+88h+var_58], 0
0x140102073  mov     dword ptr [rsp+88h+uBytes], 0
0x14010207b  mov     rax, [rdi]
0x14010207e  lea     r8, [rsp+88h+uBytes]
0x140102083  mov     rdx, r14
0x140102086  mov     rcx, rdi
0x140102089  mov     rax, [rax+120h]
0x140102090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102095  mov     rcx, [rsp+88h]; this
0x14010209d  test    eax, eax
0x14010209f  jns     short loc_1401020B5
0x1401020a1  mov     r9d, eax; char *
0x1401020a4  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1401020ab  mov     edx, 742h; void *
0x1401020b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401020b5  cmp     r15d, dword ptr [rsp+88h+uBytes]
0x1401020ba  jbe     short loc_140102112
0x1401020bc  mov     rcx, [rsp+88h]; this
0x1401020c4  mov     ebx, 8000FFFFh
0x1401020c9  mov     r9d, ebx; char *
0x1401020cc  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1401020d3  mov     edx, 74Ah; void *
0x1401020d8  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1401020dd  xor     ecx, ecx
0x1401020df  call    VmlIsDebugTraceEnabled
0x1401020e4  test    eax, eax
0x1401020e6  jz      short loc_1401020F6
0x1401020e8  lea     rdx, off_1402DA9A8; "Unexpected error.\n"
0x1401020ef  xor     ecx, ecx
0x1401020f1  call    VmlDebugTraceEx
0x1401020f6  mov     rcx, [rsp+88h]; this
0x1401020fe  mov     r9d, ebx; char *
0x140102101  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x140102108  mov     edx, 74Ch; void *
0x14010210d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140102112  mov     edx, dword ptr [rsp+88h+uBytes]; uBytes
0x140102116  mov     ecx, 40h ; '@'; uFlags
0x14010211b  call    cs:__imp_LocalAlloc
0x140102122  nop     dword ptr [rax+rax+00h]
0x140102127  mov     rbx, rax
0x14010212a  test    rax, rax
0x14010212d  jnz     short loc_140102148
0x14010212f  mov     rcx, [rsp+88h]; this
0x140102137  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14010213e  mov     edx, 355h; void *
0x140102143  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140102148  mov     qword ptr [rsp+88h+var_58], rbx
0x14010214d  mov     rax, [rsi]
0x140102150  mov     r9d, dword ptr [rsp+88h+uBytes]
0x140102155  mov     r8, rbx
0x140102158  mov     rdx, r14
0x14010215b  mov     rcx, rsi
0x14010215e  mov     rax, [rax+40h]
0x140102162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102167  mov     rcx, [rsp+88h]; this
0x14010216f  test    eax, eax
0x140102171  jns     short loc_140102187
0x140102173  mov     r9d, eax; char *
0x140102176  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x14010217d  mov     edx, 753h; void *
0x140102182  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140102187  mov     rcx, [rdi+88h]
0x14010218e  mov     rax, [rcx]
0x140102191  mov     [rsp+88h+var_68], r15d; int
0x140102196  mov     r9, r12
0x140102199  mov     r8d, dword ptr [rsp+88h+uBytes]
0x14010219e  mov     rdx, rbx
0x1401021a1  mov     rax, [rax+0D8h]
0x1401021a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401021ad  mov     rcx, [rsp+88h]; this
0x1401021b5  test    eax, eax
0x1401021b7  jns     short loc_1401021CE
0x1401021b9  mov     r9d, eax; char *
0x1401021bc  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x1401021c3  mov     edx, 759h; void *
0x1401021c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401021ce  mov     rcx, rbx; hMem
0x1401021d1  call    cs:__imp_LocalFree
0x1401021d8  nop     dword ptr [rax+rax+00h]
0x1401021dd  xor     eax, eax
0x1401021df  jmp     short loc_1401021E5
0x1401021e1  mov     eax, dword ptr [rsp+88h+uBytes]
0x1401021e5  mov     rcx, [rsp+88h+var_40]
0x1401021ea  xor     rcx, rsp; StackCookie
0x1401021ed  call    __security_check_cookie
0x1401021f2  add     rsp, 58h
0x1401021f6  pop     r15
0x1401021f8  pop     r14
0x1401021fa  pop     r12
0x1401021fc  pop     rdi
0x1401021fd  pop     rsi
0x1401021fe  pop     rbx
0x1401021ff  retn
0x140102201  mov     rax, [rsi]
0x140102204  mov     r9d, r15d
0x140102207  mov     r8, r12
0x14010220a  mov     rdx, r14
0x14010220d  mov     rcx, rsi
0x140102210  mov     rax, [rax+40h]
0x140102214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102219  mov     rcx, [rsp+88h]; this
0x140102221  test    eax, eax
0x140102223  jns     short loc_1401021DD
0x140102225  mov     r9d, eax; char *
0x140102228  lea     r8, aOnecoreVmCommo_97; "onecore\\vm\\common\\repository\\core\\"...
0x14010222f  mov     edx, 75Fh; void *
0x140102234  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
