# DllUnregisterServer

- ea: `0x1400184cc`
- end: `0x140018556`
- name: `DllUnregisterServer`
- size: `138`
- prototype: `HRESULT __stdcall()`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400183c4`
- `0x14001855c`

## callees

- `0x14001812c`
- `0x1400184cc`
- `0x1400234b8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140018506`
- `wbemcomn!GetMemLogObject` at `0x140018506`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140018511`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140018511`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rcx
  HRESULT v4; // ebx
  CMemoryLog *MemLogObject; // rax
  GUID v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = CLSID_WmiProviderHost;
  UnregisterServer(v1, v0, &v7);
  v7 = CLSID_WmiProviderHostSecured;
  v4 = UnregisterServer(v3, v2, &v7);
  if ( v4 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v4);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ab3eb8767f543ce5f762c54a6df9dbe9_Traceguids, (unsigned int)v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1400184cc  push    rbx
0x1400184ce  sub     rsp, 30h
0x1400184d2  movups  xmm0, xmmword ptr cs:CLSID_WmiProviderHost.Data1
0x1400184d9  lea     r8, [rsp+38h+var_18]
0x1400184de  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x1400184e4  call    UnregisterServer
0x1400184e9  movups  xmm0, xmmword ptr cs:CLSID_WmiProviderHostSecured.Data1
0x1400184f0  lea     r8, [rsp+38h+var_18]
0x1400184f5  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x1400184fb  call    UnregisterServer
0x140018500  mov     ebx, eax
0x140018502  test    eax, eax
0x140018504  jns     short loc_140018517
0x140018506  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001850c  mov     rcx, rax
0x14001850f  mov     edx, ebx
0x140018511  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140018517  mov     rcx, cs:WPP_GLOBAL_Control
0x14001851e  lea     rax, WPP_GLOBAL_Control
0x140018525  cmp     rcx, rax
0x140018528  jz      short loc_14001854E
0x14001852a  test    byte ptr [rcx+1Ch], 4
0x14001852e  jz      short loc_14001854E
0x140018530  cmp     byte ptr [rcx+19h], 2
0x140018534  jb      short loc_14001854E
0x140018536  mov     rcx, [rcx+10h]
0x14001853a  lea     r8, WPP_ab3eb8767f543ce5f762c54a6df9dbe9_Traceguids
0x140018541  mov     edx, 0Fh
0x140018546  mov     r9d, ebx
0x140018549  call    WPP_SF_d
0x14001854e  mov     eax, ebx
0x140018550  add     rsp, 30h
0x140018554  pop     rbx
0x140018555  retn
```
