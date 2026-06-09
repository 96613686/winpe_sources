# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002f90`
- end: `0x180003147`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180002480`
- `0x180002f90`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002fe2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000308d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000308d`
- `iisutil!PuDbgPrint` at `0x1800030d6`
- `iisutil!PuDbgPrint` at `0x1800030d6`
- `iisutil!IISGetPlatformType` at `0x18000301a`
- `iisutil!IISGetPlatformType` at `0x18000301a`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000300e`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000300e`
- `iisutil!PuCreateDebugPrintsObject` at `0x180002fc9`
- `iisutil!PuCreateDebugPrintsObject` at `0x180002fc9`
- `CRYPTSP!CryptAcquireContextW` at `0x180003083`
- `CRYPTSP!CryptAcquireContextW` at `0x180003083`

## string_xrefs

- `0x180002fdb`: `Unable to Create Debug Print Object \n`
- `0x180003007`: `System\CurrentControlSet\Services\W3SVC\Parameters\IISCertmap_auth`
- `0x1800030cf`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800030bd`: `TOKEN_KEY::Initialize`

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

  qword_18000D800 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  s_pGlobalInfo = a3;
  DebugPrintsObject = PuCreateDebugPrintsObject("Certmap_auth", 1);
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
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr(
                     "System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\IISCertmap_auth",
                     0);
  IISGetPlatformType();
  v6 = operator new(0x10u);
  if ( v6 )
  {
    *v6 = &CIISModuleFactory::`vftable';
    v6[1] = &CIISHttpModule::`vftable';
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 16LL))(
               a2,
               v6,
               2);
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
      s_pIisCertmapAuthProvider = v10;
      *v10 = &IISCERTMAP_AUTH_PROVIDER::`vftable';
      *((_WORD *)v10 + 8) = 0;
      *((_WORD *)v10 + 264) = 0;
      v10[322] = 0;
      *((_DWORD *)v10 + 646) = 0;
      return IISCERTMAP_AUTH_PROVIDER::InitializeInstance(0);
    }
    s_pIisCertmapAuthProvider = 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002f90  mov     [rsp+arg_0], rbx
0x180002f95  push    rdi
0x180002f96  sub     rsp, 30h
0x180002f9a  mov     rax, [rdx]
0x180002f9d  mov     rcx, rdx
0x180002fa0  mov     rbx, r8
0x180002fa3  mov     rdi, rdx
0x180002fa6  mov     rax, [rax+8]
0x180002faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002faf  mov     edx, 1
0x180002fb4  mov     cs:qword_18000D800, rax
0x180002fbb  lea     rcx, aCertmapAuth; "Certmap_auth"
0x180002fc2  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * s_pGlobalInfo
0x180002fc9  call    cs:__imp_PuCreateDebugPrintsObject
0x180002fcf  mov     cs:g_pDebug, rax
0x180002fd6  test    rax, rax
0x180002fd9  jnz     short loc_180002FF8
0x180002fdb  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180002fe2  call    cs:__imp_OutputDebugStringA
0x180002fe8  mov     rax, cs:g_pDebug
0x180002fef  test    rax, rax
0x180002ff2  jz      loc_180003137
0x180002ff8  cmp     dword ptr [rax+280h], 0
0x180002fff  jz      loc_180003137
0x180003005  xor     edx, edx
0x180003007  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\W3"...
0x18000300e  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180003014  mov     cs:g_dwDebugFlags, eax
0x18000301a  call    cs:__imp_IISGetPlatformType
0x180003020  mov     ecx, 10h; Size
0x180003025  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000302a  mov     rdx, rax
0x18000302d  test    rax, rax
0x180003030  jz      loc_180003130
0x180003036  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x18000303d  xor     r9d, r9d
0x180003040  mov     [rdx], rax
0x180003043  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x18000304a  mov     [rdx+8], rax
0x18000304e  mov     rcx, [rdi]
0x180003051  lea     r8d, [r9+2]
0x180003055  mov     rax, [rcx+10h]
0x180003059  mov     rcx, rdi
0x18000305c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003061  test    eax, eax
0x180003063  js      loc_18000313C
0x180003069  mov     r9d, 18h; dwProvType
0x18000306f  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x180003077  xor     r8d, r8d; szProvider
0x18000307a  lea     rcx, ?sm_hCryptProv@TOKEN_KEY@@0_KA; phProv
0x180003081  xor     edx, edx; szContainer
0x180003083  call    cs:__imp_CryptAcquireContextW
0x180003089  test    eax, eax
0x18000308b  jnz     short loc_1800030E4
0x18000308d  call    cs:__imp_GetLastError
0x180003093  mov     ebx, eax
0x180003095  test    eax, eax
0x180003097  jle     short loc_1800030A2
0x180003099  movzx   ebx, ax
0x18000309c  or      ebx, 80070000h
0x1800030a2  test    byte ptr cs:g_dwDebugFlags, 3
0x1800030a9  jz      short loc_1800030DC
0x1800030ab  mov     rcx, cs:g_pDebug
0x1800030b2  lea     rax, aCryptacquireco; "CryptAcquireContext() failed. hr = 0x%x"...
0x1800030b9  mov     [rsp+38h+var_10], ebx
0x1800030bd  lea     r9, aTokenKeyInitia; "TOKEN_KEY::Initialize"
0x1800030c4  mov     r8d, 3D6h
0x1800030ca  mov     qword ptr [rsp+38h+dwFlags], rax
0x1800030cf  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800030d6  call    cs:__imp_PuDbgPrint
0x1800030dc  test    ebx, ebx
0x1800030de  jns     short loc_1800030E4
0x1800030e0  mov     eax, ebx
0x1800030e2  jmp     short loc_18000313C
0x1800030e4  mov     ecx, 0A20h; Size
0x1800030e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800030ee  test    rax, rax
0x1800030f1  jz      short loc_180003125
0x1800030f3  lea     rcx, ??_7IISCERTMAP_AUTH_PROVIDER@@6B@; const IISCERTMAP_AUTH_PROVIDER::`vftable'
0x1800030fa  mov     cs:?s_pIisCertmapAuthProvider@@3PEAVIISCERTMAP_AUTH_PROVIDER@@EA, rax; IISCERTMAP_AUTH_PROVIDER * s_pIisCertmapAuthProvider
0x180003101  mov     [rax], rcx
0x180003104  xor     ecx, ecx; this
0x180003106  mov     [rax+10h], cx
0x18000310a  mov     [rax+210h], cx
0x180003111  mov     [rax+0A10h], rcx
0x180003118  mov     [rax+0A18h], ecx
0x18000311e  call    ?InitializeInstance@IISCERTMAP_AUTH_PROVIDER@@QEAAJXZ; IISCERTMAP_AUTH_PROVIDER::InitializeInstance(void)
0x180003123  jmp     short loc_18000313C
0x180003125  mov     cs:?s_pIisCertmapAuthProvider@@3PEAVIISCERTMAP_AUTH_PROVIDER@@EA, 0; IISCERTMAP_AUTH_PROVIDER * s_pIisCertmapAuthProvider
0x180003130  mov     eax, 80070008h
0x180003135  jmp     short loc_18000313C
0x180003137  mov     eax, 80004005h
0x18000313c  mov     rbx, [rsp+38h+arg_0]
0x180003141  add     rsp, 30h
0x180003145  pop     rdi
0x180003146  retn
```
