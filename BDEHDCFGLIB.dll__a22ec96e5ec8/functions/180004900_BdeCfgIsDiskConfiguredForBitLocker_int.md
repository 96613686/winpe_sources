# BdeCfgIsDiskConfiguredForBitLocker(int *)

- ea: `0x180004900`
- end: `0x1800049c7`
- name: `?BdeCfgIsDiskConfiguredForBitLocker@@YAJPEAH@Z`
- size: `199`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180003f68`
- `0x1800040d0`
- `0x180004900`
- `0x1800050b8`
- `0x18001358e`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall BdeCfgIsDiskConfiguredForBitLocker(int *a1)
{
  int BasicVolumePartitionProperties; // ebx
  int BootVolume; // eax
  struct IVdsVolume *v4; // rdi
  struct _VDS_PARTITION_PROP v6; // [rsp+20h] [rbp-98h] BYREF
  unsigned int v7; // [rsp+C0h] [rbp+8h] BYREF
  struct IVdsVolume *v8; // [rsp+C8h] [rbp+10h] BYREF

  v7 = 0;
  v8 = 0;
  memset_0(&v6, 0, sizeof(v6));
  if ( a1 )
  {
    BootVolume = BdeCfgGetBootVolume(&v8);
    v4 = v8;
    BasicVolumePartitionProperties = BootVolume;
    if ( BootVolume >= 0 )
    {
      BasicVolumePartitionProperties = BdeCfgGetBasicVolumePartitionProperties(v8, &v7, &v6);
      if ( BasicVolumePartitionProperties >= 0 )
        *a1 = v6.PartitionStyle == VDS_PST_GPT || BdeCfgpCheckBootVolume(v4) == -1063256062;
    }
    if ( v4 )
      ((void (__fastcall *)(struct IVdsVolume *))v4->lpVtbl->Release)(v4);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)BasicVolumePartitionProperties;
}

```

## disassembly

```asm
0x180004900  mov     rax, rsp
0x180004903  mov     [rax+18h], rbx
0x180004907  mov     [rax+20h], rsi
0x18000490b  push    rdi
0x18000490c  sub     rsp, 0B0h
0x180004913  mov     rsi, rcx
0x180004916  mov     dword ptr [rax+8], 0
0x18000491d  lea     rcx, [rsp+0B8h+var_98]; void *
0x180004922  mov     qword ptr [rax+10h], 0
0x18000492a  xor     edx, edx; Val
0x18000492c  mov     r8d, 90h; Size
0x180004932  call    memset_0
0x180004937  test    rsi, rsi
0x18000493a  jnz     short loc_180004943
0x18000493c  mov     ebx, 80004003h
0x180004941  jmp     short loc_1800049B0
0x180004943  lea     rcx, [rsp+0B8h+arg_8]; struct IVdsVolume **
0x18000494b  call    ?BdeCfgGetBootVolume@@YAJPEAPEAUIVdsVolume@@@Z; BdeCfgGetBootVolume(IVdsVolume * *)
0x180004950  mov     rdi, [rsp+0B8h+arg_8]
0x180004958  mov     ebx, eax
0x18000495a  test    eax, eax
0x18000495c  js      short loc_18000499C
0x18000495e  lea     r8, [rsp+0B8h+var_98]; struct _VDS_PARTITION_PROP *
0x180004963  mov     rcx, rdi; struct IVdsVolume *
0x180004966  lea     rdx, [rsp+0B8h+arg_0]; unsigned int *
0x18000496e  call    ?BdeCfgGetBasicVolumePartitionProperties@@YAJPEAUIVdsVolume@@PEAKPEAU_VDS_PARTITION_PROP@@@Z; BdeCfgGetBasicVolumePartitionProperties(IVdsVolume *,ulong *,_VDS_PARTITION_PROP *)
0x180004973  mov     ebx, eax
0x180004975  test    eax, eax
0x180004977  js      short loc_18000499C
0x180004979  cmp     [rsp+0B8h+var_98.PartitionStyle], 2
0x18000497e  jnz     short loc_180004988
0x180004980  mov     dword ptr [rsi], 1
0x180004986  jmp     short loc_18000499C
0x180004988  mov     rcx, rdi; struct IVdsVolume *
0x18000498b  call    ?BdeCfgpCheckBootVolume@@YAJPEAUIVdsVolume@@@Z; BdeCfgpCheckBootVolume(IVdsVolume *)
0x180004990  xor     edx, edx
0x180004992  cmp     eax, 0C0A00002h
0x180004997  setz    dl
0x18000499a  mov     [rsi], edx
0x18000499c  test    rdi, rdi
0x18000499f  jz      short loc_1800049B0
0x1800049a1  mov     rax, [rdi]
0x1800049a4  mov     rcx, rdi
0x1800049a7  mov     rax, [rax+10h]
0x1800049ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b0  lea     r11, [rsp+0B8h+var_8]
0x1800049b8  mov     eax, ebx
0x1800049ba  mov     rbx, [r11+20h]
0x1800049be  mov     rsi, [r11+28h]
0x1800049c2  mov     rsp, r11
0x1800049c5  pop     rdi
0x1800049c6  retn
```
