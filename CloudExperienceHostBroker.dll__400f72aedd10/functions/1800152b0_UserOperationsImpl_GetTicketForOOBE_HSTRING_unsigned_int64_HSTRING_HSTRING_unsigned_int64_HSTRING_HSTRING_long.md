# UserOperationsImpl::GetTicketForOOBE(HSTRING__ *,unsigned __int64,HSTRING__ *,HSTRING__ *,unsigned __int64,HSTRING__ *,HSTRING__ *,long *,long *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,__int64 *,__int64 *,long *,long *,long *,long *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800152b0`
- end: `0x18001549a`
- name: `?GetTicketForOOBE@UserOperationsImpl@@UEAAJPEAUHSTRING__@@_K00100PEAJ2PEAPEAU2@33PEA_J4222233@Z`
- size: `490`
- prototype: `__int64 __fastcall(UserOperationsImpl *__hidden this, HSTRING, unsigned __int64, HSTRING, HSTRING, unsigned __int64, HSTRING, HSTRING, int *, int *, HSTRING *, HSTRING *, HSTRING *, __int64 *, __int64 *, int *, int *, int *, int *, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x1800152b0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800152fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800152fc`

## string_xrefs

- `0x18001530f`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180015464`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserOperationsImpl::GetTicketForOOBE(
        UserOperationsImpl *this,
        HSTRING a2,
        __int64 a3,
        HSTRING a4,
        HSTRING a5)
{
  HRESULT Instance; // eax
  unsigned int v9; // ebx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  int ppv; // [rsp+20h] [rbp-A1h]
  __int64 v16; // [rsp+B0h] [rbp-11h] BYREF
  LPVOID v17[7]; // [rsp+B8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+37h]

  v17[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  Instance = CoCreateInstance(
               &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
               0,
               1u,
               &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
               v17);
  v9 = Instance;
  if ( Instance >= 0 )
  {
    v16 = 0;
    v10 = v17[0];
    v11 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v17[0] + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v12 = v11(v10, &GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2, &GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f, &v16);
    v9 = v12;
    if ( v12 >= 0 )
    {
      ppv = (int)a5;
      v12 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, HSTRING))(*(_QWORD *)v16 + 64LL))(v16, a2, a3, a4);
      v9 = v12;
      if ( v12 >= 0 )
      {
LABEL_8:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
        goto LABEL_9;
      }
      v13 = 359;
    }
    else
    {
      v13 = 337;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14E,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  return v9;
}

```

## disassembly

```asm
0x1800152b0  push    rbp
0x1800152b2  push    rbx
0x1800152b3  push    rsi
0x1800152b4  push    rdi
0x1800152b5  push    r14
0x1800152b7  push    r15
0x1800152b9  lea     rbp, [rsp-7]
0x1800152be  sub     rsp, 0C8h
0x1800152c5  mov     rsi, r9
0x1800152c8  mov     r14, r8
0x1800152cb  mov     r15, rdx
0x1800152ce  mov     [rbp+2Fh+var_38], 0
0x1800152d6  lea     rcx, [rbp+2Fh+var_38]
0x1800152da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800152df  lea     rax, [rbp+2Fh+var_38]
0x1800152e3  mov     [rsp+0F0h+ppv], rax; int
0x1800152e8  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x1800152ef  xor     edx, edx; pUnkOuter
0x1800152f1  lea     r8d, [rdx+1]; dwClsContext
0x1800152f5  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x1800152fc  call    cs:__imp_CoCreateInstance
0x180015302  mov     ebx, eax
0x180015304  test    eax, eax
0x180015306  jns     short loc_180015325
0x180015308  mov     rcx, [rbp+37h]; this
0x18001530c  mov     r9d, eax; char *
0x18001530f  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180015316  mov     edx, 14Eh; void *
0x18001531b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015320  jmp     loc_18001547F
0x180015325  mov     [rbp+2Fh+var_40], 0
0x18001532d  mov     rdi, [rbp+2Fh+var_38]
0x180015331  mov     rax, [rdi]
0x180015334  mov     rbx, [rax+20h]
0x180015338  lea     rcx, [rbp+2Fh+var_40]
0x18001533c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015341  lea     r9, [rbp+2Fh+var_40]
0x180015345  lea     r8, _GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f
0x18001534c  lea     rdx, _GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2
0x180015353  mov     rcx, rdi
0x180015356  mov     rax, rbx
0x180015359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001535e  mov     ebx, eax
0x180015360  test    eax, eax
0x180015362  jns     short loc_18001536E
0x180015364  mov     edx, 151h
0x180015369  jmp     loc_180015461
0x18001536e  mov     rcx, [rbp+2Fh+var_40]
0x180015372  mov     rax, [rcx]
0x180015375  mov     r10, [rax+40h]
0x180015379  mov     rax, [rbp+2Fh+arg_A0]
0x180015380  mov     [rsp+0F0h+var_50], rax
0x180015388  mov     rax, [rbp+2Fh+arg_98]
0x18001538f  mov     [rsp+0F0h+var_58], rax
0x180015397  mov     rax, [rbp+2Fh+arg_90]
0x18001539e  mov     [rsp+0F0h+var_60], rax
0x1800153a6  mov     rax, [rbp+2Fh+arg_88]
0x1800153ad  mov     [rsp+0F0h+var_68], rax
0x1800153b5  mov     rax, [rbp+2Fh+arg_80]
0x1800153bc  mov     [rsp+0F0h+var_70], rax
0x1800153c4  mov     rax, [rbp+2Fh+arg_78]
0x1800153cb  mov     [rsp+0F0h+var_78], rax
0x1800153d0  mov     rax, [rbp+2Fh+arg_70]
0x1800153d7  mov     [rsp+0F0h+var_80], rax
0x1800153dc  mov     rax, [rbp+2Fh+arg_68]
0x1800153e3  mov     [rsp+0F0h+var_88], rax
0x1800153e8  mov     rax, [rbp+2Fh+arg_60]
0x1800153ef  mov     [rsp+0F0h+var_90], rax
0x1800153f4  mov     rax, [rbp+2Fh+arg_58]
0x1800153fb  mov     [rsp+0F0h+var_98], rax
0x180015400  mov     rax, [rbp+2Fh+arg_50]
0x180015407  mov     [rsp+0F0h+var_A0], rax
0x18001540c  mov     rax, [rbp+2Fh+arg_48]
0x180015413  mov     [rsp+0F0h+var_A8], rax
0x180015418  mov     rdx, [rbp+2Fh+arg_40]
0x18001541c  mov     [rsp+0F0h+var_B0], rdx
0x180015421  mov     rdx, [rbp+2Fh+arg_38]
0x180015425  mov     [rsp+0F0h+var_B8], rdx
0x18001542a  mov     rdx, [rbp+2Fh+arg_30]
0x18001542e  mov     [rsp+0F0h+var_C0], rdx
0x180015433  mov     rdx, [rbp+2Fh+arg_28]
0x180015437  mov     [rsp+0F0h+var_C8], rdx
0x18001543c  mov     rdx, [rbp+2Fh+arg_20]
0x180015440  mov     [rsp+0F0h+ppv], rdx; int
0x180015445  mov     r9, rsi
0x180015448  mov     r8, r14
0x18001544b  mov     rdx, r15
0x18001544e  mov     rax, r10
0x180015451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015456  mov     ebx, eax
0x180015458  test    eax, eax
0x18001545a  jns     short loc_180015475
0x18001545c  mov     edx, 167h; void *
0x180015461  mov     r9d, eax; char *
0x180015464  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x18001546b  mov     rcx, [rbp+37h]; this
0x18001546f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015474  nop
0x180015475  lea     rcx, [rbp+2Fh+var_40]
0x180015479  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001547e  nop
0x18001547f  lea     rcx, [rbp+2Fh+var_38]
0x180015483  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015488  mov     eax, ebx
0x18001548a  add     rsp, 0C8h
0x180015491  pop     r15
0x180015493  pop     r14
0x180015495  pop     rdi
0x180015496  pop     rsi
0x180015497  pop     rbx
0x180015498  pop     rbp
0x180015499  retn
```
