# MdmBase64Coder::Encode(uchar const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001a388`
- end: `0x18001a55a`
- name: `?Encode@MdmBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(MdmBase64Coder *, const unsigned __int8 *, unsigned int, char **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008be0`
- `0x18001ae24`

## callees

- `0x1800028e4`
- `0x1800065c0`
- `0x18001a388`
- `0x18001a560`
- `0x18001dbfc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001a53e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001a53e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001a468`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001a468`

## string_xrefs

- `0x18001a3d9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmbase64coder.cpp`
- `0x18001a4da`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmbase64coder.cpp`

## pseudocode

```c
__int64 __fastcall MdmBase64Coder::Encode(MdmBase64Coder *a1, const unsigned __int8 *a2, unsigned int a3, char **a4)
{
  int v7; // r8d
  unsigned int v8; // edi
  unsigned __int16 *v9; // rsi
  int v10; // edx
  int v11; // ecx
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  char *v14; // rbp
  __int64 v15; // rbx
  char v17; // [rsp+20h] [rbp-48h]
  const char *v18; // [rsp+28h] [rbp-40h]
  unsigned __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = 0;
  if ( a2 )
  {
    if ( !a3 )
    {
      v8 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
          63,
          "CBR(cbBinaryData > 0)");
      return v8;
    }
    v8 = MdmBase64Coder::_Encode(a1, a2, a3, 0, &v19);
    if ( (v8 & 0x80000000) == 0 )
    {
      ++v19;
      v9 = (unsigned __int16 *)malloc(2 * v19);
      if ( v9 )
      {
        v8 = MdmBase64Coder::_Encode(a1, a2, a3, v9, &v19);
        if ( (v8 & 0x80000000) == 0 )
        {
          v13 = -1;
          do
            ++v13;
          while ( v9[v13] );
          if ( v13 > (unsigned __int64)a4[3] )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              a4,
              v13,
              v12,
              v9);
          }
          else
          {
            if ( (unsigned __int64)a4[3] <= 7 )
              v14 = (char *)a4;
            else
              v14 = *a4;
            a4[2] = (char *)v13;
            v15 = 2 * v13;
            memmove_0(v14, v9, 2 * v13);
            *(_WORD *)&v14[v15] = 0;
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v11,
            v10,
            v8,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
            82,
            "CHR(_Encode( pbBinaryData, cbBinaryData, pszBuffer, cchEncodedData ))");
        }
        free(v9);
        return v8;
      }
      v8 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        return v8;
      v18 = "CBR(0 != pszBuffer)";
      v17 = 74;
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        return v8;
      v18 = "CHR(_Encode(pbBinaryData, cbBinaryData, 0, cchEncodedData))";
      v17 = 66;
    }
    v7 = v8;
    goto LABEL_4;
  }
  v7 = -2147024809;
  v8 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v18 = "CPR(pbBinaryData)";
    v17 = 62;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      v7,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmbase64coder.cpp",
      v17,
      v18);
  }
  return v8;
}

```

## disassembly

```asm
0x18001a388  mov     [rsp+arg_0], rcx
0x18001a38d  push    rbx
0x18001a38e  push    rbp
0x18001a38f  push    rsi
0x18001a390  push    rdi
0x18001a391  push    r14
0x18001a393  push    r15
0x18001a395  sub     rsp, 38h
0x18001a399  xor     r15d, r15d
0x18001a39c  mov     rbx, r9
0x18001a39f  mov     [rsp+68h+arg_0], r15
0x18001a3a4  mov     ebp, r8d
0x18001a3a7  mov     r14, rdx
0x18001a3aa  test    rdx, rdx
0x18001a3ad  jnz     short loc_18001A3EA
0x18001a3af  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a3b6  mov     r8d, 80070057h
0x18001a3bc  mov     edi, r8d
0x18001a3bf  jz      loc_18001A54A
0x18001a3c5  lea     rax, aCprPbbinarydat; "CPR(pbBinaryData)"
0x18001a3cc  mov     [rsp+68h+var_40], rax
0x18001a3d1  mov     dword ptr [rsp+68h+var_48], 3Eh ; '>'
0x18001a3d9  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a3e0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a3e5  jmp     loc_18001A54A
0x18001a3ea  test    ebp, ebp
0x18001a3ec  jnz     short loc_18001A41A
0x18001a3ee  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a3f5  mov     r8d, 80070057h; unsigned int
0x18001a3fb  mov     edi, r8d
0x18001a3fe  jz      loc_18001A54A
0x18001a404  lea     rax, aCbrCbbinarydat; "CBR(cbBinaryData > 0)"
0x18001a40b  mov     [rsp+68h+var_40], rax
0x18001a410  mov     dword ptr [rsp+68h+var_48], 3Fh ; '?'
0x18001a418  jmp     short loc_18001A3D9
0x18001a41a  lea     rax, [rsp+68h+arg_0]
0x18001a41f  xor     r9d, r9d; unsigned __int16 *
0x18001a422  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x18001a427  call    ?_Encode@MdmBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z; MdmBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)
0x18001a42c  mov     edi, eax
0x18001a42e  test    eax, eax
0x18001a430  jns     short loc_18001A458
0x18001a432  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a439  jz      loc_18001A54A
0x18001a43f  lea     rax, aChrEncodePbbin_0; "CHR(_Encode(pbBinaryData, cbBinaryData,"...
0x18001a446  mov     [rsp+68h+var_40], rax
0x18001a44b  mov     dword ptr [rsp+68h+var_48], 42h ; 'B'
0x18001a453  mov     r8d, edi
0x18001a456  jmp     short loc_18001A3D9
0x18001a458  mov     rcx, [rsp+68h+arg_0]
0x18001a45d  inc     rcx
0x18001a460  mov     [rsp+68h+arg_0], rcx
0x18001a465  add     rcx, rcx; Size
0x18001a468  call    cs:__imp_malloc
0x18001a46f  nop     dword ptr [rax+rax+00h]
0x18001a474  mov     rsi, rax
0x18001a477  test    rax, rax
0x18001a47a  jnz     short loc_18001A4A4
0x18001a47c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a483  mov     edi, 8007000Eh
0x18001a488  jz      loc_18001A54A
0x18001a48e  lea     rax, aCbr0Pszbuffer; "CBR(0 != pszBuffer)"
0x18001a495  mov     [rsp+68h+var_40], rax
0x18001a49a  mov     dword ptr [rsp+68h+var_48], 4Ah ; 'J'
0x18001a4a2  jmp     short loc_18001A453
0x18001a4a4  lea     rax, [rsp+68h+arg_0]
0x18001a4a9  mov     r9, rsi; unsigned __int16 *
0x18001a4ac  mov     r8d, ebp; unsigned int
0x18001a4af  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x18001a4b4  mov     rdx, r14; unsigned __int8 *
0x18001a4b7  call    ?_Encode@MdmBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z; MdmBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)
0x18001a4bc  mov     edi, eax
0x18001a4be  test    eax, eax
0x18001a4c0  jns     short loc_18001A4F0
0x18001a4c2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a4c9  jz      short loc_18001A53B
0x18001a4cb  lea     rax, aChrEncodePbbin; "CHR(_Encode( pbBinaryData, cbBinaryData"...
0x18001a4d2  mov     r8d, edi
0x18001a4d5  mov     [rsp+68h+var_40], rax
0x18001a4da  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a4e1  mov     dword ptr [rsp+68h+var_48], 52h ; 'R'
0x18001a4e9  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a4ee  jmp     short loc_18001A53B
0x18001a4f0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001a4f4  inc     rdx
0x18001a4f7  cmp     [rsi+rdx*2], r15w
0x18001a4fc  jnz     short loc_18001A4F4
0x18001a4fe  cmp     rdx, [rbx+18h]
0x18001a502  ja      short loc_18001A530
0x18001a504  cmp     qword ptr [rbx+18h], 7
0x18001a509  jbe     short loc_18001A510
0x18001a50b  mov     rbp, [rbx]
0x18001a50e  jmp     short loc_18001A513
0x18001a510  mov     rbp, rbx
0x18001a513  mov     [rbx+10h], rdx
0x18001a517  mov     rcx, rbp; void *
0x18001a51a  lea     rbx, [rdx+rdx]
0x18001a51e  mov     rdx, rsi; Src
0x18001a521  mov     r8, rbx; Size
0x18001a524  call    memmove_0
0x18001a529  mov     [rbx+rbp], r15w
0x18001a52e  jmp     short loc_18001A53B
0x18001a530  mov     r9, rsi
0x18001a533  mov     rcx, rbx
0x18001a536  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001a53b  mov     rcx, rsi; Block
0x18001a53e  call    cs:__imp_free
0x18001a545  nop     dword ptr [rax+rax+00h]
0x18001a54a  mov     eax, edi
0x18001a54c  add     rsp, 38h
0x18001a550  pop     r15
0x18001a552  pop     r14
0x18001a554  pop     rdi
0x18001a555  pop     rsi
0x18001a556  pop     rbp
0x18001a557  pop     rbx
0x18001a558  retn
```
