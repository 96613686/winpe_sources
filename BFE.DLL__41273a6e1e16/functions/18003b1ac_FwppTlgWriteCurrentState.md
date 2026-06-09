# FwppTlgWriteCurrentState

- ea: `0x18003b1ac`
- end: `0x18003b58c`
- name: `FwppTlgWriteCurrentState`
- size: `992`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180076284`

## callees

- `0x180005268`
- `0x18000a070`
- `0x18000e7e0`
- `0x180013110`
- `0x1800197d0`
- `0x18003a83c`
- `0x18003aaa8`
- `0x18003aec8`
- `0x18003af8c`
- `0x18003b050`
- `0x18003b1ac`
- `0x18003cc6c`
- `0x18003cd5c`
- `0x18003dd9c`
- `0x180057c60`
- `0x18005aa60`
- `0x18005b4fc`
- `0x180067558`
- `0x180077214`
- `0x1800772d8`
- `0x18007739c`
- `0x18007750c`
- `0x1800775d0`
- `0x180077694`
- `0x18007778c`
- `0x1800778f4`
- `0x1800779b8`
- `0x180077a7c`
- `0x180077b80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b237`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b237`

## string_xrefs

- `0x18003b559`: `FwppTlgWriteCurrentState`
- `0x18003b3ae`: `FwppXmlWrite_FWPM_LAYER`

## pseudocode

```c
__int64 __fastcall FwppTlgWriteCurrentState(__int64 a1)
{
  int v1; // r13d
  unsigned int v3; // r14d
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 i; // rsi
  __int64 v13; // rdx
  __int64 v14; // r12
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int128 v18; // xmm0
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rsi
  __int64 j; // rdi
  unsigned int v32; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v33; // [rsp+38h] [rbp-A1h] BYREF
  int v34; // [rsp+40h] [rbp-99h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-91h] BYREF
  _OWORD v36[2]; // [rsp+50h] [rbp-89h] BYREF
  _OWORD v37[2]; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v38[8]; // [rsp+90h] [rbp-49h] BYREF
  __int128 v39; // [rsp+98h] [rbp-41h]
  int v40; // [rsp+ACh] [rbp-2Dh]
  int v41; // [rsp+C8h] [rbp-11h]

  v1 = 0;
  SystemTimeAsFileTime = 0;
  v33 = 0;
  v3 = 0;
  v32 = 0;
  memset(v37, 0, 24);
  memset_0(v38, 0, 0x48u);
  v4 = FwppXmlWriteStartTagWithAttr(a1, (unsigned int)"currentState", 1, 0, 0);
  if ( !v4 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = FwppXmlWrite_FILETIME(a1, "timeStamp", &SystemTimeAsFileTime);
    if ( !v4 )
    {
      v4 = FwppTlgFwpmSessionWriteEnum(v6, v5, a1);
      if ( !v4 )
      {
        v34 = 0;
        memset(v36, 0, sizeof(v36));
        v4 = BfeCallCreateSystem(2, v7, &v34, v36);
        if ( !v4 )
        {
          v1 = 1;
          v10 = FwppTlgFwpmLayerEnumAll(v9, v8, &v33, &v32);
          v3 = v32;
          v4 = v10;
          if ( !v10 )
          {
            v4 = FwppXmlWriteStartTagForArray(a1, "layers", v11, v32);
            if ( !v4 )
            {
              for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
              {
                v4 = FwppXmlWriteStartTagWithAttr(a1, (unsigned int)"item", 1, 0, 0);
                if ( v4 )
                  goto LABEL_31;
                v14 = v33;
                v15 = FwppXmlWrite_FWPM_LAYER0(a1, v13, *(_QWORD *)(v33 + 8 * i));
                v4 = v15;
                if ( v15 )
                {
                  WfpReportError(v15, "FwppXmlWrite_FWPM_LAYER");
                  goto LABEL_31;
                }
                *(_OWORD *)((char *)v37 + 8) = *(_OWORD *)*(_QWORD *)(v14 + 8 * i);
                v4 = FwppTlgFwpmCalloutWriteEnum(v37, v16, a1);
                if ( v4 )
                  goto LABEL_31;
                v18 = *(_OWORD *)*(_QWORD *)(v14 + 8 * i);
                v40 = 24;
                v41 = -1;
                v39 = v18;
                v4 = FwppTlgFwpmFilterWriteEnum(v38, v17, a1);
                if ( v4 )
                  goto LABEL_31;
                v4 = FwppXmlWriteEndTag(a1, "item");
                if ( v4 )
                  goto LABEL_31;
              }
              v4 = FwppXmlWriteEndTag(a1, "layers");
              if ( !v4 )
              {
                v4 = FwppTlgFwpmProviderWriteEnum(v20, v19, a1);
                if ( !v4 )
                {
                  v4 = FwppTlgFwpmProviderContextWriteEnum(v22, v21, a1);
                  if ( !v4 )
                  {
                    v4 = FwppTlgFwpmSubLayerWriteEnum(v24, v23, a1);
                    if ( !v4 )
                    {
                      v4 = FwppXmlWriteStartTagWithAttr(a1, (unsigned int)"subscriptions", 1, 0, 0);
                      if ( !v4 )
                      {
                        v4 = FwppTlgFwpmCalloutWriteSubs(a1);
                        if ( !v4 )
                        {
                          v4 = FwppTlgFwpmFilterWriteSubs(a1);
                          if ( !v4 )
                          {
                            v4 = FwppTlgFwpmNetEventWriteSubs(a1);
                            if ( !v4 )
                            {
                              v4 = FwppTlgFwpmProviderWriteSubs(a1);
                              if ( !v4 )
                              {
                                v4 = FwppTlgFwpmProviderContextWriteSubs(a1);
                                if ( !v4 )
                                {
                                  v4 = FwppTlgFwpmSubLayerWriteSubs(a1);
                                  if ( !v4 )
                                  {
                                    v4 = FwppXmlWriteEndTag(a1, "subscriptions");
                                    if ( !v4 )
                                    {
                                      v4 = FwppTlgIPsecSaContextWriteEnum(v26, v25, a1);
                                      if ( !v4 )
                                      {
                                        v4 = FwppTlgFwpsAleEndpointWriteEnum(v28, v27, a1);
                                        if ( !v4 )
                                        {
                                          BfeCallCommitEx(v36, 0);
                                          BfeCallDestroy(v36);
                                          v1 = 0;
                                          v4 = FwppXmlWriteEndTag(a1, "currentState");
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_31:
  v29 = v33;
  for ( j = 0; (unsigned int)j < v3; j = (unsigned int)(j + 1) )
    BfeObjectDestroyPublicState(3, v29 + 8 * j);
  WfpMemFree(&v33);
  if ( v1 )
  {
    BfeCallCommitEx(v36, 0);
    BfeCallDestroy(v36);
  }
  if ( v4 )
    WfpReportError(v4, "FwppTlgWriteCurrentState");
  return v4;
}

```

## disassembly

```asm
0x18003b1ac  push    rbp
0x18003b1ae  push    rbx
0x18003b1af  push    rsi
0x18003b1b0  push    rdi
0x18003b1b1  push    r12
0x18003b1b3  push    r13
0x18003b1b5  push    r14
0x18003b1b7  push    r15
0x18003b1b9  lea     rbp, [rsp-1Fh]
0x18003b1be  sub     rsp, 0F8h
0x18003b1c5  mov     rax, cs:__security_cookie
0x18003b1cc  xor     rax, rsp
0x18003b1cf  mov     [rbp+57h+var_50], rax
0x18003b1d3  xor     r13d, r13d
0x18003b1d6  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003b1df  mov     rdi, rcx
0x18003b1e2  mov     [rsp+130h+var_F8], r13
0x18003b1e7  xorps   xmm0, xmm0
0x18003b1ea  lea     rcx, [rbp+57h+var_A0]; void *
0x18003b1ee  xor     eax, eax
0x18003b1f0  xor     r14d, r14d
0x18003b1f3  lea     r8d, [r13+48h]; Size
0x18003b1f7  mov     [rsp+130h+var_100], r14d
0x18003b1fc  xor     edx, edx; Val
0x18003b1fe  mov     [rbp+57h+var_B0], rax
0x18003b202  movups  [rbp+57h+var_C0], xmm0
0x18003b206  call    memset_0
0x18003b20b  xor     r9d, r9d
0x18003b20e  mov     [rsp+130h+var_110], r13
0x18003b213  lea     r8d, [r13+1]
0x18003b217  mov     rcx, rdi
0x18003b21a  lea     rdx, aCurrentstate; "currentState"
0x18003b221  call    FwppXmlWriteStartTagWithAttr
0x18003b226  mov     rbx, rax
0x18003b229  test    rax, rax
0x18003b22c  jnz     loc_18003B50E
0x18003b232  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003b237  call    cs:__imp_GetSystemTimeAsFileTime
0x18003b23e  nop     dword ptr [rax+rax+00h]
0x18003b243  lea     r8, [rsp+130h+SystemTimeAsFileTime]
0x18003b248  mov     rcx, rdi
0x18003b24b  lea     rdx, aTimestamp; "timeStamp"
0x18003b252  call    FwppXmlWrite_FILETIME
0x18003b257  mov     rbx, rax
0x18003b25a  test    rax, rax
0x18003b25d  jnz     loc_18003B50E
0x18003b263  mov     r8, rdi
0x18003b266  call    FwppTlgFwpmSessionWriteEnum
0x18003b26b  mov     rbx, rax
0x18003b26e  test    rax, rax
0x18003b271  jnz     loc_18003B50E
0x18003b277  xorps   xmm0, xmm0
0x18003b27a  mov     [rsp+130h+var_F0], r13d
0x18003b27f  lea     r9, [rsp+130h+var_E0]
0x18003b284  lea     r8, [rsp+130h+var_F0]
0x18003b289  lea     ecx, [rax+2]
0x18003b28c  movups  [rsp+130h+var_E0], xmm0
0x18003b291  movups  [rbp+57h+var_D0], xmm0
0x18003b295  call    BfeCallCreateSystem
0x18003b29a  mov     rbx, rax
0x18003b29d  test    rax, rax
0x18003b2a0  jnz     loc_18003B50E
0x18003b2a6  lea     r9, [rsp+130h+var_100]
0x18003b2ab  lea     r8, [rsp+130h+var_F8]
0x18003b2b0  lea     r13d, [r14+1]
0x18003b2b4  call    FwppTlgFwpmLayerEnumAll
0x18003b2b9  mov     r14d, [rsp+130h+var_100]
0x18003b2be  mov     rbx, rax
0x18003b2c1  test    rax, rax
0x18003b2c4  jnz     loc_18003B50E
0x18003b2ca  mov     r9d, r14d
0x18003b2cd  lea     rdx, aLayers; "layers"
0x18003b2d4  mov     rcx, rdi
0x18003b2d7  call    FwppXmlWriteStartTagForArray
0x18003b2dc  mov     rbx, rax
0x18003b2df  test    rax, rax
0x18003b2e2  jnz     loc_18003B50E
0x18003b2e8  xor     esi, esi
0x18003b2ea  mov     rcx, rdi
0x18003b2ed  cmp     esi, r14d
0x18003b2f0  jnb     loc_18003B3C2
0x18003b2f6  xor     r9d, r9d
0x18003b2f9  mov     [rsp+130h+var_110], 0
0x18003b302  mov     r8d, r13d
0x18003b305  lea     rdx, aItem; "item"
0x18003b30c  call    FwppXmlWriteStartTagWithAttr
0x18003b311  mov     rbx, rax
0x18003b314  test    rax, rax
0x18003b317  jnz     loc_18003B50E
0x18003b31d  mov     r12, [rsp+130h+var_F8]
0x18003b322  mov     r8, [r12+rsi*8]
0x18003b326  mov     rcx, rdi
0x18003b329  call    FwppXmlWrite_FWPM_LAYER0
0x18003b32e  mov     rbx, rax
0x18003b331  test    rax, rax
0x18003b334  jnz     short loc_18003B3AE
0x18003b336  mov     rax, [r12+rsi*8]
0x18003b33a  lea     rcx, [rbp+57h+var_C0]
0x18003b33e  mov     r8, rdi
0x18003b341  movups  xmm0, xmmword ptr [rax]
0x18003b344  movdqu  [rbp+57h+var_C0+8], xmm0
0x18003b349  call    FwppTlgFwpmCalloutWriteEnum
0x18003b34e  mov     rbx, rax
0x18003b351  test    rax, rax
0x18003b354  jnz     loc_18003B50E
0x18003b35a  mov     rax, [r12+rsi*8]
0x18003b35e  lea     rcx, [rbp+57h+var_A0]
0x18003b362  mov     r8, rdi
0x18003b365  movups  xmm0, xmmword ptr [rax]
0x18003b368  mov     [rbp+57h+var_84], 18h
0x18003b36f  mov     [rbp+57h+var_68], 0FFFFFFFFh
0x18003b376  movdqu  [rbp+57h+var_98], xmm0
0x18003b37b  call    FwppTlgFwpmFilterWriteEnum
0x18003b380  mov     rbx, rax
0x18003b383  test    rax, rax
0x18003b386  jnz     loc_18003B50E
0x18003b38c  lea     rdx, aItem; "item"
0x18003b393  mov     rcx, rdi
0x18003b396  call    FwppXmlWriteEndTag
0x18003b39b  mov     rbx, rax
0x18003b39e  test    rax, rax
0x18003b3a1  jnz     loc_18003B50E
0x18003b3a7  inc     esi
0x18003b3a9  jmp     loc_18003B2EA
0x18003b3ae  lea     rdx, aFwppxmlwriteFw_51; "FwppXmlWrite_FWPM_LAYER"
0x18003b3b5  mov     rcx, rax
0x18003b3b8  call    WfpReportError
0x18003b3bd  jmp     loc_18003B50E
0x18003b3c2  lea     rdx, aLayers; "layers"
0x18003b3c9  call    FwppXmlWriteEndTag
0x18003b3ce  mov     rbx, rax
0x18003b3d1  test    rax, rax
0x18003b3d4  jnz     loc_18003B50E
0x18003b3da  mov     r8, rdi
0x18003b3dd  call    FwppTlgFwpmProviderWriteEnum
0x18003b3e2  mov     rbx, rax
0x18003b3e5  test    rax, rax
0x18003b3e8  jnz     loc_18003B50E
0x18003b3ee  mov     r8, rdi
0x18003b3f1  call    FwppTlgFwpmProviderContextWriteEnum
0x18003b3f6  mov     rbx, rax
0x18003b3f9  test    rax, rax
0x18003b3fc  jnz     loc_18003B50E
0x18003b402  mov     r8, rdi
0x18003b405  call    FwppTlgFwpmSubLayerWriteEnum
0x18003b40a  mov     rbx, rax
0x18003b40d  test    rax, rax
0x18003b410  jnz     loc_18003B50E
0x18003b416  xor     r9d, r9d
0x18003b419  mov     [rsp+130h+var_110], rax
0x18003b41e  mov     r8d, r13d
0x18003b421  lea     rdx, aSubscriptions; "subscriptions"
0x18003b428  mov     rcx, rdi
0x18003b42b  call    FwppXmlWriteStartTagWithAttr
0x18003b430  mov     rbx, rax
0x18003b433  test    rax, rax
0x18003b436  jnz     loc_18003B50E
0x18003b43c  mov     rcx, rdi
0x18003b43f  call    FwppTlgFwpmCalloutWriteSubs
0x18003b444  mov     rbx, rax
0x18003b447  test    rax, rax
0x18003b44a  jnz     loc_18003B50E
0x18003b450  mov     rcx, rdi
0x18003b453  call    FwppTlgFwpmFilterWriteSubs
0x18003b458  mov     rbx, rax
0x18003b45b  test    rax, rax
0x18003b45e  jnz     loc_18003B50E
0x18003b464  mov     rcx, rdi
0x18003b467  call    FwppTlgFwpmNetEventWriteSubs
0x18003b46c  mov     rbx, rax
0x18003b46f  test    rax, rax
0x18003b472  jnz     loc_18003B50E
0x18003b478  mov     rcx, rdi
0x18003b47b  call    FwppTlgFwpmProviderWriteSubs
0x18003b480  mov     rbx, rax
0x18003b483  test    rax, rax
0x18003b486  jnz     loc_18003B50E
0x18003b48c  mov     rcx, rdi
0x18003b48f  call    FwppTlgFwpmProviderContextWriteSubs
0x18003b494  mov     rbx, rax
0x18003b497  test    rax, rax
0x18003b49a  jnz     short loc_18003B50E
0x18003b49c  mov     rcx, rdi
0x18003b49f  call    FwppTlgFwpmSubLayerWriteSubs
0x18003b4a4  mov     rbx, rax
0x18003b4a7  test    rax, rax
0x18003b4aa  jnz     short loc_18003B50E
0x18003b4ac  lea     rdx, aSubscriptions; "subscriptions"
0x18003b4b3  mov     rcx, rdi
0x18003b4b6  call    FwppXmlWriteEndTag
0x18003b4bb  mov     rbx, rax
0x18003b4be  test    rax, rax
0x18003b4c1  jnz     short loc_18003B50E
0x18003b4c3  mov     r8, rdi
0x18003b4c6  call    FwppTlgIPsecSaContextWriteEnum
0x18003b4cb  mov     rbx, rax
0x18003b4ce  test    rax, rax
0x18003b4d1  jnz     short loc_18003B50E
0x18003b4d3  mov     r8, rdi
0x18003b4d6  call    FwppTlgFwpsAleEndpointWriteEnum
0x18003b4db  mov     rbx, rax
0x18003b4de  test    rax, rax
0x18003b4e1  jnz     short loc_18003B50E
0x18003b4e3  xor     edx, edx
0x18003b4e5  lea     rcx, [rsp+130h+var_E0]
0x18003b4ea  call    BfeCallCommitEx
0x18003b4ef  lea     rcx, [rsp+130h+var_E0]
0x18003b4f4  call    BfeCallDestroy
0x18003b4f9  lea     rdx, aCurrentstate; "currentState"
0x18003b500  mov     rcx, rdi
0x18003b503  xor     r13d, r13d
0x18003b506  call    FwppXmlWriteEndTag
0x18003b50b  mov     rbx, rax
0x18003b50e  mov     rsi, [rsp+130h+var_F8]
0x18003b513  xor     edi, edi
0x18003b515  test    r14d, r14d
0x18003b518  jz      short loc_18003B52F
0x18003b51a  lea     rdx, [rsi+rdi*8]
0x18003b51e  mov     ecx, 3
0x18003b523  call    BfeObjectDestroyPublicState
0x18003b528  inc     edi
0x18003b52a  cmp     edi, r14d
0x18003b52d  jb      short loc_18003B51A
0x18003b52f  lea     rcx, [rsp+130h+var_F8]
0x18003b534  call    WfpMemFree
0x18003b539  test    r13d, r13d
0x18003b53c  jz      short loc_18003B554
0x18003b53e  xor     edx, edx
0x18003b540  lea     rcx, [rsp+130h+var_E0]
0x18003b545  call    BfeCallCommitEx
0x18003b54a  lea     rcx, [rsp+130h+var_E0]
0x18003b54f  call    BfeCallDestroy
0x18003b554  test    rbx, rbx
0x18003b557  jz      short loc_18003B568
0x18003b559  lea     rdx, aFwpptlgwritecu; "FwppTlgWriteCurrentState"
0x18003b560  mov     rcx, rbx
0x18003b563  call    WfpReportError
0x18003b568  mov     rax, rbx
0x18003b56b  mov     rcx, [rbp+57h+var_50]
0x18003b56f  xor     rcx, rsp; StackCookie
0x18003b572  call    __security_check_cookie
0x18003b577  add     rsp, 0F8h
0x18003b57e  pop     r15
0x18003b580  pop     r14
0x18003b582  pop     r13
0x18003b584  pop     r12
0x18003b586  pop     rdi
0x18003b587  pop     rsi
0x18003b588  pop     rbx
0x18003b589  pop     rbp
0x18003b58a  retn
```
