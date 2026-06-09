# SafeArrayToMultiString(tagSAFEARRAY *,ushort,ushort * *,unsigned __int64 *)

- ea: `0x180102c48`
- end: `0x180102e76`
- name: `?SafeArrayToMultiString@@YAJPEAUtagSAFEARRAY@@GPEAPEAGPEA_K@Z`
- size: `558`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int16, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014850`
- `0x180086c10`
- `0x1800a6d0c`
- `0x1800b7b20`
- `0x1800c0f2c`
- `0x1800e3758`

## callees

- `0x18004a5d4`
- `0x180102c48`
- `0x180102e7c`
- `0x180105984`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102e46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102e46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180102d4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180102d4e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180102cd0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180102cd0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180102cae`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180102cae`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180102e56`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180102e56`

## pseudocode

```c
__int64 __fastcall SafeArrayToMultiString(
        SAFEARRAY *psa,
        unsigned __int16 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4)
{
  unsigned __int16 *v4; // rsi
  unsigned __int16 *v5; // rdi
  SAFEARRAY *v7; // r14
  HRESULT UBound; // ebx
  int v9; // r14d
  unsigned int v10; // eax
  __int64 i; // r11
  const unsigned __int16 *v12; // rcx
  int v13; // r11d
  int v14; // r14d
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int16 *v17; // r12
  __int64 v18; // r13
  unsigned __int16 *v19; // rsi
  unsigned __int64 v20; // rsi
  unsigned int v22; // [rsp+28h] [rbp-38h]
  LONG plUbound; // [rsp+30h] [rbp-30h] BYREF
  void *ppvData; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v26; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v27; // [rsp+50h] [rbp-10h]

  v4 = 0;
  plUbound = 0;
  v5 = 0;
  v26 = 0;
  ppvData = 0;
  v25 = 0;
  v7 = psa;
  if ( !psa || !a3 )
    goto LABEL_2;
  UBound = SafeArrayAccessData(psa, &ppvData);
  if ( UBound < 0 )
    goto LABEL_36;
  if ( !ppvData )
  {
LABEL_2:
    UBound = -2147024809;
    goto LABEL_36;
  }
  UBound = SafeArrayGetUBound(v7, 1u, &plUbound);
  if ( UBound >= 0 )
  {
    v9 = 0;
    v10 = ++plUbound;
    for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(v13 + 1) )
    {
      v12 = (const unsigned __int16 *)*((_QWORD *)ppvData + i);
      if ( !v12 )
      {
        UBound = -2147024809;
        goto LABEL_35;
      }
      UBound = StringCchLengthW(v12, 0x7FFFFFFFu, &v26);
      if ( UBound < 0 )
        goto LABEL_35;
      v9 += v26 + 1;
      v10 = plUbound;
    }
    v14 = (a2 != 0) + 1 + v9;
    if ( v14 < 0 )
    {
      UBound = -2147467259;
    }
    else
    {
      v5 = (unsigned __int16 *)LocalAlloc(0, (unsigned int)(2 * v14));
      if ( v5 )
      {
        v15 = (unsigned int)v14;
        v16 = (unsigned int)(v14 - 1);
        *v5 = 0;
        v5[v16] = 0;
        v17 = v5;
        v27 = v16;
        v18 = 0;
        while ( 1 )
        {
          v26 = v15;
          if ( (unsigned int)v18 >= plUbound )
            break;
          UBound = StringCchCatExW(v17, v15, *((const unsigned __int16 **)ppvData + v18), &v25, &v26, v22);
          if ( UBound < 0 )
            goto LABEL_35;
          if ( !v26 )
          {
            UBound = -2147467259;
            MicrosoftTelemetryAssertTriggeredNoArgs(v16);
            goto LABEL_35;
          }
          v19 = v25;
          v15 = v26 - 1;
          *v25 = a2;
          v4 = v19 + 1;
          v25 = v4;
          v17 = v4;
          v18 = (unsigned int)(v18 + 1);
          *v4 = 0;
        }
        if ( a2 )
        {
          if ( v4 )
          {
            *v4 = a2;
          }
          else
          {
            if ( v17 != v5 )
              MicrosoftTelemetryAssertTriggeredNoArgs(v16);
            *v17 = a2;
          }
        }
        v20 = v27;
        if ( v5[v27] )
          MicrosoftTelemetryAssertTriggeredNoArgs(v16);
        *a3 = v5;
        v5 = 0;
        if ( a4 )
        {
          if ( !v14 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v16);
          *a4 = v20;
        }
      }
      else
      {
        UBound = -2147024882;
      }
    }
LABEL_35:
    v7 = psa;
  }
LABEL_36:
  LocalFree(v5);
  if ( ppvData )
    SafeArrayUnaccessData(v7);
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x180102c48  mov     rax, rsp
0x180102c4b  mov     [rax+10h], rbx
0x180102c4f  mov     [rax+20h], r9
0x180102c53  mov     [rax+18h], r8
0x180102c57  mov     [rax+8], rcx
0x180102c5b  push    rbp
0x180102c5c  push    rsi
0x180102c5d  push    rdi
0x180102c5e  push    r12
0x180102c60  push    r13
0x180102c62  push    r14
0x180102c64  push    r15
0x180102c66  mov     rbp, rsp
0x180102c69  sub     rsp, 60h
0x180102c6d  xor     esi, esi
0x180102c6f  mov     [rbp+plUbound], 0
0x180102c76  xor     edi, edi
0x180102c78  mov     [rbp+var_18], 0
0x180102c80  mov     [rbp+ppvData], 0
0x180102c88  mov     rax, r8
0x180102c8b  mov     [rbp+var_20], rsi
0x180102c8f  movzx   r15d, dx
0x180102c93  mov     r14, rcx
0x180102c96  test    rcx, rcx
0x180102c99  jnz     short loc_180102CA5
0x180102c9b  mov     ebx, 80070057h
0x180102ca0  jmp     loc_180102E43
0x180102ca5  test    rax, rax
0x180102ca8  jz      short loc_180102C9B
0x180102caa  lea     rdx, [rbp+ppvData]; ppvData
0x180102cae  call    cs:__imp_SafeArrayAccessData
0x180102cb4  mov     ebx, eax
0x180102cb6  test    eax, eax
0x180102cb8  js      loc_180102E43
0x180102cbe  cmp     [rbp+ppvData], rsi
0x180102cc2  jz      short loc_180102C9B
0x180102cc4  lea     r8, [rbp+plUbound]; plUbound
0x180102cc8  mov     edx, 1; nDim
0x180102ccd  mov     rcx, r14; psa
0x180102cd0  call    cs:__imp_SafeArrayGetUBound
0x180102cd6  mov     ebx, eax
0x180102cd8  test    eax, eax
0x180102cda  js      loc_180102E43
0x180102ce0  mov     eax, [rbp+plUbound]
0x180102ce3  xor     r14d, r14d
0x180102ce6  inc     eax
0x180102ce8  mov     [rbp+plUbound], eax
0x180102ceb  xor     r11d, r11d
0x180102cee  cmp     r11d, eax
0x180102cf1  jnb     short loc_180102D32
0x180102cf3  mov     rax, [rbp+ppvData]
0x180102cf7  mov     rcx, [rax+r11*8]; unsigned __int16 *
0x180102cfb  test    rcx, rcx
0x180102cfe  jz      short loc_180102D28
0x180102d00  lea     r8, [rbp+var_18]; unsigned __int64 *
0x180102d04  mov     edx, 7FFFFFFFh; unsigned __int64
0x180102d09  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180102d0e  mov     ebx, eax
0x180102d10  test    eax, eax
0x180102d12  js      loc_180102E3F
0x180102d18  mov     eax, dword ptr [rbp+var_18]
0x180102d1b  inc     eax
0x180102d1d  add     r14d, eax
0x180102d20  mov     eax, [rbp+plUbound]
0x180102d23  inc     r11d
0x180102d26  jmp     short loc_180102CEE
0x180102d28  mov     ebx, 80070057h
0x180102d2d  jmp     loc_180102E3F
0x180102d32  xor     ecx, ecx
0x180102d34  xor     eax, eax
0x180102d36  cmp     ax, r15w
0x180102d3a  setnz   cl
0x180102d3d  inc     ecx
0x180102d3f  add     r14d, ecx
0x180102d42  js      loc_180102E3A
0x180102d48  lea     edx, [r14+r14]; uBytes
0x180102d4c  xor     ecx, ecx; uFlags
0x180102d4e  call    cs:__imp_LocalAlloc
0x180102d54  mov     rdi, rax
0x180102d57  test    rax, rax
0x180102d5a  jnz     short loc_180102D66
0x180102d5c  mov     ebx, 8007000Eh
0x180102d61  jmp     loc_180102E3F
0x180102d66  xor     eax, eax
0x180102d68  mov     edx, r14d; unsigned __int64
0x180102d6b  lea     ecx, [r14-1]
0x180102d6f  mov     [rdi], ax
0x180102d72  mov     [rdi+rcx*2], ax
0x180102d76  mov     r12, rdi
0x180102d79  mov     [rbp+var_10], rcx
0x180102d7d  xor     r13d, r13d
0x180102d80  mov     [rbp+var_18], rdx
0x180102d84  cmp     r13d, [rbp+plUbound]
0x180102d88  jnb     short loc_180102DE6
0x180102d8a  mov     r8, [rbp+ppvData]
0x180102d8e  lea     rcx, [rbp+var_18]
0x180102d92  mov     [rsp+60h+var_40], rcx; unsigned __int64 *
0x180102d97  lea     r9, [rbp+var_20]; unsigned __int16 **
0x180102d9b  mov     rcx, r12; unsigned __int16 *
0x180102d9e  mov     r8, [r8+r13*8]; unsigned __int16 *
0x180102da2  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180102da7  mov     ebx, eax
0x180102da9  test    eax, eax
0x180102dab  js      loc_180102E3F
0x180102db1  mov     rdx, [rbp+var_18]
0x180102db5  test    rdx, rdx
0x180102db8  jz      short loc_180102DDA
0x180102dba  mov     rsi, [rbp+var_20]
0x180102dbe  xor     eax, eax
0x180102dc0  dec     rdx
0x180102dc3  mov     [rsi], r15w
0x180102dc7  add     rsi, 2
0x180102dcb  mov     [rbp+var_20], rsi
0x180102dcf  mov     r12, rsi
0x180102dd2  inc     r13d
0x180102dd5  mov     [rsi], ax
0x180102dd8  jmp     short loc_180102D80
0x180102dda  mov     ebx, 80004005h
0x180102ddf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180102de4  jmp     short loc_180102E3F
0x180102de6  xor     eax, eax
0x180102de8  cmp     ax, r15w
0x180102dec  jz      short loc_180102E08
0x180102dee  test    rsi, rsi
0x180102df1  jz      short loc_180102DF9
0x180102df3  mov     [rsi], r15w
0x180102df7  jmp     short loc_180102E08
0x180102df9  cmp     r12, rdi
0x180102dfc  jz      short loc_180102E03
0x180102dfe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180102e03  mov     [r12], r15w
0x180102e08  mov     rsi, [rbp+var_10]
0x180102e0c  xor     eax, eax
0x180102e0e  cmp     ax, [rdi+rsi*2]
0x180102e12  jz      short loc_180102E19
0x180102e14  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180102e19  mov     rax, [rbp+arg_10]
0x180102e1d  mov     r15, [rbp+arg_18]
0x180102e21  mov     [rax], rdi
0x180102e24  xor     edi, edi
0x180102e26  test    r15, r15
0x180102e29  jz      short loc_180102E3F
0x180102e2b  test    r14d, r14d
0x180102e2e  jnz     short loc_180102E35
0x180102e30  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180102e35  mov     [r15], rsi
0x180102e38  jmp     short loc_180102E3F
0x180102e3a  mov     ebx, 80004005h
0x180102e3f  mov     r14, [rbp+arg_0]
0x180102e43  mov     rcx, rdi; hMem
0x180102e46  call    cs:__imp_LocalFree
0x180102e4c  cmp     [rbp+ppvData], 0
0x180102e51  jz      short loc_180102E5C
0x180102e53  mov     rcx, r14; psa
0x180102e56  call    cs:__imp_SafeArrayUnaccessData
0x180102e5c  mov     eax, ebx
0x180102e5e  mov     rbx, [rsp+60h+arg_8]
0x180102e66  add     rsp, 60h
0x180102e6a  pop     r15
0x180102e6c  pop     r14
0x180102e6e  pop     r13
0x180102e70  pop     r12
0x180102e72  pop     rdi
0x180102e73  pop     rsi
0x180102e74  pop     rbp
0x180102e75  retn
```
