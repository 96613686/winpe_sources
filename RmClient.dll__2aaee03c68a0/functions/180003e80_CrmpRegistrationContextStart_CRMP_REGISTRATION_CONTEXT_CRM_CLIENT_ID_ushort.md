# CrmpRegistrationContextStart(_CRMP_REGISTRATION_CONTEXT *,_CRM_CLIENT_ID,ushort *)

- ea: `0x180003e80`
- end: `0x18000415a`
- name: `?CrmpRegistrationContextStart@@YAJPEAU_CRMP_REGISTRATION_CONTEXT@@W4_CRM_CLIENT_ID@@PEAG@Z`
- size: `730`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003de0`

## callees

- `0x180003e80`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004012`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000404b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000404b`
- `ntdll!NtQueryInformationProcess` at `0x180004033`
- `ntdll!NtQueryInformationProcess` at `0x180004033`
- `RPCRT4!NdrClientCall3` at `0x18000408e`
- `RPCRT4!NdrClientCall3` at `0x18000408e`
- `RPCRT4!RpcBindingCreateW` at `0x180003fbc`
- `RPCRT4!RpcBindingCreateW` at `0x180003fbc`
- `RPCRT4!RpcBindingBind` at `0x180003fda`
- `RPCRT4!RpcBindingBind` at `0x180003fda`
- `RPCRT4!RpcBindingFree` at `0x1800040d6`
- `RPCRT4!RpcBindingFree` at `0x180004148`
- `RPCRT4!RpcBindingFree` at `0x1800040d6`
- `RPCRT4!RpcBindingFree` at `0x180004148`
- `RPCRT4!RpcExceptionFilter` at `0x18001b0ee`
- `RPCRT4!RpcExceptionFilter` at `0x18001b0ee`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800040a7`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800040a7`

## pseudocode

```c
__int64 __fastcall CrmpRegistrationContextStart(__int64 a1, int a2, __int64 a3)
{
  int v7; // esi
  RPC_STATUS v8; // eax
  int InformationProcess; // ebx
  RPC_STATUS v10; // eax
  HANDLE CurrentProcess; // rax
  LPWSTR FileNameW; // rax
  CLIENT_CALL_RETURN v13; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-368h] BYREF
  int Pointer; // [rsp+58h] [rbp-360h]
  int v17; // [rsp+60h] [rbp-358h]
  RPC_BINDING_HANDLE v18; // [rsp+68h] [rbp-350h] BYREF
  __int64 v19; // [rsp+70h] [rbp-348h] BYREF
  _QWORD v20[3]; // [rsp+78h] [rbp-340h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W v21; // [rsp+90h] [rbp-328h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-300h] BYREF
  int v23; // [rsp+C0h] [rbp-2F8h]
  int v24; // [rsp+C4h] [rbp-2F4h]
  __int128 v25; // [rsp+C8h] [rbp-2F0h]
  __int128 v26; // [rsp+D8h] [rbp-2E0h]
  __int64 v27; // [rsp+E8h] [rbp-2D0h]
  RPC_BINDING_HANDLE_OPTIONS_V1 v28; // [rsp+F0h] [rbp-2C8h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v29; // [rsp+100h] [rbp-2B8h] BYREF
  _BYTE ProcessInformation[8]; // [rsp+140h] [rbp-278h] BYREF
  LPCWSTR pszPath; // [rsp+148h] [rbp-270h]

  v20[1] = a1;
  v17 = a2;
  v18 = 0;
  v19 = 0;
  v20[0] = 0;
  Binding = 0;
  memset(&v29, 0, sizeof(v29));
  *(_QWORD *)&v28.ComTimeout = 5;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  *(_QWORD *)(&v21.Version + 1) = 0;
  HIDWORD(v21.ServerPrincName) = 0;
  v21.AuthIdentity = 0;
  v7 = 1;
  v29.Version = 1;
  v29.ProtocolSequence = 3;
  *(_QWORD *)&v28.Version = 0x100000001LL;
  v22 = 5;
  v23 = 1;
  v24 = 3;
  v21.Version = 1;
  v21.AuthnLevel = 6;
  v21.AuthnSvc = 10;
  v21.SecurityQos = (RPC_SECURITY_QOS *)&v22;
  v8 = RpcBindingCreateW(&v29, &v21, &v28, &Binding);
  InformationProcess = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      InformationProcess = (unsigned __int16)v8 | 0xC0070000;
  }
  else
  {
    v10 = RpcBindingBind(0, Binding, qword_18001D460);
    InformationProcess = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        InformationProcess = (unsigned __int16)v10 | 0xC0070000;
    }
    else
    {
      v18 = Binding;
      Binding = 0;
      InformationProcess = 0;
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( InformationProcess < 0 )
  {
    v7 = 0;
  }
  else
  {
    LODWORD(Binding) = 1;
    CurrentProcess = GetCurrentProcess();
    InformationProcess = NtQueryInformationProcess(
                           CurrentProcess,
                           ProcessImageFileNameWin32,
                           ProcessInformation,
                           0x228u,
                           0);
    if ( InformationProcess >= 0 )
    {
      FileNameW = PathFindFileNameW(pszPath);
      *(_QWORD *)&v28.Version = 0;
      v13.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DC50, 0, 0, v18, &v19, v20, a2, a3, FileNameW).Pointer;
      InformationProcess = (int)v13.Pointer;
      *(CLIENT_CALL_RETURN *)&v28.Version = v13;
      Pointer = (int)v13.Pointer;
      if ( SLODWORD(v13.Simple) >= 0 )
      {
        *(_DWORD *)a1 = a2;
        *(_QWORD *)(a1 + 8) = v19;
        *(_QWORD *)(a1 + 16) = v20[0];
        InformationProcess = 0;
      }
    }
  }
  if ( v7 )
    RpcBindingFree(&v18);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x180003e80  mov     r11, rsp
0x180003e83  push    rbx
0x180003e84  push    rsi
0x180003e85  push    rdi
0x180003e86  push    r12
0x180003e88  push    r13
0x180003e8a  push    r14
0x180003e8c  push    r15
0x180003e8e  sub     rsp, 380h
0x180003e95  mov     rax, cs:__security_cookie
0x180003e9c  xor     rax, rsp
0x180003e9f  mov     [rsp+3B8h+var_48], rax
0x180003ea7  mov     r13, r8
0x180003eaa  mov     r15d, edx
0x180003ead  mov     r12, rcx
0x180003eb0  mov     r14, rcx
0x180003eb3  mov     [rsp+3B8h+var_338], rcx
0x180003ebb  mov     [rsp+3B8h+var_358], edx
0x180003ebf  xor     edi, edi
0x180003ec1  mov     [rsp+3B8h+var_350], rdi
0x180003ec6  mov     [rsp+3B8h+var_348], rdi
0x180003ecb  mov     [rsp+3B8h+var_340], rdi
0x180003ed0  mov     [rsp+3B8h+Binding], rdi
0x180003ed5  xorps   xmm0, xmm0
0x180003ed8  xor     eax, eax
0x180003eda  movups  [rsp+3B8h+var_2B8], xmm0
0x180003ee2  movups  [rsp+3B8h+var_2A8], xmm0
0x180003eea  movups  [rsp+3B8h+var_298], xmm0
0x180003ef2  mov     [r11-288h], rax
0x180003ef9  mov     qword ptr [r11-2C0h], 5
0x180003f04  movdqu  [rsp+3B8h+var_2F0], xmm0
0x180003f0d  xorps   xmm1, xmm1
0x180003f10  movdqu  [rsp+3B8h+var_2E0], xmm1
0x180003f19  mov     [r11-2D0h], rdi
0x180003f20  mov     [r11-324h], rdi
0x180003f27  mov     [rsp+3B8h+var_31C], edi
0x180003f2e  mov     [r11-310h], rdi
0x180003f35  mov     esi, 1
0x180003f3a  mov     dword ptr [rsp+3B8h+var_2B8], esi
0x180003f41  mov     dword ptr [rsp+3B8h+var_2B8+8], 3
0x180003f4c  mov     dword ptr [rsp+3B8h+var_2C8], esi
0x180003f53  mov     dword ptr [rsp+3B8h+var_2C8+4], esi
0x180003f5a  mov     qword ptr [r11-300h], 5
0x180003f65  mov     [rsp+3B8h+var_2F8], esi
0x180003f6c  mov     [rsp+3B8h+var_2F4], 3
0x180003f77  mov     [rsp+3B8h+var_328], esi
0x180003f7e  mov     [rsp+3B8h+var_318], 6
0x180003f89  mov     [rsp+3B8h+var_314], 0Ah
0x180003f94  lea     rax, [r11-300h]
0x180003f9b  mov     [r11-308h], rax
0x180003fa2  lea     r9, [rsp+3B8h+Binding]; Binding
0x180003fa7  lea     r8, [r11-2C8h]; Options
0x180003fae  lea     rdx, [r11-328h]; Security
0x180003fb5  lea     rcx, [r11-2B8h]; Template
0x180003fbc  call    cs:__imp_RpcBindingCreateW
0x180003fc2  mov     ebx, eax
0x180003fc4  test    eax, eax
0x180003fc6  jnz     loc_18000411B
0x180003fcc  lea     r8, qword_18001D460; IfSpec
0x180003fd3  mov     rdx, [rsp+3B8h+Binding]; Binding
0x180003fd8  xor     ecx, ecx; pAsync
0x180003fda  call    cs:__imp_RpcBindingBind
0x180003fe0  mov     ebx, eax
0x180003fe2  test    eax, eax
0x180003fe4  jnz     loc_18000412F
0x180003fea  mov     rax, [rsp+3B8h+Binding]
0x180003fef  mov     [rsp+3B8h+var_350], rax
0x180003ff4  mov     [rsp+3B8h+Binding], rdi
0x180003ff9  mov     ebx, edi
0x180003ffb  cmp     [rsp+3B8h+Binding], rdi
0x180004000  jnz     loc_180004143
0x180004006  test    ebx, ebx
0x180004008  js      loc_180004153
0x18000400e  mov     dword ptr [rsp+3B8h+Binding], esi
0x180004012  call    cs:__imp_GetCurrentProcess
0x180004018  mov     rcx, rax; ProcessHandle
0x18000401b  mov     [rsp+3B8h+ReturnLength], rdi; ReturnLength
0x180004020  mov     r9d, 228h; ProcessInformationLength
0x180004026  lea     r8, [rsp+3B8h+ProcessInformation]; ProcessInformation
0x18000402e  mov     edx, 2Bh ; '+'; ProcessInformationClass
0x180004033  call    cs:__imp_NtQueryInformationProcess
0x180004039  mov     ebx, eax
0x18000403b  test    eax, eax
0x18000403d  js      loc_1800040CD
0x180004043  mov     rcx, [rsp+3B8h+pszPath]; pszPath
0x18000404b  call    cs:__imp_PathFindFileNameW
0x180004051  nop
0x180004052  mov     qword ptr [rsp+3B8h+var_2C8], rdi
0x18000405a  mov     [rsp+3B8h+var_378], rax
0x18000405f  mov     [rsp+3B8h+var_380], r13
0x180004064  mov     [rsp+3B8h+var_388], r15d
0x180004069  lea     rax, [rsp+3B8h+var_340]
0x18000406e  mov     [rsp+3B8h+var_390], rax
0x180004073  lea     rax, [rsp+3B8h+var_348]
0x180004078  mov     [rsp+3B8h+ReturnLength], rax
0x18000407d  mov     r9, [rsp+3B8h+var_350]
0x180004082  xor     r8d, r8d; pReturnValue
0x180004085  xor     edx, edx; nProcNum
0x180004087  lea     rcx, stru_18001DC50; pProxyInfo
0x18000408e  call    cs:__imp_NdrClientCall3
0x180004094  mov     rbx, rax
0x180004097  mov     qword ptr [rsp+3B8h+var_2C8], rax
0x18000409f  mov     [rsp+3B8h+var_360], eax
0x1800040a3  jmp     short loc_1800040C9
0x1800040a5  mov     ecx, eax; Status
0x1800040a7  call    cs:__imp_I_RpcMapWin32Status
0x1800040ad  mov     ebx, eax
0x1800040af  mov     [rsp+3B8h+var_360], eax
0x1800040b3  xor     edi, edi
0x1800040b5  mov     esi, dword ptr [rsp+3B8h+Binding]
0x1800040b9  mov     r14, [rsp+3B8h+var_338]
0x1800040c1  mov     r15d, [rsp+3B8h+var_358]
0x1800040c6  mov     r12, r14
0x1800040c9  test    ebx, ebx
0x1800040cb  jns     short loc_180004101
0x1800040cd  test    esi, esi
0x1800040cf  jz      short loc_1800040DC
0x1800040d1  lea     rcx, [rsp+3B8h+var_350]; Binding
0x1800040d6  call    cs:__imp_RpcBindingFree
0x1800040dc  mov     eax, ebx
0x1800040de  mov     rcx, [rsp+3B8h+var_48]
0x1800040e6  xor     rcx, rsp; StackCookie
0x1800040e9  call    __security_check_cookie
0x1800040ee  add     rsp, 380h
0x1800040f5  pop     r15
0x1800040f7  pop     r14
0x1800040f9  pop     r13
0x1800040fb  pop     r12
0x1800040fd  pop     rdi
0x1800040fe  pop     rsi
0x1800040ff  pop     rbx
0x180004100  retn
0x180004101  mov     [r12], r15d
0x180004105  mov     rax, [rsp+3B8h+var_348]
0x18000410a  mov     [r14+8], rax
0x18000410e  mov     rax, [rsp+3B8h+var_340]
0x180004113  mov     [r14+10h], rax
0x180004117  mov     ebx, edi
0x180004119  jmp     short loc_1800040CD
0x18000411b  jle     loc_180003FFB
0x180004121  movzx   ebx, ax
0x180004124  or      ebx, 0C0070000h
0x18000412a  jmp     loc_180003FFB
0x18000412f  jle     loc_180003FFB
0x180004135  movzx   ebx, ax
0x180004138  or      ebx, 0C0070000h
0x18000413e  jmp     loc_180003FFB
0x180004143  lea     rcx, [rsp+3B8h+Binding]; Binding
0x180004148  call    cs:__imp_RpcBindingFree
0x18000414e  jmp     loc_180004006
0x180004153  mov     esi, edi
0x180004155  jmp     loc_1800040CD
0x18001b0e0  push    rbp
0x18001b0e2  sub     rsp, 50h
0x18001b0e6  mov     rbp, rdx
0x18001b0e9  mov     rcx, [rcx]
0x18001b0ec  mov     ecx, [rcx]; ExceptionCode
0x18001b0ee  call    cs:__imp_RpcExceptionFilter
0x18001b0f4  nop
0x18001b0f5  add     rsp, 50h
0x18001b0f9  pop     rbp
0x18001b0fa  retn
```
