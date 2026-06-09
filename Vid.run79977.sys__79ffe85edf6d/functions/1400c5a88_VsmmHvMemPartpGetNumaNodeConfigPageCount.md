# VsmmHvMemPartpGetNumaNodeConfigPageCount

- ea: `0x1400c5a88`
- end: `0x1400c5dc4`
- name: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- size: `828`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1400c73ac`
- `0x1400c74d8`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x1400183f0`
- `0x140021c60`
- `0x140021db0`
- `0x140024a90`
- `0x14002f724`
- `0x140092114`
- `0x140092250`
- `0x140092304`
- `0x1400c5a88`
- `0x1400c64a4`
- `0x1400c7610`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400c5adb`
- `ntoskrnl!ExAllocatePool2` at `0x1400c5b2c`
- `ntoskrnl!ExAllocatePool2` at `0x1400c5adb`
- `ntoskrnl!ExAllocatePool2` at `0x1400c5b2c`

## string_xrefs

- `0x1400c5b09`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- `0x1400c5b5a`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- `0x1400c5b8b`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- `0x1400c5ca7`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- `0x1400c5d2b`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`

## pseudocode

```c
__int64 __fastcall VsmmHvMemPartpGetNumaNodeConfigPageCount(__int64 a1)
{
  _BYTE *v1; // r15
  __int64 Pool2; // rax
  int v4; // ebx
  __int64 v5; // rax
  unsigned __int8 v6; // si
  __int64 UINT64WithDefault; // rbx
  __int64 v8; // rbx
  unsigned __int8 v10; // [rsp+30h] [rbp-99h] BYREF
  __int64 v11; // [rsp+38h] [rbp-91h] BYREF
  __int64 v12; // [rsp+40h] [rbp-89h] BYREF
  __int64 v13; // [rsp+48h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+50h] [rbp-79h] BYREF
  char v15[16]; // [rsp+70h] [rbp-59h] BYREF
  char v16[16]; // [rsp+80h] [rbp-49h] BYREF
  __int64 *v17; // [rsp+90h] [rbp-39h]
  __int64 v18; // [rsp+98h] [rbp-31h]
  char *v19; // [rsp+A0h] [rbp-29h]
  __int64 v20; // [rsp+A8h] [rbp-21h]
  __int64 *v21; // [rsp+B0h] [rbp-19h]
  __int64 v22; // [rsp+B8h] [rbp-11h]
  wchar_t pszDest[20]; // [rsp+C0h] [rbp-9h] BYREF

  v1 = VidDeviceExtension;
  v12 = 0;
  Pool2 = ExAllocatePool2(256, 8LL * *((unsigned __int8 *)VidDeviceExtension + 256), 1833788502);
  *(_QWORD *)(a1 + 392) = Pool2;
  if ( !Pool2 )
  {
    v4 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmHvMemPartpGetNumaNodeConfigPageCount",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
      1232,
      3221225626LL);
    goto LABEL_19;
  }
  v5 = ExAllocatePool2(256, 8LL * (unsigned __int8)v1[256], 1833788502);
  *(_QWORD *)(a1 + 384) = v5;
  if ( !v5 )
  {
    v4 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmHvMemPartpGetNumaNodeConfigPageCount",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
      1244,
      3221225626LL);
    goto LABEL_19;
  }
  if ( (int)VsmmHvMemPartpOpenHvMemPartKey(131097, &v12) < 0 )
  {
    VidTraceInfoInternal0(
      "VsmmHvMemPartpGetNumaNodeConfigPageCount",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
      1251);
    v4 = 0;
    goto LABEL_16;
  }
  v6 = 0;
  *(_DWORD *)(a1 + 160) = *(_DWORD *)(a1 + 160) & 0xFFFFFFEF
                        | ((unsigned int)VidRegistryQueryUINT32WithDefault(v12, L"AllowNumaSpanning", 0) != 0 ? 0x10 : 0);
  if ( !v1[256] )
  {
LABEL_14:
    v4 = 0;
    if ( !*(_QWORD *)(a1 + 400) )
      VidTraceInfoInternal0(
        "VsmmHvMemPartpGetNumaNodeConfigPageCount",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
        1335);
    goto LABEL_16;
  }
  while ( 1 )
  {
    v11 = 0;
    if ( RtlStringCchPrintfW(pszDest, 0x11u, L"Node%u", v6) < 0 )
      goto LABEL_13;
    if ( (int)VidRegistryOpenSubkey(v12, pszDest, 131097, &v11) < 0 )
      goto LABEL_13;
    UINT64WithDefault = VidRegistryQueryUINT64WithDefault(v11, L"SizeInMB", 0);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v11);
    if ( !UINT64WithDefault )
      goto LABEL_13;
    v8 = UINT64WithDefault << 8;
    if ( (v8 & 0x1FF) != 0 )
      break;
    *(_QWORD *)(*(_QWORD *)(a1 + 392) + 8LL * v6) = v8;
    *(_QWORD *)(a1 + 400) += v8;
LABEL_13:
    if ( ++v6 >= v1[256] )
      goto LABEL_14;
  }
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v15, "VsmmHvMemPartpGetNumaNodeConfigPageCount");
    tlgCreate1Sz_char(v16, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c");
    LODWORD(v11) = 1322;
    v17 = &v11;
    v18 = 4;
    v19 = (char *)&v10;
    v10 = v6;
    v21 = &v13;
    v20 = 1;
    v13 = v8;
    v22 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, byte_140052C77, 0, 0, 7u, &v14);
  }
  v4 = -1073741811;
LABEL_16:
  if ( v12 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v12);
  if ( v4 < 0 )
LABEL_19:
    VsmmHvMemPartpTeardownLocked(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400c5a88  push    rbp
0x1400c5a8a  push    rbx
0x1400c5a8b  push    rsi
0x1400c5a8c  push    rdi
0x1400c5a8d  push    r13
0x1400c5a8f  push    r15
0x1400c5a91  lea     rbp, [rsp-2Fh]
0x1400c5a96  sub     rsp, 0F8h
0x1400c5a9d  mov     rax, cs:__security_cookie
0x1400c5aa4  xor     rax, rsp
0x1400c5aa7  mov     [rbp+57h+var_38], rax
0x1400c5aab  mov     r15, cs:VidDeviceExtension
0x1400c5ab2  mov     rdi, rcx
0x1400c5ab5  mov     ebx, 6D4D6456h
0x1400c5aba  mov     [rsp+120h+var_E0], 0
0x1400c5ac3  mov     r13d, 100h
0x1400c5ac9  mov     r8d, ebx
0x1400c5acc  mov     ecx, r13d
0x1400c5acf  movzx   edx, byte ptr [r15+100h]
0x1400c5ad7  shl     rdx, 3
0x1400c5adb  call    cs:__imp_ExAllocatePool2
0x1400c5ae2  nop     dword ptr [rax+rax+00h]
0x1400c5ae7  mov     [rdi+188h], rax
0x1400c5aee  test    rax, rax
0x1400c5af1  jnz     short loc_1400C5B1A
0x1400c5af3  mov     r9d, 0C000009Ah
0x1400c5af9  mov     ebx, r9d
0x1400c5afc  mov     r8d, 4D0h
0x1400c5b02  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c5b09  lea     rcx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c5b10  call    VidTraceErrorStatusInternal0
0x1400c5b15  jmp     loc_1400C5CDE
0x1400c5b1a  movzx   edx, byte ptr [r15+100h]
0x1400c5b22  mov     r8d, ebx
0x1400c5b25  shl     rdx, 3
0x1400c5b29  mov     rcx, r13
0x1400c5b2c  call    cs:__imp_ExAllocatePool2
0x1400c5b33  nop     dword ptr [rax+rax+00h]
0x1400c5b38  mov     [rdi+180h], rax
0x1400c5b3f  test    rax, rax
0x1400c5b42  jnz     short loc_1400C5B6B
0x1400c5b44  mov     r9d, 0C000009Ah
0x1400c5b4a  mov     ebx, r9d
0x1400c5b4d  mov     r8d, 4DCh
0x1400c5b53  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c5b5a  lea     rcx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c5b61  call    VidTraceErrorStatusInternal0
0x1400c5b66  jmp     loc_1400C5CDE
0x1400c5b6b  lea     rdx, [rsp+120h+var_E0]
0x1400c5b70  mov     ecx, 20019h
0x1400c5b75  call    VsmmHvMemPartpOpenHvMemPartKey
0x1400c5b7a  test    eax, eax
0x1400c5b7c  jns     short loc_1400C5B9E
0x1400c5b7e  mov     r8d, 4E3h
0x1400c5b84  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c5b8b  lea     rcx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c5b92  call    VidTraceInfoInternal0
0x1400c5b97  xor     ebx, ebx
0x1400c5b99  jmp     loc_1400C5CB3
0x1400c5b9e  mov     rcx, [rsp+120h+var_E0]
0x1400c5ba3  lea     rdx, aAllownumaspann; "AllowNumaSpanning"
0x1400c5baa  xor     r8d, r8d
0x1400c5bad  call    VidRegistryQueryUINT32WithDefault
0x1400c5bb2  neg     eax
0x1400c5bb4  mov     eax, [rdi+0A0h]
0x1400c5bba  sbb     ecx, ecx
0x1400c5bbc  and     eax, 0FFFFFFEFh
0x1400c5bbf  and     ecx, 10h
0x1400c5bc2  xor     sil, sil
0x1400c5bc5  or      ecx, eax
0x1400c5bc7  mov     [rdi+0A0h], ecx
0x1400c5bcd  cmp     [r15+100h], sil
0x1400c5bd4  jbe     loc_1400C5C8F
0x1400c5bda  movzx   r9d, sil
0x1400c5bde  lea     r8, aNodeU; "Node%u"
0x1400c5be5  mov     edx, 11h; cchDest
0x1400c5bea  mov     [rsp+120h+var_E8], 0
0x1400c5bf3  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1400c5bf7  call    RtlStringCchPrintfW
0x1400c5bfc  test    eax, eax
0x1400c5bfe  js      short loc_1400C5C7F
0x1400c5c00  mov     rcx, [rsp+120h+var_E0]
0x1400c5c05  lea     r9, [rsp+120h+var_E8]
0x1400c5c0a  mov     r8d, 20019h
0x1400c5c10  lea     rdx, [rbp+57h+pszDest]
0x1400c5c14  call    VidRegistryOpenSubkey
0x1400c5c19  test    eax, eax
0x1400c5c1b  js      short loc_1400C5C7F
0x1400c5c1d  mov     rcx, [rsp+120h+var_E8]
0x1400c5c22  lea     rdx, aSizeinmb; "SizeInMB"
0x1400c5c29  xor     r8d, r8d
0x1400c5c2c  call    VidRegistryQueryUINT64WithDefault
0x1400c5c31  mov     rcx, cs:WdfFunctions_01015
0x1400c5c38  mov     rbx, rax
0x1400c5c3b  mov     rdx, [rsp+120h+var_E8]
0x1400c5c40  mov     rax, [rcx+738h]
0x1400c5c47  mov     rcx, cs:WdfDriverGlobals
0x1400c5c4e  call    _guard_dispatch_icall
0x1400c5c53  test    rbx, rbx
0x1400c5c56  jz      short loc_1400C5C7F
0x1400c5c58  shl     rbx, 8
0x1400c5c5c  test    rbx, 1FFh
0x1400c5c63  jnz     loc_1400C5D05
0x1400c5c69  mov     rax, [rdi+188h]
0x1400c5c70  movzx   ecx, sil
0x1400c5c74  mov     [rax+rcx*8], rbx
0x1400c5c78  add     [rdi+190h], rbx
0x1400c5c7f  inc     sil
0x1400c5c82  cmp     sil, [r15+100h]
0x1400c5c89  jb      loc_1400C5BDA
0x1400c5c8f  xor     ebx, ebx
0x1400c5c91  cmp     [rdi+190h], rbx
0x1400c5c98  jnz     short loc_1400C5CB3
0x1400c5c9a  mov     r8d, 537h
0x1400c5ca0  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c5ca7  lea     rcx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c5cae  call    VidTraceInfoInternal0
0x1400c5cb3  cmp     [rsp+120h+var_E0], 0
0x1400c5cb9  jz      short loc_1400C5CDA
0x1400c5cbb  mov     rax, cs:WdfFunctions_01015
0x1400c5cc2  mov     rdx, [rsp+120h+var_E0]
0x1400c5cc7  mov     rcx, cs:WdfDriverGlobals
0x1400c5cce  mov     rax, [rax+738h]
0x1400c5cd5  call    _guard_dispatch_icall
0x1400c5cda  test    ebx, ebx
0x1400c5cdc  jns     short loc_1400C5CE6
0x1400c5cde  mov     rcx, rdi
0x1400c5ce1  call    VsmmHvMemPartpTeardownLocked
0x1400c5ce6  mov     eax, ebx
0x1400c5ce8  mov     rcx, [rbp+57h+var_38]
0x1400c5cec  xor     rcx, rsp; StackCookie
0x1400c5cef  call    __security_check_cookie
0x1400c5cf4  add     rsp, 0F8h
0x1400c5cfb  pop     r15
0x1400c5cfd  pop     r13
0x1400c5cff  pop     rdi
0x1400c5d00  pop     rsi
0x1400c5d01  pop     rbx
0x1400c5d02  pop     rbp
0x1400c5d03  retn
0x1400c5d05  mov     eax, cs:dword_140065110
0x1400c5d0b  cmp     eax, 2
0x1400c5d0e  jbe     loc_1400C5DBA
0x1400c5d14  mov     rdx, r13
0x1400c5d17  lea     rcx, dword_140065110
0x1400c5d1e  call    _tlgKeywordOn
0x1400c5d23  test    al, al
0x1400c5d25  jz      loc_1400C5DBA
0x1400c5d2b  lea     rdx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c5d32  lea     rcx, [rbp+57h+var_B0]
0x1400c5d36  call    _tlgCreate1Sz_char
0x1400c5d3b  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c5d42  lea     rcx, [rbp+57h+var_A0]
0x1400c5d46  call    _tlgCreate1Sz_char
0x1400c5d4b  lea     rax, [rsp+120h+var_E8]
0x1400c5d50  mov     dword ptr [rsp+120h+var_E8], 52Ah
0x1400c5d58  mov     [rbp+57h+var_90], rax
0x1400c5d5c  lea     rdx, byte_140052C77
0x1400c5d63  lea     rax, [rsp+120h+var_F0]
0x1400c5d68  mov     [rbp+57h+var_88], 4
0x1400c5d70  mov     [rbp+57h+var_80], rax
0x1400c5d74  lea     rcx, dword_140065110
0x1400c5d7b  lea     rax, [rsp+120h+var_D8]
0x1400c5d80  mov     [rsp+120h+var_F0], sil
0x1400c5d85  mov     [rbp+57h+var_70], rax
0x1400c5d89  xor     r9d, r9d
0x1400c5d8c  lea     rax, [rbp+57h+var_D0]
0x1400c5d90  mov     [rbp+57h+var_78], 1
0x1400c5d98  mov     [rsp+120h+var_F8], rax
0x1400c5d9d  xor     r8d, r8d
0x1400c5da0  mov     [rsp+120h+var_100], 7
0x1400c5da8  mov     [rsp+120h+var_D8], rbx
0x1400c5dad  mov     [rbp+57h+var_68], 8
0x1400c5db5  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c5dba  mov     ebx, 0C000000Dh
0x1400c5dbf  jmp     loc_1400C5CB3
```
