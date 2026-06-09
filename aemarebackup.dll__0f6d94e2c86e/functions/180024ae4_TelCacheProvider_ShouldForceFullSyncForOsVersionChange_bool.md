# TelCacheProvider::ShouldForceFullSyncForOsVersionChange(bool)

- ea: `0x180024ae4`
- end: `0x180024c48`
- name: `?ShouldForceFullSyncForOsVersionChange@TelCacheProvider@@AEAAH_N@Z`
- size: `356`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180024458`

## callees

- `0x180004ea0`
- `0x180024ae4`
- `0x1800266b8`
- `0x18004c020`
- `0x1800ec010`

## string_xrefs

- `0x180024c0f`: `Full sync may be needed because of OS upgrade/rollback`
- `0x180024b52`: `TelCacheProvider::ShouldForceFullSyncForOsVersionChange`
- `0x180024bb0`: `TelCacheProvider::ShouldForceFullSyncForOsVersionChange`
- `0x180024c1c`: `TelCacheProvider::ShouldForceFullSyncForOsVersionChange`
- `0x180024b9f`: `InventoryCache::GetMetadata failed [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::ShouldForceFullSyncForOsVersionChange(TelCacheProvider *this, unsigned __int8 a2)
{
  unsigned int v2; // esi
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // edi
  int v7; // eax
  wchar_t *v8; // rax
  int v9; // edx
  int v10; // r8d
  int v12; // [rsp+30h] [rbp-78h] BYREF
  wchar_t Buffer[8]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v14; // [rsp+48h] [rbp-60h]
  _OWORD v15[2]; // [rsp+58h] [rbp-50h] BYREF

  v2 = a2;
  v12 = 16;
  *(_OWORD *)Buffer = 0;
  v14 = 0;
  memset(v15, 0, sizeof(v15));
  v4 = VersionSPrintfW(Buffer, 0x10u, 9u, L"%M.%m.%b");
  if ( v4 < 0 )
  {
    AslLogCallPrintf(
      1,
      "TelCacheProvider::ShouldForceFullSyncForOsVersionChange",
      2174,
      "VersionSPrintf failed [%#x]",
      v4);
    return 0;
  }
  v5 = 0;
  v6 = v2;
  if ( (_BYTE)v2 )
  {
LABEL_11:
    if ( !v6 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _OWORD *, int *))(**((_QWORD **)this + 11) + 56LL))(
         *((_QWORD *)this + 11),
         L"OsVersion",
         v15,
         &v12);
  if ( v7 != -2147024894 )
  {
    if ( v7 >= 0 )
    {
      v8 = Buffer;
      do
      {
        v9 = *(wchar_t *)((char *)v8 + (char *)v15 - (char *)Buffer);
        v10 = *v8 - v9;
        if ( v10 )
          break;
        ++v8;
      }
      while ( v9 );
      LOBYTE(v5) = v10 != 0;
      v6 = v5;
    }
    else
    {
      AslLogCallPrintf(
        1,
        "TelCacheProvider::ShouldForceFullSyncForOsVersionChange",
        2191,
        "InventoryCache::GetMetadata failed [%#x]",
        v7);
    }
    goto LABEL_11;
  }
LABEL_12:
  (*(void (__fastcall **)(_QWORD, const wchar_t *, wchar_t *))(**((_QWORD **)this + 11) + 80LL))(
    *((_QWORD *)this + 11),
    L"OsVersion",
    Buffer);
LABEL_13:
  if ( v5 )
    AslLogCallPrintf(
      3,
      "TelCacheProvider::ShouldForceFullSyncForOsVersionChange",
      2209,
      "Full sync may be needed because of OS upgrade/rollback");
  return v5;
}

```

## disassembly

```asm
0x180024ae4  push    rbx
0x180024ae6  push    rbp
0x180024ae7  push    rsi
0x180024ae8  push    rdi
0x180024ae9  sub     rsp, 88h
0x180024af0  mov     rax, cs:__security_cookie
0x180024af7  xor     rax, rsp
0x180024afa  mov     [rsp+0A8h+var_30], rax
0x180024aff  xorps   xmm0, xmm0
0x180024b02  movzx   esi, dl
0x180024b05  mov     edx, 10h; unsigned __int64
0x180024b0a  lea     r9, aMMB; "%M.%m.%b"
0x180024b11  xorps   xmm1, xmm1
0x180024b14  mov     [rsp+0A8h+var_78], edx
0x180024b18  mov     rbp, rcx
0x180024b1b  lea     rcx, [rsp+0A8h+Buffer]; Buffer
0x180024b20  movups  xmmword ptr [rsp+0A8h+Buffer], xmm0
0x180024b25  lea     r8d, [rdx-7]; unsigned __int64
0x180024b29  movups  [rsp+0A8h+var_60], xmm0
0x180024b2e  movups  [rsp+0A8h+var_50], xmm1
0x180024b33  movups  [rsp+0A8h+var_40], xmm1
0x180024b38  call    ?VersionSPrintfW@@YAJPEAG_K1PEBGZZ; VersionSPrintfW(ushort *,unsigned __int64,unsigned __int64,ushort const *,...)
0x180024b3d  test    eax, eax
0x180024b3f  jns     short loc_180024B6A
0x180024b41  lea     r9, aVersionsprintf; "VersionSPrintf failed [%#x]"
0x180024b48  mov     [rsp+0A8h+var_88], eax
0x180024b4c  mov     r8d, 87Eh
0x180024b52  lea     rdx, aTelcacheprovid_21; "TelCacheProvider::ShouldForceFullSyncFo"...
0x180024b59  mov     ecx, 1
0x180024b5e  call    AslLogCallPrintf
0x180024b63  xor     ebx, ebx
0x180024b65  jmp     loc_180024C2D
0x180024b6a  xor     ebx, ebx
0x180024b6c  mov     edi, esi
0x180024b6e  test    sil, sil
0x180024b71  jnz     short loc_180024BEB
0x180024b73  mov     rcx, [rbp+58h]
0x180024b77  lea     r9, [rsp+0A8h+var_78]
0x180024b7c  lea     r8, [rsp+0A8h+var_50]
0x180024b81  lea     rdx, aOsversion; "OsVersion"
0x180024b88  mov     rax, [rcx]
0x180024b8b  mov     rax, [rax+38h]
0x180024b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b94  cmp     eax, 80070002h
0x180024b99  jz      short loc_180024BEF
0x180024b9b  test    eax, eax
0x180024b9d  jns     short loc_180024BC1
0x180024b9f  lea     r9, aInventorycache_3; "InventoryCache::GetMetadata failed [%#x"...
0x180024ba6  mov     [rsp+0A8h+var_88], eax
0x180024baa  mov     r8d, 88Fh
0x180024bb0  lea     rdx, aTelcacheprovid_21; "TelCacheProvider::ShouldForceFullSyncFo"...
0x180024bb7  lea     ecx, [rbx+1]
0x180024bba  call    AslLogCallPrintf
0x180024bbf  jmp     short loc_180024BEB
0x180024bc1  lea     rax, [rsp+0A8h+Buffer]
0x180024bc6  lea     rcx, [rsp+0A8h+var_50]
0x180024bcb  sub     rcx, rax
0x180024bce  movzx   r8d, word ptr [rax]
0x180024bd2  movzx   edx, word ptr [rax+rcx]
0x180024bd6  sub     r8d, edx
0x180024bd9  jnz     short loc_180024BE3
0x180024bdb  add     rax, 2
0x180024bdf  test    edx, edx
0x180024be1  jnz     short loc_180024BCE
0x180024be3  test    r8d, r8d
0x180024be6  setnz   bl
0x180024be9  mov     edi, ebx
0x180024beb  test    edi, edi
0x180024bed  jz      short loc_180024C0B
0x180024bef  mov     rcx, [rbp+58h]
0x180024bf3  lea     r8, [rsp+0A8h+Buffer]
0x180024bf8  lea     rdx, aOsversion; "OsVersion"
0x180024bff  mov     rax, [rcx]
0x180024c02  mov     rax, [rax+50h]
0x180024c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c0b  test    ebx, ebx
0x180024c0d  jz      short loc_180024C2D
0x180024c0f  lea     r9, aFullSyncMayBeN_0; "Full sync may be needed because of OS u"...
0x180024c16  mov     r8d, 8A1h
0x180024c1c  lea     rdx, aTelcacheprovid_21; "TelCacheProvider::ShouldForceFullSyncFo"...
0x180024c23  mov     ecx, 3
0x180024c28  call    AslLogCallPrintf
0x180024c2d  mov     eax, ebx
0x180024c2f  mov     rcx, [rsp+0A8h+var_30]
0x180024c34  xor     rcx, rsp; StackCookie
0x180024c37  call    __security_check_cookie
0x180024c3c  add     rsp, 88h
0x180024c43  pop     rdi
0x180024c44  pop     rsi
0x180024c45  pop     rbp
0x180024c46  pop     rbx
0x180024c47  retn
```
