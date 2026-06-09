# sih::CompositeTransaction::CompositeTransaction(std::function<long (_GUID,wchar_t const *,wchar_t const *,int *)>,std::function<long (_GUID,wchar_t const *,wchar_t const *)>,std::function<void (sih::OperationType,sih::OperationState,_GUID const &,long)>,sih::Environment *,std::vector<_GUID,std::allocator<_GUID>>)

- ea: `0x140026e84`
- end: `0x14002706a`
- name: `??0CompositeTransaction@sih@@QEAA@V?$function@$$A6AJU_GUID@@PEB_W1PEAH@Z@std@@V?$function@$$A6AJU_GUID@@PEB_W1@Z@3@V?$function@$$A6AXW4OperationType@sih@@W4OperationState@2@AEBU_GUID@@J@Z@3@PEAVEnvironment@1@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@@Z`
- size: `486`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140020814`

## callees

- `0x14000cad4`
- `0x14001ed4c`
- `0x14002171c`
- `0x140026e84`
- `0x140045dc0`
- `0x1400481f8`
- `0x14004cd00`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140026f9e`
- `RPCRT4!UuidCreate` at `0x140026f9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sih::CompositeTransaction::CompositeTransaction(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 (__fastcall ***v10)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v11)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v12)(_QWORD, __int64); // rcx
  RPC_STATUS v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int v19; // edx
  _BYTE pExceptionObject[32]; // [rsp+48h] [rbp-80h] BYREF
  __int64 v21; // [rsp+68h] [rbp-60h]
  __int64 v22; // [rsp+70h] [rbp-58h]
  __int64 v23; // [rsp+78h] [rbp-50h]

  v21 = a2;
  v22 = a3;
  v23 = a4;
  *(_QWORD *)(a1 + 56) = 0;
  v10 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 56);
  if ( v10 )
    *(_QWORD *)(a1 + 56) = (**v10)(v10, a1);
  *(_QWORD *)(a1 + 120) = 0;
  v11 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a3 + 56);
  if ( v11 )
    *(_QWORD *)(a1 + 120) = (**v11)(v11, a1 + 64);
  *(_QWORD *)(a1 + 184) = 0;
  v12 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a4 + 56);
  if ( v12 )
    *(_QWORD *)(a1 + 184) = (**v12)(v12, a1 + 128);
  *(_DWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 216) = a5;
  *(GUID *)(a1 + 224) = GUID_NULL;
  std::vector<_GUID>::vector<_GUID>(a1 + 240, a6);
  *(_WORD *)(a1 + 264) = 0;
  v13 = UuidCreate((UUID *)(a1 + 196));
  if ( v13 )
  {
    v19 = (unsigned __int16)v13 | 0x80070000;
    if ( v13 <= 0 )
      v19 = v13;
    sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, v19);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v15 = *(_QWORD *)(a2 + 56);
  if ( v15 )
  {
    LOBYTE(v14) = v15 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 32LL))(v15, v14);
    *(_QWORD *)(a2 + 56) = 0;
  }
  v16 = *(_QWORD *)(a3 + 56);
  if ( v16 )
  {
    LOBYTE(v14) = v16 != a3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 32LL))(v16, v14);
    *(_QWORD *)(a3 + 56) = 0;
  }
  v17 = *(_QWORD *)(a4 + 56);
  if ( v17 )
  {
    LOBYTE(v14) = v17 != a4;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 32LL))(v17, v14);
    *(_QWORD *)(a4 + 56) = 0;
  }
  std::vector<_GUID>::~vector<_GUID>(a6);
  return a1;
}

```

## disassembly

```asm
0x140026e84  push    rbx
0x140026e86  push    rbp
0x140026e87  push    rsi
0x140026e88  push    rdi
0x140026e89  push    r14
0x140026e8b  push    r15
0x140026e8d  sub     rsp, 98h
0x140026e94  mov     rax, cs:__security_cookie
0x140026e9b  xor     rax, rsp
0x140026e9e  mov     [rsp+0C8h+var_48], rax
0x140026ea6  mov     rdi, r9
0x140026ea9  mov     rsi, r8
0x140026eac  mov     r14, rdx
0x140026eaf  mov     rbx, rcx
0x140026eb2  mov     [rsp+0C8h+var_98], rcx
0x140026eb7  mov     [rsp+0C8h+var_60], rdx
0x140026ebc  mov     [rsp+0C8h+var_58], r8
0x140026ec1  mov     [rsp+0C8h+var_50], r9
0x140026ec6  mov     r15, [rsp+0C8h+arg_28]
0x140026ece  mov     [rsp+0C8h+var_88], r15
0x140026ed3  mov     [rsp+0C8h+var_A8], rcx
0x140026ed8  mov     qword ptr [rcx+38h], 0
0x140026ee0  mov     rcx, [rdx+38h]
0x140026ee4  test    rcx, rcx
0x140026ee7  jz      short loc_140026EFB
0x140026ee9  mov     rax, [rcx]
0x140026eec  mov     rdx, rbx
0x140026eef  mov     rax, [rax]
0x140026ef2  call    _guard_dispatch_icall
0x140026ef7  mov     [rbx+38h], rax
0x140026efb  lea     rbp, [rbx+40h]
0x140026eff  mov     [rsp+0C8h+var_A8], rbp
0x140026f04  mov     qword ptr [rbp+38h], 0
0x140026f0c  mov     rcx, [rsi+38h]
0x140026f10  test    rcx, rcx
0x140026f13  jz      short loc_140026F27
0x140026f15  mov     rax, [rcx]
0x140026f18  mov     rdx, rbp
0x140026f1b  mov     rax, [rax]
0x140026f1e  call    _guard_dispatch_icall
0x140026f23  mov     [rbp+38h], rax
0x140026f27  lea     rbp, [rbx+80h]
0x140026f2e  mov     [rsp+0C8h+var_A8], rbp
0x140026f33  mov     qword ptr [rbp+38h], 0
0x140026f3b  mov     rcx, [rdi+38h]
0x140026f3f  test    rcx, rcx
0x140026f42  jz      short loc_140026F56
0x140026f44  mov     rax, [rcx]
0x140026f47  mov     rdx, rbp
0x140026f4a  mov     rax, [rax]
0x140026f4d  call    _guard_dispatch_icall
0x140026f52  mov     [rbp+38h], rax
0x140026f56  mov     dword ptr [rbx+0C0h], 0
0x140026f60  mov     rax, [rsp+0C8h+arg_20]
0x140026f68  mov     [rbx+0D8h], rax
0x140026f6f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140026f76  movdqu  xmmword ptr [rbx+0E0h], xmm0
0x140026f7e  lea     rcx, [rbx+0F0h]
0x140026f85  mov     rdx, r15
0x140026f88  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<_GUID>::vector<_GUID>(std::vector<_GUID> const &)
0x140026f8d  nop
0x140026f8e  mov     word ptr [rbx+108h], 0
0x140026f97  lea     rcx, [rbx+0C4h]; Uuid
0x140026f9e  call    cs:__imp_UuidCreate
0x140026fa4  test    eax, eax
0x140026fa6  jnz     loc_140027040
0x140026fac  mov     rcx, [r14+38h]
0x140026fb0  test    rcx, rcx
0x140026fb3  jz      short loc_140026FCF
0x140026fb5  cmp     rcx, r14
0x140026fb8  setnz   dl
0x140026fbb  mov     rax, [rcx]
0x140026fbe  mov     rax, [rax+20h]
0x140026fc2  call    _guard_dispatch_icall
0x140026fc7  mov     qword ptr [r14+38h], 0
0x140026fcf  mov     rcx, [rsi+38h]
0x140026fd3  test    rcx, rcx
0x140026fd6  jz      short loc_140026FF2
0x140026fd8  cmp     rcx, rsi
0x140026fdb  setnz   dl
0x140026fde  mov     rax, [rcx]
0x140026fe1  mov     rax, [rax+20h]
0x140026fe5  call    _guard_dispatch_icall
0x140026fea  mov     qword ptr [rsi+38h], 0
0x140026ff2  mov     rcx, [rdi+38h]
0x140026ff6  test    rcx, rcx
0x140026ff9  jz      short loc_140027015
0x140026ffb  cmp     rcx, rdi
0x140026ffe  setnz   dl
0x140027001  mov     r8, [rcx]
0x140027004  mov     rax, [r8+20h]
0x140027008  call    _guard_dispatch_icall
0x14002700d  mov     qword ptr [rdi+38h], 0
0x140027015  mov     rcx, r15
0x140027018  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x14002701d  mov     rax, rbx
0x140027020  mov     rcx, [rsp+0C8h+var_48]
0x140027028  xor     rcx, rsp; StackCookie
0x14002702b  call    __security_check_cookie
0x140027030  add     rsp, 98h
0x140027037  pop     r15
0x140027039  pop     r14
0x14002703b  pop     rdi
0x14002703c  pop     rsi
0x14002703d  pop     rbp
0x14002703e  pop     rbx
0x14002703f  retn
0x140027040  movzx   edx, ax
0x140027043  or      edx, 80070000h
0x140027049  test    eax, eax
0x14002704b  cmovle  edx, eax; int
0x14002704e  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x140027053  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x140027058  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x14002705f  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x140027064  call    _CxxThrowException
```
