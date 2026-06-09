# DllRegisterServer

- ea: `0x14001855c`
- end: `0x14001861e`
- name: `DllRegisterServer`
- size: `194`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400183c4`

## callees

- `0x1400184cc`
- `0x14001855c`
- `0x140018624`
- `0x1400234b8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400185ce`
- `wbemcomn!GetMemLogObject` at `0x1400185ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400185d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400185d9`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rcx
  HRESULT v4; // ebx
  CMemoryLog *MemLogObject; // rax
  GUID v7; // [rsp+30h] [rbp-18h] BYREF

  DllUnregisterServer();
  v7 = CLSID_WmiProviderHost;
  RegisterServer(v1, v0, &v7, (BYTE *)L"Microsoft WMI Provider Subsystem Host", 0, 0);
  v7 = CLSID_WmiProviderHostSecured;
  v4 = RegisterServer(v3, v2, &v7, (BYTE *)L"Microsoft WMI Provider Subsystem Secured Host", L"-secured", 1);
  if ( v4 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v4);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ab3eb8767f543ce5f762c54a6df9dbe9_Traceguids, (unsigned int)v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14001855c  push    rbx
0x14001855e  sub     rsp, 40h
0x140018562  call    DllUnregisterServer
0x140018567  movups  xmm0, xmmword ptr cs:CLSID_WmiProviderHost.Data1
0x14001856e  mov     [rsp+48h+var_20], 0
0x140018576  lea     r9, aMicrosoftWmiPr_0; "Microsoft WMI Provider Subsystem Host"
0x14001857d  lea     r8, [rsp+48h+var_18]
0x140018582  mov     [rsp+48h+var_28], 0
0x14001858b  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x140018591  call    RegisterServer
0x140018596  movups  xmm0, xmmword ptr cs:CLSID_WmiProviderHostSecured.Data1
0x14001859d  lea     rax, aSecured; "-secured"
0x1400185a4  mov     [rsp+48h+var_20], 1
0x1400185ac  lea     r9, aMicrosoftWmiPr; "Microsoft WMI Provider Subsystem Secure"...
0x1400185b3  mov     [rsp+48h+var_28], rax
0x1400185b8  lea     r8, [rsp+48h+var_18]
0x1400185bd  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x1400185c3  call    RegisterServer
0x1400185c8  mov     ebx, eax
0x1400185ca  test    eax, eax
0x1400185cc  jns     short loc_1400185DF
0x1400185ce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400185d4  mov     rcx, rax
0x1400185d7  mov     edx, ebx
0x1400185d9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400185df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400185e6  lea     rax, WPP_GLOBAL_Control
0x1400185ed  cmp     rcx, rax
0x1400185f0  jz      short loc_140018616
0x1400185f2  test    byte ptr [rcx+1Ch], 4
0x1400185f6  jz      short loc_140018616
0x1400185f8  cmp     byte ptr [rcx+19h], 2
0x1400185fc  jb      short loc_140018616
0x1400185fe  mov     rcx, [rcx+10h]
0x140018602  lea     r8, WPP_ab3eb8767f543ce5f762c54a6df9dbe9_Traceguids
0x140018609  mov     edx, 0Eh
0x14001860e  mov     r9d, ebx
0x140018611  call    WPP_SF_d
0x140018616  mov     eax, ebx
0x140018618  add     rsp, 40h
0x14001861c  pop     rbx
0x14001861d  retn
```
