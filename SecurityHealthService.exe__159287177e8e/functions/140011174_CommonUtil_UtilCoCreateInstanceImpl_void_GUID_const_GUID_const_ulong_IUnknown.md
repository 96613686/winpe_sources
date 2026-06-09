# CommonUtil::UtilCoCreateInstanceImpl(void * *,_GUID const &,_GUID const &,ulong,IUnknown *)

- ea: `0x140011174`
- end: `0x1400111d8`
- name: `?UtilCoCreateInstanceImpl@CommonUtil@@YAJPEAPEAXAEBU_GUID@@1KPEAUIUnknown@@@Z`
- size: `100`
- prototype: `__int64 __fastcall(LPVOID *ppv, void **, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004174`

## callees

- `0x140011174`
- `0x1400111e0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14001119a`
- `ole32!CoCreateInstance` at `0x14001119a`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilCoCreateInstanceImpl(
        LPVOID *ppv,
        void **a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
{
  HRESULT Instance; // ebx

  *ppv = 0;
  Instance = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, ppv);
  if ( Instance >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2));
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140011174  push    rbx
0x140011176  sub     rsp, 30h
0x14001117a  xor     edx, edx; pUnkOuter
0x14001117c  mov     qword ptr [rcx], 0
0x140011183  mov     [rsp+38h+ppv], rcx; ppv
0x140011188  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14001118f  lea     rcx, CLSID_GlobalOptions; rclsid
0x140011196  lea     r8d, [rdx+1]; dwClsContext
0x14001119a  call    cs:__imp_CoCreateInstance
0x1400111a0  mov     ebx, eax
0x1400111a2  test    eax, eax
0x1400111a4  jns     short loc_1400111D0
0x1400111a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400111ad  lea     rax, WPP_GLOBAL_Control
0x1400111b4  cmp     rcx, rax
0x1400111b7  jz      short loc_1400111CC
0x1400111b9  test    byte ptr [rcx+1Ch], 1
0x1400111bd  jz      short loc_1400111CC
0x1400111bf  mov     rcx, [rcx+10h]
0x1400111c3  mov     dword ptr [rsp+38h+ppv], ebx
0x1400111c7  call    WPP_SF__guid_d
0x1400111cc  mov     eax, ebx
0x1400111ce  jmp     short loc_1400111D2
0x1400111d0  xor     eax, eax
0x1400111d2  add     rsp, 30h
0x1400111d6  pop     rbx
0x1400111d7  retn
```
