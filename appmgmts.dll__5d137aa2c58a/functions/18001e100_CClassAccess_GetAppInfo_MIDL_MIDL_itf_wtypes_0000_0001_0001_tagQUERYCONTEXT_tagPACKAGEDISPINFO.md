# CClassAccess::GetAppInfo(__MIDL___MIDL_itf_wtypes_0000_0001_0001 *,tagQUERYCONTEXT *,tagPACKAGEDISPINFO *)

- ea: `0x18001e100`
- end: `0x18001e2e4`
- name: `?GetAppInfo@CClassAccess@@UEAAJPEAU__MIDL___MIDL_itf_wtypes_0000_0001_0001@@PEAUtagQUERYCONTEXT@@PEAUtagPACKAGEDISPINFO@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(CClassAccess *this, struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *, struct tagQUERYCONTEXT *, struct tagPACKAGEDISPINFO *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800016d0`
- `0x180002024`
- `0x18001b780`
- `0x18001e100`
- `0x18001e2ec`
- `0x18001e4d0`
- `0x180028c90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e2b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e2b4`

## pseudocode

```c
__int64 __fastcall CClassAccess::GetAppInfo(
        CClassAccess *this,
        struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *a2,
        struct tagQUERYCONTEXT *a3,
        struct tagPACKAGEDISPINFO *a4)
{
  unsigned int v4; // r15d
  HLOCAL v5; // rdi
  struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *v7; // r13
  int v10; // r12d
  __int128 v11; // xmm1
  int UserClassStores; // eax
  int v13; // ebx
  unsigned int v14; // ecx
  struct IClassAccess *NextValidClassStore; // rax
  struct IClassAccess *v16; // r13
  unsigned int v17; // [rsp+40h] [rbp-39h] BYREF
  int v18; // [rsp+44h] [rbp-35h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-31h] BYREF
  struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *v20; // [rsp+50h] [rbp-29h]
  struct tagPACKAGEDISPINFO *v21; // [rsp+58h] [rbp-21h]
  struct tagCSPLATFORM v22; // [rsp+60h] [rbp-19h] BYREF
  __int128 v23; // [rsp+70h] [rbp-9h]

  v4 = 0;
  v20 = a2;
  v5 = 0;
  v18 = 0;
  v17 = 0;
  hMem = 0;
  v21 = a4;
  v7 = a2;
  v22 = 0;
  v23 = 0;
  if ( !a4 )
    return 2147942487LL;
  v10 = 0;
  memset_0(a4, 0, 0xD0u);
  if ( a3 )
  {
    v11 = *(_OWORD *)&a3->Platform.dwProcessorArch;
    v22 = *(struct tagCSPLATFORM *)&a3->dwContext;
    v23 = v11;
  }
  else
  {
    v22.dwPlatformId = 23;
    GetDefaultPlatform((struct tagCSPLATFORM *)&v22.dwVersionHi, 0, 0);
    *(_QWORD *)((char *)&v23 + 4) = 0xFFFFFFFF00000800uLL;
    HIDWORD(v23) = -1;
  }
  if ( gDebug )
    PrintClassSpec(v7);
  if ( *((_QWORD *)this + 1) )
    goto LABEL_11;
  UserClassStores = GetUserClassStores(
                      *((const unsigned __int16 **)this + 3),
                      (struct tagCLASSCONTAINER ***)this + 1,
                      (unsigned int *)this + 4,
                      (int *)&v17,
                      &hMem);
  v5 = hMem;
  v13 = UserClassStores;
  v18 = UserClassStores;
  if ( UserClassStores >= 0 )
  {
    v4 = v17;
LABEL_11:
    v14 = *((_DWORD *)this + 4);
    v17 = 0;
    if ( v14 )
    {
      while ( 1 )
      {
        NextValidClassStore = GetNextValidClassStore(
                                *((struct tagCLASSCONTAINER ***)this + 1),
                                v14,
                                v5,
                                0,
                                v7,
                                v4,
                                &v17,
                                &v18);
        v16 = NextValidClassStore;
        if ( !NextValidClassStore )
          return (unsigned int)v18;
        v13 = (*(__int64 (__fastcall **)(struct IClassAccess *, struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *, struct tagCSPLATFORM *, struct tagPACKAGEDISPINFO *))(*(_QWORD *)NextValidClassStore + 24LL))(
                NextValidClassStore,
                v20,
                &v22,
                v21);
        (*(void (__fastcall **)(struct IClassAccess *))(*(_QWORD *)v16 + 16LL))(v16);
        if ( v13 != -2147221143 )
          break;
        v14 = *((_DWORD *)this + 4);
        v18 = 0;
        if ( ++v17 >= v14 )
          goto LABEL_19;
        v7 = v20;
      }
      if ( v13 >= 0 )
        v10 = 1;
    }
    else
    {
LABEL_19:
      v13 = -2147221148;
    }
  }
  if ( v5 )
    LocalFree(v5);
  if ( v10 )
    return 0;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001e100  push    rbp
0x18001e102  push    rbx
0x18001e103  push    rsi
0x18001e104  push    rdi
0x18001e105  push    r12
0x18001e107  push    r13
0x18001e109  push    r14
0x18001e10b  push    r15
0x18001e10d  lea     rbp, [rsp-1Fh]
0x18001e112  sub     rsp, 98h
0x18001e119  mov     rax, cs:__security_cookie
0x18001e120  xor     rax, rsp
0x18001e123  mov     [rbp+57h+var_50], rax
0x18001e127  xor     r15d, r15d
0x18001e12a  mov     [rbp+57h+var_80], rdx
0x18001e12e  xor     edi, edi
0x18001e130  mov     [rbp+57h+var_8C], 0
0x18001e137  mov     [rbp+57h+var_90], r15d
0x18001e13b  xorps   xmm0, xmm0
0x18001e13e  mov     [rbp+57h+hMem], rdi
0x18001e142  mov     rax, r9
0x18001e145  mov     [rbp+57h+var_78], rax
0x18001e149  mov     rbx, r8
0x18001e14c  mov     r13, rdx
0x18001e14f  mov     rsi, rcx
0x18001e152  movups  xmmword ptr [rbp+57h+var_70.dwPlatformId], xmm0
0x18001e156  movups  [rbp+57h+var_60], xmm0
0x18001e15a  test    r9, r9
0x18001e15d  jnz     short loc_18001E169
0x18001e15f  mov     eax, 80070057h
0x18001e164  jmp     loc_18001E2C4
0x18001e169  xor     edx, edx; Val
0x18001e16b  mov     r8d, 0D0h; Size
0x18001e171  mov     rcx, rax; void *
0x18001e174  xor     r12d, r12d
0x18001e177  call    memset_0
0x18001e17c  test    rbx, rbx
0x18001e17f  jz      short loc_18001E192
0x18001e181  movups  xmm0, xmmword ptr [rbx]
0x18001e184  movups  xmm1, xmmword ptr [rbx+10h]
0x18001e188  movups  xmmword ptr [rbp+57h+var_70.dwPlatformId], xmm0
0x18001e18c  movups  [rbp+57h+var_60], xmm1
0x18001e190  jmp     short loc_18001E1B7
0x18001e192  xor     r8d, r8d; int
0x18001e195  mov     [rbp+57h+var_70.dwPlatformId], 17h
0x18001e19c  xor     edx, edx; int
0x18001e19e  lea     rcx, [rbp+57h+var_70.dwVersionHi]; struct tagCSPLATFORM *
0x18001e1a2  call    ?GetDefaultPlatform@@YAXPEAUtagCSPLATFORM@@HJ@Z; GetDefaultPlatform(tagCSPLATFORM *,int,long)
0x18001e1a7  or      eax, 0FFFFFFFFh
0x18001e1aa  mov     dword ptr [rbp+57h+var_60+4], 800h
0x18001e1b1  mov     dword ptr [rbp+57h+var_60+8], eax
0x18001e1b4  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x18001e1b7  cmp     cs:?gDebug@@3KA, edi; ulong gDebug
0x18001e1bd  jz      short loc_18001E1C7
0x18001e1bf  mov     rcx, r13; struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *
0x18001e1c2  call    ?PrintClassSpec@@YAXPEAU__MIDL___MIDL_itf_wtypes_0000_0001_0001@@@Z; PrintClassSpec(__MIDL___MIDL_itf_wtypes_0000_0001_0001 *)
0x18001e1c7  lea     r14, [rsi+8]
0x18001e1cb  cmp     [r14], rdi
0x18001e1ce  jnz     short loc_18001E202
0x18001e1d0  mov     rcx, [rsi+18h]; unsigned __int16 *
0x18001e1d4  lea     rax, [rbp+57h+hMem]
0x18001e1d8  lea     r8, [rsi+10h]; unsigned int *
0x18001e1dc  mov     [rsp+0D0h+var_B0], rax; void **
0x18001e1e1  lea     r9, [rbp+57h+var_90]; int *
0x18001e1e5  mov     rdx, r14; struct tagCLASSCONTAINER ***
0x18001e1e8  call    ?GetUserClassStores@@YAJPEBGPEAPEAPEAUtagCLASSCONTAINER@@PEAKPEAHPEAPEAX@Z; GetUserClassStores(ushort const *,tagCLASSCONTAINER * * *,ulong *,int *,void * *)
0x18001e1ed  mov     rdi, [rbp+57h+hMem]
0x18001e1f1  mov     ebx, eax
0x18001e1f3  mov     [rbp+57h+var_8C], eax
0x18001e1f6  test    eax, eax
0x18001e1f8  js      loc_18001E2AC
0x18001e1fe  mov     r15d, [rbp+57h+var_90]
0x18001e202  mov     ecx, [rsi+10h]
0x18001e205  mov     [rbp+57h+var_90], r12d
0x18001e209  test    ecx, ecx
0x18001e20b  jz      loc_18001E2A7
0x18001e211  lea     rax, [rbp+57h+var_8C]
0x18001e215  mov     edx, ecx; unsigned int
0x18001e217  mov     rcx, [r14]; struct tagCLASSCONTAINER **
0x18001e21a  xor     r9d, r9d; void *
0x18001e21d  mov     [rsp+0D0h+var_98], rax; int *
0x18001e222  mov     r8, rdi; void *
0x18001e225  lea     rax, [rbp+57h+var_90]
0x18001e229  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x18001e22e  mov     [rsp+0D0h+var_A8], r15d; int
0x18001e233  mov     [rsp+0D0h+var_B0], r13; struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *
0x18001e238  call    ?GetNextValidClassStore@@YAPEAUIClassAccess@@PEAPEAUtagCLASSCONTAINER@@KPEAX1PEAU__MIDL___MIDL_itf_wtypes_0000_0001_0001@@HPEAKPEAJ@Z; GetNextValidClassStore(tagCLASSCONTAINER * *,ulong,void *,void *,__MIDL___MIDL_itf_wtypes_0000_0001_0001 *,int,ulong *,long *)
0x18001e23d  mov     r13, rax
0x18001e240  test    rax, rax
0x18001e243  jz      short loc_18001E2A2
0x18001e245  mov     rcx, [rax]
0x18001e248  lea     r8, [rbp+57h+var_70]
0x18001e24c  mov     r9, [rbp+57h+var_78]
0x18001e250  mov     rdx, [rbp+57h+var_80]
0x18001e254  mov     rax, [rcx+18h]
0x18001e258  mov     rcx, r13
0x18001e25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e260  mov     rcx, [r13+0]
0x18001e264  mov     ebx, eax
0x18001e266  mov     rax, [rcx+10h]
0x18001e26a  mov     rcx, r13
0x18001e26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e272  cmp     ebx, 80040169h
0x18001e278  jnz     short loc_18001E296
0x18001e27a  mov     eax, [rbp+57h+var_90]
0x18001e27d  mov     ecx, [rsi+10h]
0x18001e280  inc     eax
0x18001e282  mov     [rbp+57h+var_8C], r12d
0x18001e286  mov     [rbp+57h+var_90], eax
0x18001e289  cmp     eax, ecx
0x18001e28b  jnb     short loc_18001E2A7
0x18001e28d  mov     r13, [rbp+57h+var_80]
0x18001e291  jmp     loc_18001E211
0x18001e296  test    ebx, ebx
0x18001e298  js      short loc_18001E2AC
0x18001e29a  mov     r12d, 1
0x18001e2a0  jmp     short loc_18001E2AC
0x18001e2a2  mov     eax, [rbp+57h+var_8C]
0x18001e2a5  jmp     short loc_18001E2C4
0x18001e2a7  mov     ebx, 80040164h
0x18001e2ac  test    rdi, rdi
0x18001e2af  jz      short loc_18001E2BA
0x18001e2b1  mov     rcx, rdi; hMem
0x18001e2b4  call    cs:__imp_LocalFree
0x18001e2ba  xor     eax, eax
0x18001e2bc  test    r12d, r12d
0x18001e2bf  cmovnz  ebx, eax
0x18001e2c2  mov     eax, ebx
0x18001e2c4  mov     rcx, [rbp+57h+var_50]
0x18001e2c8  xor     rcx, rsp; StackCookie
0x18001e2cb  call    __security_check_cookie
0x18001e2d0  add     rsp, 98h
0x18001e2d7  pop     r15
0x18001e2d9  pop     r14
0x18001e2db  pop     r13
0x18001e2dd  pop     r12
0x18001e2df  pop     rdi
0x18001e2e0  pop     rsi
0x18001e2e1  pop     rbx
0x18001e2e2  pop     rbp
0x18001e2e3  retn
```
