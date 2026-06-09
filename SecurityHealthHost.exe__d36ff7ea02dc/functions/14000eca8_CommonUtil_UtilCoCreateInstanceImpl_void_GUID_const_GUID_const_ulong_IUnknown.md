# CommonUtil::UtilCoCreateInstanceImpl(void * *,_GUID const &,_GUID const &,ulong,IUnknown *)

- ea: `0x14000eca8`
- end: `0x14000ed15`
- name: `?UtilCoCreateInstanceImpl@CommonUtil@@YAJPEAPEAXAEBU_GUID@@1KPEAUIUnknown@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(LPVOID *ppv, IID *rclsid, IID *riid, DWORD dwClsContext)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002a94`
- `0x140003188`

## callees

- `0x14000eca8`
- `0x14000ed1c`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14000eccf`
- `ole32!CoCreateInstance` at `0x14000eccf`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilCoCreateInstanceImpl(LPVOID *ppv, IID *rclsid, IID *riid, DWORD dwClsContext)
{
  __int64 v5; // rdx
  HRESULT Instance; // ebx
  __int64 v7; // r8

  *ppv = 0;
  Instance = CoCreateInstance(rclsid, 0, dwClsContext, riid, ppv);
  if ( Instance >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v7, rclsid, Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14000eca8  mov     [rsp+arg_0], rbx
0x14000ecad  push    rdi
0x14000ecae  sub     rsp, 30h
0x14000ecb2  mov     eax, r9d
0x14000ecb5  mov     qword ptr [rcx], 0
0x14000ecbc  mov     rdi, rdx
0x14000ecbf  mov     [rsp+38h+ppv], rcx; ppv
0x14000ecc4  mov     r9, r8; riid
0x14000ecc7  mov     rcx, rdi; rclsid
0x14000ecca  mov     r8d, eax; dwClsContext
0x14000eccd  xor     edx, edx; pUnkOuter
0x14000eccf  call    cs:__imp_CoCreateInstance
0x14000ecd5  mov     ebx, eax
0x14000ecd7  test    eax, eax
0x14000ecd9  jns     short loc_14000ED08
0x14000ecdb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ece2  lea     rax, WPP_GLOBAL_Control
0x14000ece9  cmp     rcx, rax
0x14000ecec  jz      short loc_14000ED04
0x14000ecee  test    byte ptr [rcx+1Ch], 1
0x14000ecf2  jz      short loc_14000ED04
0x14000ecf4  mov     rcx, [rcx+10h]
0x14000ecf8  mov     r9, rdi
0x14000ecfb  mov     dword ptr [rsp+38h+ppv], ebx
0x14000ecff  call    WPP_SF__guid_d
0x14000ed04  mov     eax, ebx
0x14000ed06  jmp     short loc_14000ED0A
0x14000ed08  xor     eax, eax
0x14000ed0a  mov     rbx, [rsp+38h+arg_0]
0x14000ed0f  add     rsp, 30h
0x14000ed13  pop     rdi
0x14000ed14  retn
```
