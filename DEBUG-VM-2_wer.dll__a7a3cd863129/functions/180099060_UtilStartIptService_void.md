# UtilStartIptService(void)

- ea: `0x180099060`
- end: `0x1800991c5`
- name: `?UtilStartIptService@@YA_NXZ`
- size: `357`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18008eb2c`

## callees

- `0x18001fe24`
- `0x180099060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800990a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009914c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800990a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009914c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099179`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800990e2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800990e2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180099140`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180099140`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800991a1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800991aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800991a1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800991aa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180099079`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180099079`

## pseudocode

```c
bool UtilStartIptService(void)
{
  BOOL started; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  DWORD v3; // eax
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  DWORD v6; // eax
  DWORD LastError; // eax

  started = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v4 = OpenServiceW(v1, L"Ipt", 0x10u);
    v5 = v4;
    if ( v4 )
    {
      started = StartServiceW(v4, 0, 0);
      if ( !started )
      {
        if ( GetLastError() == 1056 )
        {
          started = 1;
        }
        else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, LastError);
        }
      }
      CloseServiceHandle(v5);
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
    }
    CloseServiceHandle(v2);
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v3 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v3);
  }
  return started;
}

```

## disassembly

```asm
0x180099060  mov     [rsp+arg_0], rbx
0x180099065  mov     [rsp+arg_8], rsi
0x18009906a  push    rdi
0x18009906b  sub     rsp, 20h
0x18009906f  xor     ebx, ebx
0x180099071  xor     edx, edx; lpDatabaseName
0x180099073  xor     ecx, ecx; lpMachineName
0x180099075  lea     r8d, [rbx+1]; dwDesiredAccess
0x180099079  call    cs:__imp_OpenSCManagerW
0x18009907f  mov     rsi, rax
0x180099082  test    rax, rax
0x180099085  jnz     short loc_1800990D2
0x180099087  mov     rcx, cs:WPP_GLOBAL_Control
0x18009908e  lea     rax, WPP_GLOBAL_Control
0x180099095  cmp     rcx, rax
0x180099098  jz      loc_1800991B0
0x18009909e  test    byte ptr [rcx+1Ch], 1
0x1800990a2  jz      loc_1800991B0
0x1800990a8  call    cs:__imp_GetLastError
0x1800990ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800990b5  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800990bc  mov     edx, 0ABh
0x1800990c1  mov     r9d, eax
0x1800990c4  mov     rcx, [rcx+10h]
0x1800990c8  call    WPP_SF_d
0x1800990cd  jmp     loc_1800991B0
0x1800990d2  mov     r8d, 10h; dwDesiredAccess
0x1800990d8  lea     rdx, aIpt_0; "Ipt"
0x1800990df  mov     rcx, rsi; hSCManager
0x1800990e2  call    cs:__imp_OpenServiceW
0x1800990e8  mov     rdi, rax
0x1800990eb  test    rax, rax
0x1800990ee  jnz     short loc_180099138
0x1800990f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800990f7  lea     rax, WPP_GLOBAL_Control
0x1800990fe  cmp     rcx, rax
0x180099101  jz      loc_1800991A7
0x180099107  test    byte ptr [rcx+1Ch], 4
0x18009910b  jz      loc_1800991A7
0x180099111  call    cs:__imp_GetLastError
0x180099117  mov     rcx, cs:WPP_GLOBAL_Control
0x18009911e  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180099125  mov     edx, 0ACh
0x18009912a  mov     r9d, eax
0x18009912d  mov     rcx, [rcx+10h]
0x180099131  call    WPP_SF_d
0x180099136  jmp     short loc_1800991A7
0x180099138  xor     r8d, r8d; lpServiceArgVectors
0x18009913b  xor     edx, edx; dwNumServiceArgs
0x18009913d  mov     rcx, rdi; hService
0x180099140  call    cs:__imp_StartServiceW
0x180099146  mov     ebx, eax
0x180099148  test    eax, eax
0x18009914a  jnz     short loc_18009919E
0x18009914c  call    cs:__imp_GetLastError
0x180099152  cmp     eax, 420h
0x180099157  jnz     short loc_180099160
0x180099159  mov     ebx, 1
0x18009915e  jmp     short loc_18009919E
0x180099160  mov     rcx, cs:WPP_GLOBAL_Control
0x180099167  lea     rax, WPP_GLOBAL_Control
0x18009916e  cmp     rcx, rax
0x180099171  jz      short loc_18009919E
0x180099173  test    byte ptr [rcx+1Ch], 4
0x180099177  jz      short loc_18009919E
0x180099179  call    cs:__imp_GetLastError
0x18009917f  mov     rcx, cs:WPP_GLOBAL_Control
0x180099186  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009918d  mov     edx, 0ADh
0x180099192  mov     r9d, eax
0x180099195  mov     rcx, [rcx+10h]
0x180099199  call    WPP_SF_d
0x18009919e  mov     rcx, rdi; hSCObject
0x1800991a1  call    cs:__imp_CloseServiceHandle
0x1800991a7  mov     rcx, rsi; hSCObject
0x1800991aa  call    cs:__imp_CloseServiceHandle
0x1800991b0  mov     rsi, [rsp+28h+arg_8]
0x1800991b5  test    ebx, ebx
0x1800991b7  mov     rbx, [rsp+28h+arg_0]
0x1800991bc  setnz   al
0x1800991bf  add     rsp, 20h
0x1800991c3  pop     rdi
0x1800991c4  retn
```
