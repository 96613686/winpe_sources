# File::SaveFileToCache(ConfigSettings const &)

- ea: `0x1800c7f00`
- end: `0x1800c80ac`
- name: `?SaveFileToCache@File@@QEAAXAEBVConfigSettings@@@Z`
- size: `428`
- prototype: `void __fastcall(File *__hidden this, const struct ConfigSettings *)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f378`
- `0x1800c80b4`
- `0x1800c847c`
- `0x1800c8770`
- `0x1800c9400`

## callees

- `0x18000d914`
- `0x180010e84`
- `0x1800295dc`
- `0x1800c7ba4`
- `0x1800c7f00`
- `0x1800c92a0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800c8029`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800c8029`

## string_xrefs

- `0x1800c806f`: `File missing required attribute! GetProgramId:%ls GetFilePath:%ls CommandLine:%ls [%#x]`
- `0x1800c7f9a`: `Failed to add file to the cache: %ws [%#x]`
- `0x1800c7fac`: `File::SaveFileToCache`
- `0x1800c807b`: `File::SaveFileToCache`

## pseudocode

```c
void __fastcall File::SaveFileToCache(File *this, const struct ConfigSettings *a2)
{
  TelCacheProvider *v4; // rcx
  int v5; // edi
  _QWORD *v6; // rax
  __int64 v7; // rax
  _WORD *v8; // rsi
  __int64 v9; // rax
  _WORD *v10; // rdi
  const WCHAR *v11; // rax
  const wchar_t *CommandLineW; // rsi
  __int64 v13; // rax
  const wchar_t *v14; // rdi
  __int64 v15; // rax
  int v16; // [rsp+28h] [rbp-20h]

  if ( File::ShouldCacheFile(this, 0) )
  {
    if ( *(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)this + 112LL))(this) + 16)
      && *(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)this + 24LL))(this) + 16) )
    {
      v4 = (TelCacheProvider *)*((_QWORD *)a2 + 3);
      if ( *((_QWORD *)v4 + 11) )
      {
        v5 = TelCacheProvider::AddItem(
               v4,
               (struct IAmiInventoryItem *)(((unsigned __int64)this + 8)
                                          & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
        if ( v5 < 0 )
        {
          v6 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)this + 16LL))(this);
          if ( v6[3] > 7u )
            v6 = (_QWORD *)*v6;
          v16 = v5;
          AslLogCallPrintf(1, "File::SaveFileToCache", 1462, "Failed to add file to the cache: %ws [%#x]", v6, v16);
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      {
        v7 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)this + 16LL))(this);
        v8 = (_WORD *)v7;
        if ( *(_QWORD *)(v7 + 24) > 7u )
          v8 = *(_WORD **)v7;
        v9 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)this + 112LL))(this);
        v10 = (_WORD *)v9;
        if ( *(_QWORD *)(v9 + 24) > 7u )
          v10 = *(_WORD **)v9;
        v11 = (const WCHAR *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
        File::SaveFileToAeWerCache(v11, v10, v8);
      }
    }
    else
    {
      CommandLineW = GetCommandLineW();
      v13 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)this + 24LL))(this);
      v14 = (const wchar_t *)v13;
      if ( *(_QWORD *)(v13 + 24) > 7u )
        v14 = *(const wchar_t **)v13;
      v15 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)this + 112LL))(this);
      if ( *(_QWORD *)(v15 + 24) > 7u )
        v15 = *(_QWORD *)v15;
      AslLogCallPrintf(
        1,
        "File::SaveFileToCache",
        1453,
        "File missing required attribute! GetProgramId:%ls GetFilePath:%ls CommandLine:%ls [%#x]",
        (const wchar_t *)v15,
        v14,
        CommandLineW,
        -2147467259);
    }
  }
}

```

## disassembly

```asm
0x1800c7f00  mov     [rsp+arg_0], rbx
0x1800c7f05  mov     [rsp+arg_8], rsi
0x1800c7f0a  push    rdi
0x1800c7f0b  sub     rsp, 40h
0x1800c7f0f  mov     rdi, rdx
0x1800c7f12  mov     rbx, rcx
0x1800c7f15  xor     edx, edx; bool
0x1800c7f17  call    ?ShouldCacheFile@File@@IEBA_N_N@Z; File::ShouldCacheFile(bool)
0x1800c7f1c  xor     esi, esi
0x1800c7f1e  test    al, al
0x1800c7f20  jz      loc_1800C809C
0x1800c7f26  mov     rax, [rbx]
0x1800c7f29  mov     rcx, rbx
0x1800c7f2c  mov     rax, [rax+70h]
0x1800c7f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f35  cmp     [rax+10h], rsi
0x1800c7f39  jz      loc_1800C8029
0x1800c7f3f  mov     rax, [rbx]
0x1800c7f42  mov     rcx, rbx
0x1800c7f45  mov     rax, [rax+18h]
0x1800c7f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f4e  cmp     [rax+10h], rsi
0x1800c7f52  jz      loc_1800C8029
0x1800c7f58  mov     rcx, [rdi+18h]; this
0x1800c7f5c  cmp     [rcx+58h], rsi
0x1800c7f60  jz      short loc_1800C7FBD
0x1800c7f62  lea     r8, [rbx+8]
0x1800c7f66  mov     rax, rbx
0x1800c7f69  neg     rax
0x1800c7f6c  sbb     rdx, rdx
0x1800c7f6f  and     rdx, r8; struct IAmiInventoryItem *
0x1800c7f72  call    ?AddItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::AddItem(IAmiInventoryItem *)
0x1800c7f77  mov     edi, eax
0x1800c7f79  test    eax, eax
0x1800c7f7b  jns     short loc_1800C7FBD
0x1800c7f7d  mov     rcx, [rbx]
0x1800c7f80  mov     rax, [rcx+10h]
0x1800c7f84  mov     rcx, rbx
0x1800c7f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7f8c  cmp     qword ptr [rax+18h], 7
0x1800c7f91  jbe     short loc_1800C7F96
0x1800c7f93  mov     rax, [rax]
0x1800c7f96  mov     dword ptr [rsp+48h+var_20], edi
0x1800c7f9a  lea     r9, aFailedToAddFil; "Failed to add file to the cache: %ws [%"...
0x1800c7fa1  mov     r8d, 5B6h
0x1800c7fa7  mov     [rsp+48h+var_28], rax
0x1800c7fac  lea     rdx, aFileSavefileto; "File::SaveFileToCache"
0x1800c7fb3  mov     ecx, 1
0x1800c7fb8  call    AslLogCallPrintf
0x1800c7fbd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800c7fc4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800c7fc9  test    al, al
0x1800c7fcb  jz      loc_1800C809C
0x1800c7fd1  mov     rax, [rbx]
0x1800c7fd4  mov     rcx, rbx
0x1800c7fd7  mov     rax, [rax+10h]
0x1800c7fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7fe0  mov     rsi, rax
0x1800c7fe3  cmp     qword ptr [rax+18h], 7
0x1800c7fe8  jbe     short loc_1800C7FED
0x1800c7fea  mov     rsi, [rax]
0x1800c7fed  mov     rax, [rbx]
0x1800c7ff0  mov     rcx, rbx
0x1800c7ff3  mov     rax, [rax+70h]
0x1800c7ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7ffc  mov     rdi, rax
0x1800c7fff  cmp     qword ptr [rax+18h], 7
0x1800c8004  jbe     short loc_1800C8009
0x1800c8006  mov     rdi, [rax]
0x1800c8009  lea     rcx, [rbx+8]
0x1800c800d  mov     rax, [rcx]
0x1800c8010  mov     rax, [rax+8]
0x1800c8014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8019  mov     r8, rsi; LPCVOID
0x1800c801c  mov     rdx, rdi; lpData
0x1800c801f  mov     rcx, rax; lpSubKey
0x1800c8022  call    ?SaveFileToAeWerCache@File@@CAXPEBG00@Z; File::SaveFileToAeWerCache(ushort const *,ushort const *,ushort const *)
0x1800c8027  jmp     short loc_1800C809C
0x1800c8029  call    cs:__imp_GetCommandLineW
0x1800c802f  mov     rcx, [rbx]
0x1800c8032  mov     rsi, rax
0x1800c8035  mov     rax, [rcx+18h]
0x1800c8039  mov     rcx, rbx
0x1800c803c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8041  mov     rdi, rax
0x1800c8044  cmp     qword ptr [rax+18h], 7
0x1800c8049  jbe     short loc_1800C804E
0x1800c804b  mov     rdi, [rax]
0x1800c804e  mov     rax, [rbx]
0x1800c8051  mov     rcx, rbx
0x1800c8054  mov     rax, [rax+70h]
0x1800c8058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c805d  cmp     qword ptr [rax+18h], 7
0x1800c8062  jbe     short loc_1800C8067
0x1800c8064  mov     rax, [rax]
0x1800c8067  mov     [rsp+48h+var_10], 80004005h
0x1800c806f  lea     r9, aFileMissingReq; "File missing required attribute! GetPro"...
0x1800c8076  mov     [rsp+48h+var_18], rsi
0x1800c807b  lea     rdx, aFileSavefileto; "File::SaveFileToCache"
0x1800c8082  mov     [rsp+48h+var_20], rdi
0x1800c8087  mov     r8d, 5ADh
0x1800c808d  mov     ecx, 1
0x1800c8092  mov     [rsp+48h+var_28], rax
0x1800c8097  call    AslLogCallPrintf
0x1800c809c  mov     rbx, [rsp+48h+arg_0]
0x1800c80a1  mov     rsi, [rsp+48h+arg_8]
0x1800c80a6  add     rsp, 40h
0x1800c80aa  pop     rdi
0x1800c80ab  retn
```
