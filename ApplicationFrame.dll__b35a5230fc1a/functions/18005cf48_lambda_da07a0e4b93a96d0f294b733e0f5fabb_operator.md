# _lambda_da07a0e4b93a96d0f294b733e0f5fabb_::operator()

- ea: `0x18005cf48`
- end: `0x18005d030`
- name: `_lambda_da07a0e4b93a96d0f294b733e0f5fabb_::operator()`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e470`

## callees

- `0x180004c98`
- `0x180040270`
- `0x18005cacc`
- `0x18005cf48`
- `0x18005d1fc`
- `0x180072010`

## import_xrefs

- `TWINAPI!__imp_QueryWindowService` at `0x18005cf8a`
- `TWINAPI!__imp_QueryWindowService` at `0x18005cf8a`

## string_xrefs

- `0x18005cfe5`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_da07a0e4b93a96d0f294b733e0f5fabb_::operator()(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rax
  int v7; // [rsp+20h] [rbp-48h]
  _BYTE v8[40]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 *v10; // [rsp+70h] [rbp+8h] BYREF

  CRPCTimeout::CRPCTimeout((CRPCTimeout *)v8);
  v10 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v10);
  v2 = QueryWindowService(
         *(_QWORD *)(a1 + 8),
         &SID_InputPaneEventHandler,
         &GUID_87482e5d_0157_459a_bd7c_cb18085be80f,
         &v10);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = *v10;
    if ( *(_BYTE *)(a1 + 16) )
    {
      v7 = a1 + 72;
      v2 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v5 + 24))(v10, a1 + 24, a1 + 40, a1 + 56);
      v3 = v2;
      if ( v2 < 0 )
      {
        v4 = 99;
        goto LABEL_6;
      }
    }
    else
    {
      v2 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v5 + 32))(v10, *(unsigned int *)(a1 + 20));
      v3 = v2;
      if ( v2 < 0 )
      {
        v4 = 103;
        goto LABEL_6;
      }
    }
    v3 = 0;
    goto LABEL_10;
  }
  v4 = 95;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
    (const char *)(unsigned int)v2,
    v7);
LABEL_10:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v10);
  CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v8);
  return v3;
}

```

## disassembly

```asm
0x18005cf48  mov     [rsp+arg_8], rbx
0x18005cf4d  push    rdi
0x18005cf4e  sub     rsp, 60h
0x18005cf52  mov     rdi, rcx
0x18005cf55  lea     rcx, [rsp+68h+var_28]; this
0x18005cf5a  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18005cf5f  nop
0x18005cf60  mov     [rsp+68h+arg_0], 0
0x18005cf69  lea     rcx, [rsp+68h+arg_0]
0x18005cf6e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005cf73  lea     r9, [rsp+68h+arg_0]
0x18005cf78  lea     r8, _GUID_87482e5d_0157_459a_bd7c_cb18085be80f
0x18005cf7f  lea     rdx, SID_InputPaneEventHandler
0x18005cf86  mov     rcx, [rdi+8]
0x18005cf8a  call    cs:__imp_QueryWindowService
0x18005cf90  mov     ebx, eax
0x18005cf92  test    eax, eax
0x18005cf94  jns     short loc_18005CF9D
0x18005cf96  mov     edx, 5Fh ; '_'
0x18005cf9b  jmp     short loc_18005CFDD
0x18005cf9d  mov     rcx, [rsp+68h+arg_0]
0x18005cfa2  mov     rax, [rcx]
0x18005cfa5  cmp     byte ptr [rdi+10h], 0
0x18005cfa9  jz      short loc_18005CFF3
0x18005cfab  lea     r11, [rdi+48h]
0x18005cfaf  lea     r9, [rdi+38h]
0x18005cfb3  lea     r8, [rdi+28h]
0x18005cfb7  lea     rdx, [rdi+18h]
0x18005cfbb  mov     r10d, [rdi+14h]
0x18005cfbf  mov     [rsp+68h+var_40], r10d
0x18005cfc4  mov     qword ptr [rsp+68h+var_48], r11; int
0x18005cfc9  mov     rax, [rax+18h]
0x18005cfcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfd2  mov     ebx, eax
0x18005cfd4  test    eax, eax
0x18005cfd6  jns     short loc_18005D00C
0x18005cfd8  mov     edx, 63h ; 'c'; void *
0x18005cfdd  mov     rcx, [rsp+68h]; this
0x18005cfe2  mov     r9d, eax; char *
0x18005cfe5  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18005cfec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cff1  jmp     short loc_18005D00E
0x18005cff3  mov     edx, [rdi+14h]
0x18005cff6  mov     rax, [rax+20h]
0x18005cffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfff  mov     ebx, eax
0x18005d001  test    eax, eax
0x18005d003  jns     short loc_18005D00C
0x18005d005  mov     edx, 67h ; 'g'
0x18005d00a  jmp     short loc_18005CFDD
0x18005d00c  xor     ebx, ebx
0x18005d00e  lea     rcx, [rsp+68h+arg_0]
0x18005d013  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005d018  nop
0x18005d019  lea     rcx, [rsp+68h+var_28]; this
0x18005d01e  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18005d023  mov     eax, ebx
0x18005d025  mov     rbx, [rsp+68h+arg_8]
0x18005d02a  add     rsp, 60h
0x18005d02e  pop     rdi
0x18005d02f  retn
```
