# COleDispatchDriver::CreateDispatch(_GUID const &,COleException *)

- ea: `0x1800886c0`
- end: `0x180088790`
- name: `?CreateDispatch@COleDispatchDriver@@QEAAHAEBU_GUID@@PEAVCOleException@@@Z`
- size: `208`
- prototype: `int(COleDispatchDriver *__hidden this, const struct _GUID *, struct COleException *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800887a0`

## callees

- `0x18000a150`
- `0x1800886c0`
- `0x18009cf3c`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800886fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180088725`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800886fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180088725`
- `OLE32!OleRun` at `0x180088736`
- `OLE32!OleRun` at `0x180088736`

## pseudocode

```c
__int64 __fastcall COleDispatchDriver::CreateDispatch(
        COleDispatchDriver *this,
        const struct _GUID *a2,
        struct COleException *a3)
{
  HRESULT Instance; // ebx
  struct IUnknown *Interface; // rax
  LPUNKNOWN pUnknown; // [rsp+60h] [rbp+8h] BYREF

  *((_DWORD *)this + 2) = 1;
  pUnknown = 0;
  Instance = CoCreateInstance(a2, 0, 0x17u, &IID_IUnknown, (LPVOID *)&pUnknown);
  if ( Instance == -2147024809 )
    Instance = CoCreateInstance(a2, 0, 7u, &IID_IUnknown, (LPVOID *)&pUnknown);
  if ( Instance >= 0
    && (Instance = OleRun(pUnknown), Instance >= 0)
    && (Interface = _AfxQueryInterface(pUnknown, &IID_IDispatch), (*(_QWORD *)this = Interface) != 0) )
  {
    ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
    return 1;
  }
  else
  {
    _AfxRelease(&pUnknown);
    if ( a3 )
      *((_DWORD *)a3 + 4) = Instance;
    return 0;
  }
}

```

## disassembly

```asm
0x1800886c0  push    rbx
0x1800886c2  push    rbp
0x1800886c3  push    rsi
0x1800886c4  push    rdi
0x1800886c5  sub     rsp, 38h
0x1800886c9  mov     rbp, rdx
0x1800886cc  mov     dword ptr [rcx+8], 1
0x1800886d3  xor     edx, edx; pUnkOuter
0x1800886d5  mov     [rsp+58h+pUnknown], 0
0x1800886de  mov     rdi, r8
0x1800886e1  lea     rax, [rsp+58h+pUnknown]
0x1800886e6  mov     rsi, rcx
0x1800886e9  mov     [rsp+58h+ppv], rax; ppv
0x1800886ee  lea     r9, IID_IUnknown; riid
0x1800886f5  mov     rcx, rbp; rclsid
0x1800886f8  lea     r8d, [rdx+17h]; dwClsContext
0x1800886fc  call    cs:__imp_CoCreateInstance
0x180088702  mov     ebx, eax
0x180088704  cmp     eax, 80070057h
0x180088709  jnz     short loc_18008872D
0x18008870b  xor     edx, edx; pUnkOuter
0x18008870d  lea     rax, [rsp+58h+pUnknown]
0x180088712  lea     r9, IID_IUnknown; riid
0x180088719  mov     [rsp+58h+ppv], rax; ppv
0x18008871e  mov     rcx, rbp; rclsid
0x180088721  lea     r8d, [rdx+7]; dwClsContext
0x180088725  call    cs:__imp_CoCreateInstance
0x18008872b  mov     ebx, eax
0x18008872d  test    ebx, ebx
0x18008872f  js      short loc_180088773
0x180088731  mov     rcx, [rsp+58h+pUnknown]; pUnknown
0x180088736  call    cs:__imp_OleRun
0x18008873c  mov     ebx, eax
0x18008873e  test    eax, eax
0x180088740  js      short loc_180088773
0x180088742  mov     rcx, [rsp+58h+pUnknown]; struct IUnknown *
0x180088747  lea     rdx, IID_IDispatch; struct _GUID *
0x18008874e  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x180088753  mov     [rsi], rax
0x180088756  test    rax, rax
0x180088759  jz      short loc_180088773
0x18008875b  mov     rcx, [rsp+58h+pUnknown]
0x180088760  mov     rdx, [rcx]
0x180088763  mov     rax, [rdx+10h]
0x180088767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008876c  mov     eax, 1
0x180088771  jmp     short loc_180088787
0x180088773  lea     rcx, [rsp+58h+pUnknown]; struct IUnknown **
0x180088778  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x18008877d  test    rdi, rdi
0x180088780  jz      short loc_180088785
0x180088782  mov     [rdi+10h], ebx
0x180088785  xor     eax, eax
0x180088787  add     rsp, 38h
0x18008878b  pop     rdi
0x18008878c  pop     rsi
0x18008878d  pop     rbp
0x18008878e  pop     rbx
0x18008878f  retn
```
