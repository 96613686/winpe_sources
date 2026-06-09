# LsaICLookupNames_0

- ea: `0x1800208f0`
- end: `0x18002113f`
- name: `LsaICLookupNames_0`
- size: `2127`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002062c`
- `0x18002270c`
- `0x1800372d0`
- `0x18003e690`

## callees

- `0x1800208f0`
- `0x1800635cc`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180021073`
- `ntdll!RtlSubAuthorityCountSid` at `0x180021073`
- `ntdll!RtlLengthSid` at `0x180021034`
- `ntdll!RtlLengthSid` at `0x18002109b`
- `ntdll!RtlLengthSid` at `0x1800210d1`
- `ntdll!RtlLengthSid` at `0x180021034`
- `ntdll!RtlLengthSid` at `0x18002109b`
- `ntdll!RtlLengthSid` at `0x1800210d1`
- `ntdll!RtlCopySid` at `0x180021053`
- `ntdll!RtlCopySid` at `0x1800210b6`
- `ntdll!RtlCopySid` at `0x180021053`
- `ntdll!RtlCopySid` at `0x1800210b6`
- `ntdll!RtlSubAuthoritySid` at `0x18002108a`
- `ntdll!RtlSubAuthoritySid` at `0x18002108a`
- `KERNELBASE!LocalAlloc` at `0x180020cd9`
- `KERNELBASE!LocalAlloc` at `0x180020cd9`
- `KERNEL32!LocalFree` at `0x180021108`
- `KERNEL32!LocalFree` at `0x18002111e`
- `KERNEL32!LocalFree` at `0x180021129`
- `KERNEL32!LocalFree` at `0x180021134`
- `KERNEL32!LocalFree` at `0x180021108`
- `KERNEL32!LocalFree` at `0x18002111e`
- `KERNEL32!LocalFree` at `0x180021129`
- `KERNEL32!LocalFree` at `0x180021134`
- `RPCRT4!I_RpcMapWin32Status` at `0x180020ac5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180020da5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180020ea5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180020ac5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180020da5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180020ea5`
- `RPCRT4!I_RpcExceptionFilter` at `0x180065425`
- `RPCRT4!I_RpcExceptionFilter` at `0x180065441`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006545d`
- `RPCRT4!I_RpcExceptionFilter` at `0x180065425`
- `RPCRT4!I_RpcExceptionFilter` at `0x180065441`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006545d`
- `RPCRT4!NdrClientCall3` at `0x180020a88`
- `RPCRT4!NdrClientCall3` at `0x180020e5f`
- `RPCRT4!NdrClientCall3` at `0x180020a88`
- `RPCRT4!NdrClientCall3` at `0x180020e5f`

## pseudocode

```c
__int64 __fastcall LsaICLookupNames_0(
        __int64 a1,
        ULONG a2,
        unsigned int a3,
        __int64 a4,
        HLOCAL *a5,
        HLOCAL *a6,
        int a7,
        char a8,
        __int64 a9,
        _DWORD *a10)
{
  __int64 v10; // r11
  __int64 v12; // r10
  HLOCAL *v13; // r8
  __int64 v14; // r9
  int v15; // esi
  unsigned int v16; // r13d
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  CLIENT_CALL_RETURN v20; // rax
  int Pointer; // ebx
  HLOCAL *v22; // rsi
  unsigned __int64 v24; // r14
  int v25; // eax
  unsigned int v26; // ecx
  size_t v27; // r12
  HLOCAL v28; // rax
  unsigned int i; // r14d
  int v30; // r10d
  int *v31; // r8
  int v32; // ecx
  __int64 v33; // r9
  __int64 v34; // r12
  void *v35; // r13
  ULONG v36; // r13d
  PUCHAR v37; // rax
  ULONG v38; // edx
  ULONG v39; // eax
  char *v40; // r13
  __int64 v41; // [rsp+20h] [rbp-148h]
  __int64 v42; // [rsp+40h] [rbp-128h]
  unsigned int v43; // [rsp+60h] [rbp-108h]
  __int64 v44; // [rsp+88h] [rbp-E0h] BYREF
  HLOCAL v45; // [rsp+90h] [rbp-D8h]
  unsigned int v46; // [rsp+98h] [rbp-D0h]
  ULONG v47; // [rsp+A0h] [rbp-C8h]
  __int64 v48; // [rsp+A8h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-B8h]
  __int64 v50; // [rsp+B8h] [rbp-B0h] BYREF
  HLOCAL v51; // [rsp+C0h] [rbp-A8h]
  PSID v52; // [rsp+C8h] [rbp-A0h]
  __int64 v53; // [rsp+D0h] [rbp-98h]
  ULONG v54; // [rsp+D8h] [rbp-90h]
  __int64 v55; // [rsp+E0h] [rbp-88h]
  __int64 v56; // [rsp+E8h] [rbp-80h]
  CLIENT_CALL_RETURN v57; // [rsp+F0h] [rbp-78h]
  __int64 v58; // [rsp+F8h] [rbp-70h]
  __int64 v59; // [rsp+100h] [rbp-68h]
  _BYTE DestinationSid[32]; // [rsp+108h] [rbp-60h] BYREF

  v10 = a4;
  v56 = a4;
  v54 = a2;
  v12 = a1;
  v55 = a1;
  v58 = a1;
  v47 = a2;
  v46 = a3;
  v59 = a4;
  v13 = a5;
  v14 = a9;
  v53 = a9;
  v52 = a10;
  v44 = 0;
  v45 = 0;
  v50 = 0;
  v51 = 0;
  v48 = 0;
  hMem = 0;
  *a5 = 0;
  *a6 = 0;
  if ( !a1 )
    return 3221225480LL;
  if ( a3 > 0x3E8 )
    return 3221225677LL;
  v15 = 3;
  v16 = 0;
  v43 = 0;
  if ( a10 )
    *a10 = 2;
  v17 = 3 - ((a8 & 5) != 0);
  if ( (a8 & 2) != 0 )
    v17 = 1;
  v18 = v17 - 1;
  if ( !v18 )
    goto LABEL_58;
  v19 = v18 - 1;
  if ( !v19 )
    goto LABEL_57;
  if ( v19 != 1 )
  {
    Pointer = -1073741811;
    goto LABEL_28;
  }
  v57.Simple = 0;
  v20.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&stru_180067210,
                  0x44u,
                  0,
                  *(_QWORD *)(v12 + 8),
                  a3,
                  v10,
                  a5,
                  &v44,
                  a7,
                  a9,
                  a2,
                  2).Pointer;
  Pointer = (int)v20.Pointer;
  v57.Pointer = v20.Pointer;
  a2 = v54;
  v12 = v55;
  v13 = a5;
  LODWORD(v10) = v56;
  v14 = v53;
  if ( LODWORD(v20.Pointer) == -1073610734 || LODWORD(v20.Pointer) == -1073610706 )
  {
LABEL_57:
    Pointer = LsarLookupNames2(*(_QWORD *)(v12 + 8), a3, v10, (_DWORD)v13, (__int64)&v50, a7, v14, a2);
    v15 = 2;
    if ( v51 )
      v16 = v50;
    v43 = v16;
    v12 = v55;
    v13 = a5;
    v10 = v56;
    v14 = v53;
    if ( Pointer == -1073610734 || Pointer == -1073610706 )
    {
LABEL_58:
      if ( a10 )
        *a10 = 1;
      v57.Simple = 0;
      LODWORD(v42) = a7;
      LODWORD(v41) = a3;
      v57.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&stru_180067210,
                      0xEu,
                      0,
                      *(_QWORD *)(v12 + 8),
                      v41,
                      v10,
                      v13,
                      &v48,
                      v42,
                      v14).Pointer;
      Pointer = (int)v57.Pointer;
      v15 = 1;
      if ( hMem )
        v16 = v48;
      v43 = v16;
      v13 = a5;
    }
  }
  if ( Pointer >= 0
    && a3
    && (v15 == 1 && (!(_DWORD)v48 || !hMem) || v15 == 2 && (!(_DWORD)v50 || !v51) || v15 == 3 && (!(_DWORD)v44 || !v45))
    || v15 == 1 && !(_DWORD)v48 && hMem
    || v15 == 2 && !(_DWORD)v50 && v51
    || v15 == 3 && !(_DWORD)v44 && v45 )
  {
    Pointer = -1073741629;
  }
  else
  {
    if ( (v15 != 2 || !v51) && (v15 != 1 || !hMem) )
      goto LABEL_24;
    v24 = 24LL * v16;
    if ( v24 <= 0xFFFFFFFF )
    {
      v25 = 28 * v16;
      if ( 28 * (unsigned __int64)v16 <= 0xFFFFFFFF )
      {
        v26 = v25 + v24;
        if ( v25 + (int)v24 >= (unsigned int)v24 )
        {
          v27 = v26;
          v28 = LocalAlloc(0x40u, v26);
          v45 = v28;
          if ( !v28 )
          {
            Pointer = -1073741801;
LABEL_76:
            v22 = a6;
            goto LABEL_25;
          }
          memset_0(v28, 0, v27);
          v52 = (char *)v45 + v24;
          for ( i = 0; i < v16; ++i )
          {
            if ( v15 == 1 )
            {
              v30 = 0;
              v31 = (int *)((char *)hMem + 12 * i);
            }
            else
            {
              v31 = (int *)((char *)v51 + 16 * i);
              v30 = v31[3];
            }
            v32 = *v31;
            v47 = v31[1];
            v33 = (unsigned int)v31[2];
            v34 = 3LL * i;
            *((_DWORD *)v45 + 2 * v34) = v32;
            *((_DWORD *)v45 + 2 * v34 + 4) = v33;
            *((_DWORD *)v45 + 2 * v34 + 5) = v30;
            if ( (unsigned int)(v32 - 6) <= 2 )
            {
              *((_QWORD *)v45 + 3 * i + 1) = 0;
            }
            else
            {
              if ( (_DWORD)v33 == -1
                || (v35 = *(void **)(*((_QWORD *)*a5 + 1) + 24 * v33 + 16), RtlLengthSid(v35) > 0x18) )
              {
                Pointer = -1073741629;
                goto LABEL_76;
              }
              RtlCopySid(0x1Cu, DestinationSid, v35);
              v36 = v47;
              if ( v47 != -1 )
              {
                v37 = RtlSubAuthorityCountSid(DestinationSid);
                v38 = *v37;
                *v37 = v38 + 1;
                *RtlSubAuthoritySid(DestinationSid, v38) = v36;
              }
              v39 = RtlLengthSid(DestinationSid);
              v40 = (char *)v52;
              RtlCopySid(v39, v52, DestinationSid);
              *((_QWORD *)v45 + 3 * i + 1) = v40;
              v52 = &v40[RtlLengthSid(DestinationSid)];
              v16 = v43;
            }
          }
LABEL_24:
          v22 = a6;
          *a6 = v45;
          v45 = 0;
LABEL_25:
          v13 = a5;
          goto LABEL_29;
        }
      }
    }
    Pointer = -1073741675;
  }
LABEL_28:
  v22 = a6;
LABEL_29:
  if ( Pointer == -1073741629 || Pointer == -1073741801 || Pointer == -1073741675 )
  {
    if ( *v13 )
    {
      LocalFree(*v13);
      *a5 = 0;
    }
    *v22 = 0;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v51 )
    LocalFree(v51);
  if ( v45 )
    LocalFree(v45);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800208f0  push    rbx
0x1800208f2  push    rsi
0x1800208f3  push    rdi
0x1800208f4  push    r12
0x1800208f6  push    r13
0x1800208f8  push    r14
0x1800208fa  push    r15
0x1800208fc  sub     rsp, 130h
0x180020903  mov     rax, cs:__security_cookie
0x18002090a  xor     rax, rsp
0x18002090d  mov     [rsp+168h+var_40], rax
0x180020915  mov     r11, r9
0x180020918  mov     [rsp+168h+var_80], r9
0x180020920  mov     r12d, r8d
0x180020923  mov     [rsp+168h+var_90], edx
0x18002092a  mov     r10, rcx
0x18002092d  mov     [rsp+168h+var_88], rcx
0x180020935  mov     [rsp+168h+var_70], rcx
0x18002093d  mov     [rsp+168h+var_C8], edx
0x180020944  mov     [rsp+168h+var_D0], r8d
0x18002094c  mov     [rsp+168h+var_68], r9
0x180020954  mov     r8, [rsp+168h+arg_20]
0x18002095c  mov     [rsp+168h+var_F8], r8
0x180020961  mov     rax, [rsp+168h+arg_28]
0x180020969  mov     [rsp+168h+var_100], rax
0x18002096e  mov     r9, [rsp+168h+arg_40]
0x180020976  mov     [rsp+168h+var_98], r9
0x18002097e  mov     r14, [rsp+168h+arg_48]
0x180020986  mov     [rsp+168h+var_A0], r14
0x18002098e  xor     edi, edi
0x180020990  mov     [rsp+168h+var_E0], rdi
0x180020998  mov     [rsp+168h+var_D8], rdi
0x1800209a0  mov     [rsp+168h+var_B0], rdi
0x1800209a8  mov     [rsp+168h+var_A8], rdi
0x1800209b0  mov     [rsp+168h+var_C0], rdi
0x1800209b8  mov     [rsp+168h+hMem], rdi
0x1800209c0  mov     [r8], rdi
0x1800209c3  mov     [rax], rdi
0x1800209c6  test    rcx, rcx
0x1800209c9  jz      loc_180020CFA
0x1800209cf  cmp     r12d, 3E8h
0x1800209d6  ja      loc_180020D04
0x1800209dc  lea     esi, [rdi+3]
0x1800209df  mov     [rsp+168h+var_EC], esi
0x1800209e3  mov     r13d, edi
0x1800209e6  mov     [rsp+168h+var_108], edi
0x1800209ea  mov     [rsp+168h+var_E8], edi
0x1800209f1  test    r14, r14
0x1800209f4  jnz     loc_180020D0E
0x1800209fa  mov     eax, dword ptr [rsp+168h+arg_38]
0x180020a01  and     al, 5
0x180020a03  neg     al
0x180020a05  sbb     ecx, ecx
0x180020a07  add     ecx, esi
0x180020a09  test    [rsp+168h+arg_38], 2
0x180020a11  mov     r15d, 1
0x180020a17  cmovnz  ecx, r15d
0x180020a1b  sub     ecx, r15d
0x180020a1e  jz      loc_180020E11
0x180020a24  sub     ecx, r15d
0x180020a27  jz      loc_180020D24
0x180020a2d  cmp     ecx, r15d
0x180020a30  jnz     loc_180020D1A
0x180020a36  mov     [rsp+168h+var_78], rdi
0x180020a3e  mov     [rsp+168h+var_110], 2
0x180020a46  mov     [rsp+168h+var_118], edx
0x180020a4a  mov     [rsp+168h+var_120], r9
0x180020a4f  mov     eax, [rsp+168h+arg_30]
0x180020a56  mov     dword ptr [rsp+168h+var_128], eax
0x180020a5a  lea     rax, [rsp+168h+var_E0]
0x180020a62  mov     [rsp+168h+var_130], rax
0x180020a67  mov     [rsp+168h+var_138], r8
0x180020a6c  mov     [rsp+168h+var_140], r11
0x180020a71  mov     dword ptr [rsp+168h+var_148], r12d
0x180020a76  mov     r9, [r10+8]
0x180020a7a  xor     r8d, r8d; pReturnValue
0x180020a7d  lea     edx, [r15+43h]; nProcNum
0x180020a81  lea     rcx, stru_180067210; pProxyInfo
0x180020a88  call    cs:__imp_NdrClientCall3
0x180020a8e  mov     rbx, rax
0x180020a91  mov     [rsp+168h+var_78], rax
0x180020a99  mov     [rsp+168h+var_F0], eax
0x180020a9d  mov     edx, [rsp+168h+var_90]
0x180020aa4  mov     r10, [rsp+168h+var_88]
0x180020aac  mov     r8, [rsp+168h+var_F8]
0x180020ab1  mov     r11, [rsp+168h+var_80]
0x180020ab9  mov     r9, [rsp+168h+var_98]
0x180020ac1  jmp     short loc_180020B34
0x180020ac3  mov     ecx, eax; Status
0x180020ac5  call    cs:__imp_I_RpcMapWin32Status
0x180020acb  mov     ebx, 0C0000001h
0x180020ad0  test    eax, eax
0x180020ad2  cmovs   ebx, eax
0x180020ad5  mov     [rsp+168h+var_F0], ebx
0x180020ad9  xor     edi, edi
0x180020adb  lea     r15d, [rdi+1]
0x180020adf  mov     esi, [rsp+168h+var_EC]
0x180020ae3  mov     r13d, [rsp+168h+var_E8]
0x180020aeb  mov     [rsp+168h+var_108], r13d
0x180020af0  mov     r10, [rsp+168h+var_70]
0x180020af8  mov     [rsp+168h+var_88], r10
0x180020b00  mov     edx, [rsp+168h+var_C8]
0x180020b07  mov     r12d, [rsp+168h+var_D0]
0x180020b0f  mov     r11, [rsp+168h+var_68]
0x180020b17  mov     [rsp+168h+var_80], r11
0x180020b1f  mov     r8, [rsp+168h+var_F8]
0x180020b24  mov     r9, [rsp+168h+var_98]
0x180020b2c  mov     r14, [rsp+168h+var_A0]
0x180020b34  cmp     ebx, 0C0020012h
0x180020b3a  jz      loc_180020D24
0x180020b40  cmp     ebx, 0C002002Eh
0x180020b46  jz      loc_180020D24
0x180020b4c  test    ebx, ebx
0x180020b4e  js      short loc_180020B7B
0x180020b50  test    r12d, r12d
0x180020b53  jz      short loc_180020B7B
0x180020b55  cmp     esi, r15d
0x180020b58  jz      short loc_180020BC7
0x180020b5a  cmp     esi, 2
0x180020b5d  jz      loc_180020EF5
0x180020b63  cmp     esi, 3
0x180020b66  jnz     short loc_180020B7B
0x180020b68  cmp     dword ptr [rsp+168h+var_E0], edi
0x180020b6f  jz      short loc_180020BD4
0x180020b71  cmp     [rsp+168h+var_D8], rdi
0x180020b79  jz      short loc_180020BD4
0x180020b7b  cmp     esi, r15d
0x180020b7e  jz      loc_180020C7A
0x180020b84  cmp     esi, 2
0x180020b87  jz      loc_180020F15
0x180020b8d  cmp     esi, 3
0x180020b90  jz      loc_180020C5A
0x180020b96  cmp     esi, 2
0x180020b99  jz      loc_180020F35
0x180020b9f  cmp     esi, r15d
0x180020ba2  jz      loc_180020F48
0x180020ba8  mov     rax, [rsp+168h+var_D8]
0x180020bb0  mov     rsi, [rsp+168h+var_100]
0x180020bb5  mov     [rsi], rax
0x180020bb8  mov     [rsp+168h+var_D8], rdi
0x180020bc0  mov     r8, [rsp+168h+var_F8]
0x180020bc5  jmp     short loc_180020BDE
0x180020bc7  cmp     dword ptr [rsp+168h+var_C0], edi
0x180020bce  jnz     loc_180020EE2
0x180020bd4  mov     ebx, 0C00000C3h
0x180020bd9  mov     rsi, [rsp+168h+var_100]
0x180020bde  cmp     ebx, 0C00000C3h
0x180020be4  jz      loc_180021100
0x180020bea  cmp     ebx, 0C0000017h
0x180020bf0  jz      loc_180021100
0x180020bf6  cmp     ebx, 0C0000095h
0x180020bfc  jz      loc_180021100
0x180020c02  mov     rcx, [rsp+168h+hMem]; hMem
0x180020c0a  test    rcx, rcx
0x180020c0d  jnz     loc_18002111E
0x180020c13  mov     rcx, [rsp+168h+var_A8]; hMem
0x180020c1b  test    rcx, rcx
0x180020c1e  jnz     loc_180021129
0x180020c24  mov     rcx, [rsp+168h+var_D8]; hMem
0x180020c2c  test    rcx, rcx
0x180020c2f  jnz     loc_180021134
0x180020c35  mov     eax, ebx
0x180020c37  mov     rcx, [rsp+168h+var_40]
0x180020c3f  xor     rcx, rsp; StackCookie
0x180020c42  call    __security_check_cookie
0x180020c47  add     rsp, 130h
0x180020c4e  pop     r15
0x180020c50  pop     r14
0x180020c52  pop     r13
0x180020c54  pop     r12
0x180020c56  pop     rdi
0x180020c57  pop     rsi
0x180020c58  pop     rbx
0x180020c59  retn
0x180020c5a  cmp     dword ptr [rsp+168h+var_E0], edi
0x180020c61  jnz     loc_180020B96
0x180020c67  cmp     [rsp+168h+var_D8], rdi
0x180020c6f  jnz     loc_180020BD4
0x180020c75  jmp     loc_180020B96
0x180020c7a  cmp     dword ptr [rsp+168h+var_C0], edi
0x180020c81  jnz     loc_180020B84
0x180020c87  cmp     [rsp+168h+hMem], rdi
0x180020c8f  jnz     loc_180020BD4
0x180020c95  jmp     loc_180020B84
0x180020c9a  mov     ecx, r13d
0x180020c9d  lea     rax, [rcx+rcx*2]
0x180020ca1  lea     r14, ds:0[rax*8]
0x180020ca9  mov     edx, 0FFFFFFFFh
0x180020cae  cmp     r14, rdx
0x180020cb1  jbe     short loc_180020CBD
0x180020cb3  mov     ebx, 0C0000095h
0x180020cb8  jmp     loc_180020BD9
0x180020cbd  imul    rax, rcx, 1Ch
0x180020cc1  cmp     rax, rdx
0x180020cc4  ja      short loc_180020CB3
0x180020cc6  lea     ecx, [rax+r14]
0x180020cca  cmp     ecx, r14d
0x180020ccd  jb      short loc_180020CB3
0x180020ccf  mov     r12d, ecx
0x180020cd2  mov     edx, ecx; uBytes
0x180020cd4  mov     ecx, 40h ; '@'; uFlags
0x180020cd9  call    cs:__imp_LocalAlloc
0x180020cdf  mov     [rsp+168h+var_D8], rax
0x180020ce7  test    rax, rax
0x180020cea  jnz     loc_180020F6A
0x180020cf0  mov     ebx, 0C0000017h
0x180020cf5  jmp     loc_180020F60
0x180020cfa  mov     eax, 0C0000008h
0x180020cff  jmp     loc_180020C37
0x180020d04  mov     eax, 0C00000CDh
0x180020d09  jmp     loc_180020C37
0x180020d0e  mov     dword ptr [r14], 2
0x180020d15  jmp     loc_1800209FA
0x180020d1a  mov     ebx, 0C000000Dh
0x180020d1f  jmp     loc_180020BD9
0x180020d24  mov     dword ptr [rsp+168h+var_130], edx
0x180020d28  mov     [rsp+168h+var_138], r9
0x180020d2d  mov     eax, [rsp+168h+arg_30]
0x180020d34  mov     dword ptr [rsp+168h+var_140], eax
0x180020d38  lea     rax, [rsp+168h+var_B0]
0x180020d40  mov     [rsp+168h+var_148], rax
0x180020d45  mov     r9, r8
0x180020d48  mov     r8, r11
0x180020d4b  mov     edx, r12d
0x180020d4e  mov     rcx, [r10+8]
0x180020d52  call    LsarLookupNames2
0x180020d57  mov     ebx, eax
0x180020d59  mov     [rsp+168h+var_F0], eax
0x180020d5d  mov     esi, 2
0x180020d62  mov     [rsp+168h+var_EC], esi
0x180020d66  cmp     [rsp+168h+var_A8], rdi
0x180020d6e  cmovnz  r13d, dword ptr [rsp+168h+var_B0]
0x180020d77  mov     [rsp+168h+var_108], r13d
0x180020d7c  mov     [rsp+168h+var_E8], r13d
0x180020d84  mov     r10, [rsp+168h+var_88]
0x180020d8c  mov     r8, [rsp+168h+var_F8]
0x180020d91  mov     r11, [rsp+168h+var_80]
0x180020d99  mov     r9, [rsp+168h+var_98]
0x180020da1  jmp     short loc_180020DFD
0x180020da3  mov     ecx, eax; Status
0x180020da5  call    cs:__imp_I_RpcMapWin32Status
0x180020dab  mov     ebx, 0C0000001h
0x180020db0  test    eax, eax
0x180020db2  cmovs   ebx, eax
0x180020db5  mov     [rsp+168h+var_F0], ebx
0x180020db9  xor     edi, edi
0x180020dbb  lea     r15d, [rdi+1]
0x180020dbf  mov     esi, [rsp+168h+var_EC]
0x180020dc3  mov     r13d, [rsp+168h+var_E8]
0x180020dcb  mov     [rsp+168h+var_108], r13d
0x180020dd0  mov     r10, [rsp+168h+var_70]
0x180020dd8  mov     r12d, [rsp+168h+var_D0]
0x180020de0  mov     r11, [rsp+168h+var_68]
0x180020de8  mov     r8, [rsp+168h+var_F8]
0x180020ded  mov     r9, [rsp+168h+var_98]
0x180020df5  mov     r14, [rsp+168h+var_A0]
0x180020dfd  cmp     ebx, 0C0020012h
0x180020e03  jz      short loc_180020E11
0x180020e05  cmp     ebx, 0C002002Eh
0x180020e0b  jnz     loc_180020B4C
0x180020e11  test    r14, r14
0x180020e14  jz      short loc_180020E19
0x180020e16  mov     [r14], r15d
0x180020e19  mov     [rsp+168h+var_78], rdi
0x180020e21  mov     [rsp+168h+var_120], r9
0x180020e26  mov     eax, [rsp+168h+arg_30]
0x180020e2d  mov     dword ptr [rsp+168h+var_128], eax
0x180020e31  lea     rax, [rsp+168h+var_C0]
0x180020e39  mov     [rsp+168h+var_130], rax
0x180020e3e  mov     [rsp+168h+var_138], r8
0x180020e43  mov     [rsp+168h+var_140], r11
0x180020e48  mov     dword ptr [rsp+168h+var_148], r12d
0x180020e4d  mov     r9, [r10+8]
0x180020e51  xor     r8d, r8d; pReturnValue
0x180020e54  lea     edx, [r8+0Eh]; nProcNum
0x180020e58  lea     rcx, stru_180067210; pProxyInfo
0x180020e5f  call    cs:__imp_NdrClientCall3
0x180020e65  mov     [rsp+168h+var_78], rax
0x180020e6d  mov     ebx, eax
0x180020e6f  mov     [rsp+168h+var_F0], eax
0x180020e73  mov     esi, r15d
0x180020e76  mov     [rsp+168h+var_EC], r15d
0x180020e7b  cmp     [rsp+168h+hMem], rdi
0x180020e83  cmovnz  r13d, dword ptr [rsp+168h+var_C0]
0x180020e8c  mov     [rsp+168h+var_108], r13d
0x180020e91  mov     [rsp+168h+var_E8], r13d
0x180020e99  mov     r8, [rsp+168h+var_F8]
0x180020e9e  jmp     loc_180020B4C
0x180020ea3  mov     ecx, eax; Status
0x180020ea5  call    cs:__imp_I_RpcMapWin32Status
0x180020eab  mov     ebx, 0C0000001h
0x180020eb0  test    eax, eax
0x180020eb2  cmovs   ebx, eax
0x180020eb5  mov     [rsp+168h+var_F0], ebx
0x180020eb9  xor     edi, edi
0x180020ebb  lea     r15d, [rdi+1]
0x180020ebf  mov     esi, [rsp+168h+var_EC]
0x180020ec3  mov     r13d, [rsp+168h+var_E8]
0x180020ecb  mov     [rsp+168h+var_108], r13d
0x180020ed0  mov     r12d, [rsp+168h+var_D0]
  ... truncated ...
```
