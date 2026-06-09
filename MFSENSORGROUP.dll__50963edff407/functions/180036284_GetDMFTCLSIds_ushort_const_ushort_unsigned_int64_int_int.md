# GetDMFTCLSIds(ushort const *,ushort *,unsigned __int64 *,int *,int *)

- ea: `0x180036284`
- end: `0x180036606`
- name: `?GetDMFTCLSIds@@YAJPEBGPEAGPEA_KPEAH3@Z`
- size: `898`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int64 *@<r8>, int *@<r9>, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800544c4`
- `0x1800553d8`

## callees

- `0x180005fa0`
- `0x1800261a8`
- `0x180036284`
- `0x180044f30`
- `0x180051cf8`

## string_xrefs

- `0x1800364f9`: `CameraDeviceMftClsid`
- `0x18003659e`: `CameraPostProcessingPluginCLSID`
- `0x1800363b4`: `CameraDeviceMftClsidChain`

## pseudocode

```c
__int64 __fastcall GetDMFTCLSIds(
        const unsigned __int16 *a1,
        unsigned __int8 *a2,
        unsigned __int64 a3,
        int *a4,
        int *a5)
{
  __int64 v7; // rdx
  int *v8; // rdi
  unsigned __int64 *v9; // rsi
  unsigned int v10; // r12d
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int v14; // r15d
  DWORD v15; // r15d
  int v16; // eax
  unsigned __int16 v17; // cx
  __int64 v18; // rdx
  unsigned __int8 *v19; // rcx
  __int64 v20; // rax
  unsigned __int8 *v21; // rax
  int v22; // eax
  unsigned __int64 v23; // rcx
  unsigned int *v25; // [rsp+28h] [rbp-79h]
  unsigned int *v26; // [rsp+28h] [rbp-79h]
  unsigned int *v27; // [rsp+28h] [rbp-79h]
  unsigned int v28; // [rsp+30h] [rbp-71h] BYREF
  unsigned __int8 v29[4]; // [rsp+34h] [rbp-6Dh] BYREF
  int *v30; // [rsp+38h] [rbp-69h]
  int *v31; // [rsp+40h] [rbp-61h]
  unsigned __int8 v32[80]; // [rsp+50h] [rbp-51h] BYREF

  v30 = a4;
  v7 = 0;
  v31 = a5;
  *(_DWORD *)v29 = 0;
  v8 = a4;
  v28 = 0;
  v9 = (unsigned __int64 *)a3;
  v10 = 0;
  if ( !a1 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_55;
    v13 = 142;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_55;
    v13 = 143;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_55;
    v13 = 144;
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_55;
    v13 = 145;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_55;
    v13 = 146;
    goto LABEL_4;
  }
  v14 = *(_DWORD *)a3;
  *(_WORD *)a2 = 0;
  v15 = 2 * v14;
  *a4 = 0;
  *a5 = 0;
  *(_QWORD *)a3 = 0;
  v16 = FSGetDeviceInterfaceRegistryEntry2(a1, L"CameraDeviceMftClsidChain", a2, v15, &v28, v25);
  a3 = 0;
  v12 = v16;
  if ( v16 >= 0 )
  {
    v7 = v28;
    if ( v28 < 4 )
    {
      v11 = -2147024883;
      v12 = -2147024883;
      if ( !g_wppLevels )
        goto LABEL_55;
      v13 = 147;
      goto LABEL_4;
    }
    v17 = *(_WORD *)&a2[2 * ((unsigned __int64)v28 >> 1) - 2];
    if ( v17 || *(_WORD *)&a2[2 * ((unsigned __int64)v28 >> 1) - 4] )
    {
      v7 = (v17 != 0 ? 4 : 2) + v28;
      v28 = v7;
      if ( (unsigned int)v7 > v15 )
      {
        *v9 = (unsigned __int64)(unsigned int)v7 >> 1;
        v12 = -1072860816;
        if ( !g_wppLevels )
          goto LABEL_55;
        v18 = 148;
        goto LABEL_27;
      }
      *(_DWORD *)&a2[v7 - 4] = 0;
    }
    v19 = a2;
    while ( 1 )
    {
      if ( (unsigned int)a3 >= 4 )
        goto LABEL_39;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v19[2 * v20] );
      if ( !v20 )
      {
        v10 = a3;
LABEL_39:
        *v9 = (unsigned __int64)(v19 - a2) >> 1;
        goto LABEL_49;
      }
      v21 = &v19[2 * v20];
      v19 = v21 + 2;
      *(_WORD *)v21 = 59;
      if ( v21 + 2 > &a2[(unsigned int)v7] )
        break;
      a3 = (unsigned int)(a3 + 1);
    }
    v11 = -2147024883;
    v12 = -2147024883;
    if ( !g_wppLevels )
      goto LABEL_55;
    v13 = 149;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v11);
    goto LABEL_55;
  }
  if ( v16 == -1072860816 )
  {
    *v9 = (unsigned __int64)v28 >> 1;
    if ( !g_wppLevels )
      goto LABEL_55;
    v18 = 150;
    goto LABEL_27;
  }
  v22 = FSGetDeviceInterfaceRegistryEntry2(a1, L"CameraDeviceMftClsid", a2, v15, &v28, v26);
  v12 = v22;
  if ( v22 == -1072860816 )
  {
    *v9 = (unsigned __int64)v28 >> 1;
    if ( !g_wppLevels )
      goto LABEL_55;
    v18 = 151;
LABEL_27:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
      0,
      -1072860816);
    goto LABEL_55;
  }
  v8 = v30;
  if ( v22 < 0 )
  {
    *v9 = 0;
    v12 = 0;
  }
  else
  {
    v10 = 1;
    v23 = ((unsigned __int64)v28 >> 1) - 1;
    *v9 = v23;
    *(_WORD *)&a2[2 * v23] = 0;
  }
LABEL_49:
  if ( (int)FSGetDeviceInterfaceRegistryEntry2(a1, L"EnablePlatformDmft", v29, 4u, &v28, v26) >= 0 && *(_DWORD *)v29 )
  {
    *v8 = 1;
    ++v10;
  }
  if ( (int)FSGetDeviceInterfaceRegistryEntry2(a1, L"CameraPostProcessingPluginCLSID", v32, 0x4Eu, &v28, v27) >= 0
    && v28 > 1 )
  {
    *v31 = 1;
  }
LABEL_55:
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 27), v7, a3, v10, v12);
  return v12;
}

```

## disassembly

```asm
0x180036284  push    rbp
0x180036286  push    rbx
0x180036287  push    rsi
0x180036288  push    rdi
0x180036289  push    r12
0x18003628b  push    r13
0x18003628d  push    r14
0x18003628f  push    r15
0x180036291  lea     rbp, [rsp-17h]
0x180036296  sub     rsp, 0B8h
0x18003629d  mov     rax, cs:__security_cookie
0x1800362a4  xor     rax, rsp
0x1800362a7  mov     [rbp+4Fh+var_50], rax
0x1800362ab  mov     r13, rcx
0x1800362ae  mov     [rbp+4Fh+var_B8], r9
0x1800362b2  mov     rcx, [rbp+4Fh+arg_20]
0x1800362b6  mov     r14, rdx
0x1800362b9  xor     edx, edx
0x1800362bb  mov     [rbp+4Fh+var_B0], rcx
0x1800362bf  mov     dword ptr [rbp+4Fh+var_BC], edx
0x1800362c2  mov     rdi, r9
0x1800362c5  mov     [rbp+4Fh+var_C0], edx
0x1800362c8  mov     rsi, r8
0x1800362cb  mov     r12d, edx
0x1800362ce  test    r13, r13
0x1800362d1  jnz     short loc_18003630F
0x1800362d3  mov     eax, 80070057h
0x1800362d8  mov     ebx, eax
0x1800362da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800362e1  jb      loc_1800365C1
0x1800362e7  mov     edx, 8Eh
0x1800362ec  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800362f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362f7  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x1800362fe  xor     r9d, r9d
0x180036301  mov     rcx, [rcx+10h]
0x180036305  call    WPP_SF_qD
0x18003630a  jmp     loc_1800365C1
0x18003630f  test    r9, r9
0x180036312  jnz     short loc_18003632F
0x180036314  mov     eax, 80070057h
0x180036319  mov     ebx, eax
0x18003631b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180036322  jb      loc_1800365C1
0x180036328  mov     edx, 8Fh
0x18003632d  jmp     short loc_1800362EC
0x18003632f  test    rsi, rsi
0x180036332  jnz     short loc_18003634F
0x180036334  mov     eax, 80070057h
0x180036339  mov     ebx, eax
0x18003633b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180036342  jb      loc_1800365C1
0x180036348  mov     edx, 90h
0x18003634d  jmp     short loc_1800362EC
0x18003634f  test    rcx, rcx
0x180036352  jnz     short loc_180036372
0x180036354  mov     eax, 80070057h
0x180036359  mov     ebx, eax
0x18003635b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180036362  jb      loc_1800365C1
0x180036368  mov     edx, 91h
0x18003636d  jmp     loc_1800362EC
0x180036372  test    r14, r14
0x180036375  jnz     short loc_180036395
0x180036377  mov     eax, 80070057h
0x18003637c  mov     ebx, eax
0x18003637e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180036385  jb      loc_1800365C1
0x18003638b  mov     edx, 92h
0x180036390  jmp     loc_1800362EC
0x180036395  mov     r15d, [r8]
0x180036398  lea     rax, [rbp+4Fh+var_C0]
0x18003639c  mov     [r14], dx
0x1800363a0  add     r15d, r15d
0x1800363a3  mov     [r9], edx
0x1800363a6  mov     r9d, r15d; unsigned int
0x1800363a9  mov     [rcx], edx
0x1800363ab  mov     rcx, r13; unsigned __int16 *
0x1800363ae  mov     [r8], rdx
0x1800363b1  mov     r8, r14; unsigned __int8 *
0x1800363b4  lea     rdx, aCameradevicemf; "CameraDeviceMftClsidChain"
0x1800363bb  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x1800363c0  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x1800363c5  xor     r8d, r8d
0x1800363c8  mov     ebx, eax
0x1800363ca  test    eax, eax
0x1800363cc  js      loc_1800364C1
0x1800363d2  mov     edx, [rbp+4Fh+var_C0]
0x1800363d5  cmp     edx, 4
0x1800363d8  jnb     short loc_1800363F8
0x1800363da  mov     eax, 8007000Dh
0x1800363df  mov     ebx, eax
0x1800363e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800363e8  jb      loc_1800365C1
0x1800363ee  mov     edx, 93h
0x1800363f3  jmp     loc_1800362EC
0x1800363f8  mov     rax, rdx
0x1800363fb  shr     rax, 1
0x1800363fe  movzx   ecx, word ptr [r14+rax*2-2]
0x180036404  test    cx, cx
0x180036407  jnz     short loc_180036411
0x180036409  cmp     [r14+rax*2-4], r8w
0x18003640f  jz      short loc_180036457
0x180036411  neg     cx
0x180036414  sbb     eax, eax
0x180036416  and     eax, 2
0x180036419  add     eax, 2
0x18003641c  add     edx, eax
0x18003641e  mov     [rbp+4Fh+var_C0], edx
0x180036421  mov     eax, edx
0x180036423  cmp     edx, r15d
0x180036426  jbe     short loc_180036450
0x180036428  shr     rax, 1
0x18003642b  mov     edi, 0C00D7170h
0x180036430  mov     [rsi], rax
0x180036433  mov     ebx, edi
0x180036435  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003643c  jb      loc_1800365C1
0x180036442  mov     edx, 94h
0x180036447  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18003644b  jmp     loc_1800362F0
0x180036450  xor     ecx, ecx
0x180036452  mov     [r14+rdx-4], ecx
0x180036457  mov     rcx, r14
0x18003645a  xor     r15d, r15d
0x18003645d  cmp     r8d, 4
0x180036461  jnb     short loc_1800364B3
0x180036463  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036467  inc     rax
0x18003646a  cmp     [rcx+rax*2], r15w
0x18003646f  jnz     short loc_180036467
0x180036471  test    rax, rax
0x180036474  jz      short loc_1800364B0
0x180036476  lea     rax, [rcx+rax*2]
0x18003647a  lea     rcx, [rax+2]
0x18003647e  mov     word ptr [rax], 3Bh ; ';'
0x180036483  mov     eax, edx
0x180036485  add     rax, r14
0x180036488  cmp     rcx, rax
0x18003648b  ja      short loc_180036492
0x18003648d  inc     r8d
0x180036490  jmp     short loc_18003645D
0x180036492  mov     eax, 8007000Dh
0x180036497  mov     ebx, eax
0x180036499  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800364a0  jb      loc_1800365C1
0x1800364a6  mov     edx, 95h
0x1800364ab  jmp     loc_1800362EC
0x1800364b0  mov     r12d, r8d
0x1800364b3  sub     rcx, r14
0x1800364b6  shr     rcx, 1
0x1800364b9  mov     [rsi], rcx
0x1800364bc  jmp     loc_180036556
0x1800364c1  mov     edi, 0C00D7170h
0x1800364c6  cmp     eax, edi
0x1800364c8  jnz     short loc_1800364EA
0x1800364ca  mov     eax, [rbp+4Fh+var_C0]
0x1800364cd  shr     rax, 1
0x1800364d0  mov     [rsi], rax
0x1800364d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800364da  jb      loc_1800365C1
0x1800364e0  mov     edx, 96h
0x1800364e5  jmp     loc_180036447
0x1800364ea  lea     rax, [rbp+4Fh+var_C0]
0x1800364ee  mov     r9d, r15d; unsigned int
0x1800364f1  mov     r8, r14; unsigned __int8 *
0x1800364f4  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x1800364f9  lea     rdx, aCameradevicemf_0; "CameraDeviceMftClsid"
0x180036500  mov     rcx, r13; unsigned __int16 *
0x180036503  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x180036508  mov     ebx, eax
0x18003650a  cmp     eax, edi
0x18003650c  jnz     short loc_18003652E
0x18003650e  mov     eax, [rbp+4Fh+var_C0]
0x180036511  shr     rax, 1
0x180036514  mov     [rsi], rax
0x180036517  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003651e  jb      loc_1800365C1
0x180036524  mov     edx, 97h
0x180036529  jmp     loc_180036447
0x18003652e  mov     rdi, [rbp+4Fh+var_B8]
0x180036532  xor     r15d, r15d
0x180036535  test    eax, eax
0x180036537  js      short loc_180036550
0x180036539  mov     ecx, [rbp+4Fh+var_C0]
0x18003653c  lea     r12d, [r15+1]
0x180036540  shr     rcx, 1
0x180036543  dec     rcx
0x180036546  mov     [rsi], rcx
0x180036549  mov     [r14+rcx*2], r15w
0x18003654e  jmp     short loc_180036556
0x180036550  mov     [rsi], r15
0x180036553  mov     ebx, r15d
0x180036556  lea     rax, [rbp+4Fh+var_C0]
0x18003655a  mov     r9d, 4; unsigned int
0x180036560  lea     r8, [rbp+4Fh+var_BC]; unsigned __int8 *
0x180036564  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x180036569  lea     rdx, aEnableplatform; "EnablePlatformDmft"
0x180036570  mov     rcx, r13; unsigned __int16 *
0x180036573  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x180036578  test    eax, eax
0x18003657a  js      short loc_18003658B
0x18003657c  cmp     dword ptr [rbp+4Fh+var_BC], r15d
0x180036580  jz      short loc_18003658B
0x180036582  mov     dword ptr [rdi], 1
0x180036588  inc     r12d
0x18003658b  lea     rax, [rbp+4Fh+var_C0]
0x18003658f  mov     r9d, 4Eh ; 'N'; unsigned int
0x180036595  lea     r8, [rbp+4Fh+var_A0]; unsigned __int8 *
0x180036599  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18003659e  lea     rdx, aCamerapostproc; "CameraPostProcessingPluginCLSID"
0x1800365a5  mov     rcx, r13; unsigned __int16 *
0x1800365a8  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x1800365ad  test    eax, eax
0x1800365af  js      short loc_1800365C1
0x1800365b1  cmp     [rbp+4Fh+var_C0], 1
0x1800365b5  jbe     short loc_1800365C1
0x1800365b7  mov     rax, [rbp+4Fh+var_B0]
0x1800365bb  mov     dword ptr [rax], 1
0x1800365c1  cmp     cs:byte_18008D62D, 8
0x1800365c8  jb      short loc_1800365E4
0x1800365ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365d1  mov     r9d, r12d
0x1800365d4  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x1800365d8  mov     rcx, [rcx+0D8h]
0x1800365df  call    WPP_SF_dD
0x1800365e4  mov     eax, ebx
0x1800365e6  mov     rcx, [rbp+4Fh+var_50]
0x1800365ea  xor     rcx, rsp; StackCookie
0x1800365ed  call    __security_check_cookie
0x1800365f2  add     rsp, 0B8h
0x1800365f9  pop     r15
0x1800365fb  pop     r14
0x1800365fd  pop     r13
0x1800365ff  pop     r12
0x180036601  pop     rdi
0x180036602  pop     rsi
0x180036603  pop     rbx
0x180036604  pop     rbp
0x180036605  retn
```
