# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002c60`
- end: `0x180002d8f`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180001008`
- `0x180002110`
- `0x180002c60`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cb4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cb4`
- `iisutil!PuCreateDebugPrintsObject` at `0x180002c99`
- `iisutil!PuCreateDebugPrintsObject` at `0x180002c99`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180002cdf`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180002cdf`
- `iisutil!IISGetPlatformType` at `0x180002ceb`
- `iisutil!IISGetPlatformType` at `0x180002ceb`

## string_xrefs

- `0x180002cad`: `Unable to Create Debug Print Object \n`
- `0x180002cd8`: `System\CurrentControlSet\Services\W3SVC\Parameters\Certmap_auth`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  _QWORD *v6; // rax
  __int64 result; // rax
  _QWORD *v8; // rax

  s_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
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
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\Certmap_auth", 0);
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
    v8 = operator new(0x70u);
    if ( v8 )
    {
      s_pCertmapAuthProvider = v8;
      *v8 = &CERTMAP_AUTH_PROVIDER::`vftable';
      v8[2] = 0;
      v8[6] = v8 + 2;
      *((_DWORD *)v8 + 14) = 32;
      *((_WORD *)v8 + 30) = 256;
      return CERTMAP_AUTH_PROVIDER::InitializeInstance((CERTMAP_AUTH_PROVIDER *)(v8 + 2));
    }
    s_pCertmapAuthProvider = 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002c60  mov     [rsp+arg_0], rbx
0x180002c65  push    rdi
0x180002c66  sub     rsp, 30h
0x180002c6a  mov     rax, [rdx]
0x180002c6d  mov     rcx, rdx
0x180002c70  mov     rbx, r8
0x180002c73  mov     rdi, rdx
0x180002c76  mov     rax, [rax+8]
0x180002c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c7f  mov     edx, 1
0x180002c84  mov     cs:?s_pModuleContext@@3PEAXEA, rax; void * s_pModuleContext
0x180002c8b  lea     rcx, aCertmapAuth; "Certmap_auth"
0x180002c92  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * s_pGlobalInfo
0x180002c99  call    cs:__imp_PuCreateDebugPrintsObject
0x180002c9f  xor     ebx, ebx
0x180002ca1  mov     cs:g_pDebug, rax
0x180002ca8  test    rax, rax
0x180002cab  jnz     short loc_180002CCA
0x180002cad  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180002cb4  call    cs:__imp_OutputDebugStringA
0x180002cba  mov     rax, cs:g_pDebug
0x180002cc1  test    rax, rax
0x180002cc4  jz      loc_180002D7F
0x180002cca  cmp     [rax+280h], ebx
0x180002cd0  jz      loc_180002D7F
0x180002cd6  xor     edx, edx
0x180002cd8  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180002cdf  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180002ce5  mov     cs:g_dwDebugFlags, eax
0x180002ceb  call    cs:__imp_IISGetPlatformType
0x180002cf1  mov     ecx, 10h; Size
0x180002cf6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002cfb  mov     rdx, rax
0x180002cfe  test    rax, rax
0x180002d01  jz      short loc_180002D78
0x180002d03  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x180002d0a  xor     r9d, r9d
0x180002d0d  mov     [rdx], rax
0x180002d10  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180002d17  mov     [rdx+8], rax
0x180002d1b  mov     rcx, [rdi]
0x180002d1e  lea     r8d, [r9+2]
0x180002d22  mov     rax, [rcx+10h]
0x180002d26  mov     rcx, rdi
0x180002d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2e  test    eax, eax
0x180002d30  js      short loc_180002D84
0x180002d32  mov     ecx, 70h ; 'p'; Size
0x180002d37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d3c  test    rax, rax
0x180002d3f  jz      short loc_180002D71
0x180002d41  lea     rcx, ??_7CERTMAP_AUTH_PROVIDER@@6B@; const CERTMAP_AUTH_PROVIDER::`vftable'
0x180002d48  mov     cs:?s_pCertmapAuthProvider@@3PEAVCERTMAP_AUTH_PROVIDER@@EA, rax; CERTMAP_AUTH_PROVIDER * s_pCertmapAuthProvider
0x180002d4f  mov     [rax], rcx
0x180002d52  lea     rcx, [rax+10h]; this
0x180002d56  mov     [rcx], rbx
0x180002d59  mov     [rcx+20h], rcx
0x180002d5d  mov     dword ptr [rcx+28h], 20h ; ' '
0x180002d64  mov     word ptr [rcx+2Ch], 100h
0x180002d6a  call    ?InitializeInstance@CERTMAP_AUTH_PROVIDER@@QEAAJXZ; CERTMAP_AUTH_PROVIDER::InitializeInstance(void)
0x180002d6f  jmp     short loc_180002D84
0x180002d71  mov     cs:?s_pCertmapAuthProvider@@3PEAVCERTMAP_AUTH_PROVIDER@@EA, rbx; CERTMAP_AUTH_PROVIDER * s_pCertmapAuthProvider
0x180002d78  mov     eax, 80070008h
0x180002d7d  jmp     short loc_180002D84
0x180002d7f  mov     eax, 80004005h
0x180002d84  mov     rbx, [rsp+38h+arg_0]
0x180002d89  add     rsp, 30h
0x180002d8d  pop     rdi
0x180002d8e  retn
```
