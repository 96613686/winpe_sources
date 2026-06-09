# WPDLibUpdateSecurityDescriptorList

- ea: `0x180014458`
- end: `0x1800147d8`
- name: `WPDLibUpdateSecurityDescriptorList`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180014458`
- `0x180015024`
- `0x1800154fc`
- `0x180015508`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001449e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800144ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014654`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800146a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800146fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014736`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001449e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800144ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014654`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800146a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800146fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014736`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014643`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800145fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014643`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147d1`

## pseudocode

```c
HLOCAL __fastcall WPDLibUpdateSecurityDescriptorList(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // r13
  _OWORD *v4; // rdi
  char *v5; // rsi
  _QWORD *v7; // rbx
  HLOCAL v8; // rax
  _QWORD *v9; // rcx
  _QWORD *i; // rbx
  __int64 v11; // rax
  unsigned int v12; // eax
  HLOCAL *v13; // r12
  HLOCAL *v14; // rbx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  HLOCAL v18; // rax
  int v19; // ecx
  int *v20; // r12
  _QWORD *j; // rax
  _QWORD *v23; // [rsp+50h] [rbp+8h]
  _QWORD *v25; // [rsp+68h] [rbp+20h]

  v23 = a1;
  v3 = (_QWORD *)*a1;
  v4 = 0;
  v5 = (char *)*a2;
  v7 = a2;
  if ( *a1 )
  {
    v9 = 0;
    v25 = 0;
    if ( v5 )
    {
      while ( 1 )
      {
        for ( i = v3; i; i = (_QWORD *)*i )
        {
          v11 = *(_QWORD *)((char *)i + 28) - *(_QWORD *)(v5 + 28);
          if ( !v11 )
            v11 = *(_QWORD *)((char *)i + 36) - *(_QWORD *)(v5 + 36);
          if ( !v11 )
          {
            v12 = *((_DWORD *)i + 6);
            if ( v12 )
            {
              if ( *((_DWORD *)v5 + 6) )
              {
                if ( *((_DWORD *)v5 + 6) == v12 )
                {
                  v13 = (HLOCAL *)(v5 + 16);
                  if ( !memcmp_0((const void *)i[2], *((const void **)v5 + 2), v12) )
                  {
                    *((_DWORD *)i + 12) = 0;
                    v14 = (HLOCAL *)v5;
                    v5 = *(char **)v5;
                    LocalFree(*v13);
                    LocalFree(v14[1]);
                    LocalFree(v14);
                    goto LABEL_49;
                  }
                }
              }
            }
            v15 = (void *)i[2];
            if ( v15 )
              LocalFree(v15);
            v16 = (void *)i[1];
            if ( v16 )
              LocalFree(v16);
            *((_DWORD *)i + 12) = 1;
            *((_DWORD *)i + 13) = *((_DWORD *)v5 + 13);
            i[2] = *((_QWORD *)v5 + 2);
            *((_DWORD *)i + 6) = *((_DWORD *)v5 + 6);
            i[1] = *((_QWORD *)v5 + 1);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl'::`2'::impl) )
              *((_DWORD *)i + 14) = *((_DWORD *)v5 + 14);
            v17 = v5;
            v5 = *(char **)v5;
            LocalFree(v17);
            if ( v4 || (v4 = LocalAlloc(0x40u, 0x38u)) != 0 )
            {
              *v4 = 0;
              v4[1] = 0;
              v4[2] = 0;
              *((_QWORD *)v4 + 6) = 0;
              if ( !i[1] && !i[2] )
                goto LABEL_38;
              v18 = LocalAlloc(0x40u, *((unsigned int *)i + 6));
              *((_QWORD *)v4 + 1) = v18;
              if ( v18 )
              {
                *((_DWORD *)v4 + 12) = 0;
                v4[1] = *(_OWORD *)((char *)i + 28);
                *((_DWORD *)v4 + 8) = *((_DWORD *)i + 11);
                v19 = *((_DWORD *)i + 12);
                goto LABEL_47;
              }
            }
            goto LABEL_49;
          }
        }
        v20 = (int *)(v5 + 48);
        i = v5;
        *((_DWORD *)v5 + 12) = 1;
        v5 = *(char **)v5;
        v25 = i;
        *i = v9;
        if ( v4 || (v4 = LocalAlloc(0x40u, 0x38u)) != 0 )
        {
          *v4 = 0;
          v4[1] = 0;
          v4[2] = 0;
          *((_QWORD *)v4 + 6) = 0;
          if ( i[1] || i[2] )
          {
            v18 = LocalAlloc(0x40u, *((unsigned int *)i + 6));
            *((_QWORD *)v4 + 1) = v18;
            if ( !v18 )
              goto LABEL_49;
            *((_DWORD *)v4 + 12) = 0;
            v4[1] = *(_OWORD *)((char *)i + 28);
            *((_DWORD *)v4 + 8) = *((_DWORD *)i + 11);
            v19 = *v20;
LABEL_47:
            *((_DWORD *)v4 + 9) = v19;
            *((_DWORD *)v4 + 10) = *((_DWORD *)i + 13);
            memcpy_0(v18, (const void *)i[2], *((unsigned int *)i + 6));
          }
          else
          {
LABEL_38:
            *((_DWORD *)v4 + 12) = 1;
            v4[1] = *(_OWORD *)((char *)i + 28);
          }
          *(_QWORD *)v4 = *a3;
          *a3 = v4;
          v4 = 0;
        }
LABEL_49:
        if ( !v5 )
          break;
        v9 = v25;
      }
      if ( v25 )
      {
        for ( j = v3; *j; j = (_QWORD *)*j )
          ;
        *j = v25;
      }
      v7 = a2;
    }
    *v23 = v3;
    goto LABEL_57;
  }
  if ( !v5 )
    goto LABEL_13;
  do
  {
    if ( v4 || (v4 = LocalAlloc(0x40u, 0x38u)) != 0 )
    {
      *v4 = 0;
      v4[1] = 0;
      v4[2] = 0;
      *((_QWORD *)v4 + 6) = 0;
      if ( *((_QWORD *)v5 + 1) || *((_QWORD *)v5 + 2) )
      {
        v8 = LocalAlloc(0x40u, *((unsigned int *)v5 + 6));
        *((_QWORD *)v4 + 1) = v8;
        if ( !v8 )
          goto LABEL_11;
        *((_DWORD *)v4 + 12) = 0;
        v4[1] = *(_OWORD *)(v5 + 28);
        *((_DWORD *)v4 + 8) = *((_DWORD *)v5 + 11);
        *((_DWORD *)v4 + 9) = *((_DWORD *)v5 + 12);
        *((_DWORD *)v4 + 10) = *((_DWORD *)v5 + 13);
        memcpy_0(v8, *((const void **)v5 + 2), *((unsigned int *)v5 + 6));
      }
      else
      {
        *((_DWORD *)v4 + 12) = 1;
        v4[1] = *(_OWORD *)(v5 + 28);
      }
      *(_QWORD *)v4 = *a3;
      *a3 = v4;
      v4 = 0;
    }
LABEL_11:
    v5 = *(char **)v5;
  }
  while ( v5 );
  a1 = v23;
LABEL_13:
  *a1 = *v7;
LABEL_57:
  *v7 = 0;
  return LocalFree(v4);
}

```

## disassembly

```asm
0x180014458  mov     [rsp+arg_10], rbx
0x18001445d  mov     [rsp+arg_8], rdx
0x180014462  mov     [rsp+arg_0], rcx
0x180014467  push    rsi
0x180014468  push    rdi
0x180014469  push    r12
0x18001446b  push    r13
0x18001446d  push    r14
0x18001446f  sub     rsp, 20h
0x180014473  mov     r13, [rcx]
0x180014476  xor     edi, edi
0x180014478  mov     rsi, [rdx]
0x18001447b  mov     r14, r8
0x18001447e  mov     rbx, rdx
0x180014481  test    r13, r13
0x180014484  jnz     loc_180014552
0x18001448a  test    rsi, rsi
0x18001448d  jz      loc_180014547
0x180014493  test    rdi, rdi
0x180014496  jnz     short loc_1800144B0
0x180014498  lea     edx, [rdi+38h]; uBytes
0x18001449b  lea     ecx, [rdi+40h]; uFlags
0x18001449e  call    cs:__imp_LocalAlloc
0x1800144a4  mov     rdi, rax
0x1800144a7  test    rax, rax
0x1800144aa  jz      loc_180014536
0x1800144b0  xorps   xmm0, xmm0
0x1800144b3  xor     eax, eax
0x1800144b5  movups  xmmword ptr [rdi], xmm0
0x1800144b8  movups  xmmword ptr [rdi+10h], xmm0
0x1800144bc  movups  xmmword ptr [rdi+20h], xmm0
0x1800144c0  mov     [rdi+30h], rax
0x1800144c4  cmp     [rsi+8], rax
0x1800144c8  jnz     short loc_1800144E2
0x1800144ca  cmp     [rsi+10h], rax
0x1800144ce  jnz     short loc_1800144E2
0x1800144d0  mov     dword ptr [rdi+30h], 1
0x1800144d7  movups  xmm0, xmmword ptr [rsi+1Ch]
0x1800144db  movdqu  xmmword ptr [rdi+10h], xmm0
0x1800144e0  jmp     short loc_18001452B
0x1800144e2  mov     edx, [rsi+18h]; uBytes
0x1800144e5  mov     ecx, 40h ; '@'; uFlags
0x1800144ea  call    cs:__imp_LocalAlloc
0x1800144f0  mov     [rdi+8], rax
0x1800144f4  test    rax, rax
0x1800144f7  jz      short loc_180014536
0x1800144f9  mov     dword ptr [rdi+30h], 0
0x180014500  movups  xmm0, xmmword ptr [rsi+1Ch]
0x180014504  movdqu  xmmword ptr [rdi+10h], xmm0
0x180014509  mov     ecx, [rsi+2Ch]
0x18001450c  mov     [rdi+20h], ecx
0x18001450f  mov     ecx, [rsi+30h]
0x180014512  mov     [rdi+24h], ecx
0x180014515  mov     ecx, [rsi+34h]
0x180014518  mov     [rdi+28h], ecx
0x18001451b  mov     rcx, rax; void *
0x18001451e  mov     r8d, [rsi+18h]; Size
0x180014522  mov     rdx, [rsi+10h]; Src
0x180014526  call    memcpy_0
0x18001452b  mov     rax, [r14]
0x18001452e  mov     [rdi], rax
0x180014531  mov     [r14], rdi
0x180014534  xor     edi, edi
0x180014536  mov     rsi, [rsi]
0x180014539  test    rsi, rsi
0x18001453c  jnz     loc_180014493
0x180014542  mov     rcx, [rsp+48h+arg_0]
0x180014547  mov     rax, [rbx]
0x18001454a  mov     [rcx], rax
0x18001454d  jmp     loc_1800147B6
0x180014552  xor     ecx, ecx
0x180014554  mov     [rsp+48h+arg_18], rcx
0x180014559  test    rsi, rsi
0x18001455c  jz      loc_1800147AE
0x180014562  jmp     short loc_180014569
0x180014564  mov     rcx, [rsp+48h+arg_18]
0x180014569  mov     rbx, r13
0x18001456c  test    rbx, rbx
0x18001456f  jz      loc_1800146D4
0x180014575  mov     rax, [rbx+1Ch]
0x180014579  sub     rax, [rsi+1Ch]
0x18001457d  jnz     short loc_180014587
0x18001457f  mov     rax, [rbx+24h]
0x180014583  sub     rax, [rsi+24h]
0x180014587  test    rax, rax
0x18001458a  jz      short loc_180014591
0x18001458c  mov     rbx, [rbx]
0x18001458f  jmp     short loc_18001456C
0x180014591  mov     eax, [rbx+18h]
0x180014594  test    eax, eax
0x180014596  jz      short loc_1800145E6
0x180014598  cmp     dword ptr [rsi+18h], 0
0x18001459c  jbe     short loc_1800145E6
0x18001459e  cmp     [rsi+18h], eax
0x1800145a1  jnz     short loc_1800145E6
0x1800145a3  mov     rcx, [rbx+10h]; Buf1
0x1800145a7  lea     r12, [rsi+10h]
0x1800145ab  mov     rdx, [r12]; Buf2
0x1800145af  mov     r8d, eax; Size
0x1800145b2  call    memcmp_0
0x1800145b7  test    eax, eax
0x1800145b9  jnz     short loc_1800145E6
0x1800145bb  mov     [rbx+30h], eax
0x1800145be  mov     rbx, rsi
0x1800145c1  mov     rcx, [r12]; hMem
0x1800145c5  mov     rsi, [rsi]
0x1800145c8  call    cs:__imp_LocalFree
0x1800145ce  mov     rcx, [rbx+8]; hMem
0x1800145d2  call    cs:__imp_LocalFree
0x1800145d8  mov     rcx, rbx; hMem
0x1800145db  call    cs:__imp_LocalFree
0x1800145e1  jmp     loc_180014783
0x1800145e6  mov     rcx, [rbx+10h]; hMem
0x1800145ea  test    rcx, rcx
0x1800145ed  jz      short loc_1800145F5
0x1800145ef  call    cs:__imp_LocalFree
0x1800145f5  mov     rcx, [rbx+8]; hMem
0x1800145f9  test    rcx, rcx
0x1800145fc  jz      short loc_180014604
0x1800145fe  call    cs:__imp_LocalFree
0x180014604  mov     dword ptr [rbx+30h], 1
0x18001460b  mov     eax, [rsi+34h]
0x18001460e  mov     [rbx+34h], eax
0x180014611  mov     rax, [rsi+10h]
0x180014615  mov     [rbx+10h], rax
0x180014619  mov     eax, [rsi+18h]
0x18001461c  mov     [rbx+18h], eax
0x18001461f  mov     rax, [rsi+8]
0x180014623  mov     [rbx+8], rax
0x180014627  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6> `wil::Feature<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetImpl(void)'::`2'::impl
0x18001462e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::__private_IsEnabled(void)
0x180014633  test    al, al
0x180014635  jz      short loc_18001463D
0x180014637  mov     eax, [rsi+38h]
0x18001463a  mov     [rbx+38h], eax
0x18001463d  mov     rcx, rsi; hMem
0x180014640  mov     rsi, [rsi]
0x180014643  call    cs:__imp_LocalFree
0x180014649  test    rdi, rdi
0x18001464c  jnz     short loc_180014666
0x18001464e  lea     edx, [rdi+38h]; uBytes
0x180014651  lea     ecx, [rdi+40h]; uFlags
0x180014654  call    cs:__imp_LocalAlloc
0x18001465a  mov     rdi, rax
0x18001465d  test    rax, rax
0x180014660  jz      loc_180014783
0x180014666  xorps   xmm0, xmm0
0x180014669  xor     eax, eax
0x18001466b  movups  xmmword ptr [rdi], xmm0
0x18001466e  movups  xmmword ptr [rdi+10h], xmm0
0x180014672  movups  xmmword ptr [rdi+20h], xmm0
0x180014676  mov     [rdi+30h], rax
0x18001467a  cmp     [rbx+8], rax
0x18001467e  jnz     short loc_18001469B
0x180014680  cmp     [rbx+10h], rax
0x180014684  jnz     short loc_18001469B
0x180014686  mov     dword ptr [rdi+30h], 1
0x18001468d  movups  xmm0, xmmword ptr [rbx+1Ch]
0x180014691  movdqu  xmmword ptr [rdi+10h], xmm0
0x180014696  jmp     loc_180014778
0x18001469b  mov     edx, [rbx+18h]; uBytes
0x18001469e  mov     ecx, 40h ; '@'; uFlags
0x1800146a3  call    cs:__imp_LocalAlloc
0x1800146a9  mov     [rdi+8], rax
0x1800146ad  test    rax, rax
0x1800146b0  jz      loc_180014783
0x1800146b6  mov     dword ptr [rdi+30h], 0
0x1800146bd  movups  xmm0, xmmword ptr [rbx+1Ch]
0x1800146c1  movdqu  xmmword ptr [rdi+10h], xmm0
0x1800146c6  mov     ecx, [rbx+2Ch]
0x1800146c9  mov     [rdi+20h], ecx
0x1800146cc  mov     ecx, [rbx+30h]
0x1800146cf  jmp     loc_18001475F
0x1800146d4  lea     r12, [rsi+30h]
0x1800146d8  mov     rbx, rsi
0x1800146db  mov     dword ptr [r12], 1
0x1800146e3  mov     rax, rsi
0x1800146e6  mov     rsi, [rsi]
0x1800146e9  mov     [rsp+48h+arg_18], rbx
0x1800146ee  mov     [rbx], rcx
0x1800146f1  test    rdi, rdi
0x1800146f4  jnz     short loc_18001470A
0x1800146f6  lea     edx, [rdi+38h]; uBytes
0x1800146f9  lea     ecx, [rdi+40h]; uFlags
0x1800146fc  call    cs:__imp_LocalAlloc
0x180014702  mov     rdi, rax
0x180014705  test    rax, rax
0x180014708  jz      short loc_180014783
0x18001470a  xorps   xmm0, xmm0
0x18001470d  xor     eax, eax
0x18001470f  movups  xmmword ptr [rdi], xmm0
0x180014712  movups  xmmword ptr [rdi+10h], xmm0
0x180014716  movups  xmmword ptr [rdi+20h], xmm0
0x18001471a  mov     [rdi+30h], rax
0x18001471e  cmp     [rbx+8], rax
0x180014722  jnz     short loc_18001472E
0x180014724  cmp     [rbx+10h], rax
0x180014728  jz      loc_180014686
0x18001472e  mov     edx, [rbx+18h]; uBytes
0x180014731  mov     ecx, 40h ; '@'; uFlags
0x180014736  call    cs:__imp_LocalAlloc
0x18001473c  mov     [rdi+8], rax
0x180014740  test    rax, rax
0x180014743  jz      short loc_180014783
0x180014745  mov     dword ptr [rdi+30h], 0
0x18001474c  movups  xmm0, xmmword ptr [rbx+1Ch]
0x180014750  movdqu  xmmword ptr [rdi+10h], xmm0
0x180014755  mov     ecx, [rbx+2Ch]
0x180014758  mov     [rdi+20h], ecx
0x18001475b  mov     ecx, [r12]
0x18001475f  mov     [rdi+24h], ecx
0x180014762  mov     ecx, [rbx+34h]
0x180014765  mov     [rdi+28h], ecx
0x180014768  mov     rcx, rax; void *
0x18001476b  mov     r8d, [rbx+18h]; Size
0x18001476f  mov     rdx, [rbx+10h]; Src
0x180014773  call    memcpy_0
0x180014778  mov     rax, [r14]
0x18001477b  mov     [rdi], rax
0x18001477e  mov     [r14], rdi
0x180014781  xor     edi, edi
0x180014783  test    rsi, rsi
0x180014786  jnz     loc_180014564
0x18001478c  mov     rdx, [rsp+48h+arg_18]
0x180014791  test    rdx, rdx
0x180014794  jz      short loc_1800147A9
0x180014796  mov     rax, r13
0x180014799  mov     rcx, [rax]
0x18001479c  test    rcx, rcx
0x18001479f  jz      short loc_1800147A6
0x1800147a1  mov     rax, rcx
0x1800147a4  jmp     short loc_180014799
0x1800147a6  mov     [rax], rdx
0x1800147a9  mov     rbx, [rsp+48h+arg_8]
0x1800147ae  mov     rax, [rsp+48h+arg_0]
0x1800147b3  mov     [rax], r13
0x1800147b6  mov     rcx, rdi
0x1800147b9  mov     qword ptr [rbx], 0
0x1800147c0  mov     rbx, [rsp+48h+arg_10]
0x1800147c5  add     rsp, 20h
0x1800147c9  pop     r14
0x1800147cb  pop     r13
0x1800147cd  pop     r12
0x1800147cf  pop     rdi
0x1800147d0  pop     rsi
0x1800147d1  jmp     cs:__imp_LocalFree
```
