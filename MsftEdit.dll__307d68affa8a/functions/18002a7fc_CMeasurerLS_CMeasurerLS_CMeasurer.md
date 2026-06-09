# CMeasurerLS::CMeasurerLS(CMeasurer &)

- ea: `0x18002a7fc`
- end: `0x18002a970`
- name: `??0CMeasurerLS@@QEAA@AEAVCMeasurer@@@Z`
- size: `372`
- prototype: `CMeasurerLS *__fastcall(CMeasurerLS *__hidden this, struct CMeasurer *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180018af0`
- `0x180059fac`
- `0x18008a9dc`
- `0x18018ee74`

## callees

- `0x18002a7fc`
- `0x18002af88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a906`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a90c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a90c`

## pseudocode

```c
CMeasurerLS *__fastcall CMeasurerLS::CMeasurerLS(CMeasurerLS *this, struct CMeasurer *a2)
{
  __int64 v3; // rax
  bool *v5; // rcx
  __int64 v6; // rdx
  __int64 *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 v12; // rsi
  int v13; // edi
  struct LOCK_TELEMETRY near **v14; // rax
  int v15; // eax
  CMeasurerLS *result; // rax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  bool v19; // cc
  __int64 v20; // rcx
  __int64 v21; // rcx

  *(_QWORD *)this = a2;
  v3 = *((_QWORD *)a2 + 2);
  if ( v3 )
    v3 = *(_QWORD *)(v3 + 40);
  v5 = (bool *)this + 16;
  if ( v5 )
    *v5 = 0;
  v6 = *(_QWORD *)(v3 + 256);
  if ( v6 && (v7 = *(__int64 **)(v6 + 80)) != 0 )
  {
    if ( v5 )
      *v5 = (v7[2] & 4) != 0;
    v8 = *v7;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 1) = v8;
  *((_BYTE *)this + 17) = 0;
  v9 = *((_QWORD *)a2 + 2);
  if ( v9 )
    v9 = *(_QWORD *)(v9 + 40);
  v10 = *(_QWORD *)(v9 + 256);
  if ( v10 && (v11 = *(__int64 **)(v10 + 80)) != 0 )
    v12 = *v11;
  else
    v12 = 0;
  v13 = (int)CLockSharedData::LockOwner;
  *((_DWORD *)this + 6) = 0;
  if ( v13 && v13 == GetCurrentThreadId() )
  {
    if ( *((_DWORD *)this + 6) > 3u )
      v14 = 0;
    else
      v14 = &CLockSharedData::LockTelemetry + 2 * *((int *)this + 6);
    ++*(_DWORD *)v14;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(*((unsigned int *)this + 6));
    AcquireSRWLockExclusive(Lock);
    CurrentThreadId = GetCurrentThreadId();
    v19 = *((_DWORD *)this + 6) <= 3u;
    v20 = *((int *)this + 6);
    *((_DWORD *)&CLockSharedData::LockOwner + v20) = CurrentThreadId;
    if ( v19 )
      v21 = (__int64)&dword_1802DF74C[4 * v20];
    else
      v21 = 4;
    ++*(_DWORD *)v21;
  }
  ++CLSLock::_cOLSBusy;
  *((_BYTE *)this + 28) = 1;
  v15 = v12 == 0;
  g_cFCLock += v15;
  *((_DWORD *)this + 8) = v15;
  result = this;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_WORD *)this + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x18002a7fc  mov     [rsp+arg_0], rbx
0x18002a801  mov     [rsp+arg_8], rsi
0x18002a806  push    rdi
0x18002a807  sub     rsp, 20h
0x18002a80b  mov     [rcx], rdx
0x18002a80e  mov     r8, rdx
0x18002a811  mov     rax, [rdx+10h]
0x18002a815  mov     rbx, rcx
0x18002a818  test    rax, rax
0x18002a81b  jz      short loc_18002A821
0x18002a81d  mov     rax, [rax+28h]
0x18002a821  add     rcx, 10h
0x18002a825  jnz     loc_18002A93B
0x18002a82b  mov     rdx, [rax+100h]
0x18002a832  test    rdx, rdx
0x18002a835  jz      short loc_18002A844
0x18002a837  mov     rdx, [rdx+50h]
0x18002a83b  test    rdx, rdx
0x18002a83e  jnz     loc_18002A951
0x18002a844  xor     eax, eax
0x18002a846  mov     [rbx+8], rax
0x18002a84a  mov     byte ptr [rbx+11h], 0
0x18002a84e  mov     rax, [r8+10h]
0x18002a852  test    rax, rax
0x18002a855  jz      short loc_18002A85B
0x18002a857  mov     rax, [rax+28h]
0x18002a85b  mov     rcx, [rax+100h]
0x18002a862  test    rcx, rcx
0x18002a865  jz      short loc_18002A874
0x18002a867  mov     rax, [rcx+50h]
0x18002a86b  test    rax, rax
0x18002a86e  jnz     loc_18002A968
0x18002a874  xor     esi, esi
0x18002a876  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002a87c  mov     dword ptr [rbx+18h], 0
0x18002a883  test    edi, edi
0x18002a885  jz      short loc_18002A8FB
0x18002a887  call    cs:__imp_GetCurrentThreadId
0x18002a88d  cmp     edi, eax
0x18002a88f  jnz     short loc_18002A8FB
0x18002a891  cmp     dword ptr [rbx+18h], 3
0x18002a895  ja      loc_18002A943
0x18002a89b  movsxd  rax, dword ptr [rbx+18h]
0x18002a89f  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002a8a6  shl     rax, 4
0x18002a8aa  add     rax, rcx
0x18002a8ad  inc     dword ptr [rax]
0x18002a8af  inc     cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x18002a8b5  xor     eax, eax
0x18002a8b7  mov     byte ptr [rbx+1Ch], 1
0x18002a8bb  test    rsi, rsi
0x18002a8be  mov     rsi, [rsp+28h+arg_8]
0x18002a8c3  setz    al
0x18002a8c6  add     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x18002a8cc  mov     [rbx+20h], eax
0x18002a8cf  mov     rax, rbx
0x18002a8d2  mov     qword ptr [rbx+28h], 0
0x18002a8da  mov     qword ptr [rbx+30h], 0
0x18002a8e2  mov     qword ptr [rbx+38h], 0
0x18002a8ea  mov     word ptr [rbx+40h], 0
0x18002a8f0  mov     rbx, [rsp+28h+arg_0]
0x18002a8f5  add     rsp, 20h
0x18002a8f9  pop     rdi
0x18002a8fa  retn
0x18002a8fb  mov     ecx, [rbx+18h]
0x18002a8fe  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002a903  mov     rcx, rax; SRWLock
0x18002a906  call    cs:__imp_AcquireSRWLockExclusive
0x18002a90c  call    cs:__imp_GetCurrentThreadId
0x18002a912  cmp     dword ptr [rbx+18h], 3
0x18002a916  lea     rdx, ?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002a91d  movsxd  rcx, dword ptr [rbx+18h]
0x18002a921  mov     [rdx+rcx*4], eax
0x18002a924  ja      short loc_18002A94A
0x18002a926  shl     rcx, 4
0x18002a92a  lea     rax, dword_1802DF74C
0x18002a931  add     rcx, rax
0x18002a934  inc     dword ptr [rcx]
0x18002a936  jmp     loc_18002A8AF
0x18002a93b  mov     byte ptr [rcx], 0
0x18002a93e  jmp     loc_18002A82B
0x18002a943  xor     eax, eax
0x18002a945  jmp     loc_18002A8AD
0x18002a94a  mov     ecx, 4
0x18002a94f  jmp     short loc_18002A934
0x18002a951  test    rcx, rcx
0x18002a954  jz      short loc_18002A960
0x18002a956  mov     eax, [rdx+10h]
0x18002a959  shr     eax, 2
0x18002a95c  and     al, 1
0x18002a95e  mov     [rcx], al
0x18002a960  mov     rax, [rdx]
0x18002a963  jmp     loc_18002A846
0x18002a968  mov     rsi, [rax]
0x18002a96b  jmp     loc_18002A876
```
