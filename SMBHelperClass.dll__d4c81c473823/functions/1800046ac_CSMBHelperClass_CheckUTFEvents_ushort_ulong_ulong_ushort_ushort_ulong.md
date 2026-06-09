# CSMBHelperClass::CheckUTFEvents(ushort *,ulong,ulong,ushort *,ushort *,ulong &)

- ea: `0x1800046ac`
- end: `0x180004768`
- name: `?CheckUTFEvents@CSMBHelperClass@@AEAAJPEAGKK00AEAK@Z`
- size: `188`
- prototype: `__int64 __fastcall(CSMBHelperClass *this, unsigned __int16 *, unsigned int, unsigned __int16 *, EVT_HANDLE Object, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800067d0`

## callees

- `0x1800046ac`
- `0x180004864`
- `0x18000551c`
- `0x180005734`

## import_xrefs

- `wevtapi!EvtClose` at `0x18000473d`
- `wevtapi!EvtClose` at `0x18000473d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004750`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSMBHelperClass::CheckUTFEvents(
        CSMBHelperClass *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        EVT_HANDLE Object,
        unsigned __int16 *a6,
        unsigned int *a7)
{
  int ErrorCode; // ebx
  int QueryHandle; // eax
  CSMBHelperClass *v11; // rcx
  EVT_HANDLE v12; // rdi
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  Object = 0;
  pv = 0;
  if ( a2 )
  {
    ErrorCode = CSMBHelperClass::ConstructQuery(this, a3, (int)a4, a4, a6, (unsigned __int16 **)&pv);
    if ( ErrorCode >= 0 )
    {
      QueryHandle = CSMBHelperClass::GetQueryHandle(this, (unsigned __int16 *)pv, a2, &Object);
      v12 = Object;
      ErrorCode = QueryHandle;
      if ( QueryHandle >= 0 )
        ErrorCode = CSMBHelperClass::GetErrorCode(v11, Object, a7);
      if ( v12 )
        EvtClose(v12);
    }
    if ( pv )
      CoTaskMemFree(pv);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)ErrorCode;
}

```

## disassembly

```asm
0x1800046ac  mov     rax, rsp
0x1800046af  mov     [rax+8], rbx
0x1800046b3  mov     [rax+18h], rbp
0x1800046b7  push    rdi
0x1800046b8  sub     rsp, 30h
0x1800046bc  mov     qword ptr [rax+28h], 0
0x1800046c4  mov     r10d, r8d
0x1800046c7  mov     qword ptr [rax+10h], 0
0x1800046cf  mov     rdi, rdx
0x1800046d2  mov     rbp, rcx
0x1800046d5  test    rdx, rdx
0x1800046d8  jnz     short loc_1800046E1
0x1800046da  mov     ebx, 0C000000Dh
0x1800046df  jmp     short loc_180004756
0x1800046e1  lea     rax, [rsp+38h+pv]
0x1800046e6  mov     r8d, r9d; unsigned int
0x1800046e9  mov     [rsp+38h+var_10], rax; unsigned __int16 **
0x1800046ee  mov     edx, r10d; unsigned int
0x1800046f1  mov     rax, [rsp+38h+arg_28]
0x1800046f6  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x1800046fb  call    ?ConstructQuery@CSMBHelperClass@@AEAAJKKPEAG0PEAPEAG@Z; CSMBHelperClass::ConstructQuery(ulong,ulong,ushort *,ushort *,ushort * *)
0x180004700  mov     ebx, eax
0x180004702  test    eax, eax
0x180004704  js      short loc_180004743
0x180004706  mov     rdx, [rsp+38h+pv]; unsigned __int16 *
0x18000470b  lea     r9, [rsp+38h+Object]; void **
0x180004710  mov     r8, rdi; unsigned __int16 *
0x180004713  mov     rcx, rbp; this
0x180004716  call    ?GetQueryHandle@CSMBHelperClass@@AEAAJPEAG0PEAPEAX@Z; CSMBHelperClass::GetQueryHandle(ushort *,ushort *,void * *)
0x18000471b  mov     rdi, [rsp+38h+Object]
0x180004720  mov     ebx, eax
0x180004722  test    eax, eax
0x180004724  js      short loc_180004735
0x180004726  mov     r8, [rsp+38h+arg_30]; unsigned int *
0x18000472b  mov     rdx, rdi; void *
0x18000472e  call    ?GetErrorCode@CSMBHelperClass@@AEAAJPEAXAEAK@Z; CSMBHelperClass::GetErrorCode(void *,ulong &)
0x180004733  mov     ebx, eax
0x180004735  test    rdi, rdi
0x180004738  jz      short loc_180004743
0x18000473a  mov     rcx, rdi; Object
0x18000473d  call    cs:__imp_EvtClose
0x180004743  cmp     [rsp+38h+pv], 0
0x180004749  jz      short loc_180004756
0x18000474b  mov     rcx, [rsp+38h+pv]; pv
0x180004750  call    cs:__imp_CoTaskMemFree
0x180004756  mov     rbp, [rsp+38h+arg_10]
0x18000475b  mov     eax, ebx
0x18000475d  mov     rbx, [rsp+38h+arg_0]
0x180004762  add     rsp, 30h
0x180004766  pop     rdi
0x180004767  retn
```
