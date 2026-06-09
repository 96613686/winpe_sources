# ReadSafeArrayFromStream(tagSAFEARRAY * *,ushort,ISequentialStream *)

- ea: `0x1800029c8`
- end: `0x180002bde`
- name: `?ReadSafeArrayFromStream@@YAJPEAPEAUtagSAFEARRAY@@GPEAUISequentialStream@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(struct tagSAFEARRAY **, VARTYPE, struct ISequentialStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002d30`

## callees

- `0x1800029c8`
- `0x180003574`
- `0x180004010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002ac9`
- `OLEAUT32!__imp_SysFreeString` at `0x180002ac9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002a5e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002a5e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002adf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002adf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180002a7a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180002a7a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002ab2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002ab2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180002b6b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180002b6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ad1`

## pseudocode

```c
__int64 __fastcall ReadSafeArrayFromStream(struct tagSAFEARRAY **a1, VARTYPE a2, struct ISequentialStream *a3)
{
  SAFEARRAY *v3; // rsi
  OLECHAR *v4; // rdi
  HRESULT v8; // ebx
  SAFEARRAY *v9; // rax
  __int64 v10; // rcx
  void *v11; // rdx
  __int64 v13; // r15
  struct ISequentialStreamVtbl *lpVtbl; // rax
  BSTR v15; // rax
  UINT len; // [rsp+30h] [rbp-20h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-18h] BYREF
  void *ppvData; // [rsp+40h] [rbp-10h] BYREF
  int v19; // [rsp+80h] [rbp+30h] BYREF
  ULONG v20; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  v4 = 0;
  rgsabound = 0;
  ppvData = 0;
  len = 0;
  v20 = 0;
  v19 = 0;
  if ( !a1 || !a3 )
  {
    v8 = -2147467261;
    goto LABEL_17;
  }
  v8 = ((__int64 (__fastcall *)(struct ISequentialStream *, ULONG *, __int64, int *))a3->lpVtbl->Read)(
         a3,
         &v20,
         4,
         &v19);
  if ( v8 >= 0 )
  {
    if ( v19 != 4 )
    {
LABEL_6:
      v8 = -2147467259;
      goto LABEL_17;
    }
    rgsabound.cElements = v20;
    rgsabound.lLbound = 0;
    v9 = SafeArrayCreate(a2, 1u, &rgsabound);
    v3 = v9;
    if ( !v9 )
    {
LABEL_8:
      v8 = -2147024882;
      goto LABEL_17;
    }
    v8 = SafeArrayAccessData(v9, &ppvData);
    if ( v8 >= 0 )
    {
      v11 = ppvData;
      if ( !ppvData )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v10);
        v11 = ppvData;
      }
      if ( a2 != 8 )
      {
        if ( a2 == 17 )
        {
          v8 = ((__int64 (__fastcall *)(struct ISequentialStream *, void *, _QWORD, int *))a3->lpVtbl->Read)(
                 a3,
                 v11,
                 v20,
                 &v19);
          if ( v8 < 0 )
            goto LABEL_17;
          if ( v20 != v19 )
            goto LABEL_6;
        }
        else
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v10);
        }
        goto LABEL_15;
      }
      v13 = 0;
      if ( !v20 )
      {
LABEL_15:
        v4 = 0;
        v8 = SafeArrayUnaccessData(v3);
        if ( v8 >= 0 )
        {
          *a1 = v3;
          v3 = 0;
        }
        goto LABEL_17;
      }
      while ( 1 )
      {
        lpVtbl = a3->lpVtbl;
        v19 = 0;
        v8 = ((__int64 (__fastcall *)(struct ISequentialStream *, UINT *, __int64, int *))lpVtbl->Read)(
               a3,
               &len,
               4,
               &v19);
        if ( v8 < 0 )
          break;
        if ( v19 != 4 )
        {
          v8 = -2147467259;
          break;
        }
        v15 = SysAllocStringByteLen(0, len);
        v4 = v15;
        if ( !v15 )
          goto LABEL_8;
        v8 = ((__int64 (__fastcall *)(struct ISequentialStream *, BSTR, _QWORD, int *))a3->lpVtbl->Read)(
               a3,
               v15,
               len,
               &v19);
        if ( v8 < 0 )
          goto LABEL_17;
        if ( len != v19 )
          goto LABEL_6;
        v4[(unsigned __int64)len >> 1] = 0;
        *((_QWORD *)ppvData + v13) = v4;
        v13 = (unsigned int)(v13 + 1);
        if ( (unsigned int)v13 >= v20 )
          goto LABEL_15;
      }
      v4 = 0;
    }
  }
LABEL_17:
  SysFreeString(v4);
  LocalFree(0);
  if ( v3 )
    SafeArrayDestroy(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800029c8  mov     [rsp-28h+arg_8], rbx
0x1800029cd  mov     [rsp-28h+arg_10], rsi
0x1800029d2  push    rbp
0x1800029d3  push    rdi
0x1800029d4  push    r12
0x1800029d6  push    r14
0x1800029d8  push    r15
0x1800029da  mov     rbp, rsp
0x1800029dd  sub     rsp, 50h
0x1800029e1  xor     esi, esi
0x1800029e3  xor     edi, edi
0x1800029e5  mov     qword ptr [rbp+rgsabound.cElements], rsi
0x1800029e9  mov     r14, r8
0x1800029ec  mov     [rbp+ppvData], rsi
0x1800029f0  movzx   r15d, dx
0x1800029f4  mov     [rbp+len], esi
0x1800029f7  mov     r12, rcx
0x1800029fa  mov     [rbp+arg_18], esi
0x1800029fd  mov     [rbp+arg_0], esi
0x180002a00  test    rcx, rcx
0x180002a03  jnz     short loc_180002A0F
0x180002a05  mov     ebx, 80004003h
0x180002a0a  jmp     loc_180002AC6
0x180002a0f  test    r14, r14
0x180002a12  jz      short loc_180002A05
0x180002a14  mov     rax, [r8]
0x180002a17  lea     r9, [rbp+arg_0]
0x180002a1b  mov     r8d, 4
0x180002a21  lea     rdx, [rbp+arg_18]
0x180002a25  mov     rcx, r14
0x180002a28  mov     rax, [rax+18h]
0x180002a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a31  mov     ebx, eax
0x180002a33  test    eax, eax
0x180002a35  js      loc_180002AC6
0x180002a3b  cmp     [rbp+arg_0], 4
0x180002a3f  jz      short loc_180002A48
0x180002a41  mov     ebx, 80004005h
0x180002a46  jmp     short loc_180002AC6
0x180002a48  mov     eax, [rbp+arg_18]
0x180002a4b  lea     r8, [rbp+rgsabound]; rgsabound
0x180002a4f  mov     edx, 1; cDims
0x180002a54  mov     [rbp+rgsabound.cElements], eax
0x180002a57  movzx   ecx, r15w; vt
0x180002a5b  mov     [rbp+rgsabound.lLbound], esi
0x180002a5e  call    cs:__imp_SafeArrayCreate
0x180002a64  mov     rsi, rax
0x180002a67  test    rax, rax
0x180002a6a  jnz     short loc_180002A73
0x180002a6c  mov     ebx, 8007000Eh
0x180002a71  jmp     short loc_180002AC6
0x180002a73  lea     rdx, [rbp+ppvData]; ppvData
0x180002a77  mov     rcx, rsi; psa
0x180002a7a  call    cs:__imp_SafeArrayAccessData
0x180002a80  mov     ebx, eax
0x180002a82  test    eax, eax
0x180002a84  js      short loc_180002AC6
0x180002a86  mov     rdx, [rbp+ppvData]
0x180002a8a  test    rdx, rdx
0x180002a8d  jnz     short loc_180002A98
0x180002a8f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002a94  mov     rdx, [rbp+ppvData]
0x180002a98  cmp     r15w, 8
0x180002a9d  jz      loc_180002B2A
0x180002aa3  cmp     r15w, 11h
0x180002aa8  jz      short loc_180002B00
0x180002aaa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002aaf  mov     rcx, rsi; psa
0x180002ab2  call    cs:__imp_SafeArrayUnaccessData
0x180002ab8  xor     edi, edi
0x180002aba  mov     ebx, eax
0x180002abc  test    eax, eax
0x180002abe  js      short loc_180002AC6
0x180002ac0  mov     [r12], rsi
0x180002ac4  xor     esi, esi
0x180002ac6  mov     rcx, rdi; bstrString
0x180002ac9  call    cs:__imp_SysFreeString
0x180002acf  xor     ecx, ecx; hMem
0x180002ad1  call    cs:__imp_LocalFree
0x180002ad7  test    rsi, rsi
0x180002ada  jz      short loc_180002AE5
0x180002adc  mov     rcx, rsi; psa
0x180002adf  call    cs:__imp_SafeArrayDestroy
0x180002ae5  lea     r11, [rsp+50h+var_s0]
0x180002aea  mov     eax, ebx
0x180002aec  mov     rbx, [r11+38h]
0x180002af0  mov     rsi, [r11+40h]
0x180002af4  mov     rsp, r11
0x180002af7  pop     r15
0x180002af9  pop     r14
0x180002afb  pop     r12
0x180002afd  pop     rdi
0x180002afe  pop     rbp
0x180002aff  retn
0x180002b00  mov     rax, [r14]
0x180002b03  lea     r9, [rbp+arg_0]
0x180002b07  mov     r8d, [rbp+arg_18]
0x180002b0b  mov     rcx, r14
0x180002b0e  mov     rax, [rax+18h]
0x180002b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b17  mov     ebx, eax
0x180002b19  test    eax, eax
0x180002b1b  js      short loc_180002AC6
0x180002b1d  mov     eax, [rbp+arg_0]
0x180002b20  cmp     [rbp+arg_18], eax
0x180002b23  jz      short loc_180002AAF
0x180002b25  jmp     loc_180002A41
0x180002b2a  xor     r15d, r15d
0x180002b2d  cmp     [rbp+arg_18], edi
0x180002b30  jbe     loc_180002AAF
0x180002b36  mov     rax, [r14]
0x180002b39  lea     r9, [rbp+arg_0]
0x180002b3d  mov     r8d, 4
0x180002b43  mov     [rbp+arg_0], 0
0x180002b4a  lea     rdx, [rbp+len]
0x180002b4e  mov     rcx, r14
0x180002b51  mov     rax, [rax+18h]
0x180002b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b5a  mov     ebx, eax
0x180002b5c  test    eax, eax
0x180002b5e  js      short loc_180002BD7
0x180002b60  cmp     [rbp+arg_0], 4
0x180002b64  jnz     short loc_180002BD2
0x180002b66  mov     edx, [rbp+len]; len
0x180002b69  xor     ecx, ecx; psz
0x180002b6b  call    cs:__imp_SysAllocStringByteLen
0x180002b71  mov     rdi, rax
0x180002b74  test    rax, rax
0x180002b77  jz      loc_180002A6C
0x180002b7d  mov     rcx, [r14]
0x180002b80  lea     r9, [rbp+arg_0]
0x180002b84  mov     r8d, [rbp+len]
0x180002b88  mov     rdx, rdi
0x180002b8b  mov     rax, [rcx+18h]
0x180002b8f  mov     rcx, r14
0x180002b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b97  mov     ebx, eax
0x180002b99  test    eax, eax
0x180002b9b  js      loc_180002AC6
0x180002ba1  mov     eax, [rbp+len]
0x180002ba4  cmp     eax, [rbp+arg_0]
0x180002ba7  jnz     loc_180002A41
0x180002bad  mov     ecx, eax
0x180002baf  xor     eax, eax
0x180002bb1  shr     rcx, 1
0x180002bb4  mov     [rdi+rcx*2], ax
0x180002bb8  mov     rax, [rbp+ppvData]
0x180002bbc  mov     [rax+r15*8], rdi
0x180002bc0  inc     r15d
0x180002bc3  cmp     r15d, [rbp+arg_18]
0x180002bc7  jb      loc_180002B36
0x180002bcd  jmp     loc_180002AAF
0x180002bd2  mov     ebx, 80004005h
0x180002bd7  xor     edi, edi
0x180002bd9  jmp     loc_180002AC6
```
