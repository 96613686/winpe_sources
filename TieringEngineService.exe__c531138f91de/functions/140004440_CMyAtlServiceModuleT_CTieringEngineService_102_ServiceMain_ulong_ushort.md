# CMyAtlServiceModuleT<CTieringEngineService,102>::ServiceMain(ulong,ushort * *)

- ea: `0x140004440`
- end: `0x1400045c9`
- name: `?ServiceMain@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXKPEAPEAG@Z`
- size: `393`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400048c0`

## callees

- `0x140003e38`
- `0x140004440`
- `0x1400045d0`
- `0x140004a68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004536`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400044d0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400044d0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400045ba`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400045ba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004499`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004499`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400044ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400044ec`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x14000447b`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x14000447b`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14000452c`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14000452c`

## string_xrefs

- `0x1400044e5`: `Mscoree.dll`

## pseudocode

```c
void __fastcall CMyAtlServiceModuleT<CTieringEngineService,102>::ServiceMain(__int64 a1, int a2)
{
  CTieringEngineService *v2; // rbx
  char v3; // di
  SERVICE_STATUS_HANDLE v4; // rax
  void *v5; // rcx
  HRESULT v6; // eax
  signed int LastError; // eax
  int v8; // [rsp+48h] [rbp+10h] BYREF
  CTieringEngineService *v9; // [rsp+50h] [rbp+18h]

  v8 = a2;
  v2 = ATL::_pAtlModule;
  v9 = ATL::_pAtlModule;
  v3 = 0;
  *((_DWORD *)ATL::_pAtlModule + 157) = 2;
  v4 = RegisterServiceCtrlHandlerW((LPCWSTR)v2 + 52, CMyAtlServiceModuleT<CTieringEngineService,102>::_Handler);
  *((_QWORD *)v2 + 77) = v4;
  if ( !v4 )
    goto LABEL_2;
  CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(v2, 2);
  *((_DWORD *)v2 + 159) = 0;
  *(_QWORD *)((char *)v2 + 644) = 0;
  v6 = CoInitializeEx(0, 0);
  if ( v6 >= 0 )
  {
    *((_BYTE *)v2 + 98) = 1;
    v3 = 1;
    goto LABEL_10;
  }
  if ( v6 == -2147417850 && GetModuleHandleW(L"Mscoree.dll") )
  {
LABEL_10:
    *((_BYTE *)v2 + 96) = 0;
    v8 = 1;
    if ( (unsigned int)SetProcessMitigationPolicy(16, &v8) )
    {
      *((_DWORD *)v2 + 159) = CTieringEngineService::Run(v2);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids,
          (unsigned int)LastError);
      }
    }
  }
  if ( *((_QWORD *)v2 + 77) )
  {
    CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(v2, 1);
    *((_QWORD *)v2 + 77) = 0;
  }
  if ( v3 )
  {
    CoUninitialize();
    *((_BYTE *)v2 + 98) = 0;
  }
LABEL_2:
  v5 = (void *)*((_QWORD *)v2 + 82);
  if ( v5 )
    SetEvent(v5);
}

```

## disassembly

```asm
0x140004440  mov     rax, rsp
0x140004443  mov     [rax+8], rbx
0x140004447  mov     [rax+18h], r8
0x14000444b  mov     [rax+10h], edx
0x14000444e  push    rdi
0x14000444f  sub     rsp, 30h
0x140004453  mov     rbx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000445a  mov     [rsp+38h+arg_10], rbx
0x14000445f  xor     dil, dil
0x140004462  mov     [rax-18h], dil
0x140004466  mov     dword ptr [rbx+274h], 2
0x140004470  lea     rcx, [rbx+68h]; lpServiceName
0x140004474  lea     rdx, ?_Handler@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@KAXK@Z; lpHandlerProc
0x14000447b  call    cs:__imp_RegisterServiceCtrlHandlerW
0x140004481  mov     [rbx+268h], rax
0x140004488  test    rax, rax
0x14000448b  jnz     short loc_1400044AA
0x14000448d  mov     rcx, [rbx+290h]; hEvent
0x140004494  test    rcx, rcx
0x140004497  jz      short loc_14000449F
0x140004499  call    cs:__imp_SetEvent
0x14000449f  mov     rbx, [rsp+38h+arg_0]
0x1400044a4  add     rsp, 30h
0x1400044a8  pop     rdi
0x1400044a9  retn
0x1400044aa  mov     edx, 2
0x1400044af  mov     rcx, rbx
0x1400044b2  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x1400044b7  mov     dword ptr [rbx+27Ch], 0
0x1400044c1  mov     qword ptr [rbx+284h], 0
0x1400044cc  xor     edx, edx; dwCoInit
0x1400044ce  xor     ecx, ecx; pvReserved
0x1400044d0  call    cs:__imp_CoInitializeEx
0x1400044d6  test    eax, eax
0x1400044d8  jns     short loc_1400044FD
0x1400044da  cmp     eax, 80010106h
0x1400044df  jnz     loc_14000458F
0x1400044e5  lea     rcx, ModuleName; "Mscoree.dll"
0x1400044ec  call    cs:__imp_GetModuleHandleW
0x1400044f2  test    rax, rax
0x1400044f5  jz      loc_14000458F
0x1400044fb  jmp     short loc_140004509
0x1400044fd  mov     byte ptr [rbx+62h], 1
0x140004501  mov     dil, 1
0x140004504  mov     [rsp+38h+var_18], dil
0x140004509  mov     byte ptr [rbx+60h], 0
0x14000450d  mov     [rsp+38h+arg_8], 0
0x140004515  mov     [rsp+38h+arg_8], 1
0x14000451d  mov     r8d, 4
0x140004523  lea     rdx, [rsp+38h+arg_8]
0x140004528  lea     ecx, [r8+0Ch]
0x14000452c  call    cs:__imp_SetProcessMitigationPolicy
0x140004532  test    eax, eax
0x140004534  jnz     short loc_140004581
0x140004536  call    cs:__imp_GetLastError
0x14000453c  test    eax, eax
0x14000453e  jle     short loc_140004548
0x140004540  movzx   eax, ax
0x140004543  or      eax, 80070000h
0x140004548  lea     rdx, WPP_GLOBAL_Control
0x14000454f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004556  cmp     rcx, rdx
0x140004559  jz      short loc_14000458F
0x14000455b  test    byte ptr [rcx+1Ch], 1
0x14000455f  jz      short loc_14000458F
0x140004561  cmp     byte ptr [rcx+19h], 2
0x140004565  jb      short loc_14000458F
0x140004567  mov     edx, 0Ah
0x14000456c  mov     r9d, eax
0x14000456f  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004576  mov     rcx, [rcx+10h]
0x14000457a  call    WPP_SF_d
0x14000457f  jmp     short loc_14000458F
0x140004581  mov     rcx, rbx; this
0x140004584  call    ?Run@CTieringEngineService@@QEAAJH@Z; CTieringEngineService::Run(int)
0x140004589  mov     [rbx+27Ch], eax
0x14000458f  cmp     qword ptr [rbx+268h], 0
0x140004597  jz      short loc_1400045B1
0x140004599  mov     edx, 1
0x14000459e  mov     rcx, rbx
0x1400045a1  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x1400045a6  mov     qword ptr [rbx+268h], 0
0x1400045b1  test    dil, dil
0x1400045b4  jz      loc_14000448D
0x1400045ba  call    cs:__imp_CoUninitialize
0x1400045c0  mov     byte ptr [rbx+62h], 0
0x1400045c4  jmp     loc_14000448D
```
