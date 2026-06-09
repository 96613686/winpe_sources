# BdeCfgCanCreateActivePartOnDisk(IVdsDisk *)

- ea: `0x1800021b0`
- end: `0x180002286`
- name: `?BdeCfgCanCreateActivePartOnDisk@@YAJPEAUIVdsDisk@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct IVdsDisk *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180003580`
- `0x18000f430`
- `0x18000fb40`

## callees

- `0x1800021b0`
- `0x180005578`
- `0x180006b2c`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall BdeCfgCanCreateActivePartOnDisk(struct IVdsDisk *a1)
{
  int v3; // ebx
  unsigned int v4[4]; // [rsp+20h] [rbp-A8h] BYREF
  _VDS_DISK_PROP v5; // [rsp+30h] [rbp-98h] BYREF

  v4[0] = 0;
  if ( !g_pService )
    return 3231711254LL;
  memset_0(&v5, 0, sizeof(v5));
  v3 = ((__int64 (__fastcall *)(struct IVdsDisk *, _VDS_DISK_PROP *))a1->lpVtbl->GetProperties)(a1, &v5);
  if ( v3 >= 0 )
  {
    if ( v5.dwDeviceType == 7 && v5.dwMediaType == 12 )
    {
      if ( v5.PartitionStyle == VDS_PST_MBR )
      {
        v3 = BdeCfgpCountPartitionTableEntries(a1, v4);
        if ( v3 >= 0 && v4[0] >= 4 )
          v3 = -1063256017;
      }
      else
      {
        v3 = -1063256060;
      }
    }
    else
    {
      v3 = -1063256061;
    }
  }
  SAFE_FREE_DISKPROP(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800021b0  mov     [rsp+arg_8], rbx
0x1800021b5  push    rdi
0x1800021b6  sub     rsp, 0C0h
0x1800021bd  mov     rax, cs:__security_cookie
0x1800021c4  xor     rax, rsp
0x1800021c7  mov     [rsp+0C8h+var_18], rax
0x1800021cf  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x1800021d7  mov     rdi, rcx
0x1800021da  mov     [rsp+0C8h+var_A8], 0
0x1800021e2  jnz     short loc_1800021EB
0x1800021e4  mov     eax, 0C0A00016h
0x1800021e9  jmp     short loc_180002265
0x1800021eb  xor     edx, edx; Val
0x1800021ed  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800021f2  mov     r8d, 80h; Size
0x1800021f8  call    memset_0
0x1800021fd  mov     rax, [rdi]
0x180002200  lea     rdx, [rsp+0C8h+var_98]
0x180002205  mov     rcx, rdi
0x180002208  mov     rax, [rax+18h]
0x18000220c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002211  mov     ebx, eax
0x180002213  test    eax, eax
0x180002215  js      short loc_180002259
0x180002217  cmp     [rsp+0C8h+var_98.dwDeviceType], 7
0x18000221c  jnz     short loc_180002254
0x18000221e  cmp     [rsp+0C8h+var_98.dwMediaType], 0Ch
0x180002223  jnz     short loc_180002254
0x180002225  cmp     [rsp+0C8h+var_98.PartitionStyle], 1
0x18000222a  jz      short loc_180002233
0x18000222c  mov     ebx, 0C0A00004h
0x180002231  jmp     short loc_180002259
0x180002233  lea     rdx, [rsp+0C8h+var_A8]; unsigned int *
0x180002238  mov     rcx, rdi; struct IVdsDisk *
0x18000223b  call    ?BdeCfgpCountPartitionTableEntries@@YAJPEAUIVdsDisk@@PEAK@Z; BdeCfgpCountPartitionTableEntries(IVdsDisk *,ulong *)
0x180002240  mov     ebx, eax
0x180002242  test    eax, eax
0x180002244  js      short loc_180002259
0x180002246  cmp     [rsp+0C8h+var_A8], 4
0x18000224b  jb      short loc_180002259
0x18000224d  mov     ebx, 0C0A0002Fh
0x180002252  jmp     short loc_180002259
0x180002254  mov     ebx, 0C0A00003h
0x180002259  lea     rcx, [rsp+0C8h+var_98]; struct _VDS_DISK_PROP *
0x18000225e  call    ?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z; SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)
0x180002263  mov     eax, ebx
0x180002265  mov     rcx, [rsp+0C8h+var_18]
0x18000226d  xor     rcx, rsp; StackCookie
0x180002270  call    __security_check_cookie
0x180002275  mov     rbx, [rsp+0C8h+arg_8]
0x18000227d  add     rsp, 0C0h
0x180002284  pop     rdi
0x180002285  retn
```
