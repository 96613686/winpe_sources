# BdeCfgpCountPartitionTableEntries(IVdsDisk *,ulong *)

- ea: `0x180005578`
- end: `0x180005741`
- name: `?BdeCfgpCountPartitionTableEntries@@YAJPEAUIVdsDisk@@PEAK@Z`
- size: `457`
- prototype: `__int64 __fastcall(struct IVdsDisk *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800021b0`

## callees

- `0x180005578`
- `0x180006234`
- `0x180006b2c`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005704`
- `ole32!CoTaskMemFree` at `0x180005704`

## pseudocode

```c
__int64 __fastcall BdeCfgpCountPartitionTableEntries(struct IVdsDisk *a1, unsigned int *a2)
{
  int ExtendedPartitionExtent; // ebx
  int v6; // r8d
  int v7; // r9d
  int i; // ecx
  unsigned __int64 v9; // r10
  int v10; // [rsp+20h] [rbp-79h] BYREF
  __int64 v11; // [rsp+28h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int64 v14; // [rsp+40h] [rbp-59h] BYREF
  struct _VDS_DISK_PROP v15; // [rsp+50h] [rbp-49h] BYREF

  v11 = 0;
  pv = 0;
  v10 = 0;
  v13 = 0;
  v14 = 0;
  if ( !g_pService )
    return 3231711254LL;
  memset_0(&v15, 0, sizeof(v15));
  ExtendedPartitionExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, struct _VDS_DISK_PROP *))a1->lpVtbl->GetProperties)(
                              a1,
                              &v15);
  if ( ExtendedPartitionExtent >= 0 )
  {
    if ( v15.PartitionStyle == VDS_PST_MBR )
    {
      ExtendedPartitionExtent = BdeCfgpGetExtendedPartitionExtent(a1, &v13, &v14);
      if ( ExtendedPartitionExtent >= 0 )
      {
        ExtendedPartitionExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                                    a1,
                                    &IID_IVdsAdvancedDisk,
                                    &v11);
        if ( ExtendedPartitionExtent >= 0 )
        {
          ExtendedPartitionExtent = (*(__int64 (__fastcall **)(__int64, LPVOID *, int *))(*(_QWORD *)v11 + 32LL))(
                                      v11,
                                      &pv,
                                      &v10);
          if ( ExtendedPartitionExtent >= 0 )
          {
            v6 = 0;
            v7 = 0;
            for ( i = 0; i < v10; ++i )
            {
              if ( *((_DWORD *)pv + 36 * i) == 1 )
              {
                if ( *((_BYTE *)pv + 144 * i + 32) == 5 || *((_BYTE *)pv + 144 * i + 32) == 15 )
                {
                  ++v7;
                }
                else
                {
                  v9 = *((_QWORD *)pv + 18 * i + 2);
                  if ( v9 < v13 || v9 >= v14 + v13 )
                    ++v6;
                }
              }
            }
            *a2 = v7 + v6;
          }
        }
      }
    }
    else
    {
      ExtendedPartitionExtent = -1063256060;
    }
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  SAFE_FREE_DISKPROP(&v15);
  return (unsigned int)ExtendedPartitionExtent;
}

```

## disassembly

```asm
0x180005578  mov     [rsp-8+arg_10], rbx
0x18000557d  mov     [rsp-8+arg_18], rsi
0x180005582  push    rbp
0x180005583  push    rdi
0x180005584  push    r14
0x180005586  lea     rbp, [rsp-47h]
0x18000558b  sub     rsp, 0E0h
0x180005592  mov     rax, cs:__security_cookie
0x180005599  xor     rax, rsp
0x18000559c  mov     [rbp+57h+var_20], rax
0x1800055a0  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x1800055a8  mov     r14, rdx
0x1800055ab  mov     rdi, rcx
0x1800055ae  mov     [rbp+57h+var_C8], 0
0x1800055b6  mov     [rbp+57h+pv], 0
0x1800055be  mov     [rbp+57h+var_D0], 0
0x1800055c5  mov     [rbp+57h+var_B8], 0
0x1800055cd  mov     [rbp+57h+var_B0], 0
0x1800055d5  jnz     short loc_1800055E1
0x1800055d7  mov     eax, 0C0A00016h
0x1800055dc  jmp     loc_18000571D
0x1800055e1  xor     edx, edx; Val
0x1800055e3  lea     rcx, [rbp+57h+var_A0]; void *
0x1800055e7  mov     r8d, 80h; Size
0x1800055ed  call    memset_0
0x1800055f2  mov     rax, [rdi]
0x1800055f5  lea     rdx, [rbp+57h+var_A0]
0x1800055f9  mov     rcx, rdi
0x1800055fc  mov     rax, [rax+18h]
0x180005600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005605  mov     ebx, eax
0x180005607  test    eax, eax
0x180005609  js      loc_1800056DE
0x18000560f  cmp     [rbp+57h+var_A0.PartitionStyle], 1
0x180005613  jz      short loc_18000561F
0x180005615  mov     ebx, 0C0A00004h
0x18000561a  jmp     loc_1800056DE
0x18000561f  lea     r8, [rbp+57h+var_B0]; unsigned __int64 *
0x180005623  mov     rcx, rdi; struct IVdsDisk *
0x180005626  lea     rdx, [rbp+57h+var_B8]; unsigned __int64 *
0x18000562a  call    ?BdeCfgpGetExtendedPartitionExtent@@YAJPEAUIVdsDisk@@PEA_K1@Z; BdeCfgpGetExtendedPartitionExtent(IVdsDisk *,unsigned __int64 *,unsigned __int64 *)
0x18000562f  mov     ebx, eax
0x180005631  test    eax, eax
0x180005633  js      loc_1800056DE
0x180005639  mov     rax, [rdi]
0x18000563c  lea     r8, [rbp+57h+var_C8]
0x180005640  lea     rdx, IID_IVdsAdvancedDisk
0x180005647  mov     rcx, rdi
0x18000564a  mov     rax, [rax]
0x18000564d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005652  mov     ebx, eax
0x180005654  test    eax, eax
0x180005656  js      loc_1800056DE
0x18000565c  mov     rcx, [rbp+57h+var_C8]
0x180005660  lea     r8, [rbp+57h+var_D0]
0x180005664  lea     rdx, [rbp+57h+pv]
0x180005668  mov     rax, [rcx]
0x18000566b  mov     rax, [rax+20h]
0x18000566f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005674  mov     ebx, eax
0x180005676  test    eax, eax
0x180005678  js      short loc_1800056DE
0x18000567a  mov     r11d, [rbp+57h+var_D0]
0x18000567e  xor     r8d, r8d
0x180005681  xor     r9d, r9d
0x180005684  xor     ecx, ecx
0x180005686  test    r11d, r11d
0x180005689  jle     short loc_1800056D7
0x18000568b  mov     rdi, [rbp+57h+var_B8]
0x18000568f  mov     rsi, [rbp+57h+var_B0]
0x180005693  movsxd  rax, ecx
0x180005696  lea     rdx, [rax+rax*8]
0x18000569a  mov     rax, [rbp+57h+pv]
0x18000569e  add     rdx, rdx
0x1800056a1  cmp     dword ptr [rax+rdx*8], 1
0x1800056a5  jnz     short loc_1800056D0
0x1800056a7  cmp     byte ptr [rax+rdx*8+20h], 5
0x1800056ac  jz      short loc_1800056CD
0x1800056ae  cmp     byte ptr [rax+rdx*8+20h], 0Fh
0x1800056b3  jz      short loc_1800056CD
0x1800056b5  mov     r10, [rax+rdx*8+10h]
0x1800056ba  cmp     r10, rdi
0x1800056bd  jb      short loc_1800056C8
0x1800056bf  lea     rax, [rsi+rdi]
0x1800056c3  cmp     r10, rax
0x1800056c6  jb      short loc_1800056D0
0x1800056c8  inc     r8d
0x1800056cb  jmp     short loc_1800056D0
0x1800056cd  inc     r9d
0x1800056d0  inc     ecx
0x1800056d2  cmp     ecx, r11d
0x1800056d5  jl      short loc_180005693
0x1800056d7  lea     eax, [r9+r8]
0x1800056db  mov     [r14], eax
0x1800056de  mov     rcx, [rbp+57h+var_C8]
0x1800056e2  test    rcx, rcx
0x1800056e5  jz      short loc_1800056FB
0x1800056e7  mov     rax, [rcx]
0x1800056ea  mov     rax, [rax+10h]
0x1800056ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f3  mov     [rbp+57h+var_C8], 0
0x1800056fb  mov     rcx, [rbp+57h+pv]; pv
0x1800056ff  test    rcx, rcx
0x180005702  jz      short loc_180005712
0x180005704  call    cs:__imp_CoTaskMemFree
0x18000570a  mov     [rbp+57h+pv], 0
0x180005712  lea     rcx, [rbp+57h+var_A0]; struct _VDS_DISK_PROP *
0x180005716  call    ?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z; SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)
0x18000571b  mov     eax, ebx
0x18000571d  mov     rcx, [rbp+57h+var_20]
0x180005721  xor     rcx, rsp; StackCookie
0x180005724  call    __security_check_cookie
0x180005729  lea     r11, [rsp+0F0h+var_10]
0x180005731  mov     rbx, [r11+30h]
0x180005735  mov     rsi, [r11+38h]
0x180005739  mov     rsp, r11
0x18000573c  pop     r14
0x18000573e  pop     rdi
0x18000573f  pop     rbp
0x180005740  retn
```
