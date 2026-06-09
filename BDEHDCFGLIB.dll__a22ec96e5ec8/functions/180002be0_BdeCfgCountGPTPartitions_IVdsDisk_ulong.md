# BdeCfgCountGPTPartitions(IVdsDisk *,ulong *)

- ea: `0x180002be0`
- end: `0x180002d1e`
- name: `?BdeCfgCountGPTPartitions@@YAJPEAUIVdsDisk@@PEAK@Z`
- size: `318`
- prototype: `__int64 __fastcall(struct IVdsDisk *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180002be0`
- `0x180006b2c`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002ce6`
- `ole32!CoTaskMemFree` at `0x180002ce6`

## pseudocode

```c
__int64 __fastcall BdeCfgCountGPTPartitions(struct IVdsDisk *a1, unsigned int *a2)
{
  int v4; // ebx
  unsigned int v6; // [rsp+20h] [rbp-69h] BYREF
  __int64 v7; // [rsp+28h] [rbp-61h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-59h] BYREF
  struct _VDS_DISK_PROP v9; // [rsp+40h] [rbp-49h] BYREF

  v7 = 0;
  pv[0] = 0;
  v6 = 0;
  memset_0(&v9, 0, sizeof(v9));
  if ( g_pService )
  {
    if ( a1 && a2 )
    {
      v4 = ((__int64 (__fastcall *)(struct IVdsDisk *, struct _VDS_DISK_PROP *))a1->lpVtbl->GetProperties)(a1, &v9);
      if ( v4 >= 0 )
      {
        if ( v9.PartitionStyle == VDS_PST_GPT )
        {
          v4 = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                 a1,
                 &IID_IVdsAdvancedDisk,
                 &v7);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *, unsigned int *))(*(_QWORD *)v7 + 32LL))(v7, pv, &v6);
            if ( v4 >= 0 )
              *a2 = v6;
          }
        }
        else
        {
          v4 = -1063256037;
        }
      }
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        v7 = 0;
      }
      if ( pv[0] )
      {
        CoTaskMemFree(pv[0]);
        pv[0] = 0;
      }
    }
    else
    {
      v4 = -2147467261;
    }
  }
  else
  {
    v4 = -1063256042;
  }
  SAFE_FREE_DISKPROP(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002be0  mov     [rsp-8+arg_10], rbx
0x180002be5  push    rbp
0x180002be6  push    rsi
0x180002be7  push    rdi
0x180002be8  lea     rbp, [rsp-47h]
0x180002bed  sub     rsp, 0D0h
0x180002bf4  mov     rax, cs:__security_cookie
0x180002bfb  xor     rax, rsp
0x180002bfe  mov     [rbp+57h+var_20], rax
0x180002c02  mov     rsi, rdx
0x180002c05  mov     [rbp+57h+var_B8], 0
0x180002c0d  mov     rdi, rcx
0x180002c10  mov     [rbp+57h+pv], 0
0x180002c18  xor     edx, edx; Val
0x180002c1a  mov     [rbp+57h+var_C0], 0
0x180002c21  lea     rcx, [rbp+57h+var_A0]; void *
0x180002c25  mov     r8d, 80h; Size
0x180002c2b  call    memset_0
0x180002c30  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x180002c38  jnz     short loc_180002C44
0x180002c3a  mov     ebx, 0C0A00016h
0x180002c3f  jmp     loc_180002CF4
0x180002c44  test    rdi, rdi
0x180002c47  jnz     short loc_180002C53
0x180002c49  mov     ebx, 80004003h
0x180002c4e  jmp     loc_180002CF4
0x180002c53  test    rsi, rsi
0x180002c56  jz      short loc_180002C49
0x180002c58  mov     rax, [rdi]
0x180002c5b  lea     rdx, [rbp+57h+var_A0]
0x180002c5f  mov     rcx, rdi
0x180002c62  mov     rax, [rax+18h]
0x180002c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c6b  mov     ebx, eax
0x180002c6d  test    eax, eax
0x180002c6f  js      short loc_180002CC0
0x180002c71  cmp     [rbp+57h+var_A0.PartitionStyle], 2
0x180002c75  jz      short loc_180002C7E
0x180002c77  mov     ebx, 0C0A0001Bh
0x180002c7c  jmp     short loc_180002CC0
0x180002c7e  mov     rax, [rdi]
0x180002c81  lea     r8, [rbp+57h+var_B8]
0x180002c85  lea     rdx, IID_IVdsAdvancedDisk
0x180002c8c  mov     rcx, rdi
0x180002c8f  mov     rax, [rax]
0x180002c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c97  mov     ebx, eax
0x180002c99  test    eax, eax
0x180002c9b  js      short loc_180002CC0
0x180002c9d  mov     rcx, [rbp+57h+var_B8]
0x180002ca1  lea     r8, [rbp+57h+var_C0]
0x180002ca5  lea     rdx, [rbp+57h+pv]
0x180002ca9  mov     rax, [rcx]
0x180002cac  mov     rax, [rax+20h]
0x180002cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb5  mov     ebx, eax
0x180002cb7  test    eax, eax
0x180002cb9  js      short loc_180002CC0
0x180002cbb  mov     eax, [rbp+57h+var_C0]
0x180002cbe  mov     [rsi], eax
0x180002cc0  mov     rcx, [rbp+57h+var_B8]
0x180002cc4  test    rcx, rcx
0x180002cc7  jz      short loc_180002CDD
0x180002cc9  mov     rax, [rcx]
0x180002ccc  mov     rax, [rax+10h]
0x180002cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd5  mov     [rbp+57h+var_B8], 0
0x180002cdd  mov     rcx, [rbp+57h+pv]; pv
0x180002ce1  test    rcx, rcx
0x180002ce4  jz      short loc_180002CF4
0x180002ce6  call    cs:__imp_CoTaskMemFree
0x180002cec  mov     [rbp+57h+pv], 0
0x180002cf4  lea     rcx, [rbp+57h+var_A0]; struct _VDS_DISK_PROP *
0x180002cf8  call    ?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z; SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)
0x180002cfd  mov     eax, ebx
0x180002cff  mov     rcx, [rbp+57h+var_20]
0x180002d03  xor     rcx, rsp; StackCookie
0x180002d06  call    __security_check_cookie
0x180002d0b  mov     rbx, [rsp+0E0h+arg_10]
0x180002d13  add     rsp, 0D0h
0x180002d1a  pop     rdi
0x180002d1b  pop     rsi
0x180002d1c  pop     rbp
0x180002d1d  retn
```
