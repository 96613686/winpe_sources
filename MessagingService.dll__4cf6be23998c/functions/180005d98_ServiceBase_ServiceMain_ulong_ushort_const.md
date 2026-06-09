# ServiceBase::ServiceMain(ulong,ushort const * *)

- ea: `0x180005d98`
- end: `0x180005fe0`
- name: `?ServiceMain@ServiceBase@@QEAAJKPEAPEBG@Z`
- size: `584`
- prototype: `__int64 __fastcall(ServiceBase *this, __int64, WCHAR **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002f50`

## callees

- `0x180005d98`
- `0x180005fe8`
- `0x1800062dc`
- `0x180006764`
- `0x18000aa27`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e4d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005ea9`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005ea9`

## pseudocode

```c
__int64 __fastcall ServiceBase::ServiceMain(ServiceBase *this, __int64 a2, WCHAR **a3)
{
  WCHAR *v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rdx
  WCHAR *v7; // rax
  WCHAR *v8; // rcx
  __int64 v9; // rbx
  ServiceBase *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // edi
  __int64 v18; // rcx
  int v20; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v21[16]; // [rsp+38h] [rbp-40h] BYREF
  WCHAR *v22; // [rsp+48h] [rbp-30h]
  __int64 v23; // [rsp+50h] [rbp-28h]
  WCHAR *v24; // [rsp+58h] [rbp-20h]
  int v25; // [rsp+60h] [rbp-18h]
  int v26; // [rsp+64h] [rbp-14h]

  dword_180013104 = 0;
  dword_180013100 = (*(__int64 (__fastcall **)(void *))(off_1800130A0 + 56LL))(&off_1800130A0);
  dword_180013118 = (*(__int64 (__fastcall **)(void *))(off_1800130A0 + 72LL))(&off_1800130A0);
  dword_18001310C = 0;
  dword_180013114 = 0;
  dword_180013110 = (*(__int64 (__fastcall **)(void *))(off_1800130A0 + 80LL))(&off_1800130A0);
  dword_180013108 = 0;
  memset_0(&ServiceName, 0, 0x40u);
  qword_18001311C = 0;
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v4 = *a3;
  v5 = 2147483646;
  v6 = 32;
  v7 = &ServiceName;
  do
  {
    if ( !v5 )
      break;
    if ( !*v4 )
      break;
    *v7++ = *v4++;
    --v5;
    --v6;
  }
  while ( v6 );
  v8 = v7 - 1;
  if ( v6 )
    v8 = v7;
  *v8 = 0;
  v9 = -1;
  qword_1800130E8 = (__int64)RegisterServiceCtrlHandlerExW(
                               &ServiceName,
                               ServiceBase::_ServiceCtrlHandler,
                               &off_1800130A0);
  if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 8) != 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(&ServiceName + v12) );
    v22 = &ServiceName;
    v23 = (unsigned int)(2 * v12 + 2);
    McGenEventWrite_EventWriteTransfer(v10, ServiceBaseServiceStarting, v11, 2, v21);
  }
  v13 = ServiceBase::_ServiceMainInner(v10);
  v17 = v13;
  if ( v13 >= 0 )
  {
    if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x10) != 0 )
    {
      do
        ++v9;
      while ( *(&ServiceName + v9) );
      v22 = &ServiceName;
      v23 = (unsigned int)(2 * v9 + 2);
      McGenEventWrite_EventWriteTransfer(v15, ServiceBaseServiceStarted, v16, 2, v21);
    }
    return 0;
  }
  else
  {
    v18 = v13 & 0x1FFF0000;
    if ( (_DWORD)v18 == 458752 )
    {
      dword_18001310C = (unsigned __int16)v13;
    }
    else
    {
      if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 1) != 0 )
      {
        v20 = v13;
        v22 = (WCHAR *)&v20;
        v23 = 4;
        do
          ++v9;
        while ( *(&ServiceName + v9) );
        v24 = &ServiceName;
        v25 = 2 * v9 + 2;
        v26 = 0;
        McGenEventWrite_EventWriteTransfer(v18, ServiceBaseErrorEvent, v16, 3, v21);
      }
      dword_18001310C = v17;
    }
    ServiceBase::ServiceStop((ServiceBase *)&off_1800130A0, v14, v16);
    return v17;
  }
}

```

## disassembly

```asm
0x180005d98  push    rbp
0x180005d9a  push    rbx
0x180005d9b  push    rsi
0x180005d9c  push    rdi
0x180005d9d  push    r14
0x180005d9f  push    r15
0x180005da1  mov     rbp, rsp
0x180005da4  sub     rsp, 78h
0x180005da8  mov     rax, cs:__security_cookie
0x180005daf  xor     rax, rsp
0x180005db2  mov     [rbp+var_10], rax
0x180005db6  mov     rax, cs:off_1800130A0
0x180005dbd  lea     r15, off_1800130A0
0x180005dc4  xor     esi, esi
0x180005dc6  mov     rcx, r15
0x180005dc9  mov     rbx, r8
0x180005dcc  mov     cs:dword_180013104, esi
0x180005dd2  mov     rax, [rax+38h]
0x180005dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ddb  mov     cs:dword_180013100, eax
0x180005de1  mov     rcx, r15
0x180005de4  mov     rax, cs:off_1800130A0
0x180005deb  mov     rax, [rax+48h]
0x180005def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df4  mov     cs:dword_180013118, eax
0x180005dfa  mov     rcx, r15
0x180005dfd  mov     rax, cs:off_1800130A0
0x180005e04  mov     cs:dword_18001310C, esi
0x180005e0a  mov     cs:dword_180013114, esi
0x180005e10  mov     rax, [rax+50h]
0x180005e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e19  lea     r14, ServiceName
0x180005e20  mov     cs:dword_180013110, eax
0x180005e26  mov     rcx, r14; void *
0x180005e29  mov     cs:dword_180013108, esi
0x180005e2f  xor     edx, edx; Val
0x180005e31  lea     r8d, [rsi+40h]; Size
0x180005e35  call    memset_0
0x180005e3a  mov     rcx, cs:hObject; hObject
0x180005e41  mov     cs:qword_18001311C, rsi
0x180005e48  test    rcx, rcx
0x180005e4b  jz      short loc_180005E5A
0x180005e4d  call    cs:__imp_CloseHandle
0x180005e53  mov     cs:hObject, rsi
0x180005e5a  mov     r8, [rbx]
0x180005e5d  mov     ecx, 7FFFFFFEh
0x180005e62  mov     edx, 20h ; ' '
0x180005e67  mov     rax, r14
0x180005e6a  test    rcx, rcx
0x180005e6d  jz      short loc_180005E8E
0x180005e6f  movzx   r9d, word ptr [r8]
0x180005e73  test    r9w, r9w
0x180005e77  jz      short loc_180005E8E
0x180005e79  mov     [rax], r9w
0x180005e7d  add     r8, 2
0x180005e81  add     rax, 2
0x180005e85  dec     rcx
0x180005e88  sub     rdx, 1
0x180005e8c  jnz     short loc_180005E6A
0x180005e8e  test    rdx, rdx
0x180005e91  lea     rcx, [rax-2]
0x180005e95  mov     r8, r15; lpContext
0x180005e98  lea     rdx, ?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z; lpHandlerProc
0x180005e9f  cmovnz  rcx, rax
0x180005ea3  mov     [rcx], si
0x180005ea6  mov     rcx, r14; lpServiceName
0x180005ea9  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005eaf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005eb3  mov     cs:qword_1800130E8, rax
0x180005eba  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 8
0x180005ec1  jz      short loc_180005EFC
0x180005ec3  mov     rax, rbx
0x180005ec6  inc     rax
0x180005ec9  cmp     [r14+rax*2], si
0x180005ece  jnz     short loc_180005EC6
0x180005ed0  lea     eax, ds:2[rax*2]
0x180005ed7  mov     [rbp+var_30], r14
0x180005edb  mov     dword ptr [rbp+var_28], eax
0x180005ede  lea     rdx, ServiceBaseServiceStarting
0x180005ee5  lea     rax, [rbp+var_40]
0x180005ee9  mov     dword ptr [rbp+var_28+4], esi
0x180005eec  mov     r9d, 2
0x180005ef2  mov     [rsp+78h+var_58], rax
0x180005ef7  call    McGenEventWrite_EventWriteTransfer
0x180005efc  call    ?_ServiceMainInner@ServiceBase@@AEAAJXZ; ServiceBase::_ServiceMainInner(void)
0x180005f01  mov     edi, eax
0x180005f03  test    eax, eax
0x180005f05  jns     short loc_180005F86
0x180005f07  mov     ecx, eax
0x180005f09  and     ecx, 1FFF0000h
0x180005f0f  cmp     ecx, 70000h
0x180005f15  jnz     short loc_180005F22
0x180005f17  movzx   ecx, di
0x180005f1a  mov     cs:dword_18001310C, ecx
0x180005f20  jmp     short loc_180005F7A
0x180005f22  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 1
0x180005f29  jz      short loc_180005F74
0x180005f2b  lea     rax, [rbp+var_48]
0x180005f2f  mov     [rbp+var_48], edi
0x180005f32  mov     [rbp+var_30], rax
0x180005f36  mov     [rbp+var_28], 4
0x180005f3e  inc     rbx
0x180005f41  cmp     [r14+rbx*2], si
0x180005f46  jnz     short loc_180005F3E
0x180005f48  lea     eax, ds:2[rbx*2]
0x180005f4f  mov     [rbp+var_20], r14
0x180005f53  mov     [rbp+var_18], eax
0x180005f56  lea     rdx, ServiceBaseErrorEvent
0x180005f5d  lea     rax, [rbp+var_40]
0x180005f61  mov     [rbp+var_14], esi
0x180005f64  mov     r9d, 3
0x180005f6a  mov     [rsp+78h+var_58], rax
0x180005f6f  call    McGenEventWrite_EventWriteTransfer
0x180005f74  mov     cs:dword_18001310C, edi
0x180005f7a  mov     rcx, r15; this
0x180005f7d  call    ?ServiceStop@ServiceBase@@QEAAXXZ; ServiceBase::ServiceStop(void)
0x180005f82  mov     eax, edi
0x180005f84  jmp     short loc_180005FC7
0x180005f86  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 10h
0x180005f8d  jz      short loc_180005FC5
0x180005f8f  inc     rbx
0x180005f92  cmp     [r14+rbx*2], si
0x180005f97  jnz     short loc_180005F8F
0x180005f99  lea     eax, ds:2[rbx*2]
0x180005fa0  mov     [rbp+var_30], r14
0x180005fa4  mov     dword ptr [rbp+var_28], eax
0x180005fa7  lea     rdx, ServiceBaseServiceStarted
0x180005fae  lea     rax, [rbp+var_40]
0x180005fb2  mov     dword ptr [rbp+var_28+4], esi
0x180005fb5  mov     r9d, 2
0x180005fbb  mov     [rsp+78h+var_58], rax
0x180005fc0  call    McGenEventWrite_EventWriteTransfer
0x180005fc5  xor     eax, eax
0x180005fc7  mov     rcx, [rbp+var_10]
0x180005fcb  xor     rcx, rsp; StackCookie
0x180005fce  call    __security_check_cookie
0x180005fd3  add     rsp, 78h
0x180005fd7  pop     r15
0x180005fd9  pop     r14
0x180005fdb  pop     rdi
0x180005fdc  pop     rsi
0x180005fdd  pop     rbx
0x180005fde  pop     rbp
0x180005fdf  retn
```
