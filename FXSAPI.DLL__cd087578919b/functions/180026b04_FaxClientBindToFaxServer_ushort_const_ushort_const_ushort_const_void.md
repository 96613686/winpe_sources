# FaxClientBindToFaxServer(ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x180026b04`
- end: `0x180026dd3`
- name: `?FaxClientBindToFaxServer@@YAKPEBG00PEAPEAX@Z`
- size: `719`
- prototype: `unsigned int __fastcall(wchar_t *String2, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015040`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180026b04`
- `0x180026ef0`
- `0x1800278e8`
- `0x18002795c`
- `0x18002c1e0`
- `0x18002cb24`
- `0x18002ebe4`
- `0x18002f0f0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180026d2a`
- `RPCRT4!RpcStringFreeW` at `0x180026d2a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180026d17`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180026d17`
- `RPCRT4!RpcStringBindingComposeW` at `0x180026cfb`
- `RPCRT4!RpcStringBindingComposeW` at `0x180026cfb`
- `KERNEL32!LocalFree` at `0x180026dad`
- `KERNEL32!LocalFree` at `0x180026dad`
- `KERNEL32!LocalAlloc` at `0x180026bb9`
- `KERNEL32!LocalAlloc` at `0x180026bb9`
- `KERNEL32!GetLastError` at `0x180026ca3`
- `KERNEL32!GetLastError` at `0x180026d68`
- `KERNEL32!GetLastError` at `0x180026ca3`
- `KERNEL32!GetLastError` at `0x180026d68`

## pseudocode

```c
__int64 __fastcall FaxClientBindToFaxServer(
        wchar_t *String2,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void **a4)
{
  unsigned __int16 *v6; // rsi
  int ProductSKU; // eax
  BOOL v8; // edi
  SIZE_T v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbp
  int v12; // ebx
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 *v17; // rbx
  DWORD v18; // eax
  RPC_STATUS v19; // ebx
  int v20; // ecx
  DWORD LastError; // eax
  RPC_WSTR String; // [rsp+70h] [rbp+18h] BYREF

  String = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids);
  }
  *a4 = 0;
  v6 = 0;
  if ( !(unsigned int)IsLocalMachineNameW(String2) )
    v6 = String2;
  v8 = !v6
    && ((ProductSKU = GetProductSKU(), (unsigned int)(ProductSKU - 1) <= 1) || ProductSKU == 32)
    && !(unsigned int)IsWinXPRTMOrSP1FaxService();
  v9 = (-(__int64)v8 & 0xFFFFFFFFFFFFFFF2uLL) + 34;
  v10 = (unsigned __int16 *)LocalAlloc(0, v9);
  v11 = v10;
  if ( !v10 )
    goto LABEL_14;
  if ( v8 )
  {
    v12 = StringCbCopyW(v10, v9, L"SHAREDFAX");
    if ( v12 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 41;
LABEL_21:
        WPP_SF_d(v15[2], v16, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids, (unsigned int)v12);
        goto LABEL_22;
      }
      goto LABEL_22;
    }
    v17 = L"ncalrpc";
  }
  else
  {
    v12 = StringCbPrintfW(v10, v9, L"%s%s", L"\\PIPE\\", L"SHAREDFAX");
    if ( v12 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 42;
        goto LABEL_21;
      }
LABEL_22:
      if ( (v12 & 0x1FFF0000) == 0x70000 )
        v12 = (unsigned __int16)v12;
      goto LABEL_48;
    }
    v17 = L"ncacn_np";
  }
  if ( !v6 )
  {
    if ( (unsigned int)EnsureFaxServiceIsStarted(v14, v13) )
    {
      if ( !(unsigned int)WaitForServiceRPCServer() )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids, LastError);
        }
        goto LABEL_48;
      }
    }
    else
    {
      v18 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids, v18);
      }
    }
  }
  if ( RpcStringBindingComposeW(0, v17, v6, v11, 0, &String) )
  {
LABEL_14:
    v12 = -1073741801;
    goto LABEL_48;
  }
  v19 = RpcBindingFromStringBindingW(String, a4);
  RpcStringFreeW(&String);
  if ( v19 )
  {
    *a4 = 0;
    v20 = 1210;
    if ( (unsigned int)(v19 - 1706) > 1 )
      v20 = -1073741801;
    v12 = v20;
  }
  else
  {
    v12 = 0;
  }
LABEL_48:
  LocalFree(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180026b04  mov     rax, rsp
0x180026b07  mov     [rax+8], rbx
0x180026b0b  mov     [rax+10h], rbp
0x180026b0f  mov     [rax+18h], r8
0x180026b13  push    rsi
0x180026b14  push    rdi
0x180026b15  push    r12
0x180026b17  push    r13
0x180026b19  push    r14
0x180026b1b  sub     rsp, 30h
0x180026b1f  mov     r14, r9
0x180026b22  mov     qword ptr [rax+18h], 0
0x180026b2a  mov     rbx, rcx
0x180026b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b34  lea     r13, WPP_GLOBAL_Control
0x180026b3b  mov     r12d, 1000h
0x180026b41  cmp     rcx, r13
0x180026b44  jz      short loc_180026B67
0x180026b46  test    [rcx+1Ch], r12d
0x180026b4a  jz      short loc_180026B67
0x180026b4c  cmp     byte ptr [rcx+19h], 5
0x180026b50  jb      short loc_180026B67
0x180026b52  mov     rcx, [rcx+10h]
0x180026b56  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180026b5d  mov     edx, 28h ; '('
0x180026b62  call    WPP_SF_
0x180026b67  mov     rcx, rbx; String2
0x180026b6a  mov     qword ptr [r14], 0
0x180026b71  call    IsLocalMachineNameW
0x180026b76  xor     esi, esi
0x180026b78  test    eax, eax
0x180026b7a  cmovz   rsi, rbx
0x180026b7e  test    rsi, rsi
0x180026b81  jnz     short loc_180026BA3
0x180026b83  call    GetProductSKU
0x180026b88  lea     ecx, [rax-1]
0x180026b8b  cmp     ecx, 1
0x180026b8e  jbe     short loc_180026B95
0x180026b90  cmp     eax, 20h ; ' '
0x180026b93  jnz     short loc_180026BA3
0x180026b95  call    ?IsWinXPRTMOrSP1FaxService@@YAHXZ; IsWinXPRTMOrSP1FaxService(void)
0x180026b9a  test    eax, eax
0x180026b9c  jnz     short loc_180026BA3
0x180026b9e  lea     edi, [rax+1]
0x180026ba1  jmp     short loc_180026BA5
0x180026ba3  xor     edi, edi
0x180026ba5  mov     eax, edi
0x180026ba7  neg     eax
0x180026ba9  sbb     rbx, rbx
0x180026bac  xor     ecx, ecx; uFlags
0x180026bae  and     rbx, 0FFFFFFFFFFFFFFF2h
0x180026bb2  add     rbx, 22h ; '"'
0x180026bb6  mov     rdx, rbx; uBytes
0x180026bb9  call    cs:__imp_LocalAlloc
0x180026bc0  nop     dword ptr [rax+rax+00h]
0x180026bc5  mov     rbp, rax
0x180026bc8  test    rax, rax
0x180026bcb  jnz     short loc_180026BD7
0x180026bcd  mov     ebx, 0C0000017h
0x180026bd2  jmp     loc_180026DAA
0x180026bd7  mov     rdx, rbx; unsigned __int64
0x180026bda  mov     rcx, rbp; unsigned __int16 *
0x180026bdd  test    edi, edi
0x180026bdf  jz      short loc_180026C46
0x180026be1  lea     r8, aSharedfax; "SHAREDFAX"
0x180026be8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180026bed  mov     ebx, eax
0x180026bef  test    eax, eax
0x180026bf1  jns     short loc_180026C3D
0x180026bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bfa  cmp     rcx, r13
0x180026bfd  jz      short loc_180026C23
0x180026bff  test    [rcx+1Ch], r12d
0x180026c03  jz      short loc_180026C23
0x180026c05  cmp     byte ptr [rcx+19h], 2
0x180026c09  jb      short loc_180026C23
0x180026c0b  mov     edx, 29h ; ')'
0x180026c10  mov     rcx, [rcx+10h]
0x180026c14  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180026c1b  mov     r9d, ebx
0x180026c1e  call    WPP_SF_d
0x180026c23  mov     eax, ebx
0x180026c25  and     eax, 1FFF0000h
0x180026c2a  cmp     eax, 70000h
0x180026c2f  jnz     loc_180026DAA
0x180026c35  movzx   ebx, bx
0x180026c38  jmp     loc_180026DAA
0x180026c3d  lea     rbx, ProtSeq; "ncalrpc"
0x180026c44  jmp     short loc_180026C91
0x180026c46  lea     rax, aSharedfax; "SHAREDFAX"
0x180026c4d  lea     r9, aPipe; "\\PIPE\\"
0x180026c54  mov     [rsp+58h+Options], rax
0x180026c59  lea     r8, aSS_0; "%s%s"
0x180026c60  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026c65  mov     ebx, eax
0x180026c67  test    eax, eax
0x180026c69  jns     short loc_180026C8A
0x180026c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c72  cmp     rcx, r13
0x180026c75  jz      short loc_180026C23
0x180026c77  test    [rcx+1Ch], r12d
0x180026c7b  jz      short loc_180026C23
0x180026c7d  cmp     byte ptr [rcx+19h], 2
0x180026c81  jb      short loc_180026C23
0x180026c83  mov     edx, 2Ah ; '*'
0x180026c88  jmp     short loc_180026C10
0x180026c8a  lea     rbx, aNcacnNp; "ncacn_np"
0x180026c91  test    rsi, rsi
0x180026c94  jnz     short loc_180026CDD
0x180026c96  call    EnsureFaxServiceIsStarted
0x180026c9b  test    eax, eax
0x180026c9d  jnz     loc_180026D5B
0x180026ca3  call    cs:__imp_GetLastError
0x180026caa  nop     dword ptr [rax+rax+00h]
0x180026caf  mov     rcx, cs:WPP_GLOBAL_Control
0x180026cb6  cmp     rcx, r13
0x180026cb9  jz      short loc_180026CDD
0x180026cbb  test    [rcx+1Ch], r12d
0x180026cbf  jz      short loc_180026CDD
0x180026cc1  cmp     byte ptr [rcx+19h], 2
0x180026cc5  jb      short loc_180026CDD
0x180026cc7  mov     rcx, [rcx+10h]
0x180026ccb  lea     edx, [rsi+2Bh]
0x180026cce  mov     r9d, eax
0x180026cd1  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180026cd8  call    WPP_SF_d
0x180026cdd  lea     rax, [rsp+58h+String]
0x180026ce2  mov     r9, rbp; Endpoint
0x180026ce5  mov     [rsp+58h+StringBinding], rax; StringBinding
0x180026cea  mov     r8, rsi; NetworkAddr
0x180026ced  mov     rdx, rbx; ProtSeq
0x180026cf0  mov     [rsp+58h+Options], 0; Options
0x180026cf9  xor     ecx, ecx; ObjUuid
0x180026cfb  call    cs:__imp_RpcStringBindingComposeW
0x180026d02  nop     dword ptr [rax+rax+00h]
0x180026d07  test    eax, eax
0x180026d09  jnz     loc_180026BCD
0x180026d0f  mov     rcx, [rsp+58h+String]; StringBinding
0x180026d14  mov     rdx, r14; Binding
0x180026d17  call    cs:__imp_RpcBindingFromStringBindingW
0x180026d1e  nop     dword ptr [rax+rax+00h]
0x180026d23  lea     rcx, [rsp+58h+String]; String
0x180026d28  mov     ebx, eax
0x180026d2a  call    cs:__imp_RpcStringFreeW
0x180026d31  nop     dword ptr [rax+rax+00h]
0x180026d36  test    ebx, ebx
0x180026d38  jz      short loc_180026DA8
0x180026d3a  lea     eax, [rbx-6AAh]
0x180026d40  mov     qword ptr [r14], 0
0x180026d47  mov     ebx, 0C0000017h
0x180026d4c  cmp     eax, 1
0x180026d4f  mov     ecx, 4BAh
0x180026d54  cmova   ecx, ebx
0x180026d57  mov     ebx, ecx
0x180026d59  jmp     short loc_180026DAA
0x180026d5b  call    WaitForServiceRPCServer
0x180026d60  test    eax, eax
0x180026d62  jnz     loc_180026CDD
0x180026d68  call    cs:__imp_GetLastError
0x180026d6f  nop     dword ptr [rax+rax+00h]
0x180026d74  mov     ebx, eax
0x180026d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d7d  cmp     rcx, r13
0x180026d80  jz      short loc_180026DAA
0x180026d82  test    [rcx+1Ch], r12d
0x180026d86  jz      short loc_180026DAA
0x180026d88  cmp     byte ptr [rcx+19h], 2
0x180026d8c  jb      short loc_180026DAA
0x180026d8e  mov     rcx, [rcx+10h]
0x180026d92  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180026d99  mov     edx, 2Ch ; ','
0x180026d9e  mov     r9d, eax
0x180026da1  call    WPP_SF_d
0x180026da6  jmp     short loc_180026DAA
0x180026da8  xor     ebx, ebx
0x180026daa  mov     rcx, rbp; hMem
0x180026dad  call    cs:__imp_LocalFree
0x180026db4  nop     dword ptr [rax+rax+00h]
0x180026db9  mov     rbp, [rsp+58h+arg_8]
0x180026dbe  mov     eax, ebx
0x180026dc0  mov     rbx, [rsp+58h+arg_0]
0x180026dc5  add     rsp, 30h
0x180026dc9  pop     r14
0x180026dcb  pop     r13
0x180026dcd  pop     r12
0x180026dcf  pop     rdi
0x180026dd0  pop     rsi
0x180026dd1  retn
```
