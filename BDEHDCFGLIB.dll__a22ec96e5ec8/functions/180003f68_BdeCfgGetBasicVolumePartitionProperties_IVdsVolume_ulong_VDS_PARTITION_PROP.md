# BdeCfgGetBasicVolumePartitionProperties(IVdsVolume *,ulong *,_VDS_PARTITION_PROP *)

- ea: `0x180003f68`
- end: `0x1800040c7`
- name: `?BdeCfgGetBasicVolumePartitionProperties@@YAJPEAUIVdsVolume@@PEAKPEAU_VDS_PARTITION_PROP@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(struct IVdsVolume *, unsigned int *, struct _VDS_PARTITION_PROP *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180002460`
- `0x180004900`
- `0x1800050b8`
- `0x180006860`

## callees

- `0x180003390`
- `0x180003f68`
- `0x180004410`
- `0x180006b2c`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180004027`
- `msvcrt!_wtoi` at `0x180004027`
- `msvcrt!_wcsnicmp` at `0x180004015`
- `msvcrt!_wcsnicmp` at `0x180004015`

## pseudocode

```c
__int64 __fastcall BdeCfgGetBasicVolumePartitionProperties(
        struct IVdsVolume *a1,
        unsigned int *a2,
        struct _VDS_PARTITION_PROP *a3)
{
  int BasicVolumeExtent; // ebx
  int v7; // eax
  struct IVdsDisk *v8; // rcx
  struct IVdsDisk *v10; // [rsp+20h] [rbp-79h] BYREF
  __int64 v11; // [rsp+28h] [rbp-71h] BYREF
  unsigned __int64 v12; // [rsp+30h] [rbp-69h] BYREF
  struct _VDS_DISK_PROP v13; // [rsp+40h] [rbp-59h] BYREF

  v12 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(&v13, 0, sizeof(v13));
  BasicVolumeExtent = BdeCfgFindBasicVolumeExtent(a1, &v12, 0);
  if ( BasicVolumeExtent >= 0 )
  {
    BasicVolumeExtent = BdeCfgGetVolumeDisk(a1, &v10);
    if ( BasicVolumeExtent >= 0 )
    {
      BasicVolumeExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, struct _VDS_DISK_PROP *))v10->lpVtbl->GetProperties)(
                            v10,
                            &v13);
      if ( BasicVolumeExtent >= 0 )
      {
        if ( _wcsnicmp(v13.pwszName, L"\\\\?\\PhysicalDrive", 0x11u) )
        {
          BasicVolumeExtent = -1063256037;
        }
        else
        {
          v7 = _wtoi((const wchar_t *)v13.pwszName + 17);
          v8 = v10;
          *a2 = v7;
          BasicVolumeExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))v8->lpVtbl->QueryInterface)(
                                v8,
                                &IID_IVdsAdvancedDisk,
                                &v11);
          if ( BasicVolumeExtent >= 0 )
            BasicVolumeExtent = (*(__int64 (__fastcall **)(__int64, unsigned __int64, struct _VDS_PARTITION_PROP *))(*(_QWORD *)v11 + 24LL))(
                                  v11,
                                  v12,
                                  a3);
        }
      }
    }
  }
  SAFE_FREE_DISKPROP(&v13);
  if ( v10 )
  {
    ((void (__fastcall *)(struct IVdsDisk *))v10->lpVtbl->Release)(v10);
    v10 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)BasicVolumeExtent;
}

```

## disassembly

```asm
0x180003f68  push    rbp
0x180003f6a  push    rbx
0x180003f6b  push    rsi
0x180003f6c  push    rdi
0x180003f6d  push    r14
0x180003f6f  lea     rbp, [rsp-37h]
0x180003f74  sub     rsp, 0D0h
0x180003f7b  mov     rax, cs:__security_cookie
0x180003f82  xor     rax, rsp
0x180003f85  mov     [rbp+57h+var_30], rax
0x180003f89  mov     rsi, r8
0x180003f8c  mov     [rbp+57h+var_C0], 0
0x180003f94  mov     r14, rdx
0x180003f97  mov     [rbp+57h+var_D0], 0
0x180003f9f  mov     rdi, rcx
0x180003fa2  mov     [rbp+57h+var_C8], 0
0x180003faa  xor     edx, edx; Val
0x180003fac  lea     rcx, [rbp+57h+var_B0]; void *
0x180003fb0  mov     r8d, 80h; Size
0x180003fb6  call    memset_0
0x180003fbb  xor     r8d, r8d; unsigned __int64 *
0x180003fbe  lea     rdx, [rbp+57h+var_C0]; unsigned __int64 *
0x180003fc2  mov     rcx, rdi; struct IVdsVolume *
0x180003fc5  call    ?BdeCfgFindBasicVolumeExtent@@YAJPEAUIVdsVolume@@PEA_K1@Z; BdeCfgFindBasicVolumeExtent(IVdsVolume *,unsigned __int64 *,unsigned __int64 *)
0x180003fca  mov     ebx, eax
0x180003fcc  test    eax, eax
0x180003fce  js      loc_180004070
0x180003fd4  lea     rdx, [rbp+57h+var_D0]; struct IVdsDisk **
0x180003fd8  mov     rcx, rdi; struct IVdsVolume *
0x180003fdb  call    ?BdeCfgGetVolumeDisk@@YAJPEAUIVdsVolume@@PEAPEAUIVdsDisk@@@Z; BdeCfgGetVolumeDisk(IVdsVolume *,IVdsDisk * *)
0x180003fe0  mov     ebx, eax
0x180003fe2  test    eax, eax
0x180003fe4  js      loc_180004070
0x180003fea  mov     rcx, [rbp+57h+var_D0]
0x180003fee  lea     rdx, [rbp+57h+var_B0]
0x180003ff2  mov     rax, [rcx]
0x180003ff5  mov     rax, [rax+18h]
0x180003ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ffe  mov     ebx, eax
0x180004000  test    eax, eax
0x180004002  js      short loc_180004070
0x180004004  mov     rcx, [rbp+57h+var_B0.pwszName]; String1
0x180004008  lea     rdx, aPhysicaldrive; "\\\\?\\PhysicalDrive"
0x18000400f  mov     r8d, 11h; MaxCount
0x180004015  call    cs:__imp__wcsnicmp
0x18000401b  test    eax, eax
0x18000401d  jnz     short loc_18000406B
0x18000401f  mov     rcx, [rbp+57h+var_B0.pwszName]
0x180004023  add     rcx, 22h ; '"'; String
0x180004027  call    cs:__imp__wtoi
0x18000402d  mov     rcx, [rbp+57h+var_D0]
0x180004031  lea     r8, [rbp+57h+var_C8]
0x180004035  mov     [r14], eax
0x180004038  lea     rdx, IID_IVdsAdvancedDisk
0x18000403f  mov     rax, [rcx]
0x180004042  mov     rax, [rax]
0x180004045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000404a  mov     ebx, eax
0x18000404c  test    eax, eax
0x18000404e  js      short loc_180004070
0x180004050  mov     rcx, [rbp+57h+var_C8]
0x180004054  mov     r8, rsi
0x180004057  mov     rdx, [rbp+57h+var_C0]
0x18000405b  mov     rax, [rcx]
0x18000405e  mov     rax, [rax+18h]
0x180004062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004067  mov     ebx, eax
0x180004069  jmp     short loc_180004070
0x18000406b  mov     ebx, 0C0A0001Bh
0x180004070  lea     rcx, [rbp+57h+var_B0]; struct _VDS_DISK_PROP *
0x180004074  call    ?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z; SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)
0x180004079  mov     rcx, [rbp+57h+var_D0]
0x18000407d  test    rcx, rcx
0x180004080  jz      short loc_180004096
0x180004082  mov     rax, [rcx]
0x180004085  mov     rax, [rax+10h]
0x180004089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000408e  mov     [rbp+57h+var_D0], 0
0x180004096  mov     rcx, [rbp+57h+var_C8]
0x18000409a  test    rcx, rcx
0x18000409d  jz      short loc_1800040AB
0x18000409f  mov     rax, [rcx]
0x1800040a2  mov     rax, [rax+10h]
0x1800040a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ab  mov     eax, ebx
0x1800040ad  mov     rcx, [rbp+57h+var_30]
0x1800040b1  xor     rcx, rsp; StackCookie
0x1800040b4  call    __security_check_cookie
0x1800040b9  add     rsp, 0D0h
0x1800040c0  pop     r14
0x1800040c2  pop     rdi
0x1800040c3  pop     rsi
0x1800040c4  pop     rbx
0x1800040c5  pop     rbp
0x1800040c6  retn
```
