# Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::TryAllocDecommittedPages<0>(uint,Memory::PageSegmentBase<Memory::VirtualAllocWrapper> * *)

- ea: `0x1801cf544`
- end: `0x1801cfd3c`
- name: `??$TryAllocDecommittedPages@$0A@@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@IEAAPEADIPEAPEAV?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@1@@Z`
- size: `2040`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801cec08`

## callees

- `0x1801cf544`
- `0x1801d03fc`
- `0x1801d0414`
- `0x1801d04d0`
- `0x1801d084c`
- `0x1807bfa0c`
- `0x18108a7b8`
- `0x18108e998`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1801cfc10`
- `KERNEL32!GetCurrentThread` at `0x1801cfc4b`
- `KERNEL32!GetCurrentThread` at `0x1801cfcad`
- `KERNEL32!GetCurrentThread` at `0x1801cfc10`
- `KERNEL32!GetCurrentThread` at `0x1801cfc4b`
- `KERNEL32!GetCurrentThread` at `0x1801cfcad`
- `KERNEL32!GetProcAddress` at `0x1801cfb53`
- `KERNEL32!GetProcAddress` at `0x1801cfb66`
- `KERNEL32!GetProcAddress` at `0x1801cfb7d`
- `KERNEL32!GetProcAddress` at `0x1801cfb53`
- `KERNEL32!GetProcAddress` at `0x1801cfb66`
- `KERNEL32!GetProcAddress` at `0x1801cfb7d`
- `KERNEL32!GetModuleHandleW` at `0x1801cfb3b`
- `KERNEL32!GetModuleHandleW` at `0x1801cfb3b`
- `KERNEL32!LeaveCriticalSection` at `0x1801cfbce`
- `KERNEL32!LeaveCriticalSection` at `0x1801cfbce`
- `KERNEL32!EnterCriticalSection` at `0x1801cfb1f`
- `KERNEL32!EnterCriticalSection` at `0x1801cfb1f`
- `KERNEL32!GetCurrentProcess` at `0x1801cfb8f`
- `KERNEL32!GetCurrentProcess` at `0x1801cfb8f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801cf7b8`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801cfc7f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801cf7b8`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801cfc7f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1801cfce1`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1801cfce1`

## string_xrefs

- `0x1801cfb34`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x1801cfb5c`: `SetThreadInformation`
- `0x1801cfb73`: `GetThreadInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPVOID __fastcall Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::TryAllocDecommittedPages<0>(
        __int64 *a1,
        unsigned int a2,
        __int64 **a3)
{
  unsigned int v3; // esi
  __int64 *v4; // rax
  __int64 *v5; // r15
  __int64 *v7; // rdi
  _QWORD *v8; // rbx
  _QWORD *v9; // rsi
  __int64 v10; // r14
  unsigned __int64 v11; // r8
  int v12; // eax
  __int64 v13; // r10
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rax
  unsigned __int64 *v16; // r8
  unsigned int v17; // edx
  bool k; // zf
  __int64 v19; // rcx
  int v20; // eax
  unsigned __int64 v21; // rcx
  __int64 v22; // r12
  SIZE_T v23; // r13
  unsigned __int64 v24; // rdx
  char v25; // cl
  __int64 v26; // rax
  char v27; // bl
  SIZE_T v28; // rdx
  LPVOID v29; // r13
  unsigned __int64 *v30; // rcx
  int v31; // edx
  __int64 v32; // r8
  _QWORD *v33; // r8
  unsigned int i; // eax
  unsigned __int64 v35; // rdx
  int v36; // r8d
  int v37; // ebx
  int v38; // eax
  int v39; // edx
  unsigned int v40; // edx
  __int64 *v41; // rbx
  unsigned __int64 v42; // r12
  signed __int64 v43; // rax
  __int64 v44; // rcx
  __int64 *v45; // rbx
  __int64 v46; // rdx
  unsigned int v47; // edx
  bool v48; // cf
  unsigned __int64 *v49; // r8
  bool j; // zf
  __int64 *v51; // rsi
  unsigned int v52; // ebx
  HMODULE ModuleHandleW; // rax
  HMODULE v54; // rsi
  FARPROC ProcAddress; // r12
  HANDLE CurrentProcess; // rax
  int (*v57)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rsi
  HANDLE CurrentThread; // rax
  int (*v59)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v60; // rax
  void *v61; // rax
  int (*v62)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v63; // rax
  int v64; // [rsp+38h] [rbp-89h] BYREF
  int v65; // [rsp+3Ch] [rbp-85h]
  unsigned int v66; // [rsp+40h] [rbp-81h]
  int v67; // [rsp+44h] [rbp-7Dh] BYREF
  __int64 *v68; // [rsp+48h] [rbp-79h]
  LPVOID lpAddress; // [rsp+50h] [rbp-71h]
  int v70; // [rsp+58h] [rbp-69h] BYREF
  DWORD flOldProtect; // [rsp+5Ch] [rbp-65h] BYREF
  int v72; // [rsp+60h] [rbp-61h]
  unsigned int v73; // [rsp+64h] [rbp-5Dh]
  __int64 v74; // [rsp+68h] [rbp-59h]
  __int64 *v75; // [rsp+70h] [rbp-51h]
  __int64 **v76; // [rsp+78h] [rbp-49h]
  struct _RTL_CRITICAL_SECTION *v77; // [rsp+80h] [rbp-41h]
  _OWORD v78[2]; // [rsp+88h] [rbp-39h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-19h]
  _OWORD v80[2]; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v81; // [rsp+D8h] [rbp+17h]
  _QWORD v82[7]; // [rsp+E0h] [rbp+1Fh] BYREF

  v75 = a1;
  v3 = a2;
  v66 = a2;
  v76 = a3;
  v4 = a1 + 9;
  v68 = a1 + 9;
  v5 = a1 + 9;
  while ( 1 )
  {
    v5 = (__int64 *)*v5;
    if ( v5 == v4 )
      return 0;
    v7 = v5 + 2;
    v73 = *((_DWORD *)v5 + 38);
    v78[0] = *((_OWORD *)v5 + 7);
    v78[1] = *((_OWORD *)v5 + 8);
    v79 = v5[18];
    v4 = v68;
    if ( *((_DWORD *)v5 + 39) + v73 >= v3 )
    {
      v80[0] = *(_OWORD *)(v5 + 9);
      v80[1] = *(_OWORD *)(v5 + 11);
      v81 = v5[13];
      v8 = v80;
      v9 = v78;
      do
        BVUnitT<unsigned __int64>::Or(v8++, *v9++);
      while ( v8 != v82 );
      v72 = *((_DWORD *)v5 + 38);
      v65 = 0;
      k = !_BitScanForward64((unsigned __int64 *)&v10, *(unsigned __int64 *)&v80[0]);
      if ( k || (_DWORD)v10 == -1 )
      {
        v30 = (unsigned __int64 *)v80;
        v31 = 0;
        while ( ++v30 != v82 )
        {
          v31 += 64;
          v65 = 0;
          k = !_BitScanForward64((unsigned __int64 *)&v32, *v30);
          if ( !k && (_DWORD)v32 != -1 )
          {
            LODWORD(v10) = v32 + v31;
            goto LABEL_9;
          }
        }
        LODWORD(v10) = -1;
      }
LABEL_9:
      v3 = v66;
LABEL_10:
      v4 = v68;
      if ( (_DWORD)v10 == -1 )
        continue;
      v4 = v68;
      if ( *((_DWORD *)v5 + 12) - (int)v10 - *((_DWORD *)v5 + 16) < v3 )
        continue;
      if ( v3 == 1 )
        goto LABEL_23;
      v11 = (unsigned __int64)(unsigned int)v10 >> 6;
      v12 = v10 & 0x3F;
      v13 = *((_QWORD *)v80 + v11);
      if ( v12 + v3 <= 0x40 )
      {
        v14 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v3) << v12;
        v15 = v13 & v14;
        goto LABEL_15;
      }
      if ( (v13 & (0xFFFFFFFFFFFFFFFFuLL >> v12 << v12)) != 0xFFFFFFFFFFFFFFFFuLL >> v12 << v12 )
        goto LABEL_16;
      v33 = (_QWORD *)v80 + v11 + 1;
      for ( i = v12 + v3 - 64; i >= 0x40; i -= 64 )
      {
        if ( *v33 != -1 )
          goto LABEL_16;
        ++v33;
      }
      if ( !i )
        goto LABEL_23;
      v14 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)i);
      v15 = v14 & *v33;
LABEL_15:
      if ( v15 == v14 )
      {
LABEL_23:
        v21 = v5[5] + (unsigned int)((_DWORD)v10 << 12);
        lpAddress = (LPVOID)v21;
        v22 = v3;
        v74 = v3;
        v23 = (unsigned __int64)v3 << 12;
        if ( ((v23 - 1) & v21) != 0 )
        {
          v24 = (v21 % v23) >> 12;
          v25 = 0;
        }
        else
        {
          LODWORD(v24) = 0;
          v25 = 1;
        }
        v26 = v5[3];
        if ( v25 )
        {
          v65 = *(_DWORD *)(v26 + 216);
          v27 = 0;
          LOBYTE(v64) = 0;
          if ( v65 == 2 )
          {
            if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
            {
              v77 = &Memory::AutoEnableDynamicCodeGen::processPolicyCS;
              EnterCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
              if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
              {
                ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
                v54 = ModuleHandleW;
                if ( !ModuleHandleW
                  || (ProcAddress = GetProcAddress(ModuleHandleW, "GetProcessMitigationPolicy"),
                      Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v54, "SetThreadInformation"),
                      Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v54, "GetThreadInformation"),
                      !ProcAddress)
                  || (CurrentProcess = GetCurrentProcess(),
                      !((unsigned int (__fastcall *)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *))ProcAddress)(
                         CurrentProcess,
                         2,
                         &Memory::AutoEnableDynamicCodeGen::processPolicy)) )
                {
                  Memory::AutoEnableDynamicCodeGen::processPolicy.Flags &= ~1u;
                }
                Memory::AutoEnableDynamicCodeGen::processPolicyObtained = 1;
                v22 = v74;
              }
              LeaveCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
            }
            if ( (Memory::AutoEnableDynamicCodeGen::processPolicy.Flags & 1) != 0
              && (Memory::AutoEnableDynamicCodeGen::processPolicy.Flags & 2) != 0 )
            {
              if ( Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc )
              {
                v57 = Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc;
                if ( Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc )
                {
                  v67 = 0;
                  CurrentThread = GetCurrentThread();
                  if ( !((unsigned int (__fastcall *)(HANDLE, __int64, int *))v57)(CurrentThread, 2, &v67) || v67 != 1 )
                  {
                    v67 = 1;
                    v59 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
                    v60 = GetCurrentThread();
                    ((void (__fastcall *)(HANDLE, __int64, int *))v59)(v60, 2, &v67);
                    v27 = 1;
                    LOBYTE(v64) = 1;
                  }
                }
              }
            }
          }
          flOldProtect = 0;
          v28 = v23;
          if ( v65 == 2 )
          {
            v61 = VirtualAlloc(lpAddress, v23, 0x1000u, 0x40000040u);
            if ( v61 )
            {
              if ( !VirtualProtect(v61, v23, 4u, &flOldProtect) )
                CustomHeap_BadPageState_fatal_error((unsigned __int64)&Memory::VirtualAllocWrapper::Instance);
              v29 = lpAddress;
LABEL_43:
              Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)&v64);
              v35 = (unsigned __int64)(unsigned int)v10 >> 6;
              v36 = v10 & 0x3F;
              v3 = v66;
              v37 = v36 + v66;
              if ( v36 + v66 > 0x40 )
              {
                v7[v35 + 7] &= ~(0xFFFFFFFFFFFFFFFFuLL >> v36 << v36);
                v51 = &v7[v35 + 8];
                v52 = v37 - 64;
                if ( v52 >= 0x40 )
                {
                  memset_0(v51, 0, 8 * ((unsigned __int64)v52 >> 6));
                  do
                  {
                    ++v51;
                    v52 -= 64;
                  }
                  while ( v52 >= 0x40 );
                }
                if ( v52 )
                  *v51 &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v52));
                v3 = v66;
              }
              else
              {
                v7[v35 + 7] &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v66) << v36);
              }
              BVStatic<272>::ClearRange(v5 + 14, (unsigned int)v10, v3);
              v38 = BVStatic<272>::Count(v5 + 9);
              v39 = v72;
              *((_DWORD *)v5 + 38) += v38 - v72;
              *((_DWORD *)v5 + 39) += v39 - v38 - v3;
              v4 = v68;
              if ( v29 )
              {
                v40 = v73;
                v41 = v75;
                v75[15] += *((unsigned int *)v5 + 38) - (unsigned __int64)v73;
                v41[29] += (unsigned __int64)(v3 + *((_DWORD *)v5 + 38) - v40) << 12;
                v42 = v22 << 12;
                v41[26] += v42;
                v43 = _InterlockedExchangeAdd64(&qword_181592770, v42);
                if ( qword_181592770 > (unsigned __int64)qword_181592768 )
                  qword_181592768 = qword_181592770;
                if ( (byte_181592701 & 2) != 0 )
                  McTemplateU0x_EventWriteTransfer(
                    PROVIDER_JSCRIPT9_Context,
                    JSCRIPT_PAGE_ALLOCATOR_USED_SIZE,
                    v43 + v42);
                if ( !*((_DWORD *)v5 + 39) )
                {
                  if ( *((_DWORD *)v5 + 12) == *((_DWORD *)v5 + 16) )
                  {
                    v45 = 0;
                  }
                  else if ( *((_DWORD *)v5 + 38)
                         && ((v44 = v5[4]) == 0
                          || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44)) )
                  {
                    if ( *((_DWORD *)v5 + 39) )
                    {
                      v45 = v68;
                    }
                    else if ( *((_DWORD *)v5 + 38) == *((_DWORD *)v5 + 12) - *((_DWORD *)v5 + 16) )
                    {
                      v45 = v41 + 7;
                    }
                    else
                    {
                      v45 = v41 + 3;
                    }
                  }
                  else
                  {
                    v45 = v41 + 5;
                  }
                  *(_QWORD *)v5[1] = *v5;
                  *(_QWORD *)(*v5 + 8) = v5[1];
                  v46 = *v45;
                  v5[1] = *(_QWORD *)(*v45 + 8);
                  *v5 = v46;
                  **(_QWORD **)(v46 + 8) = v5;
                  *(_QWORD *)(v46 + 8) = v5;
                }
                *v76 = v7;
                return v29;
              }
              continue;
            }
            Memory::MemoryOperationLastError::RecordLastError();
            Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)&v64);
          }
          else
          {
            v29 = lpAddress;
            if ( VirtualAlloc(lpAddress, v28, 0x1000u, 4u) )
              goto LABEL_43;
            Memory::MemoryOperationLastError::RecordLastError();
            if ( v27 )
            {
              v70 = 0;
              v62 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
              v63 = GetCurrentThread();
              ((void (__fastcall *)(HANDLE, __int64, int *))v62)(v63, 2, &v70);
            }
          }
          v3 = v66;
          v4 = v68;
          if ( v66 == 1 )
            continue;
          goto LABEL_16;
        }
        v47 = v10 + v24;
        v48 = v47 < *(_DWORD *)(v26 + 104);
        v4 = v68;
        if ( !v48 )
          continue;
        LOBYTE(v19) = v47;
        v49 = (unsigned __int64 *)v80 + ((unsigned __int64)v47 >> 6);
        v17 = v47 & 0xFFFFFFC0;
        for ( j = !_BitScanForward64((unsigned __int64 *)&v19, *v49 & (-1LL << v19));
              ;
              j = !_BitScanForward64((unsigned __int64 *)&v19, *v49) )
        {
          v65 = 0;
          if ( !j && (_DWORD)v19 != -1 )
            break;
          if ( ++v49 == v82 )
          {
LABEL_71:
            v20 = -1;
            goto LABEL_20;
          }
          v17 += 64;
        }
      }
      else
      {
LABEL_16:
        v16 = (unsigned __int64 *)v80 + ((unsigned __int64)(unsigned int)(v10 + 1) >> 6);
        v17 = (v10 + 1) & 0xFFFFFFC0;
        for ( k = !_BitScanForward64((unsigned __int64 *)&v19, *v16 & (-1LL << ((unsigned __int8)v10 + 1)));
              ;
              k = !_BitScanForward64((unsigned __int64 *)&v19, *v16) )
        {
          v65 = 0;
          if ( !k && (_DWORD)v19 != -1 )
            break;
          if ( ++v16 == v82 )
            goto LABEL_71;
          v17 += 64;
        }
      }
      v20 = v19 + v17;
LABEL_20:
      LODWORD(v10) = v20;
      goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x1801cf544  mov     rax, rsp
0x1801cf547  mov     [rax+20h], rbx
0x1801cf54b  mov     [rax+18h], r8
0x1801cf54f  mov     [rax+10h], edx
0x1801cf552  mov     [rax+8], rcx
0x1801cf556  push    rbp
0x1801cf557  push    rsi
0x1801cf558  push    rdi
0x1801cf559  push    r12
0x1801cf55b  push    r13
0x1801cf55d  push    r14
0x1801cf55f  push    r15
0x1801cf561  lea     rbp, [rax-5Fh]
0x1801cf565  sub     rsp, 0E0h
0x1801cf56c  mov     rax, cs:__security_cookie
0x1801cf573  xor     rax, rsp
0x1801cf576  mov     [rbp+57h+var_38], rax
0x1801cf57a  mov     rax, [rbp+57h+arg_0]
0x1801cf57e  mov     [rbp+57h+var_A8], rax
0x1801cf582  mov     esi, [rbp+57h+arg_8]
0x1801cf585  mov     [rsp+110h+var_D8], esi
0x1801cf589  mov     rcx, [rbp+57h+arg_10]
0x1801cf58d  mov     [rbp+57h+var_A0], rcx
0x1801cf591  add     rax, 48h ; 'H'
0x1801cf595  mov     [rbp+57h+var_D0], rax
0x1801cf599  mov     r15, rax
0x1801cf59c  mov     r15, [r15]
0x1801cf59f  cmp     r15, rax
0x1801cf5a2  jnz     short loc_1801CF5CD
0x1801cf5a4  xor     eax, eax
0x1801cf5a6  mov     rcx, [rbp+57h+var_38]
0x1801cf5aa  xor     rcx, rsp; StackCookie
0x1801cf5ad  call    __security_check_cookie
0x1801cf5b2  mov     rbx, [rsp+110h+arg_18]
0x1801cf5ba  add     rsp, 0E0h
0x1801cf5c1  pop     r15
0x1801cf5c3  pop     r14
0x1801cf5c5  pop     r13
0x1801cf5c7  pop     r12
0x1801cf5c9  pop     rdi
0x1801cf5ca  pop     rsi
0x1801cf5cb  pop     rbp
0x1801cf5cc  retn
0x1801cf5cd  lea     rdi, [r15+10h]
0x1801cf5d1  mov     ecx, [rdi+88h]
0x1801cf5d7  mov     [rbp+57h+var_B4], ecx
0x1801cf5da  movups  xmm0, xmmword ptr [rdi+60h]
0x1801cf5de  movaps  [rbp+57h+var_90], xmm0
0x1801cf5e2  movups  xmm1, xmmword ptr [rdi+70h]
0x1801cf5e6  movaps  [rbp+57h+var_80], xmm1
0x1801cf5ea  movsd   xmm0, qword ptr [rdi+80h]
0x1801cf5f2  movsd   [rbp+57h+var_70], xmm0
0x1801cf5f7  add     ecx, [rdi+8Ch]
0x1801cf5fd  cmp     ecx, esi
0x1801cf5ff  mov     rax, [rbp+57h+var_D0]
0x1801cf603  jb      short loc_1801CF59C
0x1801cf605  movups  xmm0, xmmword ptr [rdi+38h]
0x1801cf609  movups  [rbp+57h+var_60], xmm0
0x1801cf60d  movups  xmm1, xmmword ptr [rdi+48h]
0x1801cf611  movups  [rbp+57h+var_50], xmm1
0x1801cf615  movsd   xmm0, qword ptr [rdi+58h]
0x1801cf61a  movsd   [rbp+57h+var_40], xmm0
0x1801cf61f  lea     rbx, [rbp+57h+var_60]
0x1801cf623  lea     rsi, [rbp+57h+var_90]
0x1801cf627  mov     rdx, [rsi]
0x1801cf62a  mov     rcx, rbx
0x1801cf62d  call    ?Or@?$BVUnitT@_K@@QEAAXV1@@Z; BVUnitT<unsigned __int64>::Or(BVUnitT<unsigned __int64>)
0x1801cf632  add     rbx, 8
0x1801cf636  lea     rsi, [rsi+8]
0x1801cf63a  lea     rax, [rbp+57h+var_38]
0x1801cf63e  cmp     rbx, rax
0x1801cf641  jnz     short loc_1801CF627
0x1801cf643  mov     eax, [rdi+88h]
0x1801cf649  mov     [rbp+57h+var_B8], eax
0x1801cf64c  mov     [rsp+110h+var_DC], 0
0x1801cf654  bsf     r14, qword ptr [rbp+57h+var_60]
0x1801cf659  setnz   al
0x1801cf65c  or      r11d, 0FFFFFFFFh
0x1801cf660  test    al, al
0x1801cf662  jz      loc_1801CF7F3
0x1801cf668  cmp     r14d, r11d
0x1801cf66b  jz      loc_1801CF7F3
0x1801cf671  mov     esi, [rsp+110h+var_D8]
0x1801cf675  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801cf679  cmp     r14d, r11d
0x1801cf67c  mov     rax, [rbp+57h+var_D0]
0x1801cf680  jz      loc_1801CF59C
0x1801cf686  mov     eax, [rdi+20h]
0x1801cf689  sub     eax, r14d
0x1801cf68c  sub     eax, [rdi+30h]
0x1801cf68f  cmp     eax, esi
0x1801cf691  mov     rax, [rbp+57h+var_D0]
0x1801cf695  jb      loc_1801CF59C
0x1801cf69b  cmp     esi, 1
0x1801cf69e  jz      loc_1801CF73E
0x1801cf6a4  mov     r8d, r14d
0x1801cf6a7  shr     r8, 6
0x1801cf6ab  mov     eax, r14d
0x1801cf6ae  and     eax, 3Fh
0x1801cf6b1  lea     r9d, [rax+rsi]
0x1801cf6b5  mov     r10, qword ptr [rbp+r8*8+57h+var_60]
0x1801cf6ba  mov     rdx, rbx
0x1801cf6bd  cmp     r9d, 40h ; '@'
0x1801cf6c1  ja      loc_1801CF82E
0x1801cf6c7  mov     ecx, 40h ; '@'
0x1801cf6cc  sub     ecx, esi
0x1801cf6ce  shr     rdx, cl
0x1801cf6d1  mov     ecx, eax
0x1801cf6d3  shl     rdx, cl
0x1801cf6d6  mov     rax, rdx
0x1801cf6d9  and     rax, r10
0x1801cf6dc  cmp     rax, rdx
0x1801cf6df  jz      short loc_1801CF73E
0x1801cf6e1  lea     edx, [r14+1]
0x1801cf6e5  mov     ecx, edx
0x1801cf6e7  mov     eax, edx
0x1801cf6e9  shr     rax, 6
0x1801cf6ed  lea     r8, [rbp+57h+var_60]
0x1801cf6f1  lea     r8, [r8+rax*8]
0x1801cf6f5  and     edx, 0FFFFFFC0h
0x1801cf6f8  mov     rax, rbx
0x1801cf6fb  shl     rax, cl
0x1801cf6fe  and     rax, [r8]
0x1801cf701  bsf     rcx, rax
0x1801cf705  setnz   al
0x1801cf708  test    al, al
0x1801cf70a  mov     [rsp+110h+var_DC], 0
0x1801cf712  jz      short loc_1801CF724
0x1801cf714  cmp     ecx, r11d
0x1801cf717  jz      short loc_1801CF724
0x1801cf719  lea     eax, [rcx+rdx]
0x1801cf71c  mov     r14d, eax
0x1801cf71f  jmp     loc_1801CF679
0x1801cf724  add     r8, 8
0x1801cf728  lea     rax, [rbp+57h+var_38]
0x1801cf72c  cmp     r8, rax
0x1801cf72f  jz      loc_1801CFA8A
0x1801cf735  add     edx, 40h ; '@'
0x1801cf738  bsf     rcx, [r8]
0x1801cf73c  jmp     short loc_1801CF705
0x1801cf73e  mov     ecx, r14d
0x1801cf741  shl     ecx, 0Ch
0x1801cf744  add     rcx, [rdi+18h]
0x1801cf748  mov     [rbp+57h+lpAddress], rcx
0x1801cf74c  mov     r12d, esi
0x1801cf74f  mov     [rbp+57h+var_B0], r12
0x1801cf753  mov     r13d, esi
0x1801cf756  shl     r13, 0Ch
0x1801cf75a  lea     rax, [r13-1]
0x1801cf75e  test    rcx, rax
0x1801cf761  jnz     loc_1801CFA65
0x1801cf767  xor     edx, edx
0x1801cf769  mov     cl, 1
0x1801cf76b  mov     rax, [rdi+8]
0x1801cf76f  test    cl, cl
0x1801cf771  jz      loc_1801CFA07
0x1801cf777  mov     ecx, [rax+0D8h]
0x1801cf77d  mov     [rsp+110h+var_DC], ecx
0x1801cf781  xor     bl, bl
0x1801cf783  mov     byte ptr [rsp+110h+var_E0], bl
0x1801cf787  cmp     ecx, 2
0x1801cf78a  jz      loc_1801CFB03
0x1801cf790  mov     [rbp+57h+flOldProtect], 0
0x1801cf797  mov     r8d, 1000h; flAllocationType
0x1801cf79d  mov     rdx, r13; dwSize
0x1801cf7a0  cmp     [rsp+110h+var_DC], 2
0x1801cf7a5  jz      loc_1801CFC75
0x1801cf7ab  mov     r9d, 4; flProtect
0x1801cf7b1  mov     r13, [rbp+57h+lpAddress]
0x1801cf7b5  mov     rcx, r13; lpAddress
0x1801cf7b8  call    cs:__imp_VirtualAlloc
0x1801cf7be  test    rax, rax
0x1801cf7c1  jnz     loc_1801CF877
0x1801cf7c7  call    ?RecordLastError@MemoryOperationLastError@Memory@@SAXXZ; Memory::MemoryOperationLastError::RecordLastError(void)
0x1801cf7cc  nop
0x1801cf7cd  test    bl, bl
0x1801cf7cf  jnz     loc_1801CFC9F
0x1801cf7d5  mov     esi, [rsp+110h+var_D8]
0x1801cf7d9  cmp     esi, 1
0x1801cf7dc  mov     rax, [rbp+57h+var_D0]
0x1801cf7e0  jz      loc_1801CF59C
0x1801cf7e6  or      r11d, 0FFFFFFFFh
0x1801cf7ea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801cf7ee  jmp     loc_1801CF6E1
0x1801cf7f3  lea     rcx, [rbp+57h+var_60]
0x1801cf7f7  xor     edx, edx
0x1801cf7f9  add     rcx, 8
0x1801cf7fd  lea     rax, [rbp+57h+var_38]
0x1801cf801  cmp     rcx, rax
0x1801cf804  jz      loc_1801CFA9B
0x1801cf80a  add     edx, 40h ; '@'
0x1801cf80d  mov     [rsp+110h+var_DC], 0
0x1801cf815  bsf     r8, [rcx]
0x1801cf819  setnz   al
0x1801cf81c  test    al, al
0x1801cf81e  jz      short loc_1801CF7F9
0x1801cf820  cmp     r8d, r11d
0x1801cf823  jz      short loc_1801CF7F9
0x1801cf825  lea     r14d, [r8+rdx]
0x1801cf829  jmp     loc_1801CF671
0x1801cf82e  mov     ecx, eax
0x1801cf830  shr     rdx, cl
0x1801cf833  shl     rdx, cl
0x1801cf836  mov     rax, rdx
0x1801cf839  and     rax, r10
0x1801cf83c  cmp     rax, rdx
0x1801cf83f  jnz     loc_1801CF6E1
0x1801cf845  lea     r8, [rbp+r8*8+57h+var_60+8]
0x1801cf84a  lea     eax, [r9-40h]
0x1801cf84e  cmp     eax, 40h ; '@'
0x1801cf851  jnb     loc_1801CFAEE
0x1801cf857  test    eax, eax
0x1801cf859  jz      loc_1801CF73E
0x1801cf85f  mov     ecx, 40h ; '@'
0x1801cf864  sub     ecx, eax
0x1801cf866  mov     rdx, rbx
0x1801cf869  shr     rdx, cl
0x1801cf86c  mov     rax, [r8]
0x1801cf86f  and     rax, rdx
0x1801cf872  jmp     loc_1801CF6DC
0x1801cf877  lea     rcx, [rsp+110h+var_E0]; this
0x1801cf87c  call    ??1AutoEnableDynamicCodeGen@Memory@@QEAA@XZ; Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen(void)
0x1801cf881  mov     edx, r14d
0x1801cf884  shr     rdx, 6
0x1801cf888  mov     r8d, r14d
0x1801cf88b  and     r8d, 3Fh
0x1801cf88f  mov     esi, [rsp+110h+var_D8]
0x1801cf893  lea     ebx, [r8+rsi]
0x1801cf897  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801cf89b  cmp     ebx, 40h ; '@'
0x1801cf89e  ja      loc_1801CFAA3
0x1801cf8a4  lea     ecx, [rax+41h]
0x1801cf8a7  sub     ecx, esi
0x1801cf8a9  shr     rax, cl
0x1801cf8ac  mov     ecx, r8d
0x1801cf8af  shl     rax, cl
0x1801cf8b2  not     rax
0x1801cf8b5  and     [rdi+rdx*8+38h], rax
0x1801cf8ba  jmp     short loc_1801CF8D8
0x1801cf8bc  test    ebx, ebx
0x1801cf8be  jz      short loc_1801CF8D4
0x1801cf8c0  mov     ecx, 40h ; '@'
0x1801cf8c5  sub     ecx, ebx
0x1801cf8c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801cf8cb  shr     rax, cl
0x1801cf8ce  not     rax
0x1801cf8d1  and     [rsi], rax
0x1801cf8d4  mov     esi, [rsp+110h+var_D8]
0x1801cf8d8  mov     r8d, esi
0x1801cf8db  mov     edx, r14d
0x1801cf8de  lea     rcx, [rdi+60h]
0x1801cf8e2  call    ?ClearRange@?$BVStatic@$0BBA@@@QEAAXII@Z; BVStatic<272>::ClearRange(uint,uint)
0x1801cf8e7  lea     rcx, [rdi+38h]
0x1801cf8eb  call    ?Count@?$BVStatic@$0BBA@@@QEBAIXZ; BVStatic<272>::Count(void)
0x1801cf8f0  mov     ecx, eax
0x1801cf8f2  mov     edx, [rbp+57h+var_B8]
0x1801cf8f5  sub     eax, edx
0x1801cf8f7  add     [rdi+88h], eax
0x1801cf8fd  sub     edx, ecx
0x1801cf8ff  sub     edx, esi
0x1801cf901  add     [rdi+8Ch], edx
0x1801cf907  test    r13, r13
0x1801cf90a  mov     rax, [rbp+57h+var_D0]
0x1801cf90e  jz      loc_1801CF59C
0x1801cf914  mov     ecx, [rdi+88h]
0x1801cf91a  mov     edx, [rbp+57h+var_B4]
0x1801cf91d  sub     rcx, rdx
0x1801cf920  mov     rbx, [rbp+57h+var_A8]
0x1801cf924  add     [rbx+78h], rcx
0x1801cf928  mov     eax, [rdi+88h]
0x1801cf92e  sub     eax, edx
0x1801cf930  add     eax, esi
0x1801cf932  shl     rax, 0Ch
0x1801cf936  add     [rbx+0E8h], rax
0x1801cf93d  shl     r12, 0Ch
0x1801cf941  add     [rbx+0D0h], r12
0x1801cf948  mov     rax, r12
0x1801cf94b  lock xadd cs:qword_181592770, rax
0x1801cf954  mov     rcx, cs:qword_181592770
0x1801cf95b  cmp     rcx, cs:qword_181592768
0x1801cf962  jbe     short loc_1801CF96B
0x1801cf964  mov     cs:qword_181592768, rcx
0x1801cf96b  test    cs:byte_181592701, 2
0x1801cf972  jnz     loc_1801CFD00
0x1801cf978  cmp     dword ptr [rdi+8Ch], 0
0x1801cf97f  jnz     short loc_1801CF9F8
0x1801cf981  mov     eax, [rdi+20h]
0x1801cf984  cmp     eax, [rdi+30h]
0x1801cf987  jz      loc_1801CFD1C
0x1801cf98d  cmp     dword ptr [rdi+88h], 0
0x1801cf994  jz      loc_1801CFA92
0x1801cf99a  mov     rcx, [rdi+10h]
0x1801cf99e  test    rcx, rcx
0x1801cf9a1  jnz     loc_1801CFD23
0x1801cf9a7  cmp     dword ptr [rdi+8Ch], 0
0x1801cf9ae  jnz     loc_1801CFA81
0x1801cf9b4  mov     eax, [rdi+20h]
0x1801cf9b7  sub     eax, [rdi+30h]
0x1801cf9ba  cmp     [rdi+88h], eax
0x1801cf9c0  jnz     loc_1801CFA78
  ... truncated ...
```
