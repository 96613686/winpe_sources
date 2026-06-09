# ServiceManager::AddPackageWithNotification(uint,ulong)

- ea: `0x1800128d0`
- end: `0x180012a32`
- name: `?AddPackageWithNotification@ServiceManager@@UEAAJIK@Z`
- size: `354`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180008110`
- `0x18000f9b4`
- `0x1800128d0`
- `0x180012a40`
- `0x18001be24`
- `0x18001e520`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001291c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001296d`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001291c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001296d`

## string_xrefs

- `0x180012913`: `ServiceManager::AddPackageWithNotification`
- `0x180012964`: `ServiceManager::AddPackageWithNotification`

## pseudocode

```c
__int64 __fastcall ServiceManager::AddPackageWithNotification(ServiceManager *this, unsigned int a2, unsigned int a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int Package; // eax
  int v8; // r8d
  const unsigned __int16 *v9; // rax
  __int64 v10; // r8
  const unsigned __int16 *v11; // rdx
  _BYTE v13[24]; // [rsp+60h] [rbp-18h] BYREF
  struct OdmlMapDataPackage *v14; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+88h] [rbp+10h] BYREF

  v15 = a2;
  v14 = 0;
  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v13);
  v5 = ServiceManager::WaitForOdmlInit(this);
  if ( v5 >= 0 )
  {
    RelockableGate::~RelockableGate((RelockableGate *)v13);
    Package = ServiceManager::AddPackages((__int64)this, 1u, &v15, 0xBu);
    if ( Package >= 0 )
    {
      Package = PackageManager::GetPackage((ServiceManager *)((char *)this + 3568), v15, &v14);
      if ( Package >= 0 )
      {
        if ( !*((_QWORD *)v14 + 11) )
          __int2c();
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        Package = ServiceManager::ShowToast(
                    this,
                    0x6Eu,
                    0x6Fu,
                    &dword_180027ABC,
                    0,
                    0,
                    0,
                    v9,
                    v11,
                    *(_DWORD *)(v10 + 28),
                    a3);
        if ( Package >= 0 )
          return 0;
        v8 = 844;
      }
      else
      {
        v8 = 830;
      }
    }
    else
    {
      v8 = 827;
    }
    return (unsigned int)ZTraceReportPropagation(Package, "ServiceManager::AddPackageWithNotification", v8, this);
  }
  else
  {
    v6 = ZTraceReportPropagation(v5, "ServiceManager::AddPackageWithNotification", 823, this);
    RelockableGate::~RelockableGate((RelockableGate *)v13);
  }
  return v6;
}

```

## disassembly

```asm
0x1800128d0  mov     rax, rsp
0x1800128d3  mov     [rax+18h], rbx
0x1800128d7  mov     [rax+10h], edx
0x1800128da  push    rdi
0x1800128db  sub     rsp, 70h
0x1800128df  mov     edi, r8d
0x1800128e2  mov     rbx, rcx
0x1800128e5  mov     qword ptr [rax+8], 0
0x1800128ed  add     rcx, 0D48h
0x1800128f4  lea     rdx, [rax-18h]
0x1800128f8  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x1800128fd  nop
0x1800128fe  mov     rcx, rbx; this
0x180012901  call    ?WaitForOdmlInit@ServiceManager@@AEAAJXZ; ServiceManager::WaitForOdmlInit(void)
0x180012906  test    eax, eax
0x180012908  jns     short loc_180012933
0x18001290a  mov     r9, rbx
0x18001290d  mov     r8d, 337h
0x180012913  lea     rdx, aServicemanager_70; "ServiceManager::AddPackageWithNotificat"...
0x18001291a  mov     ecx, eax
0x18001291c  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180012922  mov     ebx, eax
0x180012924  lea     rcx, [rsp+78h+var_18]; this
0x180012929  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001292e  jmp     loc_180012A22
0x180012933  lea     rcx, [rsp+78h+var_18]; this
0x180012938  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001293d  mov     r9d, 0Bh
0x180012943  lea     r8, [rsp+78h+arg_8]
0x18001294b  lea     edx, [r9-0Ah]
0x18001294f  mov     rcx, rbx
0x180012952  call    ?AddPackages@ServiceManager@@UEAAJKPEBIW4MapsOperationTrigger@@@Z; ServiceManager::AddPackages(ulong,uint const *,MapsOperationTrigger)
0x180012957  test    eax, eax
0x180012959  jns     short loc_18001297A
0x18001295b  mov     r8d, 33Bh
0x180012961  mov     r9, rbx
0x180012964  lea     rdx, aServicemanager_70; "ServiceManager::AddPackageWithNotificat"...
0x18001296b  mov     ecx, eax
0x18001296d  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180012973  mov     ebx, eax
0x180012975  jmp     loc_180012A22
0x18001297a  lea     rcx, [rbx+0DF0h]; this
0x180012981  lea     r8, [rsp+78h+arg_0]; struct OdmlMapDataPackage **
0x180012989  mov     edx, [rsp+78h+arg_8]; unsigned int
0x180012990  call    ?GetPackage@PackageManager@@QEAAJIPEAPEAVOdmlMapDataPackage@@@Z; PackageManager::GetPackage(uint,OdmlMapDataPackage * *)
0x180012995  test    eax, eax
0x180012997  jns     short loc_1800129A1
0x180012999  mov     r8d, 33Eh
0x18001299f  jmp     short loc_180012961
0x1800129a1  mov     r8, [rsp+78h+arg_0]
0x1800129a9  mov     rcx, [r8+58h]
0x1800129ad  test    rcx, rcx
0x1800129b0  jnz     short loc_1800129B4
0x1800129b2  int     2Ch; Windows NT - assertion failure
0x1800129b4  add     rcx, 38h ; '8'
0x1800129b8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800129bd  mov     rdx, rax
0x1800129c0  lea     rcx, [r8+38h]
0x1800129c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800129c9  mov     [rsp+78h+var_28], edi; unsigned int
0x1800129cd  mov     ecx, [r8+1Ch]
0x1800129d1  mov     [rsp+78h+var_30], ecx; unsigned int
0x1800129d5  mov     [rsp+78h+var_38], rdx; unsigned __int16 *
0x1800129da  mov     [rsp+78h+var_40], rax; unsigned __int16 *
0x1800129df  mov     [rsp+78h+var_48], 0; int
0x1800129e7  mov     [rsp+78h+var_50], 0; unsigned __int64
0x1800129f0  mov     [rsp+78h+var_58], 0; unsigned __int16 *
0x1800129f9  lea     r9, dword_180027ABC; unsigned __int16 *
0x180012a00  mov     edx, 6Eh ; 'n'; unsigned int
0x180012a05  lea     r8d, [rdx+1]; unsigned int
0x180012a09  mov     rcx, rbx; this
0x180012a0c  call    ?ShowToast@ServiceManager@@AEAAJIIPEBG0_KH00KK@Z; ServiceManager::ShowToast(uint,uint,ushort const *,ushort const *,unsigned __int64,int,ushort const *,ushort const *,ulong,ulong)
0x180012a11  test    eax, eax
0x180012a13  jns     short loc_180012A20
0x180012a15  mov     r8d, 34Ch
0x180012a1b  jmp     loc_180012961
0x180012a20  xor     ebx, ebx
0x180012a22  mov     eax, ebx
0x180012a24  mov     rbx, [rsp+78h+arg_10]
0x180012a2c  add     rsp, 70h
0x180012a30  pop     rdi
0x180012a31  retn
```
