# ServiceManager::CollectUserProxyTelemetry(void)

- ea: `0x180013f20`
- end: `0x180014006`
- name: `?CollectUserProxyTelemetry@ServiceManager@@AEAAJXZ`
- size: `230`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x180013f20`
- `0x180016100`
- `0x1800171d0`
- `0x18001e354`
- `0x18001e998`
- `0x180025010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013f6a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013f6a`

## string_xrefs

- `0x180013f61`: `ServiceManager::CollectUserProxyTelemetry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::CollectUserProxyTelemetry(ServiceManager *this)
{
  int ClientProxyResolver; // eax
  int v3; // r8d
  unsigned int v4; // ebx
  unsigned __int64 v5; // rdx
  unsigned __int8 v6; // cl
  int v7; // edi
  OfflineMapsTelemetry *v8; // rax
  int v10; // [rsp+38h] [rbp+10h] BYREF
  struct IClientProxyResolver *v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = 0;
  v10 = -1;
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&v11);
  ClientProxyResolver = ServiceManager::GetClientProxyResolver(this, &v11);
  if ( ClientProxyResolver < 0 )
  {
    v3 = 650;
LABEL_3:
    v4 = ZTraceReportPropagation(ClientProxyResolver, "ServiceManager::CollectUserProxyTelemetry", v3, this);
    goto LABEL_7;
  }
  ClientProxyResolver = (*(__int64 (__fastcall **)(struct IClientProxyResolver *, const wchar_t *, int *))(*(_QWORD *)v11 + 32LL))(
                          v11,
                          L"https://virtualearth.net/",
                          &v10);
  if ( ClientProxyResolver < 0 )
  {
    v3 = 653;
    goto LABEL_3;
  }
  v4 = 0;
LABEL_7:
  if ( (*(__int64 (__fastcall **)(struct IClientProxyResolver *))(*(_QWORD *)v11 + 24LL))(v11) )
  {
    if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 4318) )
      __int2c();
    v7 = v10;
    if ( OfflineMapsTelemetry::IsEnabled(v6, v5) )
    {
      v8 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::UserProxyConfiguration_(v8, v7, v4);
    }
  }
  else
  {
    *((_BYTE *)this + 4318) = 0;
  }
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&v11);
  return v4;
}

```

## disassembly

```asm
0x180013f20  mov     rax, rsp
0x180013f23  mov     [rax+8], rbx
0x180013f27  push    rdi
0x180013f28  sub     rsp, 20h
0x180013f2c  mov     rdi, rcx
0x180013f2f  mov     qword ptr [rax+18h], 0
0x180013f37  mov     dword ptr [rax+10h], 0FFFFFFFFh
0x180013f3e  lea     rcx, [rax+18h]
0x180013f42  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x180013f47  lea     rdx, [rsp+28h+arg_10]; struct IClientProxyResolver **
0x180013f4c  mov     rcx, rdi; this
0x180013f4f  call    ?GetClientProxyResolver@ServiceManager@@UEAAJPEAPEAUIClientProxyResolver@@@Z; ServiceManager::GetClientProxyResolver(IClientProxyResolver * *)
0x180013f54  test    eax, eax
0x180013f56  jns     short loc_180013F74
0x180013f58  mov     r8d, 28Ah
0x180013f5e  mov     r9, rdi
0x180013f61  lea     rdx, aServicemanager_83; "ServiceManager::CollectUserProxyTelemet"...
0x180013f68  mov     ecx, eax
0x180013f6a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180013f70  mov     ebx, eax
0x180013f72  jmp     short loc_180013F9F
0x180013f74  mov     rcx, [rsp+28h+arg_10]
0x180013f79  mov     rax, [rcx]
0x180013f7c  lea     r8, [rsp+28h+arg_8]
0x180013f81  lea     rdx, aHttpsVirtualea; "https://virtualearth.net/"
0x180013f88  mov     rax, [rax+20h]
0x180013f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f91  test    eax, eax
0x180013f93  jns     short loc_180013F9D
0x180013f95  mov     r8d, 28Dh
0x180013f9b  jmp     short loc_180013F5E
0x180013f9d  xor     ebx, ebx
0x180013f9f  mov     rcx, [rsp+28h+arg_10]
0x180013fa4  mov     rax, [rcx]
0x180013fa7  mov     rax, [rax+18h]
0x180013fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fb0  test    rax, rax
0x180013fb3  jnz     short loc_180013FBD
0x180013fb5  xchg    al, [rdi+10DEh]
0x180013fbb  jmp     short loc_180013FEF
0x180013fbd  lea     rcx, [rdi+10DEh]
0x180013fc4  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180013fc9  test    al, al
0x180013fcb  jnz     short loc_180013FCF
0x180013fcd  int     2Ch; Windows NT - assertion failure
0x180013fcf  mov     edi, [rsp+28h+arg_8]
0x180013fd3  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180013fd8  test    al, al
0x180013fda  jz      short loc_180013FEF
0x180013fdc  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180013fe1  mov     r8d, ebx; int
0x180013fe4  mov     edx, edi; int
0x180013fe6  mov     rcx, rax; this
0x180013fe9  call    ?UserProxyConfiguration_@OfflineMapsTelemetry@@QEAAXHJ@Z; OfflineMapsTelemetry::UserProxyConfiguration_(int,long)
0x180013fee  nop
0x180013fef  lea     rcx, [rsp+28h+arg_10]
0x180013ff4  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x180013ff9  mov     eax, ebx
0x180013ffb  mov     rbx, [rsp+28h+arg_0]
0x180014000  add     rsp, 20h
0x180014004  pop     rdi
0x180014005  retn
```
