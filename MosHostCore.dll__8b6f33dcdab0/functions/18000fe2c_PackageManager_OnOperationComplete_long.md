# PackageManager::OnOperationComplete(long)

- ea: `0x18000fe2c`
- end: `0x18000fee2`
- name: `?OnOperationComplete@PackageManager@@QEAAJJ@Z`
- size: `182`
- prototype: `__int64 __fastcall(PackageManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001aea4`

## callees

- `0x18000fdec`
- `0x18000fe2c`
- `0x18000ff9c`
- `0x180010278`
- `0x1800109f0`
- `0x1800112b4`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000feba`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000feba`

## string_xrefs

- `0x18000feb1`: `PackageManager::OnOperationComplete`

## pseudocode

```c
__int64 __fastcall PackageManager::OnOperationComplete(PackageManager *this, int a2)
{
  unsigned int v4; // edi
  struct OdmlMapDataPackage ***v5; // rcx
  struct OdmlMapDataPackage *v6; // r14
  wil *v7; // rcx
  int v8; // eax
  __int64 result; // rax
  int v10; // eax
  char v12; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  if ( *((_DWORD *)this + 60) )
  {
    v5 = (struct OdmlMapDataPackage ***)((char *)this + 216);
    v6 = **v5;
    std::vector<OdmlMapDataPackage *>::erase(v5, &v12);
    if ( (*((_BYTE *)v6 + 36) & 2) != 0 )
    {
      try
      {
        PackageManager::OnPackageAddComplete(this, v6, a2);
      }
      catch ( ... )
      {
        v10 = wil::ResultFromCaughtException(v7);
        v4 = ZTraceReportOrigination(v10, "PackageManager::OnOperationComplete", 272, this);
LABEL_8:
        result = v4;
      }
    }
    else if ( (*((_BYTE *)v6 + 36) & 1) != 0 )
    {
      PackageManager::OnPackageDeleteComplete(this, v6, a2);
    }
    *((_DWORD *)this + 60) = 0;
    v8 = PackageManager::SaveQueuedPackages(this, 0);
    if ( v8 < 0 )
    {
      v4 = ZTraceReportPropagation(v8, "PackageManager::OnOperationComplete", 266, this);
      goto LABEL_8;
    }
  }
  PackageManager::InitNextOperation(this);
  goto LABEL_8;
}

```

## disassembly

```asm
0x18000fe2c  mov     [rsp+arg_8], rbx
0x18000fe31  mov     [rsp+arg_0], rcx
0x18000fe36  push    rsi
0x18000fe37  push    rdi
0x18000fe38  push    r14
0x18000fe3a  sub     rsp, 20h
0x18000fe3e  mov     esi, edx
0x18000fe40  mov     rbx, rcx
0x18000fe43  xor     edi, edi
0x18000fe45  cmp     [rcx+0F0h], edi
0x18000fe4b  jz      short loc_18000FEC4
0x18000fe4d  add     rcx, 0D8h
0x18000fe54  mov     r8, [rcx]
0x18000fe57  mov     r14, [r8]
0x18000fe5a  lea     rdx, [rsp+38h+arg_10]
0x18000fe5f  call    ?erase@?$vector@PEAVOdmlMapDataPackage@@V?$allocator@PEAVOdmlMapDataPackage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVOdmlMapDataPackage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAVOdmlMapDataPackage@@@std@@@std@@@2@@Z; std::vector<OdmlMapDataPackage *>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<OdmlMapDataPackage *>>>)
0x18000fe64  test    byte ptr [r14+24h], 2
0x18000fe69  jz      short loc_18000FE7B
0x18000fe6b  mov     r8d, esi; int
0x18000fe6e  mov     rdx, r14; struct OdmlMapDataPackage *
0x18000fe71  mov     rcx, rbx; this
0x18000fe74  call    ?OnPackageAddComplete@PackageManager@@AEAAXPEAVOdmlMapDataPackage@@J@Z; PackageManager::OnPackageAddComplete(OdmlMapDataPackage *,long)
0x18000fe79  jmp     short loc_18000FE90
0x18000fe7b  test    byte ptr [r14+24h], 1
0x18000fe80  jz      short loc_18000FE90
0x18000fe82  mov     r8d, esi; int
0x18000fe85  mov     rdx, r14; struct OdmlMapDataPackage *
0x18000fe88  mov     rcx, rbx; this
0x18000fe8b  call    ?OnPackageDeleteComplete@PackageManager@@AEAAXPEAVOdmlMapDataPackage@@J@Z; PackageManager::OnPackageDeleteComplete(OdmlMapDataPackage *,long)
0x18000fe90  mov     dword ptr [rbx+0F0h], 0
0x18000fe9a  xor     edx, edx
0x18000fe9c  mov     rcx, rbx
0x18000fe9f  call    ?SaveQueuedPackages@PackageManager@@AEAAJW4SaveQueuedPackagesOption@1@@Z; PackageManager::SaveQueuedPackages(PackageManager::SaveQueuedPackagesOption)
0x18000fea4  test    eax, eax
0x18000fea6  jns     short loc_18000FEC4
0x18000fea8  mov     r9, rbx
0x18000feab  mov     r8d, 10Ah
0x18000feb1  lea     rdx, aPackagemanager_12; "PackageManager::OnOperationComplete"
0x18000feb8  mov     ecx, eax
0x18000feba  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000fec0  mov     edi, eax
0x18000fec2  jmp     short loc_18000FED2
0x18000fec4  mov     rcx, rbx; this
0x18000fec7  call    ?InitNextOperation@PackageManager@@AEAAXXZ; PackageManager::InitNextOperation(void)
0x18000fecc  jmp     short loc_18000FED2
0x18000fece  mov     edi, dword ptr [rsp+38h+arg_0]
0x18000fed2  mov     eax, edi
0x18000fed4  mov     rbx, [rsp+38h+arg_8]
0x18000fed9  add     rsp, 20h
0x18000fedd  pop     r14
0x18000fedf  pop     rdi
0x18000fee0  pop     rsi
0x18000fee1  retn
```
