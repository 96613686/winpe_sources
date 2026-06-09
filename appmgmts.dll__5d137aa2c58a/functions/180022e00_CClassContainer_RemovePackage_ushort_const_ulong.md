# CClassContainer::RemovePackage(ushort const *,ulong)

- ea: `0x180022e00`
- end: `0x18002303b`
- name: `?RemovePackage@CClassContainer@@UEAAJPEBGK@Z`
- size: `571`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x1800016d0`
- `0x18001d130`
- `0x1800205f4`
- `0x180021fa0`
- `0x180022e00`
- `0x180023448`
- `0x18002350c`
- `0x180024260`
- `0x18002435c`
- `0x180024458`
- `0x180026f3c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fe1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002300d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fe1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002300d`
- `adsldpc!ADSICloseDSObject` at `0x180022fcd`
- `adsldpc!ADSICloseDSObject` at `0x180022fcd`
- `adsldpc!ADSISetObjectAttributes` at `0x180022fbb`
- `adsldpc!ADSISetObjectAttributes` at `0x180022fbb`

## string_xrefs

- `0x180022f97`: `lastUpdateSequence`
- `0x180022f64`: `msiScriptName`

## pseudocode

```c
__int64 __fastcall CClassContainer::RemovePackage(const unsigned __int16 **this, const unsigned __int16 *a2, int a3)
{
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  int ConsistentPackageFlags; // ebx
  unsigned int v9; // eax
  unsigned int v10; // r14d
  unsigned int v11; // r14d
  __int64 v12; // rdx
  unsigned int v13; // edi
  unsigned __int16 *v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-B8h] BYREF
  void *v16; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct _ads_attr_info v19; // [rsp+70h] [rbp-90h] BYREF
  struct _ads_attr_info v20; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v21; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v22[20]; // [rsp+158h] [rbp+58h] BYREF

  LODWORD(v14) = a3;
  v17 = 0;
  v16 = 0;
  v18[0] = 0;
  if ( a3 && (a3 & 0x180) == 0 )
    return 2147942487LL;
  v6 = (*((__int64 (__fastcall **)(const unsigned __int16 **, const unsigned __int16 *, HLOCAL *))*this + 19))(
         this,
         a2,
         &v17);
  ConsistentPackageFlags = v6;
  if ( v6 >= 0 )
  {
    if ( v6 )
      return 2147746153LL;
    if ( a3 )
    {
      v15 = 0;
      GetCurrentUsn(v22);
      if ( (gCsOptions & 1) != 0 )
        v9 = GetADsOpenObjectFlags() | 0x21;
      else
        v9 = 101;
      ConsistentPackageFlags = DSServerOpenDSObject(this + 74, (const unsigned __int16 *)v17, v9, &v16);
      if ( ConsistentPackageFlags >= 0 )
      {
        ConsistentPackageFlags = GetConsistentPackageFlags(v16, (unsigned int *)&v14, 0, 0, 0, &v15, &v21);
        if ( ConsistentPackageFlags >= 0 )
        {
          LODWORD(v14) = v15;
          PackDWArrToAttr(&v19, (WCHAR *)L"packageFlags", (unsigned int *)&v14, 1u);
          v10 = 1;
          if ( v21 )
          {
            v14 = &v21;
            PackStrArrToAttr(&v20, (WCHAR *)L"msiScriptName", &v14, 1u);
            v10 = 2;
          }
          v14 = v22;
          PackStrArrToAttr(&v19 + v10, (WCHAR *)L"lastUpdateSequence", &v14, 1u);
          v11 = v10 + 1;
          ConsistentPackageFlags = ADSISetObjectAttributes(v16, &v19, v11, v18);
          if ( v16 )
            ADSICloseDSObject(v16, v12);
          v13 = 0;
          do
            LocalFree(*((HLOCAL *)&v19.pADsValues + 4 * v13++));
          while ( v13 < v11 );
          if ( ConsistentPackageFlags >= 0 )
            UpdateStoreUsn((void *)this[69], v22);
        }
      }
    }
    else
    {
      ConsistentPackageFlags = CClassContainer::DeletePackage((CClassContainer *)this, (unsigned __int16 *)v17);
    }
  }
  if ( v17 )
    LocalFree(v17);
  return RemapErrorCode(ConsistentPackageFlags, v7);
}

```

## disassembly

```asm
0x180022e00  push    rbp
0x180022e02  push    rbx
0x180022e03  push    rsi
0x180022e04  push    rdi
0x180022e05  push    r12
0x180022e07  push    r14
0x180022e09  push    r15
0x180022e0b  lea     rbp, [rsp-90h]
0x180022e13  sub     rsp, 190h
0x180022e1a  mov     rax, cs:__security_cookie
0x180022e21  xor     rax, rsp
0x180022e24  mov     [rbp+0C0h+var_40], rax
0x180022e2b  xor     r15d, r15d
0x180022e2e  mov     dword ptr [rsp+1C0h+var_180], r8d
0x180022e33  mov     [rsp+1C0h+var_168], r15
0x180022e38  mov     edi, r8d
0x180022e3b  mov     [rsp+1C0h+var_170], r15
0x180022e40  mov     rsi, rcx
0x180022e43  mov     [rsp+1C0h+var_160], r15d
0x180022e48  test    r8d, r8d
0x180022e4b  jz      short loc_180022E60
0x180022e4d  test    r8d, 180h
0x180022e54  jnz     short loc_180022E60
0x180022e56  mov     eax, 80070057h
0x180022e5b  jmp     loc_18002301A
0x180022e60  mov     rax, [rcx]
0x180022e63  lea     r8, [rsp+1C0h+var_168]
0x180022e68  mov     rax, [rax+98h]
0x180022e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e74  mov     ebx, eax
0x180022e76  test    eax, eax
0x180022e78  js      loc_180023003
0x180022e7e  jz      short loc_180022E8A
0x180022e80  mov     eax, 80040169h
0x180022e85  jmp     loc_18002301A
0x180022e8a  test    edi, edi
0x180022e8c  jnz     short loc_180022EA2
0x180022e8e  mov     rdx, [rsp+1C0h+var_168]; unsigned __int16 *
0x180022e93  mov     rcx, rsi; this
0x180022e96  call    ?DeletePackage@CClassContainer@@QEAAJPEBG@Z; CClassContainer::DeletePackage(ushort const *)
0x180022e9b  mov     ebx, eax
0x180022e9d  jmp     loc_180023003
0x180022ea2  lea     rcx, [rbp+0C0h+var_68]; unsigned __int16 *
0x180022ea6  mov     [rsp+1C0h+var_178], r15d
0x180022eab  call    ?GetCurrentUsn@@YAXPEAG@Z; GetCurrentUsn(ushort *)
0x180022eb0  mov     r12d, 1
0x180022eb6  test    byte ptr cs:?gCsOptions@@3KA, r12b; ulong gCsOptions
0x180022ebd  jz      short loc_180022EC9
0x180022ebf  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x180022ec4  or      eax, 21h
0x180022ec7  jmp     short loc_180022ECE
0x180022ec9  mov     eax, 65h ; 'e'
0x180022ece  mov     rdx, [rsp+1C0h+var_168]; unsigned __int16 *
0x180022ed3  lea     rcx, [rsi+250h]; struct CServerContext *
0x180022eda  lea     r9, [rsp+1C0h+var_170]; void **
0x180022edf  mov     r8d, eax; int
0x180022ee2  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180022ee7  mov     ebx, eax
0x180022ee9  test    eax, eax
0x180022eeb  js      loc_180023003
0x180022ef1  mov     rcx, [rsp+1C0h+var_170]; void *
0x180022ef6  lea     rax, [rbp+0C0h+var_70]
0x180022efa  mov     [rsp+1C0h+var_190], rax; unsigned __int16 *
0x180022eff  lea     rdx, [rsp+1C0h+var_180]; unsigned int *
0x180022f04  lea     rax, [rsp+1C0h+var_178]
0x180022f09  xor     r9d, r9d; unsigned int *
0x180022f0c  mov     [rsp+1C0h+var_198], rax; unsigned int *
0x180022f11  xor     r8d, r8d; unsigned int *
0x180022f14  mov     [rsp+1C0h+var_1A0], r15; enum _CLASSPATHTYPE *
0x180022f19  call    ?GetConsistentPackageFlags@@YAJPEAXPEAKPEAI2PEAW4_CLASSPATHTYPE@@1PEAG@Z; GetConsistentPackageFlags(void *,ulong *,uint *,uint *,_CLASSPATHTYPE *,ulong *,ushort *)
0x180022f1e  mov     ebx, eax
0x180022f20  test    eax, eax
0x180022f22  js      loc_180023003
0x180022f28  mov     eax, [rsp+1C0h+var_178]
0x180022f2c  lea     r8, [rsp+1C0h+var_180]; unsigned int *
0x180022f31  mov     r9d, r12d; unsigned int
0x180022f34  mov     dword ptr [rsp+1C0h+var_180], eax
0x180022f38  lea     rdx, aPackageflags; "packageFlags"
0x180022f3f  lea     rcx, [rsp+1C0h+var_150]; struct _ads_attr_info *
0x180022f44  call    ?PackDWArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAKK@Z; PackDWArrToAttr(_ads_attr_info *,ushort const *,ulong *,ulong)
0x180022f49  mov     r14d, r12d
0x180022f4c  cmp     [rbp+0C0h+var_70], r15w
0x180022f51  jz      short loc_180022F7A
0x180022f53  lea     rax, [rbp+0C0h+var_70]
0x180022f57  mov     r9d, r12d; unsigned int
0x180022f5a  lea     r8, [rsp+1C0h+var_180]; unsigned __int16 **
0x180022f5f  mov     [rsp+1C0h+var_180], rax
0x180022f64  lea     rdx, aMsiscriptname; "msiScriptName"
0x180022f6b  lea     rcx, [rbp+0C0h+var_130]; struct _ads_attr_info *
0x180022f6f  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x180022f74  mov     r14d, 2
0x180022f7a  lea     rax, [rbp+0C0h+var_68]
0x180022f7e  mov     r9d, r12d; unsigned int
0x180022f81  mov     [rsp+1C0h+var_180], rax
0x180022f86  lea     rcx, [rsp+1C0h+var_150]
0x180022f8b  mov     eax, r14d
0x180022f8e  lea     r8, [rsp+1C0h+var_180]; unsigned __int16 **
0x180022f93  shl     rax, 5
0x180022f97  lea     rdx, aLastupdatesequ; "lastUpdateSequence"
0x180022f9e  add     rcx, rax; struct _ads_attr_info *
0x180022fa1  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x180022fa6  mov     rcx, [rsp+1C0h+var_170]
0x180022fab  lea     r9, [rsp+1C0h+var_160]
0x180022fb0  add     r14d, r12d
0x180022fb3  lea     rdx, [rsp+1C0h+var_150]
0x180022fb8  mov     r8d, r14d
0x180022fbb  call    cs:__imp_ADSISetObjectAttributes
0x180022fc1  mov     rcx, [rsp+1C0h+var_170]
0x180022fc6  mov     ebx, eax
0x180022fc8  test    rcx, rcx
0x180022fcb  jz      short loc_180022FD3
0x180022fcd  call    cs:__imp_ADSICloseDSObject
0x180022fd3  mov     edi, r15d
0x180022fd6  mov     ecx, edi
0x180022fd8  shl     rcx, 5
0x180022fdc  mov     rcx, [rbp+rcx+0C0h+var_150.pADsValues]; hMem
0x180022fe1  call    cs:__imp_LocalFree
0x180022fe7  add     edi, r12d
0x180022fea  cmp     edi, r14d
0x180022fed  jb      short loc_180022FD6
0x180022fef  test    ebx, ebx
0x180022ff1  js      short loc_180023003
0x180022ff3  mov     rcx, [rsi+228h]; void *
0x180022ffa  lea     rdx, [rbp+0C0h+var_68]; unsigned __int16 *
0x180022ffe  call    ?UpdateStoreUsn@@YAJPEAXPEBG@Z; UpdateStoreUsn(void *,ushort const *)
0x180023003  mov     rcx, [rsp+1C0h+var_168]; hMem
0x180023008  test    rcx, rcx
0x18002300b  jz      short loc_180023013
0x18002300d  call    cs:__imp_LocalFree
0x180023013  mov     ecx, ebx; int
0x180023015  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x18002301a  mov     rcx, [rbp+0C0h+var_40]
0x180023021  xor     rcx, rsp; StackCookie
0x180023024  call    __security_check_cookie
0x180023029  add     rsp, 190h
0x180023030  pop     r15
0x180023032  pop     r14
0x180023034  pop     r12
0x180023036  pop     rdi
0x180023037  pop     rsi
0x180023038  pop     rbx
0x180023039  pop     rbp
0x18002303a  retn
```
