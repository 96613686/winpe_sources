# OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed<uint,uint,ulong,int,_FILETIME &,unsigned __int64 &,bool,_STORAGE_DEVICE_TYPE &,ulong &,long &>(uint &&,uint &&,ulong &&,int &&,_FILETIME &,unsigned __int64 &,bool &&,_STORAGE_DEVICE_TYPE &,ulong &,long &)

- ea: `0x1800117f0`
- end: `0x180011896`
- name: `??$OfflineMapCheckForUpdatesFailed@IIKHAEAU_FILETIME@@AEA_K_NAEAW4_STORAGE_DEVICE_TYPE@@AEAKAEAJ@OfflineMapsTelemetry@@SAX$$QEAI0$$QEAK$$QEAHAEAU_FILETIME@@AEA_K$$QEA_NAEAW4_STORAGE_DEVICE_TYPE@@AEAKAEAJ@Z`
- size: `166`
- prototype: `void __fastcall(unsigned int *, unsigned int *, int *, int *, struct _FILETIME *, unsigned __int64 *, bool *, unsigned int *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014744`
- `0x18001cc50`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x1800117f0`
- `0x180019bf4`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed<unsigned int,unsigned int,unsigned long,int,_FILETIME &,unsigned __int64 &,bool,enum _STORAGE_DEVICE_TYPE &,unsigned long &,long &>(
        unsigned int *a1,
        unsigned int *a2,
        int *a3,
        int *a4,
        struct _FILETIME *a5,
        unsigned __int64 *a6,
        bool *a7,
        unsigned int *a8,
        unsigned int *a9,
        int *a10)
{
  OfflineMapsTelemetry *v14; // rax

  if ( OfflineMapsTelemetry::IsEnabled((unsigned __int8)a1, (unsigned __int64)a2) )
  {
    v14 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed_(v14, *a1, *a2, *a3, *a4, *a5, *a6, *a7, *a8, *a9, *a10);
  }
}

```

## disassembly

```asm
0x1800117f0  push    rbx
0x1800117f2  push    rsi
0x1800117f3  push    rdi
0x1800117f4  push    r14
0x1800117f6  push    r15
0x1800117f8  sub     rsp, 60h
0x1800117fc  mov     rdi, r9
0x1800117ff  mov     rsi, r8
0x180011802  mov     r14, rdx
0x180011805  mov     r15, rcx
0x180011808  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001180d  test    al, al
0x18001180f  jz      short loc_18001188A
0x180011811  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180011816  mov     rdx, [rsp+88h+arg_40]
0x18001181e  mov     rbx, rax
0x180011821  mov     rax, [rsp+88h+arg_28]
0x180011829  mov     r11, [rsp+88h+arg_48]
0x180011831  mov     r10, [rsp+88h+arg_20]
0x180011839  mov     ecx, [rdx]
0x18001183b  mov     r8d, [r14]; unsigned int
0x18001183e  mov     r9d, [r11]
0x180011841  mov     r10, [r10]
0x180011844  mov     [rsp+88h+var_38], r9d; int
0x180011849  mov     r9d, [rsi]; int
0x18001184c  mov     [rsp+88h+var_40], ecx; unsigned int
0x180011850  mov     rcx, [rsp+88h+arg_38]
0x180011858  mov     edx, [rcx]
0x18001185a  mov     rcx, [rsp+88h+arg_30]
0x180011862  mov     [rsp+88h+var_48], edx; unsigned int
0x180011866  mov     dl, [rcx]
0x180011868  mov     rcx, [rax]
0x18001186b  mov     eax, [rdi]
0x18001186d  mov     [rsp+88h+var_50], dl; bool
0x180011871  mov     edx, [r15]; unsigned int
0x180011874  mov     [rsp+88h+var_58], rcx; unsigned __int64
0x180011879  mov     rcx, rbx; this
0x18001187c  mov     qword ptr [rsp+88h+var_60.dwLowDateTime], r10; struct _FILETIME
0x180011881  mov     [rsp+88h+var_68], eax; int
0x180011885  call    ?OfflineMapCheckForUpdatesFailed_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NIIJ@Z; OfflineMapsTelemetry::OfflineMapCheckForUpdatesFailed_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint,long)
0x18001188a  add     rsp, 60h
0x18001188e  pop     r15
0x180011890  pop     r14
0x180011892  pop     rdi
0x180011893  pop     rsi
0x180011894  pop     rbx
0x180011895  retn
```
