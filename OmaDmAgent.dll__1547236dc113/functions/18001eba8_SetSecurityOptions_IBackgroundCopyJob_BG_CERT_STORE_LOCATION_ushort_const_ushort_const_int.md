# SetSecurityOptions(IBackgroundCopyJob *,BG_CERT_STORE_LOCATION,ushort const *,ushort const *,int)

- ea: `0x18001eba8`
- end: `0x18001ecf9`
- name: `?SetSecurityOptions@@YAJPEAUIBackgroundCopyJob@@W4BG_CERT_STORE_LOCATION@@PEBG2H@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, enum BG_CERT_STORE_LOCATION, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b05c`

## callees

- `0x180009284`
- `0x1800092bc`
- `0x18000a0d4`
- `0x18001afb4`
- `0x18001eba8`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetSecurityOptions(
        struct IBackgroundCopyJob *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  int v8; // ebx
  unsigned int v9; // edx
  __int64 v11; // [rsp+38h] [rbp-20h] BYREF
  void *v12[2]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v13; // [rsp+A0h] [rbp+48h] BYREF

  v11 = 0;
  *(_OWORD *)v12 = 0;
  if ( a3 && a4 )
  {
    v8 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_f1bd1079_9f01_4bdc_8036_f09b70095066,
           &v11);
    if ( v8 >= 0 )
    {
      v13 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 80LL))(v11, &v13);
      if ( v8 >= 0 )
      {
        v9 = a5 == 1 ? v13 | 1 : v13 & 0xFFFFFFFE;
        v13 = v9;
        v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 72LL))(v11);
        if ( v8 >= 0 )
        {
          v8 = HexStringToBinary(a4, 0, v12);
          if ( v8 >= 0 )
          {
            v12[1] = SafeHeapAlloc(LODWORD(v12[0]));
            if ( v12[1] )
            {
              v8 = HexStringToBinary(a4, v12[1], v12);
              if ( v8 >= 0 )
              {
                v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 40LL))(v11);
                if ( v8 >= 0 )
                  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, void *))(*(_QWORD *)v11 + 24LL))(
                         v11,
                         a2,
                         a3,
                         v12[1]);
              }
            }
            else
            {
              v8 = -2147024882;
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
  SafeHeapFree(v12[1]);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001eba8  push    rbp
0x18001ebaa  push    rbx
0x18001ebab  push    rsi
0x18001ebac  push    rdi
0x18001ebad  push    r14
0x18001ebaf  push    r15
0x18001ebb1  mov     rbp, rsp
0x18001ebb4  sub     rsp, 58h
0x18001ebb8  mov     rdi, r9
0x18001ebbb  mov     rsi, r8
0x18001ebbe  mov     r14d, edx
0x18001ebc1  mov     [rbp+var_20], 0
0x18001ebc9  lea     r15, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001ebd0  mov     [rbp+var_28], r15
0x18001ebd4  xorps   xmm0, xmm0
0x18001ebd7  movups  xmmword ptr [rbp+var_18], xmm0
0x18001ebdb  test    r8, r8
0x18001ebde  jnz     short loc_18001EBEA
0x18001ebe0  mov     ebx, 80070057h
0x18001ebe5  jmp     loc_18001ECD2
0x18001ebea  test    rdi, rdi
0x18001ebed  jz      short loc_18001EBE0
0x18001ebef  mov     rax, [rcx]
0x18001ebf2  lea     r8, [rbp+var_20]
0x18001ebf6  lea     rdx, _GUID_f1bd1079_9f01_4bdc_8036_f09b70095066
0x18001ebfd  mov     rax, [rax]
0x18001ec00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec05  mov     ebx, eax
0x18001ec07  test    eax, eax
0x18001ec09  js      loc_18001ECD2
0x18001ec0f  mov     [rbp+arg_10], 0
0x18001ec16  mov     rcx, [rbp+var_20]
0x18001ec1a  mov     rax, [rcx]
0x18001ec1d  lea     rdx, [rbp+arg_10]
0x18001ec21  mov     rax, [rax+50h]
0x18001ec25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec2a  mov     ebx, eax
0x18001ec2c  test    eax, eax
0x18001ec2e  js      loc_18001ECD2
0x18001ec34  mov     edx, [rbp+arg_10]
0x18001ec37  cmp     [rbp+arg_20], 1
0x18001ec3b  jnz     short loc_18001EC42
0x18001ec3d  or      edx, 1
0x18001ec40  jmp     short loc_18001EC45
0x18001ec42  and     edx, 0FFFFFFFEh
0x18001ec45  mov     [rbp+arg_10], edx
0x18001ec48  mov     rcx, [rbp+var_20]
0x18001ec4c  mov     rax, [rcx]
0x18001ec4f  mov     rax, [rax+48h]
0x18001ec53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec58  mov     ebx, eax
0x18001ec5a  test    eax, eax
0x18001ec5c  js      short loc_18001ECD2
0x18001ec5e  lea     r8, [rbp+var_18]
0x18001ec62  xor     edx, edx
0x18001ec64  mov     rcx, rdi
0x18001ec67  call    HexStringToBinary
0x18001ec6c  mov     ebx, eax
0x18001ec6e  test    eax, eax
0x18001ec70  js      short loc_18001ECD2
0x18001ec72  mov     ecx, dword ptr [rbp+var_18]; unsigned __int64
0x18001ec75  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18001ec7a  mov     [rbp+var_18+8], rax
0x18001ec7e  test    rax, rax
0x18001ec81  jnz     short loc_18001EC8A
0x18001ec83  mov     ebx, 8007000Eh
0x18001ec88  jmp     short loc_18001ECD2
0x18001ec8a  lea     r8, [rbp+var_18]
0x18001ec8e  mov     rdx, [rbp+var_18+8]
0x18001ec92  mov     rcx, rdi
0x18001ec95  call    HexStringToBinary
0x18001ec9a  mov     ebx, eax
0x18001ec9c  test    eax, eax
0x18001ec9e  js      short loc_18001ECD2
0x18001eca0  mov     rcx, [rbp+var_20]
0x18001eca4  mov     rax, [rcx]
0x18001eca7  mov     rax, [rax+28h]
0x18001ecab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecb0  mov     ebx, eax
0x18001ecb2  test    eax, eax
0x18001ecb4  js      short loc_18001ECD2
0x18001ecb6  mov     rcx, [rbp+var_20]
0x18001ecba  mov     rax, [rcx]
0x18001ecbd  mov     r9, [rbp+var_18+8]
0x18001ecc1  mov     r8, rsi
0x18001ecc4  mov     edx, r14d
0x18001ecc7  mov     rax, [rax+18h]
0x18001eccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecd0  mov     ebx, eax
0x18001ecd2  mov     rcx, [rbp+var_18+8]; void *
0x18001ecd6  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18001ecdb  nop
0x18001ecdc  mov     [rbp+var_28], r15
0x18001ece0  lea     rcx, [rbp+var_20]
0x18001ece4  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001ece9  mov     eax, ebx
0x18001eceb  add     rsp, 58h
0x18001ecef  pop     r15
0x18001ecf1  pop     r14
0x18001ecf3  pop     rdi
0x18001ecf4  pop     rsi
0x18001ecf5  pop     rbx
0x18001ecf6  pop     rbp
0x18001ecf7  retn
```
