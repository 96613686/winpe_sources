# CService::InternalInit(ushort *,CServiceControlManager *,ulong,ushort *)

- ea: `0x180010870`
- end: `0x18001093e`
- name: `?InternalInit@CService@@IEAAJPEAGPEAVCServiceControlManager@@K0@Z`
- size: `206`
- prototype: `__int64 __fastcall(CService *__hidden this, unsigned __int16 *, struct CServiceControlManager *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180073390`

## callees

- `0x180010870`
- `0x180011ac0`
- `0x18007995c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108ed`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800108de`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800108de`

## string_xrefs

- `0x18001089e`: `com\complus\dtc\shared\util\scm.cpp`
- `0x18001090f`: `com\complus\dtc\shared\util\scm.cpp`
- `0x180010916`: `OpenServiceW call failed`
- `0x1800108c3`: `CServiceControlManager::GetHandle call failed`
- `0x180010897`: `CServiceControlManager::Create call failed`

## pseudocode

```c
__int64 __fastcall CService::InternalInit(
        struct CServiceControlManager **this,
        unsigned __int16 *a2,
        struct CServiceControlManager *a3,
        unsigned __int16 *a4)
{
  int v5; // ebx
  unsigned int v6; // r9d
  char *v7; // rdx
  SC_HANDLE v9; // rcx
  SC_HANDLE v10; // rax
  signed int LastError; // eax
  int v12; // edi
  unsigned int v13; // ecx

  v5 = CServiceControlManager::Create(this + 1, (unsigned int)a2, (unsigned __int16 *)a3, a4);
  if ( v5 < 0 )
  {
    v6 = 241;
    v7 = "CServiceControlManager::Create call failed";
LABEL_3:
    TraceFile(v5, v7, "com\\complus\\dtc\\shared\\util\\scm.cpp", v6);
    return (unsigned int)v5;
  }
  v9 = (SC_HANDLE)*((_QWORD *)this[1] + 1);
  if ( !v9 )
  {
    v6 = 258;
    v7 = "CServiceControlManager::GetHandle call failed";
    v5 = -2147467259;
    goto LABEL_3;
  }
  v10 = OpenServiceW(v9, L"MSDTC", 1u);
  this[2] = (struct CServiceControlManager *)v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    v12 = (unsigned __int16)LastError;
    v5 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    else
      v13 = LastError;
    TraceFile(v13, "OpenServiceW call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x10Du);
    if ( v5 > 0 )
      return v12 | 0x80070000;
    return (unsigned int)v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180010870  mov     [rsp+arg_0], rbx
0x180010875  mov     [rsp+arg_8], rsi
0x18001087a  push    rdi
0x18001087b  sub     rsp, 20h
0x18001087f  mov     rsi, rcx
0x180010882  add     rcx, 8; struct CServiceControlManager **
0x180010886  call    ?Create@CServiceControlManager@@SAJPEAPEAV1@KPEAG1@Z; CServiceControlManager::Create(CServiceControlManager * *,ulong,ushort *,ushort *)
0x18001088b  mov     ebx, eax
0x18001088d  test    eax, eax
0x18001088f  jns     short loc_1800108B0
0x180010891  mov     r9d, 0F1h; unsigned int
0x180010897  lea     rdx, aCservicecontro_0; "CServiceControlManager::Create call fai"...
0x18001089e  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x1800108a5  mov     ecx, ebx; int
0x1800108a7  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800108ac  mov     eax, ebx
0x1800108ae  jmp     short loc_18001092E
0x1800108b0  mov     rax, [rsi+8]
0x1800108b4  mov     rcx, [rax+8]; hSCManager
0x1800108b8  test    rcx, rcx
0x1800108bb  jnz     short loc_1800108D1
0x1800108bd  mov     r9d, 102h
0x1800108c3  lea     rdx, aCservicecontro; "CServiceControlManager::GetHandle call "...
0x1800108ca  mov     ebx, 80004005h
0x1800108cf  jmp     short loc_18001089E
0x1800108d1  mov     r8d, 1; dwDesiredAccess
0x1800108d7  lea     rdx, aMsdtc; "MSDTC"
0x1800108de  call    cs:__imp_OpenServiceW
0x1800108e4  mov     [rsi+10h], rax
0x1800108e8  test    rax, rax
0x1800108eb  jnz     short loc_18001092C
0x1800108ed  call    cs:__imp_GetLastError
0x1800108f3  movzx   edi, ax
0x1800108f6  mov     ebx, eax
0x1800108f8  mov     esi, 80070000h
0x1800108fd  test    eax, eax
0x1800108ff  jg      short loc_180010905
0x180010901  mov     ecx, eax
0x180010903  jmp     short loc_180010909
0x180010905  mov     ecx, edi
0x180010907  or      ecx, esi; int
0x180010909  mov     r9d, 10Dh; unsigned int
0x18001090f  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x180010916  lea     rdx, aOpenservicewCa; "OpenServiceW call failed"
0x18001091d  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180010922  test    ebx, ebx
0x180010924  jle     short loc_1800108AC
0x180010926  mov     ebx, edi
0x180010928  or      ebx, esi
0x18001092a  jmp     short loc_1800108AC
0x18001092c  xor     eax, eax
0x18001092e  mov     rbx, [rsp+28h+arg_0]
0x180010933  mov     rsi, [rsp+28h+arg_8]
0x180010938  add     rsp, 20h
0x18001093c  pop     rdi
0x18001093d  retn
```
