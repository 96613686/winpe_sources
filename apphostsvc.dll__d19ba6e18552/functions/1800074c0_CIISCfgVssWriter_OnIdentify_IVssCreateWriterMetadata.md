# CIISCfgVssWriter::OnIdentify(IVssCreateWriterMetadata *)

- ea: `0x1800074c0`
- end: `0x180007640`
- name: `?OnIdentify@CIISCfgVssWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z`
- size: `384`
- prototype: `bool(CIISCfgVssWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006ed8`
- `0x1800074c0`
- `0x18000a010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000762e`
- `iisutil!PuDbgPrint` at `0x18000762e`

## string_xrefs

- `0x180007622`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\cfgwriter.cxx`
- `0x1800074c9`: `IISCONFIG`
- `0x180007565`: `IISCONFIG`
- `0x180007537`: `Error AddComponent().  hr = %x\n`
- `0x18000761b`: `CIISCfgVssWriter::OnIdentify`
- `0x180007555`: `%windir%\system32\inetsrv\config`

## pseudocode

```c
char __fastcall CIISCfgVssWriter::OnIdentify(CIISCfgVssWriter *this, struct IVssCreateWriterMetadata *a2)
{
  int v3; // eax
  int v4; // eax
  CIISCfgVssWriter *v5; // rcx
  int v6; // eax
  int v7; // eax
  __int64 v9; // [rsp+28h] [rbp-50h]
  __int64 v10; // [rsp+28h] [rbp-50h]
  char v11; // [rsp+38h] [rbp-40h]
  __int64 v12; // [rsp+38h] [rbp-40h]
  char v13; // [rsp+40h] [rbp-38h]
  char v14; // [rsp+48h] [rbp-30h]
  char v15; // [rsp+50h] [rbp-28h]

  v15 = 0;
  v14 = 0;
  v13 = 0;
  v11 = 0;
  v3 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD, const wchar_t *, _QWORD, _QWORD, _DWORD, char, char, char, char, _DWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         2,
         0,
         L"IISCONFIG",
         0,
         0,
         0,
         v11,
         v13,
         v14,
         v15,
         0);
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v9) = v3;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
        123,
        "CIISCfgVssWriter::OnIdentify",
        "Error AddComponent().  hr = %x\n",
        v9);
    }
    return 0;
  }
  LODWORD(v12) = 3855;
  LOBYTE(v9) = 0;
  v4 = (*(__int64 (**)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, const wchar_t *, ...))(*(_QWORD *)a2 + 40LL))(
         a2,
         0,
         L"IISCONFIG",
         L"%windir%\\system32\\inetsrv\\config",
         L"*",
         v9,
         0,
         v12);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v10) = v4;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
        138,
        "CIISCfgVssWriter::OnIdentify",
        "Error AddFilesToFileGroup().  hr = %x\n",
        v10);
    }
    return 0;
  }
  v6 = CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles(v5, a2);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v10) = v6;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
        151,
        "CIISCfgVssWriter::OnIdentify",
        "Error IdentifyAndDeclareSchemaFiles. hr = %x\n",
        v10);
    }
    return 0;
  }
  v7 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 6, 0);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v10) = v7;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
        167,
        "CIISCfgVssWriter::OnIdentify",
        "Error setting restore method.  hr = %x\n",
        v10);
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800074c0  push    rbx
0x1800074c2  sub     rsp, 70h
0x1800074c6  mov     rax, [rdx]
0x1800074c9  lea     r9, aIisconfig; "IISCONFIG"
0x1800074d0  mov     [rsp+78h+var_20], 0
0x1800074d8  mov     rbx, rdx
0x1800074db  mov     [rsp+78h+var_28], 0
0x1800074e0  xor     r8d, r8d
0x1800074e3  mov     [rsp+78h+var_30], 0
0x1800074e8  mov     rcx, rbx
0x1800074eb  mov     rax, [rax+10h]
0x1800074ef  mov     [rsp+78h+var_38], 0
0x1800074f4  mov     byte ptr [rsp+78h+var_40], 0
0x1800074f9  lea     edx, [r8+2]
0x1800074fd  mov     dword ptr [rsp+78h+var_48], 0
0x180007505  mov     [rsp+78h+var_50], 0
0x18000750e  mov     [rsp+78h+var_58], 0
0x180007517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000751c  test    eax, eax
0x18000751e  jns     short loc_180007543
0x180007520  test    byte ptr cs:g_dwDebugFlags, 3
0x180007527  jz      loc_180007634
0x18000752d  mov     dword ptr [rsp+78h+var_50], eax
0x180007531  mov     r8d, 7Bh ; '{'
0x180007537  lea     rax, aErrorAddcompon; "Error AddComponent().  hr = %x\n"
0x18000753e  jmp     loc_180007614
0x180007543  mov     rax, [rbx]
0x180007546  lea     rcx, asc_18000D3F0; "*"
0x18000754d  mov     dword ptr [rsp+78h+var_40], 0F0Fh
0x180007555  lea     r9, aWindirSystem32_1; "%windir%\\system32\\inetsrv\\config"
0x18000755c  mov     [rsp+78h+var_48], 0
0x180007565  lea     r8, aIisconfig; "IISCONFIG"
0x18000756c  mov     byte ptr [rsp+78h+var_50], 0
0x180007571  xor     edx, edx
0x180007573  mov     rax, [rax+28h]
0x180007577  mov     [rsp+78h+var_58], rcx
0x18000757c  mov     rcx, rbx
0x18000757f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007584  test    eax, eax
0x180007586  jns     short loc_1800075A8
0x180007588  test    byte ptr cs:g_dwDebugFlags, 3
0x18000758f  jz      loc_180007634
0x180007595  mov     dword ptr [rsp+78h+var_50], eax
0x180007599  mov     r8d, 8Ah
0x18000759f  lea     rax, aErrorAddfilest; "Error AddFilesToFileGroup().  hr = %x\n"
0x1800075a6  jmp     short loc_180007614
0x1800075a8  mov     rdx, rbx; struct IVssCreateWriterMetadata *
0x1800075ab  call    ?IdentifyAndDeclareSchemaFiles@CIISCfgVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@@Z; CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles(IVssCreateWriterMetadata *)
0x1800075b0  test    eax, eax
0x1800075b2  jns     short loc_1800075D0
0x1800075b4  test    byte ptr cs:g_dwDebugFlags, 3
0x1800075bb  jz      short loc_180007634
0x1800075bd  mov     dword ptr [rsp+78h+var_50], eax
0x1800075c1  mov     r8d, 97h
0x1800075c7  lea     rax, aErrorIdentifya; "Error IdentifyAndDeclareSchemaFiles. hr"...
0x1800075ce  jmp     short loc_180007614
0x1800075d0  mov     rax, [rbx]
0x1800075d3  xor     r9d, r9d
0x1800075d6  mov     byte ptr [rsp+78h+var_50], 0
0x1800075db  xor     r8d, r8d
0x1800075de  mov     rcx, rbx
0x1800075e1  mov     dword ptr [rsp+78h+var_58], 1
0x1800075e9  mov     rax, [rax+30h]
0x1800075ed  lea     edx, [r9+6]
0x1800075f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075f6  test    eax, eax
0x1800075f8  jns     short loc_180007638
0x1800075fa  test    byte ptr cs:g_dwDebugFlags, 3
0x180007601  jz      short loc_180007634
0x180007603  mov     dword ptr [rsp+78h+var_50], eax
0x180007607  mov     r8d, 0A7h
0x18000760d  lea     rax, aErrorSettingRe; "Error setting restore method.  hr = %x"...
0x180007614  mov     rcx, cs:g_pDebug
0x18000761b  lea     r9, aCiiscfgvsswrit; "CIISCfgVssWriter::OnIdentify"
0x180007622  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007629  mov     [rsp+78h+var_58], rax
0x18000762e  call    cs:__imp_PuDbgPrint
0x180007634  xor     al, al
0x180007636  jmp     short loc_18000763A
0x180007638  mov     al, 1
0x18000763a  add     rsp, 70h
0x18000763e  pop     rbx
0x18000763f  retn
```
