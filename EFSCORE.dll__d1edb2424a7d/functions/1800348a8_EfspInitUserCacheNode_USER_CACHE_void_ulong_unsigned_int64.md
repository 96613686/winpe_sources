# EfspInitUserCacheNode(_USER_CACHE *,void *,ulong,unsigned __int64)

- ea: `0x1800348a8`
- end: `0x180034a53`
- name: `?EfspInitUserCacheNode@@YAEPEAU_USER_CACHE@@PEAXK_K@Z`
- size: `427`
- prototype: `unsigned __int8(struct _USER_CACHE *, void *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180034e70`

## callees

- `0x1800102f0`
- `0x180010bf0`
- `0x1800348a8`
- `0x180034b5c`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800348f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003491a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034984`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800348f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003491a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034984`
- `ntdll!RtlLengthSid` at `0x180034900`
- `ntdll!RtlLengthSid` at `0x180034900`
- `ntdll!RtlNtStatusToDosError` at `0x18003497c`
- `ntdll!RtlNtStatusToDosError` at `0x18003497c`
- `ntdll!RtlInitializeSRWLock` at `0x1800349ef`
- `ntdll!RtlInitializeSRWLock` at `0x180034a08`
- `ntdll!RtlInitializeSRWLock` at `0x1800349ef`
- `ntdll!RtlInitializeSRWLock` at `0x180034a08`
- `ntdll!RtlCopySid` at `0x18003496e`
- `ntdll!RtlCopySid` at `0x18003496e`

## pseudocode

```c
char __fastcall EfspInitUserCacheNode(struct _USER_CACHE *a1, void *a2, int a3, __int64 a4)
{
  char v4; // si
  SIZE_T v9; // rbp
  void *v10; // rax
  void *v11; // rdi
  int v12; // eax
  int v13; // eax
  int v14; // esi
  DWORD v15; // eax
  int v16; // eax

  v4 = 0;
  if ( a1 )
  {
    v9 = RtlLengthSid(a2);
    v10 = wil::details::heap_allocator::allocate(v9);
    v11 = v10;
    if ( v10 )
    {
      v13 = RtlCopySid(v9, v10, a2);
      v14 = v13;
      if ( v13 >= 0 )
      {
        *((_QWORD *)a1 + 2) = v11;
        *(_DWORD *)a1 = a3;
        *((_QWORD *)a1 + 1) = a4;
        *((_BYTE *)a1 + 59) = 0;
        RtlInitializeSRWLock((char *)a1 + 40);
        *((_DWORD *)a1 + 6) = 0;
        *((_QWORD *)a1 + 4) = 0;
        RtlInitializeSRWLock((char *)a1 + 48);
        *((_BYTE *)a1 + 56) = 0;
        *((_DWORD *)a1 + 15) = 0;
        *((_DWORD *)a1 + 16) = 1;
        *((_QWORD *)a1 + 10) = (char *)a1 + 72;
        *((_QWORD *)a1 + 9) = (char *)a1 + 72;
        *((_QWORD *)a1 + 14) = (char *)a1 + 104;
        *((_QWORD *)a1 + 13) = (char *)a1 + 104;
        return EfsAddUserCache(a1);
      }
      else
      {
        v15 = RtlNtStatusToDosError(v13);
        SetLastError(v15);
        v16 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v14, 20, 246);
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v16, 20, 246);
        EfsFreeHeap(v11);
        return 0;
      }
    }
    else
    {
      SetLastError(8u);
      v12 = fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, v9, 20, 240);
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 20, 240);
    }
  }
  else
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 87, 20, 233);
    SetLastError(0x57u);
  }
  return v4;
}

```

## disassembly

```asm
0x1800348a8  push    rbx
0x1800348aa  push    rbp
0x1800348ab  push    rsi
0x1800348ac  push    rdi
0x1800348ad  push    r12
0x1800348af  push    r14
0x1800348b1  push    r15
0x1800348b3  sub     rsp, 30h
0x1800348b7  xor     sil, sil
0x1800348ba  mov     r15, r9
0x1800348bd  mov     r12d, r8d
0x1800348c0  mov     r14, rdx
0x1800348c3  mov     rbx, rcx
0x1800348c6  test    rcx, rcx
0x1800348c9  jnz     short loc_1800348FD
0x1800348cb  lea     ebx, [rcx+57h]
0x1800348ce  mov     [rsp+68h+var_48], 9E9h
0x1800348d6  lea     r9d, [rcx+14h]
0x1800348da  mov     r8d, ebx
0x1800348dd  mov     rcx, cs:g_hPublisher
0x1800348e4  lea     rdx, EFS_TRACE_ERROR
0x1800348eb  call    fnEfsLogTrace1
0x1800348f0  mov     ecx, ebx; dwErrCode
0x1800348f2  call    cs:__imp_SetLastError
0x1800348f8  jmp     loc_180034A41
0x1800348fd  mov     rcx, r14; Sid
0x180034900  call    cs:__imp_RtlLengthSid
0x180034906  mov     ecx, eax; unsigned __int64
0x180034908  mov     ebp, eax
0x18003490a  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18003490f  mov     rdi, rax
0x180034912  test    rax, rax
0x180034915  jnz     short loc_180034966
0x180034917  lea     ecx, [rax+8]; dwErrCode
0x18003491a  call    cs:__imp_SetLastError
0x180034920  mov     rcx, cs:g_hPublisher
0x180034927  lea     r9d, [rdi+14h]
0x18003492b  mov     ebx, 9F0h
0x180034930  lea     rdx, EFS_ERROR_MEMORY
0x180034937  mov     r8d, ebp
0x18003493a  mov     [rsp+68h+var_48], ebx
0x18003493e  call    fnEfsLogTrace1
0x180034943  mov     rcx, cs:g_hPublisher
0x18003494a  lea     r9d, [rdi+14h]
0x18003494e  mov     r8d, eax
0x180034951  mov     [rsp+68h+var_48], ebx
0x180034955  lea     rdx, EFS_TRACE_ERROR
0x18003495c  call    fnEfsLogTrace1
0x180034961  jmp     loc_180034A41
0x180034966  mov     r8, r14; SourceSid
0x180034969  mov     rdx, rdi; DestinationSid
0x18003496c  mov     ecx, ebp; DestinationSidLength
0x18003496e  call    cs:__imp_RtlCopySid
0x180034974  mov     esi, eax
0x180034976  test    eax, eax
0x180034978  jns     short loc_1800349DC
0x18003497a  mov     ecx, eax; Status
0x18003497c  call    cs:__imp_RtlNtStatusToDosError
0x180034982  mov     ecx, eax; dwErrCode
0x180034984  call    cs:__imp_SetLastError
0x18003498a  mov     rcx, cs:g_hPublisher
0x180034991  lea     rdx, EFS_API_ERROR
0x180034998  mov     ebx, 9F6h
0x18003499d  mov     r9d, 14h
0x1800349a3  mov     r8d, esi
0x1800349a6  mov     [rsp+68h+var_48], ebx
0x1800349aa  call    fnEfsLogTrace1
0x1800349af  mov     rcx, cs:g_hPublisher
0x1800349b6  lea     rdx, EFS_TRACE_ERROR
0x1800349bd  mov     r9d, 14h
0x1800349c3  mov     [rsp+68h+var_48], ebx
0x1800349c7  mov     r8d, eax
0x1800349ca  call    fnEfsLogTrace1
0x1800349cf  mov     rcx, rdi; lpMem
0x1800349d2  call    EfsFreeHeap
0x1800349d7  xor     sil, sil
0x1800349da  jmp     short loc_180034A41
0x1800349dc  lea     rcx, [rbx+28h]
0x1800349e0  mov     [rbx+10h], rdi
0x1800349e4  mov     [rbx], r12d
0x1800349e7  mov     [rbx+8], r15
0x1800349eb  mov     byte ptr [rbx+3Bh], 0
0x1800349ef  call    cs:__imp_RtlInitializeSRWLock
0x1800349f5  lea     rcx, [rbx+30h]
0x1800349f9  mov     dword ptr [rbx+18h], 0
0x180034a00  mov     qword ptr [rbx+20h], 0
0x180034a08  call    cs:__imp_RtlInitializeSRWLock
0x180034a0e  mov     byte ptr [rbx+38h], 0
0x180034a12  lea     rax, [rbx+48h]
0x180034a16  mov     dword ptr [rbx+3Ch], 0
0x180034a1d  mov     rcx, rbx
0x180034a20  mov     dword ptr [rbx+40h], 1
0x180034a27  mov     [rax+8], rax
0x180034a2b  mov     [rax], rax
0x180034a2e  lea     rax, [rbx+68h]
0x180034a32  mov     [rax+8], rax
0x180034a36  mov     [rax], rax
0x180034a39  call    EfsAddUserCache
0x180034a3e  mov     sil, al
0x180034a41  mov     al, sil
0x180034a44  add     rsp, 30h
0x180034a48  pop     r15
0x180034a4a  pop     r14
0x180034a4c  pop     r12
0x180034a4e  pop     rdi
0x180034a4f  pop     rsi
0x180034a50  pop     rbp
0x180034a51  pop     rbx
0x180034a52  retn
```
