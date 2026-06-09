# RegistryRegRow::PutPropertyBag(ushort const *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x18003b290`
- end: `0x18003b53e`
- name: `?PutPropertyBag@RegistryRegRow@@UEAAJPEBGPEAUtagPROPVARIANT@@1@Z`
- size: `686`
- prototype: `int(RegistryRegRow *__hidden this, const unsigned __int16 *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006194`
- `0x180008fbc`
- `0x18000c910`
- `0x180028cf0`
- `0x18003b290`
- `0x18003bcd4`
- `0x180043510`
- `0x1800435a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b420`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b4df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b4df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b489`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b489`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b4ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b4ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003b416`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003b416`

## pseudocode

```c
__int64 __fastcall RegistryRegRow::PutPropertyBag(
        RegistryRegRow *this,
        const unsigned __int16 *a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  __int64 result; // rax
  unsigned int v9; // esi
  unsigned __int16 *p_dwDisposition; // rdi
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  unsigned __int16 *v14; // rax
  signed int v15; // ebx
  unsigned int v16; // esi
  const WCHAR *v17; // rcx
  signed int LastError; // eax
  HKEY v19; // rcx
  LSTATUS v20; // eax
  unsigned int ulVal; // r15d
  __int64 v22; // [rsp+0h] [rbp-50h] BYREF
  DWORD dwDisposition; // [rsp+50h] [rbp+0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+10h] BYREF
  unsigned __int64 v26; // [rsp+68h] [rbp+18h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( !a3 || !a4 || !a3->lVal )
    return 1;
  result = ValidatePropertyBag(a3, a4);
  if ( (int)result >= 0 )
  {
    hKey = 0;
    dwDisposition = 0;
    v26 = *((_DWORD *)this + 35) + 2 + (unsigned int)safe_lstrlenW(a2);
    v9 = 2 * v26;
    if ( 2 * v26 > 0xFFFFFFFF )
    {
      return 2147942934LL;
    }
    else
    {
      p_dwDisposition = 0;
      if ( !v9
        || v9 > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)v9 + g_ulAdditionalProbeSize + 8 < v9
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_43;
      }
      v11 = v9 + 23LL;
      if ( v11 <= (unsigned __int64)v9 + 8 )
        v11 = 0xFFFFFFFFFFFFFF0LL;
      v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
      v13 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
      p_dwDisposition = (unsigned __int16 *)&dwDisposition;
      if ( &v22 == (__int64 *)-80LL
        || (dwDisposition = 1801679955, (p_dwDisposition = (unsigned __int16 *)&SecurityDescriptor) == 0) )
      {
LABEL_43:
        if ( (unsigned __int64)v9 + 8 >= v9 )
        {
          v14 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
          p_dwDisposition = v14;
          if ( v14 )
          {
            *(_DWORD *)v14 = 1885431112;
            p_dwDisposition = v14 + 4;
          }
        }
      }
      if ( p_dwDisposition )
      {
        v16 = 0;
        v15 = StringCchPrintfW(p_dwDisposition, v26, L"%s\\%s", *((_QWORD *)this + 15), a2);
        if ( v15 >= 0 )
        {
          v17 = (const WCHAR *)*((_QWORD *)this + 14);
          SecurityDescriptor = 0;
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v17, 1u, &SecurityDescriptor, 0) )
          {
            v19 = (HKEY)*((_QWORD *)this + 16);
            SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
            *(_QWORD *)&SecurityAttributes.nLength = 24;
            *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
            v20 = RegCreateKeyExW(v19, p_dwDisposition, 0, 0, 0, 0x20006u, &SecurityAttributes, &hKey, &dwDisposition);
            if ( v20 )
            {
              if ( v20 > 0 )
                v15 = (unsigned __int16)v20 | 0x80070000;
              else
                v15 = v20;
            }
            else
            {
              ulVal = a3->ulVal;
              if ( ulVal )
              {
                do
                {
                  v15 = WriteRawVariant(
                          hKey,
                          *(const unsigned __int16 **)&a3->bstrblobVal.pData[8 * v16],
                          (struct tagPROPVARIANT *)&a4->bstrblobVal.pData[24 * v16]);
                  if ( v15 < 0 )
                    break;
                  ++v16;
                }
                while ( v16 < ulVal );
              }
            }
            LocalFree(SecurityDescriptor);
          }
          else
          {
            LastError = GetLastError();
            v15 = LastError;
            if ( LastError > 0 )
              v15 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
      else
      {
        v15 = -2147024882;
      }
      if ( hKey )
        RegCloseKey(hKey);
      if ( p_dwDisposition )
      {
        if ( *((_DWORD *)p_dwDisposition - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
      }
      return (unsigned int)v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003b290  push    rbp
0x18003b292  push    rbx
0x18003b293  push    rsi
0x18003b294  push    rdi
0x18003b295  push    r12
0x18003b297  push    r13
0x18003b299  push    r14
0x18003b29b  push    r15
0x18003b29d  sub     rsp, 0A8h
0x18003b2a4  lea     rbp, [rsp+50h]
0x18003b2a9  mov     rax, cs:__security_cookie
0x18003b2b0  xor     rax, rbp
0x18003b2b3  mov     [rbp+90h+var_50], rax
0x18003b2b7  mov     r12, r9
0x18003b2ba  mov     r14, r8
0x18003b2bd  mov     r15, rdx
0x18003b2c0  mov     r13, rcx
0x18003b2c3  test    rdx, rdx
0x18003b2c6  jnz     short loc_18003B2D2
0x18003b2c8  mov     eax, 80070057h
0x18003b2cd  jmp     loc_18003B521
0x18003b2d2  test    r14, r14
0x18003b2d5  jz      loc_18003B51C
0x18003b2db  test    r12, r12
0x18003b2de  jz      loc_18003B51C
0x18003b2e4  cmp     dword ptr [r8+8], 0
0x18003b2e9  jz      loc_18003B51C
0x18003b2ef  mov     rdx, r12; struct tagPROPVARIANT *
0x18003b2f2  mov     rcx, r14; struct tagPROPVARIANT *
0x18003b2f5  call    ?ValidatePropertyBag@@YAJPEBUtagPROPVARIANT@@0@Z; ValidatePropertyBag(tagPROPVARIANT const *,tagPROPVARIANT const *)
0x18003b2fa  test    eax, eax
0x18003b2fc  js      loc_18003B521
0x18003b302  mov     rcx, r15; unsigned __int16 *
0x18003b305  mov     [rbp+90h+hKey], 0
0x18003b30d  mov     [rbp+90h+dwDisposition], 0
0x18003b314  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003b319  mov     ecx, [r13+8Ch]
0x18003b320  add     ecx, 2
0x18003b323  add     eax, ecx
0x18003b325  mov     [rbp+90h+var_78], rax
0x18003b329  lea     rsi, [rax+rax]
0x18003b32d  mov     eax, 0FFFFFFFFh
0x18003b332  cmp     rsi, rax
0x18003b335  ja      loc_18003B515
0x18003b33b  xor     edi, edi
0x18003b33d  test    esi, esi
0x18003b33f  jz      short loc_18003B3A4
0x18003b341  mov     ebx, esi
0x18003b343  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18003b34a  ja      short loc_18003B3A4
0x18003b34c  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003b353  add     rcx, 8
0x18003b357  add     rcx, rbx
0x18003b35a  cmp     rcx, rbx
0x18003b35d  jb      short loc_18003B3A4
0x18003b35f  call    VerifyStackAvailable
0x18003b364  test    eax, eax
0x18003b366  jz      short loc_18003B3A4
0x18003b368  lea     rax, [rbx+8]
0x18003b36c  lea     rcx, [rax+0Fh]
0x18003b370  cmp     rcx, rax
0x18003b373  ja      short loc_18003B37F
0x18003b375  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18003b37f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003b383  mov     rax, rcx
0x18003b386  call    _alloca_probe
0x18003b38b  sub     rsp, rcx
0x18003b38e  lea     rdi, [rsp+0E0h+dwDisposition]
0x18003b393  test    rdi, rdi
0x18003b396  jz      short loc_18003B3A4
0x18003b398  mov     dword ptr [rdi], 6B637453h
0x18003b39e  add     rdi, 8
0x18003b3a2  jnz     short loc_18003B3CD
0x18003b3a4  mov     eax, esi
0x18003b3a6  lea     rcx, [rax+8]
0x18003b3aa  cmp     rcx, rax
0x18003b3ad  jb      short loc_18003B3CD
0x18003b3af  mov     rax, cs:g_pfnAllocate
0x18003b3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3bb  mov     rdi, rax
0x18003b3be  test    rax, rax
0x18003b3c1  jz      short loc_18003B3CD
0x18003b3c3  mov     dword ptr [rax], 70616548h
0x18003b3c9  add     rdi, 8
0x18003b3cd  test    rdi, rdi
0x18003b3d0  jnz     short loc_18003B3DC
0x18003b3d2  mov     ebx, 8007000Eh
0x18003b3d7  jmp     loc_18003B4E5
0x18003b3dc  mov     r9, [r13+78h]
0x18003b3e0  lea     r8, aSS; "%s\\%s"
0x18003b3e7  mov     rdx, [rbp+90h+var_78]; unsigned __int64
0x18003b3eb  mov     rcx, rdi; unsigned __int16 *
0x18003b3ee  mov     qword ptr [rsp+0E0h+dwOptions], r15
0x18003b3f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b3f8  xor     esi, esi
0x18003b3fa  mov     ebx, eax
0x18003b3fc  test    eax, eax
0x18003b3fe  js      loc_18003B4E5
0x18003b404  mov     rcx, [r13+70h]; StringSecurityDescriptor
0x18003b408  lea     r8, [rbp+90h+SecurityDescriptor]; SecurityDescriptor
0x18003b40c  xor     r9d, r9d; SecurityDescriptorSize
0x18003b40f  mov     [rbp+90h+SecurityDescriptor], rsi
0x18003b413  lea     edx, [rsi+1]; StringSDRevision
0x18003b416  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003b41c  test    eax, eax
0x18003b41e  jnz     short loc_18003B43E
0x18003b420  call    cs:__imp_GetLastError
0x18003b426  mov     ebx, eax
0x18003b428  test    eax, eax
0x18003b42a  jle     loc_18003B4E5
0x18003b430  movzx   ebx, ax
0x18003b433  or      ebx, 80070000h
0x18003b439  jmp     loc_18003B4E5
0x18003b43e  mov     rax, [rbp+90h+SecurityDescriptor]
0x18003b442  xor     r9d, r9d; lpClass
0x18003b445  mov     rcx, [r13+80h]; hKey
0x18003b44c  xor     r8d, r8d; Reserved
0x18003b44f  mov     [rbp+90h+SecurityAttributes.lpSecurityDescriptor], rax
0x18003b453  mov     rdx, rdi; lpSubKey
0x18003b456  lea     rax, [rbp+90h+dwDisposition]
0x18003b45a  mov     qword ptr [rbp+90h+SecurityAttributes.nLength], 18h
0x18003b462  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x18003b467  lea     rax, [rbp+90h+hKey]
0x18003b46b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003b470  lea     rax, [rbp+90h+SecurityAttributes]
0x18003b474  mov     [rsp+0E0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18003b479  mov     [rsp+0E0h+samDesired], 20006h; samDesired
0x18003b481  mov     [rsp+0E0h+dwOptions], esi; dwOptions
0x18003b485  mov     qword ptr [rbp+90h+SecurityAttributes.bInheritHandle], rsi
0x18003b489  call    cs:__imp_RegCreateKeyExW
0x18003b48f  test    eax, eax
0x18003b491  jz      short loc_18003B4A4
0x18003b493  jg      short loc_18003B499
0x18003b495  mov     ebx, eax
0x18003b497  jmp     short loc_18003B4DB
0x18003b499  movzx   ebx, ax
0x18003b49c  or      ebx, 80070000h
0x18003b4a2  jmp     short loc_18003B4DB
0x18003b4a4  mov     r15d, [r14+8]
0x18003b4a8  test    r15d, r15d
0x18003b4ab  jz      short loc_18003B4DB
0x18003b4ad  mov     rax, [r12+10h]
0x18003b4b2  mov     rdx, [r14+10h]
0x18003b4b6  mov     r9d, esi
0x18003b4b9  mov     rdx, [rdx+r9*8]; unsigned __int16 *
0x18003b4bd  lea     rcx, [r9+r9*2]
0x18003b4c1  lea     r8, [rax+rcx*8]; struct tagPROPVARIANT *
0x18003b4c5  mov     rcx, [rbp+90h+hKey]; HKEY
0x18003b4c9  call    ?WriteRawVariant@@YAJPEAUHKEY__@@PEBGAEAUtagPROPVARIANT@@@Z; WriteRawVariant(HKEY__ *,ushort const *,tagPROPVARIANT &)
0x18003b4ce  mov     ebx, eax
0x18003b4d0  test    eax, eax
0x18003b4d2  js      short loc_18003B4DB
0x18003b4d4  inc     esi
0x18003b4d6  cmp     esi, r15d
0x18003b4d9  jb      short loc_18003B4AD
0x18003b4db  mov     rcx, [rbp+90h+SecurityDescriptor]; hMem
0x18003b4df  call    cs:__imp_LocalFree
0x18003b4e5  mov     rcx, [rbp+90h+hKey]; hKey
0x18003b4e9  test    rcx, rcx
0x18003b4ec  jz      short loc_18003B4F4
0x18003b4ee  call    cs:__imp_RegCloseKey
0x18003b4f4  test    rdi, rdi
0x18003b4f7  jz      short loc_18003B511
0x18003b4f9  lea     rcx, [rdi-8]
0x18003b4fd  cmp     dword ptr [rcx], 70616548h
0x18003b503  jnz     short loc_18003B511
0x18003b505  mov     rax, cs:g_pfnFree
0x18003b50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b511  mov     eax, ebx
0x18003b513  jmp     short loc_18003B521
0x18003b515  mov     eax, 80070216h
0x18003b51a  jmp     short loc_18003B521
0x18003b51c  mov     eax, 1
0x18003b521  mov     rcx, [rbp+90h+var_50]
0x18003b525  xor     rcx, rbp; StackCookie
0x18003b528  call    __security_check_cookie
0x18003b52d  lea     rsp, [rbp+58h]
0x18003b531  pop     r15
0x18003b533  pop     r14
0x18003b535  pop     r13
0x18003b537  pop     r12
0x18003b539  pop     rdi
0x18003b53a  pop     rsi
0x18003b53b  pop     rbx
0x18003b53c  pop     rbp
0x18003b53d  retn
```
