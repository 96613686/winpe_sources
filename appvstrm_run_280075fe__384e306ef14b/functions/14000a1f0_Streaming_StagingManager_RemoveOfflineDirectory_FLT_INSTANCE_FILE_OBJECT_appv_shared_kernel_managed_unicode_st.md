# Streaming::StagingManager::RemoveOfflineDirectory(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &)

- ea: `0x14000a1f0`
- end: `0x14000a308`
- name: `?RemoveOfflineDirectory@StagingManager@Streaming@@CAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000a310`

## callees

- `0x14000279c`
- `0x140003284`
- `0x14000a1f0`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## string_xrefs

- `0x14000a250`: `StagingManager::RemoveOfflineDirectory() - Failed to set extended attributes on file %s with error code 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::StagingManager::RemoveOfflineDirectory(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3)
{
  int v6; // edi
  struct _FILE_OBJECT *v7; // r8
  __int64 v8; // rbx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rbx
  int v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // [rsp+20h] [rbp-58h]
  __int64 v16; // [rsp+20h] [rbp-58h]
  __int64 v17; // [rsp+30h] [rbp-48h] BYREF
  char near **v18; // [rsp+38h] [rbp-40h]
  _BYTE v19[8]; // [rsp+40h] [rbp-38h] BYREF
  volatile signed __int32 *v20; // [rsp+48h] [rbp-30h]

  v17 = 1114128;
  v18 = &strmDirectoryEaName;
  v6 = Streaming::FileOperations::SetEA(Instance, FileObject, (struct _FILE_OBJECT *)&v17, 0, v15);
  if ( v6 >= 0 )
  {
    v13 = Streaming::FileOperations::ChangeFileAttribute(Instance, FileObject, v7, 0, v16);
    v14 = 0;
    if ( v13 < 0 )
      return (unsigned int)v13;
    return v14;
  }
  else
  {
    v8 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v19, a3 + 16);
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v17);
    LODWORD(v16) = v6;
    LogWrite(
      1,
      *CurrentActivityID,
      L"StagingManager::RemoveOfflineDirectory() - Failed to set extended attributes on file %s with error code 0x%08X.",
      v8,
      v16);
    v10 = (volatile signed __int32 *)v18;
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    v11 = v20;
    if ( v20 && _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x14000a1f0  push    rbx
0x14000a1f2  push    rbp
0x14000a1f3  push    rsi
0x14000a1f4  push    rdi
0x14000a1f5  sub     rsp, 58h
0x14000a1f9  mov     rbp, r8
0x14000a1fc  mov     [rsp+78h+var_48], 110010h
0x14000a205  lea     rax, ?strmDirectoryEaName@@3PADA; "appvstrmstagedir"
0x14000a20c  xor     r9d, r9d; struct _STRING *
0x14000a20f  lea     r8, [rsp+78h+var_48]; struct _FILE_OBJECT *
0x14000a214  mov     [rsp+78h+var_40], rax
0x14000a219  mov     rbx, rdx
0x14000a21c  mov     rsi, rcx
0x14000a21f  call    ?SetEA@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEBU_STRING@@K@Z; Streaming::FileOperations::SetEA(_FLT_INSTANCE *,_FILE_OBJECT &,_STRING const &,ulong)
0x14000a224  mov     edi, eax
0x14000a226  test    eax, eax
0x14000a228  jns     loc_14000A2E7
0x14000a22e  lea     rdx, [rbp+10h]
0x14000a232  lea     rcx, [rsp+78h+var_38]
0x14000a237  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000a23c  lea     rcx, [rsp+78h+var_48]
0x14000a241  mov     rbx, [rax]
0x14000a244  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000a249  mov     r9, rbx
0x14000a24c  mov     [rsp+78h+var_58], edi
0x14000a250  lea     r8, aStagingmanager_2; "StagingManager::RemoveOfflineDirectory("...
0x14000a257  mov     ecx, 1
0x14000a25c  mov     rdx, [rax]
0x14000a25f  call    LogWrite
0x14000a264  mov     rbx, [rsp+78h+var_40]
0x14000a269  or      esi, 0FFFFFFFFh
0x14000a26c  test    rbx, rbx
0x14000a26f  jz      short loc_14000A2A5
0x14000a271  mov     eax, esi
0x14000a273  lock xadd [rbx+8], eax
0x14000a278  add     eax, esi
0x14000a27a  jnz     short loc_14000A2A5
0x14000a27c  mov     rax, [rbx]
0x14000a27f  mov     rcx, rbx
0x14000a282  mov     rax, [rax+8]
0x14000a286  call    _guard_dispatch_icall
0x14000a28b  mov     eax, esi
0x14000a28d  lock xadd [rbx+0Ch], eax
0x14000a292  add     eax, esi
0x14000a294  jnz     short loc_14000A2A5
0x14000a296  mov     rax, [rbx]
0x14000a299  mov     rcx, rbx
0x14000a29c  mov     rax, [rax+10h]
0x14000a2a0  call    _guard_dispatch_icall
0x14000a2a5  mov     rbx, [rsp+78h+var_30]
0x14000a2aa  test    rbx, rbx
0x14000a2ad  jz      short loc_14000A2E3
0x14000a2af  mov     eax, esi
0x14000a2b1  lock xadd [rbx+8], eax
0x14000a2b6  add     eax, esi
0x14000a2b8  jnz     short loc_14000A2E3
0x14000a2ba  mov     rax, [rbx]
0x14000a2bd  mov     rcx, rbx
0x14000a2c0  mov     rax, [rax+8]
0x14000a2c4  call    _guard_dispatch_icall
0x14000a2c9  mov     eax, esi
0x14000a2cb  lock xadd [rbx+0Ch], eax
0x14000a2d0  add     eax, esi
0x14000a2d2  jnz     short loc_14000A2E3
0x14000a2d4  mov     rax, [rbx]
0x14000a2d7  mov     rcx, rbx
0x14000a2da  mov     rax, [rax+10h]
0x14000a2de  call    _guard_dispatch_icall
0x14000a2e3  mov     eax, edi
0x14000a2e5  jmp     short loc_14000A2FE
0x14000a2e7  xor     r9d, r9d; unsigned int
0x14000a2ea  mov     rdx, rbx; FileObject
0x14000a2ed  mov     rcx, rsi; Instance
0x14000a2f0  call    ?ChangeFileAttribute@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@KE@Z; Streaming::FileOperations::ChangeFileAttribute(_FLT_INSTANCE *,_FILE_OBJECT &,ulong,uchar)
0x14000a2f5  xor     ecx, ecx
0x14000a2f7  test    eax, eax
0x14000a2f9  cmovs   ecx, eax
0x14000a2fc  mov     eax, ecx
0x14000a2fe  add     rsp, 58h
0x14000a302  pop     rdi
0x14000a303  pop     rsi
0x14000a304  pop     rbp
0x14000a305  pop     rbx
0x14000a306  retn
```
