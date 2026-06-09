# CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource(CTmClusterConfig *,ulong)

- ea: `0x18007d5b0`
- end: `0x18007d88f`
- name: `?Msg_GetTmResource@CTmClusterConfig_State_WaitForMsg@@UEAAXPEAVCTmClusterConfig@@K@Z`
- size: `735`
- prototype: `void(CTmClusterConfig_State_WaitForMsg *__hidden this, struct CTmClusterConfig *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001cf98`
- `0x180025104`
- `0x1800281b4`
- `0x18003a420`
- `0x18007d440`
- `0x18007d5b0`
- `0x1800846c0`
- `0x180085180`
- `0x1800857c0`
- `0x1800b83e2`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d819`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d819`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d763`
- `MTXCLU!MtxCluGetTmResource` at `0x18007d6e3`
- `MTXCLU!MtxCluGetTmResource` at `0x18007d6e3`

## string_xrefs

- `0x18007d7f4`: `com\complus\dtc\dtc\tm\src\tmclusterconfig.cpp`
- `0x18007d71d`: `CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource (com\complus\dtc\dtc\tm\src\tmclusterconfig.cpp@253): CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource - NULL != wszTmVirtualServerName`
- `0x18007d73c`: `CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource (com\complus\dtc\dtc\tm\src\tmclusterconfig.cpp@254): CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource - 0 != wcslen( wszTmVirtualServerName )`
- `0x18007d782`: `CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource (com\complus\dtc\dtc\tm\src\tmclusterconfig.cpp@260): CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource - NULL == wszTmVirtualServerName`

## pseudocode

```c
void __fastcall CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource(
        CTmClusterConfig_State_WaitForMsg *this,
        struct CTmClusterConfig *a2,
        unsigned int a3)
{
  void *v6; // r15
  CBadMsgHandler *v7; // rcx
  int NextVarItemWithinBounds; // edi
  int v9; // r8d
  char *v10; // r14
  unsigned int v11; // esi
  __int128 v12; // xmm6
  __int128 v13; // xmm7
  unsigned int v14; // r14d
  int v15; // eax
  unsigned int v16; // r14d
  __int64 v17; // rsi
  __int64 v18; // rax
  _OWORD *v19; // rax
  __int64 v20; // rcx
  void *v21; // rdx
  void *v22; // rcx
  unsigned int v23; // [rsp+30h] [rbp-81h]
  unsigned int v24; // [rsp+48h] [rbp-69h] BYREF
  void *Src; // [rsp+50h] [rbp-61h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-51h] BYREF
  void *v28; // [rsp+68h] [rbp-49h] BYREF
  unsigned __int16 *v29[2]; // [rsp+78h] [rbp-39h] BYREF
  void *v30[2]; // [rsp+88h] [rbp-29h] BYREF
  GUID Buf2; // [rsp+98h] [rbp-19h] BYREF

  v28 = 0;
  v29[0] = 0;
  v24 = 0;
  Buf2 = GUID_NULL;
  pv = 0;
  v6 = 0;
  Src = 0;
  CConnectionHelper::GetPtrToMessage(a2, &v28);
  if ( a3 < 0x28 )
  {
    NextVarItemWithinBounds = 0;
    v9 = 190;
LABEL_28:
    CBadMsgHandler::MessageLengthIncorrect(v7, "com\\complus\\dtc\\dtc\\tm\\src\\tmclusterconfig.cpp", v9, 2u, a3, v23);
    goto LABEL_29;
  }
  v10 = (char *)v28;
  v26 = a3 - 40;
  v30[0] = (char *)v28 + 40;
  NextVarItemWithinBounds = CTxStatusInfo::GetNextVarItemWithinBounds(v30, (void **)v29, &v24, &v26);
  if ( NextVarItemWithinBounds < 0 )
  {
    v9 = 211;
    goto LABEL_28;
  }
  if ( !v24 || (v7 = (CBadMsgHandler *)v29[0]) == 0 || !*v29[0] )
  {
    NextVarItemWithinBounds = -2147024809;
    v9 = 219;
    goto LABEL_28;
  }
  v11 = *(_DWORD *)v10;
  v12 = *(_OWORD *)(v10 + 4);
  v13 = *(_OWORD *)(v10 + 20);
  v14 = *((_DWORD *)v10 + 9);
  v15 = DuplicateString(v29[0], (unsigned __int16 **)&pv);
  v6 = pv;
  NextVarItemWithinBounds = v15;
  if ( v15 >= 0 )
  {
    *(_OWORD *)v30 = v13;
    *(_OWORD *)v29 = v12;
    NextVarItemWithinBounds = MtxCluGetTmResource(v11, v29, pv, v14, v30, &Src, &Buf2);
    if ( NextVarItemWithinBounds >= 0 )
    {
      v16 = 16;
      v17 = -1;
      if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
      {
        if ( Src )
          DtcInternalErrorW(
            L"CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource (com\\complus\\dtc\\dtc\\tm\\src\\tmclusterconfig.cpp@2"
             "60): CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource - NULL == wszTmVirtualServerName");
      }
      else
      {
        if ( !Src )
          DtcInternalErrorW(
            L"CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource (com\\complus\\dtc\\dtc\\tm\\src\\tmclusterconfig.cpp@2"
             "53): CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource - NULL != wszTmVirtualServerName");
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)Src + v18) );
        if ( !v18 )
          DtcInternalErrorW(
            L"CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource (com\\complus\\dtc\\dtc\\tm\\src\\tmclusterconfig.cpp@2"
             "54): CTmClusterConfig_State_WaitForMsg::Msg_GetTmResource - 0 != wcslen( wszTmVirtualServerName )");
        v16 = 4 * (((unsigned __int64)(unsigned int)(2 * v18 + 2) + 3) >> 2) + 20;
      }
      v19 = CoTaskMemAlloc(v16);
      *((_QWORD *)a2 + 8) = v19;
      if ( v19 )
      {
        *v19 = Buf2;
        if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
        {
          v20 = *((_QWORD *)a2 + 8);
          v21 = Src;
          do
            ++v17;
          while ( *((_WORD *)Src + v17) );
          *(_DWORD *)(v20 + 16) = 2 * v17 + 2;
          memcpy_0((void *)(v20 + 20), v21, (unsigned int)(2 * v17 + 2));
        }
        *((_DWORD *)a2 + 18) = v16;
      }
      else
      {
        NextVarItemWithinBounds = -2147024882;
      }
    }
  }
LABEL_29:
  CConnectionHelper::ReleaseMessage(a2, v28);
  CoTaskMemFree(v6);
  CoTaskMemFree(Src);
  if ( NextVarItemWithinBounds < 0 )
  {
    v22 = (void *)*((_QWORD *)a2 + 8);
    *((_DWORD *)a2 + 19) = NextVarItemWithinBounds;
    CoTaskMemFree(v22);
    *((_QWORD *)a2 + 8) = 0;
    *((_DWORD *)a2 + 18) = 0;
  }
  (*(void (__fastcall **)(CTmClusterConfig_State_WaitForMsg *, struct CTmClusterConfig *))(*(_QWORD *)this + 48LL))(
    this,
    a2);
  *((_QWORD *)a2 + 6) = g_CTmClusterConfig_State_QueueingResponse;
  CTmClusterConfig_State_QueueingResponse::Enter_State(
    (CTmClusterConfig_State_QueueingResponse *)g_CTmClusterConfig_State_QueueingResponse,
    a2);
}

```

## disassembly

```asm
0x18007d5b0  mov     rax, rsp
0x18007d5b3  mov     [rax+20h], rbx
0x18007d5b7  push    rbp
0x18007d5b8  push    rsi
0x18007d5b9  push    rdi
0x18007d5ba  push    r12
0x18007d5bc  push    r13
0x18007d5be  push    r14
0x18007d5c0  push    r15
0x18007d5c2  lea     rbp, [rax-5Fh]
0x18007d5c6  sub     rsp, 0D0h
0x18007d5cd  movaps  xmmword ptr [rax-48h], xmm6
0x18007d5d1  movaps  xmmword ptr [rax-58h], xmm7
0x18007d5d5  mov     rax, cs:__security_cookie
0x18007d5dc  xor     rax, rsp
0x18007d5df  mov     [rbp+57h+var_60], rax
0x18007d5e3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007d5ea  xor     r13d, r13d
0x18007d5ed  mov     rbx, rdx
0x18007d5f0  mov     r12, rcx
0x18007d5f3  mov     [rbp+57h+var_A0], r13
0x18007d5f7  lea     rdx, [rbp+57h+var_A0]; void **
0x18007d5fb  mov     [rbp+57h+var_90], r13
0x18007d5ff  mov     rcx, rbx; this
0x18007d602  mov     [rbp+57h+var_C0], r13d
0x18007d606  movdqu  [rbp+57h+Buf2], xmm0
0x18007d60b  mov     esi, r8d
0x18007d60e  mov     [rbp+57h+pv], r13
0x18007d612  mov     r15d, r13d
0x18007d615  mov     [rbp+57h+Src], r13
0x18007d619  call    ?GetPtrToMessage@CConnectionHelper@@QEAAXPEAPEAX@Z; CConnectionHelper::GetPtrToMessage(void * *)
0x18007d61e  cmp     esi, 28h ; '('
0x18007d621  jnb     short loc_18007D631
0x18007d623  mov     edi, r13d
0x18007d626  mov     r8d, 0BEh
0x18007d62c  jmp     loc_18007D7EA
0x18007d631  mov     r14, [rbp+57h+var_A0]
0x18007d635  lea     eax, [rsi-28h]
0x18007d638  mov     [rbp+57h+var_B0], eax
0x18007d63b  lea     r9, [rbp+57h+var_B0]; unsigned int *
0x18007d63f  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x18007d643  lea     rdx, [rbp+57h+var_90]; void **
0x18007d647  lea     rax, [r14+28h]
0x18007d64b  lea     rcx, [rbp+57h+var_80]; void **
0x18007d64f  mov     [rbp+57h+var_80], rax
0x18007d653  call    ?GetNextVarItemWithinBounds@CTxStatusInfo@@SAJPEAPEAX0PEAK1@Z; CTxStatusInfo::GetNextVarItemWithinBounds(void * *,void * *,ulong *,ulong *)
0x18007d658  mov     edi, eax
0x18007d65a  test    eax, eax
0x18007d65c  jns     short loc_18007D669
0x18007d65e  mov     r8d, 0D3h
0x18007d664  jmp     loc_18007D7EA
0x18007d669  cmp     [rbp+57h+var_C0], r13d
0x18007d66d  jz      loc_18007D7DF
0x18007d673  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x18007d677  test    rcx, rcx
0x18007d67a  jz      loc_18007D7DF
0x18007d680  cmp     r13w, [rcx]
0x18007d684  jz      loc_18007D7DF
0x18007d68a  mov     esi, [r14]
0x18007d68d  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x18007d691  movups  xmm6, xmmword ptr [r14+4]
0x18007d696  movups  xmm7, xmmword ptr [r14+14h]
0x18007d69b  mov     r14d, [r14+24h]
0x18007d69f  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18007d6a4  mov     r15, [rbp+57h+pv]
0x18007d6a8  mov     edi, eax
0x18007d6aa  test    eax, eax
0x18007d6ac  js      loc_18007D800
0x18007d6b2  lea     rax, [rbp+57h+Buf2]
0x18007d6b6  movdqa  xmmword ptr [rbp+57h+var_80], xmm7
0x18007d6bb  mov     [rsp+100h+var_D0], rax
0x18007d6c0  lea     rdx, [rbp+57h+var_90]
0x18007d6c4  lea     rax, [rbp+57h+Src]
0x18007d6c8  movdqa  xmmword ptr [rbp+57h+var_90], xmm6
0x18007d6cd  mov     [rsp+100h+var_D8], rax
0x18007d6d2  mov     r9d, r14d
0x18007d6d5  lea     rax, [rbp+57h+var_80]
0x18007d6d9  mov     r8, r15
0x18007d6dc  mov     ecx, esi
0x18007d6de  mov     qword ptr [rsp+100h+var_E0], rax
0x18007d6e3  call    cs:__imp_MtxCluGetTmResource
0x18007d6e9  mov     edi, eax
0x18007d6eb  test    eax, eax
0x18007d6ed  js      loc_18007D800
0x18007d6f3  mov     r14d, 10h
0x18007d6f9  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18007d6fd  mov     r8d, r14d; Size
0x18007d700  lea     rcx, GUID_NULL; Buf1
0x18007d707  call    memcmp_0
0x18007d70c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007d710  test    eax, eax
0x18007d712  jz      short loc_18007D77C
0x18007d714  mov     rcx, [rbp+57h+Src]
0x18007d718  test    rcx, rcx
0x18007d71b  jnz     short loc_18007D72A
0x18007d71d  lea     rcx, aCtmclusterconf_2; "CTmClusterConfig_State_WaitForMsg::Msg_"...
0x18007d724  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18007d72a  mov     rax, rsi
0x18007d72d  inc     rax
0x18007d730  cmp     [rcx+rax*2], r13w
0x18007d735  jnz     short loc_18007D72D
0x18007d737  test    rax, rax
0x18007d73a  jnz     short loc_18007D749
0x18007d73c  lea     rcx, aCtmclusterconf; "CTmClusterConfig_State_WaitForMsg::Msg_"...
0x18007d743  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18007d749  lea     ecx, ds:2[rax*2]
0x18007d750  add     rcx, 3
0x18007d754  shr     rcx, 2
0x18007d758  lea     r14d, ds:14h[rcx*4]
0x18007d760  mov     ecx, r14d; cb
0x18007d763  call    cs:__imp_CoTaskMemAlloc
0x18007d769  mov     [rbx+40h], rax
0x18007d76d  test    rax, rax
0x18007d770  jnz     short loc_18007D78F
0x18007d772  mov     edi, 8007000Eh
0x18007d777  jmp     loc_18007D800
0x18007d77c  cmp     [rbp+57h+Src], r13
0x18007d780  jz      short loc_18007D760
0x18007d782  lea     rcx, aCtmclusterconf_1; "CTmClusterConfig_State_WaitForMsg::Msg_"...
0x18007d789  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18007d78f  movups  xmm0, [rbp+57h+Buf2]
0x18007d793  mov     r8d, 10h; Size
0x18007d799  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18007d79d  lea     rcx, GUID_NULL; Buf1
0x18007d7a4  movdqu  xmmword ptr [rax], xmm0
0x18007d7a8  call    memcmp_0
0x18007d7ad  test    eax, eax
0x18007d7af  jz      short loc_18007D7D9
0x18007d7b1  mov     rcx, [rbx+40h]
0x18007d7b5  mov     rdx, [rbp+57h+Src]; Src
0x18007d7b9  inc     rsi
0x18007d7bc  cmp     [rdx+rsi*2], r13w
0x18007d7c1  jnz     short loc_18007D7B9
0x18007d7c3  lea     eax, ds:2[rsi*2]
0x18007d7ca  mov     [rcx+10h], eax
0x18007d7cd  add     rcx, 14h; void *
0x18007d7d1  mov     r8d, eax; Size
0x18007d7d4  call    memcpy_0
0x18007d7d9  mov     [rbx+48h], r14d
0x18007d7dd  jmp     short loc_18007D800
0x18007d7df  mov     edi, 80070057h
0x18007d7e4  mov     r8d, 0DBh; int
0x18007d7ea  mov     r9d, 2; unsigned __int16
0x18007d7f0  mov     [rsp+100h+var_E0], esi; unsigned int
0x18007d7f4  lea     rdx, aComComplusDtcD_104; "com\\complus\\dtc\\dtc\\tm\\src\\tmclus"...
0x18007d7fb  call    ?MessageLengthIncorrect@CBadMsgHandler@@QEAAXPEBDHGKK@Z; CBadMsgHandler::MessageLengthIncorrect(char const *,int,ushort,ulong,ulong)
0x18007d800  mov     rdx, [rbp+57h+var_A0]; void *
0x18007d804  mov     rcx, rbx; this
0x18007d807  call    ?ReleaseMessage@CConnectionHelper@@QEAAXPEAX@Z; CConnectionHelper::ReleaseMessage(void *)
0x18007d80c  mov     rcx, r15; pv
0x18007d80f  call    cs:__imp_CoTaskMemFree
0x18007d815  mov     rcx, [rbp+57h+Src]; pv
0x18007d819  call    cs:__imp_CoTaskMemFree
0x18007d81f  test    edi, edi
0x18007d821  jns     short loc_18007D838
0x18007d823  mov     rcx, [rbx+40h]; pv
0x18007d827  mov     [rbx+4Ch], edi
0x18007d82a  call    cs:__imp_CoTaskMemFree
0x18007d830  mov     [rbx+40h], r13
0x18007d834  mov     [rbx+48h], r13d
0x18007d838  mov     rax, [r12]
0x18007d83c  mov     rdx, rbx
0x18007d83f  mov     rcx, r12
0x18007d842  mov     rax, [rax+30h]
0x18007d846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d84b  lea     rcx, ?g_CTmClusterConfig_State_QueueingResponse@@3VCTmClusterConfig_State_QueueingResponse@@A; this
0x18007d852  mov     rdx, rbx; struct CTmClusterConfig *
0x18007d855  mov     [rbx+30h], rcx
0x18007d859  call    ?Enter_State@CTmClusterConfig_State_QueueingResponse@@UEAAXPEAVCTmClusterConfig@@@Z; CTmClusterConfig_State_QueueingResponse::Enter_State(CTmClusterConfig *)
0x18007d85e  mov     rcx, [rbp+57h+var_60]
0x18007d862  xor     rcx, rsp; StackCookie
0x18007d865  call    __security_check_cookie
0x18007d86a  lea     r11, [rsp+100h+var_30]
0x18007d872  mov     rbx, [r11+58h]
0x18007d876  movaps  xmm6, xmmword ptr [r11-10h]
0x18007d87b  movaps  xmm7, xmmword ptr [r11-20h]
0x18007d880  mov     rsp, r11
0x18007d883  pop     r15
0x18007d885  pop     r14
0x18007d887  pop     r13
0x18007d889  pop     r12
0x18007d88b  pop     rdi
0x18007d88c  pop     rsi
0x18007d88d  pop     rbp
0x18007d88e  retn
```
