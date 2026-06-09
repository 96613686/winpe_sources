# MetadataPackageSource::RemovePackage(ushort const *)

- ea: `0x180011df0`
- end: `0x180011fa9`
- name: `?RemovePackage@MetadataPackageSource@@UEAAJPEBG@Z`
- size: `441`
- prototype: `__int64 __fastcall(MetadataPackageSource *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004e2c`
- `0x18000b244`
- `0x180011df0`
- `0x180013700`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011e2b`
- `KERNEL32!EnterCriticalSection` at `0x180011e2b`
- `KERNEL32!LeaveCriticalSection` at `0x180011f7b`
- `KERNEL32!LeaveCriticalSection` at `0x180011f7b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011f2e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011f2e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011f4b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011f6f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011f4b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011f6f`
- `KERNEL32!AcquireSRWLockShared` at `0x180011e98`
- `KERNEL32!AcquireSRWLockShared` at `0x180011e98`
- `KERNEL32!ReleaseSRWLockShared` at `0x180011f02`
- `KERNEL32!ReleaseSRWLockShared` at `0x180011f02`
- `DEVRTL!NdxTableObjectFromName` at `0x180011eac`
- `DEVRTL!NdxTableObjectFromName` at `0x180011ec5`
- `DEVRTL!NdxTableObjectFromName` at `0x180011eac`
- `DEVRTL!NdxTableObjectFromName` at `0x180011ec5`
- `DEVRTL!NdxTableGetObjectType` at `0x180011f3e`
- `DEVRTL!NdxTableGetObjectType` at `0x180011f3e`

## pseudocode

```c
__int64 __fastcall MetadataPackageSource::RemovePackage(MetadataPackageSource *this, const unsigned __int16 *a2)
{
  __int64 v3; // r14
  __int64 v4; // rbp
  __int64 v5; // rdi
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  int v10; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v11[2]; // [rsp+28h] [rbp-60h] BYREF
  __int64 v12; // [rsp+48h] [rbp-40h]

  v3 = *((_QWORD *)g_pmrc + 8);
  v4 = *((_QWORD *)g_pmrc + 5);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids, a2);
  v12 = 0;
  memset(v11, 0, sizeof(v11));
  v5 = *((_QWORD *)g_pmrc + 5);
  if ( v5 && *(_DWORD *)v5 == 1229866053 )
  {
    v6 = 0;
    AcquireSRWLockShared((PSRWLOCK)(v5 + 32));
    if ( !(unsigned int)NdxTableObjectFromName(*(_QWORD *)(v5 + 40), 0, a2, v11)
      && !(unsigned int)NdxTableObjectFromName(*(_QWORD *)(v5 + 40), 1, a2, v11) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, a2);
      v6 = 1168;
    }
    ReleaseSRWLockShared((PSRWLOCK)(v5 + 32));
  }
  else
  {
    v6 = 87;
  }
  if ( v6 )
    v6 |= 0x80070000;
  if ( v6 >= 0 )
  {
    v10 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(v4 + 32));
    if ( (unsigned int)NdxTableGetObjectType(v11, &v10) )
    {
      if ( v10 == 1 )
        RemoveDataFromIndex((struct _INDEX_STRUCT *)v4, (struct NDX_OBJREF *)v11, v7, v8);
      ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 32));
      v6 = 0;
    }
    else
    {
      ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 32));
      v6 = -2147467259;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011df0  mov     [rsp+arg_0], rbx
0x180011df5  mov     [rsp+arg_10], rbp
0x180011dfa  push    rsi
0x180011dfb  push    rdi
0x180011dfc  push    r12
0x180011dfe  push    r14
0x180011e00  push    r15
0x180011e02  sub     rsp, 60h
0x180011e06  mov     rax, cs:__security_cookie
0x180011e0d  xor     rax, rsp
0x180011e10  mov     [rsp+88h+var_38], rax
0x180011e15  mov     rax, cs:?g_pmrc@@3PEAU_MRC_STRUCT@@EA; _MRC_STRUCT * g_pmrc
0x180011e1c  mov     rsi, rdx
0x180011e1f  mov     r14, [rax+40h]
0x180011e23  mov     rbp, [rax+28h]
0x180011e27  lea     rcx, [r14+8]; lpCriticalSection
0x180011e2b  call    cs:__imp_EnterCriticalSection
0x180011e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e38  lea     r12, WPP_GLOBAL_Control
0x180011e3f  cmp     rcx, r12
0x180011e42  jz      short loc_180011E62
0x180011e44  test    byte ptr [rcx+1Ch], 8
0x180011e48  jz      short loc_180011E62
0x180011e4a  mov     rcx, [rcx+10h]
0x180011e4e  lea     r8, WPP_81786cd8cf3b310d22fd5a7ce0f9edab_Traceguids
0x180011e55  mov     edx, 15h
0x180011e5a  mov     r9, rsi
0x180011e5d  call    WPP_SF_S
0x180011e62  xor     eax, eax
0x180011e64  xorps   xmm0, xmm0
0x180011e67  mov     [rsp+88h+var_40], rax
0x180011e6c  mov     rax, cs:?g_pmrc@@3PEAU_MRC_STRUCT@@EA; _MRC_STRUCT * g_pmrc
0x180011e73  movups  [rsp+88h+var_60], xmm0
0x180011e78  movups  [rsp+88h+var_50], xmm0
0x180011e7d  mov     rdi, [rax+28h]
0x180011e81  test    rdi, rdi
0x180011e84  jz      loc_180011F0A
0x180011e8a  cmp     dword ptr [rdi], 494E4445h
0x180011e90  jnz     short loc_180011F0A
0x180011e92  lea     rcx, [rdi+20h]; SRWLock
0x180011e96  xor     ebx, ebx
0x180011e98  call    cs:__imp_AcquireSRWLockShared
0x180011e9e  mov     rcx, [rdi+28h]
0x180011ea2  lea     r9, [rsp+88h+var_60]
0x180011ea7  mov     r8, rsi
0x180011eaa  xor     edx, edx
0x180011eac  call    cs:__imp_NdxTableObjectFromName
0x180011eb2  test    eax, eax
0x180011eb4  jnz     short loc_180011EFE
0x180011eb6  mov     rcx, [rdi+28h]
0x180011eba  lea     r9, [rsp+88h+var_60]
0x180011ebf  mov     r8, rsi
0x180011ec2  lea     edx, [rbx+1]
0x180011ec5  call    cs:__imp_NdxTableObjectFromName
0x180011ecb  test    eax, eax
0x180011ecd  jnz     short loc_180011EFE
0x180011ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ed6  cmp     rcx, r12
0x180011ed9  jz      short loc_180011EF9
0x180011edb  test    byte ptr [rcx+1Ch], 1
0x180011edf  jz      short loc_180011EF9
0x180011ee1  mov     rcx, [rcx+10h]
0x180011ee5  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180011eec  mov     edx, 9Ah
0x180011ef1  mov     r9, rsi
0x180011ef4  call    WPP_SF_S
0x180011ef9  mov     ebx, 490h
0x180011efe  lea     rcx, [rdi+20h]; SRWLock
0x180011f02  call    cs:__imp_ReleaseSRWLockShared
0x180011f08  jmp     short loc_180011F0F
0x180011f0a  mov     ebx, 57h ; 'W'
0x180011f0f  mov     eax, ebx
0x180011f11  or      eax, 80070000h
0x180011f16  test    ebx, ebx
0x180011f18  cmovnz  ebx, eax
0x180011f1b  test    ebx, ebx
0x180011f1d  js      short loc_180011F77
0x180011f1f  lea     rbx, [rbp+20h]
0x180011f23  mov     [rsp+88h+var_68], 0
0x180011f2b  mov     rcx, rbx; SRWLock
0x180011f2e  call    cs:__imp_AcquireSRWLockExclusive
0x180011f34  lea     rdx, [rsp+88h+var_68]
0x180011f39  lea     rcx, [rsp+88h+var_60]
0x180011f3e  call    cs:__imp_NdxTableGetObjectType
0x180011f44  test    eax, eax
0x180011f46  jnz     short loc_180011F58
0x180011f48  mov     rcx, rbx; SRWLock
0x180011f4b  call    cs:__imp_ReleaseSRWLockExclusive
0x180011f51  mov     ebx, 80004005h
0x180011f56  jmp     short loc_180011F77
0x180011f58  cmp     [rsp+88h+var_68], 1
0x180011f5d  jnz     short loc_180011F6C
0x180011f5f  lea     rdx, [rsp+88h+var_60]; struct NDX_OBJREF *
0x180011f64  mov     rcx, rbp; struct _INDEX_STRUCT *
0x180011f67  call    ?RemoveDataFromIndex@@YAXPEAU_INDEX_STRUCT@@PEAUNDX_OBJREF@@@Z; RemoveDataFromIndex(_INDEX_STRUCT *,NDX_OBJREF *)
0x180011f6c  mov     rcx, rbx; SRWLock
0x180011f6f  call    cs:__imp_ReleaseSRWLockExclusive
0x180011f75  xor     ebx, ebx
0x180011f77  lea     rcx, [r14+8]; lpCriticalSection
0x180011f7b  call    cs:__imp_LeaveCriticalSection
0x180011f81  mov     eax, ebx
0x180011f83  mov     rcx, [rsp+88h+var_38]
0x180011f88  xor     rcx, rsp; StackCookie
0x180011f8b  call    __security_check_cookie
0x180011f90  lea     r11, [rsp+88h+var_28]
0x180011f95  mov     rbx, [r11+30h]
0x180011f99  mov     rbp, [r11+40h]
0x180011f9d  mov     rsp, r11
0x180011fa0  pop     r15
0x180011fa2  pop     r14
0x180011fa4  pop     r12
0x180011fa6  pop     rdi
0x180011fa7  pop     rsi
0x180011fa8  retn
```
