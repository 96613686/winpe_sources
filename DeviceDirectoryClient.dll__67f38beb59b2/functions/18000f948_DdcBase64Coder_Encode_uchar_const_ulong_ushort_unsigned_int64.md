# DdcBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)

- ea: `0x18000f948`
- end: `0x18000fc5d`
- name: `?_Encode@DdcBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z`
- size: `789`
- prototype: `__int64 __fastcall(DdcBase64Coder *this, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f7e4`

## callees

- `0x1800050b8`
- `0x18000f948`

## string_xrefs

- `0x18000f98c`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcbase64coder.cpp`

## pseudocode

```c
__int64 __fastcall DdcBase64Coder::_Encode(
        DdcBase64Coder *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int64 *a5)
{
  const unsigned __int16 *v6; // r15
  unsigned int v7; // ebx
  const char *v8; // rcx
  unsigned __int64 v9; // rbx
  __int64 v10; // r11
  unsigned __int64 v11; // rsi
  unsigned __int16 *v12; // r10
  const unsigned __int16 *v13; // r13
  const unsigned __int16 *v14; // rbp
  unsigned __int16 *v15; // rcx
  char v16; // dl
  unsigned int v17; // r9d
  unsigned __int8 v18; // r8
  unsigned __int8 v19; // al
  __int64 v20; // r11
  unsigned __int64 v21; // rcx
  char v22; // r8
  unsigned __int8 v23; // cl
  char v25; // [rsp+20h] [rbp-48h]
  const char *v26; // [rsp+28h] [rbp-40h]

  v6 = a2;
  if ( !a2 )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      v8 = "CPR(pbBinaryData)";
      v26 = "CPR(pbBinaryData)";
      v25 = -64;
LABEL_4:
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)v8,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcbase64coder.cpp",
        v25,
        (__int64)v26);
      return v7;
    }
    return v7;
  }
  if ( !a4 )
  {
    v7 = 0;
    *a5 = (4 * a3 / 3 + 3) & 0xFFFFFFFC;
    return v7;
  }
  v9 = *a5;
  if ( (*a5 & 3) != 1 )
    return (unsigned int)-2147024809;
  v10 = a3;
  if ( 3 * (v9 >> 2) < a3 )
    return (unsigned int)-2147024809;
  v11 = v9;
  LODWORD(a2) = a3 / 3;
  v12 = a4;
  v13 = v6;
  v14 = (const unsigned __int16 *)((char *)v6 + a3 - (unsigned __int64)(a3 % 3));
  while ( 1 )
  {
    v15 = v12 + 3;
    if ( v13 >= v14 )
      break;
    v11 = v9;
    if ( v15 >= &a4[v9] )
      break;
    v16 = *(_BYTE *)v13;
    v17 = *((unsigned __int8 *)v13 + 2);
    v18 = *((_BYTE *)v13 + 1);
    *v12 = DdcBase64Coder::s_rgchBase64Digits[(unsigned __int64)*(unsigned __int8 *)v13 >> 2];
    v19 = 16 * v16;
    a2 = L"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/";
    v12[1] = DdcBase64Coder::s_rgchBase64Digits[(v19 | (v18 >> 4)) & 0x3F];
    v12[2] = DdcBase64Coder::s_rgchBase64Digits[((unsigned __int8)(4 * v18)
                                               | (unsigned __int8)((unsigned __int64)v17 >> 6))
                                              & 0x3F];
    v12[3] = DdcBase64Coder::s_rgchBase64Digits[v17 & 0x3F];
    v12 += 4;
    v13 = (const unsigned __int16 *)((char *)v13 + 3);
  }
  v7 = 0;
  v20 = (__int64)v6 + v10 - (_QWORD)v14 - 1;
  if ( !v20 )
  {
    if ( !v14 )
    {
      v7 = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v15,
          (_DWORD)a2,
          -2147418113,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcbase64coder.cpp",
          239,
          (__int64)"CPR(pbEndOfTriplets)");
      return v7;
    }
    if ( v15 >= &a4[v11] )
    {
      v7 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v8 = "CBR(pch + 3 < (pchEncodedData + cchEncodedData))";
        v26 = "CBR(pch + 3 < (pchEncodedData + cchEncodedData))";
        v25 = -16;
        goto LABEL_4;
      }
      return v7;
    }
    v23 = 16 * (*(_BYTE *)v14 & 3);
    *v12 = DdcBase64Coder::s_rgchBase64Digits[(unsigned __int64)*(unsigned __int8 *)v14 >> 2];
    *((_DWORD *)v12 + 1) = 3997757;
    v12[1] = DdcBase64Coder::s_rgchBase64Digits[v23];
    goto LABEL_25;
  }
  if ( v20 != 1 )
    goto LABEL_26;
  if ( v15 < &a4[v11] )
  {
    LODWORD(a2) = *(unsigned __int8 *)v14;
    v21 = (unsigned __int64)*((unsigned __int8 *)v14 + 1) >> 4;
    v22 = *((_BYTE *)v14 + 1) & 0xF;
    *v12 = DdcBase64Coder::s_rgchBase64Digits[(unsigned __int64)*(unsigned __int8 *)v14 >> 2];
    v12[3] = 61;
    v12[1] = DdcBase64Coder::s_rgchBase64Digits[((unsigned __int8)(16 * (_BYTE)a2) | (unsigned __int8)v21) & 0x3F];
    v12[2] = DdcBase64Coder::s_rgchBase64Digits[(unsigned __int8)(4 * v22)];
LABEL_25:
    v12 += 4;
LABEL_26:
    if ( v12 >= &a4[v11] )
    {
      v7 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v8 = "CBR(pch < pchEncodedData + cchEncodedData)";
        v26 = "CBR(pch < pchEncodedData + cchEncodedData)";
        v25 = 22;
        goto LABEL_4;
      }
    }
    else
    {
      *v12 = 0;
    }
    return v7;
  }
  v7 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v8 = "CBR(pch + 3 < (pchEncodedData + cchEncodedData))";
    v26 = "CBR(pch + 3 < (pchEncodedData + cchEncodedData))";
    v25 = 7;
    goto LABEL_4;
  }
  return v7;
}

```

## disassembly

```asm
0x18000f948  push    rbx
0x18000f94a  push    rbp
0x18000f94b  push    rsi
0x18000f94c  push    r13
0x18000f94e  push    r14
0x18000f950  push    r15
0x18000f952  sub     rsp, 38h
0x18000f956  mov     r14, r9
0x18000f959  mov     r15, rdx
0x18000f95c  test    rdx, rdx
0x18000f95f  jnz     short loc_18000F99D
0x18000f961  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f968  mov     eax, 80070057h
0x18000f96d  mov     ebx, eax
0x18000f96f  jz      loc_18000FC4D
0x18000f975  lea     rcx, aCprPbbinarydat; "CPR(pbBinaryData)"
0x18000f97c  mov     [rsp+68h+var_40], rcx
0x18000f981  mov     dword ptr [rsp+68h+var_48], 0C0h
0x18000f989  mov     r8d, eax
0x18000f98c  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f993  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f998  jmp     loc_18000FC4D
0x18000f99d  test    r14, r14
0x18000f9a0  jnz     short loc_18000F9D0
0x18000f9a2  mov     eax, 0AAAAAAABh
0x18000f9a7  lea     ecx, ds:0[r8*4]
0x18000f9af  mul     ecx
0x18000f9b1  mov     eax, 0FFFFFFFCh
0x18000f9b6  xor     ebx, ebx
0x18000f9b8  shr     edx, 1
0x18000f9ba  add     edx, 3
0x18000f9bd  and     rdx, rax
0x18000f9c0  mov     rax, [rsp+68h+arg_20]
0x18000f9c8  mov     [rax], rdx
0x18000f9cb  jmp     loc_18000FC4D
0x18000f9d0  mov     rax, [rsp+68h+arg_20]
0x18000f9d8  mov     rbx, [rax]
0x18000f9db  mov     al, bl
0x18000f9dd  and     al, 3
0x18000f9df  cmp     al, 1
0x18000f9e1  jnz     loc_18000FC48
0x18000f9e7  mov     rax, rbx
0x18000f9ea  mov     r11d, r8d
0x18000f9ed  shr     rax, 2
0x18000f9f1  lea     rax, [rax+rax*2]
0x18000f9f5  cmp     rax, r11
0x18000f9f8  jb      loc_18000FC48
0x18000f9fe  mov     eax, 0AAAAAAABh
0x18000fa03  lea     rsi, [rbx+rbx]
0x18000fa07  mul     r8d
0x18000fa0a  mov     ebp, r11d
0x18000fa0d  lea     r9, ?s_rgchBase64Digits@DdcBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18000fa14  shr     edx, 1
0x18000fa16  mov     r10, r14
0x18000fa19  mov     r13, r15
0x18000fa1c  lea     eax, [rdx+rdx*2]
0x18000fa1f  sub     r8d, eax
0x18000fa22  mov     eax, r8d
0x18000fa25  sub     rbp, rax
0x18000fa28  add     rbp, r15
0x18000fa2b  lea     rcx, [r10+6]
0x18000fa2f  cmp     r13, rbp
0x18000fa32  jnb     loc_18000FACF
0x18000fa38  lea     rsi, [rbx+rbx]
0x18000fa3c  lea     rax, [rsi+r14]
0x18000fa40  cmp     rcx, rax
0x18000fa43  jnb     loc_18000FACF
0x18000fa49  movzx   edx, byte ptr [r13+0]
0x18000fa4e  lea     rcx, ?s_rgchBase64Digits@DdcBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18000fa55  movzx   r9d, byte ptr [r13+2]
0x18000fa5a  mov     eax, edx
0x18000fa5c  movzx   r8d, byte ptr [r13+1]
0x18000fa61  shr     rax, 2
0x18000fa65  movzx   eax, word ptr [rcx+rax*2]
0x18000fa69  mov     ecx, r8d
0x18000fa6c  mov     [r10], ax
0x18000fa70  mov     al, dl
0x18000fa72  shl     al, 4
0x18000fa75  lea     rdx, ?s_rgchBase64Digits@DdcBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18000fa7c  shr     rcx, 4
0x18000fa80  or      rcx, rax
0x18000fa83  and     ecx, 3Fh
0x18000fa86  movzx   eax, word ptr [rdx+rcx*2]
0x18000fa8a  mov     ecx, r9d
0x18000fa8d  mov     [r10+2], ax
0x18000fa92  mov     al, r8b
0x18000fa95  shl     al, 2
0x18000fa98  shr     rcx, 6
0x18000fa9c  or      rcx, rax
0x18000fa9f  and     ecx, 3Fh
0x18000faa2  movzx   eax, word ptr [rdx+rcx*2]
0x18000faa6  mov     [r10+4], ax
0x18000faab  mov     eax, r9d
0x18000faae  and     eax, 3Fh
0x18000fab1  lea     r9, ?s_rgchBase64Digits@DdcBase64Coder@@0QBGB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18000fab8  movzx   eax, word ptr [r9+rax*2]
0x18000fabd  mov     [r10+6], ax
0x18000fac2  add     r10, 8
0x18000fac6  add     r13, 3
0x18000faca  jmp     loc_18000FA2B
0x18000facf  sub     r11, rbp
0x18000fad2  xor     ebx, ebx
0x18000fad4  add     r11, r15
0x18000fad7  sub     r11, 1
0x18000fadb  jz      loc_18000FB77
0x18000fae1  cmp     r11, 1
0x18000fae5  jnz     loc_18000FBE5
0x18000faeb  lea     rax, [rsi+r14]
0x18000faef  cmp     rcx, rax
0x18000faf2  jnb     short loc_18000FB4A
0x18000faf4  movzx   edx, byte ptr [rbp+0]
0x18000faf8  movzx   r8d, byte ptr [rbp+1]
0x18000fafd  mov     eax, edx
0x18000faff  shr     rax, 2
0x18000fb03  mov     ecx, r8d
0x18000fb06  shr     rcx, 4
0x18000fb0a  and     r8b, 0Fh
0x18000fb0e  movzx   eax, word ptr [r9+rax*2]
0x18000fb13  mov     [r10], ax
0x18000fb17  mov     al, dl
0x18000fb19  shl     al, 4
0x18000fb1c  or      rcx, rax
0x18000fb1f  mov     word ptr [r10+6], 3Dh ; '='
0x18000fb26  and     ecx, 3Fh
0x18000fb29  shl     r8b, 2
0x18000fb2d  movzx   eax, word ptr [r9+rcx*2]
0x18000fb32  mov     [r10+2], ax
0x18000fb37  movzx   eax, r8b
0x18000fb3b  movzx   eax, word ptr [r9+rax*2]
0x18000fb40  mov     [r10+4], ax
0x18000fb45  jmp     loc_18000FBE1
0x18000fb4a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000fb51  mov     eax, 80070057h
0x18000fb56  mov     ebx, eax
0x18000fb58  jz      loc_18000FC4D
0x18000fb5e  lea     rcx, aCbrPch3Pchenco; "CBR(pch + 3 < (pchEncodedData + cchEnco"...
0x18000fb65  mov     [rsp+68h+var_40], rcx
0x18000fb6a  mov     dword ptr [rsp+68h+var_48], 107h
0x18000fb72  jmp     loc_18000F989
0x18000fb77  test    rbp, rbp
0x18000fb7a  jnz     short loc_18000FBAA
0x18000fb7c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000fb83  mov     ebx, 8000FFFFh
0x18000fb88  jz      loc_18000FC4D
0x18000fb8e  lea     rax, aCprPbendoftrip; "CPR(pbEndOfTriplets)"
0x18000fb95  mov     r8d, ebx
0x18000fb98  mov     [rsp+68h+var_40], rax
0x18000fb9d  mov     dword ptr [rsp+68h+var_48], 0EFh
0x18000fba5  jmp     loc_18000F98C
0x18000fbaa  lea     rax, [rsi+r14]
0x18000fbae  cmp     rcx, rax
0x18000fbb1  jnb     short loc_18000FC1F
0x18000fbb3  movzx   ecx, byte ptr [rbp+0]
0x18000fbb7  mov     eax, ecx
0x18000fbb9  and     cl, 3
0x18000fbbc  shr     rax, 2
0x18000fbc0  shl     cl, 4
0x18000fbc3  movzx   eax, word ptr [r9+rax*2]
0x18000fbc8  mov     [r10], ax
0x18000fbcc  movzx   eax, cl
0x18000fbcf  mov     dword ptr [r10+4], 3D003Dh
0x18000fbd7  movzx   eax, word ptr [r9+rax*2]
0x18000fbdc  mov     [r10+2], ax
0x18000fbe1  add     r10, 8
0x18000fbe5  lea     rax, [rsi+r14]
0x18000fbe9  cmp     r10, rax
0x18000fbec  jnb     short loc_18000FBF6
0x18000fbee  xor     eax, eax
0x18000fbf0  mov     [r10], ax
0x18000fbf4  jmp     short loc_18000FC4D
0x18000fbf6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000fbfd  mov     eax, 80070057h
0x18000fc02  mov     ebx, eax
0x18000fc04  jz      short loc_18000FC4D
0x18000fc06  lea     rcx, aCbrPchPchencod; "CBR(pch < pchEncodedData + cchEncodedDa"...
0x18000fc0d  mov     [rsp+68h+var_40], rcx
0x18000fc12  mov     dword ptr [rsp+68h+var_48], 116h
0x18000fc1a  jmp     loc_18000F989
0x18000fc1f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000fc26  mov     eax, 80070057h
0x18000fc2b  mov     ebx, eax
0x18000fc2d  jz      short loc_18000FC4D
0x18000fc2f  lea     rcx, aCbrPch3Pchenco; "CBR(pch + 3 < (pchEncodedData + cchEnco"...
0x18000fc36  mov     [rsp+68h+var_40], rcx
0x18000fc3b  mov     dword ptr [rsp+68h+var_48], 0F0h
0x18000fc43  jmp     loc_18000F989
0x18000fc48  mov     ebx, 80070057h
0x18000fc4d  mov     eax, ebx
0x18000fc4f  add     rsp, 38h
0x18000fc53  pop     r15
0x18000fc55  pop     r14
0x18000fc57  pop     r13
0x18000fc59  pop     rsi
0x18000fc5a  pop     rbp
0x18000fc5b  pop     rbx
0x18000fc5c  retn
```
