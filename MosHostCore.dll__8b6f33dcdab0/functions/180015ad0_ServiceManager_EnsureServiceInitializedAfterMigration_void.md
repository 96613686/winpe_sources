# ServiceManager::EnsureServiceInitializedAfterMigration(void)

- ea: `0x180015ad0`
- end: `0x180015b39`
- name: `?EnsureServiceInitializedAfterMigration@ServiceManager@@UEAAJXZ`
- size: `105`
- prototype: `int __fastcall(ServiceManager *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180015898`
- `0x180015ad0`
- `0x18001e454`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015ae4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015ae4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015b10`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015b10`

## string_xrefs

- `0x180015b07`: `ServiceManager::EnsureServiceInitializedAfterMigration`

## pseudocode

```c
int __fastcall ServiceManager::EnsureServiceInitializedAfterMigration(ServiceManager *this)
{
  char *v1; // rdi
  int v2; // ebx
  int v3; // eax
  int v4; // r8d

  v1 = (char *)this - 8;
  v2 = *((_DWORD *)this + 852);
  if ( v2 != GetCurrentThreadId() )
    __int2c();
  v3 = ServiceManager::EnsureServiceInitialized((__int64)v1, 0);
  if ( v3 < 0 )
  {
    v4 = 3698;
    return ZTraceReportPropagation(v3, "ServiceManager::EnsureServiceInitializedAfterMigration", v4, v1);
  }
  v3 = ServiceManager::WaitForMOSAndBingInit((ServiceManager *)v1);
  if ( v3 < 0 )
  {
    v4 = 3700;
    return ZTraceReportPropagation(v3, "ServiceManager::EnsureServiceInitializedAfterMigration", v4, v1);
  }
  return 0;
}

```

## disassembly

```asm
0x180015ad0  mov     [rsp+arg_0], rbx
0x180015ad5  push    rdi
0x180015ad6  sub     rsp, 20h
0x180015ada  lea     rdi, [rcx-8]
0x180015ade  mov     ebx, [rdi+0D58h]
0x180015ae4  call    cs:__imp_GetCurrentThreadId
0x180015aea  cmp     ebx, eax
0x180015aec  jz      short loc_180015AF0
0x180015aee  int     2Ch; Windows NT - assertion failure
0x180015af0  xor     edx, edx
0x180015af2  mov     rcx, rdi
0x180015af5  call    ?EnsureServiceInitialized@ServiceManager@@AEAAJW4MapsClientType@@@Z; ServiceManager::EnsureServiceInitialized(MapsClientType)
0x180015afa  test    eax, eax
0x180015afc  jns     short loc_180015B18
0x180015afe  mov     r8d, 0E72h
0x180015b04  mov     r9, rdi
0x180015b07  lea     rdx, aServicemanager_45; "ServiceManager::EnsureServiceInitialize"...
0x180015b0e  mov     ecx, eax
0x180015b10  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180015b16  jmp     short loc_180015B2E
0x180015b18  mov     rcx, rdi; this
0x180015b1b  call    ?WaitForMOSAndBingInit@ServiceManager@@AEAAJXZ; ServiceManager::WaitForMOSAndBingInit(void)
0x180015b20  test    eax, eax
0x180015b22  jns     short loc_180015B2C
0x180015b24  mov     r8d, 0E74h
0x180015b2a  jmp     short loc_180015B04
0x180015b2c  xor     eax, eax
0x180015b2e  mov     rbx, [rsp+28h+arg_0]
0x180015b33  add     rsp, 20h
0x180015b37  pop     rdi
0x180015b38  retn
```
