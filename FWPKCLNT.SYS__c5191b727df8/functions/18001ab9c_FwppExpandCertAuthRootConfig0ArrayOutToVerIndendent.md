# FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent

- ea: `0x18001ab9c`
- end: `0x18001aff4`
- name: `FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent`
- size: `1112`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014d58`

## callees

- `0x180008480`
- `0x18000891c`
- `0x18000c9b4`
- `0x18000df5c`
- `0x180011d88`
- `0x18001a0b4`
- `0x18001a744`
- `0x18001ab9c`
- `0x18001affc`
- `0x18001b1e4`
- `0x18001f950`
- `0x1800208c0`

## string_xrefs

- `0x18001ae1c`: `The orderedCriteria weight is larger than the max config weight`
- `0x18001aeef`: `FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent`
- `0x18001afc9`: `FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent`

## pseudocode

```c
__int64 __fastcall FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int *a4,
        _QWORD *a5)
{
  int v5; // r13d
  _DWORD *v6; // rbx
  unsigned int v7; // r14d
  __int64 v10; // rbp
  unsigned int v11; // esi
  int v12; // edi
  unsigned int i; // edi
  unsigned int j; // edi
  unsigned int k; // edi
  char *v16; // r15
  unsigned int v17; // r12d
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int m; // r11d
  unsigned int n; // r8d
  unsigned int ii; // r10d
  __int64 v22; // rdi
  unsigned __int64 v23; // r9
  int v24; // r12d
  unsigned int v25; // edx
  unsigned __int64 v26; // r15
  __int64 v27; // r8
  char *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // xmm1_8
  __int64 v31; // rcx
  unsigned int jj; // edi
  int v33; // eax
  unsigned int v34; // r15d
  __int64 v35; // rsi
  char *v36; // rsi
  unsigned int kk; // r15d
  __int64 v38; // rcx
  unsigned int v40; // [rsp+20h] [rbp-58h]
  void *v41; // [rsp+28h] [rbp-50h] BYREF
  void *v42[9]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v43; // [rsp+80h] [rbp+8h]

  v5 = 0;
  *a4 = 0;
  v6 = 0;
  v7 = a1;
  v42[0] = 0;
  *a5 = 0;
  v10 = 0;
  v41 = 0;
  if ( !(_DWORD)a1 )
    goto LABEL_48;
  v10 = WfpPoolAllocNonPaged(16LL * (unsigned int)a1, 1886418758, v42);
  if ( v10 )
  {
    v6 = v42[0];
    goto LABEL_48;
  }
  v6 = v42[0];
  v11 = 0;
  memset(v42[0], 0, 16LL * v7);
  if ( a3 )
  {
    v12 = a3 - 1;
    if ( v12 )
    {
      if ( v12 == 1 )
      {
        for ( i = 0; i < v7; ++i )
        {
          v10 = FwppExpandIkeV2OutboundRootConfigToCriteria(a2 + 24LL * i, &v6[4 * i]);
          if ( v10 )
            goto LABEL_46;
          v11 += v6[4 * i];
        }
      }
    }
    else
    {
      for ( j = 0; j < v7; ++j )
      {
        v10 = FwppExpandAuthIpOutboundRootConfigToCriteria(a2 + 24LL * j, &v6[4 * j]);
        if ( v10 )
          goto LABEL_46;
        v11 += v6[4 * j];
      }
    }
  }
  else
  {
    for ( k = 0; k < v7; ++k )
    {
      v10 = FwppExpandIkeOutboundRootConfigToCriteria(a2 + 24LL * k, &v6[4 * k]);
      if ( v10 )
        goto LABEL_46;
      v11 += v6[4 * k];
    }
  }
  v10 = WfpPoolAllocNonPaged(56LL * v11, 1886418758, &v41);
  if ( v10 )
  {
LABEL_48:
    jj = 0;
    if ( v7 )
      goto LABEL_49;
    goto LABEL_62;
  }
  v16 = (char *)v41;
  v43 = 0;
  v17 = 0;
  memset(v41, 0, 56LL * v11);
  if ( (WPP_MAIN_CB.ActiveThreadCount & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = WPP_MAIN_CB.ActiveThreadCount & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BugFix_BfeTvs__private_IsEnabledDeviceUsageNoInline();
  if ( !IsEnabledDeviceUsageNoInline )
  {
    for ( m = 0; m < 6; ++m )
    {
      for ( n = 0; n < v7; ++n )
      {
        for ( ii = 0; ii < v6[4 * n]; ++ii )
        {
          v22 = *(_QWORD *)&v6[4 * n + 2];
          v23 = (unsigned __int64)ii << 6;
          if ( *(unsigned __int16 *)(v23 + v22 + 56) == m )
          {
            a1 = 56LL * v17++;
            *(_OWORD *)&v16[a1] = *(_OWORD *)(v23 + v22);
            *(_OWORD *)&v16[a1 + 16] = *(_OWORD *)(v23 + v22 + 16);
            *(_OWORD *)&v16[a1 + 32] = *(_OWORD *)(v23 + v22 + 32);
            *(_QWORD *)&v16[a1 + 48] = *(_QWORD *)(v23 + v22 + 48);
          }
        }
      }
    }
LABEL_44:
    *a4 = v11;
    *a5 = v16;
    goto LABEL_48;
  }
  a1 = 6;
  while ( 1 )
  {
    v24 = 0;
    if ( v7 )
      break;
LABEL_43:
    if ( (unsigned int)++v5 >= 6 )
      goto LABEL_44;
  }
  while ( 1 )
  {
    if ( *(_QWORD *)&v6[4 * v24 + 2] )
    {
      v25 = 0;
      v40 = 0;
      if ( v6[4 * v24] )
        break;
    }
LABEL_42:
    if ( ++v24 >= v7 )
      goto LABEL_43;
  }
  while ( 1 )
  {
    v26 = (unsigned __int64)v25 << 6;
    if ( *(_WORD *)(v26 + *(_QWORD *)&v6[4 * v24 + 2] + 56) >= 6u )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("The orderedCriteria weight is larger than the max config weight");
      v25 = v40;
    }
    v27 = *(_QWORD *)&v6[4 * v24 + 2];
    if ( *(unsigned __int16 *)(v26 + v27 + 56) != v5 )
    {
      v16 = (char *)v41;
      goto LABEL_41;
    }
    if ( v43 >= v11 )
      break;
    v28 = (char *)v41;
    v29 = 56LL * v43++;
    *(_OWORD *)((char *)v41 + v29) = *(_OWORD *)(v26 + v27);
    *(_OWORD *)&v28[v29 + 16] = *(_OWORD *)(v26 + v27 + 16);
    *(_OWORD *)&v28[v29 + 32] = *(_OWORD *)(v26 + v27 + 32);
    v30 = *(_QWORD *)(v26 + v27 + 48);
    v16 = v28;
    *(_QWORD *)&v28[v29 + 48] = v30;
LABEL_41:
    ++v25;
    a1 = 6;
    v40 = v25;
    if ( v25 >= v6[4 * v24] )
      goto LABEL_42;
  }
  MicrosoftTelemetryAssertTriggeredMsgKM("count1 is not less than count");
  v10 = WfpReportSysErrorAsHResult(v31, "FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent", 2147942487LL);
LABEL_46:
  for ( jj = 0; jj < v7; ++jj )
  {
LABEL_49:
    if ( v10 )
    {
      if ( (WPP_MAIN_CB.ActiveThreadCount & 0x10) != 0 )
        v33 = WPP_MAIN_CB.ActiveThreadCount & 1;
      else
        v33 = Feature_BugFix_BfeTvs__private_IsEnabledDeviceUsageNoInline();
      if ( v33 )
      {
        if ( v6 )
        {
          v36 = (char *)&v6[4 * jj];
          if ( *((_QWORD *)v36 + 1) )
          {
            for ( kk = 0; kk < *(_DWORD *)v36; ++kk )
              FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0(*((_QWORD *)v36 + 1) + ((unsigned __int64)kk << 6));
          }
        }
      }
      else
      {
        v34 = 0;
        v35 = 4LL * jj;
        if ( v6[v35] )
        {
          do
            FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0(*(_QWORD *)&v6[v35 + 2] + ((unsigned __int64)v34++ << 6));
          while ( v34 < v6[v35] );
        }
      }
    }
    WfpNamedPoolFree(a1, (PVOID *)&v6[4 * jj + 2]);
  }
LABEL_62:
  WfpNamedPoolFree(a1, v42);
  if ( v10 )
  {
    WfpNamedPoolFree(v38, &v41);
    WfpReportError(v10, (int)"FwppExpandCertAuthRootConfig0ArrayOutToVerIndendent");
  }
  return v10;
}

```

## disassembly

```asm
0x18001ab9c  mov     r11, rsp
0x18001ab9f  mov     [r11+10h], rbx
0x18001aba3  mov     [r11+20h], r9
0x18001aba7  push    rbp
0x18001aba8  push    rsi
0x18001aba9  push    rdi
0x18001abaa  push    r12
0x18001abac  push    r13
0x18001abae  push    r14
0x18001abb0  push    r15
0x18001abb2  sub     rsp, 40h
0x18001abb6  mov     rax, [rsp+78h+arg_20]
0x18001abbe  xor     r13d, r13d
0x18001abc1  mov     [r9], r13d
0x18001abc4  mov     ebx, r13d
0x18001abc7  mov     r14d, ecx
0x18001abca  mov     edi, r8d
0x18001abcd  mov     [r11-48h], rbx
0x18001abd1  mov     r12, rdx
0x18001abd4  mov     [rax], r13
0x18001abd7  mov     ebp, r13d
0x18001abda  mov     [r11-50h], r13
0x18001abde  test    ecx, ecx
0x18001abe0  jz      loc_18001AF0B
0x18001abe6  mov     ebx, r14d
0x18001abe9  lea     r8, [r11-48h]
0x18001abed  shl     rbx, 4
0x18001abf1  mov     edx, 70707746h
0x18001abf6  mov     rcx, rbx
0x18001abf9  call    WfpPoolAllocNonPaged
0x18001abfe  mov     rbp, rax
0x18001ac01  test    rax, rax
0x18001ac04  jnz     loc_18001AF06
0x18001ac0a  mov     r8, rbx; Size
0x18001ac0d  xor     edx, edx; Val
0x18001ac0f  mov     rbx, [rsp+78h+var_48]
0x18001ac14  mov     esi, r13d
0x18001ac17  mov     rcx, rbx; void *
0x18001ac1a  call    memset
0x18001ac1f  test    edi, edi
0x18001ac21  jz      loc_18001ACB1
0x18001ac27  sub     edi, 1
0x18001ac2a  jz      short loc_18001AC75
0x18001ac2c  cmp     edi, 1
0x18001ac2f  jnz     loc_18001ACEB
0x18001ac35  mov     edi, r13d
0x18001ac38  test    r14d, r14d
0x18001ac3b  jz      loc_18001ACEB
0x18001ac41  mov     ecx, edi
0x18001ac43  mov     r15d, edi
0x18001ac46  shl     r15, 4
0x18001ac4a  add     r15, rbx
0x18001ac4d  lea     rax, [rcx+rcx*2]
0x18001ac51  mov     rdx, r15
0x18001ac54  lea     rcx, [r12+rax*8]
0x18001ac58  call    FwppExpandIkeV2OutboundRootConfigToCriteria
0x18001ac5d  mov     rbp, rax
0x18001ac60  test    rax, rax
0x18001ac63  jnz     loc_18001AF01
0x18001ac69  add     esi, [r15]
0x18001ac6c  inc     edi
0x18001ac6e  cmp     edi, r14d
0x18001ac71  jb      short loc_18001AC41
0x18001ac73  jmp     short loc_18001ACEB
0x18001ac75  mov     edi, r13d
0x18001ac78  test    r14d, r14d
0x18001ac7b  jz      short loc_18001ACEB
0x18001ac7d  mov     ecx, edi
0x18001ac7f  mov     r15d, edi
0x18001ac82  shl     r15, 4
0x18001ac86  add     r15, rbx
0x18001ac89  lea     rax, [rcx+rcx*2]
0x18001ac8d  mov     rdx, r15
0x18001ac90  lea     rcx, [r12+rax*8]
0x18001ac94  call    FwppExpandAuthIpOutboundRootConfigToCriteria
0x18001ac99  mov     rbp, rax
0x18001ac9c  test    rax, rax
0x18001ac9f  jnz     loc_18001AF01
0x18001aca5  add     esi, [r15]
0x18001aca8  inc     edi
0x18001acaa  cmp     edi, r14d
0x18001acad  jb      short loc_18001AC7D
0x18001acaf  jmp     short loc_18001ACEB
0x18001acb1  mov     edi, r13d
0x18001acb4  test    r14d, r14d
0x18001acb7  jz      short loc_18001ACEB
0x18001acb9  mov     ecx, edi
0x18001acbb  mov     r15d, edi
0x18001acbe  shl     r15, 4
0x18001acc2  add     r15, rbx
0x18001acc5  lea     rax, [rcx+rcx*2]
0x18001acc9  mov     rdx, r15
0x18001accc  lea     rcx, [r12+rax*8]
0x18001acd0  call    FwppExpandIkeOutboundRootConfigToCriteria
0x18001acd5  mov     rbp, rax
0x18001acd8  test    rax, rax
0x18001acdb  jnz     loc_18001AF01
0x18001ace1  add     esi, [r15]
0x18001ace4  inc     edi
0x18001ace6  cmp     edi, r14d
0x18001ace9  jb      short loc_18001ACB9
0x18001aceb  mov     eax, esi
0x18001aced  lea     r8, [rsp+78h+var_50]
0x18001acf2  imul    rdi, rax, 38h ; '8'
0x18001acf6  mov     edx, 70707746h
0x18001acfb  mov     rcx, rdi
0x18001acfe  call    WfpPoolAllocNonPaged
0x18001ad03  mov     rbp, rax
0x18001ad06  test    rax, rax
0x18001ad09  jnz     loc_18001AF0B
0x18001ad0f  mov     r15, [rsp+78h+var_50]
0x18001ad14  mov     r8, rdi; Size
0x18001ad17  mov     rcx, r15; void *
0x18001ad1a  mov     [rsp+78h+arg_0], r13d
0x18001ad22  xor     edx, edx; Val
0x18001ad24  mov     r12d, r13d
0x18001ad27  call    memset
0x18001ad2c  mov     eax, cs:WPP_MAIN_CB.ActiveThreadCount
0x18001ad32  test    al, 10h
0x18001ad34  jz      short loc_18001AD3B
0x18001ad36  and     eax, 1
0x18001ad39  jmp     short loc_18001AD40
0x18001ad3b  call    Feature_BugFix_BfeTvs__private_IsEnabledDeviceUsageNoInline
0x18001ad40  test    eax, eax
0x18001ad42  jnz     loc_18001ADD6
0x18001ad48  mov     r11d, r13d
0x18001ad4b  mov     r8d, r13d
0x18001ad4e  test    r14d, r14d
0x18001ad51  jz      short loc_18001ADC4
0x18001ad53  mov     edx, r8d
0x18001ad56  mov     r10d, r13d
0x18001ad59  add     rdx, rdx
0x18001ad5c  cmp     [rbx+rdx*8], r13d
0x18001ad60  jbe     short loc_18001ADBC
0x18001ad62  mov     rdi, [rbx+rdx*8+8]
0x18001ad67  mov     r9d, r10d
0x18001ad6a  shl     r9, 6
0x18001ad6e  movzx   eax, word ptr [r9+rdi+38h]
0x18001ad74  cmp     eax, r11d
0x18001ad77  jnz     short loc_18001ADB3
0x18001ad79  movups  xmm0, xmmword ptr [r9+rdi]
0x18001ad7e  mov     eax, r12d
0x18001ad81  imul    rcx, rax, 38h ; '8'
0x18001ad85  inc     r12d
0x18001ad88  movups  xmmword ptr [rcx+r15], xmm0
0x18001ad8d  movups  xmm1, xmmword ptr [r9+rdi+10h]
0x18001ad93  movups  xmmword ptr [rcx+r15+10h], xmm1
0x18001ad99  movups  xmm0, xmmword ptr [r9+rdi+20h]
0x18001ad9f  movups  xmmword ptr [rcx+r15+20h], xmm0
0x18001ada5  movsd   xmm1, qword ptr [r9+rdi+30h]
0x18001adac  movsd   qword ptr [rcx+r15+30h], xmm1
0x18001adb3  inc     r10d
0x18001adb6  cmp     r10d, [rbx+rdx*8]
0x18001adba  jb      short loc_18001AD62
0x18001adbc  inc     r8d
0x18001adbf  cmp     r8d, r14d
0x18001adc2  jb      short loc_18001AD53
0x18001adc4  inc     r11d
0x18001adc7  cmp     r11d, 6
0x18001adcb  jb      loc_18001AD4B
0x18001add1  jmp     loc_18001AEC6
0x18001add6  mov     ecx, 6
0x18001addb  xor     r12d, r12d
0x18001adde  test    r14d, r14d
0x18001ade1  jz      loc_18001AEB7
0x18001ade7  mov     edi, r12d
0x18001adea  add     rdi, rdi
0x18001aded  cmp     qword ptr [rbx+rdi*8+8], 0
0x18001adf3  jz      loc_18001AEAB
0x18001adf9  xor     edx, edx
0x18001adfb  mov     [rsp+78h+var_58], edx
0x18001adff  cmp     [rbx+rdi*8], edx
0x18001ae02  jbe     loc_18001AEAB
0x18001ae08  mov     rax, [rbx+rdi*8+8]
0x18001ae0d  mov     r15d, edx
0x18001ae10  shl     r15, 6
0x18001ae14  cmp     [r15+rax+38h], cx
0x18001ae1a  jb      short loc_18001AE2C
0x18001ae1c  lea     rcx, aTheOrderedcrit; "The orderedCriteria weight is larger th"...
0x18001ae23  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x18001ae28  mov     edx, [rsp+78h+var_58]
0x18001ae2c  mov     r8, [rbx+rdi*8+8]
0x18001ae31  movzx   eax, word ptr [r15+r8+38h]
0x18001ae37  cmp     eax, r13d
0x18001ae3a  jnz     short loc_18001AE92
0x18001ae3c  mov     r9d, [rsp+78h+arg_0]
0x18001ae44  cmp     r9d, esi
0x18001ae47  jnb     loc_18001AEDD
0x18001ae4d  movups  xmm0, xmmword ptr [r15+r8]
0x18001ae52  mov     rax, [rsp+78h+var_50]
0x18001ae57  imul    rcx, r9, 38h ; '8'
0x18001ae5b  inc     r9d
0x18001ae5e  mov     [rsp+78h+arg_0], r9d
0x18001ae66  movups  xmmword ptr [rcx+rax], xmm0
0x18001ae6a  movups  xmm1, xmmword ptr [r15+r8+10h]
0x18001ae70  movups  xmmword ptr [rcx+rax+10h], xmm1
0x18001ae75  movups  xmm0, xmmword ptr [r15+r8+20h]
0x18001ae7b  movups  xmmword ptr [rcx+rax+20h], xmm0
0x18001ae80  movsd   xmm1, qword ptr [r15+r8+30h]
0x18001ae87  mov     r15, rax
0x18001ae8a  movsd   qword ptr [rcx+rax+30h], xmm1
0x18001ae90  jmp     short loc_18001AE97
0x18001ae92  mov     r15, [rsp+78h+var_50]
0x18001ae97  inc     edx
0x18001ae99  mov     ecx, 6
0x18001ae9e  mov     [rsp+78h+var_58], edx
0x18001aea2  cmp     edx, [rbx+rdi*8]
0x18001aea5  jb      loc_18001AE08
0x18001aeab  inc     r12d
0x18001aeae  cmp     r12d, r14d
0x18001aeb1  jb      loc_18001ADE7
0x18001aeb7  inc     r13d
0x18001aeba  cmp     r13d, ecx
0x18001aebd  jb      loc_18001ADDB
0x18001aec3  xor     r13d, r13d
0x18001aec6  mov     rax, [rsp+78h+arg_18]
0x18001aece  mov     [rax], esi
0x18001aed0  mov     rax, [rsp+78h+arg_20]
0x18001aed8  mov     [rax], r15
0x18001aedb  jmp     short loc_18001AF0B
0x18001aedd  lea     rcx, aCount1IsNotLes; "count1 is not less than count"
0x18001aee4  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x18001aee9  mov     r8d, 80070057h
0x18001aeef  lea     rdx, aFwppexpandcert_0; "FwppExpandCertAuthRootConfig0ArrayOutTo"...
0x18001aef6  call    WfpReportSysErrorAsHResult
0x18001aefb  mov     rbp, rax
0x18001aefe  xor     r13d, r13d
0x18001af01  mov     edi, r13d
0x18001af04  jmp     short loc_18001AF17
0x18001af06  mov     rbx, [rsp+78h+var_48]
0x18001af0b  mov     edi, r13d
0x18001af0e  test    r14d, r14d
0x18001af11  jz      loc_18001AFB0
0x18001af17  test    rbp, rbp
0x18001af1a  jz      short loc_18001AF93
0x18001af1c  mov     eax, cs:WPP_MAIN_CB.ActiveThreadCount
0x18001af22  test    al, 10h
0x18001af24  jz      short loc_18001AF2B
0x18001af26  and     eax, 1
0x18001af29  jmp     short loc_18001AF30
0x18001af2b  call    Feature_BugFix_BfeTvs__private_IsEnabledDeviceUsageNoInline
0x18001af30  test    eax, eax
0x18001af32  jnz     short loc_18001AF5F
0x18001af34  mov     esi, edi
0x18001af36  mov     r15d, r13d
0x18001af39  shl     rsi, 4
0x18001af3d  cmp     [rsi+rbx], r13d
0x18001af41  jbe     short loc_18001AF93
0x18001af43  mov     ecx, r15d
0x18001af46  shl     rcx, 6
0x18001af4a  add     rcx, [rsi+rbx+8]
0x18001af4f  call    FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0
0x18001af54  inc     r15d
0x18001af57  cmp     r15d, [rsi+rbx]
0x18001af5b  jb      short loc_18001AF43
0x18001af5d  jmp     short loc_18001AF93
0x18001af5f  test    rbx, rbx
0x18001af62  jz      short loc_18001AF93
0x18001af64  mov     esi, edi
0x18001af66  shl     rsi, 4
0x18001af6a  add     rsi, rbx
0x18001af6d  cmp     [rsi+8], r13
0x18001af71  jz      short loc_18001AF93
0x18001af73  mov     r15d, r13d
0x18001af76  cmp     [rsi], r13d
0x18001af79  jbe     short loc_18001AF93
0x18001af7b  mov     ecx, r15d
0x18001af7e  shl     rcx, 6
0x18001af82  add     rcx, [rsi+8]
0x18001af86  call    FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0
0x18001af8b  inc     r15d
0x18001af8e  cmp     r15d, [rsi]
0x18001af91  jb      short loc_18001AF7B
0x18001af93  mov     edx, edi
0x18001af95  shl     rdx, 4
0x18001af99  add     rdx, 8
0x18001af9d  add     rdx, rbx
0x18001afa0  call    WfpNamedPoolFree
0x18001afa5  inc     edi
0x18001afa7  cmp     edi, r14d
0x18001afaa  jb      loc_18001AF17
0x18001afb0  lea     rdx, [rsp+78h+var_48]
0x18001afb5  call    WfpNamedPoolFree
0x18001afba  test    rbp, rbp
0x18001afbd  jz      short loc_18001AFD8
0x18001afbf  lea     rdx, [rsp+78h+var_50]
0x18001afc4  call    WfpNamedPoolFree
0x18001afc9  lea     rdx, aFwppexpandcert_0; "FwppExpandCertAuthRootConfig0ArrayOutTo"...
0x18001afd0  mov     rcx, rbp
0x18001afd3  call    WfpReportError
0x18001afd8  mov     rbx, [rsp+78h+arg_8]
0x18001afe0  mov     rax, rbp
0x18001afe3  add     rsp, 40h
0x18001afe7  pop     r15
0x18001afe9  pop     r14
0x18001afeb  pop     r13
0x18001afed  pop     r12
0x18001afef  pop     rdi
0x18001aff0  pop     rsi
0x18001aff1  pop     rbp
  ... truncated ...
```
