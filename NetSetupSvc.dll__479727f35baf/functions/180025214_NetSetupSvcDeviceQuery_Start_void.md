# NetSetupSvcDeviceQuery::Start(void)

- ea: `0x180025214`
- end: `0x1800253b9`
- name: `?Start@NetSetupSvcDeviceQuery@@QEAAXXZ`
- size: `421`
- prototype: `void __fastcall(NetSetupSvcDeviceQuery *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x180025214`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18002533e`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18002533e`

## pseudocode

```c
void __fastcall NetSetupSvcDeviceQuery::Start(NetSetupSvcDeviceQuery *this)
{
  int ObjectQuery; // ebx
  _BYTE pExceptionObject[208]; // [rsp+50h] [rbp-B0h] BYREF
  int v3; // [rsp+120h] [rbp+20h]
  __int128 v4; // [rsp+128h] [rbp+28h]
  __int128 v5; // [rsp+138h] [rbp+38h]
  __int128 v6; // [rsp+148h] [rbp+48h]
  int v7; // [rsp+158h] [rbp+58h]
  DEVPROPKEY v8; // [rsp+160h] [rbp+60h]
  int v9; // [rsp+174h] [rbp+74h]
  __int64 v10; // [rsp+178h] [rbp+78h]
  int v11; // [rsp+180h] [rbp+80h]
  int v12; // [rsp+184h] [rbp+84h]
  GUID *v13; // [rsp+188h] [rbp+88h]
  int v14; // [rsp+190h] [rbp+90h]
  DEVPROPKEY v15; // [rsp+198h] [rbp+98h]
  int v16; // [rsp+1ACh] [rbp+ACh]
  __int64 v17; // [rsp+1B0h] [rbp+B0h]
  int v18; // [rsp+1B8h] [rbp+B8h]
  int v19; // [rsp+1BCh] [rbp+BCh]
  GUID *v20; // [rsp+1C0h] [rbp+C0h]
  int v21; // [rsp+1C8h] [rbp+C8h]
  __int128 v22; // [rsp+1D0h] [rbp+D0h]
  __int128 v23; // [rsp+1E0h] [rbp+E0h]
  __int128 v24; // [rsp+1F0h] [rbp+F0h]

  v8 = DEVPKEY_Device_ClassGuid;
  v15 = DEVPKEY_Device_ClassGuid;
  v4 = 0;
  v20 = &GUID_DEVCLASS_INFRARED;
  v5 = 0;
  v11 = 13;
  v6 = 0;
  v18 = 13;
  v13 = &GUID_DEVCLASS_NET;
  v12 = 16;
  v19 = 16;
  v3 = 3145728;
  v7 = 2;
  v9 = 0;
  v10 = 0;
  v14 = 2;
  v16 = 0;
  v17 = 0;
  v21 = 0x400000;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  ObjectQuery = DevCreateObjectQuery(3, 1, 0);
  if ( ObjectQuery < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_0900590468cd31afd3734c218aa47d65_Traceguids,
        (unsigned int)ObjectQuery);
    HResultException::HResultException((HResultException *)pExceptionObject, ObjectQuery);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180025214  mov     [rsp-8+arg_8], rbx
0x180025219  push    rbp
0x18002521a  lea     rbp, [rsp-110h]
0x180025222  sub     rsp, 210h
0x180025229  mov     rax, cs:__security_cookie
0x180025230  xor     rax, rsp
0x180025233  mov     [rbp+110h+var_10], rax
0x18002523a  mov     eax, cs:DEVPKEY_Device_ClassGuid.pid
0x180025240  lea     rdx, GUID_DEVCLASS_NET
0x180025247  xorps   xmm0, xmm0
0x18002524a  mov     [rsp+210h+var_1D0], rcx
0x18002524f  mov     [rsp+210h+var_1D8], rcx
0x180025254  mov     r9d, 0Dh
0x18002525a  mov     [rbp+110h+var_A0], eax
0x18002525d  mov     [rbp+110h+var_68], eax
0x180025263  lea     rax, GUID_DEVCLASS_INFRARED
0x18002526a  movups  [rbp+110h+var_E8], xmm0
0x18002526e  lea     r8d, [r9+3]
0x180025272  mov     [rbp+110h+var_50], rax
0x180025279  movups  [rbp+110h+var_D8], xmm0
0x18002527d  mov     [rbp+110h+var_90], r9d
0x180025284  lea     rax, ?QueryCallbackThunk@NetSetupSvcDeviceQuery@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; NetSetupSvcDeviceQuery::QueryCallbackThunk(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18002528b  mov     [rsp+210h+var_1E0], rax
0x180025290  lea     rax, [rbp+110h+var_F0]
0x180025294  movups  [rbp+110h+var_C8], xmm0
0x180025298  mov     [rbp+110h+var_58], r9d
0x18002529f  xor     r9d, r9d
0x1800252a2  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ClassGuid.fmtid.Data1
0x1800252a9  mov     [rbp+110h+var_88], rdx
0x1800252b0  mov     [rbp+110h+var_8C], r8d
0x1800252b7  lea     edx, [r9+1]
0x1800252bb  movaps  [rbp+110h+var_B0], xmm0
0x1800252bf  movups  [rbp+110h+var_78], xmm0
0x1800252c6  mov     [rbp+110h+var_54], r8d
0x1800252cd  lea     ecx, [rdx+2]
0x1800252d0  xorps   xmm0, xmm0
0x1800252d3  mov     [rsp+210h+var_1E8], rax
0x1800252d8  xor     r8d, r8d
0x1800252db  mov     [rbp+110h+var_F0], 300000h
0x1800252e2  mov     [rbp+110h+var_B8], 2
0x1800252e9  mov     [rbp+110h+var_9C], 0
0x1800252f0  mov     [rbp+110h+var_98], 0
0x1800252f8  mov     [rbp+110h+var_80], 2
0x180025302  mov     [rbp+110h+var_64], 0
0x18002530c  mov     [rbp+110h+var_60], 0
0x180025317  mov     [rbp+110h+var_48], 400000h
0x180025321  movups  [rbp+110h+var_40], xmm0
0x180025328  mov     [rsp+210h+var_1F0], 4
0x180025330  movups  [rbp+110h+var_30], xmm0
0x180025337  movups  [rbp+110h+var_20], xmm0
0x18002533e  call    cs:__imp_DevCreateObjectQuery
0x180025344  mov     ebx, eax
0x180025346  test    eax, eax
0x180025348  jns     short loc_180025399
0x18002534a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025351  lea     rax, WPP_GLOBAL_Control
0x180025358  cmp     rcx, rax
0x18002535b  jz      short loc_18002537B
0x18002535d  cmp     byte ptr [rcx+19h], 2
0x180025361  jb      short loc_18002537B
0x180025363  mov     rcx, [rcx+10h]
0x180025367  lea     r8, WPP_0900590468cd31afd3734c218aa47d65_Traceguids
0x18002536e  mov     edx, 0Ah
0x180025373  mov     r9d, ebx
0x180025376  call    WPP_SF_d
0x18002537b  mov     edx, ebx; int
0x18002537d  lea     rcx, [rsp+210h+pExceptionObject]; this
0x180025382  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180025387  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002538e  lea     rcx, [rsp+210h+pExceptionObject]; pExceptionObject
0x180025393  call    _CxxThrowException_0
0x180025399  mov     rcx, [rbp+110h+var_10]
0x1800253a0  xor     rcx, rsp; StackCookie
0x1800253a3  call    __security_check_cookie
0x1800253a8  mov     rbx, [rsp+210h+arg_8]
0x1800253b0  add     rsp, 210h
0x1800253b7  pop     rbp
0x1800253b8  retn
```
