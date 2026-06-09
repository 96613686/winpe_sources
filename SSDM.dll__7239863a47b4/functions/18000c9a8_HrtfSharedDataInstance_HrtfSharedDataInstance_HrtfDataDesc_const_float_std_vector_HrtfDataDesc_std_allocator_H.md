# HrtfSharedDataInstance::HrtfSharedDataInstance(HrtfDataDesc const &,float,std::vector<HrtfDataDesc,std::allocator<HrtfDataDesc>> const &)

- ea: `0x18000c9a8`
- end: `0x18000cd81`
- name: `??0HrtfSharedDataInstance@@QEAA@AEBUHrtfDataDesc@@MAEBV?$vector@UHrtfDataDesc@@V?$allocator@UHrtfDataDesc@@@std@@@std@@@Z`
- size: `985`
- prototype: `__int64 __fastcall(__int64, __int64, float, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180005ec0`

## callees

- `0x180002a88`
- `0x1800056e4`
- `0x180007468`
- `0x18000757c`
- `0x18000c610`
- `0x18000c8c4`
- `0x18000c9a8`
- `0x18000cd88`
- `0x18000d400`
- `0x18000d654`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc71`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ccf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ccf2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ccc0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ccc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ccea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cd0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ccea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cd0a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000cc55`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000cc55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd27`

## pseudocode

```c
__int64 __fastcall HrtfSharedDataInstance::HrtfSharedDataInstance(__int64 a1, __int64 a2, float a3, __int64 *a4)
{
  __int64 *v7; // rsi
  const char *v8; // r9
  char v9; // al
  void *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rdi
  void *v16; // rax
  __int64 v17; // r12
  unsigned __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r15
  __int64 v21; // r8
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // r9
  unsigned __int64 v24; // rdx
  __int64 v25; // r8
  _QWORD *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r15
  __int64 v29; // r9
  __int64 v30; // r8
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // r9
  unsigned __int64 v33; // rdx
  const void *v34; // rcx
  char *v35; // rdi
  const char *v36; // r9
  void *v37; // rsi
  DWORD LastError; // ebx
  HLOCAL v39; // rcx
  __int64 v41; // [rsp+20h] [rbp-60h] BYREF
  void *v42; // [rsp+28h] [rbp-58h]
  char v43; // [rsp+30h] [rbp-50h] BYREF
  __int128 v44; // [rsp+38h] [rbp-48h] BYREF
  __int64 v45; // [rsp+48h] [rbp-38h]
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  HLOCAL hMem; // [rsp+C8h] [rbp+48h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v7 = (__int64 *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 56) = std::_List_alloc<0,std::_List_base_types<unsigned long const>>::_Buynode0(a1, 0, 0);
  *(_QWORD *)(a1 + 72) = 0;
  if ( *(_QWORD *)(a2 + 40) == *(_QWORD *)(a2 + 32) || (v9 = 0, !(0x6DB6DB6DB6DB6DB7LL * ((a4[1] - *a4) >> 3))) )
    v9 = 1;
  if ( v9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x37,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v8);
  *(float *)(a1 + 8) = a3;
  v10 = operator new(0x18u);
  v42 = v10;
  if ( v10 )
    v12 = SharedMemory::SharedMemory(v10, a2 + 32);
  else
    v12 = 0;
  v44 = 0;
  v42 = 0;
  LOBYTE(v11) = v12;
  std::shared_ptr<SharedMemory>::_Resetp<SharedMemory,std::default_delete<SharedMemory>>(&v44, v12, v11);
  v13 = *(volatile signed __int32 **)(a1 + 24);
  *(_OWORD *)(a1 + 16) = v44;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v14 = *a4;
  v15 = a4[1];
  while ( v14 != v15 )
  {
    v16 = operator new(0x18u);
    v42 = v16;
    if ( v16 )
      v17 = SharedMemory::SharedMemory(v16, v14 + 32);
    else
      v17 = 0;
    v41 = v17;
    v18 = v7[1];
    if ( (unsigned __int64)&v41 >= v18 || *v7 > (unsigned __int64)&v41 )
    {
      v29 = v7[2];
      if ( v18 == v29 && !((__int64)(v29 - v18) >> 3) )
      {
        v30 = (__int64)(v18 - *v7) >> 3;
        if ( v30 == 0x1FFFFFFFFFFFFFFFLL )
          std::vector<unsigned char *>::_Xlen();
        v31 = v30 + 1;
        v32 = (v29 - *v7) >> 3;
        v33 = 0;
        if ( 0x1FFFFFFFFFFFFFFFLL - (v32 >> 1) >= v32 )
          v33 = v32 + (v32 >> 1);
        if ( v33 < v31 )
          v33 = v31;
        std::vector<std::unique_ptr<SharedMemory>>::_Reallocate(v7, v33);
      }
      v28 = 0;
      *(_QWORD *)v7[1] = v17;
    }
    else
    {
      v19 = v7[2];
      v20 = *v7;
      if ( v18 == v19 && !((__int64)(v19 - v18) >> 3) )
      {
        v21 = (__int64)(v18 - v20) >> 3;
        if ( v21 == 0x1FFFFFFFFFFFFFFFLL )
          std::vector<unsigned char *>::_Xlen();
        v22 = v21 + 1;
        v23 = (v19 - v20) >> 3;
        v24 = 0;
        if ( 0x1FFFFFFFFFFFFFFFLL - (v23 >> 1) >= v23 )
          v24 = v23 + (v23 >> 1);
        if ( v24 < v22 )
          v24 = v22;
        std::vector<std::unique_ptr<SharedMemory>>::_Reallocate(v7, v24);
      }
      v25 = ((__int64)&v41 - v20) >> 3;
      v26 = (_QWORD *)v7[1];
      v27 = *(_QWORD *)(*v7 + 8 * v25);
      *(_QWORD *)(*v7 + 8 * v25) = 0;
      *v26 = v27;
      v28 = v41;
    }
    v7[1] += 8;
    if ( v28 )
    {
      v34 = *(const void **)(v28 + 8);
      if ( v34 )
        UnmapViewOfFile(v34);
      if ( (unsigned __int64)(*(_QWORD *)v28 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(*(HANDLE *)v28);
      operator delete((void *)v28);
    }
    v14 += 56;
  }
  GetSecurityDescriptor(&hMem);
  *(_QWORD *)&v44 = 24;
  v45 = 1;
  *((_QWORD *)&v44 + 1) = hMem;
  *(_OWORD *)&EventAttributes.nLength = v44;
  *(_QWORD *)&EventAttributes.bInheritHandle = 1;
  v35 = (char *)CreateEventW(&EventAttributes, 0, 0, 0);
  if ( (char *)a1 == &v43 )
  {
    if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v35);
  }
  else
  {
    v37 = *(void **)a1;
    if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v37);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v35;
  }
  if ( *(_QWORD *)a1 == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x45,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v36);
  v39 = hMem;
  hMem = 0;
  if ( v39 )
    LocalFree(v39);
  return a1;
}

```

## disassembly

```asm
0x18000c9a8  mov     [rsp-38h+arg_10], rbx
0x18000c9ad  mov     [rsp-38h+arg_0], rcx
0x18000c9b2  push    rbp
0x18000c9b3  push    rsi
0x18000c9b4  push    rdi
0x18000c9b5  push    r12
0x18000c9b7  push    r13
0x18000c9b9  push    r14
0x18000c9bb  push    r15
0x18000c9bd  mov     rbp, rsp
0x18000c9c0  sub     rsp, 80h
0x18000c9c7  movaps  [rsp+80h+var_10], xmm6
0x18000c9cc  mov     r15, r9
0x18000c9cf  movaps  xmm6, xmm2
0x18000c9d2  mov     rdi, rdx
0x18000c9d5  mov     r14, rcx
0x18000c9d8  xor     r13d, r13d
0x18000c9db  mov     [rcx], r13
0x18000c9de  mov     [rcx+8], r13d
0x18000c9e2  mov     [rcx+10h], r13
0x18000c9e6  mov     [rcx+18h], r13
0x18000c9ea  lea     rsi, [rcx+20h]
0x18000c9ee  mov     [rsi], r13
0x18000c9f1  mov     [rsi+8], r13
0x18000c9f5  mov     [rsi+10h], r13
0x18000c9f9  mov     [rcx+38h], r13
0x18000c9fd  mov     [rcx+40h], r13
0x18000ca01  xor     r8d, r8d
0x18000ca04  xor     edx, edx
0x18000ca06  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@$$CBKV?$allocator@$$CBK@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<ulong const>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)
0x18000ca0b  mov     [r14+38h], rax
0x18000ca0f  xor     eax, eax
0x18000ca11  mov     [r14+48h], rax
0x18000ca15  mov     rax, [rdi+28h]
0x18000ca19  cmp     rax, [rdi+20h]
0x18000ca1d  jz      short loc_18000CA40
0x18000ca1f  mov     rax, [r15+8]
0x18000ca23  sub     rax, [r15]
0x18000ca26  sar     rax, 3
0x18000ca2a  mov     rcx, 6DB6DB6DB6DB6DB7h
0x18000ca34  imul    rax, rcx
0x18000ca38  test    rax, rax
0x18000ca3b  mov     al, r13b
0x18000ca3e  jnz     short loc_18000CA42
0x18000ca40  mov     al, 1
0x18000ca42  mov     rcx, [rbp+38h]; this
0x18000ca46  test    al, al
0x18000ca48  jnz     loc_18000CD63
0x18000ca4e  movss   dword ptr [r14+8], xmm6
0x18000ca54  mov     ecx, 18h; Size
0x18000ca59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ca5e  mov     [rbp+var_58], rax
0x18000ca62  test    rax, rax
0x18000ca65  jz      short loc_18000CA75
0x18000ca67  lea     rdx, [rdi+20h]
0x18000ca6b  mov     rcx, rax
0x18000ca6e  call    ??0SharedMemory@@QEAA@AEBV?$vector@EV?$AlignedAllocator@E$0BA@@AlignedStore@@@std@@@Z; SharedMemory::SharedMemory(std::vector<uchar,AlignedStore::AlignedAllocator<uchar,16>> const &)
0x18000ca73  jmp     short loc_18000CA78
0x18000ca75  mov     rax, r13
0x18000ca78  xorps   xmm0, xmm0
0x18000ca7b  movdqu  [rbp+var_48], xmm0
0x18000ca80  mov     [rbp+var_58], r13
0x18000ca84  mov     r8b, al
0x18000ca87  mov     rdx, rax
0x18000ca8a  lea     rcx, [rbp+var_48]
0x18000ca8e  call    ??$_Resetp@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@?$shared_ptr@VSharedMemory@@@std@@AEAAXPEAVSharedMemory@@U?$default_delete@VSharedMemory@@@1@@Z; std::shared_ptr<SharedMemory>::_Resetp<SharedMemory,std::default_delete<SharedMemory>>(SharedMemory *,std::default_delete<SharedMemory>)
0x18000ca93  mov     rbx, [r14+18h]
0x18000ca97  mov     rax, qword ptr [rbp+var_48+8]
0x18000ca9b  mov     [r14+18h], rax
0x18000ca9f  mov     rax, qword ptr [rbp+var_48]
0x18000caa3  mov     [r14+10h], rax
0x18000caa7  test    rbx, rbx
0x18000caaa  jz      short loc_18000CAE4
0x18000caac  or      eax, 0FFFFFFFFh
0x18000caaf  lock xadd [rbx+8], eax
0x18000cab4  cmp     eax, 1
0x18000cab7  jnz     short loc_18000CAE4
0x18000cab9  mov     rax, [rbx]
0x18000cabc  mov     rcx, rbx
0x18000cabf  mov     rax, [rax]
0x18000cac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cac7  or      eax, 0FFFFFFFFh
0x18000caca  lock xadd [rbx+0Ch], eax
0x18000cacf  cmp     eax, 1
0x18000cad2  jnz     short loc_18000CAE4
0x18000cad4  mov     rax, [rbx]
0x18000cad7  mov     rcx, rbx
0x18000cada  mov     rax, [rax+8]
0x18000cade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cae3  nop
0x18000cae4  mov     rbx, [r15]
0x18000cae7  mov     rdi, [r15+8]
0x18000caeb  mov     r15, 1FFFFFFFFFFFFFFFh
0x18000caf5  cmp     rbx, rdi
0x18000caf8  jz      loc_18000CC80
0x18000cafe  mov     ecx, 18h; Size
0x18000cb03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cb08  mov     [rbp+var_58], rax
0x18000cb0c  test    rax, rax
0x18000cb0f  jz      short loc_18000CB22
0x18000cb11  lea     rdx, [rbx+20h]
0x18000cb15  mov     rcx, rax
0x18000cb18  call    ??0SharedMemory@@QEAA@AEBV?$vector@EV?$AlignedAllocator@E$0BA@@AlignedStore@@@std@@@Z; SharedMemory::SharedMemory(std::vector<uchar,AlignedStore::AlignedAllocator<uchar,16>> const &)
0x18000cb1d  mov     r12, rax
0x18000cb20  jmp     short loc_18000CB25
0x18000cb22  mov     r12, r13
0x18000cb25  mov     [rbp+var_60], r12
0x18000cb29  mov     r8, [rsi+8]
0x18000cb2d  lea     rax, [rbp+var_60]
0x18000cb31  cmp     rax, r8
0x18000cb34  jnb     loc_18000CBD6
0x18000cb3a  lea     rax, [rbp+var_60]
0x18000cb3e  cmp     [rsi], rax
0x18000cb41  ja      loc_18000CBD6
0x18000cb47  mov     r9, [rsi+10h]
0x18000cb4b  mov     r15, [rsi]
0x18000cb4e  cmp     r8, r9
0x18000cb51  jnz     short loc_18000CBB3
0x18000cb53  mov     rax, r9
0x18000cb56  sub     rax, r8
0x18000cb59  sar     rax, 3
0x18000cb5d  cmp     rax, 1
0x18000cb61  jnb     short loc_18000CBB3
0x18000cb63  sub     r8, r15
0x18000cb66  sar     r8, 3
0x18000cb6a  mov     rcx, 1FFFFFFFFFFFFFFFh
0x18000cb74  mov     rax, rcx
0x18000cb77  sub     rax, r8
0x18000cb7a  cmp     rax, 1
0x18000cb7e  jb      loc_18000CD75
0x18000cb84  inc     r8
0x18000cb87  sub     r9, r15
0x18000cb8a  sar     r9, 3
0x18000cb8e  mov     rax, r9
0x18000cb91  shr     rax, 1
0x18000cb94  sub     rcx, rax
0x18000cb97  add     rax, r9
0x18000cb9a  mov     rdx, r13
0x18000cb9d  cmp     rcx, r9
0x18000cba0  cmovnb  rdx, rax
0x18000cba4  cmp     rdx, r8
0x18000cba7  cmovb   rdx, r8
0x18000cbab  mov     rcx, rsi
0x18000cbae  call    ?_Reallocate@?$vector@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<SharedMemory>>::_Reallocate(unsigned __int64)
0x18000cbb3  lea     r8, [rbp+var_60]
0x18000cbb7  sub     r8, r15
0x18000cbba  sar     r8, 3
0x18000cbbe  mov     rdx, [rsi]
0x18000cbc1  mov     rcx, [rsi+8]
0x18000cbc5  mov     rax, [rdx+r8*8]
0x18000cbc9  mov     [rdx+r8*8], r13
0x18000cbcd  mov     [rcx], rax
0x18000cbd0  mov     r15, [rbp+var_60]
0x18000cbd4  jmp     short loc_18000CC42
0x18000cbd6  mov     r9, [rsi+10h]
0x18000cbda  cmp     r8, r9
0x18000cbdd  jnz     short loc_18000CC38
0x18000cbdf  mov     rax, r9
0x18000cbe2  sub     rax, r8
0x18000cbe5  sar     rax, 3
0x18000cbe9  cmp     rax, 1
0x18000cbed  jnb     short loc_18000CC38
0x18000cbef  sub     r8, [rsi]
0x18000cbf2  sar     r8, 3
0x18000cbf6  mov     rax, r15
0x18000cbf9  sub     rax, r8
0x18000cbfc  cmp     rax, 1
0x18000cc00  jb      loc_18000CD7B
0x18000cc06  inc     r8
0x18000cc09  sub     r9, [rsi]
0x18000cc0c  sar     r9, 3
0x18000cc10  mov     rax, r9
0x18000cc13  shr     rax, 1
0x18000cc16  mov     rcx, r15
0x18000cc19  sub     rcx, rax
0x18000cc1c  add     rax, r9
0x18000cc1f  mov     rdx, r13
0x18000cc22  cmp     rcx, r9
0x18000cc25  cmovnb  rdx, rax
0x18000cc29  cmp     rdx, r8
0x18000cc2c  cmovb   rdx, r8
0x18000cc30  mov     rcx, rsi
0x18000cc33  call    ?_Reallocate@?$vector@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@V?$allocator@V?$unique_ptr@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<SharedMemory>>::_Reallocate(unsigned __int64)
0x18000cc38  mov     r15, r13
0x18000cc3b  mov     rax, [rsi+8]
0x18000cc3f  mov     [rax], r12
0x18000cc42  add     qword ptr [rsi+8], 8
0x18000cc47  test    r15, r15
0x18000cc4a  jz      short loc_18000CC77
0x18000cc4c  mov     rcx, [r15+8]; lpBaseAddress
0x18000cc50  test    rcx, rcx
0x18000cc53  jz      short loc_18000CC5B
0x18000cc55  call    cs:__imp_UnmapViewOfFile
0x18000cc5b  mov     rcx, [r15]; hObject
0x18000cc5e  lea     rax, [rcx-1]
0x18000cc62  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cc66  ja      short loc_18000CC6E
0x18000cc68  call    cs:__imp_CloseHandle
0x18000cc6e  mov     rcx, r15
0x18000cc71  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cc77  add     rbx, 38h ; '8'
0x18000cc7b  jmp     loc_18000CAEB
0x18000cc80  lea     rcx, [rbp+hMem]
0x18000cc84  call    ?GetSecurityDescriptor@@YA?AV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@PEB_W@Z; GetSecurityDescriptor(wchar_t const *)
0x18000cc89  nop
0x18000cc8a  mov     qword ptr [rbp+var_48], 18h
0x18000cc92  mov     [rbp+var_38], 1
0x18000cc9a  mov     rax, [rbp+hMem]
0x18000cc9e  mov     qword ptr [rbp+var_48+8], rax
0x18000cca2  movups  xmm0, [rbp+var_48]
0x18000cca6  movups  xmmword ptr [rbp+EventAttributes.nLength], xmm0
0x18000ccaa  movsd   xmm1, [rbp+var_38]
0x18000ccaf  movsd   qword ptr [rbp+EventAttributes.bInheritHandle], xmm1
0x18000ccb4  xor     r9d, r9d; lpName
0x18000ccb7  xor     r8d, r8d; bInitialState
0x18000ccba  xor     edx, edx; bManualReset
0x18000ccbc  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18000ccc0  call    cs:__imp_CreateEventW
0x18000ccc6  mov     rdi, rax
0x18000ccc9  lea     rax, [rbp+var_50]
0x18000cccd  cmp     r14, rax
0x18000ccd0  jz      short loc_18000CCFD
0x18000ccd2  mov     rsi, [r14]
0x18000ccd5  lea     rdx, [rsi-1]
0x18000ccd9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000ccdd  ja      short loc_18000CCF8
0x18000ccdf  call    cs:__imp_GetLastError
0x18000cce5  mov     ebx, eax
0x18000cce7  mov     rcx, rsi; hObject
0x18000ccea  call    cs:__imp_CloseHandle
0x18000ccf0  mov     ecx, ebx; dwErrCode
0x18000ccf2  call    cs:__imp_SetLastError
0x18000ccf8  mov     [r14], rdi
0x18000ccfb  jmp     short loc_18000CD10
0x18000ccfd  lea     rax, [rdi-1]
0x18000cd01  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cd05  ja      short loc_18000CD10
0x18000cd07  mov     rcx, rdi; hObject
0x18000cd0a  call    cs:__imp_CloseHandle
0x18000cd10  mov     rcx, [rbp+38h]; this
0x18000cd14  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18000cd18  jz      short loc_18000CD51
0x18000cd1a  mov     rcx, [rbp+hMem]; hMem
0x18000cd1e  mov     [rbp+hMem], r13
0x18000cd22  test    rcx, rcx
0x18000cd25  jz      short loc_18000CD2E
0x18000cd27  call    cs:__imp_LocalFree
0x18000cd2d  nop
0x18000cd2e  mov     rax, r14
0x18000cd31  mov     rbx, [rsp+80h+arg_10]
0x18000cd39  movaps  xmm6, [rsp+80h+var_10]
0x18000cd3e  add     rsp, 80h
0x18000cd45  pop     r15
0x18000cd47  pop     r14
0x18000cd49  pop     r13
0x18000cd4b  pop     r12
0x18000cd4d  pop     rdi
0x18000cd4e  pop     rsi
0x18000cd4f  pop     rbp
0x18000cd50  retn
0x18000cd51  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000cd58  mov     edx, 45h ; 'E'; void *
0x18000cd5d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000cd63  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000cd6a  mov     edx, 37h ; '7'; void *
0x18000cd6f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000cd75  call    ?_Xlen@?$vector@PEAEV?$allocator@PEAE@std@@@std@@IEBAXXZ; std::vector<uchar *>::_Xlen(void)
0x18000cd7b  call    ?_Xlen@?$vector@PEAEV?$allocator@PEAE@std@@@std@@IEBAXXZ; std::vector<uchar *>::_Xlen(void)
```
