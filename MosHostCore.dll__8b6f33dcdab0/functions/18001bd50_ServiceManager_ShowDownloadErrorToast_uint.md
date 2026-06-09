# ServiceManager::ShowDownloadErrorToast(uint)

- ea: `0x18001bd50`
- end: `0x18001be1c`
- name: `?ShowDownloadErrorToast@ServiceManager@@AEAAJI@Z`
- size: `204`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800142c4`

## callees

- `0x180008110`
- `0x18000f9b4`
- `0x18001bd50`
- `0x18001be24`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001bd8e`

## string_xrefs

- `0x18001bd80`: `ServiceManager::ShowDownloadErrorToast`

## pseudocode

```c
int __fastcall ServiceManager::ShowDownloadErrorToast(ServiceManager *this, unsigned int a2)
{
  int Package; // eax
  int v4; // r8d
  unsigned __int16 *v6; // rax
  struct OdmlMapDataPackage *v7; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  Package = PackageManager::GetPackage((ServiceManager *)((char *)this + 3568), a2, &v7);
  if ( Package < 0 )
  {
    v4 = 859;
    return ZTraceReportPropagation(Package, "ServiceManager::ShowDownloadErrorToast", v4, this);
  }
  if ( *((_DWORD *)v7 + 10) == 11 )
  {
    v6 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    Package = ServiceManager::ShowToast(
                this,
                112,
                113,
                (SAFEARRAY *)L"MapsDownloadErr",
                L"LastAPIDownloadErrorNotification",
                0x861C46800uLL,
                0,
                v6,
                (unsigned __int16 *)&dword_180027ABC,
                0,
                0);
    if ( Package < 0 )
    {
      v4 = 873;
      return ZTraceReportPropagation(Package, "ServiceManager::ShowDownloadErrorToast", v4, this);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001bd50  push    rbx
0x18001bd52  sub     rsp, 60h
0x18001bd56  mov     rbx, rcx
0x18001bd59  mov     [rsp+68h+arg_0], 0
0x18001bd62  add     rcx, 0DF0h; this
0x18001bd69  lea     r8, [rsp+68h+arg_0]; struct OdmlMapDataPackage **
0x18001bd6e  call    ?GetPackage@PackageManager@@QEAAJIPEAPEAVOdmlMapDataPackage@@@Z; PackageManager::GetPackage(uint,OdmlMapDataPackage * *)
0x18001bd73  test    eax, eax
0x18001bd75  jns     short loc_18001BD95
0x18001bd77  mov     r8d, 35Bh
0x18001bd7d  mov     r9, rbx
0x18001bd80  lea     rdx, aServicemanager_55; "ServiceManager::ShowDownloadErrorToast"
0x18001bd87  mov     ecx, eax
0x18001bd89  add     rsp, 60h
0x18001bd8d  pop     rbx
0x18001bd8e  jmp     cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001bd95  mov     rcx, [rsp+68h+arg_0]
0x18001bd9a  cmp     dword ptr [rcx+28h], 0Bh
0x18001bd9e  jnz     short loc_18001BE14
0x18001bda0  add     rcx, 38h ; '8'
0x18001bda4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bda9  mov     [rsp+68h+var_18], 0; unsigned int
0x18001bdb1  lea     rcx, dword_180027ABC
0x18001bdb8  mov     [rsp+68h+var_20], 0; unsigned int
0x18001bdc0  lea     r9, aMapsdownloader; "MapsDownloadErr"
0x18001bdc7  mov     [rsp+68h+var_28], rcx; unsigned __int16 *
0x18001bdcc  mov     edx, 70h ; 'p'; unsigned int
0x18001bdd1  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x18001bdd6  mov     rcx, rbx; this
0x18001bdd9  mov     rax, 861C46800h
0x18001bde3  mov     [rsp+68h+var_38], 0; int
0x18001bdeb  mov     [rsp+68h+var_40], rax; unsigned __int64
0x18001bdf0  lea     rax, aLastapidownloa; "LastAPIDownloadErrorNotification"
0x18001bdf7  lea     r8d, [rdx+1]; unsigned int
0x18001bdfb  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001be00  call    ?ShowToast@ServiceManager@@AEAAJIIPEBG0_KH00KK@Z; ServiceManager::ShowToast(uint,uint,ushort const *,ushort const *,unsigned __int64,int,ushort const *,ushort const *,ulong,ulong)
0x18001be05  test    eax, eax
0x18001be07  jns     short loc_18001BE14
0x18001be09  mov     r8d, 369h
0x18001be0f  jmp     loc_18001BD7D
0x18001be14  xor     eax, eax
0x18001be16  add     rsp, 60h
0x18001be1a  pop     rbx
0x18001be1b  retn
```
