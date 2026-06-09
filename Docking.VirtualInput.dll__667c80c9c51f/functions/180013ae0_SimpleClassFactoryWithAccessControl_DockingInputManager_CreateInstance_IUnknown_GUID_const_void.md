# SimpleClassFactoryWithAccessControl<DockingInputManager>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180013ae0`
- end: `0x180013bbe`
- name: `?CreateInstance@?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004ba0`
- `0x1800067a4`
- `0x180013a30`
- `0x180013ae0`
- `0x1800141d8`

## pseudocode

```c
__int64 __fastcall SimpleClassFactoryWithAccessControl<DockingInputManager>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int Instance; // eax
  int v6; // [rsp+20h] [rbp-18h]
  int v7; // [rsp+20h] [rbp-18h]
  unsigned int v8; // [rsp+24h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a4 = 0;
  if ( (int)SimpleClassFactoryWithAccessControl<DockingInputManager>::VerifyAccessForCaller() >= 0 )
  {
    Instance = Microsoft::WRL::SimpleClassFactory<DockingInputManager,0>::CreateInstance(a1, a2, a3, a4);
    v7 = wil::verify_BOOL<int>(Instance);
    if ( v7 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
        (const char *)(unsigned int)v7,
        v7);
      return v8;
    }
  }
  else
  {
    wil::verify_BOOL<int>(2147942405LL);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
      (const char *)0x80070005LL,
      v6);
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x180013ae0  mov     [rsp+arg_18], r9
0x180013ae5  mov     [rsp+arg_10], r8
0x180013aea  mov     [rsp+arg_8], rdx
0x180013aef  mov     [rsp+arg_0], rcx
0x180013af4  sub     rsp, 38h
0x180013af8  mov     rax, [rsp+38h+arg_18]
0x180013afd  mov     qword ptr [rax], 0
0x180013b04  mov     rcx, [rsp+38h+arg_0]
0x180013b09  call    ?VerifyAccessForCaller@?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@AEAAJXZ; SimpleClassFactoryWithAccessControl<DockingInputManager>::VerifyAccessForCaller(void)
0x180013b0e  test    eax, eax
0x180013b10  jge     short loc_180013B54
0x180013b12  mov     ecx, 80070005h
0x180013b17  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180013b1c  mov     [rsp+38h+var_14+4], eax
0x180013b20  xor     eax, eax
0x180013b22  cmp     eax, 1
0x180013b25  jz      short loc_180013B47
0x180013b27  mov     rax, [rsp+38h]
0x180013b2c  mov     r9d, 80070005h; char *
0x180013b32  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180013b39  mov     edx, 2Ch ; ','; void *
0x180013b3e  mov     rcx, rax; this
0x180013b41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b46  nop
0x180013b47  mov     eax, 80070005h
0x180013b4c  jmp     short loc_180013BB9
0x180013b4e  xor     eax, eax
0x180013b50  test    eax, eax
0x180013b52  jnz     short loc_180013B12
0x180013b54  mov     r9, [rsp+38h+arg_18]
0x180013b59  mov     r8, [rsp+38h+arg_10]
0x180013b5e  mov     rdx, [rsp+38h+arg_8]
0x180013b63  mov     rcx, [rsp+38h+arg_0]
0x180013b68  call    ?CreateInstance@?$SimpleClassFactory@VDockingInputManager@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::SimpleClassFactory<DockingInputManager,0>::CreateInstance(IUnknown *,_GUID const &,void * *)
0x180013b6d  mov     ecx, eax
0x180013b6f  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180013b74  mov     [rsp+38h+var_18], eax; int
0x180013b78  cmp     [rsp+38h+var_18], 0
0x180013b7d  jge     short loc_180013BB1
0x180013b7f  mov     eax, [rsp+38h+var_18]
0x180013b83  mov     [rsp+38h+var_14], eax
0x180013b87  mov     rax, [rsp+38h]
0x180013b8c  mov     r9d, [rsp+38h+var_14]; char *
0x180013b91  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180013b98  mov     edx, 2Fh ; '/'; void *
0x180013b9d  mov     rcx, rax; this
0x180013ba0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ba5  mov     eax, [rsp+38h+var_14]
0x180013ba9  jmp     short loc_180013BB9
0x180013bab  xor     eax, eax
0x180013bad  test    eax, eax
0x180013baf  jnz     short loc_180013B7F
0x180013bb1  xor     eax, eax
0x180013bb3  test    eax, eax
0x180013bb5  jnz     short loc_180013B54
0x180013bb7  xor     eax, eax
0x180013bb9  add     rsp, 38h
0x180013bbd  retn
```
