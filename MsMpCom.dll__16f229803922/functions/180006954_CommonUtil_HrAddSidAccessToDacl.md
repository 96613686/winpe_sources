# CommonUtil::HrAddSidAccessToDacl

- ea: `0x180006954`
- end: `0x180006a25`
- name: `CommonUtil::HrAddSidAccessToDacl`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006a2c`

## callees

- `0x180006954`
- `0x18000a010`

## import_xrefs

- `mpclient!MpUtilsExportFunctions` at `0x180006970`
- `mpclient!MpUtilsExportFunctions` at `0x180006970`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrAddSidAccessToDacl(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  int v7; // edi
  volatile signed __int32 *v8; // r8
  volatile signed __int32 *v10; // [rsp+30h] [rbp-38h] BYREF

  v10 = 0;
  v6 = MpUtilsExportFunctions();
  v7 = (*(__int64 (__fastcall **)(volatile signed __int32 **, _QWORD))(v6 + 216))(&v10, 0);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64, _DWORD))(*(_QWORD *)v10 + 32LL))(
           v10,
           a3,
           0x80000000LL,
           1,
           0);
    if ( v7 >= 0 )
      v7 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, __int64))(*(_QWORD *)v10 + 8LL))(v10, a1, a2);
  }
  v8 = v10;
  if ( v10 )
  {
    if ( *((_DWORD *)v10 + 2) == 1 )
    {
      *((_DWORD *)v10 + 2) = 0;
    }
    else if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) > 1 )
    {
      return (unsigned int)v7;
    }
    if ( v8 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v8)(v8, 1);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006954  push    rbp
0x180006956  push    rsi
0x180006957  push    rdi
0x180006958  push    r14
0x18000695a  sub     rsp, 48h
0x18000695e  mov     rsi, r8
0x180006961  mov     [rsp+68h+var_38], 0
0x18000696a  mov     rbp, rdx
0x18000696d  mov     r14, rcx
0x180006970  call    cs:__imp_MpUtilsExportFunctions
0x180006976  xor     edx, edx
0x180006978  lea     rcx, [rsp+68h+var_38]
0x18000697d  mov     rax, [rax+0D8h]
0x180006984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006989  mov     edi, eax
0x18000698b  test    eax, eax
0x18000698d  js      short loc_1800069D6
0x18000698f  mov     rcx, [rsp+68h+var_38]
0x180006994  mov     r9d, 1
0x18000699a  mov     r8d, 80000000h
0x1800069a0  mov     [rsp+68h+var_48], 0
0x1800069a8  mov     rdx, rsi
0x1800069ab  mov     rax, [rcx]
0x1800069ae  mov     rax, [rax+20h]
0x1800069b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b7  mov     edi, eax
0x1800069b9  test    eax, eax
0x1800069bb  js      short loc_1800069D6
0x1800069bd  mov     rcx, [rsp+68h+var_38]
0x1800069c2  mov     r8, rbp
0x1800069c5  mov     rdx, r14
0x1800069c8  mov     rax, [rcx]
0x1800069cb  mov     rax, [rax+8]
0x1800069cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d4  mov     edi, eax
0x1800069d6  mov     r8, [rsp+68h+var_38]
0x1800069db  test    r8, r8
0x1800069de  jz      short loc_180006A19
0x1800069e0  mov     ecx, [r8+8]
0x1800069e4  cmp     ecx, 1
0x1800069e7  jnz     short loc_1800069F3
0x1800069e9  mov     dword ptr [r8+8], 0
0x1800069f1  jmp     short loc_180006A01
0x1800069f3  or      eax, 0FFFFFFFFh
0x1800069f6  lock xadd [r8+8], eax
0x1800069fc  sub     eax, 1
0x1800069ff  jg      short loc_180006A19
0x180006a01  test    r8, r8
0x180006a04  jz      short loc_180006A19
0x180006a06  mov     rax, [r8]
0x180006a09  mov     edx, 1
0x180006a0e  mov     rcx, r8
0x180006a11  mov     rax, [rax]
0x180006a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a19  mov     eax, edi
0x180006a1b  add     rsp, 48h
0x180006a1f  pop     r14
0x180006a21  pop     rdi
0x180006a22  pop     rsi
0x180006a23  pop     rbp
0x180006a24  retn
```
