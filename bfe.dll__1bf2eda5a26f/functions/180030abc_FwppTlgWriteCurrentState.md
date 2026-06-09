# FwppTlgWriteCurrentState

- ea: `0x180030abc`
- end: `0x180030e95`
- name: `FwppTlgWriteCurrentState`
- size: `985`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800738a0`

## callees

- `0x180009aa0`
- `0x18000e000`
- `0x1800126e0`
- `0x180018b74`
- `0x18002fb9c`
- `0x18002fc60`
- `0x18002fd24`
- `0x180030960`
- `0x180030abc`
- `0x180032530`
- `0x180032620`
- `0x1800337f8`
- `0x180036f48`
- `0x1800495f0`
- `0x180055db4`
- `0x180058b30`
- `0x1800595ac`
- `0x180065128`
- `0x1800747d0`
- `0x180074894`
- `0x180074958`
- `0x180074ac0`
- `0x180074b84`
- `0x180074c48`
- `0x180074d40`
- `0x180074e9c`
- `0x180074f60`
- `0x180075024`
- `0x180075128`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180030b47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180030b47`

## string_xrefs

- `0x180030e63`: `FwppTlgWriteCurrentState`
- `0x180030cb8`: `FwppXmlWrite_FWPM_LAYER`

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
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-91h] BYREF
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
0x180030abc  push    rbp
0x180030abe  push    rbx
0x180030abf  push    rsi
0x180030ac0  push    rdi
0x180030ac1  push    r12
0x180030ac3  push    r13
0x180030ac5  push    r14
0x180030ac7  push    r15
0x180030ac9  lea     rbp, [rsp-1Fh]
0x180030ace  sub     rsp, 0F8h
0x180030ad5  mov     rax, cs:__security_cookie
0x180030adc  xor     rax, rsp
0x180030adf  mov     [rbp+57h+var_50], rax
0x180030ae3  xor     r13d, r13d
0x180030ae6  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180030aef  mov     rdi, rcx
0x180030af2  mov     [rsp+130h+var_F8], r13
0x180030af7  xorps   xmm0, xmm0
0x180030afa  lea     rcx, [rbp+57h+var_A0]; void *
0x180030afe  xor     eax, eax
0x180030b00  xor     r14d, r14d
0x180030b03  lea     r8d, [r13+48h]; Size
0x180030b07  mov     [rsp+130h+var_100], r14d
0x180030b0c  xor     edx, edx; Val
0x180030b0e  mov     [rbp+57h+var_B0], rax
0x180030b12  movups  [rbp+57h+var_C0], xmm0
0x180030b16  call    memset_0
0x180030b1b  xor     r9d, r9d
0x180030b1e  mov     [rsp+130h+var_110], r13
0x180030b23  lea     r8d, [r13+1]
0x180030b27  mov     rcx, rdi
0x180030b2a  lea     rdx, aCurrentstate; "currentState"
0x180030b31  call    FwppXmlWriteStartTagWithAttr
0x180030b36  mov     rbx, rax
0x180030b39  test    rax, rax
0x180030b3c  jnz     loc_180030E18
0x180030b42  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180030b47  call    cs:__imp_GetSystemTimeAsFileTime
0x180030b4d  lea     r8, [rsp+130h+SystemTimeAsFileTime]
0x180030b52  mov     rcx, rdi
0x180030b55  lea     rdx, aTimestamp; "timeStamp"
0x180030b5c  call    FwppXmlWrite_FILETIME
0x180030b61  mov     rbx, rax
0x180030b64  test    rax, rax
0x180030b67  jnz     loc_180030E18
0x180030b6d  mov     r8, rdi
0x180030b70  call    FwppTlgFwpmSessionWriteEnum
0x180030b75  mov     rbx, rax
0x180030b78  test    rax, rax
0x180030b7b  jnz     loc_180030E18
0x180030b81  xorps   xmm0, xmm0
0x180030b84  mov     [rsp+130h+var_F0], r13d
0x180030b89  lea     r9, [rsp+130h+var_E0]
0x180030b8e  lea     r8, [rsp+130h+var_F0]
0x180030b93  lea     ecx, [rax+2]
0x180030b96  movups  [rsp+130h+var_E0], xmm0
0x180030b9b  movups  [rbp+57h+var_D0], xmm0
0x180030b9f  call    BfeCallCreateSystem
0x180030ba4  mov     rbx, rax
0x180030ba7  test    rax, rax
0x180030baa  jnz     loc_180030E18
0x180030bb0  lea     r9, [rsp+130h+var_100]
0x180030bb5  lea     r8, [rsp+130h+var_F8]
0x180030bba  lea     r13d, [r14+1]
0x180030bbe  call    FwppTlgFwpmLayerEnumAll
0x180030bc3  mov     r14d, [rsp+130h+var_100]
0x180030bc8  mov     rbx, rax
0x180030bcb  test    rax, rax
0x180030bce  jnz     loc_180030E18
0x180030bd4  mov     r9d, r14d
0x180030bd7  lea     rdx, aLayers; "layers"
0x180030bde  mov     rcx, rdi
0x180030be1  call    FwppXmlWriteStartTagForArray
0x180030be6  mov     rbx, rax
0x180030be9  test    rax, rax
0x180030bec  jnz     loc_180030E18
0x180030bf2  xor     esi, esi
0x180030bf4  mov     rcx, rdi
0x180030bf7  cmp     esi, r14d
0x180030bfa  jnb     loc_180030CCC
0x180030c00  xor     r9d, r9d
0x180030c03  mov     [rsp+130h+var_110], 0
0x180030c0c  mov     r8d, r13d
0x180030c0f  lea     rdx, aItem; "item"
0x180030c16  call    FwppXmlWriteStartTagWithAttr
0x180030c1b  mov     rbx, rax
0x180030c1e  test    rax, rax
0x180030c21  jnz     loc_180030E18
0x180030c27  mov     r12, [rsp+130h+var_F8]
0x180030c2c  mov     r8, [r12+rsi*8]
0x180030c30  mov     rcx, rdi
0x180030c33  call    FwppXmlWrite_FWPM_LAYER0
0x180030c38  mov     rbx, rax
0x180030c3b  test    rax, rax
0x180030c3e  jnz     short loc_180030CB8
0x180030c40  mov     rax, [r12+rsi*8]
0x180030c44  lea     rcx, [rbp+57h+var_C0]
0x180030c48  mov     r8, rdi
0x180030c4b  movups  xmm0, xmmword ptr [rax]
0x180030c4e  movdqu  [rbp+57h+var_C0+8], xmm0
0x180030c53  call    FwppTlgFwpmCalloutWriteEnum
0x180030c58  mov     rbx, rax
0x180030c5b  test    rax, rax
0x180030c5e  jnz     loc_180030E18
0x180030c64  mov     rax, [r12+rsi*8]
0x180030c68  lea     rcx, [rbp+57h+var_A0]
0x180030c6c  mov     r8, rdi
0x180030c6f  movups  xmm0, xmmword ptr [rax]
0x180030c72  mov     [rbp+57h+var_84], 18h
0x180030c79  mov     [rbp+57h+var_68], 0FFFFFFFFh
0x180030c80  movdqu  [rbp+57h+var_98], xmm0
0x180030c85  call    FwppTlgFwpmFilterWriteEnum
0x180030c8a  mov     rbx, rax
0x180030c8d  test    rax, rax
0x180030c90  jnz     loc_180030E18
0x180030c96  lea     rdx, aItem; "item"
0x180030c9d  mov     rcx, rdi
0x180030ca0  call    FwppXmlWriteEndTag
0x180030ca5  mov     rbx, rax
0x180030ca8  test    rax, rax
0x180030cab  jnz     loc_180030E18
0x180030cb1  inc     esi
0x180030cb3  jmp     loc_180030BF4
0x180030cb8  lea     rdx, aFwppxmlwriteFw_51; "FwppXmlWrite_FWPM_LAYER"
0x180030cbf  mov     rcx, rax
0x180030cc2  call    WfpReportError
0x180030cc7  jmp     loc_180030E18
0x180030ccc  lea     rdx, aLayers; "layers"
0x180030cd3  call    FwppXmlWriteEndTag
0x180030cd8  mov     rbx, rax
0x180030cdb  test    rax, rax
0x180030cde  jnz     loc_180030E18
0x180030ce4  mov     r8, rdi
0x180030ce7  call    FwppTlgFwpmProviderWriteEnum
0x180030cec  mov     rbx, rax
0x180030cef  test    rax, rax
0x180030cf2  jnz     loc_180030E18
0x180030cf8  mov     r8, rdi
0x180030cfb  call    FwppTlgFwpmProviderContextWriteEnum
0x180030d00  mov     rbx, rax
0x180030d03  test    rax, rax
0x180030d06  jnz     loc_180030E18
0x180030d0c  mov     r8, rdi
0x180030d0f  call    FwppTlgFwpmSubLayerWriteEnum
0x180030d14  mov     rbx, rax
0x180030d17  test    rax, rax
0x180030d1a  jnz     loc_180030E18
0x180030d20  xor     r9d, r9d
0x180030d23  mov     [rsp+130h+var_110], rax
0x180030d28  mov     r8d, r13d
0x180030d2b  lea     rdx, aSubscriptions; "subscriptions"
0x180030d32  mov     rcx, rdi
0x180030d35  call    FwppXmlWriteStartTagWithAttr
0x180030d3a  mov     rbx, rax
0x180030d3d  test    rax, rax
0x180030d40  jnz     loc_180030E18
0x180030d46  mov     rcx, rdi
0x180030d49  call    FwppTlgFwpmCalloutWriteSubs
0x180030d4e  mov     rbx, rax
0x180030d51  test    rax, rax
0x180030d54  jnz     loc_180030E18
0x180030d5a  mov     rcx, rdi
0x180030d5d  call    FwppTlgFwpmFilterWriteSubs
0x180030d62  mov     rbx, rax
0x180030d65  test    rax, rax
0x180030d68  jnz     loc_180030E18
0x180030d6e  mov     rcx, rdi
0x180030d71  call    FwppTlgFwpmNetEventWriteSubs
0x180030d76  mov     rbx, rax
0x180030d79  test    rax, rax
0x180030d7c  jnz     loc_180030E18
0x180030d82  mov     rcx, rdi
0x180030d85  call    FwppTlgFwpmProviderWriteSubs
0x180030d8a  mov     rbx, rax
0x180030d8d  test    rax, rax
0x180030d90  jnz     loc_180030E18
0x180030d96  mov     rcx, rdi
0x180030d99  call    FwppTlgFwpmProviderContextWriteSubs
0x180030d9e  mov     rbx, rax
0x180030da1  test    rax, rax
0x180030da4  jnz     short loc_180030E18
0x180030da6  mov     rcx, rdi
0x180030da9  call    FwppTlgFwpmSubLayerWriteSubs
0x180030dae  mov     rbx, rax
0x180030db1  test    rax, rax
0x180030db4  jnz     short loc_180030E18
0x180030db6  lea     rdx, aSubscriptions; "subscriptions"
0x180030dbd  mov     rcx, rdi
0x180030dc0  call    FwppXmlWriteEndTag
0x180030dc5  mov     rbx, rax
0x180030dc8  test    rax, rax
0x180030dcb  jnz     short loc_180030E18
0x180030dcd  mov     r8, rdi
0x180030dd0  call    FwppTlgIPsecSaContextWriteEnum
0x180030dd5  mov     rbx, rax
0x180030dd8  test    rax, rax
0x180030ddb  jnz     short loc_180030E18
0x180030ddd  mov     r8, rdi
0x180030de0  call    FwppTlgFwpsAleEndpointWriteEnum
0x180030de5  mov     rbx, rax
0x180030de8  test    rax, rax
0x180030deb  jnz     short loc_180030E18
0x180030ded  xor     edx, edx
0x180030def  lea     rcx, [rsp+130h+var_E0]
0x180030df4  call    BfeCallCommitEx
0x180030df9  lea     rcx, [rsp+130h+var_E0]
0x180030dfe  call    BfeCallDestroy
0x180030e03  lea     rdx, aCurrentstate; "currentState"
0x180030e0a  mov     rcx, rdi
0x180030e0d  xor     r13d, r13d
0x180030e10  call    FwppXmlWriteEndTag
0x180030e15  mov     rbx, rax
0x180030e18  mov     rsi, [rsp+130h+var_F8]
0x180030e1d  xor     edi, edi
0x180030e1f  test    r14d, r14d
0x180030e22  jz      short loc_180030E39
0x180030e24  lea     rdx, [rsi+rdi*8]
0x180030e28  mov     ecx, 3
0x180030e2d  call    BfeObjectDestroyPublicState
0x180030e32  inc     edi
0x180030e34  cmp     edi, r14d
0x180030e37  jb      short loc_180030E24
0x180030e39  lea     rcx, [rsp+130h+var_F8]
0x180030e3e  call    WfpMemFree
0x180030e43  test    r13d, r13d
0x180030e46  jz      short loc_180030E5E
0x180030e48  xor     edx, edx
0x180030e4a  lea     rcx, [rsp+130h+var_E0]
0x180030e4f  call    BfeCallCommitEx
0x180030e54  lea     rcx, [rsp+130h+var_E0]
0x180030e59  call    BfeCallDestroy
0x180030e5e  test    rbx, rbx
0x180030e61  jz      short loc_180030E72
0x180030e63  lea     rdx, aFwpptlgwritecu; "FwppTlgWriteCurrentState"
0x180030e6a  mov     rcx, rbx
0x180030e6d  call    WfpReportError
0x180030e72  mov     rax, rbx
0x180030e75  mov     rcx, [rbp+57h+var_50]
0x180030e79  xor     rcx, rsp; StackCookie
0x180030e7c  call    __security_check_cookie
0x180030e81  add     rsp, 0F8h
0x180030e88  pop     r15
0x180030e8a  pop     r14
0x180030e8c  pop     r13
0x180030e8e  pop     r12
0x180030e90  pop     rdi
0x180030e91  pop     rsi
0x180030e92  pop     rbx
0x180030e93  pop     rbp
0x180030e94  retn
```
