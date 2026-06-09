# LsaICLookupNames_0

- ea: `0x18001f9d4`
- end: `0x18002025c`
- name: `LsaICLookupNames_0`
- size: `2184`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001f6bc`
- `0x1800352ec`
- `0x18003b350`
- `0x1800432a0`

## callees

- `0x18001f9d4`
- `0x180030f9c`
- `0x180070300`
- `0x180070360`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180020157`
- `ntdll!RtlSubAuthorityCountSid` at `0x180020157`
- `ntdll!RtlLengthSid` at `0x18002010f`
- `ntdll!RtlLengthSid` at `0x180020191`
- `ntdll!RtlLengthSid` at `0x1800201d8`
- `ntdll!RtlLengthSid` at `0x18002010f`
- `ntdll!RtlLengthSid` at `0x180020191`
- `ntdll!RtlLengthSid` at `0x1800201d8`
- `ntdll!RtlCopySid` at `0x180020139`
- `ntdll!RtlCopySid` at `0x1800201af`
- `ntdll!RtlCopySid` at `0x180020139`
- `ntdll!RtlCopySid` at `0x1800201af`
- `ntdll!RtlSubAuthoritySid` at `0x180020174`
- `ntdll!RtlSubAuthoritySid` at `0x180020174`
- `KERNELBASE!LocalAlloc` at `0x18002000b`
- `KERNELBASE!LocalAlloc` at `0x18002000b`
- `KERNEL32!LocalFree` at `0x18002020d`
- `KERNEL32!LocalFree` at `0x180020229`
- `KERNEL32!LocalFree` at `0x18002023a`
- `KERNEL32!LocalFree` at `0x18002024b`
- `KERNEL32!LocalFree` at `0x18002020d`
- `KERNEL32!LocalFree` at `0x180020229`
- `KERNEL32!LocalFree` at `0x18002023a`
- `KERNEL32!LocalFree` at `0x18002024b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001fbaf`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001fe20`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001fef1`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001fbaf`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001fe20`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001fef1`
- `RPCRT4!I_RpcExceptionFilter` at `0x180072438`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007245a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007247c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180072438`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007245a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007247c`
- `RPCRT4!NdrClientCall3` at `0x18001fb6c`
- `RPCRT4!NdrClientCall3` at `0x18001fb6c`

## pseudocode

```c
__int64 __fastcall LsaICLookupNames_0(
        __int64 a1,
        signed int a2,
        unsigned int a3,
        __int64 a4,
        HLOCAL *a5,
        HLOCAL *a6,
        int a7,
        char a8,
        void *a9,
        _DWORD *a10)
{
  __int64 v10; // r11
  __int64 v12; // r10
  HLOCAL *v13; // r9
  PSID v14; // r8
  int v15; // esi
  unsigned int v16; // r13d
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  CLIENT_CALL_RETURN v20; // rax
  signed int Pointer; // ebx
  HLOCAL *v22; // rsi
  __int64 v24; // r9
  unsigned int v25; // ecx
  unsigned int v26; // eax
  size_t v27; // r15
  HLOCAL v28; // rax
  unsigned int i; // r15d
  int v30; // r10d
  int *v31; // r8
  int v32; // ecx
  __int64 v33; // r9
  __int64 v34; // r12
  PUCHAR v35; // rax
  ULONG v36; // edx
  PULONG v37; // rax
  ULONG v38; // eax
  ULONG v39; // eax
  unsigned int v40; // [rsp+68h] [rbp-100h] BYREF
  HLOCAL *v41; // [rsp+70h] [rbp-F8h]
  signed int v42; // [rsp+78h] [rbp-F0h]
  int v43; // [rsp+7Ch] [rbp-ECh]
  unsigned int v44; // [rsp+80h] [rbp-E8h]
  unsigned int v45; // [rsp+84h] [rbp-E4h] BYREF
  PSID v46; // [rsp+88h] [rbp-E0h]
  __int64 v47; // [rsp+90h] [rbp-D8h] BYREF
  HLOCAL v48; // [rsp+98h] [rbp-D0h]
  signed int v49; // [rsp+A0h] [rbp-C8h]
  __int64 v50; // [rsp+A8h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-B8h]
  __int64 v52; // [rsp+B8h] [rbp-B0h] BYREF
  HLOCAL v53; // [rsp+C0h] [rbp-A8h]
  signed int v54; // [rsp+C8h] [rbp-A0h]
  __int64 v55; // [rsp+D0h] [rbp-98h]
  __int64 v56; // [rsp+D8h] [rbp-90h]
  PSID SourceSid; // [rsp+E0h] [rbp-88h]
  __int64 v58; // [rsp+E8h] [rbp-80h]
  __int64 v59; // [rsp+F0h] [rbp-78h]
  _DWORD *v60; // [rsp+F8h] [rbp-70h]
  _BYTE DestinationSid[32]; // [rsp+100h] [rbp-68h] BYREF

  v10 = a4;
  v56 = a4;
  v54 = a2;
  v12 = a1;
  v55 = a1;
  v58 = a1;
  v49 = a2;
  v40 = a3;
  v59 = a4;
  v13 = a5;
  v41 = a6;
  v14 = a9;
  v46 = a9;
  v60 = a10;
  v47 = 0;
  v48 = 0;
  v52 = 0;
  v53 = 0;
  v50 = 0;
  hMem = 0;
  v45 = 0;
  *a5 = 0;
  *a6 = 0;
  if ( !a1 )
    return 3221225480LL;
  if ( a3 > 0x3E8 )
    return 3221225677LL;
  v15 = 3;
  v43 = 3;
  v16 = 0;
  v44 = 0;
  if ( a10 )
    *a10 = 2;
  v17 = 3 - ((a8 & 5) != 0);
  if ( (a8 & 2) != 0 )
    v17 = 1;
  v18 = v17 - 1;
  if ( !v18 )
    goto LABEL_52;
  v19 = v18 - 1;
  if ( !v19 )
    goto LABEL_51;
  if ( v19 != 1 )
  {
    Pointer = -1073741811;
    goto LABEL_28;
  }
  SourceSid = 0;
  v20.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&stru_1800751F0,
                  0x44u,
                  0,
                  *(_QWORD *)(v12 + 8),
                  a3,
                  v10,
                  a5,
                  &v47,
                  a7,
                  a9,
                  a2,
                  2).Pointer;
  Pointer = (signed int)v20.Pointer;
  SourceSid = (PSID)v20.Simple;
  v42 = (signed int)v20.Pointer;
  v12 = v55;
  a2 = v54;
  LODWORD(v10) = v56;
  v14 = v46;
  v13 = a5;
  if ( LODWORD(v20.Pointer) == -1073610734 || LODWORD(v20.Pointer) == -1073610706 )
  {
LABEL_51:
    Pointer = LsarLookupNames2(*(_QWORD *)(v12 + 8), a3, v10, (_DWORD)v13, (__int64)&v52, a7, (__int64)v14, a2);
    v42 = Pointer;
    v15 = 2;
    v43 = 2;
    if ( v53 )
      v16 = v52;
    v44 = v16;
    v12 = v55;
    LODWORD(v10) = v56;
    v14 = v46;
    v13 = a5;
    if ( Pointer == -1073610734 || Pointer == -1073610706 )
    {
LABEL_52:
      if ( a10 )
        *a10 = 1;
      Pointer = LsarLookupNames(*(_QWORD *)(v12 + 8), a3, v10, (_DWORD)v13, (__int64)&v50, a7, (__int64)v14);
      v42 = Pointer;
      v15 = 1;
      v43 = 1;
      if ( hMem )
        v16 = v50;
      v44 = v16;
      v13 = a5;
    }
  }
  if ( (Pointer < 0
     || !a3
     || (v15 != 1 || (_DWORD)v50 && hMem) && (v15 != 2 || (_DWORD)v52 && v53) && (v15 != 3 || (_DWORD)v47 && v48))
    && (v15 != 1 || (_DWORD)v50 || !hMem)
    && (v15 != 2 || (_DWORD)v52 || !v53)
    && (v15 != 3 || (_DWORD)v47 || !v48) )
  {
    if ( v15 == 2 && v53 || v15 == 1 && hMem )
    {
      v40 = 0;
      v49 = Pointer;
      Pointer = RtlULongLongToULong(24LL * v16, &v45);
      if ( Pointer < 0 )
        goto LABEL_76;
      Pointer = RtlULongLongToULong(28 * v24, &v40);
      if ( Pointer < 0 )
        goto LABEL_76;
      v25 = v45 + v40;
      v26 = -1;
      if ( v45 + v40 >= v45 )
        v26 = v45 + v40;
      Pointer = v25 < v45 ? 0xC0000095 : 0;
      if ( v25 < v45 )
        goto LABEL_76;
      v27 = v26;
      v28 = LocalAlloc(0x40u, v26);
      v48 = v28;
      if ( !v28 )
      {
        Pointer = -1073741801;
LABEL_76:
        v22 = v41;
        goto LABEL_25;
      }
      Pointer = v49;
      memset_0(v28, 0, v27);
      v46 = (char *)v48 + 24 * v16;
      for ( i = 0; i < v16; ++i )
      {
        if ( v15 == 1 )
        {
          v30 = 0;
          v31 = (int *)((char *)hMem + 12 * i);
        }
        else
        {
          v31 = (int *)((char *)v53 + 16 * i);
          v30 = v31[3];
        }
        v32 = *v31;
        v45 = v31[1];
        v33 = (unsigned int)v31[2];
        v34 = 3LL * i;
        *((_DWORD *)v48 + 2 * v34) = v32;
        *((_DWORD *)v48 + 2 * v34 + 4) = v33;
        *((_DWORD *)v48 + 2 * v34 + 5) = v30;
        if ( (unsigned int)(v32 - 6) <= 2 )
        {
          *((_QWORD *)v48 + 3 * i + 1) = 0;
        }
        else
        {
          if ( (_DWORD)v33 == -1
            || (SourceSid = *(PSID *)(*((_QWORD *)*a5 + 1) + 24 * v33 + 16), RtlLengthSid(SourceSid) > 0x18) )
          {
            Pointer = -1073741629;
            goto LABEL_76;
          }
          RtlCopySid(0x1Cu, DestinationSid, SourceSid);
          if ( v45 != -1 )
          {
            v35 = RtlSubAuthorityCountSid(DestinationSid);
            v36 = *v35;
            *v35 = v36 + 1;
            v37 = RtlSubAuthoritySid(DestinationSid, v36);
            *v37 = v45;
          }
          v38 = RtlLengthSid(DestinationSid);
          RtlCopySid(v38, v46, DestinationSid);
          *((_QWORD *)v48 + 3 * i + 1) = v46;
          v39 = RtlLengthSid(DestinationSid);
          v46 = (char *)v46 + v39;
        }
      }
    }
    v22 = v41;
    *v41 = v48;
    v48 = 0;
LABEL_25:
    v13 = a5;
    goto LABEL_29;
  }
  Pointer = -1073741629;
LABEL_28:
  v22 = v41;
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
  if ( v53 )
    LocalFree(v53);
  if ( v48 )
    LocalFree(v48);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18001f9d4  push    rbx
0x18001f9d6  push    rsi
0x18001f9d7  push    rdi
0x18001f9d8  push    r12
0x18001f9da  push    r13
0x18001f9dc  push    r14
0x18001f9de  push    r15
0x18001f9e0  sub     rsp, 130h
0x18001f9e7  mov     rax, cs:__security_cookie
0x18001f9ee  xor     rax, rsp
0x18001f9f1  mov     [rsp+168h+var_48], rax
0x18001f9f9  mov     r11, r9
0x18001f9fc  mov     [rsp+168h+var_90], r9
0x18001fa04  mov     r12d, r8d
0x18001fa07  mov     [rsp+168h+var_A0], edx
0x18001fa0e  mov     r10, rcx
0x18001fa11  mov     [rsp+168h+var_98], rcx
0x18001fa19  mov     [rsp+168h+var_80], rcx
0x18001fa21  mov     [rsp+168h+var_C8], edx
0x18001fa28  mov     [rsp+168h+var_100], r8d
0x18001fa2d  mov     [rsp+168h+var_78], r9
0x18001fa35  mov     r9, [rsp+168h+arg_20]
0x18001fa3d  mov     [rsp+168h+var_108], r9
0x18001fa42  mov     rax, [rsp+168h+arg_28]
0x18001fa4a  mov     [rsp+168h+var_F8], rax
0x18001fa4f  mov     r8, [rsp+168h+arg_40]
0x18001fa57  mov     [rsp+168h+var_E0], r8
0x18001fa5f  mov     r15, [rsp+168h+arg_48]
0x18001fa67  mov     [rsp+168h+var_70], r15
0x18001fa6f  xor     edi, edi
0x18001fa71  mov     [rsp+168h+var_D8], rdi
0x18001fa79  mov     [rsp+168h+var_D0], rdi
0x18001fa81  mov     [rsp+168h+var_B0], rdi
0x18001fa89  mov     [rsp+168h+var_A8], rdi
0x18001fa91  mov     [rsp+168h+var_C0], rdi
0x18001fa99  mov     [rsp+168h+hMem], rdi
0x18001faa1  mov     [rsp+168h+var_E4], edi
0x18001faa8  mov     [r9], rdi
0x18001faab  mov     [rax], rdi
0x18001faae  test    rcx, rcx
0x18001fab1  jz      loc_18001FD83
0x18001fab7  cmp     r12d, 3E8h
0x18001fabe  ja      loc_18001FD8A
0x18001fac4  lea     esi, [rdi+3]
0x18001fac7  mov     [rsp+168h+var_EC], esi
0x18001facb  mov     r13d, edi
0x18001face  mov     [rsp+168h+var_E8], edi
0x18001fad5  test    r15, r15
0x18001fad8  jnz     loc_18001FD91
0x18001fade  mov     eax, dword ptr [rsp+168h+arg_38]
0x18001fae5  and     al, 5
0x18001fae7  neg     al
0x18001fae9  sbb     ecx, ecx
0x18001faeb  add     ecx, esi
0x18001faed  test    [rsp+168h+arg_38], 2
0x18001faf5  mov     r14d, 1
0x18001fafb  cmovnz  ecx, r14d
0x18001faff  sub     ecx, r14d
0x18001fb02  jz      loc_18001FE8A
0x18001fb08  sub     ecx, r14d
0x18001fb0b  jz      loc_18001FDA7
0x18001fb11  cmp     ecx, r14d
0x18001fb14  jnz     loc_18001FD9D
0x18001fb1a  mov     [rsp+168h+SourceSid], rdi
0x18001fb22  mov     [rsp+168h+var_110], 2
0x18001fb2a  mov     [rsp+168h+var_118], edx
0x18001fb2e  mov     [rsp+168h+var_120], r8
0x18001fb33  mov     eax, [rsp+168h+arg_30]
0x18001fb3a  mov     [rsp+168h+var_128], eax
0x18001fb3e  lea     rax, [rsp+168h+var_D8]
0x18001fb46  mov     [rsp+168h+var_130], rax
0x18001fb4b  mov     [rsp+168h+var_138], r9
0x18001fb50  mov     [rsp+168h+var_140], r11
0x18001fb55  mov     dword ptr [rsp+168h+var_148], r12d
0x18001fb5a  mov     r9, [r10+8]
0x18001fb5e  xor     r8d, r8d; pReturnValue
0x18001fb61  lea     edx, [r14+43h]; nProcNum
0x18001fb65  lea     rcx, stru_1800751F0; pProxyInfo
0x18001fb6c  call    cs:__imp_NdrClientCall3
0x18001fb73  nop     dword ptr [rax+rax+00h]
0x18001fb78  mov     rbx, rax
0x18001fb7b  mov     [rsp+168h+SourceSid], rax
0x18001fb83  mov     [rsp+168h+var_F0], eax
0x18001fb87  mov     r10, [rsp+168h+var_98]
0x18001fb8f  mov     edx, [rsp+168h+var_A0]
0x18001fb96  mov     r11, [rsp+168h+var_90]
0x18001fb9e  mov     r8, [rsp+168h+var_E0]
0x18001fba6  mov     r9, [rsp+168h+var_108]
0x18001fbab  jmp     short loc_18001FC1C
0x18001fbad  mov     ecx, eax; Status
0x18001fbaf  call    cs:__imp_I_RpcMapWin32Status
0x18001fbb6  nop     dword ptr [rax+rax+00h]
0x18001fbbb  mov     ebx, 0C0000001h
0x18001fbc0  test    eax, eax
0x18001fbc2  cmovs   ebx, eax
0x18001fbc5  mov     [rsp+168h+var_F0], ebx
0x18001fbc9  xor     edi, edi
0x18001fbcb  lea     r14d, [rdi+1]
0x18001fbcf  mov     esi, [rsp+168h+var_EC]
0x18001fbd3  mov     r13d, [rsp+168h+var_E8]
0x18001fbdb  mov     r10, [rsp+168h+var_80]
0x18001fbe3  mov     [rsp+168h+var_98], r10
0x18001fbeb  mov     edx, [rsp+168h+var_C8]
0x18001fbf2  mov     r12d, [rsp+168h+var_100]
0x18001fbf7  mov     r11, [rsp+168h+var_78]
0x18001fbff  mov     [rsp+168h+var_90], r11
0x18001fc07  mov     r9, [rsp+168h+var_108]
0x18001fc0c  mov     r8, [rsp+168h+var_E0]
0x18001fc14  mov     r15, [rsp+168h+var_70]
0x18001fc1c  cmp     ebx, 0C0020012h
0x18001fc22  jz      loc_18001FDA7
0x18001fc28  cmp     ebx, 0C002002Eh
0x18001fc2e  jz      loc_18001FDA7
0x18001fc34  test    ebx, ebx
0x18001fc36  js      short loc_18001FC63
0x18001fc38  test    r12d, r12d
0x18001fc3b  jz      short loc_18001FC63
0x18001fc3d  cmp     esi, r14d
0x18001fc40  jz      short loc_18001FCAF
0x18001fc42  cmp     esi, 2
0x18001fc45  jz      loc_18001FF3F
0x18001fc4b  cmp     esi, 3
0x18001fc4e  jnz     short loc_18001FC63
0x18001fc50  cmp     dword ptr [rsp+168h+var_D8], edi
0x18001fc57  jz      short loc_18001FCBC
0x18001fc59  cmp     [rsp+168h+var_D0], rdi
0x18001fc61  jz      short loc_18001FCBC
0x18001fc63  cmp     esi, r14d
0x18001fc66  jz      loc_18001FD63
0x18001fc6c  cmp     esi, 2
0x18001fc6f  jz      loc_18001FF5F
0x18001fc75  cmp     esi, 3
0x18001fc78  jz      loc_18001FD43
0x18001fc7e  cmp     esi, 2
0x18001fc81  jz      loc_18001FF7F
0x18001fc87  cmp     esi, r14d
0x18001fc8a  jz      loc_18001FF8E
0x18001fc90  mov     rax, [rsp+168h+var_D0]
0x18001fc98  mov     rsi, [rsp+168h+var_F8]
0x18001fc9d  mov     [rsi], rax
0x18001fca0  mov     [rsp+168h+var_D0], rdi
0x18001fca8  mov     r9, [rsp+168h+var_108]
0x18001fcad  jmp     short loc_18001FCC6
0x18001fcaf  cmp     dword ptr [rsp+168h+var_C0], edi
0x18001fcb6  jnz     loc_18001FF2C
0x18001fcbc  mov     ebx, 0C00000C3h
0x18001fcc1  mov     rsi, [rsp+168h+var_F8]
0x18001fcc6  cmp     ebx, 0C00000C3h
0x18001fccc  jz      loc_180020205
0x18001fcd2  cmp     ebx, 0C0000017h
0x18001fcd8  jz      loc_180020205
0x18001fcde  cmp     ebx, 0C0000095h
0x18001fce4  jz      loc_180020205
0x18001fcea  mov     rcx, [rsp+168h+hMem]; hMem
0x18001fcf2  test    rcx, rcx
0x18001fcf5  jnz     loc_180020229
0x18001fcfb  mov     rcx, [rsp+168h+var_A8]; hMem
0x18001fd03  test    rcx, rcx
0x18001fd06  jnz     loc_18002023A
0x18001fd0c  mov     rcx, [rsp+168h+var_D0]; hMem
0x18001fd14  test    rcx, rcx
0x18001fd17  jnz     loc_18002024B
0x18001fd1d  mov     eax, ebx
0x18001fd1f  mov     rcx, [rsp+168h+var_48]
0x18001fd27  xor     rcx, rsp; StackCookie
0x18001fd2a  call    __security_check_cookie
0x18001fd2f  add     rsp, 130h
0x18001fd36  pop     r15
0x18001fd38  pop     r14
0x18001fd3a  pop     r13
0x18001fd3c  pop     r12
0x18001fd3e  pop     rdi
0x18001fd3f  pop     rsi
0x18001fd40  pop     rbx
0x18001fd41  retn
0x18001fd43  cmp     dword ptr [rsp+168h+var_D8], edi
0x18001fd4a  jnz     loc_18001FC7E
0x18001fd50  cmp     [rsp+168h+var_D0], rdi
0x18001fd58  jnz     loc_18001FCBC
0x18001fd5e  jmp     loc_18001FC7E
0x18001fd63  cmp     dword ptr [rsp+168h+var_C0], edi
0x18001fd6a  jnz     loc_18001FC6C
0x18001fd70  cmp     [rsp+168h+hMem], rdi
0x18001fd78  jnz     loc_18001FCBC
0x18001fd7e  jmp     loc_18001FC6C
0x18001fd83  mov     eax, 0C0000008h
0x18001fd88  jmp     short loc_18001FD1F
0x18001fd8a  mov     eax, 0C00000CDh
0x18001fd8f  jmp     short loc_18001FD1F
0x18001fd91  mov     dword ptr [r15], 2
0x18001fd98  jmp     loc_18001FADE
0x18001fd9d  mov     ebx, 0C000000Dh
0x18001fda2  jmp     loc_18001FCC1
0x18001fda7  mov     dword ptr [rsp+168h+var_130], edx
0x18001fdab  mov     [rsp+168h+var_138], r8
0x18001fdb0  mov     eax, [rsp+168h+arg_30]
0x18001fdb7  mov     dword ptr [rsp+168h+var_140], eax
0x18001fdbb  lea     rax, [rsp+168h+var_B0]
0x18001fdc3  mov     [rsp+168h+var_148], rax
0x18001fdc8  mov     r8, r11
0x18001fdcb  mov     edx, r12d
0x18001fdce  mov     rcx, [r10+8]
0x18001fdd2  call    LsarLookupNames2
0x18001fdd7  mov     ebx, eax
0x18001fdd9  mov     [rsp+168h+var_F0], eax
0x18001fddd  mov     esi, 2
0x18001fde2  mov     [rsp+168h+var_EC], esi
0x18001fde6  cmp     [rsp+168h+var_A8], rdi
0x18001fdee  cmovnz  r13d, dword ptr [rsp+168h+var_B0]
0x18001fdf7  mov     [rsp+168h+var_E8], r13d
0x18001fdff  mov     r10, [rsp+168h+var_98]
0x18001fe07  mov     r11, [rsp+168h+var_90]
0x18001fe0f  mov     r8, [rsp+168h+var_E0]
0x18001fe17  mov     r9, [rsp+168h+var_108]
0x18001fe1c  jmp     short loc_18001FE76
0x18001fe1e  mov     ecx, eax; Status
0x18001fe20  call    cs:__imp_I_RpcMapWin32Status
0x18001fe27  nop     dword ptr [rax+rax+00h]
0x18001fe2c  mov     ebx, 0C0000001h
0x18001fe31  test    eax, eax
0x18001fe33  cmovs   ebx, eax
0x18001fe36  mov     [rsp+168h+var_F0], ebx
0x18001fe3a  xor     edi, edi
0x18001fe3c  lea     r14d, [rdi+1]
0x18001fe40  mov     esi, [rsp+168h+var_EC]
0x18001fe44  mov     r13d, [rsp+168h+var_E8]
0x18001fe4c  mov     r10, [rsp+168h+var_80]
0x18001fe54  mov     r12d, [rsp+168h+var_100]
0x18001fe59  mov     r11, [rsp+168h+var_78]
0x18001fe61  mov     r9, [rsp+168h+var_108]
0x18001fe66  mov     r8, [rsp+168h+var_E0]
0x18001fe6e  mov     r15, [rsp+168h+var_70]
0x18001fe76  cmp     ebx, 0C0020012h
0x18001fe7c  jz      short loc_18001FE8A
0x18001fe7e  cmp     ebx, 0C002002Eh
0x18001fe84  jnz     loc_18001FC34
0x18001fe8a  test    r15, r15
0x18001fe8d  jz      short loc_18001FE92
0x18001fe8f  mov     [r15], r14d
0x18001fe92  mov     [rsp+168h+var_138], r8
0x18001fe97  mov     eax, [rsp+168h+arg_30]
0x18001fe9e  mov     dword ptr [rsp+168h+var_140], eax
0x18001fea2  lea     rax, [rsp+168h+var_C0]
0x18001feaa  mov     [rsp+168h+var_148], rax
0x18001feaf  mov     r8, r11
0x18001feb2  mov     edx, r12d
0x18001feb5  mov     rcx, [r10+8]
0x18001feb9  call    LsarLookupNames
0x18001febe  mov     ebx, eax
0x18001fec0  mov     [rsp+168h+var_F0], eax
0x18001fec4  mov     esi, r14d
0x18001fec7  mov     [rsp+168h+var_EC], r14d
0x18001fecc  cmp     [rsp+168h+hMem], rdi
0x18001fed4  cmovnz  r13d, dword ptr [rsp+168h+var_C0]
0x18001fedd  mov     [rsp+168h+var_E8], r13d
0x18001fee5  mov     r9, [rsp+168h+var_108]
0x18001feea  jmp     loc_18001FC34
0x18001feef  mov     ecx, eax; Status
0x18001fef1  call    cs:__imp_I_RpcMapWin32Status
0x18001fef8  nop     dword ptr [rax+rax+00h]
0x18001fefd  mov     ebx, 0C0000001h
0x18001ff02  test    eax, eax
0x18001ff04  cmovs   ebx, eax
0x18001ff07  mov     [rsp+168h+var_F0], ebx
0x18001ff0b  xor     edi, edi
0x18001ff0d  lea     r14d, [rdi+1]
0x18001ff11  mov     esi, [rsp+168h+var_EC]
0x18001ff15  mov     r13d, [rsp+168h+var_E8]
0x18001ff1d  mov     r12d, [rsp+168h+var_100]
0x18001ff22  mov     r9, [rsp+168h+var_108]
0x18001ff27  jmp     loc_18001FC34
0x18001ff2c  cmp     [rsp+168h+hMem], rdi
0x18001ff34  jz      loc_18001FCBC
0x18001ff3a  jmp     loc_18001FC42
0x18001ff3f  cmp     dword ptr [rsp+168h+var_B0], edi
0x18001ff46  jz      loc_18001FCBC
0x18001ff4c  cmp     [rsp+168h+var_A8], rdi
0x18001ff54  jz      loc_18001FCBC
0x18001ff5a  jmp     loc_18001FC4B
0x18001ff5f  cmp     dword ptr [rsp+168h+var_B0], edi
0x18001ff66  jnz     loc_18001FC75
0x18001ff6c  cmp     [rsp+168h+var_A8], rdi
0x18001ff74  jnz     loc_18001FCBC
0x18001ff7a  jmp     loc_18001FC75
0x18001ff7f  cmp     [rsp+168h+var_A8], rdi
0x18001ff87  jnz     short loc_18001FF9C
0x18001ff89  jmp     loc_18001FC87
0x18001ff8e  cmp     [rsp+168h+hMem], rdi
0x18001ff96  jz      loc_18001FC90
0x18001ff9c  mov     [rsp+168h+var_100], edi
0x18001ffa0  mov     [rsp+168h+var_C8], ebx
0x18001ffa7  mov     r9d, r13d
0x18001ffaa  lea     rax, [r9+r9*2]
0x18001ffae  lea     r12, ds:0[rax*8]
0x18001ffb6  lea     rdx, [rsp+168h+var_E4]
0x18001ffbe  mov     rcx, r12
0x18001ffc1  call    RtlULongLongToULong
0x18001ffc6  mov     ebx, eax
0x18001ffc8  test    eax, eax
0x18001ffca  js      short loc_180020030
  ... truncated ...
```
