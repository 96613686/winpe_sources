# BdeCfgpFindDiskWithName(ushort const *,IVdsDisk * *)

- ea: `0x180005884`
- end: `0x180005ce0`
- name: `?BdeCfgpFindDiskWithName@@YAJPEBGPEAPEAUIVdsDisk@@@Z`
- size: `1116`
- prototype: `__int64 __fastcall(wchar_t *String2, struct IVdsDisk **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180008ca0`

## callees

- `0x180005884`
- `0x180006b2c`
- `0x18001358e`
- `0x18001359a`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005a8b`
- `ole32!CoTaskMemFree` at `0x180005cbc`
- `ole32!CoTaskMemFree` at `0x180005a8b`
- `ole32!CoTaskMemFree` at `0x180005cbc`

## pseudocode

```c
__int64 __fastcall BdeCfgpFindDiskWithName(wchar_t *String2, struct IVdsDisk **a2)
{
  int v4; // ebx
  int v5; // eax
  int v6; // ebx
  int v7; // ebx
  int v8; // eax
  int v9; // ebx
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  struct IVdsDisk *v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+5Ch] [rbp-A4h] BYREF
  int v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  struct _VDS_DISK_PROP v24; // [rsp+80h] [rbp-80h] BYREF
  __int128 v25; // [rsp+100h] [rbp+0h] BYREF
  LPVOID pv[2]; // [rsp+110h] [rbp+10h]

  *a2 = 0;
  v14 = 0;
  v23 = 0;
  v16 = 0;
  v17 = 0;
  v22 = 0;
  v15 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  memset_0(&v24, 0, sizeof(v24));
  v25 = 0;
  *(_OWORD *)pv = 0;
  if ( String2 )
  {
    if ( g_pService )
    {
      v4 = ((__int64 (__fastcall *)(struct IVdsService *, __int64, __int64 *))g_pService->lpVtbl->QueryProviders)(
             g_pService,
             1,
             &v23);
      if ( v4 >= 0 )
      {
        while ( 1 )
        {
          v19 = 0;
          v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v23 + 24LL))(
                 v23,
                 1,
                 &v14,
                 &v19);
          v4 = v5;
          if ( v5 == 1 )
            break;
          if ( v5 < 0 )
            goto LABEL_39;
          v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(v14, &IID_IVdsSwProvider, &v16);
          if ( v14 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            v14 = 0;
          }
          if ( v6 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 24LL))(v16, &v17);
            if ( v16 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              v16 = 0;
            }
            if ( v7 >= 0 )
            {
              while ( 1 )
              {
                v20 = 0;
                v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v17 + 24LL))(
                       v17,
                       1,
                       &v14,
                       &v20);
                v4 = v8;
                if ( v8 == 1 )
                  break;
                if ( v8 < 0 )
                  goto LABEL_39;
                v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(v14, &IID_IVdsPack, &v22);
                if ( v14 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                  v14 = 0;
                }
                if ( v9 >= 0 )
                {
                  v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v22 + 24LL))(v22, &v25);
                  if ( pv[0] )
                  {
                    CoTaskMemFree(pv[0]);
                    pv[0] = 0;
                  }
                  if ( v10 >= 0
                    && (BYTE4(pv[1]) & 1) == 0
                    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v18) >= 0 )
                  {
                    while ( 1 )
                    {
                      v21 = 0;
                      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v18 + 24LL))(
                              v18,
                              1,
                              &v14,
                              &v21);
                      v4 = v11;
                      if ( v11 == 1 )
                        break;
                      if ( v11 < 0 )
                        goto LABEL_39;
                      v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsDisk **))v14)(
                              v14,
                              &IID_IVdsDisk,
                              &v15);
                      if ( v14 )
                      {
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                        v14 = 0;
                      }
                      if ( v12 >= 0 )
                      {
                        v4 = ((__int64 (__fastcall *)(struct IVdsDisk *, struct _VDS_DISK_PROP *))v15->lpVtbl->GetProperties)(
                               v15,
                               &v24);
                        if ( v4 >= 0 )
                        {
                          if ( !wcsncmp_0(v24.pwszName, String2, 0x104u) )
                          {
                            *a2 = v15;
                            v15 = 0;
                            goto LABEL_39;
                          }
                          if ( v15 )
                          {
                            ((void (__fastcall *)(struct IVdsDisk *))v15->lpVtbl->Release)(v15);
                            v15 = 0;
                          }
                        }
                      }
                    }
                    if ( v18 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                      v18 = 0;
                    }
                  }
                }
              }
              if ( v17 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                v17 = 0;
              }
            }
          }
        }
        v4 = -2147023728;
      }
LABEL_39:
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v14 = 0;
      }
      if ( v23 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        v23 = 0;
      }
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v16 = 0;
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      if ( v22 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        v22 = 0;
      }
      if ( v15 )
      {
        ((void (__fastcall *)(struct IVdsDisk *))v15->lpVtbl->Release)(v15);
        v15 = 0;
      }
      if ( v18 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v18 = 0;
      }
    }
    else
    {
      v4 = -1063256042;
    }
  }
  else
  {
    v4 = -2147467261;
  }
  SAFE_FREE_DISKPROP(&v24);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005884  push    rbp
0x180005886  push    rbx
0x180005887  push    rsi
0x180005888  push    rdi
0x180005889  push    r14
0x18000588b  push    r15
0x18000588d  lea     rbp, [rsp-38h]
0x180005892  sub     rsp, 138h
0x180005899  mov     rax, cs:__security_cookie
0x1800058a0  xor     rax, rsp
0x1800058a3  mov     [rbp+60h+var_40], rax
0x1800058a7  xor     r14d, r14d
0x1800058aa  mov     rdi, rdx
0x1800058ad  mov     [rdx], r14
0x1800058b0  mov     rsi, rcx
0x1800058b3  xor     edx, edx; Val
0x1800058b5  mov     [rsp+160h+var_130], r14
0x1800058ba  mov     r8d, 80h; Size
0x1800058c0  mov     [rsp+160h+var_F0], r14
0x1800058c5  lea     rcx, [rbp+60h+var_E0]; void *
0x1800058c9  mov     [rsp+160h+var_120], r14
0x1800058ce  mov     [rsp+160h+var_118], r14
0x1800058d3  mov     [rsp+160h+var_F8], r14
0x1800058d8  mov     [rsp+160h+var_128], r14
0x1800058dd  mov     [rsp+160h+var_110], r14
0x1800058e2  mov     [rsp+160h+var_108], r14d
0x1800058e7  mov     [rsp+160h+var_104], r14d
0x1800058ec  mov     [rsp+160h+var_100], r14d
0x1800058f1  call    memset_0
0x1800058f6  xorps   xmm0, xmm0
0x1800058f9  movups  [rbp+60h+var_60], xmm0
0x1800058fd  movups  xmmword ptr [rbp+60h+pv], xmm0
0x180005901  test    rsi, rsi
0x180005904  jnz     short loc_180005910
0x180005906  mov     ebx, 80004003h
0x18000590b  jmp     loc_180005CAA
0x180005910  mov     rcx, cs:?g_pService@@3PEAUIVdsService@@EA; IVdsService * g_pService
0x180005917  test    rcx, rcx
0x18000591a  jnz     short loc_180005926
0x18000591c  mov     ebx, 0C0A00016h
0x180005921  jmp     loc_180005CAA
0x180005926  mov     rax, [rcx]
0x180005929  lea     r8, [rsp+160h+var_F0]
0x18000592e  mov     r15d, 1
0x180005934  mov     edx, r15d
0x180005937  mov     rax, [rax+30h]
0x18000593b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005940  mov     ebx, eax
0x180005942  test    eax, eax
0x180005944  js      loc_180005BED
0x18000594a  mov     rcx, [rsp+160h+var_F0]
0x18000594f  lea     r9, [rsp+160h+var_108]
0x180005954  mov     [rsp+160h+var_108], r14d
0x180005959  lea     r8, [rsp+160h+var_130]
0x18000595e  mov     edx, r15d
0x180005961  mov     rax, [rcx]
0x180005964  mov     rax, [rax+18h]
0x180005968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596d  mov     ebx, eax
0x18000596f  cmp     eax, r15d
0x180005972  jz      loc_180005BE8
0x180005978  test    eax, eax
0x18000597a  js      loc_180005BED
0x180005980  mov     rcx, [rsp+160h+var_130]
0x180005985  lea     r8, [rsp+160h+var_120]
0x18000598a  lea     rdx, IID_IVdsSwProvider
0x180005991  mov     rax, [rcx]
0x180005994  mov     rax, [rax]
0x180005997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000599c  mov     rcx, [rsp+160h+var_130]
0x1800059a1  mov     ebx, eax
0x1800059a3  test    rcx, rcx
0x1800059a6  jz      short loc_1800059B9
0x1800059a8  mov     rdx, [rcx]
0x1800059ab  mov     rax, [rdx+10h]
0x1800059af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b4  mov     [rsp+160h+var_130], r14
0x1800059b9  test    ebx, ebx
0x1800059bb  js      short loc_18000594A
0x1800059bd  mov     rcx, [rsp+160h+var_120]
0x1800059c2  lea     rdx, [rsp+160h+var_118]
0x1800059c7  mov     rax, [rcx]
0x1800059ca  mov     rax, [rax+18h]
0x1800059ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d3  mov     rcx, [rsp+160h+var_120]
0x1800059d8  mov     ebx, eax
0x1800059da  test    rcx, rcx
0x1800059dd  jz      short loc_1800059F0
0x1800059df  mov     rdx, [rcx]
0x1800059e2  mov     rax, [rdx+10h]
0x1800059e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059eb  mov     [rsp+160h+var_120], r14
0x1800059f0  test    ebx, ebx
0x1800059f2  js      loc_18000594A
0x1800059f8  mov     rcx, [rsp+160h+var_118]
0x1800059fd  lea     r9, [rsp+160h+var_104]
0x180005a02  mov     [rsp+160h+var_104], r14d
0x180005a07  lea     r8, [rsp+160h+var_130]
0x180005a0c  mov     edx, r15d
0x180005a0f  mov     rax, [rcx]
0x180005a12  mov     rax, [rax+18h]
0x180005a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a1b  mov     ebx, eax
0x180005a1d  cmp     eax, r15d
0x180005a20  jz      loc_180005BB5
0x180005a26  test    eax, eax
0x180005a28  js      loc_180005BED
0x180005a2e  mov     rcx, [rsp+160h+var_130]
0x180005a33  lea     r8, [rsp+160h+var_F8]
0x180005a38  lea     rdx, IID_IVdsPack
0x180005a3f  mov     rax, [rcx]
0x180005a42  mov     rax, [rax]
0x180005a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a4a  mov     rcx, [rsp+160h+var_130]
0x180005a4f  mov     ebx, eax
0x180005a51  test    rcx, rcx
0x180005a54  jz      short loc_180005A67
0x180005a56  mov     rdx, [rcx]
0x180005a59  mov     rax, [rdx+10h]
0x180005a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a62  mov     [rsp+160h+var_130], r14
0x180005a67  test    ebx, ebx
0x180005a69  js      short loc_1800059F8
0x180005a6b  mov     rcx, [rsp+160h+var_F8]
0x180005a70  lea     rdx, [rbp+60h+var_60]
0x180005a74  mov     rax, [rcx]
0x180005a77  mov     rax, [rax+18h]
0x180005a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a80  mov     rcx, [rbp+60h+pv]; pv
0x180005a84  mov     ebx, eax
0x180005a86  test    rcx, rcx
0x180005a89  jz      short loc_180005A95
0x180005a8b  call    cs:__imp_CoTaskMemFree
0x180005a91  mov     [rbp+60h+pv], r14
0x180005a95  test    ebx, ebx
0x180005a97  js      loc_1800059F8
0x180005a9d  test    byte ptr [rbp+60h+pv+0Ch], r15b
0x180005aa1  jnz     loc_1800059F8
0x180005aa7  mov     rcx, [rsp+160h+var_F8]
0x180005aac  lea     rdx, [rsp+160h+var_110]
0x180005ab1  mov     rax, [rcx]
0x180005ab4  mov     rax, [rax+30h]
0x180005ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005abd  test    eax, eax
0x180005abf  js      loc_1800059F8
0x180005ac5  mov     rcx, [rsp+160h+var_110]
0x180005aca  lea     r9, [rsp+160h+var_100]
0x180005acf  mov     [rsp+160h+var_100], r14d
0x180005ad4  lea     r8, [rsp+160h+var_130]
0x180005ad9  mov     edx, r15d
0x180005adc  mov     rax, [rcx]
0x180005adf  mov     rax, [rax+18h]
0x180005ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae8  mov     ebx, eax
0x180005aea  cmp     eax, r15d
0x180005aed  jz      loc_180005B91
0x180005af3  test    eax, eax
0x180005af5  js      loc_180005BED
0x180005afb  mov     rcx, [rsp+160h+var_130]
0x180005b00  lea     r8, [rsp+160h+var_128]
0x180005b05  lea     rdx, IID_IVdsDisk
0x180005b0c  mov     rax, [rcx]
0x180005b0f  mov     rax, [rax]
0x180005b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b17  mov     rcx, [rsp+160h+var_130]
0x180005b1c  mov     ebx, eax
0x180005b1e  test    rcx, rcx
0x180005b21  jz      short loc_180005B34
0x180005b23  mov     rdx, [rcx]
0x180005b26  mov     rax, [rdx+10h]
0x180005b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2f  mov     [rsp+160h+var_130], r14
0x180005b34  test    ebx, ebx
0x180005b36  js      short loc_180005AC5
0x180005b38  mov     rcx, [rsp+160h+var_128]
0x180005b3d  lea     rdx, [rbp+60h+var_E0]
0x180005b41  mov     rax, [rcx]
0x180005b44  mov     rax, [rax+18h]
0x180005b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b4d  mov     ebx, eax
0x180005b4f  test    eax, eax
0x180005b51  js      loc_180005AC5
0x180005b57  mov     rcx, [rbp+60h+var_E0.pwszName]; String1
0x180005b5b  mov     r8d, 104h; MaxCount
0x180005b61  mov     rdx, rsi; String2
0x180005b64  call    wcsncmp_0
0x180005b69  test    eax, eax
0x180005b6b  jz      short loc_180005BD9
0x180005b6d  mov     rcx, [rsp+160h+var_128]
0x180005b72  test    rcx, rcx
0x180005b75  jz      loc_180005AC5
0x180005b7b  mov     rax, [rcx]
0x180005b7e  mov     rax, [rax+10h]
0x180005b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b87  mov     [rsp+160h+var_128], r14
0x180005b8c  jmp     loc_180005AC5
0x180005b91  mov     rcx, [rsp+160h+var_110]
0x180005b96  test    rcx, rcx
0x180005b99  jz      loc_1800059F8
0x180005b9f  mov     rax, [rcx]
0x180005ba2  mov     rax, [rax+10h]
0x180005ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bab  mov     [rsp+160h+var_110], r14
0x180005bb0  jmp     loc_1800059F8
0x180005bb5  mov     rcx, [rsp+160h+var_118]
0x180005bba  test    rcx, rcx
0x180005bbd  jz      loc_18000594A
0x180005bc3  mov     rax, [rcx]
0x180005bc6  mov     rax, [rax+10h]
0x180005bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bcf  mov     [rsp+160h+var_118], r14
0x180005bd4  jmp     loc_18000594A
0x180005bd9  mov     rax, [rsp+160h+var_128]
0x180005bde  mov     [rdi], rax
0x180005be1  mov     [rsp+160h+var_128], r14
0x180005be6  jmp     short loc_180005BED
0x180005be8  mov     ebx, 80070490h
0x180005bed  mov     rcx, [rsp+160h+var_130]
0x180005bf2  test    rcx, rcx
0x180005bf5  jz      short loc_180005C08
0x180005bf7  mov     rax, [rcx]
0x180005bfa  mov     rax, [rax+10h]
0x180005bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c03  mov     [rsp+160h+var_130], r14
0x180005c08  mov     rcx, [rsp+160h+var_F0]
0x180005c0d  test    rcx, rcx
0x180005c10  jz      short loc_180005C23
0x180005c12  mov     rax, [rcx]
0x180005c15  mov     rax, [rax+10h]
0x180005c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1e  mov     [rsp+160h+var_F0], r14
0x180005c23  mov     rcx, [rsp+160h+var_120]
0x180005c28  test    rcx, rcx
0x180005c2b  jz      short loc_180005C3E
0x180005c2d  mov     rax, [rcx]
0x180005c30  mov     rax, [rax+10h]
0x180005c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c39  mov     [rsp+160h+var_120], r14
0x180005c3e  mov     rcx, [rsp+160h+var_118]
0x180005c43  test    rcx, rcx
0x180005c46  jz      short loc_180005C59
0x180005c48  mov     rax, [rcx]
0x180005c4b  mov     rax, [rax+10h]
0x180005c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c54  mov     [rsp+160h+var_118], r14
0x180005c59  mov     rcx, [rsp+160h+var_F8]
0x180005c5e  test    rcx, rcx
0x180005c61  jz      short loc_180005C74
0x180005c63  mov     rax, [rcx]
0x180005c66  mov     rax, [rax+10h]
0x180005c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c6f  mov     [rsp+160h+var_F8], r14
0x180005c74  mov     rcx, [rsp+160h+var_128]
0x180005c79  test    rcx, rcx
0x180005c7c  jz      short loc_180005C8F
0x180005c7e  mov     rax, [rcx]
0x180005c81  mov     rax, [rax+10h]
0x180005c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c8a  mov     [rsp+160h+var_128], r14
0x180005c8f  mov     rcx, [rsp+160h+var_110]
0x180005c94  test    rcx, rcx
0x180005c97  jz      short loc_180005CAA
0x180005c99  mov     rax, [rcx]
0x180005c9c  mov     rax, [rax+10h]
0x180005ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ca5  mov     [rsp+160h+var_110], r14
0x180005caa  lea     rcx, [rbp+60h+var_E0]; struct _VDS_DISK_PROP *
0x180005cae  call    ?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z; SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)
0x180005cb3  mov     rcx, [rbp+60h+pv]; pv
0x180005cb7  test    rcx, rcx
0x180005cba  jz      short loc_180005CC2
0x180005cbc  call    cs:__imp_CoTaskMemFree
0x180005cc2  mov     eax, ebx
0x180005cc4  mov     rcx, [rbp+60h+var_40]
0x180005cc8  xor     rcx, rsp; StackCookie
0x180005ccb  call    __security_check_cookie
0x180005cd0  add     rsp, 138h
0x180005cd7  pop     r15
0x180005cd9  pop     r14
0x180005cdb  pop     rdi
0x180005cdc  pop     rsi
0x180005cdd  pop     rbx
0x180005cde  pop     rbp
0x180005cdf  retn
```
