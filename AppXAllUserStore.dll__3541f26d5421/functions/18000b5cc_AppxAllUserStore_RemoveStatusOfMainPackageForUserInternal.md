# AppxAllUserStore::RemoveStatusOfMainPackageForUserInternal

- ea: `0x18000b5cc`
- end: `0x18000b873`
- name: `AppxAllUserStore::RemoveStatusOfMainPackageForUserInternal`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001eaa8`

## callees

- `0x180004920`
- `0x180004968`
- `0x180007860`
- `0x180007a10`
- `0x180007a30`
- `0x1800092c0`
- `0x18000a170`
- `0x18000b5cc`
- `0x18000ce40`
- `0x180018248`
- `0x18001a604`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000b7b4`
- `ntdll!RtlFreeHeap` at `0x18000b7b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b780`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b780`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000b674`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000b674`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b6e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b6e1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b792`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000b792`

## string_xrefs

- `0x18000b7d5`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::RemoveStatusOfMainPackageForUserInternal(
        Common::RegistryKey *a1,
        const unsigned __int16 *a2,
        const WCHAR *a3)
{
  int v4; // eax
  signed int v5; // ebx
  DWORD v6; // r15d
  int v7; // esi
  WCHAR *v8; // rdi
  DWORD v9; // r14d
  int v10; // eax
  LSTATUS v11; // eax
  unsigned __int16 **v12; // r9
  LSTATUS InfoKeyW; // eax
  int v14; // eax
  signed int v15; // eax
  DWORD v16; // r14d
  void *v17; // rbx
  unsigned int v18; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  unsigned int v21; // esi
  int lpReserved; // [rsp+20h] [rbp-59h]
  int lpReserveda; // [rsp+20h] [rbp-59h]
  int lpReservedb; // [rsp+20h] [rbp-59h]
  unsigned int lpReservedc; // [rsp+20h] [rbp-59h]
  DWORD cbMaxSubKeyLen[2]; // [rsp+60h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  LPWSTR lpName[2]; // [rsp+70h] [rbp-9h] BYREF
  int v30; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD cchName; // [rsp+F8h] [rbp+7Fh] BYREF

  hKey = 0;
  v4 = Common::RegistryKey::OpenSubKey(a1, a2, 0x2001Fu, (struct Common::AutoHandleHKEY *)&hKey);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v30 = 0;
    *(_OWORD *)lpName = 0;
    v6 = 0;
    v7 = 0;
LABEL_4:
    v8 = lpName[1];
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v8 )
        {
          v10 = 0;
          if ( v7 )
            v10 = v7 - 1;
          v9 = v10 + 1;
        }
        else
        {
          v9 = 0;
        }
        cchName = v9;
        v11 = RegEnumKeyExW(hKey, v6, v8, &cchName, 0, 0, 0, 0);
        v5 = v11;
        if ( v11 > 0 )
          v5 = (unsigned __int16)v11 | 0x80070000;
        if ( v5 >= 0 && cchName <= v9 )
        {
          v15 = Common::StringBuffer::SetLength((Common::StringBuffer *)lpName, cchName);
          v7 = v30;
          v5 = v15;
          v8 = lpName[1];
        }
        else if ( v5 == -2147024662 )
        {
          cbMaxSubKeyLen[0] = 0;
          InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
          v5 = InfoKeyW;
          if ( InfoKeyW > 0 )
            v5 = (unsigned __int16)InfoKeyW | 0x80070000;
          if ( v5 < 0 )
          {
            v19 = (unsigned int)v5;
            v20 = 1155;
          }
          else
          {
            v14 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)lpName, cbMaxSubKeyLen[0]);
            v5 = v14;
            if ( v14 >= 0 )
            {
              v7 = v30;
              goto LABEL_4;
            }
            v19 = (unsigned int)v14;
            v20 = 1157;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
            (const char *)v19,
            lpReservedb);
LABEL_32:
          if ( v5 == -2147024637 )
          {
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpName);
            v5 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF1F,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
              (const char *)(unsigned int)v5,
              lpReserveda);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpName);
          }
          goto LABEL_38;
        }
        if ( v5 < 0 )
          goto LABEL_32;
        v16 = v6;
        *(_QWORD *)cbMaxSubKeyLen = 0;
        cchName = 0;
        ++v6;
        if ( (int)AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(
                    v8,
                    (unsigned __int16 *)&cchName,
                    cbMaxSubKeyLen,
                    v12) >= 0 )
          break;
        Common::GlobalHeap::Free(*(void **)cbMaxSubKeyLen);
      }
      v17 = *(void **)cbMaxSubKeyLen;
      if ( CompareStringOrdinal(*(LPCWCH *)cbMaxSubKeyLen, -1, a3, -1, 1) == 2 )
      {
        v18 = RegDeleteTreeW(hKey, v8);
        if ( v18 )
        {
          v21 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xF19,
                  (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
                  (const char *)v18,
                  lpReservedc);
          Common::GlobalHeap::Free(v17);
          if ( v8 )
            Common::GlobalHeap::Free(v8);
          Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
          return v21;
        }
        v6 = v16;
      }
      if ( v17 )
        RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v17);
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF04,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
    (const char *)(unsigned int)v4,
    lpReserved);
LABEL_38:
  Common::RegistryKey::~RegistryKey(&hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b5cc  push    rbp
0x18000b5ce  push    rbx
0x18000b5cf  push    rsi
0x18000b5d0  push    rdi
0x18000b5d1  push    r12
0x18000b5d3  push    r13
0x18000b5d5  push    r14
0x18000b5d7  push    r15
0x18000b5d9  lea     rbp, [rsp-1Fh]
0x18000b5de  sub     rsp, 98h
0x18000b5e5  mov     r12, r8
0x18000b5e8  lea     r9, [rbp+57h+hKey]; struct Common::AutoHandleHKEY *
0x18000b5ec  xor     r13d, r13d
0x18000b5ef  mov     r8d, 2001Fh; unsigned int
0x18000b5f5  mov     [rbp+57h+hKey], r13
0x18000b5f9  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x18000b5fe  mov     ebx, eax
0x18000b600  test    eax, eax
0x18000b602  jns     short loc_18000B621
0x18000b604  mov     rcx, [rbp+5Fh]; this
0x18000b608  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000b60f  mov     r9d, eax; char *
0x18000b612  mov     edx, 0F04h; void *
0x18000b617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b61c  jmp     loc_18000B854
0x18000b621  xorps   xmm0, xmm0
0x18000b624  mov     [rbp+57h+var_50], r13d
0x18000b628  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x18000b62c  mov     r15d, r13d
0x18000b62f  mov     esi, r13d
0x18000b632  mov     rdi, [rbp+57h+lpName+8]
0x18000b636  test    rdi, rdi
0x18000b639  jnz     short loc_18000B640
0x18000b63b  mov     r14d, r13d
0x18000b63e  jmp     short loc_18000B64E
0x18000b640  mov     eax, r13d
0x18000b643  test    esi, esi
0x18000b645  jz      short loc_18000B64A
0x18000b647  lea     eax, [rsi-1]
0x18000b64a  lea     r14d, [rax+1]
0x18000b64e  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b652  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000b656  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000b65b  mov     r8, rdi; lpName
0x18000b65e  mov     [rsp+0D0h+lpcchClass], r13; lpcchClass
0x18000b663  mov     edx, r15d; dwIndex
0x18000b666  mov     [rsp+0D0h+lpClass], r13; lpClass
0x18000b66b  mov     [rsp+0D0h+lpReserved], r13; lpReserved
0x18000b670  mov     [rbp+57h+cchName], r14d
0x18000b674  call    cs:__imp_RegEnumKeyExW
0x18000b67a  mov     ebx, eax
0x18000b67c  test    eax, eax
0x18000b67e  jle     short loc_18000B689
0x18000b680  movzx   ebx, ax
0x18000b683  or      ebx, 80070000h
0x18000b689  test    ebx, ebx
0x18000b68b  js      short loc_18000B699
0x18000b68d  mov     edx, [rbp+57h+cchName]; unsigned int
0x18000b690  cmp     edx, r14d
0x18000b693  jbe     loc_18000B71C
0x18000b699  cmp     ebx, 800700EAh
0x18000b69f  jnz     loc_18000B72E
0x18000b6a5  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b6a9  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000b6ad  mov     [rsp+0D0h+var_78], r13; lpftLastWriteTime
0x18000b6b2  xor     r9d, r9d; lpReserved
0x18000b6b5  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000b6ba  xor     r8d, r8d; lpcchClass
0x18000b6bd  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000b6c2  xor     edx, edx; lpClass
0x18000b6c4  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000b6c9  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpcValues
0x18000b6ce  mov     [rsp+0D0h+lpcchClass], r13; lpcbMaxClassLen
0x18000b6d3  mov     [rsp+0D0h+lpClass], rax; lpcbMaxSubKeyLen
0x18000b6d8  mov     [rsp+0D0h+lpReserved], r13; int
0x18000b6dd  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18000b6e1  call    cs:__imp_RegQueryInfoKeyW
0x18000b6e7  mov     ebx, eax
0x18000b6e9  test    eax, eax
0x18000b6eb  jle     short loc_18000B6F6
0x18000b6ed  movzx   ebx, ax
0x18000b6f0  or      ebx, 80070000h
0x18000b6f6  test    ebx, ebx
0x18000b6f8  js      loc_18000B7C9
0x18000b6fe  mov     edx, [rbp+57h+cbMaxSubKeyLen]; unsigned int
0x18000b701  lea     rcx, [rbp+57h+lpName]; this
0x18000b705  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x18000b70a  mov     ebx, eax
0x18000b70c  test    eax, eax
0x18000b70e  js      loc_18000B7BF
0x18000b714  mov     esi, [rbp+57h+var_50]
0x18000b717  jmp     loc_18000B632
0x18000b71c  lea     rcx, [rbp+57h+lpName]; this
0x18000b720  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x18000b725  mov     esi, [rbp+57h+var_50]
0x18000b728  mov     ebx, eax
0x18000b72a  mov     rdi, [rbp+57h+lpName+8]
0x18000b72e  test    ebx, ebx
0x18000b730  js      loc_18000B7E1
0x18000b736  mov     r14d, r15d
0x18000b739  mov     qword ptr [rbp+57h+cbMaxSubKeyLen], r13
0x18000b73d  lea     r8, [rbp+57h+cbMaxSubKeyLen]; unsigned int *
0x18000b741  mov     [rbp+57h+cchName], r13d
0x18000b745  lea     rdx, [rbp+57h+cchName]; unsigned __int16 *
0x18000b749  mov     rcx, rdi; lpString1
0x18000b74c  inc     r15d
0x18000b74f  call    ?GetPackageFamilyNameFromPackageFullName@AppxAllUserStore@@YAJPEBGPEAIPEAPEAG@Z; AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(ushort const *,uint *,ushort * *)
0x18000b754  test    eax, eax
0x18000b756  jns     short loc_18000B766
0x18000b758  mov     rcx, qword ptr [rbp+57h+cbMaxSubKeyLen]; void *
0x18000b75c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000b761  jmp     loc_18000B636
0x18000b766  mov     rbx, qword ptr [rbp+57h+cbMaxSubKeyLen]
0x18000b76a  or      eax, 0FFFFFFFFh
0x18000b76d  mov     r9d, eax; cchCount2
0x18000b770  mov     dword ptr [rsp+0D0h+lpReserved], 1; unsigned int
0x18000b778  mov     edx, eax; cchCount1
0x18000b77a  mov     rcx, rbx; lpString1
0x18000b77d  mov     r8, r12; lpString2
0x18000b780  call    cs:__imp_CompareStringOrdinal
0x18000b786  cmp     eax, 2
0x18000b789  jnz     short loc_18000B79F
0x18000b78b  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b78f  mov     rdx, rdi; lpSubKey
0x18000b792  call    cs:__imp_RegDeleteTreeW
0x18000b798  test    eax, eax
0x18000b79a  jnz     short loc_18000B80C
0x18000b79c  mov     r15d, r14d
0x18000b79f  test    rbx, rbx
0x18000b7a2  jz      loc_18000B636
0x18000b7a8  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18000b7af  mov     r8, rbx; P
0x18000b7b2  xor     edx, edx; Flags
0x18000b7b4  call    cs:__imp_RtlFreeHeap
0x18000b7ba  jmp     loc_18000B636
0x18000b7bf  mov     r9d, eax
0x18000b7c2  mov     edx, 485h
0x18000b7c7  jmp     short loc_18000B7D1
0x18000b7c9  mov     r9d, ebx; char *
0x18000b7cc  mov     edx, 483h; void *
0x18000b7d1  mov     rcx, [rbp+5Fh]; this
0x18000b7d5  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\regist"...
0x18000b7dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7e1  cmp     ebx, 80070103h
0x18000b7e7  jz      short loc_18000B848
0x18000b7e9  mov     rcx, [rbp+5Fh]; this
0x18000b7ed  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000b7f4  mov     r9d, ebx; char *
0x18000b7f7  mov     edx, 0F1Fh; void *
0x18000b7fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b801  lea     rcx, [rbp+57h+lpName]; this
0x18000b805  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000b80a  jmp     short loc_18000B854
0x18000b80c  mov     rcx, [rbp+5Fh]; this
0x18000b810  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000b817  mov     r9d, eax; char *
0x18000b81a  mov     edx, 0F19h; void *
0x18000b81f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b824  mov     rcx, rbx; void *
0x18000b827  mov     esi, eax
0x18000b829  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000b82e  test    rdi, rdi
0x18000b831  jz      short loc_18000B83B
0x18000b833  mov     rcx, rdi; void *
0x18000b836  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000b83b  mov     rcx, [rbp+57h+hKey]
0x18000b83f  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000b844  mov     eax, esi
0x18000b846  jmp     short loc_18000B85F
0x18000b848  lea     rcx, [rbp+57h+lpName]; this
0x18000b84c  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000b851  mov     ebx, r13d
0x18000b854  lea     rcx, [rbp+57h+hKey]; this
0x18000b858  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18000b85d  mov     eax, ebx
0x18000b85f  add     rsp, 98h
0x18000b866  pop     r15
0x18000b868  pop     r14
0x18000b86a  pop     r13
0x18000b86c  pop     r12
0x18000b86e  pop     rdi
0x18000b86f  pop     rsi
0x18000b870  pop     rbx
0x18000b871  pop     rbp
0x18000b872  retn
```
