# BdeCfgFindRecoveryPartitionGPT(IVdsDisk *,unsigned __int64 *,int *,_VDS_PARTITION_PROP *)

- ea: `0x180003d00`
- end: `0x180003f2a`
- name: `?BdeCfgFindRecoveryPartitionGPT@@YAJPEAUIVdsDisk@@PEA_KPEAHPEAU_VDS_PARTITION_PROP@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct IVdsDisk *, unsigned __int64 *, int *, struct _VDS_PARTITION_PROP *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180003d00`
- `0x180006b2c`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003eee`
- `ole32!CoTaskMemFree` at `0x180003eee`

## pseudocode

```c
__int64 __fastcall BdeCfgFindRecoveryPartitionGPT(
        struct IVdsDisk *a1,
        unsigned __int64 *a2,
        int *a3,
        struct _VDS_PARTITION_PROP *a4)
{
  _OWORD *v8; // rdx
  __int64 v9; // r8
  int v10; // ebx
  int v12; // [rsp+20h] [rbp-79h] BYREF
  __int64 v13; // [rsp+28h] [rbp-71h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-69h] BYREF
  struct _VDS_DISK_PROP v15; // [rsp+40h] [rbp-59h] BYREF

  v13 = 0;
  pv[0] = 0;
  v12 = 0;
  memset_0(&v15, 0, sizeof(v15));
  if ( g_pService )
  {
    if ( a1 && a3 && a4 )
    {
      *a3 = 0;
      memset_0(a4, 0, sizeof(struct _VDS_PARTITION_PROP));
      v10 = ((__int64 (__fastcall *)(struct IVdsDisk *, struct _VDS_DISK_PROP *))a1->lpVtbl->GetProperties)(a1, &v15);
      if ( v10 >= 0 )
      {
        if ( v15.PartitionStyle == VDS_PST_GPT )
        {
          v10 = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                  a1,
                  &IID_IVdsAdvancedDisk,
                  &v13);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, LPVOID *, int *))(*(_QWORD *)v13 + 32LL))(v13, pv, &v12);
            if ( v10 >= 0 )
            {
              v9 = 0;
              if ( v12 > 0 )
              {
                while ( 1 )
                {
                  v8 = pv[0];
                  if ( *((_QWORD *)pv[0] + 18 * (int)v9 + 4) == *(_QWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data1
                    && *((_QWORD *)pv[0] + 18 * (int)v9 + 5) == *(_QWORD *)PARTITION_MSFT_RECOVERY_GUID.Data4
                    && (!a2 || *((_QWORD *)pv[0] + 18 * (int)v9 + 2) == *a2) )
                  {
                    break;
                  }
                  v9 = (unsigned int)(v9 + 1);
                  if ( (int)v9 >= v12 )
                    goto LABEL_20;
                }
                *(_OWORD *)&a4->PartitionStyle = *((_OWORD *)pv[0] + 9 * (int)v9);
                *(_OWORD *)&a4->ullOffset = v8[9 * (int)v9 + 1];
                *(_OWORD *)&a4->Mbr.partitionType = v8[9 * (int)v9 + 2];
                a4->Gpt.partitionId = (GUID)v8[9 * (int)v9 + 3];
                *(_OWORD *)&a4->Gpt.attributes = v8[9 * (int)v9 + 4];
                *(_OWORD *)&a4->Gpt.name[4] = v8[9 * (int)v9 + 5];
                *(_OWORD *)&a4->Gpt.name[12] = v8[9 * (int)v9 + 6];
                *(_OWORD *)&a4->Gpt.name[20] = v8[9 * (int)v9 + 7];
                *(_OWORD *)&a4->Gpt.name[28] = v8[9 * (int)v9 + 8];
                *a3 = 1;
              }
            }
          }
        }
        else
        {
          v10 = -1063256037;
        }
      }
    }
    else
    {
      v10 = -2147467261;
    }
LABEL_20:
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64, _OWORD *, __int64))(*(_QWORD *)v13 + 16LL))(v13, v8, v9);
      v13 = 0;
    }
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
  }
  else
  {
    v10 = -1063256042;
  }
  SAFE_FREE_DISKPROP(&v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003d00  mov     [rsp-8+arg_8], rbx
0x180003d05  push    rbp
0x180003d06  push    rsi
0x180003d07  push    rdi
0x180003d08  push    r14
0x180003d0a  push    r15
0x180003d0c  lea     rbp, [rsp-37h]
0x180003d11  sub     rsp, 0D0h
0x180003d18  mov     rax, cs:__security_cookie
0x180003d1f  xor     rax, rsp
0x180003d22  mov     [rbp+57h+var_30], rax
0x180003d26  mov     r14, r8
0x180003d29  mov     [rbp+57h+var_C8], 0
0x180003d31  mov     r15, rdx
0x180003d34  mov     [rbp+57h+pv], 0
0x180003d3c  mov     rsi, rcx
0x180003d3f  mov     [rbp+57h+var_D0], 0
0x180003d46  xor     edx, edx; Val
0x180003d48  lea     rcx, [rbp+57h+var_B0]; void *
0x180003d4c  mov     r8d, 80h; Size
0x180003d52  mov     rdi, r9
0x180003d55  call    memset_0
0x180003d5a  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x180003d62  jnz     short loc_180003D6E
0x180003d64  mov     ebx, 0C0A00016h
0x180003d69  jmp     loc_180003EFC
0x180003d6e  test    rsi, rsi
0x180003d71  jz      loc_180003EC3
0x180003d77  test    r14, r14
0x180003d7a  jz      loc_180003EC3
0x180003d80  test    rdi, rdi
0x180003d83  jz      loc_180003EC3
0x180003d89  xor     edx, edx; Val
0x180003d8b  mov     dword ptr [r14], 0
0x180003d92  mov     r8d, 90h; Size
0x180003d98  mov     rcx, rdi; void *
0x180003d9b  call    memset_0
0x180003da0  mov     rax, [rsi]
0x180003da3  lea     rdx, [rbp+57h+var_B0]
0x180003da7  mov     rcx, rsi
0x180003daa  mov     rax, [rax+18h]
0x180003dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db3  mov     ebx, eax
0x180003db5  test    eax, eax
0x180003db7  js      loc_180003EC8
0x180003dbd  cmp     [rbp+57h+var_B0.PartitionStyle], 2
0x180003dc1  jz      short loc_180003DCD
0x180003dc3  mov     ebx, 0C0A0001Bh
0x180003dc8  jmp     loc_180003EC8
0x180003dcd  mov     rax, [rsi]
0x180003dd0  lea     r8, [rbp+57h+var_C8]
0x180003dd4  lea     rdx, IID_IVdsAdvancedDisk
0x180003ddb  mov     rcx, rsi
0x180003dde  mov     rax, [rax]
0x180003de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de6  mov     ebx, eax
0x180003de8  test    eax, eax
0x180003dea  js      loc_180003EC8
0x180003df0  mov     rcx, [rbp+57h+var_C8]
0x180003df4  lea     r8, [rbp+57h+var_D0]
0x180003df8  lea     rdx, [rbp+57h+pv]
0x180003dfc  mov     rax, [rcx]
0x180003dff  mov     rax, [rax+20h]
0x180003e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e08  mov     ebx, eax
0x180003e0a  test    eax, eax
0x180003e0c  js      loc_180003EC8
0x180003e12  mov     r9d, [rbp+57h+var_D0]
0x180003e16  xor     r8d, r8d
0x180003e19  test    r9d, r9d
0x180003e1c  jle     loc_180003EC8
0x180003e22  mov     r10, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data4
0x180003e29  mov     r11, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data1
0x180003e30  mov     rdx, [rbp+57h+pv]
0x180003e34  movsxd  rax, r8d
0x180003e37  lea     rcx, [rax+rax*8]
0x180003e3b  add     rcx, rcx
0x180003e3e  cmp     [rdx+rcx*8+20h], r11
0x180003e43  jnz     short loc_180003E5B
0x180003e45  cmp     [rdx+rcx*8+28h], r10
0x180003e4a  jnz     short loc_180003E5B
0x180003e4c  test    r15, r15
0x180003e4f  jz      short loc_180003E65
0x180003e51  mov     rax, [r15]
0x180003e54  cmp     [rdx+rcx*8+10h], rax
0x180003e59  jz      short loc_180003E65
0x180003e5b  inc     r8d
0x180003e5e  cmp     r8d, r9d
0x180003e61  jl      short loc_180003E30
0x180003e63  jmp     short loc_180003EC8
0x180003e65  movups  xmm0, xmmword ptr [rdx+rcx*8]
0x180003e69  movups  xmmword ptr [rdi], xmm0
0x180003e6c  movups  xmm1, xmmword ptr [rdx+rcx*8+10h]
0x180003e71  movups  xmmword ptr [rdi+10h], xmm1
0x180003e75  movups  xmm0, xmmword ptr [rdx+rcx*8+20h]
0x180003e7a  movups  xmmword ptr [rdi+20h], xmm0
0x180003e7e  movups  xmm1, xmmword ptr [rdx+rcx*8+30h]
0x180003e83  movups  xmmword ptr [rdi+30h], xmm1
0x180003e87  movups  xmm0, xmmword ptr [rdx+rcx*8+40h]
0x180003e8c  movups  xmmword ptr [rdi+40h], xmm0
0x180003e90  movups  xmm1, xmmword ptr [rdx+rcx*8+50h]
0x180003e95  movups  xmmword ptr [rdi+50h], xmm1
0x180003e99  movups  xmm0, xmmword ptr [rdx+rcx*8+60h]
0x180003e9e  movups  xmmword ptr [rdi+60h], xmm0
0x180003ea2  movups  xmm1, xmmword ptr [rdx+rcx*8+70h]
0x180003ea7  movups  xmmword ptr [rdi+70h], xmm1
0x180003eab  movups  xmm0, xmmword ptr [rdx+rcx*8+80h]
0x180003eb3  movups  xmmword ptr [rdi+80h], xmm0
0x180003eba  mov     dword ptr [r14], 1
0x180003ec1  jmp     short loc_180003EC8
0x180003ec3  mov     ebx, 80004003h
0x180003ec8  mov     rcx, [rbp+57h+var_C8]
0x180003ecc  test    rcx, rcx
0x180003ecf  jz      short loc_180003EE5
0x180003ed1  mov     rax, [rcx]
0x180003ed4  mov     rax, [rax+10h]
0x180003ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003edd  mov     [rbp+57h+var_C8], 0
0x180003ee5  mov     rcx, [rbp+57h+pv]; pv
0x180003ee9  test    rcx, rcx
0x180003eec  jz      short loc_180003EFC
0x180003eee  call    cs:__imp_CoTaskMemFree
0x180003ef4  mov     [rbp+57h+pv], 0
0x180003efc  lea     rcx, [rbp+57h+var_B0]; struct _VDS_DISK_PROP *
0x180003f00  call    ?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z; SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)
0x180003f05  mov     eax, ebx
0x180003f07  mov     rcx, [rbp+57h+var_30]
0x180003f0b  xor     rcx, rsp; StackCookie
0x180003f0e  call    __security_check_cookie
0x180003f13  mov     rbx, [rsp+0F0h+arg_8]
0x180003f1b  add     rsp, 0D0h
0x180003f22  pop     r15
0x180003f24  pop     r14
0x180003f26  pop     rdi
0x180003f27  pop     rsi
0x180003f28  pop     rbp
0x180003f29  retn
```
