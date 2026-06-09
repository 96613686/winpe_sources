# IndexedFiltering::IndexManager::CheckDataSourceAndIndexConsistency(void)

- ea: `0x180013124`
- end: `0x1800131ed`
- name: `?CheckDataSourceAndIndexConsistency@IndexManager@IndexedFiltering@@AEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013768`

## callees

- `0x180002da8`
- `0x18000c790`
- `0x180013124`
- `0x1800177fc`
- `0x180022010`

## string_xrefs

- `0x180013178`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x1800131d3`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::CheckDataSourceAndIndexConsistency(
        IndexedFiltering::IndexManager *this)
{
  int Generation; // eax
  __int64 v3; // r9
  ESESession *v4; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  unsigned __int16 v8; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 v9; // [rsp+48h] [rbp+10h] BYREF

  v8 = 0;
  Generation = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 3) + 64LL))(
                 *((_QWORD *)this + 3),
                 &v8);
  if ( Generation < 0 )
  {
    v3 = 718;
LABEL_5:
    Log_HREvent(
      (unsigned int)Generation,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      v3);
    return 0;
  }
  v4 = (ESESession *)*((_QWORD *)this + 15);
  v9 = 0;
  Generation = ESESession::GetGeneration(v4, &v9);
  if ( Generation < 0 )
  {
    v3 = 734;
    goto LABEL_5;
  }
  v6 = v9;
  if ( v8 == v9 )
    return 0;
  (*(void (__fastcall **)(IndexedFiltering::IndexManager *))(*(_QWORD *)this + 80LL))(this);
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x1000) != 0 )
    McTemplateU0qq_EventWriteTransfer(v7, IndexManager_GenerationMismatch, v8, v6);
  Log_HREvent(
    2147746093LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
    749);
  return 2147746093LL;
}

```

## disassembly

```asm
0x180013124  mov     [rsp+arg_10], rbx
0x180013129  push    rdi
0x18001312a  sub     rsp, 30h
0x18001312e  xor     eax, eax
0x180013130  lea     rdx, [rsp+38h+arg_0]
0x180013135  mov     [rsp+38h+arg_0], ax
0x18001313a  mov     rdi, rcx
0x18001313d  mov     rcx, [rcx+18h]
0x180013141  mov     rax, [rcx]
0x180013144  mov     rax, [rax+40h]
0x180013148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001314d  test    eax, eax
0x18001314f  jns     short loc_180013159
0x180013151  mov     r9d, 2CEh
0x180013157  jmp     short loc_180013178
0x180013159  mov     rcx, [rdi+78h]; this
0x18001315d  lea     rdx, [rsp+38h+arg_8]; unsigned __int16 *
0x180013162  xor     eax, eax
0x180013164  mov     [rsp+38h+arg_8], ax
0x180013169  call    ?GetGeneration@ESESession@@QEAAJPEAG@Z; ESESession::GetGeneration(ushort *)
0x18001316e  test    eax, eax
0x180013170  jns     short loc_180013195
0x180013172  mov     r9d, 2DEh
0x180013178  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001317f  xor     edx, edx
0x180013181  mov     ecx, eax
0x180013183  call    Log_HREvent
0x180013188  xor     eax, eax
0x18001318a  mov     rbx, [rsp+38h+arg_10]
0x18001318f  add     rsp, 30h
0x180013193  pop     rdi
0x180013194  retn
0x180013195  movzx   ebx, [rsp+38h+arg_8]
0x18001319a  cmp     [rsp+38h+arg_0], bx
0x18001319f  jz      short loc_180013188
0x1800131a1  mov     rax, [rdi]
0x1800131a4  mov     rcx, rdi
0x1800131a7  mov     rax, [rax+50h]
0x1800131ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131b0  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 10h
0x1800131b7  jz      short loc_1800131CE
0x1800131b9  movzx   r8d, [rsp+38h+arg_0]
0x1800131bf  lea     rdx, IndexManager_GenerationMismatch
0x1800131c6  mov     r9d, ebx
0x1800131c9  call    McTemplateU0qq_EventWriteTransfer
0x1800131ce  mov     ebx, 8004012Dh
0x1800131d3  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800131da  mov     ecx, ebx
0x1800131dc  mov     r9d, 2EDh
0x1800131e2  xor     edx, edx
0x1800131e4  call    Log_HREvent
0x1800131e9  mov     eax, ebx
0x1800131eb  jmp     short loc_18001318A
```
