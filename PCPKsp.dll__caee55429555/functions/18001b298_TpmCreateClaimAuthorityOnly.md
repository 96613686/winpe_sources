# TpmCreateClaimAuthorityOnly

- ea: `0x18001b298`
- end: `0x18001b498`
- name: `TpmCreateClaimAuthorityOnly`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180050bb0`

## callees

- `0x18000f240`
- `0x180015660`
- `0x1800157c0`
- `0x18001b298`
- `0x18001c308`
- `0x180029260`
- `0x1800764d0`
- `0x1800768a0`
- `0x180076998`
- `0x18007704c`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x18001b3b2`
- `tbs!Tbsi_GetDeviceInfo` at `0x18001b3b2`

## string_xrefs

- `0x18001b2d6`: `TpmCreateClaimAuthorityOnly`

## pseudocode

```c
__int64 __fastcall TpmCreateClaimAuthorityOnly(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, _DWORD *a5)
{
  int Property; // eax
  unsigned int v9; // edi
  size_t v10; // r14
  void *v11; // rax
  void *v12; // rbx
  int v13; // eax
  const struct std::nothrow_t *v14; // rdx
  unsigned int v15; // r15d
  size_t v16; // rcx
  _BYTE *v17; // rax
  int DeviceInfo; // [rsp+30h] [rbp-40h] BYREF
  unsigned int Size; // [rsp+34h] [rbp-3Ch] BYREF
  int *Size_4[3]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v22; // [rsp+50h] [rbp-20h] BYREF

  DeviceInfo = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)Size_4, L"TpmCreateClaimAuthorityOnly", &DeviceInfo);
  Size = 0;
  v22 = 0;
  if ( !a2 || a3 && !a4 || !a5 )
    goto LABEL_17;
  Property = ProviderGetProperty(a2, 0x50u, 0, 0, (int)&Size);
  DeviceInfo = SecurityStatusFromHResult(Property);
  v9 = DeviceInfo;
  if ( DeviceInfo < 0 )
    goto LABEL_15;
  v10 = Size;
  if ( !Size )
  {
LABEL_17:
    v9 = -2147024809;
    goto LABEL_18;
  }
  v11 = operator new[](Size, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
LABEL_18:
    DeviceInfo = v9;
    goto LABEL_15;
  }
  memset_0(v11, 0, v10);
  DeviceInfo = 0;
  v13 = ProviderGetProperty(a2, 0x50u, (__int64)v12, v10, (int)&Size);
  DeviceInfo = SecurityStatusFromHResult(v13);
  if ( DeviceInfo >= 0 )
  {
    DeviceInfo = Tbsi_GetDeviceInfo(16, &v22);
    if ( DeviceInfo >= 0 )
    {
      v15 = v10 + 28;
      *a5 = v10 + 28;
      if ( a3 )
      {
        if ( a4 >= v15 )
        {
          *(_DWORD *)(a3 + 8) = DWORD1(v22);
          *(_DWORD *)a3 = 1414742347;
          *(_DWORD *)(a3 + 4) = 1;
          *(_DWORD *)(a3 + 12) = 28;
          *(_DWORD *)(a3 + 16) = v10;
          *(_QWORD *)(a3 + 20) = 0;
          if ( memcpy_s((void *const)(a3 + 28), v10, v12, v10) || v15 != *a5 )
            DeviceInfo = -2147467259;
        }
        else
        {
          DeviceInfo = -2147024809;
        }
      }
    }
  }
  if ( (_DWORD)v10 )
  {
    v16 = v10;
    v17 = v12;
    do
    {
      *v17++ = 0;
      --v16;
    }
    while ( v16 );
  }
  operator delete(v12, v14);
  v9 = DeviceInfo;
LABEL_15:
  KspFunctionLogger::~KspFunctionLogger(Size_4);
  return v9;
}

```

## disassembly

```asm
0x18001b298  mov     [rsp-38h+arg_0], rbx
0x18001b29d  push    rbp
0x18001b29e  push    rsi
0x18001b29f  push    rdi
0x18001b2a0  push    r12
0x18001b2a2  push    r13
0x18001b2a4  push    r14
0x18001b2a6  push    r15
0x18001b2a8  mov     rbp, rsp
0x18001b2ab  sub     rsp, 70h
0x18001b2af  mov     rax, cs:__security_cookie
0x18001b2b6  xor     rax, rsp
0x18001b2b9  mov     [rbp+var_10], rax
0x18001b2bd  mov     r12, [rbp+arg_20]
0x18001b2c1  lea     rcx, [rbp+Size+4]; this
0x18001b2c5  mov     rsi, r8
0x18001b2c8  mov     [rbp+var_40], 0
0x18001b2cf  mov     r15, rdx
0x18001b2d2  lea     r8, [rbp+var_40]; int *
0x18001b2d6  lea     rdx, aTpmcreateclaim_0; "TpmCreateClaimAuthorityOnly"
0x18001b2dd  mov     r13d, r9d
0x18001b2e0  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18001b2e5  mov     dword ptr [rbp+Size], 0
0x18001b2ec  xorps   xmm0, xmm0
0x18001b2ef  movups  [rbp+var_20], xmm0
0x18001b2f3  test    r15, r15
0x18001b2f6  jz      loc_18001B42D
0x18001b2fc  test    rsi, rsi
0x18001b2ff  jnz     loc_18001B424
0x18001b305  test    r12, r12
0x18001b308  jz      loc_18001B42D
0x18001b30e  xor     r9d, r9d
0x18001b311  lea     rax, [rbp+Size]
0x18001b315  xor     r8d, r8d
0x18001b318  mov     [rsp+70h+var_50], rax
0x18001b31d  mov     rcx, r15
0x18001b320  lea     edx, [r9+50h]
0x18001b324  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x18001b329  mov     ecx, eax; int
0x18001b32b  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x18001b330  mov     [rbp+var_40], eax
0x18001b333  mov     edi, eax
0x18001b335  test    eax, eax
0x18001b337  js      loc_18001B3F4
0x18001b33d  mov     r14d, dword ptr [rbp+Size]
0x18001b341  test    r14d, r14d
0x18001b344  jz      loc_18001B42D
0x18001b34a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b351  mov     ecx, r14d; unsigned __int64
0x18001b354  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b359  mov     rbx, rax
0x18001b35c  test    rax, rax
0x18001b35f  jnz     short loc_18001B36B
0x18001b361  mov     edi, 8007000Eh
0x18001b366  jmp     loc_18001B432
0x18001b36b  mov     r8, r14; Size
0x18001b36e  xor     edx, edx; Val
0x18001b370  mov     rcx, rbx; void *
0x18001b373  call    memset_0
0x18001b378  lea     rax, [rbp+Size]
0x18001b37c  mov     [rbp+var_40], 0
0x18001b383  mov     r9d, r14d
0x18001b386  mov     [rsp+70h+var_50], rax
0x18001b38b  mov     r8, rbx
0x18001b38e  mov     edx, 50h ; 'P'
0x18001b393  mov     rcx, r15
0x18001b396  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x18001b39b  mov     ecx, eax; int
0x18001b39d  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x18001b3a2  mov     [rbp+var_40], eax
0x18001b3a5  test    eax, eax
0x18001b3a7  js      short loc_18001B3D2
0x18001b3a9  lea     rdx, [rbp+var_20]
0x18001b3ad  mov     ecx, 10h
0x18001b3b2  call    cs:__imp_Tbsi_GetDeviceInfo
0x18001b3b9  nop     dword ptr [rax+rax+00h]
0x18001b3be  mov     [rbp+var_40], eax
0x18001b3c1  test    eax, eax
0x18001b3c3  js      short loc_18001B3D2
0x18001b3c5  lea     r15d, [r14+1Ch]
0x18001b3c9  mov     [r12], r15d
0x18001b3cd  test    rsi, rsi
0x18001b3d0  jnz     short loc_18001B437
0x18001b3d2  test    r14d, r14d
0x18001b3d5  jz      short loc_18001B3E9
0x18001b3d7  mov     rcx, r14
0x18001b3da  mov     rax, rbx
0x18001b3dd  mov     byte ptr [rax], 0
0x18001b3e0  inc     rax
0x18001b3e3  sub     rcx, 1
0x18001b3e7  jnz     short loc_18001B3DD
0x18001b3e9  mov     rcx, rbx; void *
0x18001b3ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b3f1  mov     edi, [rbp+var_40]
0x18001b3f4  lea     rcx, [rbp+Size+4]; this
0x18001b3f8  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001b3fd  mov     eax, edi
0x18001b3ff  mov     rcx, [rbp+var_10]
0x18001b403  xor     rcx, rsp; StackCookie
0x18001b406  call    __security_check_cookie
0x18001b40b  mov     rbx, [rsp+70h+arg_0]
0x18001b413  add     rsp, 70h
0x18001b417  pop     r15
0x18001b419  pop     r14
0x18001b41b  pop     r13
0x18001b41d  pop     r12
0x18001b41f  pop     rdi
0x18001b420  pop     rsi
0x18001b421  pop     rbp
0x18001b422  retn
0x18001b424  test    r13d, r13d
0x18001b427  jnz     loc_18001B305
0x18001b42d  mov     edi, 80070057h
0x18001b432  mov     [rbp+var_40], edi
0x18001b435  jmp     short loc_18001B3F4
0x18001b437  cmp     r13d, r15d
0x18001b43a  jnb     short loc_18001B446
0x18001b43c  mov     edi, 80070057h
0x18001b441  mov     [rbp+var_40], edi
0x18001b444  jmp     short loc_18001B3D2
0x18001b446  mov     eax, dword ptr [rbp+var_20+4]
0x18001b449  lea     rcx, [rsi+1Ch]; Destination
0x18001b44d  mov     r9, r14; SourceSize
0x18001b450  mov     [rsi+8], eax
0x18001b453  mov     r8, rbx; Source
0x18001b456  mov     dword ptr [rsi], 5453414Bh
0x18001b45c  mov     rdx, r14; DestinationSize
0x18001b45f  mov     dword ptr [rsi+4], 1
0x18001b466  mov     dword ptr [rsi+0Ch], 1Ch
0x18001b46d  mov     [rsi+10h], r14d
0x18001b471  mov     qword ptr [rsi+14h], 0
0x18001b479  call    memcpy_s
0x18001b47e  test    eax, eax
0x18001b480  jnz     short loc_18001B48C
0x18001b482  cmp     r15d, [r12]
0x18001b486  jz      loc_18001B3D2
0x18001b48c  mov     [rbp+var_40], 80004005h
0x18001b493  jmp     loc_18001B3D2
```
