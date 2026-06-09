# CClipLicense::EnsureModernLicenseForContentIdWithUserTicket(ushort const *,int,int,ushort *,long *)

- ea: `0x180012f54`
- end: `0x18001319d`
- name: `?EnsureModernLicenseForContentIdWithUserTicket@CClipLicense@@SAJPEBGHHPEAGPEAJ@Z`
- size: `585`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, int, unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001324c`
- `0x180016f70`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x180012f54`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012fd2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012fd2`

## pseudocode

```c
__int64 __fastcall CClipLicense::EnsureModernLicenseForContentIdWithUserTicket(
        const unsigned __int16 *a1,
        __int64 a2,
        int a3,
        unsigned __int16 *a4,
        int *a5)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  HRESULT v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  LPVOID ppv; // [rsp+50h] [rbp-30h] BYREF
  __int64 *v16; // [rsp+58h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-20h] BYREF
  __int64 v18; // [rsp+68h] [rbp-18h] BYREF
  __int64 v19; // [rsp+70h] [rbp-10h] BYREF

  ppv = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  if ( !a5 || !a1 )
  {
    v8 = 2147942487LL;
    v9 = -2147024809;
    goto LABEL_3;
  }
  v10 = CoCreateInstance(
          &GUID_22f5b1df_7d7a_4d21_97f8_c21aefba859c,
          0,
          4u,
          &GUID_fa4a3cd4_e3f0_4875_9c69_cad5423d05f4,
          &ppv);
  if ( v10 < 0
    || (v10 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                ppv,
                &GUID_0000013d_0000_0000_c000_000000000046,
                &v19),
        v10 < 0)
    || (v10 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, __int64, __int64, _DWORD, int, _QWORD, int))(*(_QWORD *)v19 + 32LL))(
                v19,
                ppv,
                0xFFFFFFFFLL,
                0xFFFFFFFFLL,
                -1,
                0,
                3,
                0,
                2048),
        v10 < 0) )
  {
    v9 = 0;
  }
  else
  {
    v11 = *(_QWORD *)ppv;
    if ( a3 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))v11)(
              ppv,
              &GUID_1c733a30_2a1c_11ce_ade5_00aa0044773d,
              &v17);
      v9 = v12;
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD, GUID *, __int64 **))(*(_QWORD *)v17 + 24LL))(
                v17,
                &GUID_7270d1d5_679d_4f8c_a152_a0b2b46d6d5f,
                0,
                &GUID_7270d1d5_679d_4f8c_a152_a0b2b46d6d5f,
                &v16);
        v9 = v12;
        if ( v12 >= 0 )
        {
          v13 = *v16;
          if ( a4 )
            v10 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, unsigned __int16 *))(v13 + 40))(
                    v16,
                    a1,
                    a4);
          else
            v10 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(v13 + 24))(v16, a1);
          if ( v10 >= 0 )
            v10 = 1;
          goto LABEL_21;
        }
      }
      v8 = (unsigned int)v12;
LABEL_3:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
      goto LABEL_22;
    }
    v9 = 0;
    if ( a4 )
      v10 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, unsigned __int16 *, __int64 *))(v11 + 32))(
              ppv,
              a1,
              a4,
              &v18);
    else
      v10 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(v11 + 24))(ppv, a1, &v18);
  }
LABEL_21:
  *a5 = v10;
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v9;
}

```

## disassembly

```asm
0x180012f54  push    rbp
0x180012f56  push    rbx
0x180012f57  push    rsi
0x180012f58  push    rdi
0x180012f59  push    r14
0x180012f5b  mov     rbp, rsp
0x180012f5e  sub     rsp, 80h
0x180012f65  mov     rdi, [rbp+arg_20]
0x180012f69  mov     r14, r9
0x180012f6c  mov     [rbp+var_30], 0
0x180012f74  mov     ebx, r8d
0x180012f77  mov     [rbp+var_10], 0
0x180012f7f  mov     rsi, rcx
0x180012f82  mov     [rbp+var_18], 0
0x180012f8a  mov     [rbp+var_20], 0
0x180012f92  mov     [rbp+var_28], 0
0x180012f9a  test    rdi, rdi
0x180012f9d  jnz     short loc_180012FB0
0x180012f9f  mov     ecx, 80070057h
0x180012fa4  mov     ebx, ecx
0x180012fa6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012fab  jmp     loc_1800130FD
0x180012fb0  test    rsi, rsi
0x180012fb3  jz      short loc_180012F9F
0x180012fb5  xor     edx, edx; pUnkOuter
0x180012fb7  lea     rax, [rbp+var_30]
0x180012fbb  lea     r9, _GUID_fa4a3cd4_e3f0_4875_9c69_cad5423d05f4; riid
0x180012fc2  mov     [rsp+80h+ppv], rax; ppv
0x180012fc7  lea     rcx, _GUID_22f5b1df_7d7a_4d21_97f8_c21aefba859c; rclsid
0x180012fce  lea     r8d, [rdx+4]; dwClsContext
0x180012fd2  call    cs:__imp_CoCreateInstance
0x180012fd8  test    eax, eax
0x180012fda  jns     short loc_180012FE3
0x180012fdc  xor     ebx, ebx
0x180012fde  jmp     loc_1800130FB
0x180012fe3  mov     rcx, [rbp+var_30]
0x180012fe7  lea     r8, [rbp+var_10]
0x180012feb  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x180012ff2  mov     rax, [rcx]
0x180012ff5  mov     rax, [rax]
0x180012ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ffd  test    eax, eax
0x180012fff  js      short loc_180012FDC
0x180013001  mov     rcx, [rbp+var_10]
0x180013005  or      r8d, 0FFFFFFFFh
0x180013009  mov     rdx, [rbp+var_30]
0x18001300d  mov     r9d, r8d
0x180013010  mov     [rsp+80h+var_40], 800h
0x180013018  mov     [rsp+80h+var_48], 0
0x180013021  mov     rax, [rcx]
0x180013024  mov     [rsp+80h+var_50], 3
0x18001302c  mov     [rsp+80h+var_58], 0
0x180013034  mov     [rsp+80h+ppv], 0FFFFFFFFFFFFFFFFh
0x18001303d  mov     rax, [rax+20h]
0x180013041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013046  test    eax, eax
0x180013048  js      short loc_180012FDC
0x18001304a  mov     rcx, [rbp+var_30]
0x18001304e  mov     rax, [rcx]
0x180013051  test    ebx, ebx
0x180013053  jz      short loc_1800130D2
0x180013055  mov     rax, [rax]
0x180013058  lea     r8, [rbp+var_20]
0x18001305c  lea     rdx, _GUID_1c733a30_2a1c_11ce_ade5_00aa0044773d
0x180013063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013068  mov     ebx, eax
0x18001306a  test    eax, eax
0x18001306c  jns     short loc_180013075
0x18001306e  mov     ecx, eax
0x180013070  jmp     loc_180012FA6
0x180013075  mov     rcx, [rbp+var_20]
0x180013079  lea     rdx, [rbp+var_28]
0x18001307d  mov     [rsp+80h+ppv], rdx
0x180013082  xor     r8d, r8d
0x180013085  lea     rdx, _GUID_7270d1d5_679d_4f8c_a152_a0b2b46d6d5f
0x18001308c  mov     r9, rdx
0x18001308f  mov     rax, [rcx]
0x180013092  mov     rax, [rax+18h]
0x180013096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001309b  mov     ebx, eax
0x18001309d  test    eax, eax
0x18001309f  js      short loc_18001306E
0x1800130a1  mov     rcx, [rbp+var_28]
0x1800130a5  mov     rdx, rsi
0x1800130a8  mov     rax, [rcx]
0x1800130ab  test    r14, r14
0x1800130ae  jz      short loc_1800130BE
0x1800130b0  mov     rax, [rax+28h]
0x1800130b4  mov     r8, r14
0x1800130b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130bc  jmp     short loc_1800130C7
0x1800130be  mov     rax, [rax+18h]
0x1800130c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130c7  test    eax, eax
0x1800130c9  js      short loc_1800130FB
0x1800130cb  mov     eax, 1
0x1800130d0  jmp     short loc_1800130FB
0x1800130d2  xor     ebx, ebx
0x1800130d4  mov     rdx, rsi
0x1800130d7  test    r14, r14
0x1800130da  jz      short loc_1800130EE
0x1800130dc  mov     rax, [rax+20h]
0x1800130e0  lea     r9, [rbp+var_18]
0x1800130e4  mov     r8, r14
0x1800130e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130ec  jmp     short loc_1800130FB
0x1800130ee  mov     rax, [rax+18h]
0x1800130f2  lea     r8, [rbp+var_18]
0x1800130f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130fb  mov     [rdi], eax
0x1800130fd  mov     ecx, ebx
0x1800130ff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013104  mov     rcx, [rbp+var_28]
0x180013108  test    rcx, rcx
0x18001310b  jz      short loc_180013121
0x18001310d  mov     rax, [rcx]
0x180013110  mov     rax, [rax+10h]
0x180013114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013119  mov     [rbp+var_28], 0
0x180013121  mov     rcx, [rbp+var_20]
0x180013125  test    rcx, rcx
0x180013128  jz      short loc_18001313E
0x18001312a  mov     rax, [rcx]
0x18001312d  mov     rax, [rax+10h]
0x180013131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013136  mov     [rbp+var_20], 0
0x18001313e  mov     rcx, [rbp+var_18]
0x180013142  test    rcx, rcx
0x180013145  jz      short loc_18001315B
0x180013147  mov     rax, [rcx]
0x18001314a  mov     rax, [rax+10h]
0x18001314e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013153  mov     [rbp+var_18], 0
0x18001315b  mov     rcx, [rbp+var_10]
0x18001315f  test    rcx, rcx
0x180013162  jz      short loc_180013178
0x180013164  mov     rax, [rcx]
0x180013167  mov     rax, [rax+10h]
0x18001316b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013170  mov     [rbp+var_10], 0
0x180013178  mov     rcx, [rbp+var_30]
0x18001317c  test    rcx, rcx
0x18001317f  jz      short loc_18001318D
0x180013181  mov     rax, [rcx]
0x180013184  mov     rax, [rax+10h]
0x180013188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001318d  mov     eax, ebx
0x18001318f  add     rsp, 80h
0x180013196  pop     r14
0x180013198  pop     rdi
0x180013199  pop     rsi
0x18001319a  pop     rbx
0x18001319b  pop     rbp
0x18001319c  retn
```
