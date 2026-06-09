# CONFIG_HISTORY::Initialize(void)

- ea: `0x180002e20`
- end: `0x180003015`
- name: `?Initialize@CONFIG_HISTORY@@QEAAJXZ`
- size: `501`
- prototype: `__int64 __fastcall(CONFIG_HISTORY *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005c3c`

## callees

- `0x180001008`
- `0x180002e20`
- `0x180003e70`
- `0x180004744`
- `0x180008464`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002f72`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002f72`
- `iisutil!PuDbgPrintError` at `0x180002f29`
- `iisutil!PuDbgPrintError` at `0x180002f29`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180002e5a`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180002e6a`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180002e7d`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180002ea6`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180002e5a`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180002e6a`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180002e7d`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180002ea6`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180002f93`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180002f93`

## string_xrefs

- `0x180002f1b`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history.cxx`
- `0x180002efa`: `Failed to allocate memory for CONFIG_HISTORY_ENTITY.\n`
- `0x180002f14`: `CONFIG_HISTORY::Initialize`
- `0x180002f4f`: `Failed to initialize CONFIG_HISTORY_ENTITY.\n`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY::Initialize(CONFIG_HISTORY *this)
{
  char *v2; // rax
  char *v3; // rbx
  int DefaultNativeConfigurationSystem; // ebx
  DWORD FileAttributesW; // eax
  BOOL v6; // eax
  struct INativeConfigurationSystem *v8; // [rsp+40h] [rbp+8h] BYREF
  char *v9; // [rsp+48h] [rbp+10h]

  v8 = 0;
  v2 = (char *)operator new(0x130u);
  v3 = v2;
  v9 = v2;
  if ( v2 )
  {
    STRU_PATH::STRU_PATH((STRU_PATH *)(v2 + 8), 0x5Cu);
    STRU_PATH::STRU_PATH((STRU_PATH *)(v3 + 72), 0x5Cu);
    STRU_PATH::STRU_PATH((STRU_PATH *)(v3 + 136), 0x5Cu);
    *((_QWORD *)v3 + 25) = 0;
    *((_QWORD *)v3 + 26) = 0;
    STRU_PATH::STRU_PATH((STRU_PATH *)(v3 + 216), 0x5Cu);
    *((_QWORD *)v3 + 35) = 0;
    *((_DWORD *)v3 + 72) = 0;
    *((_DWORD *)v3 + 73) = -1;
    *((_DWORD *)v3 + 74) = 0;
    *(_DWORD *)v3 = 1397049411;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 5) = v3;
  if ( v3 )
  {
    DefaultNativeConfigurationSystem = CONFIG_HISTORY_ENTITY::Initialize((CONFIG_HISTORY_ENTITY *)v3);
    if ( DefaultNativeConfigurationSystem >= 0 )
    {
      FileAttributesW = GetFileAttributesW(*(LPCWSTR *)(*((_QWORD *)this + 5) + 168LL));
      v6 = FileAttributesW != -1 && FileAttributesW != 16;
      *((_DWORD *)this + 12) = v6;
      DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem(&v8);
      if ( DefaultNativeConfigurationSystem >= 0 )
      {
        DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, CONFIG_HISTORY *))(*(_QWORD *)v8 + 40LL))(
                                             v8,
                                             this);
        if ( DefaultNativeConfigurationSystem >= 0 )
        {
          if ( !*((_DWORD *)this + 12)
            || (DefaultNativeConfigurationSystem = CONFIG_HISTORY::SetupAdministrationConfigurationSystem(this),
                DefaultNativeConfigurationSystem >= 0) )
          {
            DefaultNativeConfigurationSystem = MULTI_WORK_QUEUE::GetAndQueueWorkItem(
                                                 (APP_HOST_SERVICE *)((char *)g_pAppHostService + 24),
                                                 (struct MULTI_WORK_DISPATCH *)(((unsigned __int64)this + 8)
                                                                              & -(__int64)(this != 0)),
                                                 1u);
          }
        }
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
        260,
        "CONFIG_HISTORY::Initialize",
        DefaultNativeConfigurationSystem,
        "Failed to initialize CONFIG_HISTORY_ENTITY.\n");
    }
  }
  else
  {
    DefaultNativeConfigurationSystem = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
        247,
        "CONFIG_HISTORY::Initialize",
        -2147024888,
        "Failed to allocate memory for CONFIG_HISTORY_ENTITY.\n");
  }
  if ( v8 )
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)DefaultNativeConfigurationSystem;
}

```

## disassembly

```asm
0x180002e20  mov     [rsp+arg_10], rbx
0x180002e25  push    rdi
0x180002e26  sub     rsp, 30h
0x180002e2a  mov     rdi, rcx
0x180002e2d  mov     [rsp+38h+arg_0], 0
0x180002e36  mov     ecx, 130h; Size
0x180002e3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e40  mov     rbx, rax
0x180002e43  mov     [rsp+38h+arg_8], rax
0x180002e48  test    rax, rax
0x180002e4b  jz      loc_180002EDD
0x180002e51  mov     edx, 5Ch ; '\'
0x180002e56  lea     rcx, [rax+8]
0x180002e5a  call    cs:__imp_??0STRU_PATH@@QEAA@G@Z; STRU_PATH::STRU_PATH(ushort)
0x180002e60  nop
0x180002e61  mov     edx, 5Ch ; '\'
0x180002e66  lea     rcx, [rbx+48h]
0x180002e6a  call    cs:__imp_??0STRU_PATH@@QEAA@G@Z; STRU_PATH::STRU_PATH(ushort)
0x180002e70  nop
0x180002e71  mov     edx, 5Ch ; '\'
0x180002e76  lea     rcx, [rbx+88h]
0x180002e7d  call    cs:__imp_??0STRU_PATH@@QEAA@G@Z; STRU_PATH::STRU_PATH(ushort)
0x180002e83  nop
0x180002e84  mov     qword ptr [rbx+0C8h], 0
0x180002e8f  mov     qword ptr [rbx+0D0h], 0
0x180002e9a  mov     edx, 5Ch ; '\'
0x180002e9f  lea     rcx, [rbx+0D8h]
0x180002ea6  call    cs:__imp_??0STRU_PATH@@QEAA@G@Z; STRU_PATH::STRU_PATH(ushort)
0x180002eac  mov     qword ptr [rbx+118h], 0
0x180002eb7  mov     dword ptr [rbx+120h], 0
0x180002ec1  mov     dword ptr [rbx+124h], 0FFFFFFFFh
0x180002ecb  mov     dword ptr [rbx+128h], 0
0x180002ed5  mov     dword ptr [rbx], 53454843h
0x180002edb  jmp     short loc_180002EDF
0x180002edd  xor     ebx, ebx
0x180002edf  mov     [rdi+28h], rbx
0x180002ee3  test    rbx, rbx
0x180002ee6  jnz     short loc_180002F34
0x180002ee8  mov     ebx, 80070008h
0x180002eed  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002ef4  jz      loc_180002FF2
0x180002efa  lea     rax, aFailedToAlloca; "Failed to allocate memory for CONFIG_HI"...
0x180002f01  mov     [rsp+38h+var_10], rax
0x180002f06  mov     [rsp+38h+var_18], 80070008h
0x180002f0e  mov     r8d, 0F7h
0x180002f14  lea     r9, aConfigHistoryI; "CONFIG_HISTORY::Initialize"
0x180002f1b  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002f22  mov     rcx, cs:g_pDebug
0x180002f29  call    cs:__imp_PuDbgPrintError
0x180002f2f  jmp     loc_180002FF2
0x180002f34  mov     rcx, rbx; this
0x180002f37  call    ?Initialize@CONFIG_HISTORY_ENTITY@@QEAAJXZ; CONFIG_HISTORY_ENTITY::Initialize(void)
0x180002f3c  mov     ebx, eax
0x180002f3e  test    eax, eax
0x180002f40  jns     short loc_180002F67
0x180002f42  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002f49  jz      loc_180002FF2
0x180002f4f  lea     rax, aFailedToInitia_0; "Failed to initialize CONFIG_HISTORY_ENT"...
0x180002f56  mov     [rsp+38h+var_10], rax
0x180002f5b  mov     [rsp+38h+var_18], ebx
0x180002f5f  mov     r8d, 104h
0x180002f65  jmp     short loc_180002F14
0x180002f67  mov     rcx, [rdi+28h]
0x180002f6b  mov     rcx, [rcx+0A8h]; lpFileName
0x180002f72  call    cs:__imp_GetFileAttributesW
0x180002f78  cmp     eax, 0FFFFFFFFh
0x180002f7b  jz      short loc_180002F89
0x180002f7d  cmp     eax, 10h
0x180002f80  jz      short loc_180002F89
0x180002f82  mov     eax, 1
0x180002f87  jmp     short loc_180002F8B
0x180002f89  xor     eax, eax
0x180002f8b  mov     [rdi+30h], eax
0x180002f8e  lea     rcx, [rsp+38h+arg_0]
0x180002f93  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180002f99  mov     ebx, eax
0x180002f9b  test    eax, eax
0x180002f9d  js      short loc_180002FF2
0x180002f9f  mov     rcx, [rsp+38h+arg_0]
0x180002fa4  mov     rax, [rcx]
0x180002fa7  mov     rdx, rdi
0x180002faa  mov     rax, [rax+28h]
0x180002fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb3  mov     ebx, eax
0x180002fb5  test    eax, eax
0x180002fb7  js      short loc_180002FF2
0x180002fb9  cmp     dword ptr [rdi+30h], 0
0x180002fbd  jz      short loc_180002FCD
0x180002fbf  mov     rcx, rdi; this
0x180002fc2  call    ?SetupAdministrationConfigurationSystem@CONFIG_HISTORY@@AEAAJXZ; CONFIG_HISTORY::SetupAdministrationConfigurationSystem(void)
0x180002fc7  mov     ebx, eax
0x180002fc9  test    eax, eax
0x180002fcb  js      short loc_180002FF2
0x180002fcd  lea     rax, [rdi+8]
0x180002fd1  neg     rdi
0x180002fd4  sbb     rdx, rdx
0x180002fd7  and     rdx, rax; struct MULTI_WORK_DISPATCH *
0x180002fda  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180002fe1  add     rcx, 18h; this
0x180002fe5  mov     r8d, 1; unsigned __int64
0x180002feb  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x180002ff0  mov     ebx, eax
0x180002ff2  mov     rcx, [rsp+38h+arg_0]
0x180002ff7  test    rcx, rcx
0x180002ffa  jz      short loc_180003008
0x180002ffc  mov     rax, [rcx]
0x180002fff  mov     rax, [rax+10h]
0x180003003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003008  mov     eax, ebx
0x18000300a  mov     rbx, [rsp+38h+arg_10]
0x18000300f  add     rsp, 30h
0x180003013  pop     rdi
0x180003014  retn
```
