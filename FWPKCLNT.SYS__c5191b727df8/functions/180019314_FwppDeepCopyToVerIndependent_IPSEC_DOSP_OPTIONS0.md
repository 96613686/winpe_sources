# FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0

- ea: `0x180019314`
- end: `0x1800195ab`
- name: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180012d70`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x180013d04`
- `0x180019314`
- `0x18001a318`
- `0x180061f30`
- `0x180064264`
- `0x18006430c`

## string_xrefs

- `0x18001956e`: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_FLAGS`
- `0x180019586`: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_FLAGS`
- `0x180019545`: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0`
- `0x18001959d`: `FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v10; // rax

  if ( !a1 || !a2 )
  {
    v8 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0", -1071513572);
LABEL_29:
    v4 = v8;
    if ( !v8 )
      return v4;
    goto LABEL_30;
  }
  v4 = ((__int64 (*)(void))FwppDeepCopyToVerIndependent_UINT32)();
  if ( !v4 )
  {
    v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 4, a2 + 1);
    if ( !v4 )
    {
      v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 8, a2 + 2);
      if ( !v4 )
      {
        v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 12, a2 + 3);
        if ( !v4 )
        {
          v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 16, a2 + 4);
          if ( !v4 )
          {
            v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 20, a2 + 5);
            if ( !v4 )
            {
              v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 24, a2 + 6);
              if ( !v4 )
              {
                v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 28, a2 + 7);
                if ( !v4 )
                {
                  v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 32, a2 + 8);
                  if ( !v4 )
                  {
                    v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 36, a2 + 9);
                    if ( !v4 )
                    {
                      v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 40, a2 + 10);
                      if ( !v4 )
                      {
                        v4 = FwppDeepCopyToVerIndependent_UINT8(a1 + 44, a2 + 11);
                        if ( !v4 )
                        {
                          v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 48, a2 + 12);
                          if ( !v4 )
                          {
                            v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 52, a2 + 13);
                            if ( !v4 )
                            {
                              v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 56, a2 + 14);
                              if ( !v4 )
                              {
                                if ( a1 == -60 || (v5 = a2 + 15, a2 == (_DWORD *)-60LL) )
                                {
                                  v10 = WfpReportSysErrorAsNtStatus(
                                          (__int64)v5,
                                          (int)"FwppDeepCopyToVerIndependent_IPSEC_DOSP_FLAGS",
                                          -1071513572);
                                  v4 = v10;
                                  if ( v10 )
                                  {
                                    WfpReportError(v10, (int)"FwppDeepCopyToVerIndependent_IPSEC_DOSP_FLAGS");
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
                                  v4 = FwppArrayAllocAndDeepCopyToVerIndependent_UINT64(
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
                                  v4 = FwppArrayAllocAndDeepCopyToVerIndependent_UINT64(
                                         v7,
                                         *(unsigned int *)(a1 + 80),
                                         a2 + 22);
                                  if ( v4 )
                                    goto LABEL_30;
                                  a2[20] = *(_DWORD *)(a1 + 80);
                                }
                                v4 = FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK(a1 + 96, a2 + 24);
                                if ( !v4 )
                                {
                                  v8 = FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK(a1 + 113, (char *)a2 + 113);
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
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0");
  return v4;
}

```

## disassembly

```asm
0x180019314  mov     [rsp+arg_0], rbx
0x180019319  mov     [rsp+arg_8], rsi
0x18001931e  push    rdi
0x18001931f  sub     rsp, 20h
0x180019323  mov     rsi, rdx
0x180019326  mov     rdi, rcx
0x180019329  test    rcx, rcx
0x18001932c  jz      loc_180019597
0x180019332  test    rdx, rdx
0x180019335  jz      loc_180019597
0x18001933b  call    FwppDeepCopyToVerIndependent_UINT32
0x180019340  mov     rbx, rax
0x180019343  test    rax, rax
0x180019346  jnz     loc_180019538
0x18001934c  lea     rdx, [rsi+4]
0x180019350  lea     rcx, [rdi+4]
0x180019354  call    FwppDeepCopyToVerIndependent_UINT32
0x180019359  mov     rbx, rax
0x18001935c  test    rax, rax
0x18001935f  jnz     loc_180019538
0x180019365  lea     rdx, [rsi+8]
0x180019369  lea     rcx, [rdi+8]
0x18001936d  call    FwppDeepCopyToVerIndependent_UINT8
0x180019372  mov     rbx, rax
0x180019375  test    rax, rax
0x180019378  jnz     loc_180019538
0x18001937e  lea     rdx, [rsi+0Ch]
0x180019382  lea     rcx, [rdi+0Ch]
0x180019386  call    FwppDeepCopyToVerIndependent_UINT32
0x18001938b  mov     rbx, rax
0x18001938e  test    rax, rax
0x180019391  jnz     loc_180019538
0x180019397  lea     rdx, [rsi+10h]
0x18001939b  lea     rcx, [rdi+10h]
0x18001939f  call    FwppDeepCopyToVerIndependent_UINT32
0x1800193a4  mov     rbx, rax
0x1800193a7  test    rax, rax
0x1800193aa  jnz     loc_180019538
0x1800193b0  lea     rdx, [rsi+14h]
0x1800193b4  lea     rcx, [rdi+14h]
0x1800193b8  call    FwppDeepCopyToVerIndependent_UINT8
0x1800193bd  mov     rbx, rax
0x1800193c0  test    rax, rax
0x1800193c3  jnz     loc_180019538
0x1800193c9  lea     rdx, [rsi+18h]
0x1800193cd  lea     rcx, [rdi+18h]
0x1800193d1  call    FwppDeepCopyToVerIndependent_UINT32
0x1800193d6  mov     rbx, rax
0x1800193d9  test    rax, rax
0x1800193dc  jnz     loc_180019538
0x1800193e2  lea     rdx, [rsi+1Ch]
0x1800193e6  lea     rcx, [rdi+1Ch]
0x1800193ea  call    FwppDeepCopyToVerIndependent_UINT8
0x1800193ef  mov     rbx, rax
0x1800193f2  test    rax, rax
0x1800193f5  jnz     loc_180019538
0x1800193fb  lea     rdx, [rsi+20h]
0x1800193ff  lea     rcx, [rdi+20h]
0x180019403  call    FwppDeepCopyToVerIndependent_UINT32
0x180019408  mov     rbx, rax
0x18001940b  test    rax, rax
0x18001940e  jnz     loc_180019538
0x180019414  lea     rdx, [rsi+24h]
0x180019418  lea     rcx, [rdi+24h]
0x18001941c  call    FwppDeepCopyToVerIndependent_UINT8
0x180019421  mov     rbx, rax
0x180019424  test    rax, rax
0x180019427  jnz     loc_180019538
0x18001942d  lea     rdx, [rsi+28h]
0x180019431  lea     rcx, [rdi+28h]
0x180019435  call    FwppDeepCopyToVerIndependent_UINT32
0x18001943a  mov     rbx, rax
0x18001943d  test    rax, rax
0x180019440  jnz     loc_180019538
0x180019446  lea     rdx, [rsi+2Ch]
0x18001944a  lea     rcx, [rdi+2Ch]
0x18001944e  call    FwppDeepCopyToVerIndependent_UINT8
0x180019453  mov     rbx, rax
0x180019456  test    rax, rax
0x180019459  jnz     loc_180019538
0x18001945f  lea     rdx, [rsi+30h]
0x180019463  lea     rcx, [rdi+30h]
0x180019467  call    FwppDeepCopyToVerIndependent_UINT32
0x18001946c  mov     rbx, rax
0x18001946f  test    rax, rax
0x180019472  jnz     loc_180019538
0x180019478  lea     rdx, [rsi+34h]
0x18001947c  lea     rcx, [rdi+34h]
0x180019480  call    FwppDeepCopyToVerIndependent_UINT32
0x180019485  mov     rbx, rax
0x180019488  test    rax, rax
0x18001948b  jnz     loc_180019538
0x180019491  lea     rdx, [rsi+38h]
0x180019495  lea     rcx, [rdi+38h]
0x180019499  call    FwppDeepCopyToVerIndependent_UINT32
0x18001949e  mov     rbx, rax
0x1800194a1  test    rax, rax
0x1800194a4  jnz     loc_180019538
0x1800194aa  lea     rax, [rdi+3Ch]
0x1800194ae  test    rax, rax
0x1800194b1  jz      loc_180019568
0x1800194b7  lea     rcx, [rsi+3Ch]
0x1800194bb  test    rcx, rcx
0x1800194be  jz      loc_180019568
0x1800194c4  mov     eax, [rax]
0x1800194c6  mov     [rcx], eax
0x1800194c8  mov     rcx, [rdi+48h]
0x1800194cc  test    rcx, rcx
0x1800194cf  jz      short loc_1800194EB
0x1800194d1  mov     edx, [rdi+40h]
0x1800194d4  lea     r8, [rsi+48h]
0x1800194d8  call    FwppArrayAllocAndDeepCopyToVerIndependent_UINT64
0x1800194dd  mov     rbx, rax
0x1800194e0  test    rax, rax
0x1800194e3  jnz     short loc_180019538
0x1800194e5  mov     eax, [rdi+40h]
0x1800194e8  mov     [rsi+40h], eax
0x1800194eb  mov     rcx, [rdi+58h]
0x1800194ef  test    rcx, rcx
0x1800194f2  jz      short loc_18001950E
0x1800194f4  mov     edx, [rdi+50h]
0x1800194f7  lea     r8, [rsi+58h]
0x1800194fb  call    FwppArrayAllocAndDeepCopyToVerIndependent_UINT64
0x180019500  mov     rbx, rax
0x180019503  test    rax, rax
0x180019506  jnz     short loc_180019538
0x180019508  mov     eax, [rdi+50h]
0x18001950b  mov     [rsi+50h], eax
0x18001950e  lea     rdx, [rsi+60h]
0x180019512  lea     rcx, [rdi+60h]
0x180019516  call    FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK
0x18001951b  mov     rbx, rax
0x18001951e  test    rax, rax
0x180019521  jnz     short loc_180019538
0x180019523  lea     rdx, [rsi+71h]
0x180019527  lea     rcx, [rdi+71h]
0x18001952b  call    FwppDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK
0x180019530  mov     rbx, rax
0x180019533  test    rax, rax
0x180019536  jz      short loc_180019554
0x180019538  mov     rcx, rsi
0x18001953b  call    FwppDeepFreeContentsOnly_IPSEC_DOSP_OPTIONS0
0x180019540  test    rbx, rbx
0x180019543  jz      short loc_180019554
0x180019545  lea     rdx, aFwppdeepcopyto_3; "FwppDeepCopyToVerIndependent_IPSEC_DOSP"...
0x18001954c  mov     rcx, rbx
0x18001954f  call    WfpReportError
0x180019554  mov     rsi, [rsp+28h+arg_8]
0x180019559  mov     rax, rbx
0x18001955c  mov     rbx, [rsp+28h+arg_0]
0x180019561  add     rsp, 20h
0x180019565  pop     rdi
0x180019566  retn
0x180019568  mov     r8d, 0C022001Ch
0x18001956e  lea     rdx, aFwppdeepcopyto_21; "FwppDeepCopyToVerIndependent_IPSEC_DOSP"...
0x180019575  call    WfpReportSysErrorAsNtStatus
0x18001957a  mov     rbx, rax
0x18001957d  test    rax, rax
0x180019580  jz      loc_1800194C8
0x180019586  lea     rdx, aFwppdeepcopyto_21; "FwppDeepCopyToVerIndependent_IPSEC_DOSP"...
0x18001958d  mov     rcx, rax
0x180019590  call    WfpReportError
0x180019595  jmp     short loc_180019538
0x180019597  mov     r8d, 0C022001Ch
0x18001959d  lea     rdx, aFwppdeepcopyto_3; "FwppDeepCopyToVerIndependent_IPSEC_DOSP"...
0x1800195a4  call    WfpReportSysErrorAsNtStatus
0x1800195a9  jmp     short loc_180019530
```
