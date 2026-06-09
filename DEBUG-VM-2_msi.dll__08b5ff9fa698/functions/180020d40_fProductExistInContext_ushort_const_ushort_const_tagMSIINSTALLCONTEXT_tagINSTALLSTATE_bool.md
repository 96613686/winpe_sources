# fProductExistInContext(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,tagINSTALLSTATE &,bool &)

- ea: `0x180020d40`
- end: `0x18002101c`
- name: `?fProductExistInContext@@YA_NPEBG0W4tagMSIINSTALLCONTEXT@@AEAW4tagINSTALLSTATE@@AEA_N@Z`
- size: `732`
- prototype: `bool(const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, enum tagINSTALLSTATE *, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800e2658`
- `0x180212884`

## callees

- `0x180015950`
- `0x180017a84`
- `0x180020d40`
- `0x180021030`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180020e6c`
- `ADVAPI32!RegCloseKey` at `0x180020ee5`
- `ADVAPI32!RegCloseKey` at `0x180020e6c`
- `ADVAPI32!RegCloseKey` at `0x180020ee5`
- `KERNEL32!InitializeCriticalSection` at `0x180020db7`
- `KERNEL32!InitializeCriticalSection` at `0x180020db7`
- `KERNEL32!DeleteCriticalSection` at `0x180020e8c`
- `KERNEL32!DeleteCriticalSection` at `0x180020f05`
- `KERNEL32!DeleteCriticalSection` at `0x180020e8c`
- `KERNEL32!DeleteCriticalSection` at `0x180020f05`
- `KERNEL32!LeaveCriticalSection` at `0x180020e82`
- `KERNEL32!LeaveCriticalSection` at `0x180020efb`
- `KERNEL32!LeaveCriticalSection` at `0x180020e82`
- `KERNEL32!LeaveCriticalSection` at `0x180020efb`
- `KERNEL32!EnterCriticalSection` at `0x180020e5d`
- `KERNEL32!EnterCriticalSection` at `0x180020ed6`
- `KERNEL32!EnterCriticalSection` at `0x180020e5d`
- `KERNEL32!EnterCriticalSection` at `0x180020ed6`
- `KERNEL32!GlobalFree` at `0x180020e9c`
- `KERNEL32!GlobalFree` at `0x180020f15`
- `KERNEL32!GlobalFree` at `0x180020e9c`
- `KERNEL32!GlobalFree` at `0x180020f15`

## pseudocode

```c
char __fastcall fProductExistInContext(
        unsigned __int16 *a1,
        wchar_t *a2,
        enum tagMSIINSTALLCONTEXT a3,
        enum tagINSTALLSTATE *a4,
        bool *a5)
{
  int v9; // esi
  bool v10; // al
  unsigned __int32 v11; // ebx
  _DWORD v13[4]; // [rsp+50h] [rbp-51h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-41h] BYREF
  HGLOBAL hMem; // [rsp+70h] [rbp-31h]
  int v16; // [rsp+78h] [rbp-29h]
  __int16 v17; // [rsp+80h] [rbp-21h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+88h] [rbp-19h] BYREF

  *a4 = INSTALLSTATE_UNKNOWN;
  switch ( a3 )
  {
    case MSIINSTALLCONTEXT_MACHINE:
      v9 = 2;
      break;
    case MSIINSTALLCONTEXT_USERMANAGED:
      v9 = 0;
      break;
    case MSIINSTALLCONTEXT_USERUNMANAGED:
      v9 = 1;
      if ( !IsCurrentUser(a2) )
      {
        v10 = 1;
        goto LABEL_4;
      }
      break;
    default:
      v9 = 3;
      break;
  }
  v10 = 0;
LABEL_4:
  *a5 = v10;
  v16 = 1;
  hMem = &v17;
  *(_OWORD *)hKey = 0;
  v17 = 0;
  InitializeCriticalSection(&CriticalSection);
  v13[0] = 0;
  if ( !(unsigned int)GetInfo(a1, a2, v9, 1, (__int64)L"LocalPackage", 0, v13, 1, -1) && v13[0] )
  {
    *a4 = INSTALLSTATE_DEFAULT;
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return 1;
  }
  if ( *a5 )
    goto LABEL_32;
  if ( (a3 & 4) == 0 || (unsigned int)GetInfo(a1, a2, 2, 1, (__int64)L"AdvertiseFlags", 0, 0, 0, 1) )
  {
    v11 = a3 & 0xFFFFFFFB;
    if ( !v11 )
    {
LABEL_9:
      EnterCriticalSection(&CriticalSection);
      if ( hKey[0] )
      {
        RegCloseKey(hKey[0]);
        hKey[0] = 0;
        *(_WORD *)hMem = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      DeleteCriticalSection(&CriticalSection);
      if ( v16 > 1 )
        GlobalFree(hMem);
      return 0;
    }
    if ( (unsigned int)GetInfo(a1, a2, 0, 1, (__int64)L"AdvertiseFlags", 0, 0, *a5, 1) )
    {
      if ( !(unsigned int)GetInfo(a1, a2, 1, 1, (__int64)L"AdvertiseFlags", 0, 0, *a5, 1) )
      {
        if ( (v11 & 2) == 0 )
          goto LABEL_9;
LABEL_22:
        *a4 = INSTALLSTATE_ADVERTISED;
        CRegHandle::~CRegHandle((CRegHandle *)hKey);
        return 1;
      }
    }
    else if ( (v11 & 1) != 0 )
    {
      goto LABEL_22;
    }
LABEL_32:
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return 0;
  }
  *a4 = INSTALLSTATE_ADVERTISED;
  EnterCriticalSection(&CriticalSection);
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
    *(_WORD *)hMem = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( v16 > 1 )
    GlobalFree(hMem);
  return 1;
}

```

## disassembly

```asm
0x180020d40  mov     [rsp-8+arg_10], rbx
0x180020d45  push    rbp
0x180020d46  push    rsi
0x180020d47  push    rdi
0x180020d48  push    r12
0x180020d4a  push    r13
0x180020d4c  push    r14
0x180020d4e  push    r15
0x180020d50  lea     rbp, [rsp-1Fh]
0x180020d55  sub     rsp, 0C0h
0x180020d5c  mov     rax, cs:__security_cookie
0x180020d63  xor     rax, rsp
0x180020d66  mov     [rbp+4Fh+var_40], rax
0x180020d6a  mov     rdi, [rbp+4Fh+arg_20]
0x180020d6e  xor     r13d, r13d
0x180020d71  mov     dword ptr [r9], 0FFFFFFFFh
0x180020d78  mov     r14, r9
0x180020d7b  mov     ebx, r8d
0x180020d7e  mov     r15, rdx
0x180020d81  mov     r12, rcx
0x180020d84  cmp     r8d, 4
0x180020d88  jnz     loc_180020FD0
0x180020d8e  mov     esi, 2
0x180020d93  xor     al, al
0x180020d95  mov     [rdi], al
0x180020d97  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x180020d9b  lea     rax, [rbp+4Fh+var_70]
0x180020d9f  mov     [rbp+4Fh+var_78], 1
0x180020da6  xorps   xmm0, xmm0
0x180020da9  mov     [rbp+4Fh+hMem], rax
0x180020dad  movdqa  xmmword ptr [rbp+4Fh+hKey], xmm0
0x180020db2  mov     [rbp+4Fh+var_70], r13w
0x180020db7  call    cs:__imp_InitializeCriticalSection
0x180020dbd  mov     [rsp+0F0h+var_B0], 0FFFFFFFFh
0x180020dc5  lea     rax, [rbp+4Fh+var_A0]
0x180020dc9  mov     [rsp+0F0h+var_B8], 1
0x180020dce  mov     r9d, 1
0x180020dd4  mov     [rsp+0F0h+var_C0], rax
0x180020dd9  mov     r8d, esi
0x180020ddc  lea     rax, aLocalpackage_0; "LocalPackage"
0x180020de3  mov     [rsp+0F0h+var_C8], r13
0x180020de8  mov     rdx, r15
0x180020deb  mov     [rsp+0F0h+var_D0], rax
0x180020df0  mov     rcx, r12
0x180020df3  mov     [rbp+4Fh+var_A0], r13d
0x180020df7  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x180020dfc  test    eax, eax
0x180020dfe  jz      loc_180020FAF
0x180020e04  cmp     [rdi], r13b
0x180020e07  jnz     loc_18002100E
0x180020e0d  lea     rsi, aAdvertiseflags; "AdvertiseFlags"
0x180020e14  test    bl, 4
0x180020e17  jz      short loc_180020E50
0x180020e19  mov     [rsp+0F0h+var_B0], 1
0x180020e21  mov     r9d, 1
0x180020e27  mov     [rsp+0F0h+var_B8], r13b
0x180020e2c  mov     r8d, 2
0x180020e32  mov     [rsp+0F0h+var_C0], r13
0x180020e37  mov     rdx, r15
0x180020e3a  mov     [rsp+0F0h+var_C8], r13
0x180020e3f  mov     rcx, r12
0x180020e42  mov     [rsp+0F0h+var_D0], rsi
0x180020e47  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x180020e4c  test    eax, eax
0x180020e4e  jz      short loc_180020ECB
0x180020e50  and     ebx, 0FFFFFFFBh
0x180020e53  jnz     loc_180020F1F
0x180020e59  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x180020e5d  call    cs:__imp_EnterCriticalSection
0x180020e63  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180020e67  test    rcx, rcx
0x180020e6a  jz      short loc_180020E7E
0x180020e6c  call    cs:__imp_RegCloseKey
0x180020e72  mov     rax, [rbp+4Fh+hMem]
0x180020e76  mov     [rbp+4Fh+hKey], r13
0x180020e7a  mov     [rax], r13w
0x180020e7e  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x180020e82  call    cs:__imp_LeaveCriticalSection
0x180020e88  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x180020e8c  call    cs:__imp_DeleteCriticalSection
0x180020e92  cmp     [rbp+4Fh+var_78], 1
0x180020e96  jle     short loc_180020EA2
0x180020e98  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180020e9c  call    cs:__imp_GlobalFree
0x180020ea2  xor     al, al
0x180020ea4  mov     rcx, [rbp+4Fh+var_40]
0x180020ea8  xor     rcx, rsp; StackCookie
0x180020eab  call    __security_check_cookie
0x180020eb0  mov     rbx, [rsp+0F0h+arg_10]
0x180020eb8  add     rsp, 0C0h
0x180020ebf  pop     r15
0x180020ec1  pop     r14
0x180020ec3  pop     r13
0x180020ec5  pop     r12
0x180020ec7  pop     rdi
0x180020ec8  pop     rsi
0x180020ec9  pop     rbp
0x180020eca  retn
0x180020ecb  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x180020ecf  mov     dword ptr [r14], 1
0x180020ed6  call    cs:__imp_EnterCriticalSection
0x180020edc  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180020ee0  test    rcx, rcx
0x180020ee3  jz      short loc_180020EF7
0x180020ee5  call    cs:__imp_RegCloseKey
0x180020eeb  mov     rax, [rbp+4Fh+hMem]
0x180020eef  mov     [rbp+4Fh+hKey], r13
0x180020ef3  mov     [rax], r13w
0x180020ef7  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x180020efb  call    cs:__imp_LeaveCriticalSection
0x180020f01  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x180020f05  call    cs:__imp_DeleteCriticalSection
0x180020f0b  cmp     [rbp+4Fh+var_78], 1
0x180020f0f  jle     short loc_180020F1B
0x180020f11  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180020f15  call    cs:__imp_GlobalFree
0x180020f1b  mov     al, 1
0x180020f1d  jmp     short loc_180020EA4
0x180020f1f  movzx   eax, byte ptr [rdi]
0x180020f22  mov     r9d, 1
0x180020f28  mov     [rsp+0F0h+var_B0], 1
0x180020f30  xor     r8d, r8d
0x180020f33  mov     [rsp+0F0h+var_B8], al
0x180020f37  mov     rdx, r15
0x180020f3a  mov     [rsp+0F0h+var_C0], r13
0x180020f3f  mov     rcx, r12
0x180020f42  mov     [rsp+0F0h+var_C8], r13
0x180020f47  mov     [rsp+0F0h+var_D0], rsi
0x180020f4c  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x180020f51  test    eax, eax
0x180020f53  jz      loc_180021009
0x180020f59  movzx   eax, byte ptr [rdi]
0x180020f5c  mov     r9d, 1
0x180020f62  mov     [rsp+0F0h+var_B0], 1
0x180020f6a  mov     r8d, r9d
0x180020f6d  mov     [rsp+0F0h+var_B8], al
0x180020f71  mov     rdx, r15
0x180020f74  mov     [rsp+0F0h+var_C0], r13
0x180020f79  mov     rcx, r12
0x180020f7c  mov     [rsp+0F0h+var_C8], r13
0x180020f81  mov     [rsp+0F0h+var_D0], rsi
0x180020f86  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x180020f8b  test    eax, eax
0x180020f8d  jnz     short loc_18002100E
0x180020f8f  test    bl, 2
0x180020f92  jz      loc_180020E59
0x180020f98  lea     rcx, [rbp+4Fh+hKey]; this
0x180020f9c  mov     dword ptr [r14], 1
0x180020fa3  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180020fa8  mov     al, 1
0x180020faa  jmp     loc_180020EA4
0x180020faf  cmp     [rbp+4Fh+var_A0], r13d
0x180020fb3  jz      loc_180020E04
0x180020fb9  lea     rcx, [rbp+4Fh+hKey]; this
0x180020fbd  mov     dword ptr [r14], 5
0x180020fc4  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180020fc9  mov     al, 1
0x180020fcb  jmp     loc_180020EA4
0x180020fd0  mov     ecx, ebx
0x180020fd2  sub     ecx, 1
0x180020fd5  jz      short loc_180021001
0x180020fd7  cmp     ecx, 1
0x180020fda  jnz     short loc_180020FF7
0x180020fdc  mov     esi, ecx
0x180020fde  mov     rcx, r15; String1
0x180020fe1  call    ?IsCurrentUser@@YA_NPEBG@Z; IsCurrentUser(ushort const *)
0x180020fe6  test    al, al
0x180020fe8  jnz     loc_180020D93
0x180020fee  movzx   eax, sil
0x180020ff2  jmp     loc_180020D95
0x180020ff7  mov     esi, 3
0x180020ffc  jmp     loc_180020D93
0x180021001  mov     esi, r13d
0x180021004  jmp     loc_180020D93
0x180021009  test    bl, 1
0x18002100c  jnz     short loc_180020F98
0x18002100e  lea     rcx, [rbp+4Fh+hKey]; this
0x180021012  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180021017  jmp     loc_180020EA2
```
