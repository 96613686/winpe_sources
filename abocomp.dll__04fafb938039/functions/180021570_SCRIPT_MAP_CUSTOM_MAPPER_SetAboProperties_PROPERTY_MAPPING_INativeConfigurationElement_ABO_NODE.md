# SCRIPT_MAP_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x180021570`
- end: `0x180021907`
- name: `?SetAboProperties@SCRIPT_MAP_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `919`
- prototype: `int(SCRIPT_MAP_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180009818`
- `0x18000a838`
- `0x18001bd50`
- `0x180021570`
- `0x180026a60`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180021745`
- `msvcrt!_wcsicmp` at `0x180021764`
- `msvcrt!_wcsicmp` at `0x18002177a`
- `msvcrt!_wcsicmp` at `0x180021745`
- `msvcrt!_wcsicmp` at `0x180021764`
- `msvcrt!_wcsicmp` at `0x18002177a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800215f1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800215f1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800218d4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800218d4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800217d5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800217d5`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800215b3`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800215b3`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18002185b`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18002185b`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18002184d`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18002184d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800218de`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800218de`

## string_xrefs

- `0x18002173e`: `ServerSideIncludeModule`

## pseudocode

```c
__int64 __fastcall SCRIPT_MAP_CUSTOM_MAPPER::SetAboProperties(
        SCRIPT_MAP_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  int MergedConfigElement; // ebx
  int v9; // r9d
  unsigned int v10; // edi
  SCRIPT_MAP_CUSTOM_MAPPER *v11; // rcx
  const unsigned __int16 *Str; // r8
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  struct INativeConfigurationElement *v16; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeConfigurationElement *v18; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpSrc; // [rsp+58h] [rbp-A8h] BYREF
  struct _METADATA_RECORD v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v22[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v23[256]; // [rsp+100h] [rbp+0h] BYREF

  v18 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v21);
  v15 = 0;
  v14 = 0;
  v16 = 0;
  String1 = 0;
  lpSrc = 0;
  memset_0(v23, 0, sizeof(v23));
  STRU::STRU((STRU *)v22, v23, 0x100u);
  if ( a2 && a4 && a3 )
  {
    MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a3 + 40LL))(
                            a3,
                            &v15);
    if ( MergedConfigElement >= 0 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 72LL))(v15, &v14);
      if ( MergedConfigElement >= 0 )
      {
        if ( v14 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          v9 = *((_DWORD *)a2 + 43) & 1;
          v15 = 0;
          MergedConfigElement = ABO_NODE::GetMergedConfigElement(a4, L"system.webServer/handlers", &v18, v9);
          if ( MergedConfigElement >= 0 )
          {
            MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v18 + 40LL))(
                                    v18,
                                    &v15);
            if ( MergedConfigElement >= 0 )
            {
              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 24LL))(
                                      v15,
                                      &v14);
              if ( MergedConfigElement >= 0 )
              {
                v10 = 0;
                if ( v14 )
                {
                  while ( 1 )
                  {
                    MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v15 + 32LL))(
                                            v15,
                                            v10,
                                            &v16);
                    if ( MergedConfigElement < 0 )
                      goto LABEL_25;
                    MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v16 + 64LL))(
                                            v16,
                                            L"modules",
                                            &String1,
                                            0,
                                            0);
                    if ( MergedConfigElement < 0 )
                      goto LABEL_25;
                    if ( !_wcsicmp(String1, L"ServerSideIncludeModule") )
                      break;
                    if ( !_wcsicmp(String1, L"IsapiModule") || !_wcsicmp(String1, L"CgiModule") )
                    {
                      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v16 + 64LL))(
                                              v16,
                                              L"scriptProcessor",
                                              &lpSrc,
                                              0,
                                              0);
                      if ( MergedConfigElement < 0 )
                        goto LABEL_25;
                      if ( *lpSrc )
                      {
                        MergedConfigElement = ExpandEnvironmentVariables(lpSrc, (struct STRU *)v22);
                        if ( MergedConfigElement < 0 )
                          goto LABEL_25;
                        Str = STRU::QueryStr((STRU *)v22);
LABEL_21:
                        MergedConfigElement = SCRIPT_MAP_CUSTOM_MAPPER::AddScriptMap(
                                                v11,
                                                v16,
                                                Str,
                                                (struct MULTISZ *)v21);
                        if ( MergedConfigElement < 0 )
                          goto LABEL_25;
                      }
                    }
                    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v16 + 16LL))(v16);
                    ++v10;
                    v16 = 0;
                    if ( v10 >= v14 )
                      goto LABEL_23;
                  }
                  Str = (const unsigned __int16 *)((char *)this + 8);
                  goto LABEL_21;
                }
LABEL_23:
                v20.dwMDIdentifier = *((_DWORD *)a2 + 36);
                v20.dwMDUserType = *((_DWORD *)a2 + 37);
                v20.dwMDDataType = *((_DWORD *)a2 + 38);
                v20.dwMDAttributes = *((_DWORD *)a2 + 39);
                *(&v20.dwMDDataLen + 1) = 0;
                *(_QWORD *)&v20.dwMDDataTag = 0;
                v20.dwMDDataLen = MULTISZ::QueryCB((MULTISZ *)v21);
                v20.pbMDData = (unsigned __int8 *)MULTISZ::QueryStr((MULTISZ *)v21);
                MergedConfigElement = ABO_NODE::SetDataByMapping(a4, &v20, a2);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    MergedConfigElement = -2147024809;
  }
LABEL_25:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  STRU::~STRU((STRU *)v22);
  MULTISZ::~MULTISZ((MULTISZ *)v21);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x180021570  push    rbp
0x180021572  push    rbx
0x180021573  push    rsi
0x180021574  push    rdi
0x180021575  push    r12
0x180021577  push    r14
0x180021579  push    r15
0x18002157b  lea     rbp, [rsp-210h]
0x180021583  sub     rsp, 310h
0x18002158a  mov     rax, cs:__security_cookie
0x180021591  xor     rax, rsp
0x180021594  mov     [rbp+240h+var_40], rax
0x18002159b  mov     r15, rcx
0x18002159e  xor     r12d, r12d
0x1800215a1  lea     rcx, [rbp+240h+var_2B8]
0x1800215a5  mov     [rsp+340h+var_2F0], r12
0x1800215aa  mov     r14, r9
0x1800215ad  mov     rbx, r8
0x1800215b0  mov     rsi, rdx
0x1800215b3  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800215b9  xor     edx, edx; Val
0x1800215bb  mov     [rsp+340h+var_308], r12
0x1800215c0  mov     r8d, 200h; Size
0x1800215c6  mov     [rsp+340h+var_310], r12d
0x1800215cb  lea     rcx, [rbp+240h+var_240]; void *
0x1800215cf  mov     [rsp+340h+var_300], r12
0x1800215d4  mov     [rsp+340h+String1], r12
0x1800215d9  mov     [rsp+340h+lpSrc], r12
0x1800215de  call    memset_0
0x1800215e3  mov     r8d, 100h
0x1800215e9  lea     rdx, [rbp+240h+var_240]
0x1800215ed  lea     rcx, [rbp+240h+var_280]
0x1800215f1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800215f7  test    rsi, rsi
0x1800215fa  jz      loc_18002187A
0x180021600  test    r14, r14
0x180021603  jz      loc_18002187A
0x180021609  test    rbx, rbx
0x18002160c  jz      loc_18002187A
0x180021612  mov     rax, [rbx]
0x180021615  lea     rdx, [rsp+340h+var_308]
0x18002161a  mov     rcx, rbx
0x18002161d  mov     rax, [rax+28h]
0x180021621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021626  mov     ebx, eax
0x180021628  test    eax, eax
0x18002162a  js      loc_18002187F
0x180021630  mov     rcx, [rsp+340h+var_308]
0x180021635  lea     rdx, [rsp+340h+var_310]
0x18002163a  mov     rax, [rcx]
0x18002163d  mov     rax, [rax+48h]
0x180021641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021646  mov     ebx, eax
0x180021648  test    eax, eax
0x18002164a  js      loc_18002187F
0x180021650  cmp     [rsp+340h+var_310], r12d
0x180021655  jz      loc_18002187F
0x18002165b  mov     rcx, [rsp+340h+var_308]
0x180021660  mov     rax, [rcx]
0x180021663  mov     rax, [rax+10h]
0x180021667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002166c  mov     r9d, [rsi+0ACh]
0x180021673  lea     r8, [rsp+340h+var_2F0]; struct INativeConfigurationElement **
0x180021678  and     r9d, 1; int
0x18002167c  mov     [rsp+340h+var_308], r12
0x180021681  lea     rdx, aSystemWebserve_19; "system.webServer/handlers"
0x180021688  mov     rcx, r14; this
0x18002168b  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x180021690  mov     ebx, eax
0x180021692  test    eax, eax
0x180021694  js      loc_18002187F
0x18002169a  mov     rcx, [rsp+340h+var_2F0]
0x18002169f  lea     rdx, [rsp+340h+var_308]
0x1800216a4  mov     rax, [rcx]
0x1800216a7  mov     rax, [rax+28h]
0x1800216ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216b0  mov     ebx, eax
0x1800216b2  test    eax, eax
0x1800216b4  js      loc_18002187F
0x1800216ba  mov     rcx, [rsp+340h+var_308]
0x1800216bf  lea     rdx, [rsp+340h+var_310]
0x1800216c4  mov     rax, [rcx]
0x1800216c7  mov     rax, [rax+18h]
0x1800216cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216d0  mov     ebx, eax
0x1800216d2  test    eax, eax
0x1800216d4  js      loc_18002187F
0x1800216da  mov     edi, r12d
0x1800216dd  cmp     [rsp+340h+var_310], r12d
0x1800216e2  jbe     loc_180021818
0x1800216e8  mov     rcx, [rsp+340h+var_308]
0x1800216ed  lea     r8, [rsp+340h+var_300]
0x1800216f2  mov     edx, edi
0x1800216f4  mov     rax, [rcx]
0x1800216f7  mov     rax, [rax+20h]
0x1800216fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021700  mov     ebx, eax
0x180021702  test    eax, eax
0x180021704  js      loc_18002187F
0x18002170a  mov     rcx, [rsp+340h+var_300]
0x18002170f  lea     r8, [rsp+340h+String1]
0x180021714  xor     r9d, r9d
0x180021717  mov     [rsp+340h+var_320], r12
0x18002171c  lea     rdx, aModules; "modules"
0x180021723  mov     rax, [rcx]
0x180021726  mov     rax, [rax+40h]
0x18002172a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002172f  mov     ebx, eax
0x180021731  test    eax, eax
0x180021733  js      loc_18002187F
0x180021739  mov     rcx, [rsp+340h+String1]; String1
0x18002173e  lea     rdx, aServersideincl; "ServerSideIncludeModule"
0x180021745  call    cs:__imp__wcsicmp
0x18002174b  test    eax, eax
0x18002174d  jnz     short loc_180021758
0x18002174f  lea     r8, [r15+8]
0x180021753  jmp     loc_1800217DE
0x180021758  mov     rcx, [rsp+340h+String1]; String1
0x18002175d  lea     rdx, aIsapimodule; "IsapiModule"
0x180021764  call    cs:__imp__wcsicmp
0x18002176a  test    eax, eax
0x18002176c  jz      short loc_180021784
0x18002176e  mov     rcx, [rsp+340h+String1]; String1
0x180021773  lea     rdx, aCgimodule; "CgiModule"
0x18002177a  call    cs:__imp__wcsicmp
0x180021780  test    eax, eax
0x180021782  jnz     short loc_1800217F6
0x180021784  mov     rcx, [rsp+340h+var_300]
0x180021789  lea     r8, [rsp+340h+lpSrc]
0x18002178e  xor     r9d, r9d
0x180021791  mov     [rsp+340h+var_320], r12
0x180021796  lea     rdx, aScriptprocesso; "scriptProcessor"
0x18002179d  mov     rax, [rcx]
0x1800217a0  mov     rax, [rax+40h]
0x1800217a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217a9  mov     ebx, eax
0x1800217ab  test    eax, eax
0x1800217ad  js      loc_18002187F
0x1800217b3  mov     rcx, [rsp+340h+lpSrc]; lpSrc
0x1800217b8  cmp     [rcx], r12w
0x1800217bc  jz      short loc_1800217F6
0x1800217be  lea     rdx, [rbp+240h+var_280]; struct STRU *
0x1800217c2  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x1800217c7  mov     ebx, eax
0x1800217c9  test    eax, eax
0x1800217cb  js      loc_18002187F
0x1800217d1  lea     rcx, [rbp+240h+var_280]
0x1800217d5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800217db  mov     r8, rax; unsigned __int16 *
0x1800217de  mov     rdx, [rsp+340h+var_300]; struct INativeConfigurationElement *
0x1800217e3  lea     r9, [rbp+240h+var_2B8]; struct MULTISZ *
0x1800217e7  call    ?AddScriptMap@SCRIPT_MAP_CUSTOM_MAPPER@@AEAAJPEAVINativeConfigurationElement@@PEBGPEAVMULTISZ@@@Z; SCRIPT_MAP_CUSTOM_MAPPER::AddScriptMap(INativeConfigurationElement *,ushort const *,MULTISZ *)
0x1800217ec  mov     ebx, eax
0x1800217ee  test    eax, eax
0x1800217f0  js      loc_18002187F
0x1800217f6  mov     rcx, [rsp+340h+var_300]
0x1800217fb  mov     rax, [rcx]
0x1800217fe  mov     rax, [rax+10h]
0x180021802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021807  inc     edi
0x180021809  mov     [rsp+340h+var_300], r12
0x18002180e  cmp     edi, [rsp+340h+var_310]
0x180021812  jb      loc_1800216E8
0x180021818  mov     eax, [rsi+90h]
0x18002181e  lea     rcx, [rbp+240h+var_2B8]
0x180021822  mov     [rsp+340h+var_2E0.dwMDIdentifier], eax
0x180021826  mov     eax, [rsi+94h]
0x18002182c  mov     [rsp+340h+var_2E0.dwMDUserType], eax
0x180021830  mov     eax, [rsi+98h]
0x180021836  mov     [rsp+340h+var_2E0.dwMDDataType], eax
0x18002183a  mov     eax, [rsi+9Ch]
0x180021840  mov     [rsp+340h+var_2E0.dwMDAttributes], eax
0x180021844  mov     dword ptr [rsp+340h+var_2E0+14h], r12d
0x180021849  mov     qword ptr [rbp+240h+var_2E0.dwMDDataTag], r12
0x18002184d  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x180021853  lea     rcx, [rbp+240h+var_2B8]
0x180021857  mov     [rsp+340h+var_2E0.dwMDDataLen], eax
0x18002185b  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x180021861  mov     r8, rsi; struct PROPERTY_MAPPING *
0x180021864  lea     rdx, [rsp+340h+var_2E0]; struct _METADATA_RECORD *
0x180021869  mov     rcx, r14; this
0x18002186c  mov     [rsp+340h+var_2E0.pbMDData], rax
0x180021871  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x180021876  mov     ebx, eax
0x180021878  jmp     short loc_18002187F
0x18002187a  mov     ebx, 80070057h
0x18002187f  mov     rcx, [rsp+340h+var_308]
0x180021884  test    rcx, rcx
0x180021887  jz      short loc_18002189A
0x180021889  mov     rax, [rcx]
0x18002188c  mov     rax, [rax+10h]
0x180021890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021895  mov     [rsp+340h+var_308], r12
0x18002189a  mov     rcx, [rsp+340h+var_2F0]
0x18002189f  test    rcx, rcx
0x1800218a2  jz      short loc_1800218B5
0x1800218a4  mov     rax, [rcx]
0x1800218a7  mov     rax, [rax+10h]
0x1800218ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218b0  mov     [rsp+340h+var_2F0], r12
0x1800218b5  mov     rcx, [rsp+340h+var_300]
0x1800218ba  test    rcx, rcx
0x1800218bd  jz      short loc_1800218D0
0x1800218bf  mov     rax, [rcx]
0x1800218c2  mov     rax, [rax+10h]
0x1800218c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218cb  mov     [rsp+340h+var_300], r12
0x1800218d0  lea     rcx, [rbp+240h+var_280]
0x1800218d4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800218da  lea     rcx, [rbp+240h+var_2B8]
0x1800218de  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800218e4  mov     eax, ebx
0x1800218e6  mov     rcx, [rbp+240h+var_40]
0x1800218ed  xor     rcx, rsp; StackCookie
0x1800218f0  call    __security_check_cookie
0x1800218f5  add     rsp, 310h
0x1800218fc  pop     r15
0x1800218fe  pop     r14
0x180021900  pop     r12
0x180021902  pop     rdi
0x180021903  pop     rsi
0x180021904  pop     rbx
0x180021905  pop     rbp
0x180021906  retn
```
