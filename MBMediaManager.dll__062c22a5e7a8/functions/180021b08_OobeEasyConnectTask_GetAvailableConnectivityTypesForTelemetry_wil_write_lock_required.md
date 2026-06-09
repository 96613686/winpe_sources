# OobeEasyConnectTask::GetAvailableConnectivityTypesForTelemetry(wil::write_lock_required)

- ea: `0x180021b08`
- end: `0x180021cf5`
- name: `?GetAvailableConnectivityTypesForTelemetry@OobeEasyConnectTask@@AEAA?AW4AvailableConnectivity@@Uwrite_lock_required@wil@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800215a0`

## callees

- `0x180002150`
- `0x180021b08`
- `0x180036714`
- `0x180059010`

## string_xrefs

- `0x180021b62`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x180021b95`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x180021c02`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x180021c35`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x180021c68`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OobeEasyConnectTask::GetAvailableConnectivityTypesForTelemetry(__int64 a1)
{
  unsigned int v1; // esi
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, _QWORD, _QWORD *); // rbx
  int v4; // eax
  int v5; // eax
  unsigned int i; // r14d
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, int *); // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v13[2]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v14[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v16; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+68h] [rbp+10h]
  int v18; // [rsp+70h] [rbp+18h] BYREF
  int v19; // [rsp+78h] [rbp+20h] BYREF

  v14[0] = 0;
  v16 = 0;
  v1 = 0;
  v17 = 0;
  v2 = *(_QWORD *)(a1 + 136);
  v3 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v2 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v14);
  try
  {
    v4 = v3(v2, 0, v14);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x395,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
        (const char *)(unsigned int)v4,
        v13[0]);
    v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v14[0] + 56LL))(v14[0], &v16);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x396,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
        (const char *)(unsigned int)v5,
        v13[0]);
    for ( i = 0; i < v16; ++i )
    {
      *(_QWORD *)v13 = 0;
      v18 = 0;
      v19 = 0;
      v7 = v14[0];
      v8 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v14[0] + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v13);
      v9 = v8(v7, i, v13);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39E,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
          (const char *)(unsigned int)v9,
          v13[0]);
      v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v13 + 96LL))(*(_QWORD *)v13, &v18);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39F,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
          (const char *)(unsigned int)v10,
          v13[0]);
      v11 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v13 + 72LL))(*(_QWORD *)v13, &v19);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3A0,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
          (const char *)(unsigned int)v11,
          v13[0]);
      if ( v18 == 5 )
      {
        switch ( v19 )
        {
          case 1:
            v1 |= 2u;
            break;
          case 2:
            v1 |= 4u;
            break;
          case 3:
            v1 |= 1u;
            break;
          case 4:
            v1 |= 8u;
            break;
          case 5:
            v1 |= 0x10u;
            break;
          case 6:
            v1 |= 0x20u;
            break;
          default:
            v1 |= 0x40u;
            break;
        }
        v17 = v1;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v13);
    }
  }
  catch ( ... )
  {
    v1 = v17;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v14);
  return v1;
}

```

## disassembly

```asm
0x180021b08  mov     byte ptr [rsp+arg_8], dl
0x180021b0c  push    rbx
0x180021b0d  push    rsi
0x180021b0e  push    rdi
0x180021b0f  push    r14
0x180021b11  sub     rsp, 38h
0x180021b15  mov     [rsp+58h+var_30], 0
0x180021b1e  mov     [rsp+58h+arg_0], 0
0x180021b26  xor     esi, esi
0x180021b28  mov     [rsp+58h+arg_8], esi
0x180021b2c  mov     rdi, [rcx+88h]
0x180021b33  mov     rax, [rdi]
0x180021b36  mov     rbx, [rax+48h]
0x180021b3a  lea     rcx, [rsp+58h+var_30]
0x180021b3f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021b44  lea     r8, [rsp+58h+var_30]
0x180021b49  xor     edx, edx
0x180021b4b  mov     rcx, rdi
0x180021b4e  mov     rax, rbx
0x180021b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b56  mov     rcx, [rsp+58h]; this
0x180021b5b  test    eax, eax
0x180021b5d  jns     short loc_180021B73
0x180021b5f  mov     r9d, eax; char *
0x180021b62  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180021b69  mov     edx, 395h; void *
0x180021b6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021b73  mov     rcx, [rsp+58h+var_30]
0x180021b78  mov     rax, [rcx]
0x180021b7b  lea     rdx, [rsp+58h+arg_0]
0x180021b80  mov     rax, [rax+38h]
0x180021b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b89  mov     rcx, [rsp+58h]; this
0x180021b8e  test    eax, eax
0x180021b90  jns     short loc_180021BA6
0x180021b92  mov     r9d, eax; char *
0x180021b95  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180021b9c  mov     edx, 396h; void *
0x180021ba1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021ba6  xor     r14d, r14d
0x180021ba9  cmp     r14d, [rsp+58h+arg_0]
0x180021bae  jnb     loc_180021CD9
0x180021bb4  mov     qword ptr [rsp+58h+var_38], 0; int
0x180021bbd  mov     [rsp+58h+arg_10], 0
0x180021bc5  mov     [rsp+58h+arg_18], 0
0x180021bcd  mov     rdi, [rsp+58h+var_30]
0x180021bd2  mov     rax, [rdi]
0x180021bd5  mov     rbx, [rax+30h]
0x180021bd9  lea     rcx, [rsp+58h+var_38]
0x180021bde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021be3  lea     r8, [rsp+58h+var_38]
0x180021be8  mov     edx, r14d
0x180021beb  mov     rcx, rdi
0x180021bee  mov     rax, rbx
0x180021bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bf6  mov     rcx, [rsp+58h]; this
0x180021bfb  test    eax, eax
0x180021bfd  jns     short loc_180021C13
0x180021bff  mov     r9d, eax; char *
0x180021c02  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180021c09  mov     edx, 39Eh; void *
0x180021c0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021c13  mov     rcx, qword ptr [rsp+58h+var_38]
0x180021c18  mov     rax, [rcx]
0x180021c1b  lea     rdx, [rsp+58h+arg_10]
0x180021c20  mov     rax, [rax+60h]
0x180021c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c29  mov     rcx, [rsp+58h]; this
0x180021c2e  test    eax, eax
0x180021c30  jns     short loc_180021C46
0x180021c32  mov     r9d, eax; char *
0x180021c35  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180021c3c  mov     edx, 39Fh; void *
0x180021c41  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021c46  mov     rcx, qword ptr [rsp+58h+var_38]
0x180021c4b  mov     rax, [rcx]
0x180021c4e  lea     rdx, [rsp+58h+arg_18]
0x180021c53  mov     rax, [rax+48h]
0x180021c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c5c  mov     rcx, [rsp+58h]; this
0x180021c61  test    eax, eax
0x180021c63  jns     short loc_180021C79
0x180021c65  mov     r9d, eax; char *
0x180021c68  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180021c6f  mov     edx, 3A0h; void *
0x180021c74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021c79  cmp     [rsp+58h+arg_10], 5
0x180021c7e  jnz     short loc_180021CC7
0x180021c80  mov     ecx, [rsp+58h+arg_18]
0x180021c84  sub     ecx, 1
0x180021c87  jz      short loc_180021CC0
0x180021c89  sub     ecx, 1
0x180021c8c  jz      short loc_180021CBB
0x180021c8e  sub     ecx, 1
0x180021c91  jz      short loc_180021CB6
0x180021c93  sub     ecx, 1
0x180021c96  jz      short loc_180021CB1
0x180021c98  sub     ecx, 1
0x180021c9b  jz      short loc_180021CAC
0x180021c9d  cmp     ecx, 1
0x180021ca0  jz      short loc_180021CA7
0x180021ca2  or      esi, 40h
0x180021ca5  jmp     short loc_180021CC3
0x180021ca7  or      esi, 20h
0x180021caa  jmp     short loc_180021CC3
0x180021cac  or      esi, 10h
0x180021caf  jmp     short loc_180021CC3
0x180021cb1  or      esi, 8
0x180021cb4  jmp     short loc_180021CC3
0x180021cb6  or      esi, 1
0x180021cb9  jmp     short loc_180021CC3
0x180021cbb  or      esi, 4
0x180021cbe  jmp     short loc_180021CC3
0x180021cc0  or      esi, 2
0x180021cc3  mov     [rsp+58h+arg_8], esi
0x180021cc7  lea     rcx, [rsp+58h+var_38]
0x180021ccc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021cd1  inc     r14d
0x180021cd4  jmp     loc_180021BA9
0x180021cd9  jmp     short loc_180021CDF
0x180021cdb  mov     esi, [rsp+58h+arg_8]
0x180021cdf  lea     rcx, [rsp+58h+var_30]
0x180021ce4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021ce9  mov     eax, esi
0x180021ceb  add     rsp, 38h
0x180021cef  pop     r14
0x180021cf1  pop     rdi
0x180021cf2  pop     rsi
0x180021cf3  pop     rbx
0x180021cf4  retn
```
