# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180003f30`
- end: `0x18000409d`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180002978`
- `0x1800034c0`
- `0x180003f30`
- `0x180005680`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f84`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f84`
- `iisutil!IISGetPlatformType` at `0x180003fbb`
- `iisutil!IISGetPlatformType` at `0x180003fbb`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180003faf`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180003faf`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003f69`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003f69`

## string_xrefs

- `0x180003f7d`: `Unable to Create Debug Print Object \n`
- `0x180003fa8`: `System\CurrentControlSet\Services\W3SVC\Parameters\anon_auth`

## pseudocode

```c
signed int __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  _QWORD *v6; // rax
  signed int result; // eax
  _QWORD *v8; // rax

  s_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  s_pGlobalInfo = a3;
  DebugPrintsObject = PuCreateDebugPrintsObject("anon_auth", 1);
  g_pDebug = DebugPrintsObject;
  if ( !DebugPrintsObject )
  {
    OutputDebugStringA("Unable to Create Debug Print Object \n");
    DebugPrintsObject = g_pDebug;
    if ( !g_pDebug )
      return -2147467259;
  }
  if ( !*(_DWORD *)(DebugPrintsObject + 640) )
    return -2147467259;
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\anon_auth", 0);
  IISGetPlatformType();
  v6 = operator new(0x10u);
  if ( !v6 )
    return -2147024888;
  *v6 = &CIISModuleFactory::`vftable';
  v6[1] = &CIISHttpModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 16LL))(
             a2,
             v6,
             2);
  if ( result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, __int64, const wchar_t *))(*(_QWORD *)a2 + 32LL))(
               a2,
               2,
               L"LOW");
    if ( result >= 0 )
    {
      result = TOKEN_KEY::Initialize();
      if ( result >= 0 )
      {
        v8 = operator new(0xA78u);
        if ( v8 )
        {
          s_pAnonAuthProvider = v8;
          *v8 = &ANON_AUTH_PROVIDER::`vftable';
          *((_WORD *)v8 + 8) = 0;
          *((_WORD *)v8 + 264) = 0;
          v8[322] = 0;
          *((_DWORD *)v8 + 646) = 0;
          v8[324] = 0;
          v8[325] = 0;
          return ANON_AUTH_PROVIDER::InitializeInstance((ANON_AUTH_PROVIDER *)&ANON_AUTH_PROVIDER::`vftable');
        }
        s_pAnonAuthProvider = 0;
        return -2147024888;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003f30  mov     [rsp+arg_0], rbx
0x180003f35  push    rdi
0x180003f36  sub     rsp, 30h
0x180003f3a  mov     rax, [rdx]
0x180003f3d  mov     rcx, rdx
0x180003f40  mov     rbx, r8
0x180003f43  mov     rdi, rdx
0x180003f46  mov     rax, [rax+8]
0x180003f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f4f  mov     edx, 1
0x180003f54  mov     cs:?s_pModuleContext@@3PEAXEA, rax; void * s_pModuleContext
0x180003f5b  lea     rcx, aAnonAuth; "anon_auth"
0x180003f62  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * s_pGlobalInfo
0x180003f69  call    cs:__imp_PuCreateDebugPrintsObject
0x180003f6f  xor     ebx, ebx
0x180003f71  mov     cs:g_pDebug, rax
0x180003f78  test    rax, rax
0x180003f7b  jnz     short loc_180003F9A
0x180003f7d  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180003f84  call    cs:__imp_OutputDebugStringA
0x180003f8a  mov     rax, cs:g_pDebug
0x180003f91  test    rax, rax
0x180003f94  jz      loc_18000408D
0x180003f9a  cmp     [rax+280h], ebx
0x180003fa0  jz      loc_18000408D
0x180003fa6  xor     edx, edx
0x180003fa8  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\W3"...
0x180003faf  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180003fb5  mov     cs:g_dwDebugFlags, eax
0x180003fbb  call    cs:__imp_IISGetPlatformType
0x180003fc1  mov     ecx, 10h; Size
0x180003fc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fcb  mov     rdx, rax
0x180003fce  test    rax, rax
0x180003fd1  jz      loc_180004086
0x180003fd7  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x180003fde  xor     r9d, r9d
0x180003fe1  mov     [rdx], rax
0x180003fe4  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180003feb  mov     [rdx+8], rax
0x180003fef  mov     rcx, [rdi]
0x180003ff2  lea     r8d, [r9+2]
0x180003ff6  mov     rax, [rcx+10h]
0x180003ffa  mov     rcx, rdi
0x180003ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004002  test    eax, eax
0x180004004  js      loc_180004092
0x18000400a  mov     rax, [rdi]
0x18000400d  lea     r8, aLow; "LOW"
0x180004014  mov     edx, 2
0x180004019  mov     rcx, rdi
0x18000401c  mov     rax, [rax+20h]
0x180004020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004025  test    eax, eax
0x180004027  js      short loc_180004092
0x180004029  call    ?Initialize@TOKEN_KEY@@SAJXZ; TOKEN_KEY::Initialize(void)
0x18000402e  test    eax, eax
0x180004030  js      short loc_180004092
0x180004032  mov     ecx, 0A78h; Size
0x180004037  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000403c  test    rax, rax
0x18000403f  jz      short loc_18000407F
0x180004041  lea     rcx, ??_7ANON_AUTH_PROVIDER@@6B@; this
0x180004048  mov     cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA, rax; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x18000404f  mov     [rax], rcx
0x180004052  mov     [rax+10h], bx
0x180004056  mov     [rax+210h], bx
0x18000405d  mov     [rax+0A10h], rbx
0x180004064  mov     [rax+0A18h], ebx
0x18000406a  mov     [rax+0A20h], rbx
0x180004071  mov     [rax+0A28h], rbx
0x180004078  call    ?InitializeInstance@ANON_AUTH_PROVIDER@@QEAAJXZ; ANON_AUTH_PROVIDER::InitializeInstance(void)
0x18000407d  jmp     short loc_180004092
0x18000407f  mov     cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA, rbx; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x180004086  mov     eax, 80070008h
0x18000408b  jmp     short loc_180004092
0x18000408d  mov     eax, 80004005h
0x180004092  mov     rbx, [rsp+38h+arg_0]
0x180004097  add     rsp, 30h
0x18000409b  pop     rdi
0x18000409c  retn
```
