# BdeCfgCreatePrimaryPartition(IVdsDisk *,unsigned __int64,unsigned __int64,IVdsVolume * *)

- ea: `0x180002d24`
- end: `0x180002f4e`
- name: `?BdeCfgCreatePrimaryPartition@@YAJPEAUIVdsDisk@@_K1PEAPEAUIVdsVolume@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct IVdsDisk *, unsigned __int64, unsigned __int64, struct IVdsVolume **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800101a0`

## callees

- `0x180002d24`
- `0x180002f54`
- `0x180004620`
- `0x180006b2c`
- `0x180013576`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall BdeCfgCreatePrimaryPartition(
        struct IVdsDisk *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        struct IVdsVolume **a4)
{
  int VolumeFromId; // ebx
  struct IVdsDiskVtbl *lpVtbl; // rax
  struct _GUID v11; // xmm6
  __int64 v12; // [rsp+48h] [rbp-C0h] BYREF
  struct IVdsCreatePartitionEx *v13; // [rsp+50h] [rbp-B8h] BYREF
  struct IVdsAsync *v14; // [rsp+58h] [rbp-B0h] BYREF
  struct _GUID Buf1_8; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+78h] [rbp-90h] BYREF
  struct _GUID v17; // [rsp+88h] [rbp-80h]
  _CREATE_PARTITION_PARAMETERS v18; // [rsp+98h] [rbp-70h] BYREF
  struct _VDS_DISK_PROP v19; // [rsp+118h] [rbp+10h] BYREF

  LODWORD(v12) = 0;
  v14 = 0;
  v13 = 0;
  v16 = 0;
  v17 = 0;
  memset_0(&v18, 0, sizeof(v18));
  memset_0(&v19, 0, sizeof(v19));
  if ( !g_pService )
    return 3231711254LL;
  VolumeFromId = ((__int64 (__fastcall *)(struct IVdsDisk *, struct _VDS_DISK_PROP *))a1->lpVtbl->GetProperties)(
                   a1,
                   &v19);
  if ( VolumeFromId >= 0 )
  {
    v18.style = v19.PartitionStyle;
    if ( v19.PartitionStyle == VDS_PST_MBR )
    {
      lpVtbl = a1->lpVtbl;
      v18.MbrPartInfo = (struct _CREATE_PARTITION_PARAMETERS::$A71E5AAC677011770F084007E8ED09B8::$03861C86D548754335BA7BF7577B1ADA)7;
      VolumeFromId = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, struct IVdsCreatePartitionEx **))lpVtbl->QueryInterface)(
                       a1,
                       &IID_IVdsCreatePartitionEx,
                       &v13);
      if ( VolumeFromId >= 0 )
      {
        VolumeFromId = ((__int64 (__fastcall *)(struct IVdsCreatePartitionEx *, unsigned __int64, unsigned __int64, _QWORD, _CREATE_PARTITION_PARAMETERS *, struct IVdsAsync **))v13->lpVtbl->CreatePartitionEx)(
                         v13,
                         a2,
                         a3,
                         0,
                         &v18,
                         &v14);
        if ( VolumeFromId == -2147212273 )
          VolumeFromId = BdeCfgCreatePrimaryPartitionAdjustedSize(v13, &v18, &v14, a2, a3, v19.ullSize);
        if ( VolumeFromId >= 0 )
        {
          VolumeFromId = ((__int64 (__fastcall *)(struct IVdsAsync *, __int64 *, __int128 *))v14->lpVtbl->Wait)(
                           v14,
                           &v12,
                           &v16);
          if ( VolumeFromId >= 0 )
          {
            VolumeFromId = v12;
            if ( (int)v12 >= 0 )
            {
              v11 = v17;
              Buf1_8 = v17;
              if ( !memcmp_0(&Buf1_8, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
              {
                VolumeFromId = -1063256037;
              }
              else
              {
                Buf1_8 = v11;
                VolumeFromId = BdeCfgGetVolumeFromId(&Buf1_8, a4);
              }
            }
          }
        }
      }
    }
    else
    {
      VolumeFromId = -1063256060;
    }
  }
  if ( v13 )
  {
    ((void (__fastcall *)(struct IVdsCreatePartitionEx *))v13->lpVtbl->Release)(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IVdsAsync *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  SAFE_FREE_DISKPROP(&v19);
  return (unsigned int)VolumeFromId;
}

```

## disassembly

```asm
0x180002d24  mov     rax, rsp
0x180002d27  push    rbp
0x180002d28  push    rbx
0x180002d29  push    rsi
0x180002d2a  push    rdi
0x180002d2b  push    r14
0x180002d2d  push    r15
0x180002d2f  lea     rbp, [rax-0E8h]
0x180002d36  sub     rsp, 1B8h
0x180002d3d  movaps  xmmword ptr [rax-48h], xmm6
0x180002d41  mov     rax, cs:__security_cookie
0x180002d48  xor     rax, rsp
0x180002d4b  mov     [rbp+0E0h+var_50], rax
0x180002d52  xorps   xmm0, xmm0
0x180002d55  mov     dword ptr [rsp+1E0h+var_1A0], 0
0x180002d5d  mov     rsi, rdx
0x180002d60  mov     [rsp+1E0h+var_190], 0
0x180002d69  xor     edx, edx; Val
0x180002d6b  mov     [rsp+1E0h+var_198], 0
0x180002d74  mov     r14, r8
0x180002d77  mov     rdi, rcx
0x180002d7a  lea     rcx, [rbp+0E0h+var_150]; void *
0x180002d7e  mov     r15, r9
0x180002d81  movups  xmmword ptr [rsp+1E0h+var_178+8], xmm0
0x180002d86  lea     r8d, [rdx+78h]; Size
0x180002d8a  movups  [rbp+0E0h+var_160], xmm0
0x180002d8e  call    memset_0
0x180002d93  xor     edx, edx; Val
0x180002d95  lea     rcx, [rbp+0E0h+var_D0]; void *
0x180002d99  mov     r8d, 80h; Size
0x180002d9f  call    memset_0
0x180002da4  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x180002dac  jnz     short loc_180002DB8
0x180002dae  mov     eax, 0C0A00016h
0x180002db3  jmp     loc_180002F27
0x180002db8  mov     rax, [rdi]
0x180002dbb  lea     rdx, [rbp+0E0h+var_D0]
0x180002dbf  mov     rcx, rdi
0x180002dc2  mov     rax, [rax+18h]
0x180002dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcb  mov     ebx, eax
0x180002dcd  test    eax, eax
0x180002dcf  js      loc_180002EDE
0x180002dd5  mov     eax, [rbp+0E0h+var_D0.PartitionStyle]
0x180002dd8  mov     [rbp+0E0h+var_150.style], eax
0x180002ddb  cmp     eax, 1
0x180002dde  jz      short loc_180002DEA
0x180002de0  mov     ebx, 0C0A00004h
0x180002de5  jmp     loc_180002EDE
0x180002dea  mov     rax, [rdi]
0x180002ded  lea     r8, [rsp+1E0h+var_198]
0x180002df2  lea     rdx, IID_IVdsCreatePartitionEx
0x180002df9  mov     word ptr [rbp+0E0h+var_150.8], 7
0x180002dff  mov     rcx, rdi
0x180002e02  mov     rax, [rax]
0x180002e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e0a  mov     ebx, eax
0x180002e0c  test    eax, eax
0x180002e0e  js      loc_180002EDE
0x180002e14  mov     rcx, [rsp+1E0h+var_198]
0x180002e19  lea     rdx, [rsp+1E0h+var_190]
0x180002e1e  mov     [rsp+28h], rdx
0x180002e23  xor     r9d, r9d
0x180002e26  lea     rdx, [rbp+0E0h+var_150]
0x180002e2a  mov     r8, r14
0x180002e2d  mov     [rsp+1E0h+var_1C0], rdx
0x180002e32  mov     rdx, rsi
0x180002e35  mov     rax, [rcx]
0x180002e38  mov     rax, [rax+18h]
0x180002e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e41  mov     ebx, eax
0x180002e43  cmp     eax, 8004240Fh
0x180002e48  jnz     short loc_180002E70
0x180002e4a  mov     rax, [rbp+0E0h+var_D0.ullSize]
0x180002e4e  lea     r8, [rsp+1E0h+var_190]; struct IVdsAsync **
0x180002e53  mov     rcx, [rsp+1E0h+var_198]; struct IVdsCreatePartitionEx *
0x180002e58  lea     rdx, [rbp+0E0h+var_150]; struct _CREATE_PARTITION_PARAMETERS *
0x180002e5c  mov     [rsp+28h], rax; unsigned __int64
0x180002e61  mov     r9, rsi; unsigned __int64
0x180002e64  mov     [rsp+1E0h+var_1C0], r14; unsigned __int64
0x180002e69  call    ?BdeCfgCreatePrimaryPartitionAdjustedSize@@YAJPEAUIVdsCreatePartitionEx@@PEAU_CREATE_PARTITION_PARAMETERS@@PEAPEAUIVdsAsync@@_K33@Z; BdeCfgCreatePrimaryPartitionAdjustedSize(IVdsCreatePartitionEx *,_CREATE_PARTITION_PARAMETERS *,IVdsAsync * *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180002e6e  mov     ebx, eax
0x180002e70  test    ebx, ebx
0x180002e72  js      short loc_180002EDE
0x180002e74  mov     rcx, [rsp+1E0h+var_190]
0x180002e79  lea     r8, [rsp+1E0h+var_178+8]
0x180002e7e  lea     rdx, [rsp+1E0h+var_1A0]
0x180002e83  mov     rax, [rcx]
0x180002e86  mov     rax, [rax+20h]
0x180002e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8f  mov     ebx, eax
0x180002e91  test    eax, eax
0x180002e93  js      short loc_180002EDE
0x180002e95  mov     ebx, dword ptr [rsp+1E0h+var_1A0]
0x180002e99  test    ebx, ebx
0x180002e9b  js      short loc_180002EDE
0x180002e9d  movups  xmm6, [rbp+0E0h+var_160]
0x180002ea1  mov     r8d, 10h; Size
0x180002ea7  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180002eae  lea     rcx, [rsp+1E0h+Buf1+8]; Buf1
0x180002eb3  movdqu  [rsp+1E0h+Buf1+8], xmm6
0x180002eb9  call    memcmp_0
0x180002ebe  test    eax, eax
0x180002ec0  jnz     short loc_180002EC9
0x180002ec2  mov     ebx, 0C0A0001Bh
0x180002ec7  jmp     short loc_180002EDE
0x180002ec9  mov     rdx, r15; struct IVdsVolume **
0x180002ecc  lea     rcx, [rsp+1E0h+Buf1+8]; struct _GUID
0x180002ed1  movdqu  [rsp+1E0h+Buf1+8], xmm6
0x180002ed7  call    ?BdeCfgGetVolumeFromId@@YAJU_GUID@@PEAPEAUIVdsVolume@@@Z; BdeCfgGetVolumeFromId(_GUID,IVdsVolume * *)
0x180002edc  mov     ebx, eax
0x180002ede  mov     rcx, [rsp+1E0h+var_198]
0x180002ee3  test    rcx, rcx
0x180002ee6  jz      short loc_180002EFD
0x180002ee8  mov     rax, [rcx]
0x180002eeb  mov     rax, [rax+10h]
0x180002eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef4  mov     [rsp+1E0h+var_198], 0
0x180002efd  mov     rcx, [rsp+1E0h+var_190]
0x180002f02  test    rcx, rcx
0x180002f05  jz      short loc_180002F1C
0x180002f07  mov     rax, [rcx]
0x180002f0a  mov     rax, [rax+10h]
0x180002f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f13  mov     [rsp+1E0h+var_190], 0
0x180002f1c  lea     rcx, [rbp+0E0h+var_D0]; struct _VDS_DISK_PROP *
0x180002f20  call    ?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z; SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)
0x180002f25  mov     eax, ebx
0x180002f27  mov     rcx, [rbp+0E0h+var_50]
0x180002f2e  xor     rcx, rsp; StackCookie
0x180002f31  call    __security_check_cookie
0x180002f36  movaps  xmm6, [rsp+1E0h+var_48+8]
0x180002f3e  add     rsp, 1B8h
0x180002f45  pop     r15
0x180002f47  pop     r14
0x180002f49  pop     rdi
0x180002f4a  pop     rsi
0x180002f4b  pop     rbx
0x180002f4c  pop     rbp
0x180002f4d  retn
```
