# CApxSvc::Cleanup(void)

- ea: `0x180006554`
- end: `0x180006737`
- name: `?Cleanup@CApxSvc@@QEAAJXZ`
- size: `483`
- prototype: `__int64 __fastcall(CApxSvc *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005bc4`
- `0x180006278`
- `0x180006c94`

## callees

- `0x180006140`
- `0x1800061ac`
- `0x18000630c`
- `0x180006554`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006639`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006651`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006651`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800065b5`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800065c7`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800065b5`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800065c7`
- `RPCRT4!RpcBindingVectorFree` at `0x180006649`
- `RPCRT4!RpcBindingVectorFree` at `0x1800066b2`
- `RPCRT4!RpcBindingVectorFree` at `0x180006716`
- `RPCRT4!RpcBindingVectorFree` at `0x180006649`
- `RPCRT4!RpcBindingVectorFree` at `0x1800066b2`
- `RPCRT4!RpcBindingVectorFree` at `0x180006716`
- `RPCRT4!RpcEpUnregister` at `0x1800066c4`
- `RPCRT4!RpcEpUnregister` at `0x1800066d8`
- `RPCRT4!RpcEpUnregister` at `0x1800066c4`
- `RPCRT4!RpcEpUnregister` at `0x1800066d8`
- `RPCRT4!RpcServerInqBindings` at `0x180006622`
- `RPCRT4!RpcServerInqBindings` at `0x180006663`
- `RPCRT4!RpcServerInqBindings` at `0x180006622`
- `RPCRT4!RpcServerInqBindings` at `0x180006663`

## pseudocode

```c
__int64 __fastcall CApxSvc::Cleanup(CApxSvc *this)
{
  unsigned int v2; // ebx
  RPC_BINDING_VECTOR *v3; // rdi
  DWORD LastError; // eax
  DWORD v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  CApxSvc *v9; // [rsp+20h] [rbp-10h] BYREF
  char v10; // [rsp+28h] [rbp-8h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+50h] [rbp+20h] BYREF
  RPC_BINDING_VECTOR *v12; // [rsp+58h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids);
  }
  v9 = this;
  v10 = 1;
  if ( RpcServerUnregisterIfEx(qword_18000A300, 0, 1) )
  {
    v2 = RpcServerUnregisterIfEx(qword_18000A300, 0, 1) | 0x80010000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids, v2);
    }
    goto LABEL_28;
  }
  BindingVector = 0;
  if ( RpcServerInqBindings(&BindingVector) )
  {
    v3 = BindingVector;
    if ( BindingVector )
    {
      LastError = GetLastError();
      v12 = v3;
      v5 = LastError;
      RpcBindingVectorFree(&v12);
      SetLastError(v5);
    }
    BindingVector = 0;
    v2 = RpcServerInqBindings(&BindingVector) | 0x80010000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    v7 = 31;
    goto LABEL_17;
  }
  if ( RpcEpUnregister(qword_18000A300, BindingVector, 0) )
  {
    v2 = RpcEpUnregister(qword_18000A300, BindingVector, 0) | 0x80010000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_18:
      if ( BindingVector )
      {
        v12 = BindingVector;
        RpcBindingVectorFree(&v12);
      }
      goto LABEL_28;
    }
    v7 = 32;
LABEL_17:
    WPP_SF_d(v6[2], v7, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids, v2);
    goto LABEL_18;
  }
  if ( BindingVector )
  {
    v12 = BindingVector;
    RpcBindingVectorFree(&v12);
  }
  v2 = 0;
LABEL_28:
  wil::details::lambda_call__lambda_be34179165920f5a33d2c68e6cbd9a77___::_lambda_call__lambda_be34179165920f5a33d2c68e6cbd9a77___(&v9);
  return v2;
}

```

## disassembly

```asm
0x180006554  mov     [rsp-18h+arg_10], rbx
0x180006559  push    rbp
0x18000655a  push    rdi
0x18000655b  push    r14
0x18000655d  mov     rbp, rsp
0x180006560  sub     rsp, 30h
0x180006564  mov     rbx, rcx
0x180006567  mov     rcx, cs:WPP_GLOBAL_Control
0x18000656e  lea     r14, WPP_GLOBAL_Control
0x180006575  mov     edi, 1
0x18000657a  cmp     rcx, r14
0x18000657d  jz      short loc_18000659E
0x18000657f  test    [rcx+1Ch], dil
0x180006583  jz      short loc_18000659E
0x180006585  cmp     byte ptr [rcx+19h], 5
0x180006589  jb      short loc_18000659E
0x18000658b  mov     rcx, [rcx+10h]
0x18000658f  lea     edx, [rdi+1Bh]
0x180006592  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x180006599  call    WPP_SF_
0x18000659e  mov     [rbp+var_10], rbx
0x1800065a2  mov     r8d, edi; RundownContextHandles
0x1800065a5  lea     rbx, qword_18000A300
0x1800065ac  mov     [rbp+var_8], dil
0x1800065b0  mov     rcx, rbx; IfSpec
0x1800065b3  xor     edx, edx; MgrTypeUuid
0x1800065b5  call    cs:__imp_RpcServerUnregisterIfEx
0x1800065bb  test    eax, eax
0x1800065bd  jz      short loc_180006616
0x1800065bf  mov     r8d, edi; RundownContextHandles
0x1800065c2  xor     edx, edx; MgrTypeUuid
0x1800065c4  mov     rcx, rbx; IfSpec
0x1800065c7  call    cs:__imp_RpcServerUnregisterIfEx
0x1800065cd  mov     ebx, eax
0x1800065cf  or      ebx, 80010000h
0x1800065d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065dc  cmp     rcx, r14
0x1800065df  jz      loc_18000671E
0x1800065e5  test    byte ptr [rcx+1Ch], 80h
0x1800065e9  jz      loc_18000671E
0x1800065ef  cmp     byte ptr [rcx+19h], 2
0x1800065f3  jb      loc_18000671E
0x1800065f9  mov     rcx, [rcx+10h]
0x1800065fd  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x180006604  mov     edx, 1Eh
0x180006609  mov     r9d, ebx
0x18000660c  call    WPP_SF_d
0x180006611  jmp     loc_18000671E
0x180006616  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000661a  mov     [rbp+BindingVector], 0
0x180006622  call    cs:__imp_RpcServerInqBindings
0x180006628  test    eax, eax
0x18000662a  jz      loc_1800066BA
0x180006630  mov     rdi, [rbp+BindingVector]
0x180006634  test    rdi, rdi
0x180006637  jz      short loc_180006657
0x180006639  call    cs:__imp_GetLastError
0x18000663f  lea     rcx, [rbp+arg_8]; BindingVector
0x180006643  mov     [rbp+arg_8], rdi
0x180006647  mov     ebx, eax
0x180006649  call    cs:__imp_RpcBindingVectorFree
0x18000664f  mov     ecx, ebx; dwErrCode
0x180006651  call    cs:__imp_SetLastError
0x180006657  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000665b  mov     [rbp+BindingVector], 0
0x180006663  call    cs:__imp_RpcServerInqBindings
0x180006669  mov     ebx, eax
0x18000666b  or      ebx, 80010000h
0x180006671  mov     rcx, cs:WPP_GLOBAL_Control
0x180006678  cmp     rcx, r14
0x18000667b  jz      short loc_1800066A1
0x18000667d  test    byte ptr [rcx+1Ch], 80h
0x180006681  jz      short loc_1800066A1
0x180006683  cmp     byte ptr [rcx+19h], 2
0x180006687  jb      short loc_1800066A1
0x180006689  mov     edx, 1Fh
0x18000668e  mov     rcx, [rcx+10h]
0x180006692  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x180006699  mov     r9d, ebx
0x18000669c  call    WPP_SF_d
0x1800066a1  mov     rax, [rbp+BindingVector]
0x1800066a5  test    rax, rax
0x1800066a8  jz      short loc_18000671E
0x1800066aa  lea     rcx, [rbp+arg_8]; BindingVector
0x1800066ae  mov     [rbp+arg_8], rax
0x1800066b2  call    cs:__imp_RpcBindingVectorFree
0x1800066b8  jmp     short loc_18000671E
0x1800066ba  mov     rdx, [rbp+BindingVector]; BindingVector
0x1800066be  xor     r8d, r8d; UuidVector
0x1800066c1  mov     rcx, rbx; IfSpec
0x1800066c4  call    cs:__imp_RpcEpUnregister
0x1800066ca  test    eax, eax
0x1800066cc  jz      short loc_180006705
0x1800066ce  mov     rdx, [rbp+BindingVector]; BindingVector
0x1800066d2  xor     r8d, r8d; UuidVector
0x1800066d5  mov     rcx, rbx; IfSpec
0x1800066d8  call    cs:__imp_RpcEpUnregister
0x1800066de  mov     ebx, eax
0x1800066e0  or      ebx, 80010000h
0x1800066e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066ed  cmp     rcx, r14
0x1800066f0  jz      short loc_1800066A1
0x1800066f2  test    byte ptr [rcx+1Ch], 80h
0x1800066f6  jz      short loc_1800066A1
0x1800066f8  cmp     byte ptr [rcx+19h], 2
0x1800066fc  jb      short loc_1800066A1
0x1800066fe  mov     edx, 20h ; ' '
0x180006703  jmp     short loc_18000668E
0x180006705  mov     rax, [rbp+BindingVector]
0x180006709  test    rax, rax
0x18000670c  jz      short loc_18000671C
0x18000670e  lea     rcx, [rbp+arg_8]; BindingVector
0x180006712  mov     [rbp+arg_8], rax
0x180006716  call    cs:__imp_RpcBindingVectorFree
0x18000671c  xor     ebx, ebx
0x18000671e  lea     rcx, [rbp+var_10]
0x180006722  call    wil__details__lambda_call__lambda_be34179165920f5a33d2c68e6cbd9a77______lambda_call__lambda_be34179165920f5a33d2c68e6cbd9a77___
0x180006727  mov     eax, ebx
0x180006729  mov     rbx, [rsp+30h+arg_10]
0x18000672e  add     rsp, 30h
0x180006732  pop     r14
0x180006734  pop     rdi
0x180006735  pop     rbp
0x180006736  retn
```
