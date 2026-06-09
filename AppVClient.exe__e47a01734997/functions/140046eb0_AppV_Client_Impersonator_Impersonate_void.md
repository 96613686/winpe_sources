# AppV::Client::Impersonator::Impersonate(void *)

- ea: `0x140046eb0`
- end: `0x140046fc0`
- name: `?Impersonate@Impersonator@Client@AppV@@UEAA_KPEAX@Z`
- size: `272`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Impersonator *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400518c0`
- `0x140052220`

## callees

- `0x140018bec`
- `0x140046eb0`
- `0x140046fd0`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140046f2f`
- `ADVAPI32!OpenThreadToken` at `0x140046f2f`
- `KERNEL32!GetCurrentThread` at `0x140046f19`
- `KERNEL32!GetCurrentThread` at `0x140046f19`
- `KERNEL32!GetLastError` at `0x140046f39`
- `KERNEL32!GetLastError` at `0x140046f39`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140046ed7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140046f54`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140046ed7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140046f54`

## string_xrefs

- `0x140046ed0`: `admin\appman\appv\client\common\impersonator.cpp`
- `0x140046ee7`: `admin\appman\appv\client\common\impersonator.cpp`
- `0x140046f4d`: `admin\appman\appv\client\common\impersonator.cpp`
- `0x140046f64`: `admin\appman\appv\client\common\impersonator.cpp`

## pseudocode

```c
unsigned __int64 __fastcall AppV::Client::Impersonator::Impersonate(AppV::Client::Impersonator *this, void *a2)
{
  char *v4; // rax
  const char *v5; // rax
  unsigned __int64 v6; // rax
  __int64 v7; // rcx
  unsigned __int64 result; // rax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v11; // rbx
  char *v12; // rax
  const char *v13; // rax
  unsigned __int64 FileId; // rax

  if ( *((_BYTE *)this + 12) )
  {
    v4 = strrchr("admin\\appman\\appv\\client\\common\\impersonator.cpp", 92);
    if ( v4 )
      v5 = v4 + 1;
    else
      v5 = "admin\\appman\\appv\\client\\common\\impersonator.cpp";
    v6 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v5) << 52;
    v7 = 0x80800000002LL;
    return v7 | v6;
  }
  if ( *((_DWORD *)this + 2) == 1 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)this + 2) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError != 1008 )
      {
        v12 = strrchr("admin\\appman\\appv\\client\\common\\impersonator.cpp", 92);
        if ( v12 )
          v13 = v12 + 1;
        else
          v13 = "admin\\appman\\appv\\client\\common\\impersonator.cpp";
        FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v13);
        v7 = 0x92800000000LL;
        v6 = v11 | (FileId << 52);
        return v7 | v6;
      }
    }
  }
  result = AppV::Client::Personation::Impersonate(this, a2);
  if ( (result & 0x8000000000LL) != 0 )
  {
    *((_BYTE *)this + 12) = 1;
    return 0x8000000000LL;
  }
  return result;
}

```

## disassembly

```asm
0x140046eb0  mov     [rsp+arg_0], rbx
0x140046eb5  mov     [rsp+arg_8], rsi
0x140046eba  push    rdi
0x140046ebb  sub     rsp, 20h
0x140046ebf  cmp     byte ptr [rcx+0Ch], 0
0x140046ec3  mov     rsi, rdx
0x140046ec6  mov     rdi, rcx
0x140046ec9  jz      short loc_140046F13
0x140046ecb  mov     edx, 5Ch ; '\'; Ch
0x140046ed0  lea     rcx, aAdminAppmanApp_1; "admin\\appman\\appv\\client\\common\\im"...
0x140046ed7  call    cs:__imp_strrchr
0x140046edd  test    rax, rax
0x140046ee0  jz      short loc_140046EE7
0x140046ee2  inc     rax
0x140046ee5  jmp     short loc_140046EEE
0x140046ee7  lea     rax, aAdminAppmanApp_1; "admin\\appman\\appv\\client\\common\\im"...
0x140046eee  mov     rdx, rax; char *
0x140046ef1  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140046ef8  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140046efd  shl     rax, 34h
0x140046f01  mov     rcx, 80800000002h
0x140046f0b  or      rax, rcx
0x140046f0e  jmp     loc_140046FB0
0x140046f13  cmp     dword ptr [rcx+8], 1
0x140046f17  jnz     short loc_140046F90
0x140046f19  call    cs:__imp_GetCurrentThread
0x140046f1f  mov     edx, 0Ch; DesiredAccess
0x140046f24  lea     r9, [rdi+10h]; TokenHandle
0x140046f28  mov     rcx, rax; ThreadHandle
0x140046f2b  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x140046f2f  call    cs:__imp_OpenThreadToken
0x140046f35  test    eax, eax
0x140046f37  jnz     short loc_140046F90
0x140046f39  call    cs:__imp_GetLastError
0x140046f3f  mov     ebx, eax
0x140046f41  cmp     eax, 3F0h
0x140046f46  jz      short loc_140046F90
0x140046f48  mov     edx, 5Ch ; '\'; Ch
0x140046f4d  lea     rcx, aAdminAppmanApp_1; "admin\\appman\\appv\\client\\common\\im"...
0x140046f54  call    cs:__imp_strrchr
0x140046f5a  test    rax, rax
0x140046f5d  jz      short loc_140046F64
0x140046f5f  inc     rax
0x140046f62  jmp     short loc_140046F6B
0x140046f64  lea     rax, aAdminAppmanApp_1; "admin\\appman\\appv\\client\\common\\im"...
0x140046f6b  mov     rdx, rax; char *
0x140046f6e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140046f75  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140046f7a  shl     rax, 34h
0x140046f7e  mov     rcx, 92800000000h
0x140046f88  or      rax, rbx
0x140046f8b  jmp     loc_140046F0B
0x140046f90  mov     rdx, rsi; void *
0x140046f93  mov     rcx, rdi; this
0x140046f96  call    ?Impersonate@Personation@Client@AppV@@MEAA_KPEAX@Z; AppV::Client::Personation::Impersonate(void *)
0x140046f9b  bt      rax, 27h ; '''
0x140046fa0  jnb     short loc_140046FB0
0x140046fa2  mov     byte ptr [rdi+0Ch], 1
0x140046fa6  mov     rax, 8000000000h
0x140046fb0  mov     rbx, [rsp+28h+arg_0]
0x140046fb5  mov     rsi, [rsp+28h+arg_8]
0x140046fba  add     rsp, 20h
0x140046fbe  pop     rdi
0x140046fbf  retn
```
