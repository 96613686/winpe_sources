# PackageManager::AddPackagesToInstall(ulong,uint const *,MapsOperationTrigger)

- ea: `0x18000ea5c`
- end: `0x18000eaf7`
- name: `?AddPackagesToInstall@PackageManager@@QEAAJKPEBIW4MapsOperationTrigger@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012a40`
- `0x180012f00`
- `0x180018508`
- `0x18001ac90`

## callees

- `0x18000e57c`
- `0x18000e6a0`
- `0x18000ea5c`
- `0x18000eb00`
- `0x180010338`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000eac3`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000eac3`

## string_xrefs

- `0x18000eaba`: `PackageManager::AddPackagesToInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PackageManager::AddPackagesToInstall(__int64 a1, unsigned int a2, __int64 a3, int a4)
{
  unsigned int v8; // edi
  int v9; // eax
  int v10; // r8d
  unsigned int v11; // ebx
  _BYTE v13[56]; // [rsp+30h] [rbp-38h] BYREF

  v8 = 774;
  if ( a4 != 1 )
    v8 = 258;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v13,
    (struct _RTL_CRITICAL_SECTION *)a1);
  if ( !*(_BYTE *)(a1 + 104) )
  {
    v9 = PackageManager::AddPackagesToRestoreList(a1, a2, a3, v8);
    if ( v9 < 0 )
    {
      v10 = 826;
      goto LABEL_6;
    }
LABEL_9:
    v11 = 0;
    goto LABEL_10;
  }
  v9 = PackageManager::QueuePackagesToOperateOn(a1, a2, a3, v8, a4);
  if ( v9 >= 0 )
    goto LABEL_9;
  v10 = 822;
LABEL_6:
  v11 = ZTraceReportPropagation(v9, "PackageManager::AddPackagesToInstall", v10, (const void *)a1);
LABEL_10:
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)v13);
  return v11;
}

```

## disassembly

```asm
0x18000ea5c  push    rbx
0x18000ea5e  push    rbp
0x18000ea5f  push    rsi
0x18000ea60  push    rdi
0x18000ea61  push    r14
0x18000ea63  sub     rsp, 40h
0x18000ea67  mov     esi, r9d
0x18000ea6a  mov     rbp, r8
0x18000ea6d  mov     r14d, edx
0x18000ea70  mov     rbx, rcx
0x18000ea73  mov     edi, 306h
0x18000ea78  mov     eax, 102h
0x18000ea7d  cmp     r9d, 1
0x18000ea81  cmovnz  edi, eax
0x18000ea84  mov     rdx, rcx
0x18000ea87  lea     rcx, [rsp+68h+var_38]
0x18000ea8c  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18000ea91  nop
0x18000ea92  mov     [rsp+68h+var_48], esi
0x18000ea96  mov     r9d, edi
0x18000ea99  mov     r8, rbp
0x18000ea9c  mov     edx, r14d
0x18000ea9f  mov     rcx, rbx
0x18000eaa2  cmp     byte ptr [rbx+68h], 0
0x18000eaa6  jz      short loc_18000EACD
0x18000eaa8  call    ?QueuePackagesToOperateOn@PackageManager@@AEAAJKPEBIHW4MapsOperationTrigger@@@Z; PackageManager::QueuePackagesToOperateOn(ulong,uint const *,int,MapsOperationTrigger)
0x18000eaad  test    eax, eax
0x18000eaaf  jns     short loc_18000EADE
0x18000eab1  mov     r8d, 336h
0x18000eab7  mov     r9, rbx
0x18000eaba  lea     rdx, aPackagemanager; "PackageManager::AddPackagesToInstall"
0x18000eac1  mov     ecx, eax
0x18000eac3  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000eac9  mov     ebx, eax
0x18000eacb  jmp     short loc_18000EAE0
0x18000eacd  call    ?AddPackagesToRestoreList@PackageManager@@AEAAJKPEBIHW4MapsOperationTrigger@@@Z; PackageManager::AddPackagesToRestoreList(ulong,uint const *,int,MapsOperationTrigger)
0x18000ead2  test    eax, eax
0x18000ead4  jns     short loc_18000EADE
0x18000ead6  mov     r8d, 33Ah
0x18000eadc  jmp     short loc_18000EAB7
0x18000eade  xor     ebx, ebx
0x18000eae0  lea     rcx, [rsp+68h+var_38]
0x18000eae5  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000eaea  mov     eax, ebx
0x18000eaec  add     rsp, 40h
0x18000eaf0  pop     r14
0x18000eaf2  pop     rdi
0x18000eaf3  pop     rsi
0x18000eaf4  pop     rbp
0x18000eaf5  pop     rbx
0x18000eaf6  retn
```
