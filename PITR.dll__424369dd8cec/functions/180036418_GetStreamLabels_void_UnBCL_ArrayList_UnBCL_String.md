# GetStreamLabels(void *,UnBCL::ArrayList<UnBCL::String *> *)

- ea: `0x180036418`
- end: `0x18003661e`
- name: `?GetStreamLabels@@YAJPEAXPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(HANDLE FileHandle, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002fd88`

## callees

- `0x180036418`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036457`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036484`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036498`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800365e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036457`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036484`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036498`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800365e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800364a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800364a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036492`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800365ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036492`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800365ee`
- `ntdll!NtQueryInformationFile` at `0x1800364cd`
- `ntdll!NtQueryInformationFile` at `0x1800364cd`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18003657c`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18003657c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800364e3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800364e3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180036541`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180036541`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180036557`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180036557`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003652c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003652c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800365c5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800365d5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800365c5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800365d5`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18003659c`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18003659c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180036538`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180036566`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180036538`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180036566`
- `unbcl!??0String@UnBCL@@QEAA@PEBGHH@Z` at `0x180036507`
- `unbcl!??0String@UnBCL@@QEAA@PEBGHH@Z` at `0x180036507`

## pseudocode

```c
__int64 __fastcall GetStreamLabels(HANDLE FileHandle, __int64 a2)
{
  HANDLE ProcessHeap; // rax
  SIZE_T v5; // rdi
  unsigned int v6; // esi
  HANDLE v7; // rax
  unsigned int *v8; // rax
  unsigned int *v9; // rbp
  NTSTATUS v10; // esi
  const unsigned __int16 *v11; // r14
  UnBCL::String *v12; // rax
  UnBCL::String *v13; // rbx
  UnBCL::String *v14; // rax
  const unsigned __int16 *CString; // rax
  UnBCL::String *v16; // rax
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, __int64); // rbx
  __int64 v19; // rax
  HANDLE v20; // rax
  _BYTE v22[16]; // [rsp+38h] [rbp-50h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-40h] BYREF

  IoStatusBlock = 0;
  if ( FileHandle && a2 )
  {
    ProcessHeap = GetProcessHeap();
    v5 = 0x10000;
    while ( 1 )
    {
      v8 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v5);
      v9 = v8;
      if ( !v8 )
        return (unsigned int)-2147024888;
      v10 = NtQueryInformationFile(FileHandle, &IoStatusBlock, v8, v5, FileStreamInformation);
      if ( !v10 )
        break;
      if ( v10 != -2147483643 && v10 != -1073741820 )
      {
        v6 = v10 | 0x10000000;
        goto LABEL_21;
      }
      v5 = (unsigned int)(2 * v5);
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v9);
      ProcessHeap = GetProcessHeap();
    }
    v6 = 0;
    v11 = (const unsigned __int16 *)v9;
    while ( 1 )
    {
      v12 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v13 = v12;
      if ( v12 )
      {
        UnBCL::String::String(v12, v11 + 12, 0, *((_DWORD *)v11 + 1) >> 1);
        *(_QWORD *)v13 = &UnBCL::String::`local vftable';
      }
      else
      {
        v13 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v22, v13);
      v14 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v22);
      CString = UnBCL::String::get_CString(v14);
      if ( UnBCL::String::Compare(CString, L"::$DATA", 1) )
      {
        v16 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v22);
        if ( UnBCL::String::EndsWith(v16, L":$DATA", 1) )
        {
          v17 = *(int *)(*(_QWORD *)(a2 + 8) + 16LL);
          v18 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v17 + a2 + 8) + 40LL);
          v19 = UnBCL::SmartPtr<UnBCL::String>::Steal(v22);
          v18(v17 + a2 + 8, v19);
        }
      }
      if ( !*(_DWORD *)v11 )
        break;
      v11 = (const unsigned __int16 *)((char *)v11 + *(unsigned int *)v11);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v22);
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v22);
LABEL_21:
    if ( v9 )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v9);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180036418  mov     [rsp+arg_10], rbx
0x18003641d  push    rbp
0x18003641e  push    rsi
0x18003641f  push    rdi
0x180036420  push    r14
0x180036422  push    r15
0x180036424  sub     rsp, 60h
0x180036428  mov     rax, cs:__security_cookie
0x18003642f  xor     rax, rsp
0x180036432  mov     [rsp+88h+var_30], rax
0x180036437  mov     r15, rdx
0x18003643a  mov     r14, rcx
0x18003643d  xorps   xmm0, xmm0
0x180036440  movups  xmmword ptr [rsp+88h+IoStatusBlock], xmm0
0x180036445  test    rcx, rcx
0x180036448  jz      loc_1800365F6
0x18003644e  test    rdx, rdx
0x180036451  jz      loc_1800365F6
0x180036457  call    cs:__imp_GetProcessHeap
0x18003645d  mov     edi, 10000h
0x180036462  jmp     short loc_18003649E
0x180036464  mov     esi, 80070008h
0x180036469  jmp     loc_1800365FB
0x18003646e  cmp     esi, 80000005h
0x180036474  jz      short loc_180036482
0x180036476  cmp     esi, 0C0000004h
0x18003647c  jnz     loc_180036519
0x180036482  add     edi, edi
0x180036484  call    cs:__imp_GetProcessHeap
0x18003648a  mov     rcx, rax; hHeap
0x18003648d  mov     r8, rbp; lpMem
0x180036490  xor     edx, edx; dwFlags
0x180036492  call    cs:__imp_HeapFree
0x180036498  call    cs:__imp_GetProcessHeap
0x18003649e  mov     r8, rdi; dwBytes
0x1800364a1  mov     edx, 8; dwFlags
0x1800364a6  mov     rcx, rax; hHeap
0x1800364a9  call    cs:__imp_HeapAlloc
0x1800364af  test    rax, rax
0x1800364b2  mov     rbp, rax
0x1800364b5  jz      short loc_180036464
0x1800364b7  mov     [rsp+88h+FileInformationClass], 16h; FileInformationClass
0x1800364bf  mov     r9d, edi; Length
0x1800364c2  mov     r8, rax; FileInformation
0x1800364c5  lea     rdx, [rsp+88h+IoStatusBlock]; IoStatusBlock
0x1800364ca  mov     rcx, r14; FileHandle
0x1800364cd  call    cs:__imp_NtQueryInformationFile
0x1800364d3  test    eax, eax
0x1800364d5  mov     esi, eax
0x1800364d7  jnz     short loc_18003646E
0x1800364d9  xor     esi, esi
0x1800364db  mov     r14, rbp
0x1800364de  mov     ecx, 18h
0x1800364e3  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800364e9  mov     rbx, rax
0x1800364ec  mov     [rsp+88h+var_58], rax
0x1800364f1  test    rax, rax
0x1800364f4  jz      short loc_180036522
0x1800364f6  mov     r9d, [r14+4]
0x1800364fa  shr     r9d, 1
0x1800364fd  lea     rdx, [r14+18h]
0x180036501  xor     r8d, r8d
0x180036504  mov     rcx, rax
0x180036507  call    cs:__imp_??0String@UnBCL@@QEAA@PEBGHH@Z; UnBCL::String::String(ushort const *,int,int)
0x18003650d  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180036514  mov     [rbx], rax
0x180036517  jmp     short loc_180036524
0x180036519  bts     esi, 1Ch
0x18003651d  jmp     loc_1800365DB
0x180036522  xor     ebx, ebx
0x180036524  mov     rdx, rbx
0x180036527  lea     rcx, [rsp+88h+var_50]
0x18003652c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180036532  nop
0x180036533  lea     rcx, [rsp+88h+var_50]
0x180036538  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18003653e  mov     rcx, rax
0x180036541  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180036547  mov     rcx, rax
0x18003654a  mov     r8d, 1
0x180036550  lea     rdx, aData; "::$DATA"
0x180036557  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x18003655d  test    eax, eax
0x18003655f  jz      short loc_1800365B4
0x180036561  lea     rcx, [rsp+88h+var_50]
0x180036566  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18003656c  mov     r8d, 1
0x180036572  lea     rdx, aData_0; ":$DATA"
0x180036579  mov     rcx, rax
0x18003657c  call    cs:__imp_?EndsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::EndsWith(ushort const *,int)
0x180036582  test    eax, eax
0x180036584  jz      short loc_1800365B4
0x180036586  mov     rax, [r15+8]
0x18003658a  movsxd  rdi, dword ptr [rax+10h]
0x18003658e  mov     rax, [rdi+r15+8]
0x180036593  mov     rbx, [rax+28h]
0x180036597  lea     rcx, [rsp+88h+var_50]
0x18003659c  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x1800365a2  mov     rdx, rax
0x1800365a5  lea     rcx, [r15+8]
0x1800365a9  add     rcx, rdi
0x1800365ac  mov     rax, rbx
0x1800365af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365b4  cmp     dword ptr [r14], 0
0x1800365b8  jz      short loc_1800365D0
0x1800365ba  mov     eax, [r14]
0x1800365bd  add     r14, rax
0x1800365c0  lea     rcx, [rsp+88h+var_50]
0x1800365c5  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800365cb  jmp     loc_1800364DE
0x1800365d0  lea     rcx, [rsp+88h+var_50]
0x1800365d5  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800365db  test    rbp, rbp
0x1800365de  jz      short loc_1800365FB
0x1800365e0  call    cs:__imp_GetProcessHeap
0x1800365e6  mov     rcx, rax; hHeap
0x1800365e9  mov     r8, rbp; lpMem
0x1800365ec  xor     edx, edx; dwFlags
0x1800365ee  call    cs:__imp_HeapFree
0x1800365f4  jmp     short loc_1800365FB
0x1800365f6  mov     esi, 80070057h
0x1800365fb  mov     eax, esi
0x1800365fd  mov     rcx, [rsp+88h+var_30]
0x180036602  xor     rcx, rsp; StackCookie
0x180036605  call    __security_check_cookie
0x18003660a  mov     rbx, [rsp+88h+arg_10]
0x180036612  add     rsp, 60h
0x180036616  pop     r15
0x180036618  pop     r14
0x18003661a  pop     rdi
0x18003661b  pop     rsi
0x18003661c  pop     rbp
0x18003661d  retn
```
