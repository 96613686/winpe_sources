# StandardCollectorHost::GetServiceAndSession(_GUID const &,IStandardCollectorVersion * *,IStandardCollectorVersion * *)

- ea: `0x140006370`
- end: `0x140006524`
- name: `?GetServiceAndSession@StandardCollectorHost@@UEAAJAEBU_GUID@@PEAPEAUIStandardCollectorVersion@@1@Z`
- size: `436`
- prototype: `__int64 __fastcall(StandardCollectorHost *this, const struct _GUID *, struct IStandardCollectorVersion **, struct IStandardCollectorVersion **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006370`
- `0x14000a278`
- `0x1400137e0`
- `0x14001472c`
- `0x140014c70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000642c`
- `KERNEL32!LeaveCriticalSection` at `0x14000642c`
- `KERNEL32!EnterCriticalSection` at `0x1400063cc`
- `KERNEL32!EnterCriticalSection` at `0x1400063cc`
- `ole32!StringFromGUID2` at `0x14000647a`
- `ole32!StringFromGUID2` at `0x14000647a`

## string_xrefs

- `0x1400064b2`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Service\StandardCollectorHost.cpp`
- `0x1400064ab`: `Found session '%s' in collection service '%s'`

## pseudocode

```c
__int64 __fastcall StandardCollectorHost::GetServiceAndSession(
        StandardCollectorHost *this,
        const struct _GUID *a2,
        struct IStandardCollectorVersion **a3,
        struct IStandardCollectorVersion **a4)
{
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  __int64 (__fastcall ***v10)(_QWORD, GUID *, struct IStandardCollectorVersion **); // rcx
  _QWORD *v11; // r14
  _QWORD *v12; // rbx
  int v13; // ebx
  int pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  char *v15; // [rsp+38h] [rbp-C8h]
  __int64 (__fastcall ***v16)(_QWORD, GUID *, struct IStandardCollectorVersion **); // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[112]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a3 )
    *a3 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  v15 = (char *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v10 = 0;
  v16 = 0;
  v11 = (_QWORD *)*((_QWORD *)this + 12);
  v12 = (_QWORD *)*v11;
  if ( (_QWORD *)*v11 == v11 )
  {
LABEL_9:
    v13 = -2147023728;
  }
  else
  {
    while ( (*(unsigned int (__fastcall **)(_QWORD, const struct _GUID *, _QWORD))(*(_QWORD *)v12[3] + 32LL))(
              v12[3],
              a2,
              &v16) )
    {
      v12 = (_QWORD *)*v12;
      if ( v12 == v11 )
      {
        v10 = v16;
        goto LABEL_9;
      }
    }
    if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
    {
      if ( !StringFromGUID2(a2, sz, 39) )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      sz[39] = 0;
      sz[78] = 0;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Service\\StandardCollectorHost.cpp",
        L"Found session '%s' in collection service '%s'",
        sz,
        v12[2]);
    }
    if ( !a3
      || (v13 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IStandardCollectorVersion **))v12[3])(
                  v12[3],
                  &GUID_55ab9bed_994c_45ec_8492_73c78af2ff56,
                  a3),
          v13 >= 0) )
    {
      v13 = (**v16)(v16, &GUID_55ab9bed_994c_45ec_8492_73c78af2ff56, a4);
    }
    v10 = v16;
  }
  if ( v10 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IStandardCollectorVersion **)))(*v10)[2])(v10);
  LeaveCriticalSection(v9);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140006370  mov     [rsp-8+arg_0], rbx
0x140006375  push    rbp
0x140006376  push    rsi
0x140006377  push    rdi
0x140006378  push    r12
0x14000637a  push    r13
0x14000637c  push    r14
0x14000637e  push    r15
0x140006380  lea     rbp, [rsp-40h]
0x140006385  sub     rsp, 140h
0x14000638c  mov     rax, cs:__security_cookie
0x140006393  xor     rax, rsp
0x140006396  mov     [rbp+70h+var_40], rax
0x14000639a  mov     r15, r9
0x14000639d  mov     rsi, r8
0x1400063a0  mov     r12, rdx
0x1400063a3  mov     r14, rcx
0x1400063a6  xor     r13d, r13d
0x1400063a9  test    r9, r9
0x1400063ac  jnz     short loc_1400063B5
0x1400063ae  mov     eax, 80004003h
0x1400063b3  jmp     short loc_140006434
0x1400063b5  mov     [r9], r13
0x1400063b8  test    rsi, rsi
0x1400063bb  jz      short loc_1400063C0
0x1400063bd  mov     [r8], r13
0x1400063c0  lea     rdi, [rcx+30h]
0x1400063c4  mov     [rsp+170h+var_138], rdi
0x1400063c9  mov     rcx, rdi; lpCriticalSection
0x1400063cc  call    cs:__imp_EnterCriticalSection
0x1400063d2  nop
0x1400063d3  mov     rcx, r13
0x1400063d6  mov     [rsp+170h+var_130], rcx
0x1400063db  mov     r14, [r14+60h]
0x1400063df  mov     rbx, [r14]
0x1400063e2  cmp     rbx, r14
0x1400063e5  jz      short loc_140006411
0x1400063e7  mov     rcx, [rbx+18h]
0x1400063eb  mov     rax, [rcx]
0x1400063ee  lea     r8, [rsp+170h+var_130]
0x1400063f3  mov     rdx, r12
0x1400063f6  mov     rax, [rax+20h]
0x1400063fa  call    cs:__guard_dispatch_icall_fptr
0x140006400  test    eax, eax
0x140006402  jz      short loc_14000645B
0x140006404  mov     rbx, [rbx]
0x140006407  cmp     rbx, r14
0x14000640a  jnz     short loc_1400063E7
0x14000640c  mov     rcx, [rsp+170h+var_130]
0x140006411  mov     ebx, 80070490h
0x140006416  test    rcx, rcx
0x140006419  jz      short loc_140006429
0x14000641b  mov     rdx, [rcx]
0x14000641e  mov     rax, [rdx+10h]
0x140006422  call    cs:__guard_dispatch_icall_fptr
0x140006428  nop
0x140006429  mov     rcx, rdi; lpCriticalSection
0x14000642c  call    cs:__imp_LeaveCriticalSection
0x140006432  mov     eax, ebx
0x140006434  mov     rcx, [rbp+70h+var_40]
0x140006438  xor     rcx, rsp; StackCookie
0x14000643b  call    __security_check_cookie
0x140006440  mov     rbx, [rsp+170h+arg_0]
0x140006448  add     rsp, 140h
0x14000644f  pop     r15
0x140006451  pop     r14
0x140006453  pop     r13
0x140006455  pop     r12
0x140006457  pop     rdi
0x140006458  pop     rsi
0x140006459  pop     rbp
0x14000645a  retn
0x14000645b  mov     rdx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x140006462  mov     rax, [rdx+40h]
0x140006466  cmp     [rdx+38h], rax
0x14000646a  jz      short loc_1400064BE
0x14000646c  mov     r8d, 27h ; '''; cchMax
0x140006472  lea     rdx, [rsp+170h+sz]; lpsz
0x140006477  mov     rcx, r12; rguid
0x14000647a  call    cs:__imp_StringFromGUID2
0x140006480  test    eax, eax
0x140006482  jz      loc_14000650A
0x140006488  mov     [rbp+70h+var_D2], r13w
0x14000648d  mov     [rbp+70h+var_84], r13w
0x140006492  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x140006499  add     rcx, 38h ; '8'; this
0x14000649d  mov     rax, [rbx+10h]
0x1400064a1  mov     [rsp+170h+var_150], rax
0x1400064a6  lea     r9, [rsp+170h+sz]
0x1400064ab  lea     r8, aFoundSessionSI; "Found session '%s' in collection servic"...
0x1400064b2  lea     rdx, aDAWork1SSource_0; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1400064b9  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1400064be  test    rsi, rsi
0x1400064c1  jz      short loc_1400064E3
0x1400064c3  mov     rcx, [rbx+18h]
0x1400064c7  mov     rax, [rcx]
0x1400064ca  mov     r8, rsi
0x1400064cd  lea     rdx, _GUID_55ab9bed_994c_45ec_8492_73c78af2ff56
0x1400064d4  mov     rax, [rax]
0x1400064d7  call    cs:__guard_dispatch_icall_fptr
0x1400064dd  mov     ebx, eax
0x1400064df  test    eax, eax
0x1400064e1  js      short loc_140006500
0x1400064e3  mov     rcx, [rsp+170h+var_130]
0x1400064e8  mov     rax, [rcx]
0x1400064eb  mov     r8, r15
0x1400064ee  lea     rdx, _GUID_55ab9bed_994c_45ec_8492_73c78af2ff56
0x1400064f5  mov     rax, [rax]
0x1400064f8  call    cs:__guard_dispatch_icall_fptr
0x1400064fe  mov     ebx, eax
0x140006500  mov     rcx, [rsp+170h+var_130]
0x140006505  jmp     loc_140006416
0x14000650a  mov     [rsp+170h+pExceptionObject], 8007000Eh
0x140006512  lea     rdx, _TI1J; pThrowInfo
0x140006519  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x14000651e  call    _CxxThrowException_0
```
