# DoReverseAdapterMaintenanceInternal(int,GenerateEnum)

- ea: `0x140006bb4`
- end: `0x140006d1e`
- name: `?DoReverseAdapterMaintenanceInternal@@YAJHW4GenerateEnum@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140005ad0`

## callees

- `0x140006528`
- `0x140006870`
- `0x140006bb4`
- `0x1400076bc`
- `0x14000784c`
- `0x140007ab8`
- `0x14000887c`
- `0x140017010`

## import_xrefs

- `wbemcomn!??0CStaticCritSec@@QEAA@XZ` at `0x140006c08`
- `wbemcomn!??0CStaticCritSec@@QEAA@XZ` at `0x140006c08`
- `wbemcomn!?anyFailure@CStaticCritSec@@SAHXZ` at `0x140006bc7`
- `wbemcomn!?anyFailure@CStaticCritSec@@SAHXZ` at `0x140006bc7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006beb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006beb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006cbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006cbc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006c8e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006c8e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006d02`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006d02`

## pseudocode

```c
__int64 __fastcall DoReverseAdapterMaintenanceInternal(unsigned int a1)
{
  unsigned int v1; // r14d
  _DWORD *v3; // rax
  WmiRefresherStuff *v4; // rdi
  HRESULT Instance; // edi
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF
  _DWORD *v10; // [rsp+68h] [rbp+20h]

  v1 = a1;
  if ( (unsigned int)CStaticCritSec::anyFailure() )
    return 2147749894LL;
  std::unique_ptr<WmiRefresherStuff>::unique_ptr<WmiRefresherStuff>(&v9);
  try
  {
    v3 = CWin32DefaultArena::WbemMemAlloc(0x80u);
    v4 = (WmiRefresherStuff *)v3;
    v10 = v3;
    if ( v3 )
    {
      *v3 = 0;
      CStaticCritSec::CStaticCritSec((CStaticCritSec *)(v3 + 2));
      *((_QWORD *)v4 + 7) = 0;
      *((_QWORD *)v4 + 8) = 0;
      *((_QWORD *)v4 + 9) = 0;
      *((_QWORD *)v4 + 10) = 0;
      *((_QWORD *)v4 + 14) = 0;
      *((_QWORD *)v4 + 15) = 0;
      WmiRefresherStuff::WMIHandleInit(v4);
    }
    std::unique_ptr<WmiRefresherStuff>::reset(&v9, v4);
    Instance = 0;
    v6 = v9;
    if ( !v9 )
      Instance = -2147024882;
  }
  catch ( CX_MemoryException )
  {
    v1 = a1;
    Instance = -2147024882;
    v6 = v9;
  }
  v3 = CWin32DefaultArena::WbemMemAlloc(0x80u);
  v4 = (WmiRefresherStuff *)v3;
  v10 = v3;
}

```

## disassembly

```asm
0x140006bb4  mov     [rsp+arg_8], edx
0x140006bb8  mov     [rsp+arg_0], ecx
0x140006bbc  push    rsi
0x140006bbd  push    rdi
0x140006bbe  push    r14
0x140006bc0  sub     rsp, 30h
0x140006bc4  mov     r14d, ecx
0x140006bc7  call    cs:__imp_?anyFailure@CStaticCritSec@@SAHXZ; CStaticCritSec::anyFailure(void)
0x140006bcd  test    eax, eax
0x140006bcf  jz      short loc_140006BDB
0x140006bd1  mov     eax, 80041006h
0x140006bd6  jmp     loc_140006D15
0x140006bdb  lea     rcx, [rsp+48h+arg_10]
0x140006be0  call    ??0?$unique_ptr@VWmiRefresherStuff@@U?$default_delete@VWmiRefresherStuff@@@std@@@std@@QEAA@XZ; std::unique_ptr<WmiRefresherStuff>::unique_ptr<WmiRefresherStuff>(void)
0x140006be5  nop
0x140006be6  mov     ecx, 80h
0x140006beb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140006bf1  mov     rdi, rax
0x140006bf4  mov     [rsp+48h+arg_18], rax
0x140006bf9  test    rdi, rdi
0x140006bfc  jz      short loc_140006C47
0x140006bfe  mov     dword ptr [rax], 0
0x140006c04  lea     rcx, [rax+8]
0x140006c08  call    cs:__imp_??0CStaticCritSec@@QEAA@XZ; CStaticCritSec::CStaticCritSec(void)
0x140006c0e  mov     qword ptr [rdi+38h], 0
0x140006c16  mov     qword ptr [rdi+40h], 0
0x140006c1e  mov     qword ptr [rdi+48h], 0
0x140006c26  mov     qword ptr [rdi+50h], 0
0x140006c2e  mov     qword ptr [rdi+70h], 0
0x140006c36  mov     qword ptr [rdi+78h], 0
0x140006c3e  mov     rcx, rdi; this
0x140006c41  call    ?WMIHandleInit@WmiRefresherStuff@@AEAAJXZ; WmiRefresherStuff::WMIHandleInit(void)
0x140006c46  nop
0x140006c47  mov     rdx, rdi
0x140006c4a  lea     rcx, [rsp+48h+arg_10]
0x140006c4f  call    ?reset@?$unique_ptr@VWmiRefresherStuff@@U?$default_delete@VWmiRefresherStuff@@@std@@@std@@QEAAXPEAVWmiRefresherStuff@@@Z; std::unique_ptr<WmiRefresherStuff>::reset(WmiRefresherStuff *)
0x140006c54  xor     edi, edi
0x140006c56  mov     eax, 8007000Eh
0x140006c5b  mov     rsi, [rsp+48h+arg_10]
0x140006c60  test    rsi, rsi
0x140006c63  cmovz   edi, eax
0x140006c66  jmp     short loc_140006C76
0x140006c68  mov     r14d, [rsp+48h+arg_0]
0x140006c6d  mov     edi, [rsp+48h+arg_8]
0x140006c71  mov     rsi, [rsp+48h+arg_10]
0x140006c76  test    rsi, rsi
0x140006c79  jz      loc_140006D09
0x140006c7f  call    ?WbemMaintenanceInitialize@@YAJXZ; WbemMaintenanceInitialize(void)
0x140006c84  mov     edi, eax
0x140006c86  test    eax, eax
0x140006c88  js      short loc_140006D09
0x140006c8a  xor     edx, edx; dwCoInit
0x140006c8c  xor     ecx, ecx; pvReserved
0x140006c8e  call    cs:__imp_CoInitializeEx
0x140006c94  mov     edi, eax
0x140006c96  test    eax, eax
0x140006c98  js      short loc_140006CC4
0x140006c9a  mov     r8d, 1; dwClsContext
0x140006ca0  mov     [rsi], r8d
0x140006ca3  lea     rax, [rsi+38h]
0x140006ca7  mov     [rsp+48h+ppv], rax; ppv
0x140006cac  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x140006cb3  xor     edx, edx; pUnkOuter
0x140006cb5  lea     rcx, _GUID_4590f811_1d3a_11d0_891f_00aa004b2e24; rclsid
0x140006cbc  call    cs:__imp_CoCreateInstance
0x140006cc2  mov     edi, eax
0x140006cc4  test    edi, edi
0x140006cc6  js      short loc_140006CE0
0x140006cc8  mov     edx, r14d
0x140006ccb  mov     rcx, rsi
0x140006cce  call    ?Generate@WmiRefresherStuff@@QEAAJHW4GenerateEnum@@@Z; WmiRefresherStuff::Generate(int,GenerateEnum)
0x140006cd3  mov     edi, eax
0x140006cd5  jmp     short loc_140006CE0
0x140006cd7  mov     edi, [rsp+48h+arg_8]
0x140006cdb  mov     rsi, [rsp+48h+arg_10]
0x140006ce0  cmp     dword ptr [rsi], 0
0x140006ce3  jz      short loc_140006D09
0x140006ce5  mov     rcx, [rsi+38h]
0x140006ce9  test    rcx, rcx
0x140006cec  jz      short loc_140006D02
0x140006cee  mov     qword ptr [rsi+38h], 0
0x140006cf6  mov     rax, [rcx]
0x140006cf9  mov     rax, [rax+10h]
0x140006cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d02  call    cs:__imp_CoUninitialize
0x140006d08  nop
0x140006d09  lea     rcx, [rsp+48h+arg_10]
0x140006d0e  call    ??1?$unique_ptr@VWmiRefresherStuff@@U?$default_delete@VWmiRefresherStuff@@@std@@@std@@QEAA@XZ; std::unique_ptr<WmiRefresherStuff>::~unique_ptr<WmiRefresherStuff>(void)
0x140006d13  mov     eax, edi
0x140006d15  add     rsp, 30h
0x140006d19  pop     r14
0x140006d1b  pop     rdi
0x140006d1c  pop     rsi
0x140006d1d  retn
```
