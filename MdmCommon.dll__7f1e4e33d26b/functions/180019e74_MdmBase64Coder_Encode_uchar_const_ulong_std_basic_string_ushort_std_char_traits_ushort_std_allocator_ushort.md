# MdmBase64Coder::Encode(uchar const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180019e74`
- end: `0x18001a039`
- name: `?Encode@MdmBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int8 *, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008a6c`
- `0x18001a8d4`

## callees

- `0x1800028e4`
- `0x180006548`
- `0x180019e74`
- `0x18001a040`
- `0x18001d51c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001a024`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001a024`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180019f54`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180019f54`

## string_xrefs

- `0x180019ec5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmbase64coder.cpp`
- `0x180019fc0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmbase64coder.cpp`

## pseudocode

```c
__int64 __fastcall MdmBase64Coder::Encode(unsigned __int64 a1, const unsigned __int8 *a2, unsigned int a3, __int64 a4)
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
          a1,
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
          if ( v13 > *(_QWORD *)(a4 + 24) )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              (char **)a4,
              v13,
              v12,
              v9);
          }
          else
          {
            if ( *(_QWORD *)(a4 + 24) <= 7u )
              v14 = (char *)a4;
            else
              v14 = *(char **)a4;
            *(_QWORD *)(a4 + 16) = v13;
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
      a1,
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
0x180019e74  mov     [rsp+arg_0], rcx
0x180019e79  push    rbx
0x180019e7a  push    rbp
0x180019e7b  push    rsi
0x180019e7c  push    rdi
0x180019e7d  push    r14
0x180019e7f  push    r15
0x180019e81  sub     rsp, 38h
0x180019e85  xor     r15d, r15d
0x180019e88  mov     rbx, r9
0x180019e8b  mov     [rsp+68h+arg_0], r15
0x180019e90  mov     ebp, r8d
0x180019e93  mov     r14, rdx
0x180019e96  test    rdx, rdx
0x180019e99  jnz     short loc_180019ED6
0x180019e9b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180019ea2  mov     r8d, 80070057h
0x180019ea8  mov     edi, r8d
0x180019eab  jz      loc_18001A02A
0x180019eb1  lea     rax, aCprPbbinarydat; "CPR(pbBinaryData)"
0x180019eb8  mov     [rsp+68h+var_40], rax
0x180019ebd  mov     dword ptr [rsp+68h+var_48], 3Eh ; '>'
0x180019ec5  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180019ecc  call    McTemplateU0dsqs_EventWriteTransfer
0x180019ed1  jmp     loc_18001A02A
0x180019ed6  test    ebp, ebp
0x180019ed8  jnz     short loc_180019F06
0x180019eda  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180019ee1  mov     r8d, 80070057h; unsigned int
0x180019ee7  mov     edi, r8d
0x180019eea  jz      loc_18001A02A
0x180019ef0  lea     rax, aCbrCbbinarydat; "CBR(cbBinaryData > 0)"
0x180019ef7  mov     [rsp+68h+var_40], rax
0x180019efc  mov     dword ptr [rsp+68h+var_48], 3Fh ; '?'
0x180019f04  jmp     short loc_180019EC5
0x180019f06  lea     rax, [rsp+68h+arg_0]
0x180019f0b  xor     r9d, r9d; unsigned __int16 *
0x180019f0e  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x180019f13  call    ?_Encode@MdmBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z; MdmBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)
0x180019f18  mov     edi, eax
0x180019f1a  test    eax, eax
0x180019f1c  jns     short loc_180019F44
0x180019f1e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180019f25  jz      loc_18001A02A
0x180019f2b  lea     rax, aChrEncodePbbin_0; "CHR(_Encode(pbBinaryData, cbBinaryData,"...
0x180019f32  mov     [rsp+68h+var_40], rax
0x180019f37  mov     dword ptr [rsp+68h+var_48], 42h ; 'B'
0x180019f3f  mov     r8d, edi
0x180019f42  jmp     short loc_180019EC5
0x180019f44  mov     rcx, [rsp+68h+arg_0]
0x180019f49  inc     rcx
0x180019f4c  mov     [rsp+68h+arg_0], rcx
0x180019f51  add     rcx, rcx; Size
0x180019f54  call    cs:__imp_malloc
0x180019f5a  mov     rsi, rax
0x180019f5d  test    rax, rax
0x180019f60  jnz     short loc_180019F8A
0x180019f62  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180019f69  mov     edi, 8007000Eh
0x180019f6e  jz      loc_18001A02A
0x180019f74  lea     rax, aCbr0Pszbuffer; "CBR(0 != pszBuffer)"
0x180019f7b  mov     [rsp+68h+var_40], rax
0x180019f80  mov     dword ptr [rsp+68h+var_48], 4Ah ; 'J'
0x180019f88  jmp     short loc_180019F3F
0x180019f8a  lea     rax, [rsp+68h+arg_0]
0x180019f8f  mov     r9, rsi; unsigned __int16 *
0x180019f92  mov     r8d, ebp; unsigned int
0x180019f95  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x180019f9a  mov     rdx, r14; unsigned __int8 *
0x180019f9d  call    ?_Encode@MdmBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z; MdmBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)
0x180019fa2  mov     edi, eax
0x180019fa4  test    eax, eax
0x180019fa6  jns     short loc_180019FD6
0x180019fa8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180019faf  jz      short loc_18001A021
0x180019fb1  lea     rax, aChrEncodePbbin; "CHR(_Encode( pbBinaryData, cbBinaryData"...
0x180019fb8  mov     r8d, edi
0x180019fbb  mov     [rsp+68h+var_40], rax
0x180019fc0  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180019fc7  mov     dword ptr [rsp+68h+var_48], 52h ; 'R'
0x180019fcf  call    McTemplateU0dsqs_EventWriteTransfer
0x180019fd4  jmp     short loc_18001A021
0x180019fd6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019fda  inc     rdx
0x180019fdd  cmp     [rsi+rdx*2], r15w
0x180019fe2  jnz     short loc_180019FDA
0x180019fe4  cmp     rdx, [rbx+18h]
0x180019fe8  ja      short loc_18001A016
0x180019fea  cmp     qword ptr [rbx+18h], 7
0x180019fef  jbe     short loc_180019FF6
0x180019ff1  mov     rbp, [rbx]
0x180019ff4  jmp     short loc_180019FF9
0x180019ff6  mov     rbp, rbx
0x180019ff9  mov     [rbx+10h], rdx
0x180019ffd  mov     rcx, rbp; void *
0x18001a000  lea     rbx, [rdx+rdx]
0x18001a004  mov     rdx, rsi; Src
0x18001a007  mov     r8, rbx; Size
0x18001a00a  call    memmove_0
0x18001a00f  mov     [rbx+rbp], r15w
0x18001a014  jmp     short loc_18001A021
0x18001a016  mov     r9, rsi
0x18001a019  mov     rcx, rbx
0x18001a01c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001a021  mov     rcx, rsi; Block
0x18001a024  call    cs:__imp_free
0x18001a02a  mov     eax, edi
0x18001a02c  add     rsp, 38h
0x18001a030  pop     r15
0x18001a032  pop     r14
0x18001a034  pop     rdi
0x18001a035  pop     rsi
0x18001a036  pop     rbp
0x18001a037  pop     rbx
0x18001a038  retn
```
