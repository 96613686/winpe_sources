# MdmBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)

- ea: `0x18001a560`
- end: `0x18001a8b7`
- name: `?_Encode@MdmBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z`
- size: `855`
- prototype: `__int64 __fastcall(MdmBase64Coder *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a388`

## callees

- `0x1800065c0`
- `0x18001a560`

## string_xrefs

- `0x18001a899`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmbase64coder.cpp`

## pseudocode

```c
__int64 __fastcall MdmBase64Coder::_Encode(
        unsigned __int64 this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int64 *a5)
{
  unsigned int v7; // ebx
  unsigned __int64 v8; // rdi
  __int64 v9; // rbx
  unsigned __int16 *v10; // r10
  const unsigned __int16 *v11; // rdx
  const unsigned __int8 *v12; // r13
  const unsigned __int8 *v13; // rsi
  unsigned __int16 *v14; // r15
  unsigned __int8 v15; // dl
  unsigned int v16; // r9d
  unsigned __int64 v17; // rax
  unsigned int v18; // r8d
  const unsigned __int8 *v19; // rbx
  unsigned __int16 *v20; // rcx
  unsigned __int64 v21; // rcx
  char v22; // r8
  unsigned __int16 *v23; // rcx

  if ( !a2 )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        this,
        0,
        -2147024809,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
        200,
        "CPR(pbBinaryData)");
    return v7;
  }
  if ( a3 )
  {
    if ( !a4 )
    {
      v7 = 0;
      *a5 = (4 * a3 / 3 + 3) & 0xFFFFFFFC;
      return v7;
    }
    v8 = *a5;
    if ( (*a5 & 3) != 1 )
      return (unsigned int)-2147024809;
    v9 = a3;
    if ( 3 * (v8 >> 2) < a3 )
      return (unsigned int)-2147024809;
    v10 = a4;
    LODWORD(v11) = a3 / 3;
    v12 = a2;
    v13 = &a2[a3 - (unsigned __int64)(a3 % 3)];
    if ( a2 < v13 )
    {
      v14 = &a4[v8];
      do
      {
        if ( v10 + 3 >= v14 )
          break;
        v15 = *v12;
        v16 = v12[2];
        v17 = *v12;
        v18 = v12[1];
        v12 += 3;
        *v10 = MdmBase64Coder::s_rgchBase64Digits[v17 >> 2];
        LOBYTE(v17) = 16 * v15;
        v11 = L"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/";
        v10[1] = MdmBase64Coder::s_rgchBase64Digits[((unsigned __int8)v17 | (unsigned __int8)((unsigned __int64)v18 >> 4))
                                                  & 0x3F];
        this = ((unsigned __int8)(4 * v18) | (unsigned __int8)((unsigned __int64)v16 >> 6)) & 0x3F;
        v10[2] = MdmBase64Coder::s_rgchBase64Digits[this];
        v10[3] = MdmBase64Coder::s_rgchBase64Digits[v16 & 0x3F];
        v10 += 4;
      }
      while ( v12 < v13 );
    }
    v19 = &a2[v9 - (_QWORD)v13 - 1];
    if ( v19 )
    {
      if ( v19 != (const unsigned __int8 *)1 )
        goto LABEL_25;
      v20 = &a4[v8];
      if ( v10 + 3 < v20 )
      {
        LODWORD(v11) = *v13;
        v21 = (unsigned __int64)v13[1] >> 4;
        v22 = v13[1] & 0xF;
        *v10 = MdmBase64Coder::s_rgchBase64Digits[(unsigned __int64)*v13 >> 2];
        v10[3] = 61;
        this = ((unsigned __int8)(16 * (_BYTE)v11) | (unsigned __int8)v21) & 0x3F;
        v10[1] = MdmBase64Coder::s_rgchBase64Digits[this];
        v10[2] = MdmBase64Coder::s_rgchBase64Digits[(unsigned __int8)(4 * v22)];
LABEL_24:
        v10 += 4;
LABEL_25:
        if ( v10 >= &a4[v8] )
        {
          v7 = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              this,
              (_DWORD)v11,
              -2147024809,
              "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
              30,
              "CBR(pch < pchEncodedData + cchEncodedData)");
        }
        else
        {
          *v10 = 0;
          return 0;
        }
        return v7;
      }
      v7 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v20,
          (_DWORD)v11,
          -2147024809,
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
          15,
          "CBR(pch + 3 < (pchEncodedData + cchEncodedData))");
    }
    else if ( v13 )
    {
      v23 = &a4[v8];
      if ( v10 + 3 < v23 )
      {
        LODWORD(this) = *v13;
        LOBYTE(this) = 16 * (this & 3);
        *v10 = MdmBase64Coder::s_rgchBase64Digits[(unsigned __int64)*v13 >> 2];
        *((_DWORD *)v10 + 1) = 3997757;
        v10[1] = MdmBase64Coder::s_rgchBase64Digits[(unsigned __int8)this];
        goto LABEL_24;
      }
      v7 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v23,
          (_DWORD)v11,
          -2147024809,
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
          248,
          "CBR(pch + 3 < (pchEncodedData + cchEncodedData))");
    }
    else
    {
      v7 = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          this,
          (_DWORD)v11,
          -2147418113,
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
          247,
          "CPR(pbEndOfTriplets)");
    }
  }
  else
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        this,
        (_DWORD)a2,
        -2147024809,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
        201,
        "CBR(cbBinaryData > 0)");
  }
  return v7;
}

```

## disassembly

```asm
0x18001a560  push    rbx
0x18001a562  push    rbp
0x18001a563  push    rsi
0x18001a564  push    rdi
0x18001a565  push    r13
0x18001a567  push    r14
0x18001a569  push    r15
0x18001a56b  sub     rsp, 30h
0x18001a56f  mov     r14, r9
0x18001a572  mov     rbp, rdx
0x18001a575  test    rdx, rdx
0x18001a578  jnz     short loc_18001A5AC
0x18001a57a  mov     r11b, 1
0x18001a57d  mov     r8d, 80070057h
0x18001a583  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a58a  mov     ebx, r8d
0x18001a58d  jz      loc_18001A8A5
0x18001a593  lea     rax, aCprPbbinarydat; "CPR(pbBinaryData)"
0x18001a59a  mov     [rsp+68h+var_40], rax
0x18001a59f  mov     [rsp+68h+var_48], 0C8h
0x18001a5a7  jmp     loc_18001A899
0x18001a5ac  test    r8d, r8d
0x18001a5af  jz      loc_18001A870
0x18001a5b5  test    r14, r14
0x18001a5b8  jnz     short loc_18001A5E8
0x18001a5ba  mov     eax, 0AAAAAAABh
0x18001a5bf  lea     ecx, ds:0[r8*4]
0x18001a5c7  mul     ecx
0x18001a5c9  mov     eax, 0FFFFFFFCh
0x18001a5ce  xor     ebx, ebx
0x18001a5d0  shr     edx, 1
0x18001a5d2  add     edx, 3
0x18001a5d5  and     rdx, rax
0x18001a5d8  mov     rax, [rsp+68h+arg_20]
0x18001a5e0  mov     [rax], rdx
0x18001a5e3  jmp     loc_18001A8A5
0x18001a5e8  mov     rax, [rsp+68h+arg_20]
0x18001a5f0  mov     r11b, 1
0x18001a5f3  mov     rdi, [rax]
0x18001a5f6  mov     al, dil
0x18001a5f9  and     al, 3
0x18001a5fb  cmp     al, r11b
0x18001a5fe  jnz     loc_18001A869
0x18001a604  mov     rax, rdi
0x18001a607  mov     ebx, r8d
0x18001a60a  shr     rax, 2
0x18001a60e  lea     rax, [rax+rax*2]
0x18001a612  cmp     rax, rbx
0x18001a615  jb      loc_18001A869
0x18001a61b  mov     eax, 0AAAAAAABh
0x18001a620  lea     r9, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a627  mul     r8d
0x18001a62a  mov     esi, ebx
0x18001a62c  mov     r10, r14
0x18001a62f  shr     edx, 1
0x18001a631  mov     r13, rbp
0x18001a634  lea     eax, [rdx+rdx*2]
0x18001a637  sub     r8d, eax
0x18001a63a  mov     eax, r8d
0x18001a63d  sub     rsi, rax
0x18001a640  add     rsi, rbp
0x18001a643  cmp     rbp, rsi
0x18001a646  jnb     loc_18001A6E7
0x18001a64c  lea     r15, [r14+rdi*2]
0x18001a650  lea     rax, [r10+6]
0x18001a654  cmp     rax, r15
0x18001a657  jnb     loc_18001A6E7
0x18001a65d  movzx   edx, byte ptr [r13+0]
0x18001a662  lea     rcx, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a669  movzx   r9d, byte ptr [r13+2]
0x18001a66e  mov     eax, edx
0x18001a670  movzx   r8d, byte ptr [r13+1]
0x18001a675  add     r13, 3
0x18001a679  shr     rax, 2
0x18001a67d  movzx   eax, word ptr [rcx+rax*2]
0x18001a681  mov     ecx, r8d
0x18001a684  mov     [r10], ax
0x18001a688  mov     al, dl
0x18001a68a  shl     al, 4
0x18001a68d  lea     rdx, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a694  shr     rcx, 4
0x18001a698  or      rcx, rax
0x18001a69b  and     ecx, 3Fh
0x18001a69e  movzx   eax, word ptr [rdx+rcx*2]
0x18001a6a2  mov     ecx, r9d
0x18001a6a5  mov     [r10+2], ax
0x18001a6aa  mov     al, r8b
0x18001a6ad  shl     al, 2
0x18001a6b0  shr     rcx, 6
0x18001a6b4  or      rcx, rax
0x18001a6b7  and     ecx, 3Fh
0x18001a6ba  movzx   eax, word ptr [rdx+rcx*2]
0x18001a6be  mov     [r10+4], ax
0x18001a6c3  mov     eax, r9d
0x18001a6c6  and     eax, 3Fh
0x18001a6c9  lea     r9, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a6d0  movzx   eax, word ptr [r9+rax*2]
0x18001a6d5  mov     [r10+6], ax
0x18001a6da  add     r10, 8
0x18001a6de  cmp     r13, rsi
0x18001a6e1  jb      loc_18001A650
0x18001a6e7  sub     rbx, rsi
0x18001a6ea  add     rbx, rbp
0x18001a6ed  sub     rbx, 1
0x18001a6f1  jz      loc_18001A792
0x18001a6f7  cmp     rbx, 1
0x18001a6fb  jnz     loc_18001A803
0x18001a701  lea     rcx, [r14+rdi*2]
0x18001a705  lea     rax, [r10+6]
0x18001a709  cmp     rax, rcx
0x18001a70c  jnb     short loc_18001A763
0x18001a70e  movzx   edx, byte ptr [rsi]
0x18001a711  movzx   r8d, byte ptr [rsi+1]
0x18001a716  mov     eax, edx
0x18001a718  shr     rax, 2
0x18001a71c  mov     ecx, r8d
0x18001a71f  shr     rcx, 4
0x18001a723  and     r8b, 0Fh
0x18001a727  movzx   eax, word ptr [r9+rax*2]
0x18001a72c  mov     [r10], ax
0x18001a730  mov     al, dl
0x18001a732  shl     al, 4
0x18001a735  or      rcx, rax
0x18001a738  mov     word ptr [r10+6], 3Dh ; '='
0x18001a73f  and     ecx, 3Fh
0x18001a742  shl     r8b, 2
0x18001a746  movzx   eax, word ptr [r9+rcx*2]
0x18001a74b  mov     [r10+2], ax
0x18001a750  movzx   eax, r8b
0x18001a754  movzx   eax, word ptr [r9+rax*2]
0x18001a759  mov     [r10+4], ax
0x18001a75e  jmp     loc_18001A7FF
0x18001a763  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a76a  mov     r8d, 80070057h
0x18001a770  mov     ebx, r8d
0x18001a773  jz      loc_18001A8A5
0x18001a779  lea     rax, aCbrPch3Pchenco; "CBR(pch + 3 < (pchEncodedData + cchEnco"...
0x18001a780  mov     [rsp+68h+var_40], rax
0x18001a785  mov     [rsp+68h+var_48], 10Fh
0x18001a78d  jmp     loc_18001A899
0x18001a792  test    rsi, rsi
0x18001a795  jnz     short loc_18001A7C5
0x18001a797  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a79e  mov     ebx, 8000FFFFh
0x18001a7a3  jz      loc_18001A8A5
0x18001a7a9  lea     rax, aCprPbendoftrip; "CPR(pbEndOfTriplets)"
0x18001a7b0  mov     r8d, ebx
0x18001a7b3  mov     [rsp+68h+var_40], rax
0x18001a7b8  mov     [rsp+68h+var_48], 0F7h
0x18001a7c0  jmp     loc_18001A899
0x18001a7c5  lea     rcx, [r14+rdi*2]
0x18001a7c9  lea     rax, [r10+6]
0x18001a7cd  cmp     rax, rcx
0x18001a7d0  jnb     short loc_18001A841
0x18001a7d2  movzx   ecx, byte ptr [rsi]
0x18001a7d5  mov     eax, ecx
0x18001a7d7  and     cl, 3
0x18001a7da  shr     rax, 2
0x18001a7de  shl     cl, 4
0x18001a7e1  movzx   eax, word ptr [r9+rax*2]
0x18001a7e6  mov     [r10], ax
0x18001a7ea  movzx   eax, cl
0x18001a7ed  mov     dword ptr [r10+4], 3D003Dh
0x18001a7f5  movzx   eax, word ptr [r9+rax*2]
0x18001a7fa  mov     [r10+2], ax
0x18001a7ff  add     r10, 8
0x18001a803  lea     rax, [r14+rdi*2]
0x18001a807  cmp     r10, rax
0x18001a80a  jnb     short loc_18001A819
0x18001a80c  xor     eax, eax
0x18001a80e  mov     [r10], ax
0x18001a812  xor     ebx, ebx
0x18001a814  jmp     loc_18001A8A5
0x18001a819  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a820  mov     r8d, 80070057h
0x18001a826  mov     ebx, r8d
0x18001a829  jz      short loc_18001A8A5
0x18001a82b  lea     rax, aCbrPchPchencod; "CBR(pch < pchEncodedData + cchEncodedDa"...
0x18001a832  mov     [rsp+68h+var_40], rax
0x18001a837  mov     [rsp+68h+var_48], 11Eh
0x18001a83f  jmp     short loc_18001A899
0x18001a841  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a848  mov     r8d, 80070057h
0x18001a84e  mov     ebx, r8d
0x18001a851  jz      short loc_18001A8A5
0x18001a853  lea     rax, aCbrPch3Pchenco; "CBR(pch + 3 < (pchEncodedData + cchEnco"...
0x18001a85a  mov     [rsp+68h+var_40], rax
0x18001a85f  mov     [rsp+68h+var_48], 0F8h
0x18001a867  jmp     short loc_18001A899
0x18001a869  mov     ebx, 80070057h
0x18001a86e  jmp     short loc_18001A8A5
0x18001a870  mov     r11b, 1
0x18001a873  mov     r8d, 80070057h
0x18001a879  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a880  mov     ebx, r8d
0x18001a883  jz      short loc_18001A8A5
0x18001a885  lea     rax, aCbrCbbinarydat; "CBR(cbBinaryData > 0)"
0x18001a88c  mov     [rsp+68h+var_40], rax
0x18001a891  mov     [rsp+68h+var_48], 0C9h
0x18001a899  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a8a0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a8a5  mov     eax, ebx
0x18001a8a7  add     rsp, 30h
0x18001a8ab  pop     r15
0x18001a8ad  pop     r14
0x18001a8af  pop     r13
0x18001a8b1  pop     rdi
0x18001a8b2  pop     rsi
0x18001a8b3  pop     rbp
0x18001a8b4  pop     rbx
0x18001a8b5  retn
```
