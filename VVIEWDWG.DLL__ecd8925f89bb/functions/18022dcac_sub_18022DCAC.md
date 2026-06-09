# sub_18022DCAC

- ea: `0x18022dcac`
- end: `0x18022e0a9`
- name: `sub_18022DCAC`
- size: `1021`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation`

## callers

- `0x18022dcac`
- `0x18022e0b0`

## callees

- `0x180002ad0`
- `0x180002b7c`
- `0x180002bc0`
- `0x1800da9b0`
- `0x1800daae8`
- `0x1800dab50`
- `0x1800fafd0`
- `0x1800fb3c4`
- `0x1800fe86c`
- `0x18013e410`
- `0x18013e9e0`
- `0x18013ea4c`
- `0x18013f804`
- `0x1801625dc`
- `0x1801e6d78`
- `0x1801efd10`
- `0x18022dcac`
- `0x1802966e8`
- `0x180296b38`
- `0x1802a2278`
- `0x1802a4de4`
- `0x1802a4e80`
- `0x1802aea58`
- `0x1802ee7ac`
- `0x1802ee8f0`
- `0x1802ee960`
- `0x1804c7dfe`
- `0x1804c82c0`

## string_xrefs

- `0x18022dd30`: `ACLYDICTIONARY`
- `0x18022debc`: `ACLYDICTIONARY`

## pseudocode

```c
__int64 __fastcall sub_18022DCAC(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 i; // rsi
  _QWORD *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  _BYTE v34[8]; // [rsp+20h] [rbp-79h] BYREF
  __int64 v35; // [rsp+28h] [rbp-71h] BYREF
  _BYTE pExceptionObject[8]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v37[8]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v38[8]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v39[8]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v40[8]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v41[8]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v42[8]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v43[16]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v44; // [rsp+78h] [rbp-21h]
  _BYTE v45[16]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v46[16]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v47[8]; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v48[8]; // [rsp+A8h] [rbp+Fh] BYREF
  _BYTE v49[64]; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v50; // [rsp+110h] [rbp+77h] BYREF

  v8 = sub_180002B7C(a2);
  v9 = sub_1802A4E80(v8, pExceptionObject);
  v10 = sub_1801E6D78(v9, v37, 1, 0);
  sub_1800FAFD0(v34, v10);
  sub_1800DAAE8(v37);
  if ( !(unsigned __int8)sub_180002BC0(v34) )
  {
    v12 = sub_180002B7C(v34);
    sub_18013E9E0((__int64)&v50, L"ACLYDICTIONARY");
    sub_1802966E8(v12, pExceptionObject, &v50);
    sub_18013EA4C(&v50);
  }
  unknown_libname_1(&v35, v11);
  for ( i = 0;
        (unsigned int)i < *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 120LL))(*a3) - 4LL);
        i = (unsigned int)(i + 1) )
  {
    v14 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 120LL))(*a3);
    if ( (unsigned int)i >= *(_DWORD *)(*v14 - 4LL) )
    {
      sub_18013E410(pExceptionObject);
      throw (OdError_InvalidIndex *)pExceptionObject;
    }
    unknown_libname_1(&v50, *v14);
    v16 = *(_QWORD *)(v15 + 8 * i);
    v50 = v16;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
      v16 = v50;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v16 + 152LL))(v16) )
    {
      if ( (unsigned __int8)sub_180002BC0(&v35) )
      {
        v17 = *(_QWORD *)sub_1801625DC(v40);
        sub_1800DAB50(&v35);
        v35 = v17;
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
        sub_1800DAAE8(v40);
        if ( (unsigned __int8)sub_180002BC0(v34) )
        {
          v18 = sub_180002B7C(a2);
          sub_1802A2278(v18);
          sub_1802AEA58(*(_QWORD *)(v18 + 8));
          v19 = sub_180002B7C(a2);
          v20 = sub_1802A4E80(v19, v47);
          v21 = sub_1801E6D78(v20, v41, 1, 0);
          v22 = sub_180002B7C(v21);
          sub_1800DAB50(v34);
          sub_1800FE86C(v34, v22);
          sub_1800DAAE8(v41);
        }
        v23 = sub_180002B7C(v34);
        v24 = sub_180002B7C(&v35);
        sub_18013E9E0((__int64)v37, L"ACLYDICTIONARY");
        sub_180296B38(v23, v48, v37, v24);
        sub_18013EA4C(v37);
      }
      sub_1801EFD10(v39);
      v25 = sub_180002B7C(v39);
      sub_1802EE7AC(v43, v25, a1);
      v27 = v50;
      if ( *a4 == v50 )
      {
        LOBYTE(v26) = 1;
        sub_1802EE960(v43, 290, v26);
        v27 = v50;
      }
      v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
      v29 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v28 + 136LL))(v28, v42);
      sub_1802EE8F0(v43, 1, v29);
      sub_18013EA4C(v42);
      (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v50 + 232LL))(v50, v43);
      sub_1800DA9B0(v38);
      sub_18013F804(v38, L"*A%d", (unsigned int)i);
      v30 = sub_180002B7C(&v35);
      sub_180296B38(v30, v49, v38, v25);
      v31 = sub_1800FB3C4(pExceptionObject, v39);
      sub_18022DCAC(a1, v31, &v50, a4);
      sub_18013EA4C(v38);
      sub_1800DAAE8(v46);
      sub_1800DAAE8(v45);
      if ( v44 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 40LL))(v44);
        v44 = 0;
      }
      sub_1800DAAE8(v39);
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 40LL))(v50);
      v50 = 0;
    }
  }
  v32 = sub_180002B7C(a2);
  sub_1802A4DE4(v32);
  sub_1800DAAE8(&v35);
  sub_1800DAAE8(v34);
  return sub_1800DAAE8(a2);
}

```

## disassembly

```asm
0x18022dcac  mov     [rsp-8+arg_0], rbx
0x18022dcb1  mov     [rsp-8+arg_8], rdx
0x18022dcb6  push    rbp
0x18022dcb7  push    rsi
0x18022dcb8  push    rdi
0x18022dcb9  push    r12
0x18022dcbb  push    r13
0x18022dcbd  push    r14
0x18022dcbf  push    r15
0x18022dcc1  lea     rbp, [rsp-27h]
0x18022dcc6  sub     rsp, 0C0h
0x18022dccd  mov     r12, r9
0x18022dcd0  mov     r15, r8
0x18022dcd3  mov     r14, rdx
0x18022dcd6  mov     r13, rcx
0x18022dcd9  mov     rcx, rdx
0x18022dcdc  call    sub_180002B7C
0x18022dce1  lea     rdx, [rbp+57h+pExceptionObject]
0x18022dce5  mov     rcx, rax
0x18022dce8  call    sub_1802A4E80
0x18022dced  xor     r9d, r9d
0x18022dcf0  lea     r8d, [r9+1]
0x18022dcf4  lea     rdx, [rbp+57h+var_B8]
0x18022dcf8  mov     rcx, rax
0x18022dcfb  call    sub_1801E6D78
0x18022dd00  nop
0x18022dd01  mov     rdx, rax
0x18022dd04  lea     rcx, [rbp+57h+var_D0]
0x18022dd08  call    sub_1800FAFD0
0x18022dd0d  nop
0x18022dd0e  lea     rcx, [rbp+57h+var_B8]
0x18022dd12  call    sub_1800DAAE8
0x18022dd17  lea     rcx, [rbp+57h+var_D0]
0x18022dd1b  call    sub_180002BC0
0x18022dd20  test    al, al
0x18022dd22  jnz     short loc_18022DD5B
0x18022dd24  lea     rcx, [rbp+57h+var_D0]
0x18022dd28  call    sub_180002B7C
0x18022dd2d  mov     rbx, rax
0x18022dd30  lea     rdx, aAclydictionary; "ACLYDICTIONARY"
0x18022dd37  lea     rcx, [rbp+57h+arg_10]
0x18022dd3b  call    sub_18013E9E0
0x18022dd40  nop
0x18022dd41  lea     r8, [rbp+57h+arg_10]
0x18022dd45  lea     rdx, [rbp+57h+pExceptionObject]
0x18022dd49  mov     rcx, rbx
0x18022dd4c  call    sub_1802966E8
0x18022dd51  nop
0x18022dd52  lea     rcx, [rbp+57h+arg_10]
0x18022dd56  call    sub_18013EA4C
0x18022dd5b  lea     rcx, [rbp+57h+var_C8]
0x18022dd5f  call    unknown_libname_1; Microsoft VisualC v7/14 64bit runtime
0x18022dd64  xor     esi, esi
0x18022dd66  mov     rcx, [r15]
0x18022dd69  mov     rax, [rcx]
0x18022dd6c  mov     rax, [rax+78h]
0x18022dd70  call    cs:__guard_dispatch_icall_fptr
0x18022dd76  mov     rcx, [rax]
0x18022dd79  cmp     esi, [rcx-4]
0x18022dd7c  jnb     loc_18022E04B
0x18022dd82  mov     rcx, [r15]
0x18022dd85  mov     rax, [rcx]
0x18022dd88  mov     rax, [rax+78h]
0x18022dd8c  call    cs:__guard_dispatch_icall_fptr
0x18022dd92  mov     rdx, [rax]
0x18022dd95  cmp     esi, [rdx-4]
0x18022dd98  jnb     loc_18022E08F
0x18022dd9e  lea     rcx, [rbp+57h+arg_10]
0x18022dda2  call    unknown_libname_1; Microsoft VisualC v7/14 64bit runtime
0x18022dda7  mov     rcx, [rdx+rsi*8]
0x18022ddab  mov     [rbp+57h+arg_10], rcx
0x18022ddaf  test    rcx, rcx
0x18022ddb2  jz      short loc_18022DDC5
0x18022ddb4  mov     rax, [rcx]
0x18022ddb7  mov     rax, [rax+20h]
0x18022ddbb  call    cs:__guard_dispatch_icall_fptr
0x18022ddc1  mov     rcx, [rbp+57h+arg_10]
0x18022ddc5  mov     rax, [rcx]
0x18022ddc8  mov     rax, [rax+98h]
0x18022ddcf  call    cs:__guard_dispatch_icall_fptr
0x18022ddd5  test    al, al
0x18022ddd7  jz      short loc_18022DDDE
0x18022ddd9  jmp     loc_18022E026
0x18022ddde  lea     rcx, [rbp+57h+var_C8]
0x18022dde2  call    sub_180002BC0
0x18022dde7  test    al, al
0x18022dde9  jz      loc_18022DEEA
0x18022ddef  lea     rcx, [rbp+57h+var_A0]
0x18022ddf3  call    sub_1801625DC
0x18022ddf8  mov     rbx, [rax]
0x18022ddfb  lea     rcx, [rbp+57h+var_C8]
0x18022ddff  call    sub_1800DAB50
0x18022de04  mov     [rbp+57h+var_C8], rbx
0x18022de08  test    rbx, rbx
0x18022de0b  jz      short loc_18022DE20
0x18022de0d  mov     rax, [rbx]
0x18022de10  mov     rcx, rbx
0x18022de13  mov     rax, [rax+20h]
0x18022de17  call    cs:__guard_dispatch_icall_fptr
0x18022de1d  nop
0x18022de1e  xchg    ax, ax
0x18022de20  lea     rcx, [rbp+57h+var_A0]
0x18022de24  call    sub_1800DAAE8
0x18022de29  lea     rcx, [rbp+57h+var_D0]
0x18022de2d  call    sub_180002BC0
0x18022de32  test    al, al
0x18022de34  jz      short loc_18022DEA4
0x18022de36  mov     rcx, r14
0x18022de39  call    sub_180002B7C
0x18022de3e  mov     rbx, rax
0x18022de41  mov     rcx, rax
0x18022de44  call    sub_1802A2278
0x18022de49  mov     rcx, [rbx+8]
0x18022de4d  call    sub_1802AEA58
0x18022de52  mov     rcx, r14
0x18022de55  call    sub_180002B7C
0x18022de5a  lea     rdx, [rbp+57h+var_50]
0x18022de5e  mov     rcx, rax
0x18022de61  call    sub_1802A4E80
0x18022de66  xor     r9d, r9d
0x18022de69  lea     r8d, [r9+1]
0x18022de6d  lea     rdx, [rbp+57h+var_98]
0x18022de71  mov     rcx, rax
0x18022de74  call    sub_1801E6D78
0x18022de79  nop
0x18022de7a  mov     rcx, rax
0x18022de7d  call    sub_180002B7C
0x18022de82  mov     rbx, rax
0x18022de85  lea     rcx, [rbp+57h+var_D0]
0x18022de89  call    sub_1800DAB50
0x18022de8e  mov     rdx, rbx
0x18022de91  lea     rcx, [rbp+57h+var_D0]
0x18022de95  call    sub_1800FE86C
0x18022de9a  nop
0x18022de9b  lea     rcx, [rbp+57h+var_98]
0x18022de9f  call    sub_1800DAAE8
0x18022dea4  lea     rcx, [rbp+57h+var_D0]
0x18022dea8  call    sub_180002B7C
0x18022dead  mov     rdi, rax
0x18022deb0  lea     rcx, [rbp+57h+var_C8]
0x18022deb4  call    sub_180002B7C
0x18022deb9  mov     rbx, rax
0x18022debc  lea     rdx, aAclydictionary; "ACLYDICTIONARY"
0x18022dec3  lea     rcx, [rbp+57h+var_B8]
0x18022dec7  call    sub_18013E9E0
0x18022decc  nop
0x18022decd  mov     r9, rbx
0x18022ded0  lea     r8, [rbp+57h+var_B8]
0x18022ded4  lea     rdx, [rbp+57h+var_48]
0x18022ded8  mov     rcx, rdi
0x18022dedb  call    sub_180296B38
0x18022dee0  nop
0x18022dee1  lea     rcx, [rbp+57h+var_B8]
0x18022dee5  call    sub_18013EA4C
0x18022deea  lea     rcx, [rbp+57h+var_A8]
0x18022deee  call    sub_1801EFD10
0x18022def3  nop
0x18022def4  lea     rcx, [rbp+57h+var_A8]
0x18022def8  call    sub_180002B7C
0x18022defd  mov     rbx, rax
0x18022df00  mov     r8, r13
0x18022df03  mov     rdx, rax
0x18022df06  lea     rcx, [rbp+57h+var_88]
0x18022df0a  call    sub_1802EE7AC
0x18022df0f  nop
0x18022df10  mov     rcx, [rbp+57h+arg_10]
0x18022df14  cmp     [r12], rcx
0x18022df18  jnz     short loc_18022DF2F
0x18022df1a  mov     r8b, 1
0x18022df1d  mov     edx, 122h
0x18022df22  lea     rcx, [rbp+57h+var_88]
0x18022df26  call    sub_1802EE960
0x18022df2b  mov     rcx, [rbp+57h+arg_10]
0x18022df2f  mov     rax, [rcx]
0x18022df32  mov     rax, [rax+18h]
0x18022df36  call    cs:__guard_dispatch_icall_fptr
0x18022df3c  mov     r8, rax
0x18022df3f  mov     rcx, [rax]
0x18022df42  mov     rax, [rcx+88h]
0x18022df49  lea     rdx, [rbp+57h+var_90]
0x18022df4d  mov     rcx, r8
0x18022df50  call    cs:__guard_dispatch_icall_fptr
0x18022df56  nop
0x18022df57  mov     r8, rax
0x18022df5a  mov     edx, 1
0x18022df5f  lea     rcx, [rbp+57h+var_88]
0x18022df63  call    sub_1802EE8F0
0x18022df68  nop
0x18022df69  lea     rcx, [rbp+57h+var_90]
0x18022df6d  call    sub_18013EA4C
0x18022df72  mov     rcx, [rbp+57h+arg_10]
0x18022df76  mov     rax, [rcx]
0x18022df79  lea     rdx, [rbp+57h+var_88]
0x18022df7d  mov     rax, [rax+0E8h]
0x18022df84  call    cs:__guard_dispatch_icall_fptr
0x18022df8a  lea     rcx, [rbp+57h+var_B0]
0x18022df8e  call    sub_1800DA9B0
0x18022df93  nop
0x18022df94  mov     r8d, esi
0x18022df97  lea     rdx, aAD; "*A%d"
0x18022df9e  lea     rcx, [rbp+57h+var_B0]
0x18022dfa2  call    sub_18013F804
0x18022dfa7  lea     rcx, [rbp+57h+var_C8]
0x18022dfab  call    sub_180002B7C
0x18022dfb0  mov     r9, rbx
0x18022dfb3  lea     r8, [rbp+57h+var_B0]
0x18022dfb7  lea     rdx, [rbp+57h+var_40]
0x18022dfbb  mov     rcx, rax
0x18022dfbe  call    sub_180296B38
0x18022dfc3  lea     rdx, [rbp+57h+var_A8]
0x18022dfc7  lea     rcx, [rbp+57h+pExceptionObject]
0x18022dfcb  call    sub_1800FB3C4
0x18022dfd0  mov     r9, r12
0x18022dfd3  lea     r8, [rbp+57h+arg_10]
0x18022dfd7  mov     rdx, rax
0x18022dfda  mov     rcx, r13
0x18022dfdd  call    sub_18022DCAC
0x18022dfe2  nop
0x18022dfe3  lea     rcx, [rbp+57h+var_B0]
0x18022dfe7  call    sub_18013EA4C
0x18022dfec  lea     rcx, [rbp+57h+var_60]
0x18022dff0  call    sub_1800DAAE8
0x18022dff5  lea     rcx, [rbp+57h+var_70]
0x18022dff9  call    sub_1800DAAE8
0x18022dffe  mov     rcx, [rbp+57h+var_78]
0x18022e002  test    rcx, rcx
0x18022e005  jz      short loc_18022E01C
0x18022e007  mov     rax, [rcx]
0x18022e00a  mov     rax, [rax+28h]
0x18022e00e  call    cs:__guard_dispatch_icall_fptr
0x18022e014  mov     [rbp+57h+var_78], 0
0x18022e01c  lea     rcx, [rbp+57h+var_A8]
0x18022e020  call    sub_1800DAAE8
0x18022e025  nop
0x18022e026  mov     rcx, [rbp+57h+arg_10]
0x18022e02a  test    rcx, rcx
0x18022e02d  jz      short loc_18022E044
0x18022e02f  mov     rax, [rcx]
0x18022e032  mov     rax, [rax+28h]
0x18022e036  call    cs:__guard_dispatch_icall_fptr
0x18022e03c  mov     [rbp+57h+arg_10], 0
0x18022e044  inc     esi
0x18022e046  jmp     loc_18022DD66
0x18022e04b  mov     rcx, r14
0x18022e04e  call    sub_180002B7C
0x18022e053  mov     rcx, rax
0x18022e056  call    sub_1802A4DE4
0x18022e05b  lea     rcx, [rbp+57h+var_C8]
0x18022e05f  call    sub_1800DAAE8
0x18022e064  lea     rcx, [rbp+57h+var_D0]
0x18022e068  call    sub_1800DAAE8
0x18022e06d  mov     rcx, r14
0x18022e070  mov     rbx, [rsp+0F0h+arg_0]
0x18022e078  add     rsp, 0C0h
0x18022e07f  pop     r15
0x18022e081  pop     r14
0x18022e083  pop     r13
0x18022e085  pop     r12
0x18022e087  pop     rdi
0x18022e088  pop     rsi
0x18022e089  pop     rbp
0x18022e08a  jmp     sub_1800DAAE8
0x18022e08f  lea     rcx, [rbp+57h+pExceptionObject]
0x18022e093  call    sub_18013E410
0x18022e098  lea     rdx, __TI2?AVOdError_InvalidIndex@@; pThrowInfo
0x18022e09f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18022e0a3  call    _CxxThrowException
```
