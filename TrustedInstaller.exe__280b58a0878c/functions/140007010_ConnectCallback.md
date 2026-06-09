# ConnectCallback

- ea: `0x140007010`
- end: `0x1400070c9`
- name: `ConnectCallback`
- size: `185`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007010`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140007092`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140007092`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140007063`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140007063`

## string_xrefs

- `0x14000709e`: `Unable to resume suspended COM objects.`

## pseudocode

```c
__int64 ConnectCallback()
{
  unsigned int i; // edi
  unsigned __int64 v1; // rcx
  IUnknown *v2; // rdx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HRESULT v5; // eax

  for ( i = 0; i < 4; ++i )
  {
    v1 = 32LL * (int)i;
    if ( *(_DWORD *)((char *)&vrgComInfo + v1 + 28) <= vComRegPhase )
    {
      v2 = *(IUnknown **)((char *)&vrgComInfo + v1 + 16);
      if ( v2 )
      {
        v3 = CoRegisterClassObject(
               (const IID *const)((char *)&vrgComInfo + v1),
               v2,
               4u,
               5u,
               (LPDWORD)&qword_14003F298[v1 / 8]);
        v4 = v3;
        if ( v3 < 0 )
        {
          CBSWdsLogLight(0x4000000, (unsigned int)v3, 1, "Failed to register class factory No:%d", i);
          return v4;
        }
      }
    }
  }
  v5 = CoResumeClassObjects();
  v4 = v5;
  if ( v5 < 0 )
    CBSWdsLogLight(0x4000000, (unsigned int)v5, 1, "Unable to resume suspended COM objects.");
  return v4;
}

```

## disassembly

```asm
0x140007010  mov     [rsp+arg_0], rbx
0x140007015  mov     [rsp+arg_8], rbp
0x14000701a  push    rdi
0x14000701b  sub     rsp, 30h
0x14000701f  xor     edi, edi
0x140007021  lea     rbp, ?vrgComInfo@@3PAUCOM_INFORMATION@@A; COM_INFORMATION near * vrgComInfo
0x140007028  cmp     edi, 4
0x14000702b  jnb     short loc_140007092
0x14000702d  mov     eax, cs:?vComRegPhase@@3W4COM_REGISTER_PHASE@@A; COM_REGISTER_PHASE vComRegPhase
0x140007033  movsxd  rcx, edi
0x140007036  shl     rcx, 5
0x14000703a  cmp     [rcx+rbp+1Ch], eax
0x14000703e  jg      short loc_14000706F
0x140007040  mov     rdx, [rcx+rbp+10h]; pUnk
0x140007045  test    rdx, rdx
0x140007048  jz      short loc_14000706F
0x14000704a  mov     r9d, 5; flags
0x140007050  lea     rax, [rbp+18h]
0x140007054  add     rax, rcx
0x140007057  add     rcx, rbp; rclsid
0x14000705a  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x14000705f  lea     r8d, [r9-1]; dwClsContext
0x140007063  call    cs:__imp_CoRegisterClassObject
0x140007069  mov     ebx, eax
0x14000706b  test    eax, eax
0x14000706d  js      short loc_140007073
0x14000706f  inc     edi
0x140007071  jmp     short loc_140007028
0x140007073  lea     r9, aFailedToRegist; "Failed to register class factory No:%d"
0x14000707a  mov     dword ptr [rsp+38h+lpdwRegister], edi
0x14000707e  mov     r8d, 1
0x140007084  mov     edx, eax
0x140007086  mov     ecx, 4000000h
0x14000708b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007090  jmp     short loc_1400070B7
0x140007092  call    cs:__imp_CoResumeClassObjects
0x140007098  mov     ebx, eax
0x14000709a  test    eax, eax
0x14000709c  jns     short loc_1400070B7
0x14000709e  lea     r9, aUnableToResume; "Unable to resume suspended COM objects."
0x1400070a5  mov     r8d, 1
0x1400070ab  mov     edx, eax
0x1400070ad  mov     ecx, 4000000h
0x1400070b2  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400070b7  mov     rbp, [rsp+38h+arg_8]
0x1400070bc  mov     eax, ebx
0x1400070be  mov     rbx, [rsp+38h+arg_0]
0x1400070c3  add     rsp, 30h
0x1400070c7  pop     rdi
0x1400070c8  retn
```
