# LocateCLMDDevicesA(unsigned __int64,SCARD_READERSTATEA *,ulong,_SCARD_ATRMASK * *,ulong *)

- ea: `0x180024b4c`
- end: `0x180024efc`
- name: `?LocateCLMDDevicesA@@YAX_KPEAUSCARD_READERSTATEA@@KPEAPEAU_SCARD_ATRMASK@@PEAK@Z`
- size: `944`
- prototype: `void __fastcall(unsigned __int64, struct SCARD_READERSTATEA *, unsigned int, struct _SCARD_ATRMASK **, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180026640`

## callees

- `0x180003ee0`
- `0x180005de0`
- `0x18000e3d0`
- `0x180014b00`
- `0x18001b9b8`
- `0x18001b9c4`
- `0x18001ba04`
- `0x18001c7a8`
- `0x180024b4c`
- `0x180028ed8`
- `0x18002a390`
- `0x18002ef20`
- `0x18002ef2c`
- `0x18002ef38`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LocateCLMDDevicesA(
        SCARDCONTEXT a1,
        struct SCARD_READERSTATEA *a2,
        unsigned int a3,
        struct _SCARD_ATRMASK **a4,
        unsigned int *a5)
{
  struct _SCARD_ATRMASK *v5; // r12
  LONG v6; // edi
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v7; // rax
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v8; // r15
  unsigned int v9; // esi
  unsigned int i; // eax
  unsigned __int64 v11; // rsi
  unsigned int v12; // edi
  WCHAR *v13; // rax
  const WCHAR *v14; // rax
  char *v15; // rbx
  unsigned __int64 v16; // rax
  char *v17; // rbx
  unsigned __int64 v18; // rax
  __int64 v19; // rbx
  unsigned int v20; // [rsp+30h] [rbp-98h]
  ulong v21; // [rsp+34h] [rbp-94h]
  unsigned int v22; // [rsp+38h] [rbp-90h]
  const int *v23; // [rsp+40h] [rbp-88h] BYREF
  const WCHAR *v24; // [rsp+48h] [rbp-80h]
  __int64 v25; // [rsp+50h] [rbp-78h]
  LONG pExceptionObject; // [rsp+58h] [rbp-70h] BYREF
  void *Buf2; // [rsp+60h] [rbp-68h]
  void *v28; // [rsp+68h] [rbp-60h] BYREF
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v29; // [rsp+70h] [rbp-58h]
  ulong v30; // [rsp+78h] [rbp-50h] BYREF
  struct _SCARD_ATRMASK *v31; // [rsp+80h] [rbp-48h]

  Buf2 = 0;
  v28 = 0;
  if ( !a1 || !a2 || !a4 || !a5 )
  {
    v6 = -2146435041;
LABEL_41:
    pExceptionObject = v6;
    throw (ulong *)&pExceptionObject;
  }
  v5 = (struct _SCARD_ATRMASK *)operator new[](saturated_mul(a3, 0x4Cu));
  v31 = v5;
  if ( !v5 )
  {
    v6 = -2146435066;
    goto LABEL_41;
  }
  v7 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)operator new(0x40u);
  v8 = v7;
  v29 = v7;
  if ( v7 )
  {
    v6 = 0;
    v21 = 0;
    v9 = 0;
    v20 = 0;
    memset_0(v7, 0, sizeof(struct $B80B7D01E79FADDB4AAC58DE22BC823F));
    for ( i = 0; ; i = v22 + 1 )
    {
      v22 = i;
      if ( i >= a3 )
        break;
      v23 = &CBuffer::`vftable';
      v24 = 0;
      v25 = 0;
      try
      {
        v11 = (unsigned __int64)i << 6;
        v12 = MoveToUnicodeString(0, *(LPCCH *)((char *)&a2->szReader + v11), 0);
        CBuffer::Presize((CBuffer *)&v23, 2 * v12, 0);
        LODWORD(v25) = 2 * v12;
        v13 = (WCHAR *)CBuffer::Access((CBuffer *)&v23, 0);
        MoveToUnicodeString(v13, *(LPCCH *)((char *)&a2->szReader + v11), v12);
      }
      catch ( ulong v30 )
      {
        v21 = v30;
        v23 = &CBuffer::`vftable';
        CBuffer::Clear((CBuffer *)&v23);
        v6 = v21;
        v5 = v31;
        v8 = v29;
        goto LABEL_47;
      }
      v14 = &WideCharStr;
      if ( HIDWORD(v25) )
        v14 = v24;
      v8->szReader = v14;
      v8->dwCurrentState = 0;
      v6 = SCardGetStatusChangeW(a1, 0, v8, 1u);
      v21 = v6;
      if ( v6 )
      {
        v23 = &CBuffer::`vftable';
        CBuffer::Clear((CBuffer *)&v23);
        goto LABEL_47;
      }
      if ( !v8->cbAtr || (unsigned int)CidUtilGetDeviceIdByReaderName(v8->szReader, (__int64)&v28) )
        goto LABEL_33;
      v15 = (char *)Buf2;
      if ( Buf2 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)Buf2 + v16) );
        if ( v16 > 0xD
          && !memcmp_0(L"SCFILTER\\CID_", Buf2, 0x1Au)
          && (!memcmp_0(L"2777BE07-6993-4513-BD80-C184FCB0AB2D", v15 + 26, 0x4Au)
           || !memcmp_0(L"E2F748F9-DB8B-4C08-A258-583D8955D94A", v15 + 26, 0x4Au)) )
        {
          goto LABEL_32;
        }
      }
      v17 = (char *)v28;
      if ( !v28 )
        goto LABEL_33;
      v18 = -1;
      do
        ++v18;
      while ( *((_WORD *)v28 + v18) );
      if ( v18 > 0xD
        && !memcmp_0(L"SCFILTER\\CID_", v28, 0x1Au)
        && (!memcmp_0(L"2777BE07-6993-4513-BD80-C184FCB0AB2D", v17 + 26, 0x4Au)
         || !memcmp_0(L"E2F748F9-DB8B-4C08-A258-583D8955D94A", v17 + 26, 0x4Au)) )
      {
LABEL_32:
        v19 = v20;
        memcpy_0(v5[v19].rgbAtr, v8->rgbAtr, v8->cbAtr);
        memset_0(v5[v19].rgbMask, 255, v8->cbAtr);
        v5[v19].cbAtr = v8->cbAtr;
        v9 = ++v20;
      }
      else
      {
LABEL_33:
        v9 = v20;
      }
      v23 = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)&v23);
    }
    *a4 = v5;
    *a5 = v9;
    goto LABEL_52;
  }
  v6 = -2146435066;
  v21 = -2146435066;
LABEL_47:
  try
  {
    operator delete(v5);
  }
  catch ( ... )
  {
    v6 = v21;
    v8 = v29;
  }
  if ( v8 )
  {
LABEL_52:
    try
    {
      operator delete(v8);
    }
    catch ( ... )
    {
      v6 = v21;
    }
  }
  if ( v6 )
    goto LABEL_41;
}

```

## disassembly

```asm
0x180024b4c  mov     r11, rsp
0x180024b4f  mov     [r11+20h], r9
0x180024b53  mov     [r11+18h], r8d
0x180024b57  mov     [r11+10h], rdx
0x180024b5b  mov     [r11+8], rcx
0x180024b5f  push    rbx
0x180024b60  push    rsi
0x180024b61  push    rdi
0x180024b62  push    r12
0x180024b64  push    r13
0x180024b66  push    r14
0x180024b68  push    r15
0x180024b6a  sub     rsp, 90h
0x180024b71  mov     rbx, r9
0x180024b74  mov     eax, r8d
0x180024b77  xor     r14d, r14d
0x180024b7a  mov     [r11-68h], r14
0x180024b7e  mov     [r11-60h], r14
0x180024b82  test    rcx, rcx
0x180024b85  jz      loc_180024EE1
0x180024b8b  test    rdx, rdx
0x180024b8e  jz      loc_180024EE1
0x180024b94  test    rbx, rbx
0x180024b97  jz      loc_180024EE1
0x180024b9d  cmp     [rsp+0C8h+arg_20], r14
0x180024ba5  jz      loc_180024EE1
0x180024bab  mov     ecx, eax
0x180024bad  lea     eax, [r14+4Ch]
0x180024bb1  mul     rcx
0x180024bb4  lea     rcx, [r14-1]
0x180024bb8  cmovb   rax, rcx
0x180024bbc  mov     rcx, rax; unsigned __int64
0x180024bbf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180024bc4  mov     r12, rax
0x180024bc7  mov     [rsp+0C8h+var_48], rax
0x180024bcf  test    rax, rax
0x180024bd2  jnz     short loc_180024BDE
0x180024bd4  mov     edi, 80100006h
0x180024bd9  jmp     loc_180024EE6
0x180024bde  mov     ecx, 40h ; '@'; Size
0x180024be3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024be8  mov     r15, rax
0x180024beb  mov     [rsp+0C8h+var_58], rax
0x180024bf0  test    rax, rax
0x180024bf3  jnz     short loc_180024C03
0x180024bf5  mov     edi, 80100006h
0x180024bfa  mov     [rsp+0C8h+var_94], edi
0x180024bfe  jmp     loc_180024E86
0x180024c03  mov     edi, r14d
0x180024c06  mov     [rsp+0C8h+var_94], r14d
0x180024c0b  mov     esi, r14d
0x180024c0e  mov     [rsp+0C8h+var_98], r14d
0x180024c13  xor     edx, edx; Val
0x180024c15  lea     r8d, [rdx+40h]; Size
0x180024c19  mov     rcx, r15; void *
0x180024c1c  call    memset_0
0x180024c21  mov     eax, r14d
0x180024c24  lea     r13, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180024c2b  mov     [rsp+0C8h+var_90], eax
0x180024c2f  cmp     eax, [rsp+0C8h+arg_10]
0x180024c36  jnb     loc_180024EA1
0x180024c3c  mov     [rsp+0C8h+var_88], r13
0x180024c41  mov     [rsp+0C8h+var_80], r14
0x180024c46  mov     [rsp+0C8h+var_78], r14
0x180024c4b  mov     esi, eax
0x180024c4d  shl     rsi, 6
0x180024c51  xor     r8d, r8d; cchWideChar
0x180024c54  mov     rdx, [rsp+0C8h+arg_8]
0x180024c5c  mov     rdx, [rsi+rdx]; lpMultiByteStr
0x180024c60  xor     ecx, ecx; lpWideCharStr
0x180024c62  call    ?MoveToUnicodeString@@YAKPEAGPEBDK@Z; MoveToUnicodeString(ushort *,char const *,ulong)
0x180024c67  mov     edi, eax
0x180024c69  lea     ebx, [rax+rax]
0x180024c6c  xor     r8d, r8d; int
0x180024c6f  mov     edx, ebx; unsigned int
0x180024c71  lea     rcx, [rsp+0C8h+var_88]; this
0x180024c76  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x180024c7b  mov     dword ptr [rsp+0C8h+var_78], ebx
0x180024c7f  xor     edx, edx; unsigned int
0x180024c81  lea     rcx, [rsp+0C8h+var_88]; this
0x180024c86  call    ?Access@CBuffer@@QEBAPEAEK@Z; CBuffer::Access(ulong)
0x180024c8b  mov     rcx, rax; lpWideCharStr
0x180024c8e  mov     r8d, edi; cchWideChar
0x180024c91  mov     rax, [rsp+0C8h+arg_8]
0x180024c99  mov     rdx, [rsi+rax]; lpMultiByteStr
0x180024c9d  call    ?MoveToUnicodeString@@YAKPEAGPEBDK@Z; MoveToUnicodeString(ushort *,char const *,ulong)
0x180024ca2  nop
0x180024ca3  lea     rax, WideCharStr
0x180024caa  cmp     dword ptr [rsp+0C8h+var_78+4], r14d
0x180024caf  cmova   rax, [rsp+0C8h+var_80]
0x180024cb5  mov     [r15], rax
0x180024cb8  mov     [r15+10h], r14d
0x180024cbc  mov     r9d, 1; cReaders
0x180024cc2  mov     r8, r15; rgReaderStates
0x180024cc5  xor     edx, edx; dwTimeout
0x180024cc7  mov     rcx, [rsp+0C8h+hContext]; hContext
0x180024ccf  call    SCardGetStatusChangeW
0x180024cd4  mov     edi, eax
0x180024cd6  mov     [rsp+0C8h+var_94], eax
0x180024cda  test    eax, eax
0x180024cdc  jz      short loc_180024CF2
0x180024cde  mov     [rsp+0C8h+var_88], r13
0x180024ce3  lea     rcx, [rsp+0C8h+var_88]; this
0x180024ce8  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180024ced  jmp     loc_180024E86
0x180024cf2  mov     r8d, [r15+18h]
0x180024cf6  test    r8d, r8d
0x180024cf9  jz      loc_180024E41
0x180024cff  lea     rdx, [r15+1Ch]
0x180024d03  lea     rcx, [rsp+0C8h+var_60]
0x180024d08  mov     [rsp+0C8h+var_A8], rcx; __int64
0x180024d0d  lea     r9, [rsp+0C8h+Buf2]
0x180024d12  mov     rcx, [r15]; szReader
0x180024d15  call    CidUtilGetDeviceIdByReaderName
0x180024d1a  test    eax, eax
0x180024d1c  jnz     loc_180024E41
0x180024d22  mov     rbx, [rsp+0C8h+Buf2]
0x180024d27  test    rbx, rbx
0x180024d2a  jz      short loc_180024D8F
0x180024d2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024d30  inc     rax
0x180024d33  cmp     [rbx+rax*2], r14w
0x180024d38  jnz     short loc_180024D30
0x180024d3a  cmp     rax, 0Dh
0x180024d3e  jbe     short loc_180024D8F
0x180024d40  mov     r8d, 1Ah; Size
0x180024d46  mov     rdx, rbx; Buf2
0x180024d49  lea     rcx, aScfilterCid; "SCFILTER\\CID_"
0x180024d50  call    memcmp_0
0x180024d55  test    eax, eax
0x180024d57  jnz     short loc_180024D8F
0x180024d59  lea     r8d, [rax+4Ah]; Size
0x180024d5d  lea     rdx, [rbx+1Ah]; Buf2
0x180024d61  lea     rcx, a2777be07699345; "2777BE07-6993-4513-BD80-C184FCB0AB2D"
0x180024d68  call    memcmp_0
0x180024d6d  test    eax, eax
0x180024d6f  jz      loc_180024E00
0x180024d75  mov     r8d, 4Ah ; 'J'; Size
0x180024d7b  lea     rdx, [rbx+1Ah]; Buf2
0x180024d7f  lea     rcx, aE2f748f9Db8b4c; "E2F748F9-DB8B-4C08-A258-583D8955D94A"
0x180024d86  call    memcmp_0
0x180024d8b  test    eax, eax
0x180024d8d  jz      short loc_180024E00
0x180024d8f  mov     rbx, [rsp+0C8h+var_60]
0x180024d94  test    rbx, rbx
0x180024d97  jz      loc_180024E41
0x180024d9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024da1  inc     rax
0x180024da4  cmp     [rbx+rax*2], r14w
0x180024da9  jnz     short loc_180024DA1
0x180024dab  cmp     rax, 0Dh
0x180024daf  jbe     loc_180024E41
0x180024db5  mov     r8d, 1Ah; Size
0x180024dbb  mov     rdx, rbx; Buf2
0x180024dbe  lea     rcx, aScfilterCid; "SCFILTER\\CID_"
0x180024dc5  call    memcmp_0
0x180024dca  test    eax, eax
0x180024dcc  jnz     short loc_180024E41
0x180024dce  lea     r8d, [rax+4Ah]; Size
0x180024dd2  lea     rdx, [rbx+1Ah]; Buf2
0x180024dd6  lea     rcx, a2777be07699345; "2777BE07-6993-4513-BD80-C184FCB0AB2D"
0x180024ddd  call    memcmp_0
0x180024de2  test    eax, eax
0x180024de4  jz      short loc_180024E00
0x180024de6  mov     r8d, 4Ah ; 'J'; Size
0x180024dec  lea     rdx, [rbx+1Ah]; Buf2
0x180024df0  lea     rcx, aE2f748f9Db8b4c; "E2F748F9-DB8B-4C08-A258-583D8955D94A"
0x180024df7  call    memcmp_0
0x180024dfc  test    eax, eax
0x180024dfe  jnz     short loc_180024E41
0x180024e00  mov     esi, [rsp+0C8h+var_98]
0x180024e04  imul    rbx, rsi, 4Ch ; 'L'
0x180024e08  mov     r8d, [r15+18h]; Size
0x180024e0c  lea     rcx, [rbx+4]
0x180024e10  add     rcx, r12; void *
0x180024e13  lea     rdx, [r15+1Ch]; Src
0x180024e17  call    memcpy_0
0x180024e1c  mov     r8d, [r15+18h]; Size
0x180024e20  lea     rcx, [rbx+28h]
0x180024e24  add     rcx, r12; void *
0x180024e27  mov     edx, 0FFh; Val
0x180024e2c  call    memset_0
0x180024e31  mov     eax, [r15+18h]
0x180024e35  mov     [rbx+r12], eax
0x180024e39  inc     esi
0x180024e3b  mov     [rsp+0C8h+var_98], esi
0x180024e3f  jmp     short loc_180024E45
0x180024e41  mov     esi, [rsp+0C8h+var_98]
0x180024e45  mov     [rsp+0C8h+var_88], r13
0x180024e4a  lea     rcx, [rsp+0C8h+var_88]; this
0x180024e4f  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180024e54  mov     eax, [rsp+0C8h+var_90]
0x180024e58  inc     eax
0x180024e5a  jmp     loc_180024C2B
0x180024e5f  lea     r13, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180024e66  mov     [rsp+0C8h+var_88], r13
0x180024e6b  lea     rcx, [rsp+0C8h+var_88]; this
0x180024e70  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180024e75  mov     edi, [rsp+0C8h+var_94]
0x180024e79  mov     r12, [rsp+0C8h+var_48]
0x180024e81  mov     r15, [rsp+0C8h+var_58]
0x180024e86  mov     rcx, r12; void *
0x180024e89  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024e8e  nop
0x180024e8f  jmp     short loc_180024E9A
0x180024e91  mov     edi, [rsp+0C8h+var_94]
0x180024e95  mov     r15, [rsp+0C8h+var_58]
0x180024e9a  test    r15, r15
0x180024e9d  jz      short loc_180024ECA
0x180024e9f  jmp     short loc_180024EB6
0x180024ea1  mov     rax, [rsp+0C8h+arg_18]
0x180024ea9  mov     [rax], r12
0x180024eac  mov     rax, [rsp+0C8h+arg_20]
0x180024eb4  mov     [rax], esi
0x180024eb6  mov     edx, 40h ; '@'; unsigned __int64
0x180024ebb  mov     rcx, r15; void *
0x180024ebe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024ec3  nop
0x180024ec4  jmp     short loc_180024ECA
0x180024ec6  mov     edi, [rsp+0C8h+var_94]
0x180024eca  test    edi, edi
0x180024ecc  jnz     short loc_180024EE6
0x180024ece  add     rsp, 90h
0x180024ed5  pop     r15
0x180024ed7  pop     r14
0x180024ed9  pop     r13
0x180024edb  pop     r12
0x180024edd  pop     rdi
0x180024ede  pop     rsi
0x180024edf  pop     rbx
0x180024ee0  retn
0x180024ee1  mov     edi, 8010001Fh
0x180024ee6  mov     [rsp+0C8h+pExceptionObject], edi
0x180024eea  lea     rdx, _TI1K; pThrowInfo
0x180024ef1  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180024ef6  call    _CxxThrowException_0
```
