# XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)

- ea: `0x180012a4c`
- end: `0x180012bc0`
- name: `?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z`
- size: `372`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c4a0`
- `0x18000cf80`

## callees

- `0x180012a4c`
- `0x180012db0`
- `0x1800133f8`
- `0x180013458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012acc`
- `OLEAUT32!__imp_VariantInit` at `0x180012a65`
- `OLEAUT32!__imp_VariantInit` at `0x180012a65`
- `OLEAUT32!__imp_VariantClear` at `0x180012bad`
- `OLEAUT32!__imp_VariantClear` at `0x180012bad`

## pseudocode

```c
__int64 __fastcall XcGetNodeHexBinaryValue(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  unsigned int NodeTypedValue; // eax
  DWORD LastError; // ebx
  unsigned __int64 v9; // rdi
  unsigned __int8 *v10; // r9
  unsigned int v11; // r10d
  unsigned int v12; // edx
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rcx
  char v16; // cl
  char v17; // cl
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF

  VariantInit(&pvarg);
  NodeTypedValue = XcGetNodeTypedValue(a1, L".", &pvarg);
  LastError = NodeTypedValue;
  if ( NodeTypedValue == 1168 )
    goto LABEL_6;
  if ( !NodeTypedValue )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(pvarg.llVal + 2 * v9) );
    if ( v9 > 0xFFFFFFFF )
    {
LABEL_6:
      LastError = 1206;
      goto LABEL_31;
    }
    v10 = (unsigned __int8 *)Xc_Process_user_allocate((v9 + 1) >> 1);
    if ( v10 )
    {
      v11 = 0;
      v12 = 0;
      if ( !v9 )
        goto LABEL_30;
      do
      {
        v13 = *(unsigned __int16 *)(pvarg.llVal + 2LL * v11);
        if ( (unsigned int)v13 > 0x20 || (v14 = 0x100002600LL, !_bittest64(&v14, v13)) )
        {
          if ( (unsigned __int16)(v13 - 48) > 0x36u )
            goto LABEL_30;
          v15 = 0x7E0000007E03FFLL;
          if ( !_bittest64(&v15, (unsigned int)(v13 - 48)) )
            goto LABEL_30;
          if ( (v12 & 1) != 0 )
          {
            if ( (unsigned int)v13 > 0x39 )
            {
              v17 = v13 - 55;
              if ( (unsigned int)v13 > 0x46 )
                v17 = v13 - 87;
            }
            else
            {
              v17 = v13 - 48;
            }
            v10[(unsigned __int64)v12 >> 1] |= v17;
          }
          else
          {
            if ( (unsigned int)v13 > 0x39 )
            {
              v16 = v13 - 55;
              if ( (unsigned int)v13 > 0x46 )
                v16 = v13 - 87;
            }
            else
            {
              v16 = v13 - 48;
            }
            v10[(unsigned __int64)v12 >> 1] = 16 * v16;
          }
          ++v12;
        }
        ++v11;
      }
      while ( v11 < v9 );
      if ( v12 && (v12 & 1) == 0 )
      {
        *a3 = v10;
        *a4 = v12 >> 1;
      }
      else
      {
LABEL_30:
        LastError = 1206;
        Xc_Process_user_free(v10);
      }
    }
    else
    {
      LastError = GetLastError();
    }
  }
LABEL_31:
  VariantClear(&pvarg);
  return LastError;
}

```

## disassembly

```asm
0x180012a4c  push    rbx
0x180012a4e  push    rbp
0x180012a4f  push    rsi
0x180012a50  push    rdi
0x180012a51  push    r14
0x180012a53  sub     rsp, 40h
0x180012a57  mov     rbx, rcx
0x180012a5a  mov     rsi, r9
0x180012a5d  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180012a62  mov     r14, r8
0x180012a65  call    cs:__imp_VariantInit
0x180012a6b  lea     r8, [rsp+68h+pvarg]; struct tagVARIANT *
0x180012a70  mov     rcx, rbx; struct IXMLDOMNode *
0x180012a73  lea     rdx, asc_18001646C; "."
0x180012a7a  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x180012a7f  mov     ebx, eax
0x180012a81  cmp     eax, 490h
0x180012a86  jz      short loc_180012AAE
0x180012a88  xor     ebp, ebp
0x180012a8a  test    eax, eax
0x180012a8c  jnz     loc_180012BA8
0x180012a92  mov     rax, qword ptr [rsp+68h+pvarg+8]
0x180012a97  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180012a9b  inc     rdi
0x180012a9e  cmp     [rax+rdi*2], bp
0x180012aa2  jnz     short loc_180012A9B
0x180012aa4  mov     eax, 0FFFFFFFFh
0x180012aa9  cmp     rdi, rax
0x180012aac  jbe     short loc_180012AB8
0x180012aae  mov     ebx, 4B6h
0x180012ab3  jmp     loc_180012BA8
0x180012ab8  lea     rcx, [rdi+1]
0x180012abc  shr     rcx, 1; dwBytes
0x180012abf  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180012ac4  mov     r9, rax
0x180012ac7  test    rax, rax
0x180012aca  jnz     short loc_180012AD9
0x180012acc  call    cs:__imp_GetLastError
0x180012ad2  mov     ebx, eax
0x180012ad4  jmp     loc_180012BA8
0x180012ad9  mov     r10d, ebp
0x180012adc  mov     edx, ebp
0x180012ade  test    rdi, rdi
0x180012ae1  jz      loc_180012B9B
0x180012ae7  mov     rax, qword ptr [rsp+68h+pvarg+8]
0x180012aec  mov     ecx, r10d
0x180012aef  movzx   r8d, word ptr [rax+rcx*2]
0x180012af4  cmp     r8d, 20h ; ' '
0x180012af8  ja      short loc_180012B0A
0x180012afa  mov     rcx, 100002600h
0x180012b04  bt      rcx, r8
0x180012b08  jb      short loc_180012B7A
0x180012b0a  lea     eax, [r8-30h]
0x180012b0e  cmp     ax, 36h ; '6'
0x180012b12  ja      loc_180012B9B
0x180012b18  mov     rcx, 7E0000007E03FFh
0x180012b22  bt      rcx, rax
0x180012b26  jnb     short loc_180012B9B
0x180012b28  test    dl, 1
0x180012b2b  jnz     short loc_180012B55
0x180012b2d  cmp     r8d, 39h ; '9'
0x180012b31  ja      short loc_180012B39
0x180012b33  lea     ecx, [r8-30h]
0x180012b37  jmp     short loc_180012B47
0x180012b39  lea     ecx, [r8-37h]
0x180012b3d  cmp     r8d, 46h ; 'F'
0x180012b41  jbe     short loc_180012B47
0x180012b43  lea     ecx, [r8-57h]
0x180012b47  shl     cl, 4
0x180012b4a  mov     eax, edx
0x180012b4c  shr     rax, 1
0x180012b4f  mov     [rax+r9], cl
0x180012b53  jmp     short loc_180012B78
0x180012b55  cmp     r8d, 39h ; '9'
0x180012b59  ja      short loc_180012B61
0x180012b5b  lea     ecx, [r8-30h]
0x180012b5f  jmp     short loc_180012B6F
0x180012b61  lea     ecx, [r8-37h]
0x180012b65  cmp     r8d, 46h ; 'F'
0x180012b69  jbe     short loc_180012B6F
0x180012b6b  lea     ecx, [r8-57h]
0x180012b6f  mov     eax, edx
0x180012b71  shr     rax, 1
0x180012b74  or      [rax+r9], cl
0x180012b78  inc     edx
0x180012b7a  inc     r10d
0x180012b7d  mov     eax, r10d
0x180012b80  cmp     rax, rdi
0x180012b83  jb      loc_180012AE7
0x180012b89  test    edx, edx
0x180012b8b  jz      short loc_180012B9B
0x180012b8d  test    dl, 1
0x180012b90  jnz     short loc_180012B9B
0x180012b92  shr     edx, 1
0x180012b94  mov     [r14], r9
0x180012b97  mov     [rsi], edx
0x180012b99  jmp     short loc_180012BA8
0x180012b9b  mov     rcx, r9; lpMem
0x180012b9e  mov     ebx, 4B6h
0x180012ba3  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x180012ba8  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180012bad  call    cs:__imp_VariantClear
0x180012bb3  mov     eax, ebx
0x180012bb5  add     rsp, 40h
0x180012bb9  pop     r14
0x180012bbb  pop     rdi
0x180012bbc  pop     rsi
0x180012bbd  pop     rbp
0x180012bbe  pop     rbx
0x180012bbf  retn
```
