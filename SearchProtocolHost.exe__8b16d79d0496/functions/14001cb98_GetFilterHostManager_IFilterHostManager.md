# GetFilterHostManager(IFilterHostManager * *)

- ea: `0x14001cb98`
- end: `0x14001cbe8`
- name: `?GetFilterHostManager@@YAJPEAPEAUIFilterHostManager@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(struct IFilterHostManager **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`
- `0x1400409d0`

## callees

- `0x14001cb98`
- `0x140028044`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001cbb7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001cbb7`

## string_xrefs

- `0x14001cbc8`: `onecoreuap\base\appmodel\Search\common\include\filterhostmanager.hxx`

## pseudocode

```c
__int64 __fastcall GetFilterHostManager(LPVOID *a1)
{
  HRESULT Instance; // eax
  unsigned int v2; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Instance = CoCreateInstance(&rclsid, 0, 4u, &GUID_dfaff96b_c9f3_47dd_8288_94852eef4541, a1);
  v2 = Instance;
  if ( Instance >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B,
    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\filterhostmanager.hxx",
    (const char *)(unsigned int)Instance,
    ppv);
  return v2;
}

```

## disassembly

```asm
0x14001cb98  push    rbx
0x14001cb9a  sub     rsp, 30h
0x14001cb9e  xor     edx, edx; pUnkOuter
0x14001cba0  mov     qword ptr [rsp+38h+ppv], rcx; int
0x14001cba5  lea     r9, _GUID_dfaff96b_c9f3_47dd_8288_94852eef4541; riid
0x14001cbac  lea     rcx, rclsid; rclsid
0x14001cbb3  lea     r8d, [rdx+4]; dwClsContext
0x14001cbb7  call    cs:__imp_CoCreateInstance
0x14001cbbd  mov     ebx, eax
0x14001cbbf  test    eax, eax
0x14001cbc1  jns     short loc_14001CBE0
0x14001cbc3  mov     rcx, [rsp+38h]; this
0x14001cbc8  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14001cbcf  mov     r9d, eax; char *
0x14001cbd2  mov     edx, 1Bh; void *
0x14001cbd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001cbdc  mov     eax, ebx
0x14001cbde  jmp     short loc_14001CBE2
0x14001cbe0  xor     eax, eax
0x14001cbe2  add     rsp, 30h
0x14001cbe6  pop     rbx
0x14001cbe7  retn
```
