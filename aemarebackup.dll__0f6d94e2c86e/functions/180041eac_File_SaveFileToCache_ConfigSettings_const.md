# File::SaveFileToCache(ConfigSettings const &)

- ea: `0x180041eac`
- end: `0x180042058`
- name: `?SaveFileToCache@File@@QEAAXAEBVConfigSettings@@@Z`
- size: `428`
- prototype: `void __fastcall(File *__hidden this, const struct ConfigSettings *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042170`

## callees

- `0x180015b48`
- `0x18002772c`
- `0x180041b28`
- `0x180041eac`
- `0x180042a00`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180041fd5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180041fd5`

## string_xrefs

- `0x18004201b`: `File missing required attribute! GetProgramId:%ls GetFilePath:%ls CommandLine:%ls [%#x]`
- `0x180041f58`: `File::SaveFileToCache`
- `0x180042027`: `File::SaveFileToCache`
- `0x180041f46`: `Failed to add file to the cache: %ws [%#x]`

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
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
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
0x180041eac  mov     [rsp+arg_0], rbx
0x180041eb1  mov     [rsp+arg_8], rsi
0x180041eb6  push    rdi
0x180041eb7  sub     rsp, 40h
0x180041ebb  mov     rdi, rdx
0x180041ebe  mov     rbx, rcx
0x180041ec1  xor     edx, edx; bool
0x180041ec3  call    ?ShouldCacheFile@File@@IEBA_N_N@Z; File::ShouldCacheFile(bool)
0x180041ec8  xor     esi, esi
0x180041eca  test    al, al
0x180041ecc  jz      loc_180042048
0x180041ed2  mov     rax, [rbx]
0x180041ed5  mov     rcx, rbx
0x180041ed8  mov     rax, [rax+70h]
0x180041edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ee1  cmp     [rax+10h], rsi
0x180041ee5  jz      loc_180041FD5
0x180041eeb  mov     rax, [rbx]
0x180041eee  mov     rcx, rbx
0x180041ef1  mov     rax, [rax+18h]
0x180041ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041efa  cmp     [rax+10h], rsi
0x180041efe  jz      loc_180041FD5
0x180041f04  mov     rcx, [rdi+18h]; this
0x180041f08  cmp     [rcx+58h], rsi
0x180041f0c  jz      short loc_180041F69
0x180041f0e  lea     r8, [rbx+8]
0x180041f12  mov     rax, rbx
0x180041f15  neg     rax
0x180041f18  sbb     rdx, rdx
0x180041f1b  and     rdx, r8; struct IAmiInventoryItem *
0x180041f1e  call    ?AddItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::AddItem(IAmiInventoryItem *)
0x180041f23  mov     edi, eax
0x180041f25  test    eax, eax
0x180041f27  jns     short loc_180041F69
0x180041f29  mov     rcx, [rbx]
0x180041f2c  mov     rax, [rcx+10h]
0x180041f30  mov     rcx, rbx
0x180041f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f38  cmp     qword ptr [rax+18h], 7
0x180041f3d  jbe     short loc_180041F42
0x180041f3f  mov     rax, [rax]
0x180041f42  mov     dword ptr [rsp+48h+var_20], edi
0x180041f46  lea     r9, aFailedToAddFil; "Failed to add file to the cache: %ws [%"...
0x180041f4d  mov     r8d, 5B6h
0x180041f53  mov     [rsp+48h+var_28], rax
0x180041f58  lea     rdx, aFileSavefileto; "File::SaveFileToCache"
0x180041f5f  mov     ecx, 1
0x180041f64  call    AslLogCallPrintf
0x180041f69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180041f70  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180041f75  test    al, al
0x180041f77  jz      loc_180042048
0x180041f7d  mov     rax, [rbx]
0x180041f80  mov     rcx, rbx
0x180041f83  mov     rax, [rax+10h]
0x180041f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f8c  mov     rsi, rax
0x180041f8f  cmp     qword ptr [rax+18h], 7
0x180041f94  jbe     short loc_180041F99
0x180041f96  mov     rsi, [rax]
0x180041f99  mov     rax, [rbx]
0x180041f9c  mov     rcx, rbx
0x180041f9f  mov     rax, [rax+70h]
0x180041fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fa8  mov     rdi, rax
0x180041fab  cmp     qword ptr [rax+18h], 7
0x180041fb0  jbe     short loc_180041FB5
0x180041fb2  mov     rdi, [rax]
0x180041fb5  lea     rcx, [rbx+8]
0x180041fb9  mov     rax, [rcx]
0x180041fbc  mov     rax, [rax+8]
0x180041fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fc5  mov     r8, rsi; LPCVOID
0x180041fc8  mov     rdx, rdi; lpData
0x180041fcb  mov     rcx, rax; lpSubKey
0x180041fce  call    ?SaveFileToAeWerCache@File@@CAXPEBG00@Z; File::SaveFileToAeWerCache(ushort const *,ushort const *,ushort const *)
0x180041fd3  jmp     short loc_180042048
0x180041fd5  call    cs:__imp_GetCommandLineW
0x180041fdb  mov     rcx, [rbx]
0x180041fde  mov     rsi, rax
0x180041fe1  mov     rax, [rcx+18h]
0x180041fe5  mov     rcx, rbx
0x180041fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fed  mov     rdi, rax
0x180041ff0  cmp     qword ptr [rax+18h], 7
0x180041ff5  jbe     short loc_180041FFA
0x180041ff7  mov     rdi, [rax]
0x180041ffa  mov     rax, [rbx]
0x180041ffd  mov     rcx, rbx
0x180042000  mov     rax, [rax+70h]
0x180042004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042009  cmp     qword ptr [rax+18h], 7
0x18004200e  jbe     short loc_180042013
0x180042010  mov     rax, [rax]
0x180042013  mov     [rsp+48h+var_10], 80004005h
0x18004201b  lea     r9, aFileMissingReq; "File missing required attribute! GetPro"...
0x180042022  mov     [rsp+48h+var_18], rsi
0x180042027  lea     rdx, aFileSavefileto; "File::SaveFileToCache"
0x18004202e  mov     [rsp+48h+var_20], rdi
0x180042033  mov     r8d, 5ADh
0x180042039  mov     ecx, 1
0x18004203e  mov     [rsp+48h+var_28], rax
0x180042043  call    AslLogCallPrintf
0x180042048  mov     rbx, [rsp+48h+arg_0]
0x18004204d  mov     rsi, [rsp+48h+arg_8]
0x180042052  add     rsp, 40h
0x180042056  pop     rdi
0x180042057  retn
```
