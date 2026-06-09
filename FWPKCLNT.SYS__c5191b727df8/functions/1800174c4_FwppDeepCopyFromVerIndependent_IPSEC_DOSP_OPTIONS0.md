# FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0

- ea: `0x1800174c4`
- end: `0x18001775b`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180012618`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x180013808`
- `0x180016218`
- `0x1800174c4`
- `0x18001a318`
- `0x1800612c4`
- `0x18006136c`

## string_xrefs

- `0x18001771e`: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_FLAGS`
- `0x180017736`: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_FLAGS`
- `0x1800176f5`: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0`
- `0x18001774d`: `FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v10; // rax

  if ( !a1 || !a2 )
  {
    v8 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0", -1071513572);
LABEL_29:
    v4 = v8;
    if ( !v8 )
      return v4;
    goto LABEL_30;
  }
  v4 = ((__int64 (*)(void))FwppDeepCopyFromVerIndependent_UINT32)();
  if ( !v4 )
  {
    v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 4, a2 + 1);
    if ( !v4 )
    {
      v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 8, a2 + 2);
      if ( !v4 )
      {
        v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 12, a2 + 3);
        if ( !v4 )
        {
          v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 16, a2 + 4);
          if ( !v4 )
          {
            v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 20, a2 + 5);
            if ( !v4 )
            {
              v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 24, a2 + 6);
              if ( !v4 )
              {
                v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 28, a2 + 7);
                if ( !v4 )
                {
                  v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 32, a2 + 8);
                  if ( !v4 )
                  {
                    v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 36, a2 + 9);
                    if ( !v4 )
                    {
                      v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 40, a2 + 10);
                      if ( !v4 )
                      {
                        v4 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 44, a2 + 11);
                        if ( !v4 )
                        {
                          v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 48, a2 + 12);
                          if ( !v4 )
                          {
                            v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 52, a2 + 13);
                            if ( !v4 )
                            {
                              v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 56, a2 + 14);
                              if ( !v4 )
                              {
                                if ( a1 == -60 || (v5 = a2 + 15, a2 == (_DWORD *)-60LL) )
                                {
                                  v10 = WfpReportSysErrorAsNtStatus(
                                          (__int64)v5,
                                          (int)"FwppDeepCopyFromVerIndependent_IPSEC_DOSP_FLAGS",
                                          -1071513572);
                                  v4 = v10;
                                  if ( v10 )
                                  {
                                    WfpReportError(v10, (int)"FwppDeepCopyFromVerIndependent_IPSEC_DOSP_FLAGS");
                                    goto LABEL_30;
                                  }
                                }
                                else
                                {
                                  *v5 = *(_DWORD *)(a1 + 60);
                                }
                                v6 = *(_QWORD *)(a1 + 72);
                                if ( v6 )
                                {
                                  v4 = FwppArrayAllocAndDeepCopyFromVerIndependent_UINT64(
                                         v6,
                                         *(unsigned int *)(a1 + 64),
                                         a2 + 18);
                                  if ( v4 )
                                    goto LABEL_30;
                                  a2[16] = *(_DWORD *)(a1 + 64);
                                }
                                v7 = *(_QWORD *)(a1 + 88);
                                if ( v7 )
                                {
                                  v4 = FwppArrayAllocAndDeepCopyFromVerIndependent_UINT64(
                                         v7,
                                         *(unsigned int *)(a1 + 80),
                                         a2 + 22);
                                  if ( v4 )
                                    goto LABEL_30;
                                  a2[20] = *(_DWORD *)(a1 + 80);
                                }
                                v4 = FwppDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK(a1 + 96, a2 + 24);
                                if ( !v4 )
                                {
                                  v8 = FwppDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK(a1 + 113, (char *)a2 + 113);
                                  goto LABEL_29;
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
LABEL_30:
  FwppDeepFreeContentsOnly_IPSEC_DOSP_OPTIONS0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0");
  return v4;
}

```

## disassembly

```asm
0x1800174c4  mov     [rsp+arg_0], rbx
0x1800174c9  mov     [rsp+arg_8], rsi
0x1800174ce  push    rdi
0x1800174cf  sub     rsp, 20h
0x1800174d3  mov     rsi, rdx
0x1800174d6  mov     rdi, rcx
0x1800174d9  test    rcx, rcx
0x1800174dc  jz      loc_180017747
0x1800174e2  test    rdx, rdx
0x1800174e5  jz      loc_180017747
0x1800174eb  call    FwppDeepCopyFromVerIndependent_UINT32
0x1800174f0  mov     rbx, rax
0x1800174f3  test    rax, rax
0x1800174f6  jnz     loc_1800176E8
0x1800174fc  lea     rdx, [rsi+4]
0x180017500  lea     rcx, [rdi+4]
0x180017504  call    FwppDeepCopyFromVerIndependent_UINT32
0x180017509  mov     rbx, rax
0x18001750c  test    rax, rax
0x18001750f  jnz     loc_1800176E8
0x180017515  lea     rdx, [rsi+8]
0x180017519  lea     rcx, [rdi+8]
0x18001751d  call    FwppDeepCopyFromVerIndependent_UINT8
0x180017522  mov     rbx, rax
0x180017525  test    rax, rax
0x180017528  jnz     loc_1800176E8
0x18001752e  lea     rdx, [rsi+0Ch]
0x180017532  lea     rcx, [rdi+0Ch]
0x180017536  call    FwppDeepCopyFromVerIndependent_UINT32
0x18001753b  mov     rbx, rax
0x18001753e  test    rax, rax
0x180017541  jnz     loc_1800176E8
0x180017547  lea     rdx, [rsi+10h]
0x18001754b  lea     rcx, [rdi+10h]
0x18001754f  call    FwppDeepCopyFromVerIndependent_UINT32
0x180017554  mov     rbx, rax
0x180017557  test    rax, rax
0x18001755a  jnz     loc_1800176E8
0x180017560  lea     rdx, [rsi+14h]
0x180017564  lea     rcx, [rdi+14h]
0x180017568  call    FwppDeepCopyFromVerIndependent_UINT8
0x18001756d  mov     rbx, rax
0x180017570  test    rax, rax
0x180017573  jnz     loc_1800176E8
0x180017579  lea     rdx, [rsi+18h]
0x18001757d  lea     rcx, [rdi+18h]
0x180017581  call    FwppDeepCopyFromVerIndependent_UINT32
0x180017586  mov     rbx, rax
0x180017589  test    rax, rax
0x18001758c  jnz     loc_1800176E8
0x180017592  lea     rdx, [rsi+1Ch]
0x180017596  lea     rcx, [rdi+1Ch]
0x18001759a  call    FwppDeepCopyFromVerIndependent_UINT8
0x18001759f  mov     rbx, rax
0x1800175a2  test    rax, rax
0x1800175a5  jnz     loc_1800176E8
0x1800175ab  lea     rdx, [rsi+20h]
0x1800175af  lea     rcx, [rdi+20h]
0x1800175b3  call    FwppDeepCopyFromVerIndependent_UINT32
0x1800175b8  mov     rbx, rax
0x1800175bb  test    rax, rax
0x1800175be  jnz     loc_1800176E8
0x1800175c4  lea     rdx, [rsi+24h]
0x1800175c8  lea     rcx, [rdi+24h]
0x1800175cc  call    FwppDeepCopyFromVerIndependent_UINT8
0x1800175d1  mov     rbx, rax
0x1800175d4  test    rax, rax
0x1800175d7  jnz     loc_1800176E8
0x1800175dd  lea     rdx, [rsi+28h]
0x1800175e1  lea     rcx, [rdi+28h]
0x1800175e5  call    FwppDeepCopyFromVerIndependent_UINT32
0x1800175ea  mov     rbx, rax
0x1800175ed  test    rax, rax
0x1800175f0  jnz     loc_1800176E8
0x1800175f6  lea     rdx, [rsi+2Ch]
0x1800175fa  lea     rcx, [rdi+2Ch]
0x1800175fe  call    FwppDeepCopyFromVerIndependent_UINT8
0x180017603  mov     rbx, rax
0x180017606  test    rax, rax
0x180017609  jnz     loc_1800176E8
0x18001760f  lea     rdx, [rsi+30h]
0x180017613  lea     rcx, [rdi+30h]
0x180017617  call    FwppDeepCopyFromVerIndependent_UINT32
0x18001761c  mov     rbx, rax
0x18001761f  test    rax, rax
0x180017622  jnz     loc_1800176E8
0x180017628  lea     rdx, [rsi+34h]
0x18001762c  lea     rcx, [rdi+34h]
0x180017630  call    FwppDeepCopyFromVerIndependent_UINT32
0x180017635  mov     rbx, rax
0x180017638  test    rax, rax
0x18001763b  jnz     loc_1800176E8
0x180017641  lea     rdx, [rsi+38h]
0x180017645  lea     rcx, [rdi+38h]
0x180017649  call    FwppDeepCopyFromVerIndependent_UINT32
0x18001764e  mov     rbx, rax
0x180017651  test    rax, rax
0x180017654  jnz     loc_1800176E8
0x18001765a  lea     rax, [rdi+3Ch]
0x18001765e  test    rax, rax
0x180017661  jz      loc_180017718
0x180017667  lea     rcx, [rsi+3Ch]
0x18001766b  test    rcx, rcx
0x18001766e  jz      loc_180017718
0x180017674  mov     eax, [rax]
0x180017676  mov     [rcx], eax
0x180017678  mov     rcx, [rdi+48h]
0x18001767c  test    rcx, rcx
0x18001767f  jz      short loc_18001769B
0x180017681  mov     edx, [rdi+40h]
0x180017684  lea     r8, [rsi+48h]
0x180017688  call    FwppArrayAllocAndDeepCopyFromVerIndependent_UINT64
0x18001768d  mov     rbx, rax
0x180017690  test    rax, rax
0x180017693  jnz     short loc_1800176E8
0x180017695  mov     eax, [rdi+40h]
0x180017698  mov     [rsi+40h], eax
0x18001769b  mov     rcx, [rdi+58h]
0x18001769f  test    rcx, rcx
0x1800176a2  jz      short loc_1800176BE
0x1800176a4  mov     edx, [rdi+50h]
0x1800176a7  lea     r8, [rsi+58h]
0x1800176ab  call    FwppArrayAllocAndDeepCopyFromVerIndependent_UINT64
0x1800176b0  mov     rbx, rax
0x1800176b3  test    rax, rax
0x1800176b6  jnz     short loc_1800176E8
0x1800176b8  mov     eax, [rdi+50h]
0x1800176bb  mov     [rsi+50h], eax
0x1800176be  lea     rdx, [rsi+60h]
0x1800176c2  lea     rcx, [rdi+60h]
0x1800176c6  call    FwppDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK
0x1800176cb  mov     rbx, rax
0x1800176ce  test    rax, rax
0x1800176d1  jnz     short loc_1800176E8
0x1800176d3  lea     rdx, [rsi+71h]
0x1800176d7  lea     rcx, [rdi+71h]
0x1800176db  call    FwppDeepCopyFromVerIndependent_FWP_V6_ADDR_AND_MASK
0x1800176e0  mov     rbx, rax
0x1800176e3  test    rax, rax
0x1800176e6  jz      short loc_180017704
0x1800176e8  mov     rcx, rsi
0x1800176eb  call    FwppDeepFreeContentsOnly_IPSEC_DOSP_OPTIONS0
0x1800176f0  test    rbx, rbx
0x1800176f3  jz      short loc_180017704
0x1800176f5  lea     rdx, aFwppdeepcopyfr_75; "FwppDeepCopyFromVerIndependent_IPSEC_DO"...
0x1800176fc  mov     rcx, rbx
0x1800176ff  call    WfpReportError
0x180017704  mov     rsi, [rsp+28h+arg_8]
0x180017709  mov     rax, rbx
0x18001770c  mov     rbx, [rsp+28h+arg_0]
0x180017711  add     rsp, 20h
0x180017715  pop     rdi
0x180017716  retn
0x180017718  mov     r8d, 0C022001Ch
0x18001771e  lea     rdx, aFwppdeepcopyfr_100; "FwppDeepCopyFromVerIndependent_IPSEC_DO"...
0x180017725  call    WfpReportSysErrorAsNtStatus
0x18001772a  mov     rbx, rax
0x18001772d  test    rax, rax
0x180017730  jz      loc_180017678
0x180017736  lea     rdx, aFwppdeepcopyfr_100; "FwppDeepCopyFromVerIndependent_IPSEC_DO"...
0x18001773d  mov     rcx, rax
0x180017740  call    WfpReportError
0x180017745  jmp     short loc_1800176E8
0x180017747  mov     r8d, 0C022001Ch
0x18001774d  lea     rdx, aFwppdeepcopyfr_75; "FwppDeepCopyFromVerIndependent_IPSEC_DO"...
0x180017754  call    WfpReportSysErrorAsNtStatus
0x180017759  jmp     short loc_1800176E0
```
