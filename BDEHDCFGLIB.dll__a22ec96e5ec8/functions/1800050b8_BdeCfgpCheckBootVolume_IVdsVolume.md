# BdeCfgpCheckBootVolume(IVdsVolume *)

- ea: `0x1800050b8`
- end: `0x18000527c`
- name: `?BdeCfgpCheckBootVolume@@YAJPEAUIVdsVolume@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(struct IVdsVolume *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180004900`
- `0x180005024`

## callees

- `0x180003f68`
- `0x1800050b8`
- `0x180005284`
- `0x180005ce8`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800051bd`
- `ole32!CoTaskMemFree` at `0x18000525c`
- `ole32!CoTaskMemFree` at `0x1800051bd`
- `ole32!CoTaskMemFree` at `0x18000525c`

## pseudocode

```c
__int64 __fastcall BdeCfgpCheckBootVolume(struct IVdsVolume *a1)
{
  struct IVdsVolume *v2; // rdi
  int BasicVolumePartitionProperties; // ebx
  struct IVdsVolumeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetProperties)(IVdsVolume *, VDS_VOLUME_PROP *); // rax
  int FirstVolume; // eax
  struct IVdsVolume *v8; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v9; // [rsp+38h] [rbp-C8h] BYREF
  struct _VDS_PARTITION_PROP v10; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v11; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v12; // [rsp+E0h] [rbp-20h]
  __int128 v13; // [rsp+F0h] [rbp-10h]
  LPVOID pv; // [rsp+100h] [rbp+0h]

  v2 = 0;
  pv = 0;
  v8 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  memset_0(&v10, 0, sizeof(v10));
  v9 = 0;
  if ( !a1 )
  {
    BasicVolumePartitionProperties = -2147467261;
    goto LABEL_24;
  }
  BasicVolumePartitionProperties = BdeCfgGetBasicVolumePartitionProperties(a1, &v9, &v10);
  if ( BasicVolumePartitionProperties >= 0 )
  {
    if ( v10.PartitionStyle != VDS_PST_MBR )
    {
      BasicVolumePartitionProperties = -1063256060;
      goto LABEL_24;
    }
    if ( v10.Mbr.partitionType == 66 )
    {
      BasicVolumePartitionProperties = -1063256055;
      goto LABEL_24;
    }
    BasicVolumePartitionProperties = BdeCfgpCheckVolumeFileSystemAndSpace(a1, 0, 0, 0, 0);
    if ( BasicVolumePartitionProperties >= 0 )
    {
      pv = 0;
      lpVtbl = a1->lpVtbl;
      v11 = 0;
      v12 = 0;
      GetProperties = lpVtbl->GetProperties;
      v13 = 0;
      BasicVolumePartitionProperties = ((__int64 (__fastcall *)(struct IVdsVolume *, __int128 *))GetProperties)(
                                         a1,
                                         &v11);
      if ( BasicVolumePartitionProperties >= 0 )
      {
        if ( (BYTE8(v13) & 1) != 0 )
        {
          if ( (BYTE8(v13) & 4) != 0 )
            goto LABEL_24;
        }
        else
        {
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          FirstVolume = BdeCfgpFindFirstVolume(
                          (int (*)(struct IVdsVolume *, unsigned __int64))BdeCfgpFilterVolumesByFlags,
                          1u,
                          &v8);
          v2 = v8;
          BasicVolumePartitionProperties = FirstVolume;
          if ( FirstVolume < 0 )
            goto LABEL_22;
          if ( FirstVolume == 1 )
            goto LABEL_15;
          BasicVolumePartitionProperties = ((__int64 (__fastcall *)(struct IVdsVolume *, __int128 *))v8->lpVtbl->GetProperties)(
                                             v8,
                                             &v11);
          if ( BasicVolumePartitionProperties < 0 )
          {
LABEL_22:
            if ( v2 )
              ((void (__fastcall *)(struct IVdsVolume *))v2->lpVtbl->Release)(v2);
            goto LABEL_24;
          }
          if ( (BYTE8(v13) & 4) != 0 )
          {
            BasicVolumePartitionProperties = BdeCfgpCheckVolumeFileSystemAndSpace(v2, 0, 0, 0, 0);
            if ( BasicVolumePartitionProperties >= 0 )
            {
LABEL_15:
              BasicVolumePartitionProperties = -1063256062;
              goto LABEL_22;
            }
            goto LABEL_22;
          }
        }
        BasicVolumePartitionProperties = -1063256058;
        goto LABEL_22;
      }
    }
  }
LABEL_24:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)BasicVolumePartitionProperties;
}

```

## disassembly

```asm
0x1800050b8  push    rbp
0x1800050ba  push    rbx
0x1800050bb  push    rsi
0x1800050bc  push    rdi
0x1800050bd  lea     rbp, [rsp-18h]
0x1800050c2  sub     rsp, 118h
0x1800050c9  mov     rax, cs:__security_cookie
0x1800050d0  xor     rax, rsp
0x1800050d3  mov     [rbp+30h+var_28], rax
0x1800050d7  xorps   xmm0, xmm0
0x1800050da  mov     rsi, rcx
0x1800050dd  xor     eax, eax
0x1800050df  lea     rcx, [rsp+130h+var_F0]; void *
0x1800050e4  xor     edi, edi
0x1800050e6  mov     [rbp+30h+pv], rax
0x1800050ea  xor     edx, edx; Val
0x1800050ec  mov     [rsp+130h+var_100], rdi
0x1800050f1  mov     r8d, 90h; Size
0x1800050f7  movups  [rbp+30h+var_60], xmm0
0x1800050fb  movups  [rbp+30h+var_50], xmm0
0x1800050ff  movups  [rbp+30h+var_40], xmm0
0x180005103  call    memset_0
0x180005108  mov     [rsp+130h+var_F8], edi
0x18000510c  test    rsi, rsi
0x18000510f  jnz     short loc_18000511B
0x180005111  mov     ebx, 80004003h
0x180005116  jmp     loc_180005253
0x18000511b  lea     r8, [rsp+130h+var_F0]; struct _VDS_PARTITION_PROP *
0x180005120  mov     rcx, rsi; struct IVdsVolume *
0x180005123  lea     rdx, [rsp+130h+var_F8]; unsigned int *
0x180005128  call    ?BdeCfgGetBasicVolumePartitionProperties@@YAJPEAUIVdsVolume@@PEAKPEAU_VDS_PARTITION_PROP@@@Z; BdeCfgGetBasicVolumePartitionProperties(IVdsVolume *,ulong *,_VDS_PARTITION_PROP *)
0x18000512d  mov     ebx, eax
0x18000512f  test    eax, eax
0x180005131  js      loc_180005253
0x180005137  cmp     [rsp+130h+var_F0.PartitionStyle], 1
0x18000513c  jz      short loc_180005148
0x18000513e  mov     ebx, 0C0A00004h
0x180005143  jmp     loc_180005253
0x180005148  cmp     byte ptr [rsp+130h+var_F0.20h], 42h ; 'B'
0x18000514d  jnz     short loc_180005159
0x18000514f  mov     ebx, 0C0A00009h
0x180005154  jmp     loc_180005253
0x180005159  xor     r9d, r9d; int
0x18000515c  mov     [rsp+130h+var_110], rdi; unsigned __int64 *
0x180005161  xor     r8d, r8d; struct _BDECFG_SIZE_REQUIREMENTS *
0x180005164  xor     edx, edx; unsigned __int64
0x180005166  mov     rcx, rsi; struct IVdsVolume *
0x180005169  call    ?BdeCfgpCheckVolumeFileSystemAndSpace@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@HPEA_K@Z; BdeCfgpCheckVolumeFileSystemAndSpace(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,int,unsigned __int64 *)
0x18000516e  mov     ebx, eax
0x180005170  test    eax, eax
0x180005172  js      loc_180005253
0x180005178  xor     eax, eax
0x18000517a  lea     rdx, [rbp+30h+var_60]
0x18000517e  xorps   xmm0, xmm0
0x180005181  mov     [rbp+30h+pv], rax
0x180005185  mov     rax, [rsi]
0x180005188  mov     rcx, rsi
0x18000518b  movups  [rbp+30h+var_60], xmm0
0x18000518f  movups  [rbp+30h+var_50], xmm0
0x180005193  mov     rax, [rax+18h]
0x180005197  movups  [rbp+30h+var_40], xmm0
0x18000519b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a0  mov     ebx, eax
0x1800051a2  test    eax, eax
0x1800051a4  js      loc_180005253
0x1800051aa  test    byte ptr [rbp+30h+var_40+8], 1
0x1800051ae  jnz     loc_180005234
0x1800051b4  mov     rcx, [rbp+30h+pv]; pv
0x1800051b8  test    rcx, rcx
0x1800051bb  jz      short loc_1800051C7
0x1800051bd  call    cs:__imp_CoTaskMemFree
0x1800051c3  mov     [rbp+30h+pv], rdi
0x1800051c7  lea     r8, [rsp+130h+var_100]; struct IVdsVolume **
0x1800051cc  mov     edx, 1; unsigned __int64
0x1800051d1  lea     rcx, ?BdeCfgpFilterVolumesByFlags@@YAHPEAUIVdsVolume@@_K@Z; int (*)(struct IVdsVolume *, unsigned __int64)
0x1800051d8  call    ?BdeCfgpFindFirstVolume@@YAJP6AHPEAUIVdsVolume@@_K@Z1PEAPEAU1@@Z; BdeCfgpFindFirstVolume(int (*)(IVdsVolume *,unsigned __int64),unsigned __int64,IVdsVolume * *)
0x1800051dd  mov     rdi, [rsp+130h+var_100]
0x1800051e2  mov     ebx, eax
0x1800051e4  test    eax, eax
0x1800051e6  js      short loc_18000523F
0x1800051e8  cmp     eax, 1
0x1800051eb  jnz     short loc_1800051F4
0x1800051ed  mov     ebx, 0C0A00002h
0x1800051f2  jmp     short loc_18000523F
0x1800051f4  mov     rax, [rdi]
0x1800051f7  lea     rdx, [rbp+30h+var_60]
0x1800051fb  mov     rcx, rdi
0x1800051fe  mov     rax, [rax+18h]
0x180005202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005207  mov     ebx, eax
0x180005209  test    eax, eax
0x18000520b  js      short loc_18000523F
0x18000520d  test    byte ptr [rbp+30h+var_40+8], 4
0x180005211  jz      short loc_18000523A
0x180005213  xor     r9d, r9d; int
0x180005216  mov     [rsp+130h+var_110], 0; unsigned __int64 *
0x18000521f  xor     r8d, r8d; struct _BDECFG_SIZE_REQUIREMENTS *
0x180005222  xor     edx, edx; unsigned __int64
0x180005224  mov     rcx, rdi; struct IVdsVolume *
0x180005227  call    ?BdeCfgpCheckVolumeFileSystemAndSpace@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@HPEA_K@Z; BdeCfgpCheckVolumeFileSystemAndSpace(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,int,unsigned __int64 *)
0x18000522c  mov     ebx, eax
0x18000522e  test    eax, eax
0x180005230  js      short loc_18000523F
0x180005232  jmp     short loc_1800051ED
0x180005234  test    byte ptr [rbp+30h+var_40+8], 4
0x180005238  jnz     short loc_180005253
0x18000523a  mov     ebx, 0C0A00006h
0x18000523f  test    rdi, rdi
0x180005242  jz      short loc_180005253
0x180005244  mov     rax, [rdi]
0x180005247  mov     rcx, rdi
0x18000524a  mov     rax, [rax+10h]
0x18000524e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005253  mov     rcx, [rbp+30h+pv]; pv
0x180005257  test    rcx, rcx
0x18000525a  jz      short loc_180005262
0x18000525c  call    cs:__imp_CoTaskMemFree
0x180005262  mov     eax, ebx
0x180005264  mov     rcx, [rbp+30h+var_28]
0x180005268  xor     rcx, rsp; StackCookie
0x18000526b  call    __security_check_cookie
0x180005270  add     rsp, 118h
0x180005277  pop     rdi
0x180005278  pop     rsi
0x180005279  pop     rbx
0x18000527a  pop     rbp
0x18000527b  retn
```
