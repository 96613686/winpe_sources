# WaasMedic::TasksHelper::GetTaskURI(ushort const *,ushort * *)

- ea: `0x18005f7cc`
- end: `0x18005f9b4`
- name: `?GetTaskURI@TasksHelper@WaasMedic@@QEAAJPEBGPEAPEAG@Z`
- size: `488`
- prototype: `int(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800555cc`

## callees

- `0x180009a54`
- `0x18002543c`
- `0x18005f7cc`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005f7ee`
- `OLEAUT32!__imp_SysAllocString` at `0x18005f7ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f9a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f9a1`

## string_xrefs

- `0x18005f83b`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x18005f93c`: `Failed to get URI info. hr = 0x%08x`
- `0x18005f810`: `Invalid pointer input for GetTaskURI`
- `0x18005f950`: `Failed to get TaskURI hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaasMedic::TasksHelper::GetTaskURI(
        WaasMedic::TasksHelper *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  OLECHAR *v5; // rbx
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // r14
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  __int64 v19; // [rsp+58h] [rbp+38h] BYREF
  __int64 v20; // [rsp+60h] [rbp+40h] BYREF
  OLECHAR *v21; // [rsp+68h] [rbp+48h]

  v5 = 0;
  v21 = 0;
  if ( a2 )
  {
    v5 = SysAllocString(a2);
    v21 = v5;
  }
  v20 = 0;
  v19 = 0;
  if ( !a3 )
  {
    LogLevelW(2u, L"Invalid pointer input for GetTaskURI");
    v6 = -2147467261;
    goto LABEL_19;
  }
  if ( *((_BYTE *)this + 16) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)this + 72LL))(*(_QWORD *)this, 0, &v20);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v20 + 160LL))(v20, v5);
      if ( v6 >= 0 )
      {
        v9 = v20;
        v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 56LL);
        v11 = v19;
        if ( v19 )
        {
          v19 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        v12 = v10(v9, &v19);
        if ( v12 < 0 )
          LogLevelW(2u, L"Failed to get registration info. hr = 0x%08x", (unsigned int)v12);
        v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v19 + 152LL))(v19, a3);
        v6 = v13;
        if ( v13 >= 0 )
          goto LABEL_20;
        LogLevelW(2u, L"Failed to get URI info. hr = 0x%08x", (unsigned int)v13);
      }
    }
LABEL_19:
    LogLevelW(2u, L"Failed to get TaskURI hr = 0x%08x", (unsigned int)v6);
LABEL_20:
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_24;
  }
  v6 = -2147019873;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5AE,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
    (const char *)0x8007139FLL,
    savedregs);
  v7 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
LABEL_24:
  SysFreeString(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005f7cc  push    rbp
0x18005f7ce  push    rbx
0x18005f7cf  push    rsi
0x18005f7d0  push    rdi
0x18005f7d1  push    r14; int
0x18005f7d3  mov     rbp, rsp
0x18005f7d6  sub     rsp, 20h
0x18005f7da  mov     rsi, r8
0x18005f7dd  mov     rdi, rcx
0x18005f7e0  xor     ebx, ebx
0x18005f7e2  mov     [rbp+arg_18], rbx
0x18005f7e6  test    rdx, rdx
0x18005f7e9  jz      short loc_18005F7FB
0x18005f7eb  mov     rcx, rdx; psz
0x18005f7ee  call    cs:__imp_SysAllocString
0x18005f7f4  mov     rbx, rax
0x18005f7f7  mov     [rbp+arg_18], rax
0x18005f7fb  mov     [rbp+arg_10], 0
0x18005f803  mov     [rbp+arg_8], 0
0x18005f80b  test    rsi, rsi
0x18005f80e  jnz     short loc_18005F829
0x18005f810  lea     rdx, aInvalidPointer_1; "Invalid pointer input for GetTaskURI"
0x18005f817  lea     ecx, [rsi+2]; unsigned __int8
0x18005f81a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f81f  mov     edi, 80004003h
0x18005f824  jmp     loc_18005F94D
0x18005f829  cmp     byte ptr [rdi+10h], 0
0x18005f82d  jnz     short loc_18005F88E
0x18005f82f  mov     rcx, [rbp+28h]; this
0x18005f833  mov     edi, 8007139Fh
0x18005f838  mov     r9d, edi; char *
0x18005f83b  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005f842  mov     edx, 5AEh; void *
0x18005f847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f84c  nop
0x18005f84d  mov     rcx, [rbp+arg_8]
0x18005f851  test    rcx, rcx
0x18005f854  jz      short loc_18005F86B
0x18005f856  mov     [rbp+arg_8], 0
0x18005f85e  mov     rax, [rcx]
0x18005f861  mov     rax, [rax+10h]
0x18005f865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f86a  nop
0x18005f86b  mov     rcx, [rbp+arg_10]
0x18005f86f  test    rcx, rcx
0x18005f872  jz      short loc_18005F889
0x18005f874  mov     [rbp+arg_10], 0
0x18005f87c  mov     rax, [rcx]
0x18005f87f  mov     rax, [rax+10h]
0x18005f883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f888  nop
0x18005f889  jmp     loc_18005F99E
0x18005f88e  mov     rcx, [rdi]
0x18005f891  mov     rax, [rcx]
0x18005f894  lea     r8, [rbp+arg_10]
0x18005f898  xor     edx, edx
0x18005f89a  mov     rax, [rax+48h]
0x18005f89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f8a3  mov     edi, eax
0x18005f8a5  test    eax, eax
0x18005f8a7  js      loc_18005F94D
0x18005f8ad  mov     rcx, [rbp+arg_10]
0x18005f8b1  mov     rax, [rcx]
0x18005f8b4  mov     rdx, rbx
0x18005f8b7  mov     rax, [rax+0A0h]
0x18005f8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f8c3  mov     edi, eax
0x18005f8c5  test    eax, eax
0x18005f8c7  js      loc_18005F94D
0x18005f8cd  mov     rdi, [rbp+arg_10]
0x18005f8d1  mov     rax, [rdi]
0x18005f8d4  mov     r14, [rax+38h]
0x18005f8d8  mov     rcx, [rbp+arg_8]
0x18005f8dc  test    rcx, rcx
0x18005f8df  jz      short loc_18005F8F6
0x18005f8e1  mov     [rbp+arg_8], 0
0x18005f8e9  mov     rdx, [rcx]
0x18005f8ec  mov     rax, [rdx+10h]
0x18005f8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f8f5  nop
0x18005f8f6  lea     rdx, [rbp+arg_8]
0x18005f8fa  mov     rcx, rdi
0x18005f8fd  mov     rax, r14
0x18005f900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f905  test    eax, eax
0x18005f907  jns     short loc_18005F91D
0x18005f909  mov     r8d, eax
0x18005f90c  lea     rdx, aFailedToGetReg; "Failed to get registration info. hr = 0"...
0x18005f913  mov     ecx, 2; unsigned __int8
0x18005f918  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f91d  mov     rcx, [rbp+arg_8]
0x18005f921  mov     rax, [rcx]
0x18005f924  mov     rdx, rsi
0x18005f927  mov     rax, [rax+98h]
0x18005f92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f933  mov     edi, eax
0x18005f935  test    eax, eax
0x18005f937  jns     short loc_18005F962
0x18005f939  mov     r8d, eax
0x18005f93c  lea     rdx, aFailedToGetUri; "Failed to get URI info. hr = 0x%08x"
0x18005f943  mov     ecx, 2; unsigned __int8
0x18005f948  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f94d  mov     r8d, edi
0x18005f950  lea     rdx, aFailedToGetTas_0; "Failed to get TaskURI hr = 0x%08x"
0x18005f957  mov     ecx, 2; unsigned __int8
0x18005f95c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f961  nop
0x18005f962  mov     rcx, [rbp+arg_8]
0x18005f966  test    rcx, rcx
0x18005f969  jz      short loc_18005F980
0x18005f96b  mov     [rbp+arg_8], 0
0x18005f973  mov     rax, [rcx]
0x18005f976  mov     rax, [rax+10h]
0x18005f97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f97f  nop
0x18005f980  mov     rcx, [rbp+arg_10]
0x18005f984  test    rcx, rcx
0x18005f987  jz      short loc_18005F99E
0x18005f989  mov     [rbp+arg_10], 0
0x18005f991  mov     rax, [rcx]
0x18005f994  mov     rax, [rax+10h]
0x18005f998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f99d  nop
0x18005f99e  mov     rcx, rbx; bstrString
0x18005f9a1  call    cs:__imp_SysFreeString
0x18005f9a7  mov     eax, edi
0x18005f9a9  add     rsp, 20h
0x18005f9ad  pop     r14
0x18005f9af  pop     rdi
0x18005f9b0  pop     rsi
0x18005f9b1  pop     rbx
0x18005f9b2  pop     rbp
0x18005f9b3  retn
```
