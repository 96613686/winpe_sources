# COMPRESSION_CUSTOM_PROVIDER::GenerateServiceLevelProperties(ABO_NODE *)

- ea: `0x180025e78`
- end: `0x180026159`
- name: `?GenerateServiceLevelProperties@COMPRESSION_CUSTOM_PROVIDER@@QEAAJPEAVABO_NODE@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(COMPRESSION_CUSTOM_PROVIDER *__hidden this, struct ABO_NODE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800259c0`

## callees

- `0x180001f90`
- `0x180002990`
- `0x1800065a8`
- `0x1800077dc`
- `0x18000fa00`
- `0x18000fd48`
- `0x180025e78`
- `0x180026b44`
- `0x180027294`
- `0x18002c010`

## string_xrefs

- `0x180025ecd`: `system.webServer/urlCompression`
- `0x180025f01`: `system.webServer/urlCompression`
- `0x180026035`: `doStaticCompression`
- `0x180025f40`: `doDynamicCompression`
- `0x180025f19`: `Failed to get UrlCompression section.  hr = %08x\n`

## pseudocode

```c
__int64 __fastcall COMPRESSION_CUSTOM_PROVIDER::GenerateServiceLevelProperties(
        COMPRESSION_CUSTOM_PROVIDER *this,
        struct ABO_NODE *a2)
{
  int v3; // ebx
  _QWORD *v4; // r14
  char *v5; // r9
  __int64 v6; // rcx
  int v7; // eax
  ABO_MAPPER_LOG *v8; // rcx
  PROPERTY_ENTRY *v9; // rax
  PROPERTY_ENTRY *v10; // rax
  struct PROPERTY_ENTRY *v11; // rdi
  PROPERTY_ENTRY *v12; // rax
  PROPERTY_ENTRY *v13; // rax
  struct INativeSectionException *v15; // [rsp+30h] [rbp-30h] BYREF
  struct _METADATA_RECORD v16; // [rsp+38h] [rbp-28h] BYREF
  int v17; // [rsp+A8h] [rbp+48h] BYREF
  BOOL v18; // [rsp+B0h] [rbp+50h] BYREF
  struct INativePropertyExtendedInfo *v19; // [rsp+B8h] [rbp+58h] BYREF

  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v4 = (_QWORD *)((char *)this + 32);
  v5 = (char *)this + 32;
  v6 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 176LL) + 32LL);
  v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, char *, struct INativeSectionException **))(*(_QWORD *)v6 + 64LL))(
         v6,
         L"system.webServer/urlCompression",
         L"MACHINE/WEBROOT/APPHOST",
         v5,
         &v15);
  v3 = v7;
  if ( v7 < 0 )
  {
    if ( v15 )
      ABO_MAPPER_LOG::WriteConfigSectionException(
        v8,
        L"system.webServer/urlCompression",
        L"MACHINE/WEBROOT/APPHOST",
        v15);
    else
      ABO_MAPPER_LOG::WriteLogEntry(
        (HANDLE *)g_pAboLog,
        L"Failed to get UrlCompression section.  hr = %08x\n",
        (unsigned int)v7);
LABEL_25:
    if ( v19 )
    {
      (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    goto LABEL_27;
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)*v4 + 72LL))(
         *v4,
         L"doDynamicCompression",
         &v17,
         0,
         &v19);
  if ( v3 < 0 )
    goto LABEL_25;
  if ( (unsigned int)FSetHere(v19) )
  {
    *(_QWORD *)&v16.dwMDDataLen = 4;
    *(_QWORD *)&v16.dwMDDataTag = 0;
    v18 = v17 != 0;
    v16.pbMDData = (unsigned __int8 *)&v18;
    *(_QWORD *)&v16.dwMDIdentifier = 2213;
    v16.dwMDUserType = 1;
    v16.dwMDDataType = 1;
    v9 = (PROPERTY_ENTRY *)operator new(0x50u);
    if ( !v9 )
      goto LABEL_30;
    v10 = PROPERTY_ENTRY::PROPERTY_ENTRY(v9, 1);
    v11 = v10;
    if ( !v10 )
      goto LABEL_30;
    v3 = PROPERTY_ENTRY::Create(v10, &v16);
    if ( v3 < 0 )
      goto LABEL_31;
    v3 = PROPERTY_BAG::AddEntry((struct ABO_NODE *)((char *)a2 + 184), v11, 1);
    if ( v3 < 0 )
      goto LABEL_31;
    PROPERTY_MAPPING::DereferencePropertyMapping(v11);
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)*v4 + 72LL))(
         *v4,
         L"doStaticCompression",
         &v17,
         0,
         &v19);
  if ( v3 < 0 )
    goto LABEL_25;
  if ( (unsigned int)FSetHere(v19) )
  {
    *(_QWORD *)&v16.dwMDDataLen = 4;
    *(_QWORD *)&v16.dwMDDataTag = 0;
    v18 = v17 != 0;
    v16.pbMDData = (unsigned __int8 *)&v18;
    *(_QWORD *)&v16.dwMDIdentifier = 2214;
    v16.dwMDUserType = 1;
    v16.dwMDDataType = 1;
    v12 = (PROPERTY_ENTRY *)operator new(0x50u);
    if ( v12 )
    {
      v13 = PROPERTY_ENTRY::PROPERTY_ENTRY(v12, 1);
      v11 = v13;
      if ( v13 )
      {
        v3 = PROPERTY_ENTRY::Create(v13, &v16);
        if ( v3 >= 0 )
        {
          v3 = PROPERTY_BAG::AddEntry((struct ABO_NODE *)((char *)a2 + 184), v11, 1);
          if ( v3 >= 0 )
          {
            PROPERTY_MAPPING::DereferencePropertyMapping(v11);
            goto LABEL_23;
          }
        }
LABEL_31:
        PROPERTY_MAPPING::DereferencePropertyMapping(v11);
        goto LABEL_25;
      }
    }
LABEL_30:
    v3 = -2147024888;
    goto LABEL_25;
  }
LABEL_23:
  if ( v19 )
  {
    (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
    goto LABEL_25;
  }
LABEL_27:
  if ( v15 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180025e78  push    rbp
0x180025e7a  push    rbx
0x180025e7b  push    rsi
0x180025e7c  push    rdi
0x180025e7d  push    r12
0x180025e7f  push    r14
0x180025e81  push    r15
0x180025e83  mov     rbp, rsp
0x180025e86  sub     rsp, 60h
0x180025e8a  xor     r15d, r15d
0x180025e8d  mov     rsi, rdx
0x180025e90  mov     [rbp+var_30], r15
0x180025e94  mov     rdx, rcx
0x180025e97  mov     [rbp+arg_8], r15d
0x180025e9b  mov     [rbp+arg_10], r15d
0x180025e9f  mov     [rbp+arg_18], r15
0x180025ea3  test    rsi, rsi
0x180025ea6  jnz     short loc_180025EB2
0x180025ea8  mov     ebx, 80070057h
0x180025ead  jmp     loc_180026137
0x180025eb2  mov     rax, [rcx+10h]
0x180025eb6  lea     r14, [rdx+20h]
0x180025eba  lea     rdx, [rbp+var_30]
0x180025ebe  mov     r9, r14
0x180025ec1  mov     [rsp+60h+var_40], rdx
0x180025ec6  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180025ecd  lea     rdx, aSystemWebserve_17; "system.webServer/urlCompression"
0x180025ed4  mov     rcx, [rax+0B0h]
0x180025edb  mov     rcx, [rcx+20h]
0x180025edf  mov     rax, [rcx]
0x180025ee2  mov     rax, [rax+40h]
0x180025ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eeb  mov     ebx, eax
0x180025eed  test    eax, eax
0x180025eef  jns     short loc_180025F2D
0x180025ef1  mov     r9, [rbp+var_30]; struct INativeSectionException *
0x180025ef5  test    r9, r9
0x180025ef8  jz      short loc_180025F12
0x180025efa  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180025f01  lea     rdx, aSystemWebserve_17; "system.webServer/urlCompression"
0x180025f08  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x180025f0d  jmp     loc_180026109
0x180025f12  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180025f19  lea     rdx, aFailedToGetUrl; "Failed to get UrlCompression section.  "...
0x180025f20  mov     r8d, eax
0x180025f23  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180025f28  jmp     loc_180026109
0x180025f2d  mov     rcx, [r14]
0x180025f30  lea     rdx, [rbp+arg_18]
0x180025f34  mov     [rsp+60h+var_40], rdx
0x180025f39  lea     r8, [rbp+arg_8]
0x180025f3d  xor     r9d, r9d
0x180025f40  lea     rdx, aDodynamiccompr; "doDynamicCompression"
0x180025f47  mov     rax, [rcx]
0x180025f4a  mov     rax, [rax+48h]
0x180025f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f53  mov     ebx, eax
0x180025f55  test    eax, eax
0x180025f57  js      loc_180026109
0x180025f5d  mov     rcx, [rbp+arg_18]; struct INativePropertyExtendedInfo *
0x180025f61  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x180025f66  mov     r12d, 1
0x180025f6c  test    eax, eax
0x180025f6e  jz      loc_180026009
0x180025f74  cmp     [rbp+arg_8], r15d
0x180025f78  lea     ecx, [r12+4Fh]; Size
0x180025f7d  mov     eax, r15d
0x180025f80  mov     qword ptr [rbp+var_28.dwMDDataLen], 4
0x180025f88  setnz   al
0x180025f8b  mov     qword ptr [rbp+var_28.dwMDDataTag], r15
0x180025f8f  mov     [rbp+arg_10], eax
0x180025f92  lea     rax, [rbp+arg_10]
0x180025f96  mov     [rbp+var_28.pbMDData], rax
0x180025f9a  mov     qword ptr [rbp+var_28.dwMDIdentifier], 8A5h
0x180025fa2  mov     [rbp+var_28.dwMDUserType], r12d
0x180025fa6  mov     [rbp+var_28.dwMDDataType], r12d
0x180025faa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025faf  test    rax, rax
0x180025fb2  jz      loc_180026148
0x180025fb8  mov     edx, r12d; int
0x180025fbb  mov     rcx, rax; this
0x180025fbe  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x180025fc3  mov     rdi, rax
0x180025fc6  test    rax, rax
0x180025fc9  jz      loc_180026148
0x180025fcf  lea     rdx, [rbp+var_28]; struct _METADATA_RECORD *
0x180025fd3  mov     rcx, rax; this
0x180025fd6  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x180025fdb  mov     ebx, eax
0x180025fdd  test    eax, eax
0x180025fdf  js      loc_18002614F
0x180025fe5  lea     rcx, [rsi+0B8h]; this
0x180025fec  mov     r8d, r12d; int
0x180025fef  mov     rdx, rdi; struct PROPERTY_ENTRY *
0x180025ff2  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x180025ff7  mov     ebx, eax
0x180025ff9  test    eax, eax
0x180025ffb  js      loc_18002614F
0x180026001  mov     rcx, rdi; this
0x180026004  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180026009  mov     rcx, [rbp+arg_18]
0x18002600d  test    rcx, rcx
0x180026010  jz      short loc_180026022
0x180026012  mov     rax, [rcx]
0x180026015  mov     rax, [rax+10h]
0x180026019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002601e  mov     [rbp+arg_18], r15
0x180026022  mov     rcx, [r14]
0x180026025  lea     rdx, [rbp+arg_18]
0x180026029  mov     [rsp+60h+var_40], rdx
0x18002602e  lea     r8, [rbp+arg_8]
0x180026032  xor     r9d, r9d
0x180026035  lea     rdx, aDostaticcompre; "doStaticCompression"
0x18002603c  mov     rax, [rcx]
0x18002603f  mov     rax, [rax+48h]
0x180026043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026048  mov     ebx, eax
0x18002604a  test    eax, eax
0x18002604c  js      loc_180026109
0x180026052  mov     rcx, [rbp+arg_18]; struct INativePropertyExtendedInfo *
0x180026056  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18002605b  test    eax, eax
0x18002605d  jz      loc_1800260F0
0x180026063  cmp     [rbp+arg_8], r15d
0x180026067  mov     eax, r15d
0x18002606a  mov     ecx, 50h ; 'P'; Size
0x18002606f  mov     qword ptr [rbp+var_28.dwMDDataLen], 4
0x180026077  setnz   al
0x18002607a  mov     qword ptr [rbp+var_28.dwMDDataTag], r15
0x18002607e  mov     [rbp+arg_10], eax
0x180026081  lea     rax, [rbp+arg_10]
0x180026085  mov     [rbp+var_28.pbMDData], rax
0x180026089  mov     qword ptr [rbp+var_28.dwMDIdentifier], 8A6h
0x180026091  mov     [rbp+var_28.dwMDUserType], r12d
0x180026095  mov     [rbp+var_28.dwMDDataType], r12d
0x180026099  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002609e  test    rax, rax
0x1800260a1  jz      loc_180026148
0x1800260a7  mov     edx, r12d; int
0x1800260aa  mov     rcx, rax; this
0x1800260ad  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x1800260b2  mov     rdi, rax
0x1800260b5  test    rax, rax
0x1800260b8  jz      loc_180026148
0x1800260be  lea     rdx, [rbp+var_28]; struct _METADATA_RECORD *
0x1800260c2  mov     rcx, rax; this
0x1800260c5  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x1800260ca  mov     ebx, eax
0x1800260cc  test    eax, eax
0x1800260ce  js      short loc_18002614F
0x1800260d0  lea     rcx, [rsi+0B8h]; this
0x1800260d7  mov     r8d, r12d; int
0x1800260da  mov     rdx, rdi; struct PROPERTY_ENTRY *
0x1800260dd  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x1800260e2  mov     ebx, eax
0x1800260e4  test    eax, eax
0x1800260e6  js      short loc_18002614F
0x1800260e8  mov     rcx, rdi; this
0x1800260eb  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x1800260f0  mov     rcx, [rbp+arg_18]
0x1800260f4  test    rcx, rcx
0x1800260f7  jz      short loc_180026122
0x1800260f9  mov     rax, [rcx]
0x1800260fc  mov     rax, [rax+10h]
0x180026100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026105  mov     [rbp+arg_18], r15
0x180026109  mov     rcx, [rbp+arg_18]
0x18002610d  test    rcx, rcx
0x180026110  jz      short loc_180026122
0x180026112  mov     rax, [rcx]
0x180026115  mov     rax, [rax+10h]
0x180026119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002611e  mov     [rbp+arg_18], r15
0x180026122  mov     rcx, [rbp+var_30]
0x180026126  test    rcx, rcx
0x180026129  jz      short loc_180026137
0x18002612b  mov     rax, [rcx]
0x18002612e  mov     rax, [rax+10h]
0x180026132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026137  mov     eax, ebx
0x180026139  add     rsp, 60h
0x18002613d  pop     r15
0x18002613f  pop     r14
0x180026141  pop     r12
0x180026143  pop     rdi
0x180026144  pop     rsi
0x180026145  pop     rbx
0x180026146  pop     rbp
0x180026147  retn
0x180026148  mov     ebx, 80070008h
0x18002614d  jmp     short loc_180026109
0x18002614f  mov     rcx, rdi; this
0x180026152  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180026157  jmp     short loc_180026109
```
