# ServiceManager::ProcessPackageOrUpdateOperation(void)

- ea: `0x18001b068`
- end: `0x18001b19e`
- name: `?ProcessPackageOrUpdateOperation@ServiceManager@@AEAAJXZ`
- size: `310`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180014c00`
- `0x18001ac90`
- `0x18001af8c`
- `0x18001cf60`

## callees

- `0x180009c04`
- `0x180012cf0`
- `0x180014c00`
- `0x180015ed0`
- `0x18001aea4`
- `0x18001b068`
- `0x18001d224`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001b13f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001b16a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001b13f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001b16a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001b10e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001b10e`

## string_xrefs

- `0x18001b105`: `ServiceManager::ProcessPackageOrUpdateOperation`
- `0x18001b130`: `ServiceManager::ProcessPackageOrUpdateOperation`
- `0x18001b15b`: `ServiceManager::ProcessPackageOrUpdateOperation`

## pseudocode

```c
__int64 __fastcall ServiceManager::ProcessPackageOrUpdateOperation(ServiceManager *this)
{
  char *v1; // rdi
  bool v3; // si
  int started; // eax
  char v5; // si
  int v6; // r8d
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax

  v1 = (char *)this + 3816;
  v3 = (unsigned int)(*((_DWORD *)this + 882) - 4) <= 1;
  if ( (unsigned __int8)ClientsTracker::HasClientsOf((char *)this + 3816, 2)
    || (started = ServiceManager::AttachClient(this, 2, 1, 0, 0), started >= 0) )
  {
    if ( !(unsigned __int8)ClientsTracker::HasClientsOf(v1, 2) )
      __int2c();
    if ( !v3 )
      return 0;
    started = ServiceManager::StartOperation(this);
    if ( started >= 0 )
      return 0;
    v5 = 1;
    v6 = 1299;
  }
  else
  {
    v5 = 0;
    v6 = 1286;
  }
  v7 = ZTraceReportOrigination(started, "ServiceManager::ProcessPackageOrUpdateOperation", v6, this);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( v5 )
    {
      v9 = ServiceManager::OnOperationComplete(this, v7);
      if ( v9 < 0 )
        ZTraceReportIgnore(v9, "ServiceManager::ProcessPackageOrUpdateOperation", 1308, this);
      v10 = ServiceManager::DetachClient(this, 2, 0);
      if ( v10 < 0 )
        ZTraceReportIgnore(v10, "ServiceManager::ProcessPackageOrUpdateOperation", 1309, this);
    }
    *((_DWORD *)this + 884) = 1;
    *((_DWORD *)this + 885) = v8;
    ServiceManager::FireOdmlStateChange(this);
  }
  return v8;
}

```

## disassembly

```asm
0x18001b068  mov     [rsp+arg_0], rbx
0x18001b06d  mov     [rsp+arg_8], rsi
0x18001b072  push    rdi
0x18001b073  sub     rsp, 30h
0x18001b077  mov     eax, [rcx+0DC8h]
0x18001b07d  lea     rdi, [rcx+0EE8h]
0x18001b084  sub     eax, 4
0x18001b087  mov     rbx, rcx
0x18001b08a  cmp     eax, 1
0x18001b08d  mov     edx, 2
0x18001b092  mov     rcx, rdi
0x18001b095  setbe   sil
0x18001b099  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x18001b09e  test    al, al
0x18001b0a0  jnz     short loc_18001B0CD
0x18001b0a2  xor     r9d, r9d
0x18001b0a5  mov     [rsp+38h+var_18], 0
0x18001b0ae  mov     rcx, rbx
0x18001b0b1  lea     edx, [r9+2]
0x18001b0b5  lea     r8d, [r9+1]
0x18001b0b9  call    ?AttachClient@ServiceManager@@UEAAJW4MapsClientType@@W4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@KPEAX@Z; ServiceManager::AttachClient(MapsClientType,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,ulong,void *)
0x18001b0be  test    eax, eax
0x18001b0c0  jns     short loc_18001B0CD
0x18001b0c2  xor     sil, sil
0x18001b0c5  mov     r8d, 506h
0x18001b0cb  jmp     short loc_18001B102
0x18001b0cd  mov     edx, 2
0x18001b0d2  mov     rcx, rdi
0x18001b0d5  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x18001b0da  test    al, al
0x18001b0dc  jnz     short loc_18001B0E0
0x18001b0de  int     2Ch; Windows NT - assertion failure
0x18001b0e0  test    sil, sil
0x18001b0e3  jz      loc_18001B18A
0x18001b0e9  mov     rcx, rbx; this
0x18001b0ec  call    ?StartOperation@ServiceManager@@AEAAJXZ; ServiceManager::StartOperation(void)
0x18001b0f1  test    eax, eax
0x18001b0f3  jns     loc_18001B18A
0x18001b0f9  mov     sil, 1
0x18001b0fc  mov     r8d, 513h
0x18001b102  mov     r9, rbx
0x18001b105  lea     rdx, aServicemanager; "ServiceManager::ProcessPackageOrUpdateO"...
0x18001b10c  mov     ecx, eax
0x18001b10e  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001b114  mov     edi, eax
0x18001b116  test    eax, eax
0x18001b118  jns     short loc_18001B18C
0x18001b11a  test    sil, sil
0x18001b11d  jz      short loc_18001B170
0x18001b11f  mov     edx, eax; int
0x18001b121  mov     rcx, rbx; this
0x18001b124  call    ?OnOperationComplete@ServiceManager@@AEAAJJ@Z; ServiceManager::OnOperationComplete(long)
0x18001b129  test    eax, eax
0x18001b12b  jns     short loc_18001B145
0x18001b12d  mov     r9, rbx
0x18001b130  lea     rdx, aServicemanager; "ServiceManager::ProcessPackageOrUpdateO"...
0x18001b137  mov     r8d, 51Ch
0x18001b13d  mov     ecx, eax
0x18001b13f  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001b145  xor     r8d, r8d
0x18001b148  mov     rcx, rbx
0x18001b14b  lea     edx, [r8+2]
0x18001b14f  call    ?DetachClient@ServiceManager@@UEAAJW4MapsClientType@@K@Z; ServiceManager::DetachClient(MapsClientType,ulong)
0x18001b154  test    eax, eax
0x18001b156  jns     short loc_18001B170
0x18001b158  mov     r9, rbx
0x18001b15b  lea     rdx, aServicemanager; "ServiceManager::ProcessPackageOrUpdateO"...
0x18001b162  mov     r8d, 51Dh
0x18001b168  mov     ecx, eax
0x18001b16a  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001b170  mov     rcx, rbx; this
0x18001b173  mov     dword ptr [rbx+0DD0h], 1
0x18001b17d  mov     [rbx+0DD4h], edi
0x18001b183  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001b188  jmp     short loc_18001B18C
0x18001b18a  xor     edi, edi
0x18001b18c  mov     rbx, [rsp+38h+arg_0]
0x18001b191  mov     eax, edi
0x18001b193  mov     rsi, [rsp+38h+arg_8]
0x18001b198  add     rsp, 30h
0x18001b19c  pop     rdi
0x18001b19d  retn
```
