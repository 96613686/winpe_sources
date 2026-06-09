# SensorGroupGetClassFactory(_GUID const &,void * *)

- ea: `0x1800245c4`
- end: `0x180024646`
- name: `?SensorGroupGetClassFactory@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `130`
- prototype: `int(const struct _GUID *, void **)`
- caller_count: `20`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022fa0`
- `0x1800230c0`
- `0x180024070`
- `0x180024190`
- `0x1800242b0`
- `0x1800243b0`
- `0x1800244b0`
- `0x180024780`
- `0x180024cb0`
- `0x180024db0`
- `0x180056800`
- `0x1800568f0`
- `0x1800569f0`
- `0x180056ae0`
- `0x180056bd0`
- `0x180056cc0`
- `0x180056df0`
- `0x1800580e0`
- `0x1800581d0`
- `0x1800582e0`

## callees

- `0x180005fa0`
- `0x1800245c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800245ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800245ef`

## pseudocode

```c
__int64 __fastcall SensorGroupGetClassFactory(const struct _GUID *a1, void **ppv)
{
  HRESULT Instance; // ebx
  __int64 v4; // rdx

  if ( ppv )
  {
    *ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_MFSensorGroupClassFactory,
                 0,
                 1u,
                 &GUID_fe4f9dca_ffd8_4d38_932f_282acb3fb775,
                 ppv);
    if ( Instance < 0 && g_wppLevels )
    {
      v4 = 11;
      goto LABEL_8;
    }
  }
  else
  {
    Instance = -2147467261;
    if ( g_wppLevels )
    {
      v4 = 10;
LABEL_8:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, Instance);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800245c4  push    rbx
0x1800245c6  sub     rsp, 30h
0x1800245ca  test    rdx, rdx
0x1800245cd  jz      short loc_180024603
0x1800245cf  mov     qword ptr [rdx], 0
0x1800245d6  lea     r9, _GUID_fe4f9dca_ffd8_4d38_932f_282acb3fb775; riid
0x1800245dd  mov     [rsp+38h+ppv], rdx; ppv
0x1800245e2  lea     rcx, CLSID_MFSensorGroupClassFactory; rclsid
0x1800245e9  xor     edx, edx; pUnkOuter
0x1800245eb  lea     r8d, [rdx+1]; dwClsContext
0x1800245ef  call    cs:__imp_CoCreateInstance
0x1800245f5  mov     ebx, eax
0x1800245f7  test    eax, eax
0x1800245f9  js      short loc_180024618
0x1800245fb  mov     eax, ebx
0x1800245fd  add     rsp, 30h
0x180024601  pop     rbx
0x180024602  retn
0x180024603  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002460a  mov     ebx, 80004003h
0x18002460f  jb      short loc_1800245FB
0x180024611  mov     edx, 0Ah
0x180024616  jmp     short loc_180024626
0x180024618  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002461f  jb      short loc_1800245FB
0x180024621  mov     edx, 0Bh
0x180024626  mov     rcx, cs:WPP_GLOBAL_Control
0x18002462d  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180024634  xor     r9d, r9d
0x180024637  mov     dword ptr [rsp+38h+ppv], ebx
0x18002463b  mov     rcx, [rcx+10h]
0x18002463f  call    WPP_SF_qD
0x180024644  jmp     short loc_1800245FB
```
