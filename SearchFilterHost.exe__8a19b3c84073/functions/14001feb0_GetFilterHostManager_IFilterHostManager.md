# GetFilterHostManager(IFilterHostManager * *)

- ea: `0x14001feb0`
- end: `0x14001ff00`
- name: `?GetFilterHostManager@@YAJPEAPEAUIFilterHostManager@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002753c`

## callees

- `0x140009f14`
- `0x14001feb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fecf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fecf`

## string_xrefs

- `0x14001fee0`: `onecoreuap\base\appmodel\Search\common\include\filterhostmanager.hxx`

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
0x14001feb0  push    rbx
0x14001feb2  sub     rsp, 30h
0x14001feb6  xor     edx, edx; pUnkOuter
0x14001feb8  mov     qword ptr [rsp+38h+ppv], rcx; int
0x14001febd  lea     r9, _GUID_dfaff96b_c9f3_47dd_8288_94852eef4541; riid
0x14001fec4  lea     rcx, rclsid; rclsid
0x14001fecb  lea     r8d, [rdx+4]; dwClsContext
0x14001fecf  call    cs:__imp_CoCreateInstance
0x14001fed5  mov     ebx, eax
0x14001fed7  test    eax, eax
0x14001fed9  jns     short loc_14001FEF8
0x14001fedb  mov     rcx, [rsp+38h]; this
0x14001fee0  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14001fee7  mov     r9d, eax; char *
0x14001feea  mov     edx, 1Bh; void *
0x14001feef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001fef4  mov     eax, ebx
0x14001fef6  jmp     short loc_14001FEFA
0x14001fef8  xor     eax, eax
0x14001fefa  add     rsp, 30h
0x14001fefe  pop     rbx
0x14001feff  retn
```
