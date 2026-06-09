# CTitleBarPersistence::SetColor(PERSISTED_COLOR,ulong *)

- ea: `0x180014910`
- end: `0x180014b37`
- name: `?SetColor@CTitleBarPersistence@@UEAAJW4PERSISTED_COLOR@@PEAK@Z`
- size: `551`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003e30`
- `0x1800145b0`
- `0x180014910`
- `0x180040270`
- `0x180046b0c`
- `0x180061834`
- `0x18006187c`
- `0x180072010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180014a06`
- `SHCORE!SHTaskPoolQueueTask` at `0x180014ae3`
- `SHCORE!SHTaskPoolQueueTask` at `0x180014a06`
- `SHCORE!SHTaskPoolQueueTask` at `0x180014ae3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTitleBarPersistence::SetColor(_DWORD *a1, int a2, int *a3)
{
  __int64 v5; // rsi
  unsigned int v6; // r14d
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // r14
  unsigned int v13; // r15d
  _QWORD *v14; // rax
  _QWORD *v15; // rsi
  int v16; // [rsp+20h] [rbp-58h]
  _DWORD *v17; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v18[8]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v20; // [rsp+88h] [rbp+10h] BYREF
  int v21; // [rsp+98h] [rbp+20h] BYREF

  v20 = a2;
  if ( (unsigned __int64)a2 >= 0xC )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
      (const char *)0x80070057LL,
      v16);
    return 2147942487LL;
  }
  else
  {
    v17 = a1;
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 8LL))(a1);
    if ( a3 )
    {
      v21 = *a3;
      v5 = lambda_ba247e7265b9f0a64e1c9c3167d645f1_::_lambda_ba247e7265b9f0a64e1c9c3167d645f1_(
             (unsigned int)v18,
             (unsigned int)&v17,
             (_DWORD)a1,
             (unsigned int)&v21,
             (__int64)&v20);
      v6 = a1[12];
      v7 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
      v8 = v7;
      if ( v7 )
      {
        Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v7);
        v9 = *(_QWORD *)v5;
        v8[2] = *(_QWORD *)v5;
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        v8[3] = *(_QWORD *)(v5 + 8);
        *((_DWORD *)v8 + 8) = *(_DWORD *)(v5 + 16);
        *((_DWORD *)v8 + 9) = *(_DWORD *)(v5 + 20);
        *v8 = &off_1800731A0;
      }
      else
      {
        v8 = 0;
      }
      SHTaskPoolQueueTask(3, 2, v6, 0);
      if ( v8 )
        (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
    }
    else
    {
      v12 = lambda_745ecb8cb459e98119c2927706dead90_::_lambda_745ecb8cb459e98119c2927706dead90_(v18, &v17, a1, &v20);
      v13 = a1[12];
      v14 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
      v15 = v14;
      if ( v14 )
      {
        Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v14);
        v15[2] = *(_QWORD *)v12;
        Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(v15 + 2);
        v15[3] = *(_QWORD *)(v12 + 8);
        *((_DWORD *)v15 + 8) = *(_DWORD *)(v12 + 16);
        *v15 = &off_1800731F0;
      }
      else
      {
        v15 = 0;
      }
      SHTaskPoolQueueTask(3, 2, v13, 0);
      if ( v15 )
        (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    }
    v10 = v18[0];
    if ( v18[0] )
    {
      v18[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 16LL))(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x180014910  mov     [rsp+arg_0], rbx
0x180014915  mov     [rsp+arg_8], edx
0x180014919  push    rbp
0x18001491a  push    rsi
0x18001491b  push    rdi
0x18001491c  push    r14
0x18001491e  push    r15
0x180014920  sub     rsp, 50h
0x180014924  mov     rdi, r8
0x180014927  mov     rbx, rcx
0x18001492a  movsxd  rax, edx
0x18001492d  cmp     rax, 0Ch
0x180014931  jnb     loc_180014B11
0x180014937  mov     [rsp+78h+var_48], rcx
0x18001493c  test    rcx, rcx
0x18001493f  jz      short loc_18001494E
0x180014941  mov     rax, [rcx]
0x180014944  mov     rax, [rax+8]
0x180014948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001494d  nop
0x18001494e  mov     r8, rbx
0x180014951  lea     rdx, [rsp+78h+var_48]
0x180014956  lea     rcx, [rsp+78h+var_40]
0x18001495b  test    rdi, rdi
0x18001495e  jz      loc_180014A69
0x180014964  mov     eax, [rdi]
0x180014966  mov     [rsp+78h+arg_18], eax
0x18001496d  lea     rax, [rsp+78h+arg_8]
0x180014975  mov     [rsp+78h+var_58], rax
0x18001497a  lea     r9, [rsp+78h+arg_18]
0x180014982  call    _lambda_ba247e7265b9f0a64e1c9c3167d645f1____lambda_ba247e7265b9f0a64e1c9c3167d645f1_
0x180014987  mov     rsi, rax
0x18001498a  mov     r14d, [rbx+30h]
0x18001498e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014995  mov     ecx, 28h ; '('; unsigned __int64
0x18001499a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001499f  mov     rdi, rax
0x1800149a2  xor     ebp, ebp
0x1800149a4  test    rax, rax
0x1800149a7  jz      loc_180014B04
0x1800149ad  mov     rcx, rax
0x1800149b0  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x1800149b5  mov     rcx, [rsi]
0x1800149b8  mov     [rdi+10h], rcx
0x1800149bc  test    rcx, rcx
0x1800149bf  jz      short loc_1800149CE
0x1800149c1  mov     rax, [rcx]
0x1800149c4  mov     rax, [rax+8]
0x1800149c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149cd  nop
0x1800149ce  mov     rax, [rsi+8]
0x1800149d2  mov     [rdi+18h], rax
0x1800149d6  mov     eax, [rsi+10h]
0x1800149d9  mov     [rdi+20h], eax
0x1800149dc  mov     eax, [rsi+14h]
0x1800149df  mov     [rdi+24h], eax
0x1800149e2  lea     rax, off_1800731A0
0x1800149e9  mov     [rdi], rax
0x1800149ec  mov     [rsp+78h+var_50], rbp
0x1800149f1  mov     [rsp+78h+var_58], rdi
0x1800149f6  xor     r9d, r9d
0x1800149f9  mov     r8d, r14d
0x1800149fc  mov     edx, 2
0x180014a01  mov     ecx, 3
0x180014a06  call    cs:__imp_SHTaskPoolQueueTask
0x180014a0c  nop
0x180014a0d  test    rdi, rdi
0x180014a10  jz      short loc_180014A22
0x180014a12  mov     rax, [rdi]
0x180014a15  mov     rcx, rdi
0x180014a18  mov     rax, [rax+10h]
0x180014a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a21  nop
0x180014a22  mov     rcx, [rsp+78h+var_40]
0x180014a27  test    rcx, rcx
0x180014a2a  jz      short loc_180014A3E
0x180014a2c  mov     [rsp+78h+var_40], rbp
0x180014a31  mov     rax, [rcx]
0x180014a34  mov     rax, [rax+10h]
0x180014a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a3d  nop
0x180014a3e  test    rbx, rbx
0x180014a41  jz      short loc_180014A53
0x180014a43  mov     rax, [rbx]
0x180014a46  mov     rcx, rbx
0x180014a49  mov     rax, [rax+10h]
0x180014a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a52  nop
0x180014a53  xor     eax, eax
0x180014a55  mov     rbx, [rsp+78h+arg_0]
0x180014a5d  add     rsp, 50h
0x180014a61  pop     r15
0x180014a63  pop     r14
0x180014a65  pop     rdi
0x180014a66  pop     rsi
0x180014a67  pop     rbp
0x180014a68  retn
0x180014a69  lea     r9, [rsp+78h+arg_8]
0x180014a71  call    _lambda_745ecb8cb459e98119c2927706dead90____lambda_745ecb8cb459e98119c2927706dead90_
0x180014a76  mov     r14, rax
0x180014a79  mov     r15d, [rbx+30h]
0x180014a7d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014a84  mov     ecx, 28h ; '('; unsigned __int64
0x180014a89  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014a8e  mov     rsi, rax
0x180014a91  xor     ebp, ebp
0x180014a93  test    rax, rax
0x180014a96  jz      short loc_180014B0C
0x180014a98  mov     rcx, rax
0x180014a9b  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180014aa0  mov     rax, [r14]
0x180014aa3  mov     [rsi+10h], rax
0x180014aa7  lea     rcx, [rsi+10h]
0x180014aab  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x180014ab0  mov     rax, [r14+8]
0x180014ab4  mov     [rsi+18h], rax
0x180014ab8  mov     eax, [r14+10h]
0x180014abc  mov     [rsi+20h], eax
0x180014abf  lea     rax, off_1800731F0
0x180014ac6  mov     [rsi], rax
0x180014ac9  mov     [rsp+78h+var_50], rbp
0x180014ace  mov     [rsp+78h+var_58], rsi
0x180014ad3  xor     r9d, r9d
0x180014ad6  mov     r8d, r15d
0x180014ad9  mov     edx, 2
0x180014ade  mov     ecx, 3
0x180014ae3  call    cs:__imp_SHTaskPoolQueueTask
0x180014ae9  nop
0x180014aea  test    rsi, rsi
0x180014aed  jz      short loc_180014AFF
0x180014aef  mov     rax, [rsi]
0x180014af2  mov     rcx, rsi
0x180014af5  mov     rax, [rax+10h]
0x180014af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014afe  nop
0x180014aff  jmp     loc_180014A22
0x180014b04  mov     rdi, rbp
0x180014b07  jmp     loc_1800149EC
0x180014b0c  mov     rsi, rbp
0x180014b0f  jmp     short loc_180014AC9
0x180014b11  mov     rcx, [rsp+78h]; this
0x180014b16  mov     r9d, 80070057h; char *
0x180014b1c  lea     r8, aPcshellShellAp; "pcshell\\shell\\applicationframe\\frame"...
0x180014b23  mov     edx, 92h; void *
0x180014b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b2d  mov     eax, 80070057h
0x180014b32  jmp     loc_180014A55
```
