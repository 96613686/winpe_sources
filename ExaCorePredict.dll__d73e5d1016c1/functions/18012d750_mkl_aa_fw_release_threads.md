# mkl_aa_fw_release_threads

- ea: `0x18012d750`
- end: `0x18012d8b0`
- name: `mkl_aa_fw_release_threads`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180061160`

## callees

- `0x180038b70`
- `0x18012d750`
- `0x1804537f0`
- `0x180453810`
- `0x180453860`
- `0x180453d40`
- `0x1832ce3b0`
- `0x1832ceb40`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18012d7e1`
- `KERNEL32!GetCurrentProcessId` at `0x18012d7e1`

## pseudocode

```c
__int64 mkl_aa_fw_release_threads()
{
  void *v0; // rsp
  unsigned int v1; // ebx
  int v2; // ebp
  __int64 CurrentProcessId; // rdx
  int v5; // esi
  __int64 v6; // rdi
  __int64 v7; // r12
  __int64 i; // rbp
  __int64 v9; // r9
  _DWORD *v10; // r8
  _DWORD v11[1015]; // [rsp+0h] [rbp-220A4h]
  int v12; // [rsp+FF4h] [rbp-210B0h] BYREF
  int v13; // [rsp+FF8h] [rbp-210ACh] BYREF
  _DWORD v14[33828]; // [rsp+FFCh] [rbp-210A8h] BYREF

  v0 = alloca(135384);
  v1 = 0;
  v2 = mkl_ueaa_get_phy_device_count() - 1;
  mkl_serv_dsecnd();
  if ( *(double *)&mkl_aa_fraction <= 0.0 )
    return 0;
  if ( (unsigned int)mkl_aa_fw_lock_sharing_mask(v14, &v12) )
    return 0xFFFFFFFFLL;
  CurrentProcessId = GetCurrentProcessId();
  if ( v2 > 0 )
  {
    v5 = CurrentProcessId;
    v6 = 1025;
    v7 = v2;
    for ( i = 1; i <= v7; ++i )
    {
      mkl_ueaa_get_phy_device_mask((unsigned int)i, &v13);
      if ( v13 )
      {
        v9 = 0;
        if ( (int)v11[v6] > 0 )
        {
          v10 = &v14[v6 + 3];
          do
          {
            if ( v5 == v10[v9 - 1025] )
            {
              v10[v9 - 1025] = 0;
              ++v1;
            }
            ++v9;
          }
          while ( v9 < (int)v11[v6] );
        }
      }
      v6 += 1025;
    }
  }
  mkl_aa_fw_unlock_sharing_mask(v14, CurrentProcessId);
  return v1;
}

```

## disassembly

```asm
0x18012d750  push    rbx
0x18012d751  push    rbp
0x18012d752  mov     eax, 210D8h
0x18012d757  call    _alloca_probe
0x18012d75c  sub     rsp, 210D8h
0x18012d763  xor     ebx, ebx
0x18012d765  mov     rax, cs:__security_cookie
0x18012d76c  xor     rax, rsp
0x18012d76f  mov     [rsp+210E8h+var_18], rax
0x18012d777  call    mkl_ueaa_get_phy_device_count
0x18012d77c  mov     ebp, eax
0x18012d77e  dec     ebp
0x18012d780  call    mkl_serv_dsecnd
0x18012d785  pxor    xmm0, xmm0
0x18012d789  comisd  xmm0, cs:mkl_aa_fraction
0x18012d791  jb      short loc_18012D7AF
0x18012d793  mov     rcx, [rsp+210E8h+var_18]
0x18012d79b  xor     rcx, rsp; StackCookie
0x18012d79e  call    __security_check_cookie
0x18012d7a3  xor     eax, eax
0x18012d7a5  add     rsp, 210D8h
0x18012d7ac  pop     rbp
0x18012d7ad  pop     rbx
0x18012d7ae  retn
0x18012d7af  lea     rcx, [rsp+210E8h+var_210A8]
0x18012d7b4  lea     rdx, [rsp+210E8h+var_210B0]
0x18012d7b9  call    mkl_aa_fw_lock_sharing_mask
0x18012d7be  test    eax, eax
0x18012d7c0  jz      short loc_18012D7E1
0x18012d7c2  mov     rcx, [rsp+210E8h+var_18]
0x18012d7ca  xor     rcx, rsp; StackCookie
0x18012d7cd  call    __security_check_cookie
0x18012d7d2  mov     eax, 0FFFFFFFFh
0x18012d7d7  add     rsp, 210D8h
0x18012d7de  pop     rbp
0x18012d7df  pop     rbx
0x18012d7e0  retn
0x18012d7e1  call    cs:__imp_GetCurrentProcessId
0x18012d7e7  mov     edx, eax
0x18012d7e9  mov     ecx, 1
0x18012d7ee  mov     eax, 1004h
0x18012d7f3  test    ebp, ebp
0x18012d7f5  jle     loc_18012D884
0x18012d7fb  movsxd  rbp, ebp
0x18012d7fe  mov     [rsp+210E8h+var_210B8], rsi
0x18012d803  mov     esi, edx
0x18012d805  mov     [rsp+210E8h+var_210C0], rdi
0x18012d80a  mov     rdi, rax
0x18012d80d  mov     [rsp+210E8h+var_210C8], r12
0x18012d812  mov     r12, rbp
0x18012d815  mov     rbp, rcx
0x18012d818  mov     ecx, ebp
0x18012d81a  lea     rdx, [rsp+210E8h+var_210AC]
0x18012d81f  call    mkl_ueaa_get_phy_device_mask
0x18012d824  cmp     [rsp+210E8h+var_210AC], 0
0x18012d829  jz      short loc_18012D865
0x18012d82b  xor     r9d, r9d
0x18012d82e  cmp     [rsp+rdi+210E8h+var_220A4], 0
0x18012d836  jle     short loc_18012D865
0x18012d838  lea     r8, [rsp+rdi+210E8h+var_2109C]
0x18012d83d  cmp     esi, [r8+r9*4-1004h]
0x18012d845  jnz     short loc_18012D855
0x18012d847  mov     dword ptr [r8+r9*4-1004h], 0
0x18012d853  inc     ebx
0x18012d855  inc     r9
0x18012d858  movsxd  r10, [rsp+rdi+210E8h+var_220A4]
0x18012d860  cmp     r9, r10
0x18012d863  jl      short loc_18012D83D
0x18012d865  nop
0x18012d866  inc     rbp
0x18012d869  add     rdi, 1004h
0x18012d870  cmp     rbp, r12
0x18012d873  jle     short loc_18012D818
0x18012d875  mov     rsi, [rsp+210E8h+var_210B8]
0x18012d87a  mov     rdi, [rsp+210E8h+var_210C0]
0x18012d87f  mov     r12, [rsp+210E8h+var_210C8]
0x18012d884  lea     rcx, [rsp+210E8h+var_210A8]
0x18012d889  call    mkl_aa_fw_unlock_sharing_mask
0x18012d88e  mov     rcx, [rsp+210E8h+var_18]
0x18012d896  xor     rcx, rsp; StackCookie
0x18012d899  call    __security_check_cookie
0x18012d89e  mov     eax, ebx
0x18012d8a0  add     rsp, 210D8h
0x18012d8a7  pop     rbp
0x18012d8a8  pop     rbx
0x18012d8a9  retn
```
