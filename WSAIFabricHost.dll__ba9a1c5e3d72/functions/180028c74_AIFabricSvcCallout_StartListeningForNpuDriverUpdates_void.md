# AIFabricSvcCallout::StartListeningForNpuDriverUpdates(void)

- ea: `0x180028c74`
- end: `0x180028dd7`
- name: `?StartListeningForNpuDriverUpdates@AIFabricSvcCallout@@AEAAXXZ`
- size: `355`
- prototype: `void __fastcall(AIFabricSvcCallout *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027f48`

## callees

- `0x180004ca0`
- `0x1800189b8`
- `0x180028c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028d50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028d50`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180028d90`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180028d90`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180028d48`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180028d48`

## string_xrefs

- `0x180028dc2`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\aifabricsvccallout.cpp`

## pseudocode

```c
void __fastcall AIFabricSvcCallout::StartListeningForNpuDriverUpdates(AIFabricSvcCallout *this)
{
  _QWORD *v1; // rdi
  __int64 v2; // rsi
  DWORD LastError; // ebx
  int v5; // eax
  int v6; // [rsp+20h] [rbp-89h]
  GUID v7; // [rsp+50h] [rbp-59h] BYREF
  int v8; // [rsp+60h] [rbp-49h] BYREF
  DEVPROPKEY v9; // [rsp+68h] [rbp-41h]
  int v10; // [rsp+7Ch] [rbp-2Dh]
  __int64 v11; // [rsp+80h] [rbp-29h]
  int v12; // [rsp+88h] [rbp-21h]
  int v13; // [rsp+8Ch] [rbp-1Dh]
  GUID *v14; // [rsp+90h] [rbp-19h]
  DEVPROPKEY v15; // [rsp+A0h] [rbp-9h] BYREF
  int v16; // [rsp+B4h] [rbp+Bh]
  __int64 v17; // [rsp+B8h] [rbp+Fh]
  DEVPROPKEY v18; // [rsp+C0h] [rbp+17h]
  int v19; // [rsp+D4h] [rbp+2Bh]
  __int64 v20; // [rsp+D8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v1 = (_QWORD *)((char *)this + 48);
  v2 = *((_QWORD *)this + 6);
  v15 = DEVPKEY_Device_DriverInfPath;
  v18 = DEVPKEY_Device_IsRebootRequired;
  v9 = DEVPKEY_Device_ClassGuid;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v8 = 2;
  v10 = 0;
  v11 = 0;
  v12 = 13;
  v13 = 16;
  v14 = &v7;
  v7 = GUID_DEVCLASS_COMPUTEACCELERATOR;
  if ( v2 )
  {
    LastError = GetLastError();
    DevCloseObjectQuery(v2);
    SetLastError(LastError);
  }
  *v1 = 0;
  v5 = DevCreateObjectQuery(3, 1, 2, &v15, 1, &v8, AIFabricSvcCallout::NpuDeviceQueryCallback, this, v1);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\aifabricsvccallout.cpp",
      (const char *)(unsigned int)v5,
      v6);
}

```

## disassembly

```asm
0x180028c74  mov     [rsp-8+arg_8], rbx
0x180028c79  mov     [rsp-8+arg_10], rsi
0x180028c7e  push    rbp
0x180028c7f  push    rdi
0x180028c80  push    r14
0x180028c82  lea     rbp, [rsp-47h]
0x180028c87  sub     rsp, 0F0h
0x180028c8e  mov     rax, cs:__security_cookie
0x180028c95  xor     rax, rsp
0x180028c98  mov     [rbp+57h+var_20], rax
0x180028c9c  mov     eax, cs:DEVPKEY_Device_DriverInfPath.pid
0x180028ca2  lea     rdi, [rcx+30h]
0x180028ca6  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverInfPath.fmtid.Data1
0x180028cad  mov     rsi, [rdi]
0x180028cb0  mov     r14, rcx
0x180028cb3  mov     [rbp+57h+var_50], eax
0x180028cb6  mov     eax, cs:DEVPKEY_Device_IsRebootRequired.pid
0x180028cbc  movaps  [rbp+57h+var_60], xmm0
0x180028cc0  mov     [rbp+57h+var_30], eax
0x180028cc3  mov     eax, cs:DEVPKEY_Device_ClassGuid.pid
0x180028cc9  mov     [rbp+57h+var_88], eax
0x180028ccc  lea     rax, [rbp+57h+var_B0]
0x180028cd0  mov     [rbp+57h+var_4C], 0
0x180028cd7  mov     [rbp+57h+var_48], 0
0x180028cdf  mov     [rbp+57h+var_2C], 0
0x180028ce6  mov     [rbp+57h+var_28], 0
0x180028cee  mov     [rbp+57h+var_A0], 2
0x180028cf5  mov     [rbp+57h+var_84], 0
0x180028cfc  mov     [rbp+57h+var_80], 0
0x180028d04  mov     [rbp+57h+var_78], 0Dh
0x180028d0b  mov     [rbp+57h+var_74], 10h
0x180028d12  mov     [rbp+57h+var_70], rax
0x180028d16  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_IsRebootRequired.fmtid.Data1
0x180028d1d  movaps  [rbp+57h+var_40], xmm0
0x180028d21  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_COMPUTEACCELERATOR.Data1
0x180028d28  movdqu  [rbp+57h+var_B0], xmm0
0x180028d2d  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ClassGuid.fmtid.Data1
0x180028d34  movups  [rbp+57h+var_98], xmm0
0x180028d38  test    rsi, rsi
0x180028d3b  jz      short loc_180028D56
0x180028d3d  call    cs:__imp_GetLastError
0x180028d43  mov     rcx, rsi
0x180028d46  mov     ebx, eax
0x180028d48  call    cs:__imp_DevCloseObjectQuery
0x180028d4e  mov     ecx, ebx; dwErrCode
0x180028d50  call    cs:__imp_SetLastError
0x180028d56  mov     [rsp+100h+var_C0], rdi
0x180028d5b  lea     rax, ?NpuDeviceQueryCallback@AIFabricSvcCallout@@SAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; AIFabricSvcCallout::NpuDeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180028d62  mov     edx, 1
0x180028d67  mov     [rsp+100h+var_C8], r14
0x180028d6c  mov     [rsp+100h+var_D0], rax
0x180028d71  lea     r9, [rbp+57h+var_60]
0x180028d75  lea     rax, [rbp+57h+var_A0]
0x180028d79  mov     qword ptr [rdi], 0
0x180028d80  mov     [rsp+100h+var_D8], rax
0x180028d85  lea     ecx, [rdx+2]
0x180028d88  mov     [rsp+100h+var_E0], edx; int
0x180028d8c  lea     r8d, [rdx+1]
0x180028d90  call    cs:__imp_DevCreateObjectQuery
0x180028d96  test    eax, eax
0x180028d98  js      short loc_180028DBE
0x180028d9a  mov     rcx, [rbp+57h+var_20]
0x180028d9e  xor     rcx, rsp; StackCookie
0x180028da1  call    __security_check_cookie
0x180028da6  lea     r11, [rsp+100h+var_10]
0x180028dae  mov     rbx, [r11+28h]
0x180028db2  mov     rsi, [r11+30h]
0x180028db6  mov     rsp, r11
0x180028db9  pop     r14
0x180028dbb  pop     rdi
0x180028dbc  pop     rbp
0x180028dbd  retn
0x180028dbe  mov     rcx, [rbp+5Fh]; this
0x180028dc2  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x180028dc9  mov     r9d, eax; char *
0x180028dcc  mov     edx, 18Fh; void *
0x180028dd1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
