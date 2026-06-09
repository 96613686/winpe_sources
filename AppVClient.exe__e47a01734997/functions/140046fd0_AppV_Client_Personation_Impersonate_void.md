# AppV::Client::Personation::Impersonate(void *)

- ea: `0x140046fd0`
- end: `0x14004708b`
- name: `?Impersonate@Personation@Client@AppV@@MEAA_KPEAX@Z`
- size: `187`
- prototype: `unsigned __int64(AppV::Client::Personation *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140046da0`
- `0x140046eb0`

## callees

- `0x140018bec`
- `0x140046fd0`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140047023`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140047023`
- `KERNEL32!GetLastError` at `0x140047064`
- `KERNEL32!GetLastError` at `0x140047064`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140046fe7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140047037`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140046fe7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140047037`

## string_xrefs

- `0x140046fe0`: `admin\appman\appv\client\common\impersonator.cpp`
- `0x140046ff7`: `admin\appman\appv\client\common\impersonator.cpp`
- `0x140047030`: `admin\appman\appv\client\common\impersonator.cpp`
- `0x140047047`: `admin\appman\appv\client\common\impersonator.cpp`

## pseudocode

```c
unsigned __int64 __fastcall AppV::Client::Personation::Impersonate(AppV::Client::Personation *this, void *a2)
{
  char *v2; // rax
  const char *v3; // rax
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  char *v7; // rax
  const char *v8; // rax
  unsigned __int64 v9; // rbx
  DWORD LastError; // eax

  if ( !a2 )
  {
    v2 = strrchr("admin\\appman\\appv\\client\\common\\impersonator.cpp", 92);
    if ( v2 )
      v3 = v2 + 1;
    else
      v3 = "admin\\appman\\appv\\client\\common\\impersonator.cpp";
    v4 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v3) << 52;
    v5 = 0x30800000001LL;
    return v5 | v4;
  }
  if ( !ImpersonateLoggedOnUser(a2) )
  {
    v7 = strrchr("admin\\appman\\appv\\client\\common\\impersonator.cpp", 92);
    if ( v7 )
      v8 = v7 + 1;
    else
      v8 = "admin\\appman\\appv\\client\\common\\impersonator.cpp";
    v9 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v8) << 52;
    LastError = GetLastError();
    v5 = 0x32800000000LL;
    v4 = v9 | LastError;
    return v5 | v4;
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x140046fd0  push    rbx
0x140046fd2  sub     rsp, 20h
0x140046fd6  test    rdx, rdx
0x140046fd9  jnz     short loc_140047020
0x140046fdb  mov     edx, 5Ch ; '\'; Ch
0x140046fe0  lea     rcx, aAdminAppmanApp_1; "admin\\appman\\appv\\client\\common\\im"...
0x140046fe7  call    cs:__imp_strrchr
0x140046fed  test    rax, rax
0x140046ff0  jz      short loc_140046FF7
0x140046ff2  inc     rax
0x140046ff5  jmp     short loc_140046FFE
0x140046ff7  lea     rax, aAdminAppmanApp_1; "admin\\appman\\appv\\client\\common\\im"...
0x140046ffe  mov     rdx, rax; char *
0x140047001  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140047008  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004700d  shl     rax, 34h
0x140047011  mov     rcx, 30800000001h
0x14004701b  or      rax, rcx
0x14004701e  jmp     short loc_140047085
0x140047020  mov     rcx, rdx; hToken
0x140047023  call    cs:__imp_ImpersonateLoggedOnUser
0x140047029  test    eax, eax
0x14004702b  jnz     short loc_14004707B
0x14004702d  lea     edx, [rax+5Ch]; Ch
0x140047030  lea     rcx, aAdminAppmanApp_1; "admin\\appman\\appv\\client\\common\\im"...
0x140047037  call    cs:__imp_strrchr
0x14004703d  test    rax, rax
0x140047040  jz      short loc_140047047
0x140047042  inc     rax
0x140047045  jmp     short loc_14004704E
0x140047047  lea     rax, aAdminAppmanApp_1; "admin\\appman\\appv\\client\\common\\im"...
0x14004704e  mov     rdx, rax; char *
0x140047051  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140047058  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004705d  mov     rbx, rax
0x140047060  shl     rbx, 34h
0x140047064  call    cs:__imp_GetLastError
0x14004706a  mov     eax, eax
0x14004706c  mov     rcx, 32800000000h
0x140047076  or      rax, rbx
0x140047079  jmp     short loc_14004701B
0x14004707b  mov     rax, 8000000000h
0x140047085  add     rsp, 20h
0x140047089  pop     rbx
0x14004708a  retn
```
