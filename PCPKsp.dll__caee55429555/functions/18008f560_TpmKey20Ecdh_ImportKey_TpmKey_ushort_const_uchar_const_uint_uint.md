# TpmKey20Ecdh::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)

- ea: `0x18008f560`
- end: `0x18008f7d4`
- name: `?ImportKey@TpmKey20Ecdh@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z`
- size: `628`
- prototype: `__int64 __usercall@<rax>(TpmKey20Ecdh *__hidden this@<rcx>, struct TpmKey *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int8 *@<r9>, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008f310`

## callees

- `0x18000dc90`
- `0x180015660`
- `0x1800157c0`
- `0x18008e850`
- `0x18008f560`
- `0x1800c2ce0`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18008f764`
- `bcrypt!BCryptImportKeyPair` at `0x18008f764`
- `bcrypt!BCryptDestroyKey` at `0x18008f72a`
- `bcrypt!BCryptDestroyKey` at `0x18008f72a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008f6c1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008f6c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TpmKey20Ecdh::ImportKey(
        TpmKey20Ecdh *this,
        struct TpmKey *a2,
        const unsigned __int16 *a3,
        UCHAR *a4,
        ULONG cbInput,
        unsigned int a6)
{
  int KeyInTpm; // ebx
  NTSTATUS v10; // eax
  void *v11; // rcx
  NTSTATUS v12; // eax
  PUCHAR pbInput; // [rsp+20h] [rbp-48h]
  int v15; // [rsp+40h] [rbp-28h] BYREF
  int *v16[4]; // [rsp+48h] [rbp-20h] BYREF

  v15 = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v16, L"TpmKey20Ecdh::ImportKey", &v15);
  if ( (a6 & 0xFFFFEFF7) != 0 )
  {
    KeyInTpm = -2144795644;
LABEL_36:
    v15 = KeyInTpm;
    goto LABEL_37;
  }
  if ( !wcscmp_0(a3, L"ECCPUBLICBLOB") || !wcscmp_0(a3, L"ECCFULLPUBLICBLOB") )
  {
    if ( *((_DWORD *)this + 116) || *((_QWORD *)this + 12) )
    {
      KeyInTpm = -2144795628;
      goto LABEL_36;
    }
    if ( !*((_QWORD *)this + 129) )
    {
      v10 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 129, L"ECDH", L"Microsoft Primitive Provider", 0);
      if ( v10 )
      {
        if ( (v10 & 0xFFFF000) == 0x290000 )
        {
          KeyInTpm = v10 & 0xFFF | 0x80280000;
        }
        else if ( (v10 & 0xFFF0000) == 0x70000 )
        {
          KeyInTpm = (unsigned __int16)v10;
          if ( (_WORD)v10 )
            KeyInTpm = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          KeyInTpm = v10 | 0x10000000;
        }
        v15 = KeyInTpm;
        if ( KeyInTpm < 0 )
          goto LABEL_37;
      }
      else
      {
        v15 = 0;
      }
    }
    v11 = (void *)*((_QWORD *)this + 130);
    if ( v11 )
    {
      BCryptDestroyKey(v11);
      *((_QWORD *)this + 130) = 0;
    }
    v12 = BCryptImportKeyPair(
            *((BCRYPT_ALG_HANDLE *)this + 129),
            0,
            a3,
            (BCRYPT_KEY_HANDLE *)this + 130,
            a4,
            cbInput,
            0);
    KeyInTpm = v12;
    if ( v12 )
    {
      if ( (v12 & 0xFFFF000) == 0x290000 )
      {
        KeyInTpm = v12 & 0xFFF | 0x80280000;
      }
      else if ( (v12 & 0xFFF0000) == 0x70000 )
      {
        KeyInTpm = (unsigned __int16)v12;
        if ( (_WORD)v12 )
          KeyInTpm = (unsigned __int16)v12 | 0x80070000;
      }
      else
      {
        KeyInTpm = v12 | 0x10000000;
      }
    }
    goto LABEL_36;
  }
  if ( wcscmp_0(a3, L"OpaqueKeyBlob")
    && wcscmp_0(a3, L"PcpTpmProtectedKeyBlob")
    && wcscmp_0(a3, L"ECCFULLPRIVATEBLOB")
    && wcscmp_0(a3, L"ECCPRIVATEBLOB")
    && wcscmp_0(a3, L"PcpTpmPersistentKeyBlob") )
  {
    KeyInTpm = -2144795643;
    goto LABEL_36;
  }
  LODWORD(pbInput) = cbInput;
  KeyInTpm = TpmKey20Ecc::ImportKey(this, 0, a3, a4, (rsize_t)pbInput, a6);
  v15 = KeyInTpm;
  if ( KeyInTpm >= 0 && (a6 & 8) == 0 )
  {
    KeyInTpm = TpmKey20::LoadKeyInTpm(this);
    v15 = KeyInTpm;
  }
LABEL_37:
  KspFunctionLogger::~KspFunctionLogger(v16);
  return (unsigned int)KeyInTpm;
}

```

## disassembly

```asm
0x18008f560  push    rbp
0x18008f562  push    rbx
0x18008f563  push    rsi
0x18008f564  push    rdi
0x18008f565  push    r14
0x18008f567  push    r15
0x18008f569  mov     rbp, rsp
0x18008f56c  sub     rsp, 68h
0x18008f570  mov     r15, r9
0x18008f573  mov     rdi, r8
0x18008f576  mov     rsi, rcx
0x18008f579  mov     [rbp+var_28], 0
0x18008f580  lea     r8, [rbp+var_28]; int *
0x18008f584  lea     rdx, aTpmkey20ecdhIm; "TpmKey20Ecdh::ImportKey"
0x18008f58b  lea     rcx, [rbp+var_20]; this
0x18008f58f  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18008f594  nop
0x18008f595  mov     r14d, [rbp+arg_28]
0x18008f599  test    r14d, 0FFFFEFF7h
0x18008f5a0  jz      short loc_18008F5AC
0x18008f5a2  mov     ebx, 80290404h
0x18008f5a7  jmp     loc_18008F7B8
0x18008f5ac  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x18008f5b3  mov     rcx, rdi; String1
0x18008f5b6  call    wcscmp_0
0x18008f5bb  test    eax, eax
0x18008f5bd  jz      loc_18008F688
0x18008f5c3  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x18008f5ca  mov     rcx, rdi; String1
0x18008f5cd  call    wcscmp_0
0x18008f5d2  test    eax, eax
0x18008f5d4  jz      loc_18008F688
0x18008f5da  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18008f5e1  mov     rcx, rdi; String1
0x18008f5e4  call    wcscmp_0
0x18008f5e9  test    eax, eax
0x18008f5eb  jz      short loc_18008F643
0x18008f5ed  lea     rdx, aPcptpmprotecte; "PcpTpmProtectedKeyBlob"
0x18008f5f4  mov     rcx, rdi; String1
0x18008f5f7  call    wcscmp_0
0x18008f5fc  test    eax, eax
0x18008f5fe  jz      short loc_18008F643
0x18008f600  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x18008f607  mov     rcx, rdi; String1
0x18008f60a  call    wcscmp_0
0x18008f60f  test    eax, eax
0x18008f611  jz      short loc_18008F643
0x18008f613  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x18008f61a  mov     rcx, rdi; String1
0x18008f61d  call    wcscmp_0
0x18008f622  test    eax, eax
0x18008f624  jz      short loc_18008F643
0x18008f626  lea     rdx, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x18008f62d  mov     rcx, rdi; String1
0x18008f630  call    wcscmp_0
0x18008f635  test    eax, eax
0x18008f637  jz      short loc_18008F643
0x18008f639  mov     ebx, 80290405h
0x18008f63e  jmp     loc_18008F7B8
0x18008f643  mov     [rsp+68h+cbInput], r14d; unsigned int
0x18008f648  mov     eax, [rbp+arg_20]
0x18008f64b  mov     dword ptr [rsp+68h+pbInput], eax; DestinationSize
0x18008f64f  mov     r9, r15; unsigned __int8 *
0x18008f652  mov     r8, rdi; unsigned __int16 *
0x18008f655  xor     edx, edx; struct TpmKey *
0x18008f657  mov     rcx, rsi; this
0x18008f65a  call    ?ImportKey@TpmKey20Ecc@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z; TpmKey20Ecc::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)
0x18008f65f  mov     ebx, eax
0x18008f661  mov     [rbp+var_28], eax
0x18008f664  test    eax, eax
0x18008f666  js      loc_18008F7BB
0x18008f66c  test    r14b, 8
0x18008f670  jnz     loc_18008F7BB
0x18008f676  mov     rcx, rsi; this
0x18008f679  call    ?LoadKeyInTpm@TpmKey20@@IEAAJXZ; TpmKey20::LoadKeyInTpm(void)
0x18008f67e  mov     ebx, eax
0x18008f680  mov     [rbp+var_28], eax
0x18008f683  jmp     loc_18008F7BB
0x18008f688  cmp     dword ptr [rsi+1D0h], 0
0x18008f68f  jnz     loc_18008F7B3
0x18008f695  cmp     qword ptr [rsi+60h], 0
0x18008f69a  jnz     loc_18008F7B3
0x18008f6a0  lea     r14, [rsi+408h]
0x18008f6a7  cmp     qword ptr [r14], 0
0x18008f6ab  jnz     short loc_18008F71E
0x18008f6ad  xor     r9d, r9d; dwFlags
0x18008f6b0  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18008f6b7  lea     rdx, aEcdh; "ECDH"
0x18008f6be  mov     rcx, r14; phAlgorithm
0x18008f6c1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008f6c8  nop     dword ptr [rax+rax+00h]
0x18008f6cd  mov     ebx, eax
0x18008f6cf  test    eax, eax
0x18008f6d1  jnz     short loc_18008F6D8
0x18008f6d3  mov     [rbp+var_28], eax
0x18008f6d6  jmp     short loc_18008F71E
0x18008f6d8  and     eax, 0FFFF000h
0x18008f6dd  cmp     eax, 290000h
0x18008f6e2  jnz     short loc_18008F6F2
0x18008f6e4  and     ebx, 0FFFh
0x18008f6ea  or      ebx, 80280000h
0x18008f6f0  jmp     short loc_18008F713
0x18008f6f2  mov     eax, ebx
0x18008f6f4  and     eax, 0FFF0000h
0x18008f6f9  cmp     eax, 70000h
0x18008f6fe  jnz     short loc_18008F70F
0x18008f700  movzx   ebx, bx
0x18008f703  test    ebx, ebx
0x18008f705  jz      short loc_18008F713
0x18008f707  or      ebx, 80070000h
0x18008f70d  jmp     short loc_18008F713
0x18008f70f  bts     ebx, 1Ch
0x18008f713  mov     [rbp+var_28], ebx
0x18008f716  test    ebx, ebx
0x18008f718  js      loc_18008F7BB
0x18008f71e  mov     rcx, [rsi+410h]; hKey
0x18008f725  test    rcx, rcx
0x18008f728  jz      short loc_18008F741
0x18008f72a  call    cs:__imp_BCryptDestroyKey
0x18008f731  nop     dword ptr [rax+rax+00h]
0x18008f736  mov     qword ptr [rsi+410h], 0
0x18008f741  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18008f749  mov     eax, [rbp+arg_20]
0x18008f74c  mov     [rsp+68h+cbInput], eax; cbInput
0x18008f750  mov     [rsp+68h+pbInput], r15; pbInput
0x18008f755  lea     r9, [rsi+410h]; phKey
0x18008f75c  mov     r8, rdi; pszBlobType
0x18008f75f  xor     edx, edx; hImportKey
0x18008f761  mov     rcx, [r14]; hAlgorithm
0x18008f764  call    cs:__imp_BCryptImportKeyPair
0x18008f76b  nop     dword ptr [rax+rax+00h]
0x18008f770  mov     ebx, eax
0x18008f772  test    eax, eax
0x18008f774  jz      short loc_18008F7B8
0x18008f776  and     eax, 0FFFF000h
0x18008f77b  cmp     eax, 290000h
0x18008f780  jnz     short loc_18008F790
0x18008f782  and     ebx, 0FFFh
0x18008f788  or      ebx, 80280000h
0x18008f78e  jmp     short loc_18008F7B8
0x18008f790  mov     eax, ebx
0x18008f792  and     eax, 0FFF0000h
0x18008f797  cmp     eax, 70000h
0x18008f79c  jnz     short loc_18008F7AD
0x18008f79e  movzx   ebx, bx
0x18008f7a1  test    ebx, ebx
0x18008f7a3  jz      short loc_18008F7B8
0x18008f7a5  or      ebx, 80070000h
0x18008f7ab  jmp     short loc_18008F7B8
0x18008f7ad  bts     ebx, 1Ch
0x18008f7b1  jmp     short loc_18008F7B8
0x18008f7b3  mov     ebx, 80290414h
0x18008f7b8  mov     [rbp+var_28], ebx
0x18008f7bb  lea     rcx, [rbp+var_20]; this
0x18008f7bf  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18008f7c4  mov     eax, ebx
0x18008f7c6  add     rsp, 68h
0x18008f7ca  pop     r15
0x18008f7cc  pop     r14
0x18008f7ce  pop     rdi
0x18008f7cf  pop     rsi
0x18008f7d0  pop     rbx
0x18008f7d1  pop     rbp
0x18008f7d2  retn
```
