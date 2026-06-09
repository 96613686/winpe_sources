# MdmBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)

- ea: `0x18001a040`
- end: `0x18001a396`
- name: `?_Encode@MdmBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z`
- size: `854`
- prototype: `__int64 __fastcall(unsigned __int64 this, const unsigned __int8 *, unsigned int, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019e74`

## callees

- `0x180006548`
- `0x18001a040`

## string_xrefs

- `0x18001a379`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmbase64coder.cpp`

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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
        200,
        (__int64)"CPR(pbBinaryData)");
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
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
              30,
              (__int64)"CBR(pch < pchEncodedData + cchEncodedData)");
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
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
          15,
          (__int64)"CBR(pch + 3 < (pchEncodedData + cchEncodedData))");
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
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
          248,
          (__int64)"CBR(pch + 3 < (pchEncodedData + cchEncodedData))");
    }
    else
    {
      v7 = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          this,
          (_DWORD)v11,
          -2147418113,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
          247,
          (__int64)"CPR(pbEndOfTriplets)");
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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
        201,
        (__int64)"CBR(cbBinaryData > 0)");
  }
  return v7;
}

```

## disassembly

```asm
0x18001a040  push    rbx
0x18001a042  push    rbp
0x18001a043  push    rsi
0x18001a044  push    rdi
0x18001a045  push    r13
0x18001a047  push    r14
0x18001a049  push    r15
0x18001a04b  sub     rsp, 30h
0x18001a04f  mov     r14, r9
0x18001a052  mov     rbp, rdx
0x18001a055  test    rdx, rdx
0x18001a058  jnz     short loc_18001A08C
0x18001a05a  mov     r11b, 1
0x18001a05d  mov     r8d, 80070057h
0x18001a063  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a06a  mov     ebx, r8d
0x18001a06d  jz      loc_18001A385
0x18001a073  lea     rax, aCprPbbinarydat; "CPR(pbBinaryData)"
0x18001a07a  mov     [rsp+68h+var_40], rax
0x18001a07f  mov     [rsp+68h+var_48], 0C8h
0x18001a087  jmp     loc_18001A379
0x18001a08c  test    r8d, r8d
0x18001a08f  jz      loc_18001A350
0x18001a095  test    r14, r14
0x18001a098  jnz     short loc_18001A0C8
0x18001a09a  mov     eax, 0AAAAAAABh
0x18001a09f  lea     ecx, ds:0[r8*4]
0x18001a0a7  mul     ecx
0x18001a0a9  mov     eax, 0FFFFFFFCh
0x18001a0ae  xor     ebx, ebx
0x18001a0b0  shr     edx, 1
0x18001a0b2  add     edx, 3
0x18001a0b5  and     rdx, rax
0x18001a0b8  mov     rax, [rsp+68h+arg_20]
0x18001a0c0  mov     [rax], rdx
0x18001a0c3  jmp     loc_18001A385
0x18001a0c8  mov     rax, [rsp+68h+arg_20]
0x18001a0d0  mov     r11b, 1
0x18001a0d3  mov     rdi, [rax]
0x18001a0d6  mov     al, dil
0x18001a0d9  and     al, 3
0x18001a0db  cmp     al, r11b
0x18001a0de  jnz     loc_18001A349
0x18001a0e4  mov     rax, rdi
0x18001a0e7  mov     ebx, r8d
0x18001a0ea  shr     rax, 2
0x18001a0ee  lea     rax, [rax+rax*2]
0x18001a0f2  cmp     rax, rbx
0x18001a0f5  jb      loc_18001A349
0x18001a0fb  mov     eax, 0AAAAAAABh
0x18001a100  lea     r9, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a107  mul     r8d
0x18001a10a  mov     esi, ebx
0x18001a10c  mov     r10, r14
0x18001a10f  shr     edx, 1
0x18001a111  mov     r13, rbp
0x18001a114  lea     eax, [rdx+rdx*2]
0x18001a117  sub     r8d, eax
0x18001a11a  mov     eax, r8d
0x18001a11d  sub     rsi, rax
0x18001a120  add     rsi, rbp
0x18001a123  cmp     rbp, rsi
0x18001a126  jnb     loc_18001A1C7
0x18001a12c  lea     r15, [r14+rdi*2]
0x18001a130  lea     rax, [r10+6]
0x18001a134  cmp     rax, r15
0x18001a137  jnb     loc_18001A1C7
0x18001a13d  movzx   edx, byte ptr [r13+0]
0x18001a142  lea     rcx, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a149  movzx   r9d, byte ptr [r13+2]
0x18001a14e  mov     eax, edx
0x18001a150  movzx   r8d, byte ptr [r13+1]
0x18001a155  add     r13, 3
0x18001a159  shr     rax, 2
0x18001a15d  movzx   eax, word ptr [rcx+rax*2]
0x18001a161  mov     ecx, r8d
0x18001a164  mov     [r10], ax
0x18001a168  mov     al, dl
0x18001a16a  shl     al, 4
0x18001a16d  lea     rdx, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a174  shr     rcx, 4
0x18001a178  or      rcx, rax
0x18001a17b  and     ecx, 3Fh
0x18001a17e  movzx   eax, word ptr [rdx+rcx*2]
0x18001a182  mov     ecx, r9d
0x18001a185  mov     [r10+2], ax
0x18001a18a  mov     al, r8b
0x18001a18d  shl     al, 2
0x18001a190  shr     rcx, 6
0x18001a194  or      rcx, rax
0x18001a197  and     ecx, 3Fh
0x18001a19a  movzx   eax, word ptr [rdx+rcx*2]
0x18001a19e  mov     [r10+4], ax
0x18001a1a3  mov     eax, r9d
0x18001a1a6  and     eax, 3Fh
0x18001a1a9  lea     r9, ?s_rgchBase64Digits@MdmBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18001a1b0  movzx   eax, word ptr [r9+rax*2]
0x18001a1b5  mov     [r10+6], ax
0x18001a1ba  add     r10, 8
0x18001a1be  cmp     r13, rsi
0x18001a1c1  jb      loc_18001A130
0x18001a1c7  sub     rbx, rsi
0x18001a1ca  add     rbx, rbp
0x18001a1cd  sub     rbx, 1
0x18001a1d1  jz      loc_18001A272
0x18001a1d7  cmp     rbx, 1
0x18001a1db  jnz     loc_18001A2E3
0x18001a1e1  lea     rcx, [r14+rdi*2]
0x18001a1e5  lea     rax, [r10+6]
0x18001a1e9  cmp     rax, rcx
0x18001a1ec  jnb     short loc_18001A243
0x18001a1ee  movzx   edx, byte ptr [rsi]
0x18001a1f1  movzx   r8d, byte ptr [rsi+1]
0x18001a1f6  mov     eax, edx
0x18001a1f8  shr     rax, 2
0x18001a1fc  mov     ecx, r8d
0x18001a1ff  shr     rcx, 4
0x18001a203  and     r8b, 0Fh
0x18001a207  movzx   eax, word ptr [r9+rax*2]
0x18001a20c  mov     [r10], ax
0x18001a210  mov     al, dl
0x18001a212  shl     al, 4
0x18001a215  or      rcx, rax
0x18001a218  mov     word ptr [r10+6], 3Dh ; '='
0x18001a21f  and     ecx, 3Fh
0x18001a222  shl     r8b, 2
0x18001a226  movzx   eax, word ptr [r9+rcx*2]
0x18001a22b  mov     [r10+2], ax
0x18001a230  movzx   eax, r8b
0x18001a234  movzx   eax, word ptr [r9+rax*2]
0x18001a239  mov     [r10+4], ax
0x18001a23e  jmp     loc_18001A2DF
0x18001a243  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a24a  mov     r8d, 80070057h
0x18001a250  mov     ebx, r8d
0x18001a253  jz      loc_18001A385
0x18001a259  lea     rax, aCbrPch3Pchenco; "CBR(pch + 3 < (pchEncodedData + cchEnco"...
0x18001a260  mov     [rsp+68h+var_40], rax
0x18001a265  mov     [rsp+68h+var_48], 10Fh
0x18001a26d  jmp     loc_18001A379
0x18001a272  test    rsi, rsi
0x18001a275  jnz     short loc_18001A2A5
0x18001a277  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a27e  mov     ebx, 8000FFFFh
0x18001a283  jz      loc_18001A385
0x18001a289  lea     rax, aCprPbendoftrip; "CPR(pbEndOfTriplets)"
0x18001a290  mov     r8d, ebx
0x18001a293  mov     [rsp+68h+var_40], rax
0x18001a298  mov     [rsp+68h+var_48], 0F7h
0x18001a2a0  jmp     loc_18001A379
0x18001a2a5  lea     rcx, [r14+rdi*2]
0x18001a2a9  lea     rax, [r10+6]
0x18001a2ad  cmp     rax, rcx
0x18001a2b0  jnb     short loc_18001A321
0x18001a2b2  movzx   ecx, byte ptr [rsi]
0x18001a2b5  mov     eax, ecx
0x18001a2b7  and     cl, 3
0x18001a2ba  shr     rax, 2
0x18001a2be  shl     cl, 4
0x18001a2c1  movzx   eax, word ptr [r9+rax*2]
0x18001a2c6  mov     [r10], ax
0x18001a2ca  movzx   eax, cl
0x18001a2cd  mov     dword ptr [r10+4], 3D003Dh
0x18001a2d5  movzx   eax, word ptr [r9+rax*2]
0x18001a2da  mov     [r10+2], ax
0x18001a2df  add     r10, 8
0x18001a2e3  lea     rax, [r14+rdi*2]
0x18001a2e7  cmp     r10, rax
0x18001a2ea  jnb     short loc_18001A2F9
0x18001a2ec  xor     eax, eax
0x18001a2ee  mov     [r10], ax
0x18001a2f2  xor     ebx, ebx
0x18001a2f4  jmp     loc_18001A385
0x18001a2f9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a300  mov     r8d, 80070057h
0x18001a306  mov     ebx, r8d
0x18001a309  jz      short loc_18001A385
0x18001a30b  lea     rax, aCbrPchPchencod; "CBR(pch < pchEncodedData + cchEncodedDa"...
0x18001a312  mov     [rsp+68h+var_40], rax
0x18001a317  mov     [rsp+68h+var_48], 11Eh
0x18001a31f  jmp     short loc_18001A379
0x18001a321  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a328  mov     r8d, 80070057h
0x18001a32e  mov     ebx, r8d
0x18001a331  jz      short loc_18001A385
0x18001a333  lea     rax, aCbrPch3Pchenco; "CBR(pch + 3 < (pchEncodedData + cchEnco"...
0x18001a33a  mov     [rsp+68h+var_40], rax
0x18001a33f  mov     [rsp+68h+var_48], 0F8h
0x18001a347  jmp     short loc_18001A379
0x18001a349  mov     ebx, 80070057h
0x18001a34e  jmp     short loc_18001A385
0x18001a350  mov     r11b, 1
0x18001a353  mov     r8d, 80070057h
0x18001a359  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r11b
0x18001a360  mov     ebx, r8d
0x18001a363  jz      short loc_18001A385
0x18001a365  lea     rax, aCbrCbbinarydat; "CBR(cbBinaryData > 0)"
0x18001a36c  mov     [rsp+68h+var_40], rax
0x18001a371  mov     [rsp+68h+var_48], 0C9h
0x18001a379  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a380  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a385  mov     eax, ebx
0x18001a387  add     rsp, 30h
0x18001a38b  pop     r15
0x18001a38d  pop     r14
0x18001a38f  pop     r13
0x18001a391  pop     rdi
0x18001a392  pop     rsi
0x18001a393  pop     rbp
0x18001a394  pop     rbx
0x18001a395  retn
```
