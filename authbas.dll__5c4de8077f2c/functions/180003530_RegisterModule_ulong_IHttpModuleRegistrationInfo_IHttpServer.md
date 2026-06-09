# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180003530`
- end: `0x1800036e3`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180002820`
- `0x180003530`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003582`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003629`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x1800035ae`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x1800035ae`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003569`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003569`
- `iisutil!PuDbgPrint` at `0x180003672`
- `iisutil!PuDbgPrint` at `0x180003672`
- `CRYPTSP!CryptAcquireContextW` at `0x18000361f`
- `CRYPTSP!CryptAcquireContextW` at `0x18000361f`

## string_xrefs

- `0x18000357b`: `Unable to Create Debug Print Object \n`
- `0x1800035a7`: `System\CurrentControlSet\Services\W3SVC\Parameters\basicauth`
- `0x18000366b`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180003659`: `TOKEN_KEY::Initialize`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  _QWORD *v6; // rax
  __int64 result; // rax
  signed int LastError; // eax
  signed int v9; // ebx
  _QWORD *v10; // rax

  s_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  s_pGlobalInfo = a3;
  DebugPrintsObject = PuCreateDebugPrintsObject("basicauth", 1);
  g_pDebug = DebugPrintsObject;
  if ( !DebugPrintsObject )
  {
    OutputDebugStringA("Unable to Create Debug Print Object \n");
    DebugPrintsObject = g_pDebug;
    if ( !g_pDebug )
      return 2147500037LL;
  }
  if ( !*(_DWORD *)(DebugPrintsObject + 640) )
    return 2147500037LL;
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\basicauth", 0);
  v6 = operator new(0x10u);
  if ( v6 )
  {
    *v6 = &CIISModuleFactory::`vftable';
    v6[1] = &CIISHttpModule::`vftable';
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
               a2,
               v6,
               536870914,
               0);
    if ( (int)result < 0 )
      return result;
    if ( !CryptAcquireContextW(&TOKEN_KEY::sm_hCryptProv, 0, 0, 0x18u, 0xF0000000) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
          982,
          "TOKEN_KEY::Initialize",
          "CryptAcquireContext() failed. hr = 0x%x\n",
          v9);
      if ( v9 < 0 )
        return (unsigned int)v9;
    }
    v10 = operator new(0xA20u);
    if ( v10 )
    {
      s_pBasicAuthProvider = v10;
      *v10 = &BASIC_AUTH_PROVIDER::`vftable';
      *((_WORD *)v10 + 8) = 0;
      *((_WORD *)v10 + 264) = 0;
      v10[322] = 0;
      *((_DWORD *)v10 + 646) = 0;
      return BASIC_AUTH_PROVIDER::InitializeInstance(0);
    }
    s_pBasicAuthProvider = 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180003530  mov     [rsp+arg_0], rbx
0x180003535  push    rdi
0x180003536  sub     rsp, 30h
0x18000353a  mov     rax, [rdx]
0x18000353d  mov     rcx, rdx
0x180003540  mov     rbx, r8
0x180003543  mov     rdi, rdx
0x180003546  mov     rax, [rax+8]
0x18000354a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354f  mov     edx, 1
0x180003554  mov     cs:?s_pModuleContext@@3PEAXEA, rax; void * s_pModuleContext
0x18000355b  lea     rcx, aBasicauth; "basicauth"
0x180003562  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * s_pGlobalInfo
0x180003569  call    cs:__imp_PuCreateDebugPrintsObject
0x18000356f  mov     cs:g_pDebug, rax
0x180003576  test    rax, rax
0x180003579  jnz     short loc_180003598
0x18000357b  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180003582  call    cs:__imp_OutputDebugStringA
0x180003588  mov     rax, cs:g_pDebug
0x18000358f  test    rax, rax
0x180003592  jz      loc_1800036D3
0x180003598  cmp     dword ptr [rax+280h], 0
0x18000359f  jz      loc_1800036D3
0x1800035a5  xor     edx, edx
0x1800035a7  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\W3"...
0x1800035ae  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x1800035b4  mov     ecx, 10h; Size
0x1800035b9  mov     cs:g_dwDebugFlags, eax
0x1800035bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035c4  mov     rdx, rax
0x1800035c7  test    rax, rax
0x1800035ca  jz      loc_1800036CC
0x1800035d0  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800035d7  xor     r9d, r9d
0x1800035da  mov     [rdx], rax
0x1800035dd  mov     r8d, 20000002h
0x1800035e3  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x1800035ea  mov     [rdx+8], rax
0x1800035ee  mov     rcx, [rdi]
0x1800035f1  mov     rax, [rcx+10h]
0x1800035f5  mov     rcx, rdi
0x1800035f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035fd  test    eax, eax
0x1800035ff  js      loc_1800036D8
0x180003605  mov     r9d, 18h; dwProvType
0x18000360b  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x180003613  xor     r8d, r8d; szProvider
0x180003616  lea     rcx, ?sm_hCryptProv@TOKEN_KEY@@0_KA; phProv
0x18000361d  xor     edx, edx; szContainer
0x18000361f  call    cs:__imp_CryptAcquireContextW
0x180003625  test    eax, eax
0x180003627  jnz     short loc_180003680
0x180003629  call    cs:__imp_GetLastError
0x18000362f  mov     ebx, eax
0x180003631  test    eax, eax
0x180003633  jle     short loc_18000363E
0x180003635  movzx   ebx, ax
0x180003638  or      ebx, 80070000h
0x18000363e  test    byte ptr cs:g_dwDebugFlags, 3
0x180003645  jz      short loc_180003678
0x180003647  mov     rcx, cs:g_pDebug
0x18000364e  lea     rax, aCryptacquireco; "CryptAcquireContext() failed. hr = 0x%x"...
0x180003655  mov     [rsp+38h+var_10], ebx
0x180003659  lea     r9, aTokenKeyInitia; "TOKEN_KEY::Initialize"
0x180003660  mov     r8d, 3D6h
0x180003666  mov     qword ptr [rsp+38h+dwFlags], rax
0x18000366b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003672  call    cs:__imp_PuDbgPrint
0x180003678  test    ebx, ebx
0x18000367a  jns     short loc_180003680
0x18000367c  mov     eax, ebx
0x18000367e  jmp     short loc_1800036D8
0x180003680  mov     ecx, 0A20h; Size
0x180003685  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000368a  test    rax, rax
0x18000368d  jz      short loc_1800036C1
0x18000368f  lea     rcx, ??_7BASIC_AUTH_PROVIDER@@6B@; const BASIC_AUTH_PROVIDER::`vftable'
0x180003696  mov     cs:?s_pBasicAuthProvider@@3PEAVBASIC_AUTH_PROVIDER@@EA, rax; BASIC_AUTH_PROVIDER * s_pBasicAuthProvider
0x18000369d  mov     [rax], rcx
0x1800036a0  xor     ecx, ecx; this
0x1800036a2  mov     [rax+10h], cx
0x1800036a6  mov     [rax+210h], cx
0x1800036ad  mov     [rax+0A10h], rcx
0x1800036b4  mov     [rax+0A18h], ecx
0x1800036ba  call    ?InitializeInstance@BASIC_AUTH_PROVIDER@@QEAAJXZ; BASIC_AUTH_PROVIDER::InitializeInstance(void)
0x1800036bf  jmp     short loc_1800036D8
0x1800036c1  mov     cs:?s_pBasicAuthProvider@@3PEAVBASIC_AUTH_PROVIDER@@EA, 0; BASIC_AUTH_PROVIDER * s_pBasicAuthProvider
0x1800036cc  mov     eax, 80070008h
0x1800036d1  jmp     short loc_1800036D8
0x1800036d3  mov     eax, 80004005h
0x1800036d8  mov     rbx, [rsp+38h+arg_0]
0x1800036dd  add     rsp, 30h
0x1800036e1  pop     rdi
0x1800036e2  retn
```
