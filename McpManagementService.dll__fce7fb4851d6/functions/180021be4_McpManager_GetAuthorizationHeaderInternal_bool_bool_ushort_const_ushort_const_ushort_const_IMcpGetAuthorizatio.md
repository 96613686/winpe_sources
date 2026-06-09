# McpManager::GetAuthorizationHeaderInternal(bool,bool,ushort const *,ushort const *,ushort const *,IMcpGetAuthorizationHeaderOperation * *)

- ea: `0x180021be4`
- end: `0x180021cc4`
- name: `?GetAuthorizationHeaderInternal@McpManager@@AEAAJ_N0PEBG11PEAPEAUIMcpGetAuthorizationHeaderOperation@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(McpManager *this, char, char, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IMcpGetAuthorizationHeaderOperation **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180021ba0`
- `0x180021cd0`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x18001b060`
- `0x1800214dc`
- `0x180021be4`
- `0x180022000`
- `0x18002341c`

## string_xrefs

- `0x180021c9d`: `Failed to spawn McpGetAuthorizationHeaderOperation worker thread. hr=%#x`

## pseudocode

```c
__int64 __fastcall McpManager::GetAuthorizationHeaderInternal(
        McpManager *this,
        char a2,
        char a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct IMcpGetAuthorizationHeaderOperation **a7)
{
  struct IMcpGetAuthorizationHeaderOperation **v7; // rdi
  __int64 Error; // rbx
  struct IMcpGetAuthorizationHeaderOperation *v9; // rcx
  int v11; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  McpManager *v13; // [rsp+50h] [rbp+20h] BYREF
  char v14; // [rsp+58h] [rbp+28h] BYREF
  char v15; // [rsp+60h] [rbp+30h] BYREF
  const unsigned __int16 *v16; // [rsp+68h] [rbp+38h] BYREF

  v16 = a4;
  v15 = a3;
  v14 = a2;
  v13 = this;
  v7 = a7;
  if ( a7 )
  {
    *a7 = 0;
    v13 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    LODWORD(Error) = Microsoft::WRL::Details::MakeAndInitialize<McpGetAuthorizationHeaderOperation,McpGetAuthorizationHeaderOperation,bool &,bool &,unsigned short const * &,unsigned short const * &,unsigned short const * &>(
                       (unsigned int)&v13,
                       (unsigned int)&v14,
                       (unsigned int)&v15,
                       (unsigned int)&v16,
                       (__int64)&a5,
                       (__int64)&a6);
    if ( (int)Error >= 0 )
    {
      if ( McpOperationHandler::CreateOperationThread(*((void **)v13 + 41)) )
      {
        v9 = v13;
        v13 = 0;
        *v7 = v9;
      }
      else
      {
        Error = (unsigned int)ResultFromKnownLastError();
        McpManagementTelemetry::WriteDbgTraceWarning(
          "McpManager::GetAuthorizationHeaderInternal",
          L"Failed to spawn McpGetAuthorizationHeaderOperation worker thread. hr=%#x",
          Error);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  }
  else
  {
    LODWORD(Error) = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpmanager.cpp",
      (const char *)0x80004003LL,
      v11);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180021be4  mov     rax, rsp
0x180021be7  mov     [rax+20h], r9
0x180021beb  mov     [rax+18h], r8b
0x180021bef  mov     [rax+10h], dl
0x180021bf2  mov     [rax+8], rcx
0x180021bf6  push    rbp
0x180021bf7  push    rbx
0x180021bf8  push    rdi
0x180021bf9  mov     rbp, rsp
0x180021bfc  sub     rsp, 30h
0x180021c00  mov     rdi, [rbp+arg_30]
0x180021c04  test    rdi, rdi
0x180021c07  jnz     short loc_180021C29
0x180021c09  mov     rcx, [rbp+18h]; this
0x180021c0d  mov     ebx, 80004003h
0x180021c12  mov     r9d, ebx; char *
0x180021c15  lea     r8, aOnecoreuapPrin_10; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180021c1c  lea     edx, [rdi+6Bh]; void *
0x180021c1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021c24  jmp     loc_180021CBA
0x180021c29  mov     qword ptr [rdi], 0
0x180021c30  mov     [rbp+arg_0], 0
0x180021c38  lea     rcx, [rbp+arg_0]
0x180021c3c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021c41  lea     rax, [rbp+arg_28]
0x180021c45  mov     [rsp+30h+var_8], rax
0x180021c4a  lea     rax, [rbp+arg_20]
0x180021c4e  mov     [rsp+30h+var_10], rax
0x180021c53  lea     r9, [rbp+arg_18]
0x180021c57  lea     r8, [rbp+arg_10]
0x180021c5b  lea     rdx, [rbp+arg_8]
0x180021c5f  lea     rcx, [rbp+arg_0]
0x180021c63  call    ??$MakeAndInitialize@VMcpGetAuthorizationHeaderOperation@@V1@AEA_NAEA_NAEAPEBGAEAPEBGAEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAVMcpGetAuthorizationHeaderOperation@@AEA_N1AEAPEBG22@Z; Microsoft::WRL::Details::MakeAndInitialize<McpGetAuthorizationHeaderOperation,McpGetAuthorizationHeaderOperation,bool &,bool &,ushort const * &,ushort const * &,ushort const * &>(McpGetAuthorizationHeaderOperation * *,bool &,bool &,ushort const * &,ushort const * &,ushort const * &)
0x180021c68  mov     ebx, eax
0x180021c6a  test    eax, eax
0x180021c6c  js      short loc_180021CB1
0x180021c6e  mov     rcx, [rbp+arg_0]
0x180021c72  mov     rcx, [rcx+148h]; lpParameter
0x180021c79  call    ?CreateOperationThread@McpOperationHandler@@SA_NPEAX@Z; McpOperationHandler::CreateOperationThread(void *)
0x180021c7e  test    al, al
0x180021c80  jz      short loc_180021C93
0x180021c82  mov     rcx, [rbp+arg_0]
0x180021c86  mov     [rbp+arg_0], 0
0x180021c8e  mov     [rdi], rcx
0x180021c91  jmp     short loc_180021CB1
0x180021c93  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021c98  mov     ebx, eax
0x180021c9a  mov     r8d, eax
0x180021c9d  lea     rdx, aFailedToSpawnM; "Failed to spawn McpGetAuthorizationHead"...
0x180021ca4  lea     rcx, aMcpmanagerGeta; "McpManager::GetAuthorizationHeaderInter"...
0x180021cab  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180021cb0  nop
0x180021cb1  lea     rcx, [rbp+arg_0]
0x180021cb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021cba  mov     eax, ebx
0x180021cbc  add     rsp, 30h
0x180021cc0  pop     rdi
0x180021cc1  pop     rbx
0x180021cc2  pop     rbp
0x180021cc3  retn
```
