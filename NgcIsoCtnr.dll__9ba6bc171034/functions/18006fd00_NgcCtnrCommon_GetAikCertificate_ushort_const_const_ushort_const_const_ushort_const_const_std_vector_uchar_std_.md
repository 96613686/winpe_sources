# NgcCtnrCommon::GetAikCertificate(ushort const * const,ushort const * const,ushort const * const,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x18006fd00`
- end: `0x18006fe31`
- name: `?GetAikCertificate@NgcCtnrCommon@@YAJQEBG00PEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023590`

## callees

- `0x180007670`
- `0x18000d62c`
- `0x180017264`
- `0x180017f94`
- `0x18006fd00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fdcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fe12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fdcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fe12`
- `cryptngc!NgcGetKeyAttestationForContainerService` at `0x18006fd83`
- `cryptngc!NgcGetKeyAttestationForContainerService` at `0x18006fd83`

## string_xrefs

- `0x18006fd9c`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcCtnrCommon::GetAikCertificate(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int KeyAttestationForContainerService; // ebx
  __int64 v6; // rdx
  HLOCAL v7; // rcx
  HLOCAL v9; // rcx
  HLOCAL *p_hMem; // [rsp+40h] [rbp-9h] BYREF
  int v11[2]; // [rsp+48h] [rbp-1h] BYREF
  char v12; // [rsp+50h] [rbp+7h]
  unsigned int v13; // [rsp+58h] [rbp+Fh]
  _QWORD v14[3]; // [rsp+60h] [rbp+17h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+2Fh] BYREF
  int v16; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v14[0] = a2;
  v14[1] = a3;
  v14[2] = 0;
  hMem = 0;
  v13 = 0;
  v16 = 0;
  p_hMem = &hMem;
  *(_QWORD *)v11 = 0;
  v12 = 1;
  KeyAttestationForContainerService = NgcGetKeyAttestationForContainerService(v14, a1, 0, 0);
  wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( KeyAttestationForContainerService >= 0 )
  {
    std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(a4, hMem, v13);
    v9 = hMem;
    hMem = 0;
    if ( v9 )
      LocalFree(v9);
    return 0;
  }
  else
  {
    if ( v16 == 4 )
    {
      KeyAttestationForContainerService = -2142371836;
      v6 = 166;
    }
    else if ( v16 == 5 )
    {
      KeyAttestationForContainerService = -2142371835;
      v6 = 170;
    }
    else
    {
      v6 = 172;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
      (const char *)(unsigned int)KeyAttestationForContainerService,
      (int)v11);
    v7 = hMem;
    hMem = 0;
    if ( v7 )
      LocalFree(v7);
    return (unsigned int)KeyAttestationForContainerService;
  }
}

```

## disassembly

```asm
0x18006fd00  push    rbp
0x18006fd02  push    rbx
0x18006fd03  push    rdi
0x18006fd04  lea     rbp, [rsp-47h]
0x18006fd09  sub     rsp, 90h
0x18006fd10  mov     rax, cs:__security_cookie
0x18006fd17  xor     rax, rsp
0x18006fd1a  mov     [rbp+57h+var_18], rax
0x18006fd1e  mov     rdi, r9
0x18006fd21  mov     [rbp+57h+var_40], rdx
0x18006fd25  mov     [rbp+57h+var_38], r8
0x18006fd29  mov     [rbp+57h+var_30], 0
0x18006fd31  mov     [rbp+57h+hMem], 0
0x18006fd39  mov     [rbp+57h+var_48], 0
0x18006fd40  mov     [rbp+57h+var_20], 0
0x18006fd47  lea     rax, [rbp+57h+hMem]
0x18006fd4b  mov     [rbp+57h+var_60], rax
0x18006fd4f  mov     qword ptr [rbp+57h+var_58], 0
0x18006fd57  mov     [rbp+57h+var_50], 1
0x18006fd5b  lea     rax, [rbp+57h+var_20]
0x18006fd5f  mov     [rsp+0A0h+var_70], rax
0x18006fd64  lea     rax, [rbp+57h+var_48]
0x18006fd68  mov     [rsp+0A0h+var_78], rax
0x18006fd6d  lea     rax, [rbp+57h+var_58]
0x18006fd71  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x18006fd76  xor     r9d, r9d
0x18006fd79  xor     r8d, r8d
0x18006fd7c  mov     rdx, rcx
0x18006fd7f  lea     rcx, [rbp+57h+var_40]
0x18006fd83  call    cs:__imp_NgcGetKeyAttestationForContainerService
0x18006fd89  mov     ebx, eax
0x18006fd8b  lea     rcx, [rbp+57h+var_60]
0x18006fd8f  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18006fd94  test    ebx, ebx
0x18006fd96  jns     short loc_18006FDF0
0x18006fd98  mov     rcx, [rbp+5Fh]; this
0x18006fd9c  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18006fda3  cmp     [rbp+57h+var_20], 4
0x18006fda7  jnz     short loc_18006FDD7
0x18006fda9  mov     ebx, 804E0004h
0x18006fdae  mov     edx, 0A6h; void *
0x18006fdb3  mov     r9d, ebx; char *
0x18006fdb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fdbb  nop
0x18006fdbc  mov     rcx, [rbp+57h+hMem]; hMem
0x18006fdc0  mov     [rbp+57h+hMem], 0
0x18006fdc8  test    rcx, rcx
0x18006fdcb  jz      short loc_18006FDD3
0x18006fdcd  call    cs:__imp_LocalFree
0x18006fdd3  mov     eax, ebx
0x18006fdd5  jmp     short loc_18006FE1A
0x18006fdd7  cmp     [rbp+57h+var_20], 5
0x18006fddb  jnz     short loc_18006FDE9
0x18006fddd  mov     ebx, 804E0005h
0x18006fde2  mov     edx, 0AAh
0x18006fde7  jmp     short loc_18006FDB3
0x18006fde9  mov     edx, 0ACh
0x18006fdee  jmp     short loc_18006FDB3
0x18006fdf0  mov     rdx, [rbp+57h+hMem]
0x18006fdf4  mov     r8d, [rbp+57h+var_48]
0x18006fdf8  mov     rcx, rdi
0x18006fdfb  call    ??$_Assign_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x18006fe00  nop
0x18006fe01  mov     rcx, [rbp+57h+hMem]; hMem
0x18006fe05  mov     [rbp+57h+hMem], 0
0x18006fe0d  test    rcx, rcx
0x18006fe10  jz      short loc_18006FE18
0x18006fe12  call    cs:__imp_LocalFree
0x18006fe18  xor     eax, eax
0x18006fe1a  mov     rcx, [rbp+57h+var_18]
0x18006fe1e  xor     rcx, rsp; StackCookie
0x18006fe21  call    __security_check_cookie
0x18006fe26  add     rsp, 90h
0x18006fe2d  pop     rdi
0x18006fe2e  pop     rbx
0x18006fe2f  pop     rbp
0x18006fe30  retn
```
