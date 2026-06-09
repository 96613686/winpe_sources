# ShieldProvider::QueryAndActionManager::GetFirstVolumePathName(ushort const *,ushort * *)

- ea: `0x180030b28`
- end: `0x180030d86`
- name: `?GetFirstVolumePathName@QueryAndActionManager@ShieldProvider@@QEAAJPEBGPEAPEAG@Z`
- size: `606`
- prototype: `int(ShieldProvider::QueryAndActionManager *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032464`

## callees

- `0x180004ae0`
- `0x180005028`
- `0x18000d7fc`
- `0x180015894`
- `0x180030b28`
- `0x1800dfc38`
- `0x1800e1690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180030bd4`
- `KERNEL32!GetLastError` at `0x180030bd4`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180030b60`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180030c8f`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180030b60`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180030c8f`

## pseudocode

```c
__int64 __fastcall ShieldProvider::QueryAndActionManager::GetFirstVolumePathName(
        ShieldProvider::QueryAndActionManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  void *v4; // rbx
  PVOID *v5; // rcx
  int LastFailure; // edi
  int v8; // eax
  __int64 v9; // r15
  WCHAR *v10; // r12
  BOOL VolumePathNamesForVolumeNameW; // eax
  __int64 v12; // rcx
  const unsigned __int16 *v13; // r8
  const struct std::nothrow_t *v14; // rdx
  unsigned __int16 *v15; // r15
  const struct std::nothrow_t *v16; // rdx
  DWORD cchReturnLength; // [rsp+60h] [rbp+40h] BYREF
  int v18; // [rsp+64h] [rbp+44h]
  LPCWSTR lpszVolumeName; // [rsp+68h] [rbp+48h]
  DWORD v20; // [rsp+70h] [rbp+50h] BYREF
  void *v21; // [rsp+78h] [rbp+58h] BYREF

  lpszVolumeName = a2;
  v18 = HIDWORD(this);
  *a3 = 0;
  cchReturnLength = 0;
  v4 = 0;
  v21 = 0;
  if ( GetVolumePathNamesForVolumeNameW(a2, 0, 0, &cchReturnLength) )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        cchReturnLength);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      WPP_SF_d(v5[2], 174, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, 2147500037LL);
    return 2147500037LL;
  }
  else
  {
    LastFailure = 0;
    if ( GetLastError() == 234 || (v8 = ((__int64 (*)(void))HrGetLastFailure)(), LastFailure = v8, v8 >= 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          176,
          WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
          cchReturnLength);
      v9 = -1;
      v10 = (WCHAR *)operator new[](saturated_mul(cchReturnLength, 2u));
      v20 = 0;
      VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(lpszVolumeName, v10, cchReturnLength, &v20);
      v14 = 0;
      if ( VolumePathNamesForVolumeNameW )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, v10);
          v14 = 0;
        }
        do
          ++v9;
        while ( v10[v9] );
        if ( v9 )
        {
          LastFailure = CommonUtil::HrDuplicateStringW((CommonUtil *)&v21, (unsigned __int16 **)v10, v13);
          if ( LastFailure < 0 )
          {
            v4 = v21;
          }
          else
          {
            v15 = (unsigned __int16 *)v21;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, v21);
            *a3 = v15;
          }
        }
        else
        {
          *a3 = 0;
        }
      }
      else
      {
        LastFailure = HrGetLastFailure(v12, 0);
      }
      operator delete(v10, v14);
      if ( LastFailure < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          179,
          WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
          (unsigned int)LastFailure);
      }
      if ( v4 )
        operator delete(v4, v16);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        175,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)v8);
    }
    return (unsigned int)LastFailure;
  }
}

```

## disassembly

```asm
0x180030b28  mov     [rsp-38h+lpszVolumeName], rdx
0x180030b2d  mov     qword ptr [rsp-38h+cchReturnLength], rcx
0x180030b32  push    rbp
0x180030b33  push    rbx
0x180030b34  push    rsi
0x180030b35  push    rdi
0x180030b36  push    r12
0x180030b38  push    r13
0x180030b3a  push    r15
0x180030b3c  mov     rbp, rsp
0x180030b3f  sub     rsp, 20h
0x180030b43  xor     esi, esi
0x180030b45  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180030b49  mov     [r8], rsi
0x180030b4c  mov     r13, r8
0x180030b4f  mov     rcx, rdx; lpszVolumeName
0x180030b52  mov     [rbp+cchReturnLength], esi
0x180030b55  mov     ebx, esi
0x180030b57  xor     r8d, r8d; cchBufferLength
0x180030b5a  xor     edx, edx; lpszVolumePathNames
0x180030b5c  mov     [rbp+arg_18], rbx
0x180030b60  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180030b66  test    eax, eax
0x180030b68  jz      short loc_180030BD2
0x180030b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b71  lea     rsi, WPP_GLOBAL_Control
0x180030b78  cmp     rcx, rsi
0x180030b7b  jz      short loc_180030BA3
0x180030b7d  test    byte ptr [rcx+1Ch], 1
0x180030b81  jz      short loc_180030BA3
0x180030b83  mov     r9d, [rbp+cchReturnLength]
0x180030b87  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030b8e  mov     rcx, [rcx+10h]
0x180030b92  mov     edx, 0ADh
0x180030b97  call    WPP_SF_d
0x180030b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ba3  mov     ebx, 80004005h
0x180030ba8  cmp     rcx, rsi
0x180030bab  jz      short loc_180030BCB
0x180030bad  test    byte ptr [rcx+1Ch], 1
0x180030bb1  jz      short loc_180030BCB
0x180030bb3  mov     rcx, [rcx+10h]
0x180030bb7  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030bbe  mov     edx, 0AEh
0x180030bc3  mov     r9d, ebx
0x180030bc6  call    WPP_SF_d
0x180030bcb  mov     eax, ebx
0x180030bcd  jmp     loc_180030D77
0x180030bd2  mov     edi, esi
0x180030bd4  call    cs:__imp_GetLastError
0x180030bda  cmp     eax, 0EAh
0x180030bdf  jz      short loc_180030C2A
0x180030be1  call    HrGetLastFailure
0x180030be6  mov     edi, eax
0x180030be8  test    eax, eax
0x180030bea  jns     short loc_180030C2A
0x180030bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180030bf3  lea     rsi, WPP_GLOBAL_Control
0x180030bfa  cmp     rcx, rsi
0x180030bfd  jz      loc_180030D75
0x180030c03  test    byte ptr [rcx+1Ch], 1
0x180030c07  jz      loc_180030D75
0x180030c0d  mov     rcx, [rcx+10h]
0x180030c11  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030c18  mov     edx, 0AFh
0x180030c1d  mov     r9d, eax
0x180030c20  call    WPP_SF_d
0x180030c25  jmp     loc_180030D75
0x180030c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c31  lea     rsi, WPP_GLOBAL_Control
0x180030c38  cmp     rcx, rsi
0x180030c3b  jz      short loc_180030C5C
0x180030c3d  test    byte ptr [rcx+1Ch], 10h
0x180030c41  jz      short loc_180030C5C
0x180030c43  mov     r9d, [rbp+cchReturnLength]
0x180030c47  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030c4e  mov     rcx, [rcx+10h]
0x180030c52  mov     edx, 0B0h
0x180030c57  call    WPP_SF_d
0x180030c5c  mov     ecx, [rbp+cchReturnLength]
0x180030c5f  mov     eax, 2
0x180030c64  mul     rcx
0x180030c67  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180030c6e  cmovb   rax, r15
0x180030c72  mov     rcx, rax; unsigned __int64
0x180030c75  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180030c7a  mov     r8d, [rbp+cchReturnLength]; cchBufferLength
0x180030c7e  lea     r9, [rbp+arg_10]; lpcchReturnLength
0x180030c82  mov     rcx, [rbp+lpszVolumeName]; lpszVolumeName
0x180030c86  mov     rdx, rax; lpszVolumePathNames
0x180030c89  mov     r12, rax
0x180030c8c  mov     [rbp+arg_10], ebx
0x180030c8f  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180030c95  xor     edx, edx
0x180030c97  test    eax, eax
0x180030c99  jnz     short loc_180030CA7
0x180030c9b  call    HrGetLastFailure
0x180030ca0  mov     edi, eax
0x180030ca2  jmp     loc_180030D32
0x180030ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cae  cmp     rcx, rsi
0x180030cb1  jz      short loc_180030CD3
0x180030cb3  test    byte ptr [rcx+1Ch], 10h
0x180030cb7  jz      short loc_180030CD3
0x180030cb9  mov     rcx, [rcx+10h]
0x180030cbd  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030cc4  mov     edx, 0B1h
0x180030cc9  mov     r9, r12
0x180030ccc  call    WPP_SF_S
0x180030cd1  xor     edx, edx; struct std::nothrow_t *
0x180030cd3  inc     r15
0x180030cd6  cmp     [r12+r15*2], dx
0x180030cdb  jnz     short loc_180030CD3
0x180030cdd  test    r15, r15
0x180030ce0  jz      short loc_180030D2E
0x180030ce2  mov     rdx, r12; unsigned __int16 **
0x180030ce5  lea     rcx, [rbp+arg_18]; this
0x180030ce9  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x180030cee  mov     edi, eax
0x180030cf0  test    eax, eax
0x180030cf2  js      short loc_180030D28
0x180030cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cfb  mov     r15, [rbp+arg_18]
0x180030cff  cmp     rcx, rsi
0x180030d02  jz      short loc_180030D22
0x180030d04  test    byte ptr [rcx+1Ch], 10h
0x180030d08  jz      short loc_180030D22
0x180030d0a  mov     rcx, [rcx+10h]
0x180030d0e  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030d15  mov     edx, 0B2h
0x180030d1a  mov     r9, r15
0x180030d1d  call    WPP_SF_S
0x180030d22  mov     [r13+0], r15
0x180030d26  jmp     short loc_180030D32
0x180030d28  mov     rbx, [rbp+arg_18]
0x180030d2c  jmp     short loc_180030D32
0x180030d2e  mov     [r13+0], rdx
0x180030d32  mov     rcx, r12; void *
0x180030d35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030d3a  test    edi, edi
0x180030d3c  jns     short loc_180030D68
0x180030d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d45  cmp     rcx, rsi
0x180030d48  jz      short loc_180030D68
0x180030d4a  test    byte ptr [rcx+1Ch], 1
0x180030d4e  jz      short loc_180030D68
0x180030d50  mov     rcx, [rcx+10h]
0x180030d54  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030d5b  mov     edx, 0B3h
0x180030d60  mov     r9d, edi
0x180030d63  call    WPP_SF_d
0x180030d68  test    rbx, rbx
0x180030d6b  jz      short loc_180030D75
0x180030d6d  mov     rcx, rbx; void *
0x180030d70  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030d75  mov     eax, edi
0x180030d77  add     rsp, 20h
0x180030d7b  pop     r15
0x180030d7d  pop     r13
0x180030d7f  pop     r12
0x180030d81  pop     rdi
0x180030d82  pop     rsi
0x180030d83  pop     rbx
0x180030d84  pop     rbp
0x180030d85  retn
```
