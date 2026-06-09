# CPersistDSO::GetPropertyInfo(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPINFOSET * *,ushort * *)

- ea: `0x1800144b0`
- end: `0x1800145d6`
- name: `?GetPropertyInfo@CPersistDSO@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPINFOSET@@PEAPEAG@Z`
- size: `294`
- prototype: `int(CPersistDSO *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPINFOSET **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800144b0`
- `0x180015fb4`
- `0x18002aed4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800144f8`
- `KERNEL32!GetCurrentThreadId` at `0x1800144f8`
- `KERNEL32!LeaveCriticalSection` at `0x1800145b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800145b3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014517`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014517`
- `MSDART!UMSEnterCSWraper` at `0x1800144e4`
- `MSDART!UMSEnterCSWraper` at `0x1800144e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::GetPropertyInfo(
        CPersistDSO *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPINFOSET **a5,
        unsigned __int16 **a6)
{
  CPersistDSO *v9; // rbx
  _QWORD *v10; // r14
  _DWORD *v11; // rdi
  _DWORD *v12; // rsi
  int PropertyInfo; // eax
  unsigned int v14; // r15d
  __int64 v16; // rcx
  int v19; // [rsp+40h] [rbp-58h]
  int v20; // [rsp+40h] [rbp-58h]
  int v21; // [rsp+44h] [rbp-54h] BYREF
  char *v22; // [rsp+48h] [rbp-50h]
  _DWORD *v23; // [rsp+50h] [rbp-48h]
  _DWORD *v24; // [rsp+58h] [rbp-40h]
  _QWORD *v25; // [rsp+60h] [rbp-38h]

  v9 = this;
  v10 = (_QWORD *)((char *)this + 48);
  v22 = (char *)this + 48;
  UMSEnterCSWraper((char *)this + 48);
  v11 = (_DWORD *)((char *)v9 + 60);
  v23 = (_DWORD *)((char *)v9 + 60);
  if ( !*((_DWORD *)v9 + 15) )
    *((_DWORD *)v9 + 14) = GetCurrentThreadId();
  ++*v11;
  v12 = (_DWORD *)((char *)v9 + 64);
  v24 = (_DWORD *)((char *)v9 + 64);
  ++*((_DWORD *)v9 + 16);
  v25 = v10;
  SetErrorInfo(0, 0);
  try
  {
    *((GUID *)v9 + 6) = IID_IDBProperties;
    *((_DWORD *)v9 + 1053) = 0;
    PropertyInfo = CUtlPropInfo::GetPropertyInfo(
                     (CPersistDSO *)((char *)v9 + 4728),
                     a2,
                     a3,
                     a4,
                     a5,
                     a6,
                     (CPersistDSO *)((char *)v9 + 4584));
  }
  catch ( long v21 )
  {
    v19 = v21;
    v12 = v24;
    v11 = v23;
    v10 = v22;
    PropertyInfo = v19;
    v9 = this;
  }
  catch ( ... )
  {
    v20 = -2147467259;
    v12 = v24;
    v11 = v23;
    v10 = v22;
    PropertyInfo = v20;
    v9 = this;
  }
  v14 = Exit(PropertyInfo, 0xBB9u);
  --*v12;
  if ( (*v11)-- == 1 )
    *((_DWORD *)v9 + 14) = -1;
  v16 = *v10;
  --*(_DWORD *)(v16 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 8));
  return v14;
}

```

## disassembly

```asm
0x1800144b0  mov     [rsp+arg_8], rbx
0x1800144b5  mov     [rsp+arg_10], rsi
0x1800144ba  mov     [rsp+arg_0], rcx
0x1800144bf  push    rdi
0x1800144c0  push    r12
0x1800144c2  push    r13
0x1800144c4  push    r14
0x1800144c6  push    r15
0x1800144c8  sub     rsp, 70h
0x1800144cc  mov     r15, r9
0x1800144cf  mov     r12, r8
0x1800144d2  mov     r13d, edx
0x1800144d5  mov     rbx, rcx
0x1800144d8  lea     r14, [rcx+30h]
0x1800144dc  mov     [rsp+98h+var_50], r14
0x1800144e1  mov     rcx, r14
0x1800144e4  call    cs:__imp_UMSEnterCSWraper
0x1800144ea  lea     rdi, [rbx+3Ch]
0x1800144ee  mov     [rsp+98h+var_48], rdi
0x1800144f3  cmp     dword ptr [rdi], 0
0x1800144f6  jnz     short loc_180014501
0x1800144f8  call    cs:__imp_GetCurrentThreadId
0x1800144fe  mov     [rbx+38h], eax
0x180014501  inc     dword ptr [rdi]
0x180014503  lea     rsi, [rbx+40h]
0x180014507  mov     [rsp+98h+var_40], rsi
0x18001450c  inc     dword ptr [rsi]
0x18001450e  mov     [rsp+98h+var_38], r14
0x180014513  xor     edx, edx; perrinfo
0x180014515  xor     ecx, ecx; dwReserved
0x180014517  call    cs:__imp_SetErrorInfo
0x18001451d  movups  xmm0, xmmword ptr cs:IID_IDBProperties.Data1
0x180014524  movdqu  xmmword ptr [rbx+60h], xmm0
0x180014529  mov     dword ptr [rbx+1074h], 0
0x180014533  lea     rax, [rbx+11E8h]
0x18001453a  lea     rcx, [rbx+1278h]; this
0x180014541  mov     [rsp+98h+var_68], rax; struct CBidGenericBase *
0x180014546  mov     rax, [rsp+98h+arg_28]
0x18001454e  mov     [rsp+98h+var_70], rax; unsigned __int16 **
0x180014553  mov     rax, [rsp+98h+arg_20]
0x18001455b  mov     [rsp+98h+var_78], rax; struct tagDBPROPINFOSET **
0x180014560  mov     r9, r15; unsigned int *
0x180014563  mov     r8, r12; struct tagDBPROPIDSET *
0x180014566  mov     edx, r13d; unsigned int
0x180014569  call    ?GetPropertyInfo@CUtlPropInfo@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPINFOSET@@PEAPEAGAEBVCBidGenericBase@@@Z; CUtlPropInfo::GetPropertyInfo(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPINFOSET * *,ushort * *,CBidGenericBase const &)
0x18001456e  nop
0x18001456f  jmp     short loc_18001458E
0x180014571  jmp     short $+2
0x180014573  mov     rsi, [rsp+98h+var_40]
0x180014578  mov     rdi, [rsp+98h+var_48]
0x18001457d  mov     r14, [rsp+98h+var_50]
0x180014582  mov     eax, [rsp+98h+var_58]
0x180014586  mov     rbx, [rsp+98h+arg_0]
0x18001458e  mov     edx, 0BB9h; unsigned int
0x180014593  mov     ecx, eax; int
0x180014595  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001459a  mov     r15d, eax
0x18001459d  or      eax, 0FFFFFFFFh
0x1800145a0  add     [rsi], eax
0x1800145a2  add     [rdi], eax
0x1800145a4  jnz     short loc_1800145A9
0x1800145a6  mov     [rbx+38h], eax
0x1800145a9  mov     rcx, [r14]
0x1800145ac  dec     dword ptr [rcx+30h]
0x1800145af  add     rcx, 8; lpCriticalSection
0x1800145b3  call    cs:__imp_LeaveCriticalSection
0x1800145b9  mov     eax, r15d
0x1800145bc  lea     r11, [rsp+98h+var_28]
0x1800145c1  mov     rbx, [r11+38h]
0x1800145c5  mov     rsi, [r11+40h]
0x1800145c9  mov     rsp, r11
0x1800145cc  pop     r15
0x1800145ce  pop     r14
0x1800145d0  pop     r13
0x1800145d2  pop     r12
0x1800145d4  pop     rdi
0x1800145d5  retn
```
