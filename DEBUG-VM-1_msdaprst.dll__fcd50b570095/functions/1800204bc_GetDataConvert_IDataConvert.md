# GetDataConvert(IDataConvert * *)

- ea: `0x1800204bc`
- end: `0x180020585`
- name: `?GetDataConvert@@YAJPEAPEAUIDataConvert@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct IDataConvert **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ba50`
- `0x18002058c`
- `0x180024ac8`

## callees

- `0x1800204bc`
- `0x18002090c`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800204e4`
- `KERNEL32!GetCurrentThreadId` at `0x1800204e4`
- `KERNEL32!LeaveCriticalSection` at `0x18002056d`
- `KERNEL32!LeaveCriticalSection` at `0x18002056d`
- `ole32!CoCreateInstance` at `0x180020528`
- `ole32!CoCreateInstance` at `0x180020528`
- `MSDART!UMSEnterCSWraper` at `0x1800204d8`
- `MSDART!UMSEnterCSWraper` at `0x1800204d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDataConvert(struct IDataConvert **a1)
{
  unsigned __int8 *v2; // rbx
  HRESULT Instance; // edi
  __int64 v5; // rcx

  v2 = g_pcsDataConvert;
  UMSEnterCSWraper(g_pcsDataConvert);
  if ( !*((_DWORD *)v2 + 3) )
    *((_DWORD *)v2 + 2) = GetCurrentThreadId();
  ++*((_DWORD *)v2 + 3);
  ++*((_DWORD *)v2 + 4);
  if ( g_pIDataConvert )
  {
    Instance = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pIDataConvert + 8LL))(g_pIDataConvert);
  }
  else
  {
    Instance = CoCreateInstance(&CLSID_OLEDB_CONVERSIONLIBRARY, 0, 1u, &IID_IDataConvert, &g_pIDataConvert);
    if ( Instance >= 0 )
      Instance = SetVersionDC();
  }
  *a1 = (struct IDataConvert *)g_pIDataConvert;
  --*((_DWORD *)v2 + 4);
  if ( (*((_DWORD *)v2 + 3))-- == 1 )
    *((_DWORD *)v2 + 2) = -1;
  v5 = *(_QWORD *)v2;
  --*(_DWORD *)(v5 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800204bc  mov     [rsp+arg_8], rbx
0x1800204c1  mov     [rsp+arg_10], rsi
0x1800204c6  push    rdi
0x1800204c7  sub     rsp, 30h
0x1800204cb  mov     rsi, rcx
0x1800204ce  mov     rbx, cs:?g_pcsDataConvert@@3PEAVCFoxCriticalSection@@EA; CFoxCriticalSection * g_pcsDataConvert
0x1800204d5  mov     rcx, rbx
0x1800204d8  call    cs:__imp_UMSEnterCSWraper
0x1800204de  cmp     dword ptr [rbx+0Ch], 0
0x1800204e2  jnz     short loc_1800204ED
0x1800204e4  call    cs:__imp_GetCurrentThreadId
0x1800204ea  mov     [rbx+8], eax
0x1800204ed  mov     r8d, 1; dwClsContext
0x1800204f3  add     [rbx+0Ch], r8d
0x1800204f7  add     [rbx+10h], r8d
0x1800204fb  mov     [rsp+38h+arg_0], rbx
0x180020500  mov     rcx, cs:?g_pIDataConvert@@3PEAUIDataConvert@@EA; IDataConvert * g_pIDataConvert
0x180020507  test    rcx, rcx
0x18002050a  jnz     short loc_18002053D
0x18002050c  lea     rax, ?g_pIDataConvert@@3PEAUIDataConvert@@EA; IDataConvert * g_pIDataConvert
0x180020513  mov     [rsp+38h+ppv], rax; ppv
0x180020518  lea     r9, IID_IDataConvert; riid
0x18002051f  xor     edx, edx; pUnkOuter
0x180020521  lea     rcx, CLSID_OLEDB_CONVERSIONLIBRARY; rclsid
0x180020528  call    cs:__imp_CoCreateInstance
0x18002052e  mov     edi, eax
0x180020530  test    eax, eax
0x180020532  js      short loc_18002054B
0x180020534  call    SetVersionDC
0x180020539  mov     edi, eax
0x18002053b  jmp     short loc_18002054B
0x18002053d  xor     edi, edi
0x18002053f  mov     rax, [rcx]
0x180020542  mov     rax, [rax+8]
0x180020546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002054b  mov     rax, cs:?g_pIDataConvert@@3PEAUIDataConvert@@EA; IDataConvert * g_pIDataConvert
0x180020552  mov     [rsi], rax
0x180020555  or      ecx, 0FFFFFFFFh
0x180020558  add     [rbx+10h], ecx
0x18002055b  add     [rbx+0Ch], ecx
0x18002055e  jnz     short loc_180020563
0x180020560  mov     [rbx+8], ecx
0x180020563  mov     rcx, [rbx]
0x180020566  dec     dword ptr [rcx+30h]
0x180020569  add     rcx, 8; lpCriticalSection
0x18002056d  call    cs:__imp_LeaveCriticalSection
0x180020573  mov     eax, edi
0x180020575  mov     rbx, [rsp+38h+arg_8]
0x18002057a  mov     rsi, [rsp+38h+arg_10]
0x18002057f  add     rsp, 30h
0x180020583  pop     rdi
0x180020584  retn
```
