# _lambda_e81da2bcca06b18c928f65ad7368e3c1_::operator()

- ea: `0x1800222c8`
- end: `0x18002236f`
- name: `_lambda_e81da2bcca06b18c928f65ad7368e3c1_::operator()`
- size: `167`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180022930`

## callees

- `0x18000df30`
- `0x180018844`
- `0x180018bbc`
- `0x180022000`
- `0x1800222c8`

## string_xrefs

- `0x1800222d4`: `McpGetCloudPrintServiceOperation::RuntimeClassInitialize::<lambda_e81da2bcca06b18c928f65ad7368e3c1>::operator ()`
- `0x18002235b`: `McpGetCloudPrintServiceOperation::RuntimeClassInitialize::<lambda_e81da2bcca06b18c928f65ad7368e3c1>::operator ()`

## pseudocode

```c
__int64 __fastcall lambda_e81da2bcca06b18c928f65ad7368e3c1_::operator()(__int64 a1)
{
  int (*v2)(void *); // rdx
  int (*v3)(void *); // r8
  _QWORD *v4; // r9
  int v5; // eax
  int (*v6)(void *); // r8
  _QWORD *v7; // r9
  unsigned int v8; // ebx

  if ( *(_BYTE *)(*(_QWORD *)a1 + 24LL) )
  {
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpGetCloudPrintServiceOperation::RuntimeClassInitialize::<lambda_e81da2bcca06b18c928f65ad7368e3c1>::operator ()",
      L"Initializing CloudPrintHelper Silent");
    v4 = *(_QWORD **)(*(_QWORD *)a1 + 56LL);
    if ( v4 )
      v4 = (_QWORD *)*v4;
    v5 = CloudPrint::CloudPrintHelper::InitializeSilent(
           *(CloudPrint::CloudPrintHelper **)(*(_QWORD *)a1 + 40LL),
           v2,
           v3,
           v4,
           *(_BYTE *)(*(_QWORD *)a1 + 25LL));
  }
  else
  {
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpGetCloudPrintServiceOperation::RuntimeClassInitialize::<lambda_e81da2bcca06b18c928f65ad7368e3c1>::operator ()",
      L"Initializing CloudPrintHelper");
    v7 = *(_QWORD **)(*(_QWORD *)a1 + 56LL);
    if ( v7 )
      v7 = (_QWORD *)*v7;
    LOBYTE(v6) = *(_BYTE *)(*(_QWORD *)a1 + 26LL);
    v5 = CloudPrint::CloudPrintHelper::Initialize(
           *(CloudPrint::CloudPrintHelper **)(*(_QWORD *)a1 + 40LL),
           *(int (**)(void *))(*(_QWORD *)a1 + 32LL),
           v6,
           v7,
           (bool)v6,
           *(HWND *)(*(_QWORD *)a1 + 32LL),
           *(_BYTE *)(*(_QWORD *)a1 + 25LL));
  }
  v8 = v5;
  if ( v5 < 0 )
    McpManagementTelemetry::WriteDbgTraceWarning(
      "McpGetCloudPrintServiceOperation::RuntimeClassInitialize::<lambda_e81da2bcca06b18c928f65ad7368e3c1>::operator ()",
      L"Failed to Init CloudPrintHelper. hr=%#x",
      (unsigned int)v5);
  return v8;
}

```

## disassembly

```asm
0x1800222c8  push    rbx
0x1800222ca  sub     rsp, 40h
0x1800222ce  mov     rax, [rcx]
0x1800222d1  mov     rbx, rcx
0x1800222d4  lea     rcx, aMcpgetcloudpri_4; "McpGetCloudPrintServiceOperation::Runti"...
0x1800222db  cmp     byte ptr [rax+18h], 0
0x1800222df  jz      short loc_18002230E
0x1800222e1  lea     rdx, aInitializingCl; "Initializing CloudPrintHelper Silent"
0x1800222e8  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800222ed  mov     rax, [rbx]
0x1800222f0  mov     r9, [rax+38h]
0x1800222f4  mov     cl, [rax+19h]
0x1800222f7  test    r9, r9
0x1800222fa  jz      short loc_1800222FF
0x1800222fc  mov     r9, [r9]; void *
0x1800222ff  mov     [rsp+48h+var_28], cl; bool
0x180022303  mov     rcx, [rax+28h]; this
0x180022307  call    ?InitializeSilent@CloudPrintHelper@CloudPrint@@QEAAJP6AJPEAX@Z10_N@Z; CloudPrint::CloudPrintHelper::InitializeSilent(long (*)(void *),long (*)(void *),void *,bool)
0x18002230c  jmp     short loc_18002234B
0x18002230e  lea     rdx, aInitializingCl_0; "Initializing CloudPrintHelper"
0x180022315  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002231a  mov     rax, [rbx]
0x18002231d  mov     r9, [rax+38h]
0x180022321  mov     cl, [rax+19h]
0x180022324  mov     rdx, [rax+20h]; int (*)(void *)
0x180022328  mov     r8b, [rax+1Ah]; int (*)(void *)
0x18002232c  test    r9, r9
0x18002232f  jz      short loc_180022334
0x180022331  mov     r9, [r9]; void *
0x180022334  mov     [rsp+48h+var_18], cl; bool
0x180022338  mov     rcx, [rax+28h]; this
0x18002233c  mov     [rsp+48h+var_20], rdx; HWND
0x180022341  mov     [rsp+48h+var_28], r8b; bool
0x180022346  call    ?Initialize@CloudPrintHelper@CloudPrint@@QEAAJP6AJPEAX@Z10_NPEAUHWND__@@2@Z; CloudPrint::CloudPrintHelper::Initialize(long (*)(void *),long (*)(void *),void *,bool,HWND__ *,bool)
0x18002234b  mov     ebx, eax
0x18002234d  test    eax, eax
0x18002234f  jns     short loc_180022367
0x180022351  mov     r8d, eax
0x180022354  lea     rdx, aFailedToInitCl; "Failed to Init CloudPrintHelper. hr=%#x"
0x18002235b  lea     rcx, aMcpgetcloudpri_4; "McpGetCloudPrintServiceOperation::Runti"...
0x180022362  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180022367  mov     eax, ebx
0x180022369  add     rsp, 40h
0x18002236d  pop     rbx
0x18002236e  retn
```
