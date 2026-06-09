# BdeCfgpFindFirstVolume(int (*)(IVdsVolume *,unsigned __int64),unsigned __int64,IVdsVolume * *)

- ea: `0x180005ce8`
- end: `0x1800060fe`
- name: `?BdeCfgpFindFirstVolume@@YAJP6AHPEAUIVdsVolume@@_K@Z1PEAPEAU1@@Z`
- size: `1046`
- prototype: `__int64 __fastcall(unsigned int (__fastcall *)(struct IVdsVolume *, __int64), __int64, struct IVdsVolume **)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003240`
- `0x180003f30`
- `0x180003f50`
- `0x1800040d0`
- `0x1800050b8`
- `0x18000fb40`
- `0x1800101a0`

## callees

- `0x180005ce8`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005ec9`
- `ole32!CoTaskMemFree` at `0x1800060ab`
- `ole32!CoTaskMemFree` at `0x180005ec9`
- `ole32!CoTaskMemFree` at `0x1800060ab`

## pseudocode

```c
__int64 __fastcall BdeCfgpFindFirstVolume(
        unsigned int (__fastcall *a1)(struct IVdsVolume *, __int64),
        __int64 a2,
        struct IVdsVolume **a3)
{
  int v7; // ebx
  int v8; // eax
  int v9; // ebx
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  int v13; // ebx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // [rsp+30h] [rbp-69h] BYREF
  __int64 v17; // [rsp+38h] [rbp-61h] BYREF
  struct IVdsVolume *v18; // [rsp+40h] [rbp-59h] BYREF
  __int64 v19; // [rsp+48h] [rbp-51h] BYREF
  __int64 v20; // [rsp+50h] [rbp-49h] BYREF
  __int64 v21; // [rsp+58h] [rbp-41h] BYREF
  int v22; // [rsp+60h] [rbp-39h] BYREF
  int v23; // [rsp+64h] [rbp-35h] BYREF
  int v24; // [rsp+68h] [rbp-31h] BYREF
  __int64 v25; // [rsp+70h] [rbp-29h] BYREF
  __int128 v26; // [rsp+78h] [rbp-21h] BYREF
  LPVOID pv[2]; // [rsp+88h] [rbp-11h]
  __int128 v28; // [rsp+98h] [rbp-1h]

  v16 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v25 = 0;
  v21 = 0;
  v18 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( !g_pService )
    return 3231711254LL;
  *a3 = 0;
  v28 = 0;
  v26 = 0;
  *(_OWORD *)pv = 0;
  v7 = ((__int64 (__fastcall *)(struct IVdsService *, __int64, __int64 *))g_pService->lpVtbl->QueryProviders)(
         g_pService,
         1,
         &v17);
  if ( v7 < 0 )
  {
LABEL_35:
    v15 = v17;
  }
  else
  {
    while ( 1 )
    {
      v22 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v17 + 24LL))(v17, 1, &v16, &v22);
      v7 = v8;
      if ( v8 == 1 )
        break;
      if ( v8 < 0 )
        goto LABEL_35;
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IVdsSwProvider, &v19);
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v16 = 0;
      }
      if ( v9 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 24LL))(v19, &v20);
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          v19 = 0;
        }
        if ( v10 >= 0 )
        {
          while ( 1 )
          {
            v23 = 0;
            v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v20 + 24LL))(
                    v20,
                    1,
                    &v16,
                    &v23);
            v7 = v11;
            if ( v11 == 1 )
              break;
            if ( v11 < 0 )
              goto LABEL_35;
            v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IVdsPack, &v25);
            if ( v16 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              v16 = 0;
            }
            if ( v12 >= 0 )
            {
              v13 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v25 + 24LL))(v25, &v26);
              if ( pv[0] )
              {
                CoTaskMemFree(pv[0]);
                pv[0] = 0;
              }
              if ( v13 >= 0
                && (BYTE4(pv[1]) & 1) == 0
                && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 40LL))(v25, &v21) >= 0 )
              {
                while ( 1 )
                {
                  v24 = 0;
                  v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v21 + 24LL))(
                          v21,
                          1,
                          &v16,
                          &v24);
                  v7 = v14;
                  if ( v14 == 1 )
                    break;
                  if ( v14 < 0 )
                    goto LABEL_35;
                  v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsVolume **))v16)(
                         v16,
                         &IID_IVdsVolume,
                         &v18);
                  if ( v16 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                    v16 = 0;
                  }
                  if ( v7 >= 0 )
                  {
                    if ( a1(v18, a2) )
                    {
                      *a3 = v18;
                      v18 = 0;
                      goto LABEL_35;
                    }
                    if ( v18 )
                    {
                      ((void (__fastcall *)(struct IVdsVolume *))v18->lpVtbl->Release)(v18);
                      v18 = 0;
                    }
                  }
                }
                if ( v21 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                  v21 = 0;
                }
              }
            }
          }
          if ( v20 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v20 = 0;
          }
        }
      }
    }
    v15 = v17;
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v15 = 0;
      v17 = 0;
    }
    v7 = 1;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v15 = v17;
    v16 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v17 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v18 )
  {
    ((void (__fastcall *)(struct IVdsVolume *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005ce8  mov     [rsp-8+arg_18], rbx
0x180005ced  push    rbp
0x180005cee  push    rsi
0x180005cef  push    rdi
0x180005cf0  push    r12
0x180005cf2  push    r13
0x180005cf4  push    r14
0x180005cf6  push    r15
0x180005cf8  lea     rbp, [rsp-27h]
0x180005cfd  sub     rsp, 0C0h
0x180005d04  mov     rax, cs:__security_cookie
0x180005d0b  xor     rax, rsp
0x180005d0e  mov     [rbp+57h+var_40], rax
0x180005d12  xor     r15d, r15d
0x180005d15  mov     rdi, r8
0x180005d18  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, r15; IVdsService * g_pService
0x180005d1f  mov     r14, rdx
0x180005d22  mov     rsi, rcx
0x180005d25  mov     [rbp+57h+var_C0], r15
0x180005d29  mov     [rbp+57h+var_B8], r15
0x180005d2d  mov     [rbp+57h+var_A8], r15
0x180005d31  mov     [rbp+57h+var_A0], r15
0x180005d35  mov     [rbp+57h+var_80], r15
0x180005d39  mov     [rbp+57h+var_98], r15
0x180005d3d  mov     [rbp+57h+var_B0], r15
0x180005d41  mov     [rbp+57h+var_90], r15d
0x180005d45  mov     [rbp+57h+var_8C], r15d
0x180005d49  mov     [rbp+57h+var_88], r15d
0x180005d4d  jnz     short loc_180005D59
0x180005d4f  mov     eax, 0C0A00016h
0x180005d54  jmp     loc_1800060B3
0x180005d59  xorps   xmm0, xmm0
0x180005d5c  mov     [r8], r15
0x180005d5f  mov     rcx, cs:?g_pService@@3PEAUIVdsService@@EA; IVdsService * g_pService
0x180005d66  lea     r8, [rbp+57h+var_B8]
0x180005d6a  movups  [rbp+57h+var_78], xmm0
0x180005d6e  mov     r12d, 1
0x180005d74  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180005d78  mov     edx, r12d
0x180005d7b  movups  [rbp+57h+var_58], xmm0
0x180005d7f  movups  [rbp+57h+var_78], xmm0
0x180005d83  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180005d87  mov     rax, [rcx]
0x180005d8a  mov     rax, [rax+30h]
0x180005d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d93  mov     ebx, eax
0x180005d95  test    eax, eax
0x180005d97  js      loc_180005FEC
0x180005d9d  mov     rcx, [rbp+57h+var_B8]
0x180005da1  lea     r9, [rbp+57h+var_90]
0x180005da5  mov     [rbp+57h+var_90], r15d
0x180005da9  lea     r8, [rbp+57h+var_C0]
0x180005dad  mov     edx, r12d
0x180005db0  mov     rax, [rcx]
0x180005db3  mov     rax, [rax+18h]
0x180005db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbc  mov     ebx, eax
0x180005dbe  cmp     eax, r12d
0x180005dc1  jz      loc_1800060DA
0x180005dc7  test    eax, eax
0x180005dc9  js      loc_180005FEC
0x180005dcf  mov     rcx, [rbp+57h+var_C0]
0x180005dd3  lea     r8, [rbp+57h+var_A8]
0x180005dd7  lea     rdx, IID_IVdsSwProvider
0x180005dde  mov     rax, [rcx]
0x180005de1  mov     rax, [rax]
0x180005de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de9  mov     rcx, [rbp+57h+var_C0]
0x180005ded  mov     ebx, eax
0x180005def  test    rcx, rcx
0x180005df2  jz      short loc_180005E04
0x180005df4  mov     rdx, [rcx]
0x180005df7  mov     rax, [rdx+10h]
0x180005dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e00  mov     [rbp+57h+var_C0], r15
0x180005e04  test    ebx, ebx
0x180005e06  js      short loc_180005D9D
0x180005e08  mov     rcx, [rbp+57h+var_A8]
0x180005e0c  lea     rdx, [rbp+57h+var_A0]
0x180005e10  mov     rax, [rcx]
0x180005e13  mov     rax, [rax+18h]
0x180005e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1c  mov     rcx, [rbp+57h+var_A8]
0x180005e20  mov     ebx, eax
0x180005e22  test    rcx, rcx
0x180005e25  jz      short loc_180005E37
0x180005e27  mov     rdx, [rcx]
0x180005e2a  mov     rax, [rdx+10h]
0x180005e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e33  mov     [rbp+57h+var_A8], r15
0x180005e37  test    ebx, ebx
0x180005e39  js      loc_180005D9D
0x180005e3f  mov     rcx, [rbp+57h+var_A0]
0x180005e43  lea     r9, [rbp+57h+var_8C]
0x180005e47  mov     [rbp+57h+var_8C], r15d
0x180005e4b  lea     r8, [rbp+57h+var_C0]
0x180005e4f  mov     edx, r12d
0x180005e52  mov     rax, [rcx]
0x180005e55  mov     rax, [rax+18h]
0x180005e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5e  mov     ebx, eax
0x180005e60  cmp     eax, r12d
0x180005e63  jz      loc_180005FBF
0x180005e69  test    eax, eax
0x180005e6b  js      loc_180005FEC
0x180005e71  mov     rcx, [rbp+57h+var_C0]
0x180005e75  lea     r8, [rbp+57h+var_80]
0x180005e79  lea     rdx, IID_IVdsPack
0x180005e80  mov     rax, [rcx]
0x180005e83  mov     rax, [rax]
0x180005e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8b  mov     rcx, [rbp+57h+var_C0]
0x180005e8f  mov     ebx, eax
0x180005e91  test    rcx, rcx
0x180005e94  jz      short loc_180005EA6
0x180005e96  mov     rdx, [rcx]
0x180005e99  mov     rax, [rdx+10h]
0x180005e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea2  mov     [rbp+57h+var_C0], r15
0x180005ea6  test    ebx, ebx
0x180005ea8  js      short loc_180005E3F
0x180005eaa  mov     rcx, [rbp+57h+var_80]
0x180005eae  lea     rdx, [rbp+57h+var_78]
0x180005eb2  mov     rax, [rcx]
0x180005eb5  mov     rax, [rax+18h]
0x180005eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ebe  mov     rcx, [rbp+57h+pv]; pv
0x180005ec2  mov     ebx, eax
0x180005ec4  test    rcx, rcx
0x180005ec7  jz      short loc_180005ED3
0x180005ec9  call    cs:__imp_CoTaskMemFree
0x180005ecf  mov     [rbp+57h+pv], r15
0x180005ed3  test    ebx, ebx
0x180005ed5  js      loc_180005E3F
0x180005edb  test    byte ptr [rbp+57h+pv+0Ch], r12b
0x180005edf  jnz     loc_180005E3F
0x180005ee5  mov     rcx, [rbp+57h+var_80]
0x180005ee9  lea     rdx, [rbp+57h+var_98]
0x180005eed  mov     rax, [rcx]
0x180005ef0  mov     rax, [rax+28h]
0x180005ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef9  test    eax, eax
0x180005efb  js      loc_180005E3F
0x180005f01  mov     rcx, [rbp+57h+var_98]
0x180005f05  lea     r9, [rbp+57h+var_88]
0x180005f09  mov     [rbp+57h+var_88], r15d
0x180005f0d  lea     r8, [rbp+57h+var_C0]
0x180005f11  mov     edx, r12d
0x180005f14  mov     rax, [rcx]
0x180005f17  mov     rax, [rax+18h]
0x180005f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f20  mov     ebx, eax
0x180005f22  cmp     eax, r12d
0x180005f25  jz      short loc_180005F9D
0x180005f27  test    eax, eax
0x180005f29  js      loc_180005FEC
0x180005f2f  mov     rcx, [rbp+57h+var_C0]
0x180005f33  lea     r8, [rbp+57h+var_B0]
0x180005f37  lea     rdx, IID_IVdsVolume
0x180005f3e  mov     rax, [rcx]
0x180005f41  mov     rax, [rax]
0x180005f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f49  mov     rcx, [rbp+57h+var_C0]
0x180005f4d  mov     ebx, eax
0x180005f4f  test    rcx, rcx
0x180005f52  jz      short loc_180005F64
0x180005f54  mov     rax, [rcx]
0x180005f57  mov     rax, [rax+10h]
0x180005f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f60  mov     [rbp+57h+var_C0], r15
0x180005f64  test    ebx, ebx
0x180005f66  js      short loc_180005F01
0x180005f68  mov     rcx, [rbp+57h+var_B0]
0x180005f6c  mov     rdx, r14
0x180005f6f  mov     rax, rsi
0x180005f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f77  test    eax, eax
0x180005f79  jnz     short loc_180005FE1
0x180005f7b  mov     rcx, [rbp+57h+var_B0]
0x180005f7f  test    rcx, rcx
0x180005f82  jz      loc_180005F01
0x180005f88  mov     rax, [rcx]
0x180005f8b  mov     rax, [rax+10h]
0x180005f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f94  mov     [rbp+57h+var_B0], r15
0x180005f98  jmp     loc_180005F01
0x180005f9d  mov     rcx, [rbp+57h+var_98]
0x180005fa1  test    rcx, rcx
0x180005fa4  jz      loc_180005E3F
0x180005faa  mov     rax, [rcx]
0x180005fad  mov     rax, [rax+10h]
0x180005fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb6  mov     [rbp+57h+var_98], r15
0x180005fba  jmp     loc_180005E3F
0x180005fbf  mov     rcx, [rbp+57h+var_A0]
0x180005fc3  test    rcx, rcx
0x180005fc6  jz      loc_180005D9D
0x180005fcc  mov     rax, [rcx]
0x180005fcf  mov     rax, [rax+10h]
0x180005fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd8  mov     [rbp+57h+var_A0], r15
0x180005fdc  jmp     loc_180005D9D
0x180005fe1  mov     rax, [rbp+57h+var_B0]
0x180005fe5  mov     [rdi], rax
0x180005fe8  mov     [rbp+57h+var_B0], r15
0x180005fec  mov     rcx, [rbp+57h+var_B8]
0x180005ff0  mov     rdx, [rbp+57h+var_C0]
0x180005ff4  test    rdx, rdx
0x180005ff7  jz      short loc_180006010
0x180005ff9  mov     rax, [rdx]
0x180005ffc  mov     rcx, rdx
0x180005fff  mov     rax, [rax+10h]
0x180006003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006008  mov     rcx, [rbp+57h+var_B8]
0x18000600c  mov     [rbp+57h+var_C0], r15
0x180006010  test    rcx, rcx
0x180006013  jz      short loc_180006025
0x180006015  mov     rax, [rcx]
0x180006018  mov     rax, [rax+10h]
0x18000601c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006021  mov     [rbp+57h+var_B8], r15
0x180006025  mov     rcx, [rbp+57h+var_A8]
0x180006029  test    rcx, rcx
0x18000602c  jz      short loc_18000603E
0x18000602e  mov     rax, [rcx]
0x180006031  mov     rax, [rax+10h]
0x180006035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000603a  mov     [rbp+57h+var_A8], r15
0x18000603e  mov     rcx, [rbp+57h+var_A0]
0x180006042  test    rcx, rcx
0x180006045  jz      short loc_180006057
0x180006047  mov     rax, [rcx]
0x18000604a  mov     rax, [rax+10h]
0x18000604e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006053  mov     [rbp+57h+var_A0], r15
0x180006057  mov     rcx, [rbp+57h+var_80]
0x18000605b  test    rcx, rcx
0x18000605e  jz      short loc_180006070
0x180006060  mov     rax, [rcx]
0x180006063  mov     rax, [rax+10h]
0x180006067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000606c  mov     [rbp+57h+var_80], r15
0x180006070  mov     rcx, [rbp+57h+var_98]
0x180006074  test    rcx, rcx
0x180006077  jz      short loc_180006089
0x180006079  mov     rax, [rcx]
0x18000607c  mov     rax, [rax+10h]
0x180006080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006085  mov     [rbp+57h+var_98], r15
0x180006089  mov     rcx, [rbp+57h+var_B0]
0x18000608d  test    rcx, rcx
0x180006090  jz      short loc_1800060A2
0x180006092  mov     rax, [rcx]
0x180006095  mov     rax, [rax+10h]
0x180006099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000609e  mov     [rbp+57h+var_B0], r15
0x1800060a2  mov     rcx, [rbp+57h+pv]; pv
0x1800060a6  test    rcx, rcx
0x1800060a9  jz      short loc_1800060B1
0x1800060ab  call    cs:__imp_CoTaskMemFree
0x1800060b1  mov     eax, ebx
0x1800060b3  mov     rcx, [rbp+57h+var_40]
0x1800060b7  xor     rcx, rsp; StackCookie
0x1800060ba  call    __security_check_cookie
0x1800060bf  mov     rbx, [rsp+0F0h+arg_18]
0x1800060c7  add     rsp, 0C0h
0x1800060ce  pop     r15
0x1800060d0  pop     r14
0x1800060d2  pop     r13
0x1800060d4  pop     r12
0x1800060d6  pop     rdi
0x1800060d7  pop     rsi
0x1800060d8  pop     rbp
0x1800060d9  retn
0x1800060da  mov     rcx, [rbp+57h+var_B8]
0x1800060de  test    rcx, rcx
0x1800060e1  jz      short loc_1800060F6
0x1800060e3  mov     rax, [rcx]
0x1800060e6  mov     rax, [rax+10h]
0x1800060ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ef  mov     rcx, r15
0x1800060f2  mov     [rbp+57h+var_B8], rcx
0x1800060f6  mov     ebx, r12d
0x1800060f9  jmp     loc_180005FF0
```
