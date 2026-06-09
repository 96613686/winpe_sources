# CEventSysTier2Factory::CreateInstanceForDomain(ushort const *,_GUID const &,void * *)

- ea: `0x180021b30`
- end: `0x180021c2a`
- name: `?CreateInstanceForDomain@CEventSysTier2Factory@@UEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `250`
- prototype: `int(CEventSysTier2Factory *__hidden this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012654`
- `0x180021b30`
- `0x180034588`
- `0x18003ecb0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044d70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021b9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021b9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021bc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021bc9`

## string_xrefs

- `0x180021b8c`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
__int64 __fastcall CEventSysTier2Factory::CreateInstanceForDomain(
        CEventSysTier2Factory *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  CEventSystem2 *v9; // rax
  unsigned int v11; // [rsp+20h] [rbp-28h]

  if ( a4 )
  {
    *a4 = 0;
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    if ( !*((_DWORD *)this + 14) )
      InternalAssert(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x12Eu, 0x10u, L"m_fInitialized");
    EnterCriticalSection(v8);
    if ( !*((_QWORD *)this + 8) )
    {
      v9 = (CEventSystem2 *)CoTaskMemAlloc(0x198u);
      if ( v9 )
        v9 = CEventSystem2::CEventSystem2(v9, a2);
      *((_QWORD *)this + 8) = v9;
      if ( !v9 )
      {
        v11 = -2147024882;
        goto LABEL_11;
      }
      _InterlockedIncrement(&g_tier2ActiveObjects);
    }
    v11 = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 8))(
            *((_QWORD *)this + 8),
            a3,
            a4);
LABEL_11:
    LeaveCriticalSection(v8);
    return v11;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180021b30  mov     rax, rsp
0x180021b33  mov     [rax+10h], rbx
0x180021b37  mov     [rax+18h], rsi
0x180021b3b  mov     [rax+8], rcx
0x180021b3f  push    rdi
0x180021b40  push    r14
0x180021b42  push    r15
0x180021b44  sub     rsp, 30h
0x180021b48  mov     rsi, r9
0x180021b4b  mov     r15, r8
0x180021b4e  mov     r14, rdx
0x180021b51  mov     rdi, rcx
0x180021b54  test    r9, r9
0x180021b57  jz      loc_180021C23
0x180021b5d  mov     qword ptr [r9], 0
0x180021b64  mov     dword ptr [rax-28h], 0
0x180021b6b  lea     rbx, [rcx+10h]
0x180021b6f  mov     [rsp+48h+arg_18], rbx
0x180021b74  cmp     dword ptr [rbx+28h], 0
0x180021b78  jnz     short loc_180021B98
0x180021b7a  mov     r8d, 10h; unsigned __int16
0x180021b80  lea     r9, aMFinitialized; "m_fInitialized"
0x180021b87  mov     edx, 12Eh; unsigned int
0x180021b8c  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x180021b93  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180021b98  mov     rcx, rbx; lpCriticalSection
0x180021b9b  call    cs:__imp_EnterCriticalSection
0x180021ba1  nop
0x180021ba2  cmp     qword ptr [rdi+40h], 0
0x180021ba7  jz      short loc_180021BC4
0x180021ba9  mov     rcx, [rdi+40h]
0x180021bad  mov     rax, [rcx]
0x180021bb0  mov     r8, rsi
0x180021bb3  mov     rdx, r15
0x180021bb6  mov     rax, [rax]
0x180021bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bbe  mov     [rsp+48h+var_28], eax
0x180021bc2  jmp     short loc_180021BFB
0x180021bc4  mov     ecx, 198h; cb
0x180021bc9  call    cs:__imp_CoTaskMemAlloc
0x180021bcf  test    rax, rax
0x180021bd2  jz      short loc_180021BDF
0x180021bd4  mov     rdx, r14; unsigned __int16 *
0x180021bd7  mov     rcx, rax; this
0x180021bda  call    ??0CEventSystem2@@QEAA@PEBG@Z; CEventSystem2::CEventSystem2(ushort const *)
0x180021bdf  mov     [rdi+40h], rax
0x180021be3  test    rax, rax
0x180021be6  jnz     short loc_180021BF2
0x180021be8  mov     [rsp+48h+var_28], 8007000Eh
0x180021bf0  jmp     short loc_180021BFB
0x180021bf2  lock inc cs:?g_tier2ActiveObjects@@3JA; long g_tier2ActiveObjects
0x180021bf9  jmp     short loc_180021BA9
0x180021bfb  jmp     short loc_180021C02
0x180021bfd  mov     rbx, [rsp+48h+arg_18]
0x180021c02  mov     rcx, rbx; lpCriticalSection
0x180021c05  call    cs:__imp_LeaveCriticalSection
0x180021c0b  mov     eax, [rsp+48h+var_28]
0x180021c0f  mov     rbx, [rsp+48h+arg_8]
0x180021c14  mov     rsi, [rsp+48h+arg_10]
0x180021c19  add     rsp, 30h
0x180021c1d  pop     r15
0x180021c1f  pop     r14
0x180021c21  pop     rdi
0x180021c22  retn
0x180021c23  mov     eax, 80004003h
0x180021c28  jmp     short loc_180021C0F
0x180044d40  push    rbp
0x180044d42  sub     rsp, 20h
0x180044d46  mov     rbp, rdx
0x180044d49  lea     rdx, [rbp+20h]; int *
0x180044d4d  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180044d52  nop
0x180044d53  add     rsp, 20h
0x180044d57  pop     rbp
0x180044d58  retn
0x180044d5a  push    rbp
0x180044d5c  sub     rsp, 20h
0x180044d60  mov     rbp, rdx
0x180044d63  mov     rcx, [rbp+50h]
0x180044d67  add     rcx, 10h
0x180044d6b  add     rsp, 20h
0x180044d6f  pop     rbp
0x180044d70  jmp     cs:__imp_LeaveCriticalSection
```
