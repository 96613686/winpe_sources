# mkl_serv_get_version

- ea: `0x180053fa0`
- end: `0x180054070`
- name: `mkl_serv_get_version`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bb30`

## callees

- `0x180053fa0`
- `0x1800779d0`
- `0x1800b31b0`

## string_xrefs

- `0x18005404b`: `Intel(R) Streaming SIMD Extensions 2 (Intel(R) SSE2) enabled processors`
- `0x180054042`: `Intel(R) Supplemental Streaming SIMD Extensions 3 (Intel(R) SSSE3) enabled processors`
- `0x180054039`: `Intel(R) Streaming SIMD Extensions 4.2 (Intel(R) SSE4.2) enabled processors`
- `0x180054030`: `Intel(R) Advanced Vector Extensions (Intel(R) AVX) enabled processors`
- `0x180054027`: `Intel(R) Advanced Vector Extensions 2 (Intel(R) AVX2) enabled processors`
- `0x180054015`: `Intel(R) Advanced Vector Extensions 512 (Intel(R) AVX-512) enabled processors`
- `0x18005401e`: `Intel(R) Advanced Vector Extensions 512 (Intel(R) AVX-512) for Intel(R) Many Integrated Core Architecture (Intel(R) MIC Architecture) enabled processors`

## pseudocode

```c
void __fastcall mkl_serv_get_version(__int64 a1)
{
  const char *v2; // rax

  if ( a1 )
  {
    *(_DWORD *)a1 = 2017;
    *(_DWORD *)(a1 + 4) = 0;
    *(_DWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = "Product";
    *(_QWORD *)(a1 + 24) = "20160801";
    *(_QWORD *)(a1 + 40) = "Intel(R) 64 architecture";
    if ( (unsigned int)mkl_serv_intel_cpu() )
    {
      switch ( (unsigned int)mkl_serv_cpu_detect() )
      {
        case 0u:
          v2 = "Intel(R) Streaming SIMD Extensions 2 (Intel(R) SSE2) enabled processors";
          break;
        case 2u:
          v2 = "Intel(R) Supplemental Streaming SIMD Extensions 3 (Intel(R) SSSE3) enabled processors";
          break;
        case 3u:
          v2 = "Intel(R) Streaming SIMD Extensions 4.2 (Intel(R) SSE4.2) enabled processors";
          break;
        case 4u:
          v2 = "Intel(R) Advanced Vector Extensions (Intel(R) AVX) enabled processors";
          break;
        case 5u:
          v2 = "Intel(R) Advanced Vector Extensions 2 (Intel(R) AVX2) enabled processors";
          break;
        case 6u:
          v2 = "Intel(R) Advanced Vector Extensions 512 (Intel(R) AVX-512) for Intel(R) Many Integrated Core Architecture"
               " (Intel(R) MIC Architecture) enabled processors";
          break;
        case 7u:
          v2 = "Intel(R) Advanced Vector Extensions 512 (Intel(R) AVX-512) enabled processors";
          break;
        default:
          goto LABEL_11;
      }
    }
    else
    {
LABEL_11:
      v2 = "Intel(R) Architecture processors";
    }
    *(_QWORD *)(a1 + 32) = v2;
  }
}

```

## disassembly

```asm
0x180053fa0  push    r14
0x180053fa2  sub     rsp, 20h
0x180053fa6  mov     r14, rcx
0x180053fa9  test    r14, r14
0x180053fac  jnz     short loc_180053FB5
0x180053fae  add     rsp, 20h
0x180053fb2  pop     r14
0x180053fb4  retn
0x180053fb5  xor     eax, eax
0x180053fb7  lea     rdx, aProduct+10h; "Product"
0x180053fbe  lea     rcx, a20160801; "20160801"
0x180053fc5  lea     r8, aIntelR64Archit; "Intel(R) 64 architecture"
0x180053fcc  mov     dword ptr [r14], 7E1h
0x180053fd3  mov     [r14+4], eax
0x180053fd7  mov     [r14+8], eax
0x180053fdb  mov     [r14+10h], rdx
0x180053fdf  mov     [r14+18h], rcx
0x180053fe3  mov     [r14+28h], r8
0x180053fe7  call    mkl_serv_intel_cpu
0x180053fec  test    eax, eax
0x180053fee  jz      short def_180054013; jumptable 0000000180054013 default case, case 1
0x180053ff0  call    mkl_serv_cpu_detect
0x180053ff5  cmp     eax, 7; switch 8 cases
0x180053ff8  ja      short def_180054013; jumptable 0000000180054013 default case, case 1
0x180053ffa  mov     edx, eax
0x180053ffc  lea     rcx, cs:180000000h
0x180054003  movzx   eax, ds:(jpt_180054013 - 180000000h)[rcx+rdx]
0x18005400b  lea     rax, (loc_180054015 - 180000000h)[rcx+rax]; jumptable 0000000180054013 case 7
0x180054013  jmp     rax; switch jump
0x180054015  lea     rax, aIntelRAdvanced_1; jumptable 0000000180054013 case 7
0x18005401c  jmp     short loc_18005405B
0x18005401e  lea     rax, aIntelRAdvanced_0; jumptable 0000000180054013 case 6
0x180054025  jmp     short loc_18005405B
0x180054027  lea     rax, aIntelRAdvanced; jumptable 0000000180054013 case 5
0x18005402e  jmp     short loc_18005405B
0x180054030  lea     rax, aIntelRAdvanced_2; jumptable 0000000180054013 case 4
0x180054037  jmp     short loc_18005405B
0x180054039  lea     rax, aIntelRStreamin_0; jumptable 0000000180054013 case 3
0x180054040  jmp     short loc_18005405B
0x180054042  lea     rax, aIntelRSuppleme; jumptable 0000000180054013 case 2
0x180054049  jmp     short loc_18005405B
0x18005404b  lea     rax, aIntelRStreamin; jumptable 0000000180054013 case 0
0x180054052  jmp     short loc_18005405B
0x180054054  lea     rax, aIntelRArchitec; jumptable 0000000180054013 default case, case 1
0x18005405b  mov     [r14+20h], rax
0x18005405f  add     rsp, 20h
0x180054063  pop     r14
0x180054065  retn
```
