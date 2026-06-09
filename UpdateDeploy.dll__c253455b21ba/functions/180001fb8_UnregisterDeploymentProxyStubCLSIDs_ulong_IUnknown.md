# UnregisterDeploymentProxyStubCLSIDs(ulong *,IUnknown * *)

- ea: `0x180001fb8`
- end: `0x180002094`
- name: `?UnregisterDeploymentProxyStubCLSIDs@@YAJPEAKPEAPEAUIUnknown@@@Z`
- size: `220`
- prototype: `int(unsigned int *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006be0`
- `0x180018400`

## callees

- `0x180001fb8`
- `0x180003180`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18000203e`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18000203e`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180002005`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180002005`

## string_xrefs

- `0x180001fda`: `C:\__w\1\s\src\Client\UpdateDeployment\Dll\ComReg.cpp`
- `0x180002016`: `C:\__w\1\s\src\Client\UpdateDeployment\Dll\ComReg.cpp`
- `0x18000204f`: `C:\__w\1\s\src\Client\UpdateDeployment\Dll\ComReg.cpp`

## pseudocode

```c
__int64 __fastcall UnregisterDeploymentProxyStubCLSIDs(unsigned int *a1, struct IUnknown **a2)
{
  __int64 v4; // rdx
  DWORD v6; // ecx
  HRESULT v7; // eax
  unsigned int v8; // esi
  HRESULT v9; // eax
  unsigned int v10; // edi
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v4 = 83;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Dll\\ComReg.cpp",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    v4 = 84;
    goto LABEL_3;
  }
  v6 = *a1;
  if ( v6 )
  {
    v7 = CoRevokeClassObject(v6);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Dll\\ComReg.cpp",
        (const char *)(unsigned int)v7,
        v11);
      return v8;
    }
    *a1 = 0;
  }
  if ( *a2 )
  {
    v9 = CoDisconnectObject(*a2, 0);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Dll\\ComReg.cpp",
        (const char *)(unsigned int)v9,
        v11);
      return v10;
    }
    if ( *a2 )
      ((void (__fastcall *)(_QWORD))(*a2)->lpVtbl->Release)(*a2);
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180001fb8  mov     [rsp+arg_0], rbx
0x180001fbd  mov     [rsp+arg_8], rsi
0x180001fc2  push    rdi; int
0x180001fc3  sub     rsp, 20h
0x180001fc7  mov     rbx, rdx
0x180001fca  mov     rdi, rcx
0x180001fcd  test    rcx, rcx
0x180001fd0  jnz     short loc_180001FF5
0x180001fd2  lea     edx, [rcx+53h]; void *
0x180001fd5  mov     rcx, [rsp+28h]; this
0x180001fda  lea     r8, aCW1SSrcClientU_9; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180001fe1  mov     ebx, 80004003h
0x180001fe6  mov     r9d, ebx; char *
0x180001fe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001fee  mov     eax, ebx
0x180001ff0  jmp     loc_180002084
0x180001ff5  test    rbx, rbx
0x180001ff8  jnz     short loc_180001FFF
0x180001ffa  lea     edx, [rbx+54h]
0x180001ffd  jmp     short loc_180001FD5
0x180001fff  mov     ecx, [rcx]; dwRegister
0x180002001  test    ecx, ecx
0x180002003  jz      short loc_180002034
0x180002005  call    cs:__imp_CoRevokeClassObject
0x18000200b  mov     esi, eax
0x18000200d  test    eax, eax
0x18000200f  jns     short loc_18000202E
0x180002011  mov     rcx, [rsp+28h]; this
0x180002016  lea     r8, aCW1SSrcClientU_9; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18000201d  mov     r9d, eax; char *
0x180002020  mov     edx, 59h ; 'Y'; void *
0x180002025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000202a  mov     eax, esi
0x18000202c  jmp     short loc_180002084
0x18000202e  mov     dword ptr [rdi], 0
0x180002034  mov     rcx, [rbx]; pUnk
0x180002037  test    rcx, rcx
0x18000203a  jz      short loc_180002082
0x18000203c  xor     edx, edx; dwReserved
0x18000203e  call    cs:__imp_CoDisconnectObject
0x180002044  mov     edi, eax
0x180002046  test    eax, eax
0x180002048  jns     short loc_180002067
0x18000204a  mov     rcx, [rsp+28h]; this
0x18000204f  lea     r8, aCW1SSrcClientU_9; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180002056  mov     r9d, eax; char *
0x180002059  mov     edx, 5Fh ; '_'; void *
0x18000205e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002063  mov     eax, edi
0x180002065  jmp     short loc_180002084
0x180002067  mov     rcx, [rbx]
0x18000206a  test    rcx, rcx
0x18000206d  jz      short loc_18000207B
0x18000206f  mov     rax, [rcx]
0x180002072  mov     rax, [rax+10h]
0x180002076  call    _guard_dispatch_icall
0x18000207b  mov     qword ptr [rbx], 0
0x180002082  xor     eax, eax
0x180002084  mov     rbx, [rsp+28h+arg_0]
0x180002089  mov     rsi, [rsp+28h+arg_8]
0x18000208e  add     rsp, 20h
0x180002092  pop     rdi
0x180002093  retn
```
